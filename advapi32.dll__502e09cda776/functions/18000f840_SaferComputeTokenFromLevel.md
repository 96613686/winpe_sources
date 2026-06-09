# SaferComputeTokenFromLevel

- ea: `0x18000f840`
- end: `0x18000fb3e`
- name: `SaferComputeTokenFromLevel`
- size: `766`
- prototype: `BOOL __stdcall(SAFER_LEVEL_HANDLE LevelHandle, HANDLE InAccessToken, PHANDLE OutAccessToken, DWORD dwFlags, LPVOID lpReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015bd0`

## callees

- `0x18000f660`
- `0x18000f73c`
- `0x18000f840`
- `0x18000fb50`
- `0x18000fc88`
- `0x180010910`
- `0x180013f20`
- `0x18004b568`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x18000f9d4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000f9d4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000f9f0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000f9f0`
- `ntdll!NtDuplicateToken` at `0x18000fa4c`
- `ntdll!NtDuplicateToken` at `0x18000fa4c`
- `ntdll!NtQueryInformationToken` at `0x18000faaf`
- `ntdll!NtQueryInformationToken` at `0x18000faaf`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f933`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f933`
- `ntdll!RtlEnterCriticalSection` at `0x18000f8cb`
- `ntdll!RtlEnterCriticalSection` at `0x18000f8cb`
- `KERNEL32!LocalFree` at `0x18000fa5d`
- `KERNEL32!LocalFree` at `0x18000fa5d`
- `KERNEL32!BaseSetLastNTError` at `0x18000f985`
- `KERNEL32!BaseSetLastNTError` at `0x18000f985`
- `KERNEL32!SetLastError` at `0x18000fb14`
- `KERNEL32!SetLastError` at `0x18000fb14`

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
0x18000f840  push    rbp; ComputeAccessTokenFromCodeAuthzLevel
0x18000f842  push    rbx
0x18000f843  push    rsi
0x18000f844  push    r12
0x18000f846  push    r13
0x18000f848  push    r14
0x18000f84a  push    r15
0x18000f84c  lea     rbp, [rsp-1Fh]
0x18000f851  sub     rsp, 0B0h
0x18000f858  mov     rax, cs:__security_cookie
0x18000f85f  xor     rax, rsp
0x18000f862  mov     [rbp+4Fh+var_38], rax
0x18000f866  mov     r12, [rbp+4Fh+lpReserved]
0x18000f86a  xorps   xmm0, xmm0
0x18000f86d  xor     eax, eax
0x18000f86f  xor     r14d, r14d
0x18000f872  cmp     cs:g_bInitializedFirstTime, r14b
0x18000f879  mov     r15d, r9d
0x18000f87c  mov     r13, r8
0x18000f87f  mov     [rbp+4Fh+var_B0], r14
0x18000f883  mov     rsi, rdx
0x18000f886  mov     [rbp+4Fh+var_48], rax
0x18000f88a  mov     rbx, rcx
0x18000f88d  mov     [rbp+4Fh+var_40], eax
0x18000f890  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000f894  mov     [rbp+4Fh+var_50], rax
0x18000f898  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000f89c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f8a0  movups  [rbp+4Fh+SecurityDescriptor], xmm0
0x18000f8a4  movups  [rbp+4Fh+var_60], xmm0
0x18000f8a8  jz      loc_18000F97E
0x18000f8ae  test    rcx, rcx
0x18000f8b1  jz      loc_18000F995
0x18000f8b7  call    IsSaferDisabled
0x18000f8bc  test    eax, eax
0x18000f8be  jnz     loc_18000F99C
0x18000f8c4  lea     rcx, g_TableCritSec; CriticalSection
0x18000f8cb  call    cs:__imp_RtlEnterCriticalSection
0x18000f8d2  nop     dword ptr [rax+rax+00h]
0x18000f8d7  lea     rdx, [rbp+4Fh+var_B0]
0x18000f8db  mov     rcx, rbx
0x18000f8de  call    CodeAuthzHandleToLevelStruct
0x18000f8e3  mov     ebx, eax
0x18000f8e5  test    eax, eax
0x18000f8e7  js      short loc_18000F92C
0x18000f8e9  mov     rdx, [rbp+4Fh+var_B0]
0x18000f8ed  mov     edx, [rdx+8]
0x18000f8f0  call    CodeAuthzLevelObjpLookupByLevelId
0x18000f8f5  mov     r14, rax
0x18000f8f8  test    rax, rax
0x18000f8fb  jz      loc_18000FA6E
0x18000f901  test    r15b, 2
0x18000f905  jnz     loc_18000FA78
0x18000f90b  mov     rax, [rbp+4Fh+var_B0]
0x18000f90f  mov     r9d, r15d
0x18000f912  mov     [rsp+0E0h+NewTokenHandle], rax
0x18000f917  mov     r8, r13
0x18000f91a  mov     rdx, rsi
0x18000f91d  mov     qword ptr [rsp+0E0h+TokenType], r12
0x18000f922  mov     rcx, r14
0x18000f925  call    __CodeAuthzpComputeAccessTokenFromCodeAuthzObject
0x18000f92a  mov     ebx, eax
0x18000f92c  lea     rcx, g_TableCritSec; CriticalSection
0x18000f933  call    cs:__imp_RtlLeaveCriticalSection
0x18000f93a  nop     dword ptr [rax+rax+00h]
0x18000f93f  cmp     ebx, 0FFFFFFFFh
0x18000f942  jz      loc_18000FAF5
0x18000f948  mov     ecx, 40000032h
0x18000f94d  cmp     ebx, ecx
0x18000f94f  jz      loc_18000FB25
0x18000f955  test    ebx, ebx
0x18000f957  js      short loc_18000F983
0x18000f959  mov     eax, 1
0x18000f95e  mov     rcx, [rbp+4Fh+var_38]
0x18000f962  xor     rcx, rsp; StackCookie
0x18000f965  call    __security_check_cookie
0x18000f96a  add     rsp, 0B0h
0x18000f971  pop     r15
0x18000f973  pop     r14
0x18000f975  pop     r13
0x18000f977  pop     r12
0x18000f979  pop     rsi
0x18000f97a  pop     rbx
0x18000f97b  pop     rbp
0x18000f97c  retn
0x18000f97e  mov     ebx, 0C0000001h
0x18000f983  mov     ecx, ebx
0x18000f985  call    cs:__imp_BaseSetLastNTError
0x18000f98c  nop     dword ptr [rax+rax+00h]
0x18000f991  xor     eax, eax
0x18000f993  jmp     short loc_18000F95E
0x18000f995  mov     ebx, 0C0000008h
0x18000f99a  jmp     short loc_18000F983
0x18000f99c  test    r15b, 1
0x18000f9a0  jz      short loc_18000F9A8
0x18000f9a2  mov     [r13+0], r14
0x18000f9a6  jmp     short loc_18000F959
0x18000f9a8  mov     edx, 1; TokenInformationClass
0x18000f9ad  mov     rcx, rsi; TokenHandle
0x18000f9b0  call    CodeAuthzpGetTokenInformation
0x18000f9b5  mov     r14, rax
0x18000f9b8  test    rax, rax
0x18000f9bb  jz      short loc_18000F97E
0x18000f9bd  mov     edx, 1; Revision
0x18000f9c2  mov     [rbp+4Fh+var_48], 0Ch
0x18000f9ca  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000f9ce  mov     word ptr [rbp+4Fh+var_40], 1
0x18000f9d4  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000f9db  nop     dword ptr [rax+rax+00h]
0x18000f9e0  mov     ebx, eax
0x18000f9e2  test    eax, eax
0x18000f9e4  js      short loc_18000FA5A
0x18000f9e6  mov     rdx, [r14]; Owner
0x18000f9e9  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000f9ed  xor     r8d, r8d; OwnerDefaulted
0x18000f9f0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000f9f7  nop     dword ptr [rax+rax+00h]
0x18000f9fc  mov     ebx, eax
0x18000f9fe  test    eax, eax
0x18000fa00  js      short loc_18000FA5A
0x18000fa02  lea     rax, [rbp+4Fh+SecurityDescriptor]
0x18000fa06  mov     [rsp+0E0h+NewTokenHandle], r13; NewTokenHandle
0x18000fa0b  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x18000fa0f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000fa13  lea     rax, [rbp+4Fh+var_48]
0x18000fa17  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000fa1e  xor     r9d, r9d; EffectiveOnly
0x18000fa21  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x18000fa25  mov     edx, 0F01FFh; DesiredAccess
0x18000fa2a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18000fa32  mov     rcx, rsi; ExistingTokenHandle
0x18000fa35  mov     [rbp+4Fh+ObjectAttributes.Attributes], 2
0x18000fa3c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], 0
0x18000fa44  mov     [rsp+0E0h+TokenType], 1; TokenType
0x18000fa4c  call    cs:__imp_NtDuplicateToken
0x18000fa53  nop     dword ptr [rax+rax+00h]
0x18000fa58  mov     ebx, eax
0x18000fa5a  mov     rcx, r14; hMem
0x18000fa5d  call    cs:__imp_LocalFree
0x18000fa64  nop     dword ptr [rax+rax+00h]
0x18000fa69  jmp     loc_18000F93F
0x18000fa6e  mov     ebx, 0C0000008h
0x18000fa73  jmp     loc_18000F92C
0x18000fa78  mov     [rbp+4Fh+TokenInformation], 0
0x18000fa7f  mov     [rbp+4Fh+ReturnLength], 0
0x18000fa86  test    rsi, rsi
0x18000fa89  jnz     short loc_18000FA95
0x18000fa8b  mov     ebx, 0C000000Dh
0x18000fa90  jmp     loc_18000F92C
0x18000fa95  mov     r9d, 4; TokenInformationLength
0x18000fa9b  lea     rax, [rbp+4Fh+ReturnLength]
0x18000fa9f  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18000faa3  mov     qword ptr [rsp+0E0h+TokenType], rax; ReturnLength
0x18000faa8  mov     rcx, rsi; TokenHandle
0x18000faab  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000faaf  call    cs:__imp_NtQueryInformationToken
0x18000fab6  nop     dword ptr [rax+rax+00h]
0x18000fabb  mov     ebx, eax
0x18000fabd  test    eax, eax
0x18000fabf  js      short loc_18000FAEB
0x18000fac1  cmp     [rbp+4Fh+TokenInformation], 0
0x18000fac5  jz      short loc_18000FAD4
0x18000fac7  mov     dword ptr [r12], 1
0x18000facf  jmp     loc_18000F92C
0x18000fad4  mov     rcx, [rbp+4Fh+var_B0]
0x18000fad8  mov     r9, r12
0x18000fadb  mov     r8, rsi
0x18000fade  mov     rdx, r14
0x18000fae1  call    __CodeAuthzpCompareCodeAuthzLevelWithToken
0x18000fae6  jmp     loc_18000F92A
0x18000faeb  mov     ebx, 0C0000001h
0x18000faf0  jmp     loc_18000F92C
0x18000faf5  mov     rax, [rbp+4Fh+var_B0]
0x18000faf9  test    rax, rax
0x18000fafc  jz      short loc_18000FB0F
0x18000fafe  test    dword ptr [rax+228h], 2000h
0x18000fb08  mov     ecx, 312h
0x18000fb0d  jnz     short loc_18000FB14
0x18000fb0f  mov     ecx, 4ECh; dwErrCode
0x18000fb14  call    cs:__imp_SetLastError
0x18000fb1b  nop     dword ptr [rax+rax+00h]
0x18000fb20  jmp     loc_18000F991
0x18000fb25  mov     rdx, [rbp+4Fh+var_B0]
0x18000fb29  xor     r9d, r9d
0x18000fb2c  lea     r8, [rdx+10h]
0x18000fb30  add     rdx, 20h ; ' '
0x18000fb34  call    SaferpRecordEventLogEntryHelper
0x18000fb39  jmp     loc_18000F959
```
