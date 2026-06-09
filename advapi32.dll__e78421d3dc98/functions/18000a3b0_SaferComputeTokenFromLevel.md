# SaferComputeTokenFromLevel

- ea: `0x18000a3b0`
- end: `0x18000a677`
- name: `SaferComputeTokenFromLevel`
- size: `711`
- prototype: `BOOL __stdcall(SAFER_LEVEL_HANDLE LevelHandle, HANDLE InAccessToken, PHANDLE OutAccessToken, DWORD dwFlags, LPVOID lpReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x18000a204`
- `0x18000a2cc`
- `0x18000a3b0`
- `0x18000a680`
- `0x18000a78c`
- `0x18000b340`
- `0x18000e4fc`
- `0x180045d7c`
- `0x180065090`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x18000a531`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000a531`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000a547`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000a547`
- `ntdll!NtDuplicateToken` at `0x18000a59d`
- `ntdll!NtDuplicateToken` at `0x18000a59d`
- `ntdll!NtQueryInformationToken` at `0x18000a5f4`
- `ntdll!NtQueryInformationToken` at `0x18000a5f4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a49d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a49d`
- `ntdll!RtlEnterCriticalSection` at `0x18000a43b`
- `ntdll!RtlEnterCriticalSection` at `0x18000a43b`
- `KERNEL32!LocalFree` at `0x18000a5a8`
- `KERNEL32!LocalFree` at `0x18000a5a8`
- `KERNEL32!BaseSetLastNTError` at `0x18000a4e8`
- `KERNEL32!BaseSetLastNTError` at `0x18000a4e8`
- `KERNEL32!SetLastError` at `0x18000a653`
- `KERNEL32!SetLastError` at `0x18000a653`

## pseudocode

```c
BOOL __stdcall SaferComputeTokenFromLevel(
        SAFER_LEVEL_HANDLE LevelHandle,
        HANDLE InAccessToken,
        PHANDLE OutAccessToken,
        DWORD dwFlags,
        LPVOID lpReserved)
{
  char v5; // r15
  __int64 v9; // rcx
  NTSTATUS v10; // ebx
  __int64 v11; // r14
  NTSTATUS v12; // eax
  PSID *v14; // r14
  DWORD v15; // ecx
  __int64 v16; // [rsp+30h] [rbp-61h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-59h] BYREF
  ULONG ReturnLength; // [rsp+3Ch] [rbp-55h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-51h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v21; // [rsp+90h] [rbp-1h]
  __int64 v22; // [rsp+98h] [rbp+7h] BYREF
  int v23; // [rsp+A0h] [rbp+Fh]

  v5 = dwFlags;
  v16 = 0;
  v22 = 0;
  v23 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v21 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !g_bInitializedFirstTime )
    goto LABEL_14;
  if ( !LevelHandle )
  {
    v10 = -1073741816;
    goto LABEL_15;
  }
  if ( (unsigned int)IsSaferDisabled() )
  {
    if ( (v5 & 1) != 0 )
    {
      *OutAccessToken = 0;
      return 1;
    }
    v14 = (PSID *)CodeAuthzpGetTokenInformation(InAccessToken, TokenUser);
    if ( v14 )
    {
      v22 = 12;
      LOWORD(v23) = 1;
      v10 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v10 >= 0 )
      {
        v10 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *v14, 0);
        if ( v10 >= 0 )
        {
          ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
          ObjectAttributes.Length = 48;
          ObjectAttributes.SecurityQualityOfService = &v22;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 2;
          ObjectAttributes.ObjectName = 0;
          v10 = NtDuplicateToken(InAccessToken, 0xF01FFu, &ObjectAttributes, 0, TokenPrimary, OutAccessToken);
        }
      }
      LocalFree(v14);
      goto LABEL_10;
    }
LABEL_14:
    v10 = -1073741823;
    goto LABEL_15;
  }
  RtlEnterCriticalSection(&g_TableCritSec);
  v10 = CodeAuthzHandleToLevelStruct(LevelHandle, &v16);
  if ( v10 >= 0 )
  {
    v11 = CodeAuthzLevelObjpLookupByLevelId(v9, *(unsigned int *)(v16 + 8));
    if ( v11 )
    {
      if ( (v5 & 2) != 0 )
      {
        TokenInformation = 0;
        ReturnLength = 0;
        if ( !InAccessToken )
        {
          v10 = -1073741811;
          goto LABEL_9;
        }
        v10 = NtQueryInformationToken(InAccessToken, TokenSandBoxInert, &TokenInformation, 4u, &ReturnLength);
        if ( v10 < 0 )
        {
          v10 = -1073741823;
          goto LABEL_9;
        }
        if ( TokenInformation )
        {
          *(_DWORD *)lpReserved = 1;
          goto LABEL_9;
        }
        v12 = _CodeAuthzpCompareCodeAuthzLevelWithToken(v16, v11, InAccessToken, lpReserved);
      }
      else
      {
        v12 = _CodeAuthzpComputeAccessTokenFromCodeAuthzObject(
                v11,
                InAccessToken,
                OutAccessToken,
                v5,
                (int *)lpReserved,
                v16);
      }
      v10 = v12;
    }
    else
    {
      v10 = -1073741816;
    }
  }
LABEL_9:
  RtlLeaveCriticalSection(&g_TableCritSec);
LABEL_10:
  if ( v10 == -1 )
  {
    if ( !v16 || (v15 = 786, (*(_DWORD *)(v16 + 552) & 0x2000) == 0) )
      v15 = 1260;
    SetLastError(v15);
    return 0;
  }
  if ( v10 == 1073741874 )
  {
    SaferpRecordEventLogEntryHelper(1073741874, v16 + 32, v16 + 16, 0);
    return 1;
  }
  if ( v10 >= 0 )
    return 1;
LABEL_15:
  BaseSetLastNTError((unsigned int)v10);
  return 0;
}

```

