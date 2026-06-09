# Windows::Registry::DeleteSystemValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002de30`
- end: `0x18002df7d`
- name: `?DeleteSystemValue@Registry@Windows@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x18002de30`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002de92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002de92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df59`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002df02`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002df02`

## string_xrefs

- `0x18002dede`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x18002df3e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Registry::DeleteSystemValue(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4)
{
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  const char *v7; // r9
  const WCHAR *v8; // rdx
  LPCWSTR *v9; // rax
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // r9
  LPCWSTR *v13; // rax
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a2, a3);
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( v17 > 7 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20006u, &hKey);
  v7 = (const char *)v6;
  if ( v6 - 2 > 1 )
  {
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v8 = a4;
    else
      v8 = *(const WCHAR **)a4;
    v9 = lpSubKey;
    if ( v17 > 7 )
      v9 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      v7,
      (unsigned int)"%ws[%ws]",
      (const char *)v9,
      v8);
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v10 = a4;
    else
      v10 = *(const WCHAR **)a4;
    v11 = RegDeleteValueW(hKey, v10);
    v12 = (const char *)v11;
    if ( v11 - 2 > 1 )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const WCHAR **)a4;
      v13 = lpSubKey;
      if ( v17 > 7 )
        v13 = (LPCWSTR *)lpSubKey[0];
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
        v12,
        (unsigned int)"%ws[%ws]",
        (const char *)v13,
        a4);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return std::wstring::_Tidy_deallocate(lpSubKey);
}

```

## disassembly

```asm
0x18002de30  push    rbp
0x18002de32  push    rbx
0x18002de33  push    rdi
0x18002de34  mov     rbp, rsp
0x18002de37  sub     rsp, 70h
0x18002de3b  mov     rax, cs:__security_cookie
0x18002de42  xor     rax, rsp
0x18002de45  mov     [rbp+var_8], rax
0x18002de49  mov     rbx, r9
0x18002de4c  mov     rax, [rcx]
0x18002de4f  mov     r9, r8
0x18002de52  mov     r8, rdx
0x18002de55  lea     rdx, [rbp+lpSubKey]
0x18002de59  mov     rax, [rax+58h]
0x18002de5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de62  nop
0x18002de63  mov     [rbp+hKey], 0
0x18002de6b  lea     rdx, [rbp+lpSubKey]
0x18002de6f  cmp     [rbp+var_10], 7
0x18002de74  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18002de79  lea     rax, [rbp+hKey]
0x18002de7d  mov     [rsp+70h+phkResult], rax; phkResult
0x18002de82  mov     r9d, 20006h; samDesired
0x18002de88  xor     r8d, r8d; ulOptions
0x18002de8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002de92  call    cs:__imp_RegOpenKeyExW
0x18002de98  mov     r9d, eax; char *
0x18002de9b  lea     ecx, [rax-2]
0x18002de9e  cmp     ecx, 1
0x18002dea1  jbe     loc_18002DF50
0x18002dea7  cmp     qword ptr [rbx+18h], 7
0x18002deac  jbe     short loc_18002DEB3
0x18002deae  mov     rdx, [rbx]
0x18002deb1  jmp     short loc_18002DEB6
0x18002deb3  mov     rdx, rbx
0x18002deb6  lea     rax, [rbp+lpSubKey]
0x18002deba  cmp     [rbp+var_10], 7
0x18002debf  cmova   rax, [rbp+lpSubKey]
0x18002dec4  mov     rcx, [rbp+18h]; this
0x18002dec8  mov     [rsp+70h+var_40], rdx
0x18002decd  mov     [rsp+70h+var_48], rax; char *
0x18002ded2  lea     rdi, aWsWs; "%ws[%ws]"
0x18002ded9  mov     [rsp+70h+phkResult], rdi; unsigned int
0x18002dede  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002dee5  mov     edx, 1A4h; void *
0x18002deea  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002deef  cmp     qword ptr [rbx+18h], 7
0x18002def4  jbe     short loc_18002DEFB
0x18002def6  mov     rdx, [rbx]
0x18002def9  jmp     short loc_18002DEFE
0x18002defb  mov     rdx, rbx; lpValueName
0x18002defe  mov     rcx, [rbp+hKey]; hKey
0x18002df02  call    cs:__imp_RegDeleteValueW
0x18002df08  mov     r9d, eax; char *
0x18002df0b  lea     ecx, [rax-2]
0x18002df0e  cmp     ecx, 1
0x18002df11  jbe     short loc_18002DF50
0x18002df13  cmp     qword ptr [rbx+18h], 7
0x18002df18  jbe     short loc_18002DF1D
0x18002df1a  mov     rbx, [rbx]
0x18002df1d  lea     rax, [rbp+lpSubKey]
0x18002df21  cmp     [rbp+var_10], 7
0x18002df26  cmova   rax, [rbp+lpSubKey]
0x18002df2b  mov     rcx, [rbp+18h]; this
0x18002df2f  mov     [rsp+70h+var_40], rbx
0x18002df34  mov     [rsp+70h+var_48], rax; char *
0x18002df39  mov     [rsp+70h+phkResult], rdi; unsigned int
0x18002df3e  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002df45  mov     edx, 1AEh; void *
0x18002df4a  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002df4f  nop
0x18002df50  mov     rcx, [rbp+hKey]; hKey
0x18002df54  test    rcx, rcx
0x18002df57  jz      short loc_18002DF60
0x18002df59  call    cs:__imp_RegCloseKey
0x18002df5f  nop
0x18002df60  lea     rcx, [rbp+lpSubKey]
0x18002df64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df69  mov     rcx, [rbp+var_8]
0x18002df6d  xor     rcx, rsp; StackCookie
0x18002df70  call    __security_check_cookie
0x18002df75  add     rsp, 70h
0x18002df79  pop     rdi
0x18002df7a  pop     rbx
0x18002df7b  pop     rbp
0x18002df7c  retn
```
