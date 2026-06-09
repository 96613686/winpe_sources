# EnableAllPrivileges(uchar * *)

- ea: `0x1800dfd30`
- end: `0x1800dfeda`
- name: `?EnableAllPrivileges@@YAHPEAPEAE@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned __int8 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800621e0`
- `0x1800dfd30`
- `0x18010d8c6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dfe25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dfe25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfdda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfdda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfdd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfe46`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfdd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfe46`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800dfeab`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800dfeab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfde9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfde9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfebb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfd80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfd80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfd98`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfd98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnableAllPrivileges(unsigned __int8 **a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v4; // edi
  struct _TOKEN_PRIVILEGES *v5; // rbx
  unsigned __int8 *v6; // rax
  DWORD i; // ecx
  __int128 TokenInformation; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+28h] BYREF
  struct _TOKEN_PRIVILEGES *v11; // [rsp+70h] [rbp+30h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 2104, L"2104", 0x54Fu, 0);
    return 0;
  }
  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v4 = 1;
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    return 0;
  TokenInformationLength = 0;
  v11 = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(TokenHandle, TokenPrivileges, &TokenInformation, 0x10u, &TokenInformationLength)
    && GetLastError() != 122 )
  {
LABEL_7:
    CloseHandle(TokenHandle);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v11);
    return 0;
  }
  v5 = (struct _TOKEN_PRIVILEGES *)WSManMemory::Alloc(TokenInformationLength, 0, 0);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v11);
  v11 = v5;
  if ( !v5 )
    goto LABEL_9;
  if ( !GetTokenInformation(TokenHandle, TokenPrivileges, v5, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_7;
  v6 = (unsigned __int8 *)WSManMemory::Alloc(TokenInformationLength, 0, 0);
  *a1 = v6;
  if ( !v6 )
  {
LABEL_9:
    SetLastError(0xEu);
    goto LABEL_7;
  }
  memcpy_0(v6, v5, TokenInformationLength);
  for ( i = 0; i < v5->PrivilegeCount; ++i )
    v5->Privileges[i].Attributes |= 2u;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, v5, 0, 0, 0) )
    v4 = 0;
  CloseHandle(TokenHandle);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v11);
  return v4;
}

```

## disassembly

