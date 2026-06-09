# DeleteAutoUpdatePauseEndTimeKey(void)

- ea: `0x180020ea8`
- end: `0x180020edc`
- name: `?DeleteAutoUpdatePauseEndTimeKey@@YAXXZ`
- size: `52`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020a1c`

## callees

- `0x180029190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180020ed0`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180020ed0`

## string_xrefs

- `0x180020eac`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180020ebf`: `AutoUpdatePauseEndTime`

## pseudocode

```c
void DeleteAutoUpdatePauseEndTimeKey(void)
{
  const WCHAR *RegistryLocation; // rax

  RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                      &qword_18006A458,
                                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
  RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, RegistryLocation, L"AutoUpdatePauseEndTime");
}

```

## disassembly

```asm
0x180020ea8  sub     rsp, 48h
0x180020eac  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180020eb3  lea     rcx, qword_18006A458
0x180020eba  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180020ebf  lea     r8, ValueName; "AutoUpdatePauseEndTime"
0x180020ec6  mov     rdx, rax; lpSubKey
0x180020ec9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020ed0  call    cs:__imp_RegDeleteKeyValueW
0x180020ed6  nop
0x180020ed7  add     rsp, 48h
0x180020edb  retn
```
