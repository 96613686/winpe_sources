# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x18006c054`
- end: `0x18006c1be`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006c1d0`

## callees

- `0x18001f51c`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003e8f8`
- `0x18006c054`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006c122`
- `KERNEL32!GetLastError` at `0x18006c139`
- `KERNEL32!GetLastError` at `0x18006c172`
- `KERNEL32!GetLastError` at `0x18006c182`
- `KERNEL32!GetLastError` at `0x18006c122`
- `KERNEL32!GetLastError` at `0x18006c139`
- `KERNEL32!GetLastError` at `0x18006c172`
- `KERNEL32!GetLastError` at `0x18006c182`
- `KERNEL32!GetProcAddress` at `0x18006c15e`
- `KERNEL32!GetProcAddress` at `0x18006c15e`
- `KERNEL32!LoadLibraryExW` at `0x18006c103`
- `KERNEL32!LoadLibraryExW` at `0x18006c103`

## string_xrefs

- `0x18006c0fc`: `kernelbase.dll`
- `0x18006c086`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18006c0c6`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18006c157`: `GetTempPath2W`
- `0x18006c099`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x18006c0d9`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x18006c0a4`: `Not-null check failed: phDll`

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
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v11);
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
    JUMPOUT(0x18006C1BDLL);
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
0x18006c054  mov     [rsp-8+arg_0], rbx
0x18006c059  mov     [rsp-8+arg_8], rdi
0x18006c05e  push    rbp
0x18006c05f  mov     rbp, rsp
0x18006c062  sub     rsp, 50h
0x18006c066  mov     rax, cs:__security_cookie
0x18006c06d  xor     rax, rsp
0x18006c070  mov     [rbp+var_8], rax
0x18006c074  mov     [rbp+var_10], 0
0x18006c07b  mov     rbx, r9
0x18006c07e  mov     rdi, r8
0x18006c081  test    r8, r8
0x18006c084  jnz     short loc_18006C0C1
0x18006c086  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x18006c08d  mov     [rbp+var_20], 6Ch ; 'l'
0x18006c095  mov     [rbp+var_30], rax
0x18006c099  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x18006c0a0  mov     [rbp+var_28], rax
0x18006c0a4  lea     rax, aNotNullCheckFa_89; "Not-null check failed: phDll"
0x18006c0ab  lea     rdx, [rbp+var_30]
0x18006c0af  mov     [rbp+var_18], rax
0x18006c0b3  lea     rcx, [rbp+var_10]
0x18006c0b7  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006c0bc  jmp     loc_18006C196
0x18006c0c1  test    rbx, rbx
0x18006c0c4  jnz     short loc_18006C0ED
0x18006c0c6  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x18006c0cd  mov     [rbp+var_20], 6Dh ; 'm'
0x18006c0d5  mov     [rbp+var_30], rax
0x18006c0d9  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x18006c0e0  mov     [rbp+var_28], rax
0x18006c0e4  lea     rax, aNotNullCheckFa_35; "Not-null check failed: ppfn"
0x18006c0eb  jmp     short loc_18006C0AB
0x18006c0ed  xor     edx, edx; hFile
0x18006c0ef  mov     qword ptr [r9], 0
0x18006c0f6  mov     r8d, 800h; dwFlags
0x18006c0fc  lea     rcx, LibFileName; "kernelbase.dll"
0x18006c103  call    cs:__imp_LoadLibraryExW
0x18006c10a  nop     dword ptr [rax+rax+00h]
0x18006c10f  mov     rdx, rax
0x18006c112  mov     rcx, rdi
0x18006c115  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18006c11a  mov     rcx, [rdi]; hModule
0x18006c11d  test    rcx, rcx
0x18006c120  jnz     short loc_18006C157
0x18006c122  call    cs:__imp_GetLastError
0x18006c129  nop     dword ptr [rax+rax+00h]
0x18006c12e  test    eax, eax
0x18006c130  jnz     short loc_18006C139
0x18006c132  mov     eax, 36FDh
0x18006c137  jmp     short loc_18006C149
0x18006c139  call    cs:__imp_GetLastError
0x18006c140  nop     dword ptr [rax+rax+00h]
0x18006c145  test    eax, eax
0x18006c147  jz      short loc_18006C1B3
0x18006c149  test    eax, eax
0x18006c14b  jle     short loc_18006C196
0x18006c14d  movzx   eax, ax
0x18006c150  or      eax, 80070000h
0x18006c155  jmp     short loc_18006C196
0x18006c157  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18006c15e  call    cs:__imp_GetProcAddress
0x18006c165  nop     dword ptr [rax+rax+00h]
0x18006c16a  mov     [rbx], rax
0x18006c16d  test    rax, rax
0x18006c170  jnz     short loc_18006C194
0x18006c172  call    cs:__imp_GetLastError
0x18006c179  nop     dword ptr [rax+rax+00h]
0x18006c17e  test    eax, eax
0x18006c180  jz      short loc_18006C132
0x18006c182  call    cs:__imp_GetLastError
0x18006c189  nop     dword ptr [rax+rax+00h]
0x18006c18e  test    eax, eax
0x18006c190  jz      short loc_18006C1B3
0x18006c192  jmp     short loc_18006C14B
0x18006c194  xor     eax, eax
0x18006c196  mov     rcx, [rbp+var_8]
0x18006c19a  xor     rcx, rsp; StackCookie
0x18006c19d  call    __security_check_cookie
0x18006c1a2  mov     rbx, [rsp+50h+arg_0]
0x18006c1a7  mov     rdi, [rsp+50h+arg_8]
0x18006c1ac  add     rsp, 50h
0x18006c1b0  pop     rbp
0x18006c1b1  retn
0x18006c1b3  mov     ecx, 0C00000E5h; int
0x18006c1b8  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
