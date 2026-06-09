# Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc

- ea: `0x18003a568`
- end: `0x18003a60c`
- name: `Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003a614`
- `0x18003a74c`

## callees

- `0x180037fa0`
- `0x18003a47c`
- `0x18003a568`
- `0x1800563c8`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a5c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a5c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003a5dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003a5dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003a599`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003a599`

## string_xrefs

- `0x18003a5c0`: `GetDockedComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc()
{
  HMODULE UsoDockedModule; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  BOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    UsoDockedModule = Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule();
    qword_18009FAA0 = (__int64)GetProcAddress(UsoDockedModule, "GetDockedComponent");
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v2, v1);
  }
  return qword_18009FAA0;
}

```

## disassembly

```asm
0x18003a568  push    rbx
0x18003a56a  sub     rsp, 40h
0x18003a56e  mov     rax, cs:__security_cookie
0x18003a575  xor     rax, rsp
0x18003a578  mov     [rsp+48h+var_10], rax
0x18003a57d  mov     [rsp+48h+fPending], 0
0x18003a585  xor     r9d, r9d; lpContext
0x18003a588  lea     r8, [rsp+48h+fPending]; fPending
0x18003a58d  xor     edx, edx; dwFlags
0x18003a58f  lea     rbx, InitOnce
0x18003a596  mov     rcx, rbx; lpInitOnce
0x18003a599  call    cs:__imp___std_init_once_begin_initialize
0x18003a59f  test    eax, eax
0x18003a5a1  jz      short loc_18003A606
0x18003a5a3  cmp     [rsp+48h+fPending], 0
0x18003a5a8  jz      short loc_18003A5E6
0x18003a5aa  mov     [rsp+48h+var_28], rbx
0x18003a5af  mov     [rsp+48h+var_20], 4
0x18003a5b8  call    Windows__DockedHelpers___anonymous_namespace___GetUsoDockedModule
0x18003a5bd  mov     rcx, rax; hModule
0x18003a5c0  lea     rdx, aGetdockedcompo; "GetDockedComponent"
0x18003a5c7  call    cs:__imp_GetProcAddress
0x18003a5cd  mov     cs:qword_18009FAA0, rax
0x18003a5d4  xor     r8d, r8d; lpContext
0x18003a5d7  xor     edx, edx; dwFlags
0x18003a5d9  mov     rcx, rbx; lpInitOnce
0x18003a5dc  call    cs:__imp_InitOnceComplete
0x18003a5e2  test    eax, eax
0x18003a5e4  jz      short loc_18003A600
0x18003a5e6  mov     rax, cs:qword_18009FAA0
0x18003a5ed  mov     rcx, [rsp+48h+var_10]
0x18003a5f2  xor     rcx, rsp; StackCookie
0x18003a5f5  call    __security_check_cookie
0x18003a5fa  add     rsp, 40h
0x18003a5fe  pop     rbx
0x18003a5ff  retn
0x18003a600  call    __std_init_once_link_alternate_names_and_abort
0x18003a606  call    abort
```