```asm
0x1800dfd30  mov     [rsp-18h+arg_18], rbx
0x1800dfd35  push    rbp
0x1800dfd36  push    rsi
0x1800dfd37  push    rdi
0x1800dfd38  mov     rbp, rsp
0x1800dfd3b  sub     rsp, 40h
0x1800dfd3f  mov     rsi, rcx
0x1800dfd42  test    rcx, rcx
0x1800dfd45  jnz     short loc_1800DFD71
0x1800dfd47  mov     [rsp+40h+ReturnLength], rcx; struct IRequestContext *
0x1800dfd4c  mov     r9d, 54Fh; unsigned int
0x1800dfd52  lea     r8, a2104; "2104"
0x1800dfd59  mov     edx, 838h; unsigned int
0x1800dfd5e  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x1800dfd65  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800dfd6a  xor     eax, eax
0x1800dfd6c  jmp     loc_1800DFECD
0x1800dfd71  mov     qword ptr [rcx], 0
0x1800dfd78  mov     [rbp+TokenHandle], 0
0x1800dfd80  call    cs:__imp_GetCurrentThread
0x1800dfd86  mov     rcx, rax; ThreadHandle
0x1800dfd89  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dfd8d  mov     edi, 1
0x1800dfd92  mov     r8d, edi; OpenAsSelf
0x1800dfd95  lea     edx, [rdi+27h]; DesiredAccess
0x1800dfd98  call    cs:__imp_OpenThreadToken
0x1800dfd9e  test    eax, eax
0x1800dfda0  jz      short loc_1800DFD6A
0x1800dfda2  mov     [rbp+TokenInformationLength], 0
0x1800dfda9  mov     [rbp+arg_10], 0
0x1800dfdb1  xorps   xmm0, xmm0
0x1800dfdb4  movups  [rbp+TokenInformation], xmm0
0x1800dfdb8  lea     rax, [rbp+TokenInformationLength]
0x1800dfdbc  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800dfdc1  lea     r9d, [rdi+0Fh]; TokenInformationLength
0x1800dfdc5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800dfdc9  lea     edx, [rdi+2]; TokenInformationClass
0x1800dfdcc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800dfdd0  call    cs:__imp_GetTokenInformation
0x1800dfdd6  test    eax, eax
0x1800dfdd8  jnz     short loc_1800DFDFE
0x1800dfdda  call    cs:__imp_GetLastError
0x1800dfde0  cmp     eax, 7Ah ; 'z'
0x1800dfde3  jz      short loc_1800DFDFE
0x1800dfde5  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dfde9  call    cs:__imp_CloseHandle
0x1800dfdef  nop
0x1800dfdf0  lea     rcx, [rbp+arg_10]
0x1800dfdf4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800dfdf9  jmp     loc_1800DFD6A
0x1800dfdfe  mov     ecx, [rbp+TokenInformationLength]
0x1800dfe01  xor     r8d, r8d
0x1800dfe04  xor     edx, edx
0x1800dfe06  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800dfe0b  mov     rbx, rax
0x1800dfe0e  lea     rcx, [rbp+arg_10]
0x1800dfe12  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800dfe17  mov     [rbp+arg_10], rbx
0x1800dfe1b  test    rbx, rbx
0x1800dfe1e  jnz     short loc_1800DFE2D
0x1800dfe20  mov     ecx, 0Eh; dwErrCode
0x1800dfe25  call    cs:__imp_SetLastError
0x1800dfe2b  jmp     short loc_1800DFDE5
0x1800dfe2d  lea     rax, [rbp+TokenInformationLength]
0x1800dfe31  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800dfe36  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800dfe3a  mov     r8, rbx; TokenInformation
0x1800dfe3d  mov     edx, 3; TokenInformationClass
0x1800dfe42  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800dfe46  call    cs:__imp_GetTokenInformation
0x1800dfe4c  test    eax, eax
0x1800dfe4e  jz      short loc_1800DFDE5
0x1800dfe50  mov     ecx, [rbp+TokenInformationLength]
0x1800dfe53  xor     r8d, r8d
0x1800dfe56  xor     edx, edx
0x1800dfe58  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800dfe5d  mov     [rsi], rax
0x1800dfe60  test    rax, rax
0x1800dfe63  jz      short loc_1800DFE20
0x1800dfe65  mov     r8d, [rbp+TokenInformationLength]; Size
0x1800dfe69  mov     rdx, rbx; Src
0x1800dfe6c  mov     rcx, rax; void *
0x1800dfe6f  call    memcpy_0
0x1800dfe74  xor     ecx, ecx
0x1800dfe76  cmp     [rbx], ecx
0x1800dfe78  jbe     short loc_1800DFE8D
0x1800dfe7a  mov     eax, ecx
0x1800dfe7c  add     rax, rdi
0x1800dfe7f  lea     rax, [rax+rax*2]
0x1800dfe83  or      dword ptr [rbx+rax*4], 2
0x1800dfe87  add     ecx, edi
0x1800dfe89  cmp     ecx, [rbx]
0x1800dfe8b  jb      short loc_1800DFE7A
0x1800dfe8d  mov     [rsp+40h+var_18], 0; ReturnLength
0x1800dfe96  mov     [rsp+40h+ReturnLength], 0; PreviousState
0x1800dfe9f  xor     r9d, r9d; BufferLength
0x1800dfea2  mov     r8, rbx; NewState
0x1800dfea5  xor     edx, edx; DisableAllPrivileges
0x1800dfea7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800dfeab  call    cs:__imp_AdjustTokenPrivileges
0x1800dfeb1  test    eax, eax
0x1800dfeb3  jnz     short loc_1800DFEB7
0x1800dfeb5  xor     edi, edi
0x1800dfeb7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dfebb  call    cs:__imp_CloseHandle
0x1800dfec1  nop
0x1800dfec2  lea     rcx, [rbp+arg_10]
0x1800dfec6  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800dfecb  mov     eax, edi
0x1800dfecd  mov     rbx, [rsp+40h+arg_18]
0x1800dfed2  add     rsp, 40h
0x1800dfed6  pop     rdi
0x1800dfed7  pop     rsi
0x1800dfed8  pop     rbp
0x1800dfed9  retn
```
