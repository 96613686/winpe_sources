# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x1800234ec`
- end: `0x18002365b`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020c30`

## callees

- `0x180021794`
- `0x1800234ec`
- `0x180023664`
- `0x18002d2b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800235ba`
- `KERNEL32!GetLastError` at `0x1800235d1`
- `KERNEL32!GetLastError` at `0x18002360a`
- `KERNEL32!GetLastError` at `0x18002361a`
- `KERNEL32!GetLastError` at `0x1800235ba`
- `KERNEL32!GetLastError` at `0x1800235d1`
- `KERNEL32!GetLastError` at `0x18002360a`
- `KERNEL32!GetLastError` at `0x18002361a`
- `KERNEL32!LoadLibraryExW` at `0x18002359b`
- `KERNEL32!LoadLibraryExW` at `0x18002359b`
- `KERNEL32!GetProcAddress` at `0x1800235f6`
- `KERNEL32!GetProcAddress` at `0x1800235f6`
- `ntdll!RtlRaiseStatus` at `0x18002362f`
- `ntdll!RtlRaiseStatus` at `0x18002362f`

## string_xrefs

- `0x18002351e`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18002355e`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x180023594`: `kernelbase.dll`
- `0x1800235ef`: `GetTempPath2W`
- `0x180023531`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x180023571`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x18002353c`: `Not-null check failed: phDll`

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
LABEL_16:
    RtlRaiseStatus(-1073741595);
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
    goto LABEL_16;
LABEL_11:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800234ec  mov     [rsp-8+arg_0], rbx
0x1800234f1  mov     [rsp-8+arg_8], rdi
0x1800234f6  push    rbp
0x1800234f7  mov     rbp, rsp
0x1800234fa  sub     rsp, 50h
0x1800234fe  mov     rax, cs:__security_cookie
0x180023505  xor     rax, rsp
0x180023508  mov     [rbp+var_8], rax
0x18002350c  mov     [rbp+var_10], 0
0x180023513  mov     rbx, r9
0x180023516  mov     rdi, r8
0x180023519  test    r8, r8
0x18002351c  jnz     short loc_180023559
0x18002351e  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180023525  mov     [rbp+var_20], 6Ch ; 'l'
0x18002352d  mov     [rbp+var_30], rax
0x180023531  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x180023538  mov     [rbp+var_28], rax
0x18002353c  lea     rax, aNotNullCheckFa_89; "Not-null check failed: phDll"
0x180023543  lea     rdx, [rbp+var_30]
0x180023547  mov     [rbp+var_18], rax
0x18002354b  lea     rcx, [rbp+var_10]
0x18002354f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180023554  jmp     loc_18002363E
0x180023559  test    rbx, rbx
0x18002355c  jnz     short loc_180023585
0x18002355e  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180023565  mov     [rbp+var_20], 6Dh ; 'm'
0x18002356d  mov     [rbp+var_30], rax
0x180023571  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x180023578  mov     [rbp+var_28], rax
0x18002357c  lea     rax, aNotNullCheckFa_35; "Not-null check failed: ppfn"
0x180023583  jmp     short loc_180023543
0x180023585  xor     edx, edx; hFile
0x180023587  mov     qword ptr [r9], 0
0x18002358e  mov     r8d, 800h; dwFlags
0x180023594  lea     rcx, LibFileName; "kernelbase.dll"
0x18002359b  call    cs:__imp_LoadLibraryExW
0x1800235a2  nop     dword ptr [rax+rax+00h]
0x1800235a7  mov     rdx, rax
0x1800235aa  mov     rcx, rdi
0x1800235ad  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x1800235b2  mov     rcx, [rdi]; hModule
0x1800235b5  test    rcx, rcx
0x1800235b8  jnz     short loc_1800235EF
0x1800235ba  call    cs:__imp_GetLastError
0x1800235c1  nop     dword ptr [rax+rax+00h]
0x1800235c6  test    eax, eax
0x1800235c8  jnz     short loc_1800235D1
0x1800235ca  mov     eax, 36FDh
0x1800235cf  jmp     short loc_1800235E1
0x1800235d1  call    cs:__imp_GetLastError
0x1800235d8  nop     dword ptr [rax+rax+00h]
0x1800235dd  test    eax, eax
0x1800235df  jz      short loc_18002362A
0x1800235e1  test    eax, eax
0x1800235e3  jle     short loc_18002363E
0x1800235e5  movzx   eax, ax
0x1800235e8  or      eax, 80070000h
0x1800235ed  jmp     short loc_18002363E
0x1800235ef  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800235f6  call    cs:__imp_GetProcAddress
0x1800235fd  nop     dword ptr [rax+rax+00h]
0x180023602  mov     [rbx], rax
0x180023605  test    rax, rax
0x180023608  jnz     short loc_18002363C
0x18002360a  call    cs:__imp_GetLastError
0x180023611  nop     dword ptr [rax+rax+00h]
0x180023616  test    eax, eax
0x180023618  jz      short loc_1800235CA
0x18002361a  call    cs:__imp_GetLastError
0x180023621  nop     dword ptr [rax+rax+00h]
0x180023626  test    eax, eax
0x180023628  jnz     short loc_1800235E3
0x18002362a  mov     ecx, 0C00000E5h; Status
0x18002362f  call    cs:__imp_RtlRaiseStatus
0x180023636  nop     dword ptr [rax+rax+00h]
0x18002363b  int     3; Trap to Debugger
0x18002363c  xor     eax, eax
0x18002363e  mov     rcx, [rbp+var_8]
0x180023642  xor     rcx, rsp; StackCookie
0x180023645  call    __security_check_cookie
0x18002364a  mov     rbx, [rsp+50h+arg_0]
0x18002364f  mov     rdi, [rsp+50h+arg_8]
0x180023654  add     rsp, 50h
0x180023658  pop     rbp
0x180023659  retn
```
