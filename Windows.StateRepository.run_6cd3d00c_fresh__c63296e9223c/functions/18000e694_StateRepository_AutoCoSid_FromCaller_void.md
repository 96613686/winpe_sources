# StateRepository::AutoCoSid::FromCaller(void)

- ea: `0x18000e694`
- end: `0x18000e8a9`
- name: `?FromCaller@AutoCoSid@StateRepository@@QEAAJXZ`
- size: `533`
- prototype: `__int64 __fastcall(StateRepository::AutoCoSid *__hidden this)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b780`
- `0x18000da98`
- `0x18000dbec`
- `0x18000dc60`
- `0x18000e144`
- `0x18008b8b4`
- `0x1801a52ac`

## callees

- `0x18000e694`
- `0x18000e8b0`
- `0x18000e8dc`
- `0x18000e8fc`
- `0x18000e91c`
- `0x18001a9e0`
- `0x18018f650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e6f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e6f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e70b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e70b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7ea`
- `ntdll!RtlLengthSid` at `0x18000e7bc`
- `ntdll!RtlLengthSid` at `0x18000e7bc`
- `ntdll!RtlCopySid` at `0x18000e7af`
- `ntdll!RtlCopySid` at `0x18000e7af`
- `ntdll!NtQueryInformationToken` at `0x18000e796`
- `ntdll!NtQueryInformationToken` at `0x18000e796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e828`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e750`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e750`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e719`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e719`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e6d0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e6d0`

## string_xrefs

- `0x18000e725`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`
- `0x18000e812`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`
- `0x18000e85b`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`
- `0x18000e873`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`
- `0x18000e892`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::AutoCoSid::FromCaller(HLOCAL *this)
{
  char v2; // bl
  HRESULT v3; // eax
  int LastError; // edi
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  HLOCAL v7; // rbx
  __int64 v8; // rcx
  NTSTATUS v9; // eax
  PSID v10; // rdi
  void *v12; // rcx
  void *v13; // rdx
  int ReturnLength; // [rsp+20h] [rbp-69h]
  int ReturnLengtha; // [rsp+20h] [rbp-69h]
  char v16[8]; // [rsp+30h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  ULONG v18; // [rsp+40h] [rbp-49h] BYREF
  HLOCAL v19; // [rsp+48h] [rbp-41h]
  PSID TokenInformation[12]; // [rsp+50h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  TokenHandle = 0;
  v2 = 0;
  v16[0] = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v3 = CoImpersonateClient();
    LastError = v3;
    if ( v3 < 0 )
    {
      if ( v3 != -2147417833 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\AutoCoSid.hpp",
          (const char *)(unsigned int)v3,
          ReturnLength);
        goto LABEL_25;
      }
    }
    else
    {
      v2 = 1;
      v16[0] = 1;
    }
  }
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      goto LABEL_6;
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x45,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\AutoCoSid.hpp",
                  v6);
    Common::AutoCoImpersonate::~AutoCoImpersonate((Common::AutoCoImpersonate *)v16);
    if ( LastError >= 0 )
      goto LABEL_9;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\AutoCoSid.hpp",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    goto LABEL_21;
  }
  TokenHandle = (void *)-4LL;
LABEL_6:
  if ( v2 )
    CoRevertToSelf();
LABEL_9:
  v7 = LocalAlloc(0, 0x44u);
  v19 = v7;
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\AutoCoSid.hpp",
      (const char *)0x8007000ELL,
      ReturnLength);
    v12 = 0;
    goto LABEL_20;
  }
  v8 = -6;
  if ( TokenHandle )
    v8 = (__int64)TokenHandle;
  v18 = 0;
  v9 = NtQueryInformationToken((HANDLE)v8, TokenUser, TokenInformation, 0x54u, &v18);
  if ( v9 < 0 || (v10 = TokenInformation[0], v9 = RtlCopySid(0x44u, v7, TokenInformation[0]), v9 < 0) )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x57,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\AutoCoSid.hpp",
                  (const char *)(unsigned int)v9,
                  ReturnLengtha);
    v12 = v7;
LABEL_20:
    LocalFree(v12);
LABEL_21:
    Common::CloseHandleHelper((Common *)TokenHandle, v13);
    return (unsigned int)LastError;
  }
  RtlLengthSid(v10);
  if ( *this != v7 )
  {
    LocalFree(*this);
    *this = v7;
  }
  LocalFree(0);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18000e694  push    rbp
0x18000e696  push    rbx
0x18000e697  push    rdi
0x18000e698  push    r14
0x18000e69a  lea     rbp, [rsp-3Fh]
0x18000e69f  sub     rsp, 0C8h
0x18000e6a6  mov     rax, cs:__security_cookie
0x18000e6ad  xor     rax, rsp
0x18000e6b0  mov     [rbp+57h+var_30], rax
0x18000e6b4  mov     r14, rcx
0x18000e6b7  mov     [rbp+57h+TokenHandle], 0
0x18000e6bf  xor     bl, bl
0x18000e6c1  mov     [rbp+57h+var_B0], bl
0x18000e6c4  mov     eax, gs:179Ch
0x18000e6cc  test    eax, eax
0x18000e6ce  jnz     short loc_18000E6E5
0x18000e6d0  call    cs:__imp_CoImpersonateClient
0x18000e6d6  mov     edi, eax
0x18000e6d8  test    eax, eax
0x18000e6da  js      loc_18000E849
0x18000e6e0  mov     bl, 1
0x18000e6e2  mov     [rbp+57h+var_B0], bl
0x18000e6e5  mov     eax, gs:179Ch
0x18000e6ed  test    eax, eax
0x18000e6ef  jz      loc_18000E83C
0x18000e6f5  call    cs:__imp_GetCurrentThread
0x18000e6fb  mov     rcx, rax; ThreadHandle
0x18000e6fe  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000e702  mov     edx, 0Ch; DesiredAccess
0x18000e707  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18000e70b  call    cs:__imp_OpenThreadToken
0x18000e711  test    eax, eax
0x18000e713  jz      short loc_18000E721
0x18000e715  test    bl, bl
0x18000e717  jz      short loc_18000E749
0x18000e719  call    cs:__imp_CoRevertToSelf
0x18000e71f  jmp     short loc_18000E749
0x18000e721  mov     rcx, [rbp+5Fh]; this
0x18000e725  lea     r8, aOnecoreBaseApp_378; "onecore\\base\\appmodel\\staterepositor"...
0x18000e72c  mov     edx, 45h ; 'E'; void *
0x18000e731  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e736  mov     edi, eax
0x18000e738  lea     rcx, [rbp+57h+var_B0]; this
0x18000e73c  call    ??1AutoCoImpersonate@Common@@QEAA@XZ; Common::AutoCoImpersonate::~AutoCoImpersonate(void)
0x18000e741  test    edi, edi
0x18000e743  js      loc_18000E86C
0x18000e749  mov     edx, 44h ; 'D'; uBytes
0x18000e74e  xor     ecx, ecx; uFlags
0x18000e750  call    cs:__imp_LocalAlloc
0x18000e756  mov     rbx, rax
0x18000e759  mov     [rbp+57h+var_98], rax
0x18000e75d  test    rax, rax
0x18000e760  jz      loc_18000E886
0x18000e766  mov     rax, [rbp+57h+TokenHandle]
0x18000e76a  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18000e771  test    rax, rax
0x18000e774  cmovnz  rcx, rax; TokenHandle
0x18000e778  mov     [rbp+57h+var_A0], 0
0x18000e77f  lea     rax, [rbp+57h+var_A0]
0x18000e783  mov     qword ptr [rsp+0E0h+ReturnLength], rax; int
0x18000e788  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000e78e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000e792  lea     edx, [r9-53h]; TokenInformationClass
0x18000e796  call    cs:__imp_NtQueryInformationToken
0x18000e79c  test    eax, eax
0x18000e79e  js      short loc_18000E80B
0x18000e7a0  mov     rdi, [rbp+57h+TokenInformation]
0x18000e7a4  mov     r8, rdi; SourceSid
0x18000e7a7  mov     rdx, rbx; DestinationSid
0x18000e7aa  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000e7af  call    cs:__imp_RtlCopySid
0x18000e7b5  test    eax, eax
0x18000e7b7  js      short loc_18000E80B
0x18000e7b9  mov     rcx, rdi; Sid
0x18000e7bc  call    cs:__imp_RtlLengthSid
0x18000e7c2  cmp     [r14], rbx
0x18000e7c5  jz      short loc_18000E7D3
0x18000e7c7  mov     rcx, [r14]; hMem
0x18000e7ca  call    cs:__imp_LocalFree
0x18000e7d0  mov     [r14], rbx
0x18000e7d3  xor     ecx, ecx; hMem
0x18000e7d5  call    cs:__imp_LocalFree
0x18000e7db  nop
0x18000e7dc  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000e7e0  lea     rax, [rcx-1]
0x18000e7e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e7e8  ja      short loc_18000E7F0
0x18000e7ea  call    cs:__imp_CloseHandle
0x18000e7f0  xor     eax, eax
0x18000e7f2  mov     rcx, [rbp+57h+var_30]
0x18000e7f6  xor     rcx, rsp; StackCookie
0x18000e7f9  call    __security_check_cookie
0x18000e7fe  add     rsp, 0C8h
0x18000e805  pop     r14
0x18000e807  pop     rdi
0x18000e808  pop     rbx
0x18000e809  pop     rbp
0x18000e80a  retn
0x18000e80b  mov     rcx, [rbp+5Fh]; this
0x18000e80f  mov     r9d, eax; char *
0x18000e812  lea     r8, aOnecoreBaseApp_378; "onecore\\base\\appmodel\\staterepositor"...
0x18000e819  mov     edx, 57h ; 'W'; void *
0x18000e81e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000e823  mov     edi, eax
0x18000e825  mov     rcx, rbx; hMem
0x18000e828  call    cs:__imp_LocalFree
0x18000e82e  nop
0x18000e82f  mov     rcx, [rbp+57h+TokenHandle]; this
0x18000e833  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x18000e838  mov     eax, edi
0x18000e83a  jmp     short loc_18000E7F2
0x18000e83c  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18000e844  jmp     loc_18000E715
0x18000e849  cmp     eax, 80010117h
0x18000e84e  jz      loc_18000E6E5
0x18000e854  mov     rcx, [rbp+5Fh]; this
0x18000e858  mov     r9d, eax; char *
0x18000e85b  lea     r8, aOnecoreBaseApp_378; "onecore\\base\\appmodel\\staterepositor"...
0x18000e862  mov     edx, 39h ; '9'; void *
0x18000e867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e86c  mov     rcx, [rbp+5Fh]; this
0x18000e870  mov     r9d, edi; char *
0x18000e873  lea     r8, aOnecoreBaseApp_378; "onecore\\base\\appmodel\\staterepositor"...
0x18000e87a  mov     edx, 51h ; 'Q'; void *
0x18000e87f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e884  jmp     short loc_18000E82F
0x18000e886  mov     rcx, [rbp+5Fh]; this
0x18000e88a  mov     edi, 8007000Eh
0x18000e88f  mov     r9d, edi; char *
0x18000e892  lea     r8, aOnecoreBaseApp_378; "onecore\\base\\appmodel\\staterepositor"...
0x18000e899  mov     edx, 55h ; 'U'; void *
0x18000e89e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e8a3  nop
0x18000e8a4  xor     ecx, ecx
0x18000e8a6  jmp     short loc_18000E828
```
