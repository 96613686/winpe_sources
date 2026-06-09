# DeviceHelperIsCapabilityPresentForProcessId

- ea: `0x180013348`
- end: `0x1800134d6`
- name: `DeviceHelperIsCapabilityPresentForProcessId`
- size: `398`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a1e0`

## callees

- `0x180004c70`
- `0x180013348`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800133e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800133e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013405`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013405`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001343c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001343c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800133c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800133c6`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800133b6`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800133b6`
- `ntdll!RtlInitUnicodeString` at `0x1800133a4`
- `ntdll!RtlInitUnicodeString` at `0x1800133a4`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001345b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001345b`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180013477`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180013477`

## pseudocode

```c
char __fastcall DeviceHelperIsCapabilityPresentForProcessId(DWORD dwProcessId)
{
  HANDLE v2; // rax
  void *v3; // rsi
  bool v4; // bl
  char v5; // di
  _BYTE v7[4]; // [rsp+30h] [rbp-69h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-65h] BYREF
  int v9; // [rsp+38h] [rbp-61h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-59h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v14[48]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v15[48]; // [rsp+98h] [rbp-1h] BYREF

  TokenHandle = 0;
  hObject = 0;
  ReturnLength = 0;
  TokenInformation = 1;
  DestinationString = 0;
  v7[0] = 0;
  v9 = 0;
  RtlInitUnicodeString(&DestinationString, L"hidTelephony");
  RtlDeriveCapabilitySidsFromName(&DestinationString, v15, v14);
  v2 = OpenProcess(0x1000u, 0, dwProcessId);
  v3 = v2;
  v4 = v2
    && OpenProcessToken(v2, 0xEu, &TokenHandle)
    && GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
    && TokenInformation != 0;
  v5 = DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &hObject) && v4;
  if ( !v5 )
  {
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
  if ( (int)CapabilityCheck(hObject, L"hidTelephony", v7) < 0 || !v7[0] )
  {
    if ( (unsigned int)CheckTokenCapability(hObject, v14, &v9) && v9 )
    {
      v5 = 1;
      goto LABEL_13;
    }
    goto LABEL_12;
  }
LABEL_13:
  if ( v3 )
    CloseHandle(v3);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x180013348  push    rbp
0x18001334a  push    rbx
0x18001334b  push    rsi
0x18001334c  push    rdi
0x18001334d  lea     rbp, [rsp-3Fh]
0x180013352  sub     rsp, 0D8h
0x180013359  mov     rax, cs:__security_cookie
0x180013360  xor     rax, rsp
0x180013363  mov     [rbp+57h+var_28], rax
0x180013367  mov     ebx, ecx
0x180013369  mov     [rbp+57h+TokenHandle], 0
0x180013371  xorps   xmm0, xmm0
0x180013374  mov     [rbp+57h+hObject], 0
0x18001337c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180013380  mov     [rbp+57h+var_A0], 0
0x180013387  lea     rdx, SourceString; "hidTelephony"
0x18001338e  mov     [rbp+57h+TokenInformation], 1
0x180013395  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180013399  mov     [rbp+57h+var_C0], 0
0x18001339d  mov     [rbp+57h+var_B8], 0
0x1800133a4  call    cs:__imp_RtlInitUnicodeString
0x1800133aa  lea     r8, [rbp+57h+var_88]
0x1800133ae  lea     rdx, [rbp+57h+var_58]
0x1800133b2  lea     rcx, [rbp+57h+DestinationString]
0x1800133b6  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800133bc  mov     r8d, ebx; dwProcessId
0x1800133bf  xor     edx, edx; bInheritHandle
0x1800133c1  mov     ecx, 1000h; dwDesiredAccess
0x1800133c6  call    cs:__imp_OpenProcess
0x1800133cc  mov     rsi, rax
0x1800133cf  test    rax, rax
0x1800133d2  jz      short loc_18001340F
0x1800133d4  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800133d8  mov     edx, 0Eh; DesiredAccess
0x1800133dd  mov     rcx, rax; ProcessHandle
0x1800133e0  call    cs:__imp_OpenProcessToken
0x1800133e6  test    eax, eax
0x1800133e8  jz      short loc_18001340F
0x1800133ea  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800133ee  lea     rax, [rbp+57h+var_A0]
0x1800133f2  mov     r9d, 4; TokenInformationLength
0x1800133f8  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x1800133fd  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180013401  lea     edx, [r9+19h]; TokenInformationClass
0x180013405  call    cs:__imp_GetTokenInformation
0x18001340b  test    eax, eax
0x18001340d  jnz     short loc_180013413
0x18001340f  xor     bl, bl
0x180013411  jmp     short loc_18001341D
0x180013413  mov     eax, [rbp+57h+TokenInformation]
0x180013416  neg     eax
0x180013418  sbb     bl, bl
0x18001341a  and     bl, 1
0x18001341d  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x180013421  lea     rax, [rbp+57h+hObject]
0x180013425  mov     r9d, 2; ImpersonationLevel
0x18001342b  mov     [rsp+0F0h+phNewToken], rax; phNewToken
0x180013430  xor     r8d, r8d; lpTokenAttributes
0x180013433  mov     dword ptr [rsp+0F0h+ReturnLength], r9d; TokenType
0x180013438  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18001343c  call    cs:__imp_DuplicateTokenEx
0x180013442  neg     eax
0x180013444  sbb     dil, dil
0x180013447  and     dil, bl
0x18001344a  jz      short loc_18001348C
0x18001344c  mov     rcx, [rbp+57h+hObject]
0x180013450  lea     r8, [rbp+57h+var_C0]
0x180013454  lea     rdx, SourceString; "hidTelephony"
0x18001345b  call    cs:__imp_CapabilityCheck
0x180013461  test    eax, eax
0x180013463  js      short loc_18001346B
0x180013465  cmp     [rbp+57h+var_C0], 0
0x180013469  jnz     short loc_18001348F
0x18001346b  mov     rcx, [rbp+57h+hObject]
0x18001346f  lea     r8, [rbp+57h+var_B8]
0x180013473  lea     rdx, [rbp+57h+var_88]
0x180013477  call    cs:__imp_CheckTokenCapability
0x18001347d  test    eax, eax
0x18001347f  jz      short loc_18001348C
0x180013481  cmp     [rbp+57h+var_B8], 0
0x180013485  jz      short loc_18001348C
0x180013487  mov     dil, 1
0x18001348a  jmp     short loc_18001348F
0x18001348c  xor     dil, dil
0x18001348f  test    rsi, rsi
0x180013492  jz      short loc_18001349D
0x180013494  mov     rcx, rsi; hObject
0x180013497  call    cs:__imp_CloseHandle
0x18001349d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800134a1  test    rcx, rcx
0x1800134a4  jz      short loc_1800134AC
0x1800134a6  call    cs:__imp_CloseHandle
0x1800134ac  mov     rcx, [rbp+57h+hObject]; hObject
0x1800134b0  test    rcx, rcx
0x1800134b3  jz      short loc_1800134BB
0x1800134b5  call    cs:__imp_CloseHandle
0x1800134bb  mov     al, dil
0x1800134be  mov     rcx, [rbp+57h+var_28]
0x1800134c2  xor     rcx, rsp; StackCookie
0x1800134c5  call    __security_check_cookie
0x1800134ca  add     rsp, 0D8h
0x1800134d1  pop     rdi
0x1800134d2  pop     rsi
0x1800134d3  pop     rbx
0x1800134d4  pop     rbp
0x1800134d5  retn
```
