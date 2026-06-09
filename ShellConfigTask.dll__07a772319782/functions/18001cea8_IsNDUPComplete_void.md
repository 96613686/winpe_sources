# IsNDUPComplete(void)

- ea: `0x18001cea8`
- end: `0x18001cf8a`
- name: `?IsNDUPComplete@@YA_NXZ`
- size: `226`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800146c0`
- `0x18001a754`
- `0x18001f998`

## callees

- `0x18001cea8`
- `0x1800233ec`
- `0x180024e7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf7c`

## string_xrefs

- `0x18001cec0`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Updates`
- `0x18001cedc`: `OOBEUpdateStarted`
- `0x18001cf22`: `EnableExpeditedUpdateSyncInstallCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char IsNDUPComplete(void)
{
  __int64 v0; // rax
  HKEY v1; // rcx
  __int64 value_dword; // rax
  HKEY phkResult; // [rsp+30h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+18h] BYREF
  char v6; // [rsp+40h] [rbp+20h] BYREF

  phkResult = 0;
  wil::reg::open_unique_key_nothrow(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Updates",
    &phkResult,
    0);
  if ( !phkResult
    || (v0 = wil::reg::try_get_value_dword(&v6, phkResult, L"OOBEUpdateStarted"), !*(_BYTE *)(v0 + 4))
    || *(_DWORD *)v0 != 1 )
  {
    hKey = 0;
    wil::reg::open_unique_key_nothrow(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP",
      &hKey,
      0);
    v1 = hKey;
    if ( hKey )
    {
      value_dword = wil::reg::try_get_value_dword(&v6, hKey, L"EnableExpeditedUpdateSyncInstallCompleted");
      if ( *(_BYTE *)(value_dword + 4) && *(_DWORD *)value_dword == 1 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        if ( phkResult )
          RegCloseKey(phkResult);
        return 1;
      }
      v1 = hKey;
    }
    if ( v1 )
      RegCloseKey(v1);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x18001cea8  push    rbp
0x18001ceaa  mov     rbp, rsp
0x18001cead  sub     rsp, 20h
0x18001ceb1  mov     [rbp+phkResult], 0
0x18001ceb9  xor     r9d, r9d
0x18001cebc  lea     r8, [rbp+phkResult]; phkResult
0x18001cec0  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001cec7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cece  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001ced3  mov     rdx, [rbp+phkResult]
0x18001ced7  test    rdx, rdx
0x18001ceda  jz      short loc_18001CEF7
0x18001cedc  lea     r8, aOobeupdatestar; "OOBEUpdateStarted"
0x18001cee3  lea     rcx, [rbp+arg_10]
0x18001cee7  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18001ceec  cmp     byte ptr [rax+4], 0
0x18001cef0  jz      short loc_18001CEF7
0x18001cef2  cmp     dword ptr [rax], 1
0x18001cef5  jz      short loc_18001CF73
0x18001cef7  mov     [rbp+hKey], 0
0x18001ceff  xor     r9d, r9d
0x18001cf02  lea     r8, [rbp+hKey]; phkResult
0x18001cf06  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001cf0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cf14  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001cf19  mov     rcx, [rbp+hKey]
0x18001cf1d  test    rcx, rcx
0x18001cf20  jz      short loc_18001CF67
0x18001cf22  lea     r8, aEnableexpedite; "EnableExpeditedUpdateSyncInstallComplet"...
0x18001cf29  mov     rdx, rcx
0x18001cf2c  lea     rcx, [rbp+arg_10]
0x18001cf30  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18001cf35  cmp     byte ptr [rax+4], 0
0x18001cf39  jz      short loc_18001CF63
0x18001cf3b  cmp     dword ptr [rax], 1
0x18001cf3e  jnz     short loc_18001CF63
0x18001cf40  mov     rcx, [rbp+hKey]; hKey
0x18001cf44  test    rcx, rcx
0x18001cf47  jz      short loc_18001CF50
0x18001cf49  call    cs:__imp_RegCloseKey
0x18001cf4f  nop
0x18001cf50  mov     rcx, [rbp+phkResult]; hKey
0x18001cf54  test    rcx, rcx
0x18001cf57  jz      short loc_18001CF5F
0x18001cf59  call    cs:__imp_RegCloseKey
0x18001cf5f  mov     al, 1
0x18001cf61  jmp     short loc_18001CF84
0x18001cf63  mov     rcx, [rbp+hKey]; hKey
0x18001cf67  test    rcx, rcx
0x18001cf6a  jz      short loc_18001CF73
0x18001cf6c  call    cs:__imp_RegCloseKey
0x18001cf72  nop
0x18001cf73  mov     rcx, [rbp+phkResult]; hKey
0x18001cf77  test    rcx, rcx
0x18001cf7a  jz      short loc_18001CF82
0x18001cf7c  call    cs:__imp_RegCloseKey
0x18001cf82  xor     al, al
0x18001cf84  add     rsp, 20h
0x18001cf88  pop     rbp
0x18001cf89  retn
```
