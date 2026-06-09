# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x140026c70`
- end: `0x140026dbb`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `331`
- prototype: `signed int __fastcall(__int64, __int64, HMODULE *, FARPROC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140026dc4`

## callees

- `0x140002310`
- `0x140006950`
- `0x140006b54`
- `0x140006d44`
- `0x140026c70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026d6e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026d6e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140026d25`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140026d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d86`

## string_xrefs

- `0x140026d1e`: `kernelbase.dll`
- `0x140026d67`: `GetTempPath2W`
- `0x140026ca2`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026ce8`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026cb5`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x140026cfb`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x140026cc0`: `Not-null check failed: phDll`

## pseudocode

```c
signed int __fastcall Windows::COM::LoadSystemLibraryAndFunction(__int64 a1, __int64 a2, HMODULE *a3, FARPROC *a4)
{
  const char *v6; // rax
  signed int result; // eax
  HMODULE Library; // rax
  bool v9; // cc
  FARPROC ProcAddress; // rax
  const char *v11; // [rsp+20h] [rbp-30h] BYREF
  const char *v12; // [rsp+28h] [rbp-28h]
  __int64 v13; // [rsp+30h] [rbp-20h]
  const char *v14; // [rsp+38h] [rbp-18h]
  int v15; // [rsp+40h] [rbp-10h] BYREF

  v15 = 0;
  if ( !a3 )
  {
    v13 = 108;
    v11 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: phDll";
LABEL_3:
    v14 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v15,
             &v11,
             2147500035LL);
  }
  if ( !a4 )
  {
    v13 = 109;
    v11 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: ppfn";
    goto LABEL_3;
  }
  *a4 = 0;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    a3,
    Library);
  if ( !*a3 )
  {
    if ( !GetLastError() )
    {
LABEL_8:
      result = 14077;
LABEL_10:
      v9 = result <= 0;
      goto LABEL_11;
    }
    result = GetLastError();
    if ( result )
      goto LABEL_10;
LABEL_19:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  ProcAddress = GetProcAddress(*a3, "GetTempPath2W");
  *a4 = ProcAddress;
  if ( ProcAddress )
    return 0;
  if ( !GetLastError() )
    goto LABEL_8;
  result = GetLastError();
  v9 = result <= 0;
  if ( !result )
    goto LABEL_19;
LABEL_11:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140026c70  mov     [rsp-8+arg_0], rbx
0x140026c75  mov     [rsp-8+arg_8], rdi
0x140026c7a  push    rbp
0x140026c7b  mov     rbp, rsp
0x140026c7e  sub     rsp, 50h
0x140026c82  mov     rax, cs:__security_cookie
0x140026c89  xor     rax, rsp
0x140026c8c  mov     [rbp+var_8], rax
0x140026c90  mov     [rbp+var_10], 0
0x140026c97  mov     rbx, r9
0x140026c9a  mov     rdi, r8
0x140026c9d  test    r8, r8
0x140026ca0  jnz     short loc_140026CE3
0x140026ca2  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026ca9  mov     [rbp+var_20], 6Ch ; 'l'
0x140026cb1  mov     [rbp+var_30], rax
0x140026cb5  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x140026cbc  mov     [rbp+var_28], rax
0x140026cc0  lea     rax, aNotNullCheckFa_0; "Not-null check failed: phDll"
0x140026cc7  mov     r8d, 80004003h
0x140026ccd  mov     [rbp+var_18], rax
0x140026cd1  lea     rdx, [rbp+var_30]
0x140026cd5  lea     rcx, [rbp+var_10]
0x140026cd9  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026cde  jmp     loc_140026D94
0x140026ce3  test    rbx, rbx
0x140026ce6  jnz     short loc_140026D0F
0x140026ce8  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026cef  mov     [rbp+var_20], 6Dh ; 'm'
0x140026cf7  mov     [rbp+var_30], rax
0x140026cfb  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x140026d02  mov     [rbp+var_28], rax
0x140026d06  lea     rax, aNotNullCheckFa; "Not-null check failed: ppfn"
0x140026d0d  jmp     short loc_140026CC7
0x140026d0f  xor     edx, edx; hFile
0x140026d11  mov     qword ptr [r9], 0
0x140026d18  mov     r8d, 800h; dwFlags
0x140026d1e  lea     rcx, LibFileName; "kernelbase.dll"
0x140026d25  call    cs:__imp_LoadLibraryExW
0x140026d2b  mov     rdx, rax
0x140026d2e  mov     rcx, rdi
0x140026d31  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x140026d36  mov     rcx, [rdi]; hModule
0x140026d39  test    rcx, rcx
0x140026d3c  jnz     short loc_140026D67
0x140026d3e  call    cs:__imp_GetLastError
0x140026d44  test    eax, eax
0x140026d46  jnz     short loc_140026D4F
0x140026d48  mov     eax, 36FDh
0x140026d4d  jmp     short loc_140026D59
0x140026d4f  call    cs:__imp_GetLastError
0x140026d55  test    eax, eax
0x140026d57  jz      short loc_140026DB0
0x140026d59  test    eax, eax
0x140026d5b  jle     short loc_140026D94
0x140026d5d  movzx   eax, ax
0x140026d60  or      eax, 80070000h
0x140026d65  jmp     short loc_140026D94
0x140026d67  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x140026d6e  call    cs:__imp_GetProcAddress
0x140026d74  mov     [rbx], rax
0x140026d77  test    rax, rax
0x140026d7a  jnz     short loc_140026D92
0x140026d7c  call    cs:__imp_GetLastError
0x140026d82  test    eax, eax
0x140026d84  jz      short loc_140026D48
0x140026d86  call    cs:__imp_GetLastError
0x140026d8c  test    eax, eax
0x140026d8e  jz      short loc_140026DB0
0x140026d90  jmp     short loc_140026D5B
0x140026d92  xor     eax, eax
0x140026d94  mov     rcx, [rbp+var_8]
0x140026d98  xor     rcx, rsp; StackCookie
0x140026d9b  call    __security_check_cookie
0x140026da0  mov     rbx, [rsp+50h+arg_0]
0x140026da5  mov     rdi, [rsp+50h+arg_8]
0x140026daa  add     rsp, 50h
0x140026dae  pop     rbp
0x140026daf  retn
0x140026db0  mov     ecx, 0C00000E5h; int
0x140026db5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
