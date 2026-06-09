# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x180051104`
- end: `0x18005123e`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180051244`

## callees

- `0x18000aedc`
- `0x1800497c0`
- `0x180051104`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511e9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180051218`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180051218`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800511b8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800511b8`

## string_xrefs

- `0x1800511b1`: `kernelbase.dll`
- `0x180051121`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18005117b`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18005120e`: `GetTempPath2W`
- `0x18005113f`: `Not-null check failed: phDll`
- `0x180051134`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x18005118e`: `Windows::COM::LoadSystemLibraryAndFunction`

## pseudocode

```c
signed int __fastcall Windows::COM::LoadSystemLibraryAndFunction(__int64 a1, __int64 a2, HMODULE *a3, FARPROC *a4)
{
  const char *v6; // rax
  signed int result; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const char *v10; // [rsp+20h] [rbp-20h] BYREF
  const char *v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  const char *v13; // [rsp+38h] [rbp-8h]

  if ( !a3 )
  {
    v12 = 108;
    v10 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v11 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: phDll";
LABEL_3:
    v13 = v6;
    RtlReportErrorOrigination(&v10, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147500035LL);
    return -2147467261;
  }
  if ( !a4 )
  {
    v12 = 109;
    v10 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v11 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: ppfn";
    goto LABEL_3;
  }
  *a4 = 0;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  if ( *a3 )
    goto LABEL_16;
  *a3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTempPath2W");
    *a4 = ProcAddress;
    if ( ProcAddress )
      return 0;
  }
  if ( !GetLastError() )
  {
    result = 14077;
    goto LABEL_12;
  }
  result = GetLastError();
  if ( !result )
  {
LABEL_16:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18005123DLL);
  }
LABEL_12:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180051104  mov     [rsp-8+arg_0], rbx
0x180051109  mov     [rsp-8+arg_8], rdi
0x18005110e  push    rbp
0x18005110f  mov     rbp, rsp
0x180051112  sub     rsp, 40h
0x180051116  mov     rbx, r9
0x180051119  mov     rdi, r8
0x18005111c  test    r8, r8
0x18005111f  jnz     short loc_180051176
0x180051121  lea     rax, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180051128  mov     [rbp+var_10], 6Ch ; 'l'
0x180051130  mov     [rbp+var_20], rax
0x180051134  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x18005113b  mov     [rbp+var_18], rax
0x18005113f  lea     rax, aNotNullCheckFa_49; "Not-null check failed: phDll"
0x180051146  mov     r8d, 80004003h
0x18005114c  mov     [rbp+var_8], rax
0x180051150  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180051157  lea     rcx, [rbp+var_20]
0x18005115b  call    RtlReportErrorOrigination
0x180051160  mov     eax, 80004003h
0x180051165  mov     rbx, [rsp+40h+arg_0]
0x18005116a  mov     rdi, [rsp+40h+arg_8]
0x18005116f  add     rsp, 40h
0x180051173  pop     rbp
0x180051174  retn
0x180051176  test    rbx, rbx
0x180051179  jnz     short loc_1800511A2
0x18005117b  lea     rax, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180051182  mov     [rbp+var_10], 6Dh ; 'm'
0x18005118a  mov     [rbp+var_20], rax
0x18005118e  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x180051195  mov     [rbp+var_18], rax
0x180051199  lea     rax, aNotNullCheckFa_24; "Not-null check failed: ppfn"
0x1800511a0  jmp     short loc_180051146
0x1800511a2  xor     edx, edx; hFile
0x1800511a4  mov     qword ptr [r9], 0
0x1800511ab  mov     r8d, 800h; dwFlags
0x1800511b1  lea     rcx, LibFileName; "kernelbase.dll"
0x1800511b8  call    cs:__imp_LoadLibraryExW
0x1800511bf  nop     dword ptr [rax+rax+00h]
0x1800511c4  cmp     qword ptr [rdi], 0
0x1800511c8  jnz     short loc_180051233
0x1800511ca  mov     [rdi], rax
0x1800511cd  test    rax, rax
0x1800511d0  jnz     short loc_18005120E
0x1800511d2  call    cs:__imp_GetLastError
0x1800511d9  nop     dword ptr [rax+rax+00h]
0x1800511de  test    eax, eax
0x1800511e0  jnz     short loc_1800511E9
0x1800511e2  mov     eax, 36FDh
0x1800511e7  jmp     short loc_1800511F9
0x1800511e9  call    cs:__imp_GetLastError
0x1800511f0  nop     dword ptr [rax+rax+00h]
0x1800511f5  test    eax, eax
0x1800511f7  jz      short loc_180051233
0x1800511f9  test    eax, eax
0x1800511fb  jle     loc_180051165
0x180051201  movzx   eax, ax
0x180051204  or      eax, 80070000h
0x180051209  jmp     loc_180051165
0x18005120e  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180051215  mov     rcx, rax; hModule
0x180051218  call    cs:__imp_GetProcAddress
0x18005121f  nop     dword ptr [rax+rax+00h]
0x180051224  mov     [rbx], rax
0x180051227  test    rax, rax
0x18005122a  jz      short loc_1800511D2
0x18005122c  xor     eax, eax
0x18005122e  jmp     loc_180051165
0x180051233  mov     ecx, 0C00000E5h; int
0x180051238  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
