# SyncRootManagerSettingsProviderHelpers::RegDeleteTreeHelper(HKEY__ *,ushort const *)

- ea: `0x180032f10`
- end: `0x180032fae`
- name: `?RegDeleteTreeHelper@SyncRootManagerSettingsProviderHelpers@@YAXPEAUHKEY__@@PEBG@Z`
- size: `158`
- prototype: `void __fastcall(HKEY hKey, HKEY lpSubKey, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a4e4`
- `0x180032cd0`

## callees

- `0x180004d6c`
- `0x180020358`
- `0x180032f10`
- `0x180059c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032f70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032f70`

## string_xrefs

- `0x180032f82`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SyncRootManagerSettingsProviderHelpers::RegDeleteTreeHelper(
        HKEY hKey,
        const WCHAR *lpSubKey,
        const unsigned __int16 *a3)
{
  LSTATUS v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h]
  __int64 *v8; // [rsp+30h] [rbp-28h] BYREF
  HKEY v9; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  v8 = &v12;
  v9 = 0;
  v10 = 1;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20119u, &v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
  if ( !v5 )
  {
    v6 = RegDeleteTreeW(hKey, lpSubKey);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCD,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
        (const char *)v6,
        v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
}

```

## disassembly

```asm
0x180032f10  mov     r11, rsp
0x180032f13  mov     [r11+8], rbx
0x180032f17  mov     [r11+10h], rsi
0x180032f1b  push    rdi
0x180032f1c  sub     rsp, 50h
0x180032f20  mov     rdi, rdx
0x180032f23  mov     rsi, rcx
0x180032f26  mov     qword ptr [r11+18h], 0
0x180032f2e  lea     rax, [r11+18h]
0x180032f32  mov     [r11-28h], rax
0x180032f36  mov     qword ptr [r11-20h], 0
0x180032f3e  mov     [rsp+58h+var_18], 1
0x180032f43  lea     rax, [r11-20h]
0x180032f47  mov     [r11-38h], rax
0x180032f4b  mov     r9d, 20119h; samDesired
0x180032f51  xor     r8d, r8d; ulOptions
0x180032f54  call    cs:__imp_RegOpenKeyExW
0x180032f5a  mov     ebx, eax
0x180032f5c  lea     rcx, [rsp+58h+var_28]
0x180032f61  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180032f66  test    ebx, ebx
0x180032f68  jnz     short loc_180032F94
0x180032f6a  mov     rdx, rdi; lpSubKey
0x180032f6d  mov     rcx, rsi; hKey
0x180032f70  call    cs:__imp_RegDeleteTreeW
0x180032f76  mov     rcx, [rsp+58h]; this
0x180032f7b  test    eax, eax
0x180032f7d  jz      short loc_180032F94
0x180032f7f  mov     r9d, eax; char *
0x180032f82  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x180032f89  mov     edx, 0CDh; void *
0x180032f8e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180032f94  lea     rcx, [rsp+58h+arg_10]
0x180032f99  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180032f9e  mov     rbx, [rsp+58h+arg_0]
0x180032fa3  mov     rsi, [rsp+58h+arg_8]
0x180032fa8  add     rsp, 50h
0x180032fac  pop     rdi
0x180032fad  retn
```
