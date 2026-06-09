# mutex::GetBuiltinAdminSid(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x1800384b4`
- end: `0x180038579`
- name: `?GetBuiltinAdminSid@mutex@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180038914`
- `0x180038d40`

## callees

- `0x180002214`
- `0x1800384b4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038536`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038541`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800384fe`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800384fe`

## string_xrefs

- `0x18003850d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`

## pseudocode

```c
__int64 __fastcall mutex::GetBuiltinAdminSid(void **a1)
{
  HLOCAL v2; // rdi
  const char *v3; // r9
  unsigned int v4; // ebx
  void *v5; // rsi
  DWORD LastError; // ebx
  DWORD cbSid; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  cbSid = 68;
  v2 = LocalAlloc(0, 0x44u);
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v2, &cbSid) )
  {
    v5 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      LocalFree(v5);
      SetLastError(LastError);
    }
    *a1 = v2;
    return 0;
  }
  else
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x22,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
           v3);
    if ( v2 )
      LocalFree(v2);
  }
  return v4;
}

```

## disassembly

```asm
0x1800384b4  mov     [rsp+arg_8], rbx
0x1800384b9  mov     [rsp+arg_10], rsi
0x1800384be  mov     [rsp+arg_18], rdi
0x1800384c3  push    r14
0x1800384c5  sub     rsp, 30h
0x1800384c9  mov     rax, cs:__security_cookie
0x1800384d0  xor     rax, rsp
0x1800384d3  mov     [rsp+38h+var_10], rax
0x1800384d8  mov     r14, rcx
0x1800384db  mov     ebx, 44h ; 'D'
0x1800384e0  mov     edx, ebx; uBytes
0x1800384e2  xor     ecx, ecx; uFlags
0x1800384e4  call    cs:__imp_LocalAlloc
0x1800384ea  lea     r9, [rsp+38h+cbSid]; cbSid
0x1800384ef  mov     [rsp+38h+cbSid], ebx
0x1800384f3  mov     r8, rax; pSid
0x1800384f6  lea     ecx, [rbx-2Ah]; WellKnownSidType
0x1800384f9  xor     edx, edx; DomainSid
0x1800384fb  mov     rdi, rax
0x1800384fe  call    cs:__imp_CreateWellKnownSid
0x180038504  test    eax, eax
0x180038506  jnz     short loc_18003852E
0x180038508  mov     rcx, [rsp+38h]; this
0x18003850d  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038514  lea     edx, [rbx-22h]; void *
0x180038517  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003851c  mov     ebx, eax
0x18003851e  test    rdi, rdi
0x180038521  jz      short loc_180038554
0x180038523  mov     rcx, rdi; hMem
0x180038526  call    cs:__imp_LocalFree
0x18003852c  jmp     short loc_180038554
0x18003852e  mov     rsi, [r14]
0x180038531  test    rsi, rsi
0x180038534  jz      short loc_18003854F
0x180038536  call    cs:__imp_GetLastError
0x18003853c  mov     rcx, rsi; hMem
0x18003853f  mov     ebx, eax
0x180038541  call    cs:__imp_LocalFree
0x180038547  mov     ecx, ebx; dwErrCode
0x180038549  call    cs:__imp_SetLastError
0x18003854f  mov     [r14], rdi
0x180038552  xor     ebx, ebx
0x180038554  mov     eax, ebx
0x180038556  mov     rcx, [rsp+38h+var_10]
0x18003855b  xor     rcx, rsp; StackCookie
0x18003855e  call    __security_check_cookie
0x180038563  mov     rbx, [rsp+38h+arg_8]
0x180038568  mov     rsi, [rsp+38h+arg_10]
0x18003856d  mov     rdi, [rsp+38h+arg_18]
0x180038572  add     rsp, 30h
0x180038576  pop     r14
0x180038578  retn
```
