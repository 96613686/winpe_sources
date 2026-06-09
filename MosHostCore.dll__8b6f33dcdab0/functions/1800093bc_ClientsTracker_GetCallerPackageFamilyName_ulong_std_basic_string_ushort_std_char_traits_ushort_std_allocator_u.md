# ClientsTracker::GetCallerPackageFamilyName(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800093bc`
- end: `0x1800094cc`
- name: `?GetCallerPackageFamilyName@ClientsTracker@@AEAAJKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(const void *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800094d4`

## callees

- `0x180003410`
- `0x180008e00`
- `0x1800093bc`
- `0x18000af48`
- `0x18000b170`
- `0x180022ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009432`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009402`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009402`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000945f`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000945f`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x180009473`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x180009473`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClientsTracker::GetCallerPackageFamilyName(const void *a1, DWORD a2, __int64 a3)
{
  HANDLE v5; // rax
  int LastError; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  UINT32 packageFamilyNameLength; // [rsp+20h] [rbp-1038h] BYREF
  HANDLE hProcess; // [rsp+28h] [rbp-1030h] BYREF
  __int64 v12; // [rsp+30h] [rbp-1028h] BYREF
  WCHAR packageFamilyName[2048]; // [rsp+40h] [rbp-1018h] BYREF

  hProcess = 0;
  packageFamilyNameLength = 2048;
  v5 = OpenProcess(0x1000u, 0, a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hProcess,
    v5);
  v12 = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  if ( hProcess )
  {
    LastError = GetPackageFamilyName(hProcess, &packageFamilyNameLength, packageFamilyName);
    if ( !LastError )
    {
      v8 = 0;
      std::wstring::assign(a3, packageFamilyName);
      goto LABEL_13;
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = 529;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v7 = 527;
  }
  v8 = ZTraceReportOrigination(LastError, "ClientsTracker::GetCallerPackageFamilyName", v7, a1);
LABEL_13:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
  return v8;
}

```

## disassembly

```asm
0x1800093bc  mov     [rsp+arg_18], rbx
0x1800093c1  push    rdi
0x1800093c2  mov     eax, 1050h
0x1800093c7  call    _alloca_probe
0x1800093cc  sub     rsp, rax
0x1800093cf  mov     rax, cs:__security_cookie
0x1800093d6  xor     rax, rsp
0x1800093d9  mov     [rsp+1058h+var_18], rax
0x1800093e1  mov     rdi, r8
0x1800093e4  mov     rbx, rcx
0x1800093e7  mov     [rsp+1058h+hProcess], 0
0x1800093f0  mov     [rsp+1058h+packageFamilyNameLength], 800h
0x1800093f8  mov     r8d, edx; dwProcessId
0x1800093fb  xor     edx, edx; bInheritHandle
0x1800093fd  mov     ecx, 1000h; dwDesiredAccess
0x180009402  call    cs:__imp_OpenProcess
0x180009408  mov     rdx, rax
0x18000940b  lea     rcx, [rsp+1058h+hProcess]
0x180009410  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180009415  mov     [rsp+1058h+var_1028], 0
0x18000941e  lea     rcx, [rsp+1058h+var_1028]
0x180009423  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009428  mov     rcx, [rsp+1058h+hProcess]; hProcess
0x18000942d  test    rcx, rcx
0x180009430  jnz     short loc_180009469
0x180009432  call    cs:__imp_GetLastError
0x180009438  test    eax, eax
0x18000943a  jz      short loc_180009448
0x18000943c  jle     short loc_18000944D
0x18000943e  movzx   eax, ax
0x180009441  or      eax, 80070000h
0x180009446  jmp     short loc_18000944D
0x180009448  mov     eax, 80390004h
0x18000944d  mov     r8d, 20Fh
0x180009453  mov     r9, rbx
0x180009456  lea     rdx, aClientstracker; "ClientsTracker::GetCallerPackageFamilyN"...
0x18000945d  mov     ecx, eax
0x18000945f  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180009465  mov     ebx, eax
0x180009467  jmp     short loc_18000949F
0x180009469  lea     r8, [rsp+1058h+packageFamilyName]; packageFamilyName
0x18000946e  lea     rdx, [rsp+1058h+packageFamilyNameLength]; packageFamilyNameLength
0x180009473  call    cs:__imp_GetPackageFamilyName
0x180009479  test    eax, eax
0x18000947b  jz      short loc_18000948F
0x18000947d  jle     short loc_180009487
0x18000947f  movzx   eax, ax
0x180009482  or      eax, 80070000h
0x180009487  mov     r8d, 211h
0x18000948d  jmp     short loc_180009453
0x18000948f  xor     ebx, ebx
0x180009491  lea     rdx, [rsp+1058h+packageFamilyName]
0x180009496  mov     rcx, rdi
0x180009499  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18000949e  nop
0x18000949f  lea     rcx, [rsp+1058h+hProcess]
0x1800094a4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800094a9  mov     eax, ebx
0x1800094ab  mov     rcx, [rsp+1058h+var_18]
0x1800094b3  xor     rcx, rsp; StackCookie
0x1800094b6  call    __security_check_cookie
0x1800094bb  mov     rbx, [rsp+1058h+arg_18]
0x1800094c3  add     rsp, 1050h
0x1800094ca  pop     rdi
0x1800094cb  retn
```
