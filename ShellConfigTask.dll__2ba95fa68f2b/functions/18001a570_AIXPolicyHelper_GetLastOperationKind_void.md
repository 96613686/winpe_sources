# AIXPolicyHelper::GetLastOperationKind(void)

- ea: `0x18001a570`
- end: `0x18001a5f1`
- name: `?GetLastOperationKind@AIXPolicyHelper@@YA?AW4LastOperationKind@@XZ`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bf24`
- `0x18001fd50`
- `0x180028844`
- `0x18002b864`
- `0x18002d050`

## callees

- `0x18001a570`
- `0x1800233ec`
- `0x180024e7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5e4`

## string_xrefs

- `0x18001a585`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 AIXPolicyHelper::GetLastOperationKind()
{
  HKEY v0; // rcx
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v3; // [rsp+38h] [rbp+10h] BYREF
  char v4; // [rsp+3Ch] [rbp+14h]

  hKey = 0;
  wil::reg::open_unique_key_nothrow(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
    &hKey,
    0);
  v0 = hKey;
  if ( hKey )
  {
    wil::reg::try_get_value_dword(&v3, hKey, L"LastOperationKind");
    if ( v4 && v3 <= 5 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
    v0 = hKey;
  }
  if ( v0 )
    RegCloseKey(v0);
  return 0;
}

```

## disassembly

```asm
0x18001a570  sub     rsp, 28h
0x18001a574  mov     [rsp+28h+hKey], 0
0x18001a57d  xor     r9d, r9d
0x18001a580  lea     r8, [rsp+28h+hKey]; phkResult
0x18001a585  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a58c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a593  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001a598  mov     rcx, [rsp+28h+hKey]
0x18001a59d  test    rcx, rcx
0x18001a5a0  jz      short loc_18001A5DF
0x18001a5a2  lea     r8, aLastoperationk; "LastOperationKind"
0x18001a5a9  mov     rdx, rcx
0x18001a5ac  lea     rcx, [rsp+28h+arg_8]
0x18001a5b1  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18001a5b6  cmp     [rsp+28h+arg_C], 0
0x18001a5bb  jz      short loc_18001A5DA
0x18001a5bd  cmp     [rsp+28h+arg_8], 5
0x18001a5c2  ja      short loc_18001A5DA
0x18001a5c4  mov     rcx, [rsp+28h+hKey]; hKey
0x18001a5c9  test    rcx, rcx
0x18001a5cc  jz      short loc_18001A5D4
0x18001a5ce  call    cs:__imp_RegCloseKey
0x18001a5d4  mov     eax, [rsp+28h+arg_8]
0x18001a5d8  jmp     short loc_18001A5EC
0x18001a5da  mov     rcx, [rsp+28h+hKey]; hKey
0x18001a5df  test    rcx, rcx
0x18001a5e2  jz      short loc_18001A5EA
0x18001a5e4  call    cs:__imp_RegCloseKey
0x18001a5ea  xor     eax, eax
0x18001a5ec  add     rsp, 28h
0x18001a5f0  retn
```