## disassembly

```asm
0x18000a3b0  push    rbp; ComputeAccessTokenFromCodeAuthzLevel
0x18000a3b2  push    rbx
0x18000a3b3  push    rsi
0x18000a3b4  push    r12
0x18000a3b6  push    r13
0x18000a3b8  push    r14
0x18000a3ba  push    r15
0x18000a3bc  lea     rbp, [rsp-1Fh]
0x18000a3c1  sub     rsp, 0B0h
0x18000a3c8  mov     rax, cs:__security_cookie
0x18000a3cf  xor     rax, rsp
0x18000a3d2  mov     [rbp+4Fh+var_38], rax
0x18000a3d6  mov     r12, [rbp+4Fh+lpReserved]
0x18000a3da  xorps   xmm0, xmm0
0x18000a3dd  xor     eax, eax
0x18000a3df  xor     r14d, r14d
0x18000a3e2  cmp     cs:g_bInitializedFirstTime, r14b
0x18000a3e9  mov     r15d, r9d
0x18000a3ec  mov     r13, r8
0x18000a3ef  mov     [rbp+4Fh+var_B0], r14
0x18000a3f3  mov     rsi, rdx
0x18000a3f6  mov     [rbp+4Fh+var_48], rax
0x18000a3fa  mov     rbx, rcx
0x18000a3fd  mov     [rbp+4Fh+var_40], eax
0x18000a400  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000a404  mov     [rbp+4Fh+var_50], rax
0x18000a408  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000a40c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a410  movups  [rbp+4Fh+SecurityDescriptor], xmm0
0x18000a414  movups  [rbp+4Fh+var_60], xmm0
0x18000a418  jz      loc_18000A4E1
0x18000a41e  test    rcx, rcx
0x18000a421  jz      loc_18000A4F2
0x18000a427  call    IsSaferDisabled
0x18000a42c  test    eax, eax
0x18000a42e  jnz     loc_18000A4F9
0x18000a434  lea     rcx, g_TableCritSec; CriticalSection
0x18000a43b  call    cs:__imp_RtlEnterCriticalSection
0x18000a441  lea     rdx, [rbp+4Fh+var_B0]
0x18000a445  mov     rcx, rbx
0x18000a448  call    CodeAuthzHandleToLevelStruct
0x18000a44d  mov     ebx, eax
0x18000a44f  test    eax, eax
0x18000a451  js      short loc_18000A496
0x18000a453  mov     rdx, [rbp+4Fh+var_B0]
0x18000a457  mov     edx, [rdx+8]
0x18000a45a  call    CodeAuthzLevelObjpLookupByLevelId
0x18000a45f  mov     r14, rax
0x18000a462  test    rax, rax
0x18000a465  jz      loc_18000A5B3
0x18000a46b  test    r15b, 2
0x18000a46f  jnz     loc_18000A5BD
0x18000a475  mov     rax, [rbp+4Fh+var_B0]
0x18000a479  mov     r9d, r15d
0x18000a47c  mov     [rsp+0E0h+NewTokenHandle], rax
0x18000a481  mov     r8, r13
0x18000a484  mov     rdx, rsi
0x18000a487  mov     qword ptr [rsp+0E0h+TokenType], r12
0x18000a48c  mov     rcx, r14
0x18000a48f  call    __CodeAuthzpComputeAccessTokenFromCodeAuthzObject
0x18000a494  mov     ebx, eax
0x18000a496  lea     rcx, g_TableCritSec; CriticalSection
0x18000a49d  call    cs:__imp_RtlLeaveCriticalSection
0x18000a4a3  cmp     ebx, 0FFFFFFFFh
0x18000a4a6  jz      loc_18000A634
0x18000a4ac  mov     ecx, 40000032h
0x18000a4b1  cmp     ebx, ecx
0x18000a4b3  jz      loc_18000A65E
0x18000a4b9  test    ebx, ebx
0x18000a4bb  js      short loc_18000A4E6
0x18000a4bd  mov     eax, 1
0x18000a4c2  mov     rcx, [rbp+4Fh+var_38]
0x18000a4c6  xor     rcx, rsp; StackCookie
0x18000a4c9  call    __security_check_cookie
0x18000a4ce  add     rsp, 0B0h
0x18000a4d5  pop     r15
0x18000a4d7  pop     r14
0x18000a4d9  pop     r13
0x18000a4db  pop     r12
0x18000a4dd  pop     rsi
0x18000a4de  pop     rbx
0x18000a4df  pop     rbp
0x18000a4e0  retn
0x18000a4e1  mov     ebx, 0C0000001h
0x18000a4e6  mov     ecx, ebx
0x18000a4e8  call    cs:__imp_BaseSetLastNTError
0x18000a4ee  xor     eax, eax
0x18000a4f0  jmp     short loc_18000A4C2
0x18000a4f2  mov     ebx, 0C0000008h
0x18000a4f7  jmp     short loc_18000A4E6
0x18000a4f9  test    r15b, 1
0x18000a4fd  jz      short loc_18000A505
0x18000a4ff  mov     [r13+0], r14
0x18000a503  jmp     short loc_18000A4BD
0x18000a505  mov     edx, 1; TokenInformationClass
0x18000a50a  mov     rcx, rsi; TokenHandle
0x18000a50d  call    CodeAuthzpGetTokenInformation
0x18000a512  mov     r14, rax
0x18000a515  test    rax, rax
0x18000a518  jz      short loc_18000A4E1
0x18000a51a  mov     edx, 1; Revision
0x18000a51f  mov     [rbp+4Fh+var_48], 0Ch
0x18000a527  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000a52b  mov     word ptr [rbp+4Fh+var_40], 1
0x18000a531  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000a537  mov     ebx, eax
0x18000a539  test    eax, eax
0x18000a53b  js      short loc_18000A5A5
0x18000a53d  mov     rdx, [r14]; Owner
0x18000a540  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000a544  xor     r8d, r8d; OwnerDefaulted
0x18000a547  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000a54d  mov     ebx, eax
0x18000a54f  test    eax, eax
0x18000a551  js      short loc_18000A5A5
0x18000a553  lea     rax, [rbp+4Fh+SecurityDescriptor]
0x18000a557  mov     [rsp+0E0h+NewTokenHandle], r13; NewTokenHandle
0x18000a55c  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x18000a560  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a564  lea     rax, [rbp+4Fh+var_48]
0x18000a568  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a56f  xor     r9d, r9d; EffectiveOnly
0x18000a572  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x18000a576  mov     edx, 0F01FFh; DesiredAccess
0x18000a57b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18000a583  mov     rcx, rsi; ExistingTokenHandle
0x18000a586  mov     [rbp+4Fh+ObjectAttributes.Attributes], 2
0x18000a58d  mov     [rbp+4Fh+ObjectAttributes.ObjectName], 0
0x18000a595  mov     [rsp+0E0h+TokenType], 1; TokenType
0x18000a59d  call    cs:__imp_NtDuplicateToken
0x18000a5a3  mov     ebx, eax
0x18000a5a5  mov     rcx, r14; hMem
0x18000a5a8  call    cs:__imp_LocalFree
0x18000a5ae  jmp     loc_18000A4A3
0x18000a5b3  mov     ebx, 0C0000008h
0x18000a5b8  jmp     loc_18000A496
0x18000a5bd  mov     [rbp+4Fh+TokenInformation], 0
0x18000a5c4  mov     [rbp+4Fh+ReturnLength], 0
0x18000a5cb  test    rsi, rsi
0x18000a5ce  jnz     short loc_18000A5DA
0x18000a5d0  mov     ebx, 0C000000Dh
0x18000a5d5  jmp     loc_18000A496
0x18000a5da  mov     r9d, 4; TokenInformationLength
0x18000a5e0  lea     rax, [rbp+4Fh+ReturnLength]
0x18000a5e4  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18000a5e8  mov     qword ptr [rsp+0E0h+TokenType], rax; ReturnLength
0x18000a5ed  mov     rcx, rsi; TokenHandle
0x18000a5f0  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000a5f4  call    cs:__imp_NtQueryInformationToken
0x18000a5fa  mov     ebx, eax
0x18000a5fc  test    eax, eax
0x18000a5fe  js      short loc_18000A62A
0x18000a600  cmp     [rbp+4Fh+TokenInformation], 0
0x18000a604  jz      short loc_18000A613
0x18000a606  mov     dword ptr [r12], 1
0x18000a60e  jmp     loc_18000A496
0x18000a613  mov     rcx, [rbp+4Fh+var_B0]
0x18000a617  mov     r9, r12
0x18000a61a  mov     r8, rsi
0x18000a61d  mov     rdx, r14
0x18000a620  call    __CodeAuthzpCompareCodeAuthzLevelWithToken
0x18000a625  jmp     loc_18000A494
0x18000a62a  mov     ebx, 0C0000001h
0x18000a62f  jmp     loc_18000A496
0x18000a634  mov     rax, [rbp+4Fh+var_B0]
0x18000a638  test    rax, rax
0x18000a63b  jz      short loc_18000A64E
0x18000a63d  test    dword ptr [rax+228h], 2000h
0x18000a647  mov     ecx, 312h
0x18000a64c  jnz     short loc_18000A653
0x18000a64e  mov     ecx, 4ECh; dwErrCode
0x18000a653  call    cs:__imp_SetLastError
0x18000a659  jmp     loc_18000A4EE
0x18000a65e  mov     rdx, [rbp+4Fh+var_B0]
0x18000a662  xor     r9d, r9d
0x18000a665  lea     r8, [rdx+10h]
0x18000a669  add     rdx, 20h ; ' '
0x18000a66d  call    SaferpRecordEventLogEntryHelper
0x18000a672  jmp     loc_18000A4BD
```
