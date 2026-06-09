# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x1400269ac`
- end: `0x140026af7`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `331`
- prototype: `signed int __fastcall(__int64, __int64, HMODULE *, FARPROC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140026b00`

## callees

- `0x1400023e0`
- `0x1400076ec`
- `0x140008138`
- `0x140015738`
- `0x1400269ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026aaa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140026aaa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140026a61`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140026a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ac2`

## string_xrefs

- `0x140026a5a`: `kernelbase.dll`
- `0x1400269de`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026a24`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026aa3`: `GetTempPath2W`
- `0x1400269f1`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x140026a37`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x1400269fc`: `Not-null check failed: phDll`

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
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(a3, Library);
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
0x1400269ac  mov     [rsp-8+arg_0], rbx
0x1400269b1  mov     [rsp-8+arg_8], rdi
0x1400269b6  push    rbp
0x1400269b7  mov     rbp, rsp
0x1400269ba  sub     rsp, 50h
0x1400269be  mov     rax, cs:__security_cookie
0x1400269c5  xor     rax, rsp
0x1400269c8  mov     [rbp+var_8], rax
0x1400269cc  mov     [rbp+var_10], 0
0x1400269d3  mov     rbx, r9
0x1400269d6  mov     rdi, r8
0x1400269d9  test    r8, r8
0x1400269dc  jnz     short loc_140026A1F
0x1400269de  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x1400269e5  mov     [rbp+var_20], 6Ch ; 'l'
0x1400269ed  mov     [rbp+var_30], rax
0x1400269f1  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x1400269f8  mov     [rbp+var_28], rax
0x1400269fc  lea     rax, aNotNullCheckFa_0; "Not-null check failed: phDll"
0x140026a03  mov     r8d, 80004003h
0x140026a09  mov     [rbp+var_18], rax
0x140026a0d  lea     rdx, [rbp+var_30]
0x140026a11  lea     rcx, [rbp+var_10]
0x140026a15  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026a1a  jmp     loc_140026AD0
0x140026a1f  test    rbx, rbx
0x140026a22  jnz     short loc_140026A4B
0x140026a24  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026a2b  mov     [rbp+var_20], 6Dh ; 'm'
0x140026a33  mov     [rbp+var_30], rax
0x140026a37  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x140026a3e  mov     [rbp+var_28], rax
0x140026a42  lea     rax, aNotNullCheckFa; "Not-null check failed: ppfn"
0x140026a49  jmp     short loc_140026A03
0x140026a4b  xor     edx, edx; hFile
0x140026a4d  mov     qword ptr [r9], 0
0x140026a54  mov     r8d, 800h; dwFlags
0x140026a5a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140026a61  call    cs:__imp_LoadLibraryExW
0x140026a67  mov     rdx, rax
0x140026a6a  mov     rcx, rdi
0x140026a6d  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x140026a72  mov     rcx, [rdi]; hModule
0x140026a75  test    rcx, rcx
0x140026a78  jnz     short loc_140026AA3
0x140026a7a  call    cs:__imp_GetLastError
0x140026a80  test    eax, eax
0x140026a82  jnz     short loc_140026A8B
0x140026a84  mov     eax, 36FDh
0x140026a89  jmp     short loc_140026A95
0x140026a8b  call    cs:__imp_GetLastError
0x140026a91  test    eax, eax
0x140026a93  jz      short loc_140026AEC
0x140026a95  test    eax, eax
0x140026a97  jle     short loc_140026AD0
0x140026a99  movzx   eax, ax
0x140026a9c  or      eax, 80070000h
0x140026aa1  jmp     short loc_140026AD0
0x140026aa3  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x140026aaa  call    cs:__imp_GetProcAddress
0x140026ab0  mov     [rbx], rax
0x140026ab3  test    rax, rax
0x140026ab6  jnz     short loc_140026ACE
0x140026ab8  call    cs:__imp_GetLastError
0x140026abe  test    eax, eax
0x140026ac0  jz      short loc_140026A84
0x140026ac2  call    cs:__imp_GetLastError
0x140026ac8  test    eax, eax
0x140026aca  jz      short loc_140026AEC
0x140026acc  jmp     short loc_140026A97
0x140026ace  xor     eax, eax
0x140026ad0  mov     rcx, [rbp+var_8]
0x140026ad4  xor     rcx, rsp; StackCookie
0x140026ad7  call    __security_check_cookie
0x140026adc  mov     rbx, [rsp+50h+arg_0]
0x140026ae1  mov     rdi, [rsp+50h+arg_8]
0x140026ae6  add     rsp, 50h
0x140026aea  pop     rbp
0x140026aeb  retn
0x140026aec  mov     ecx, 0C00000E5h; int
0x140026af1  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
