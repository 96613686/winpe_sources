# SystemSettings::PenSettings::ActionTypeOptionManager::IsOneNoteDesktopInstalled(void)

- ea: `0x18002c580`
- end: `0x18002c5eb`
- name: `?IsOneNoteDesktopInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SA_NXZ`
- size: `107`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028910`
- `0x18002a3d4`

## callees

- `0x180020614`
- `0x180020780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c5c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c5c4`

## string_xrefs

- `0x18002c598`: `SOFTWARE\Microsoft\Windows\CurrentVersion\App Paths\OneNote.exe`

## pseudocode

```c
bool SystemSettings::PenSettings::ActionTypeOptionManager::IsOneNoteDesktopInstalled(void)
{
  bool v0; // bl
  __int64 *v2; // [rsp+30h] [rbp-28h] BYREF
  HKEY v3; // [rsp+38h] [rbp-20h] BYREF
  char v4; // [rsp+40h] [rbp-18h]
  __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v2 = &v5;
  v5 = 0;
  v4 = 1;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\App Paths\\OneNote.exe",
         0,
         0x20019u,
         &v3) == 0;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v5);
  return v0;
}

```

## disassembly

```asm
0x18002c580  mov     r11, rsp
0x18002c583  push    rbx
0x18002c584  sub     rsp, 50h
0x18002c588  lea     rax, [r11+8]
0x18002c58c  mov     qword ptr [r11-20h], 0
0x18002c594  mov     [r11-28h], rax
0x18002c598  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002c59f  lea     rax, [r11-20h]
0x18002c5a3  mov     qword ptr [r11+8], 0
0x18002c5ab  mov     r9d, 20019h; samDesired
0x18002c5b1  mov     [r11-38h], rax
0x18002c5b5  xor     r8d, r8d; ulOptions
0x18002c5b8  mov     [rsp+58h+var_18], 1
0x18002c5bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c5c4  call    cs:__imp_RegOpenKeyExW
0x18002c5ca  test    eax, eax
0x18002c5cc  lea     rcx, [rsp+58h+var_28]
0x18002c5d1  setz    bl
0x18002c5d4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002c5d9  lea     rcx, [rsp+58h+arg_0]
0x18002c5de  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c5e3  mov     al, bl
0x18002c5e5  add     rsp, 50h
0x18002c5e9  pop     rbx
0x18002c5ea  retn
```
