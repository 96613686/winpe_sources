# Windows::DockedHelpers::GetDockedComponentFunc(void)

- ea: `0x180044dec`
- end: `0x180044ec9`
- name: `?GetDockedComponentFunc@DockedHelpers@Windows@@YAP6AJAEBU_GUID@@PEAPEAX@ZXZ`
- size: `221`
- prototype: `int (*__fastcall(Windows::DockedHelpers *__hidden this))(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044ed0`
- `0x180045008`
- `0x180045140`

## callees

- `0x180007238`
- `0x180023a18`
- `0x180044dec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044e45`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044e45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044e80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044e80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044e70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044e70`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044e12`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044e12`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044e95`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044e95`

## string_xrefs

- `0x180044e3e`: `UsoDocked.dll`
- `0x180044eb7`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\dockedhelpers.cpp`
- `0x180044e76`: `GetDockedComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int (*__fastcall Windows::DockedHelpers::GetDockedComponentFunc(
        Windows::DockedHelpers *this))(const struct _GUID *, void **)
{
  HMODULE Library; // rax
  const char *v2; // r9
  HMODULE v3; // rbx
  HMODULE v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+8h] BYREF
  HMODULE v10; // [rsp+48h] [rbp+10h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    Library = LoadLibraryExW(L"UsoDocked.dll", 0, 0x800u);
    v3 = Library;
    v10 = Library;
    if ( !Library )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\dockedhelpers.cpp",
        v2);
    v4 = Windows::DockedHelpers::g_UsoDockedModule;
    Windows::DockedHelpers::g_UsoDockedModule = Library;
    if ( v4 )
      FreeLibrary(v4);
    qword_180095D70 = (__int64)GetProcAddress(v3, "GetDockedComponent");
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v6, v5);
  }
  return (int (*)(const struct _GUID *, void **))qword_180095D70;
}

```

## disassembly

```asm
0x180044dec  mov     [rsp+arg_10], rbx
0x180044df1  push    rdi
0x180044df2  sub     rsp, 30h
0x180044df6  mov     [rsp+38h+fPending], 0
0x180044dfe  xor     r9d, r9d; lpContext
0x180044e01  lea     r8, [rsp+38h+fPending]; fPending
0x180044e06  xor     edx, edx; dwFlags
0x180044e08  lea     rdi, InitOnce
0x180044e0f  mov     rcx, rdi; lpInitOnce
0x180044e12  call    cs:__imp___std_init_once_begin_initialize
0x180044e18  test    eax, eax
0x180044e1a  jnz     short loc_180044E21
0x180044e1c  lea     ecx, [rax+5]
0x180044e1f  int     29h; Win8: RtlFailFast(ecx)
0x180044e21  cmp     [rsp+38h+fPending], 0
0x180044e26  jz      short loc_180044E9F
0x180044e28  mov     [rsp+38h+var_18], rdi
0x180044e2d  mov     [rsp+38h+var_10], 4
0x180044e36  xor     edx, edx; hFile
0x180044e38  mov     r8d, 800h; dwFlags
0x180044e3e  lea     rcx, aUsodockedDll_0; "UsoDocked.dll"
0x180044e45  call    cs:__imp_LoadLibraryExW
0x180044e4b  mov     rbx, rax
0x180044e4e  mov     [rsp+38h+arg_8], rax
0x180044e53  mov     rcx, [rsp+38h]; this
0x180044e58  test    rax, rax
0x180044e5b  jz      short loc_180044EB7
0x180044e5d  mov     rcx, cs:?g_UsoDockedModule@DockedHelpers@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hLibModule
0x180044e64  mov     cs:?g_UsoDockedModule@DockedHelpers@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rax; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::DockedHelpers::g_UsoDockedModule
0x180044e6b  test    rcx, rcx
0x180044e6e  jz      short loc_180044E76
0x180044e70  call    cs:__imp_FreeLibrary
0x180044e76  lea     rdx, aGetdockedcompo_0; "GetDockedComponent"
0x180044e7d  mov     rcx, rbx; hModule
0x180044e80  call    cs:__imp_GetProcAddress
0x180044e86  mov     cs:qword_180095D70, rax
0x180044e8d  xor     r8d, r8d; lpContext
0x180044e90  xor     edx, edx; dwFlags
0x180044e92  mov     rcx, rdi; lpInitOnce
0x180044e95  call    cs:__imp_InitOnceComplete
0x180044e9b  test    eax, eax
0x180044e9d  jz      short loc_180044EB1
0x180044e9f  mov     rax, cs:qword_180095D70
0x180044ea6  mov     rbx, [rsp+38h+arg_10]
0x180044eab  add     rsp, 30h
0x180044eaf  pop     rdi
0x180044eb0  retn
0x180044eb1  call    __std_init_once_link_alternate_names_and_abort
0x180044eb7  lea     r8, aOnecoreEnduser_28; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180044ebe  mov     edx, 11h; void *
0x180044ec3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
