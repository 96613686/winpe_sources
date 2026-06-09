# DeleteCLSIDRegKey

- ea: `0x180008e60`
- end: `0x180008eb1`
- name: `DeleteCLSIDRegKey`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008680`

## callees

- `0x180001880`
- `0x180008bd0`
- `0x180008e60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008e93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008e93`

## pseudocode

```c
LSTATUS __fastcall DeleteCLSIDRegKey(const struct _GUID *a1)
{
  LSTATUS result; // eax
  WCHAR SubKey[80]; // [rsp+20h] [rbp-B8h] BYREF

  result = MakeCLSIDRegPath(a1, SubKey);
  if ( result >= 0 )
    return RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
  return result;
}

```

## disassembly

```asm
0x180008e60  sub     rsp, 0D8h
0x180008e67  mov     rax, cs:__security_cookie
0x180008e6e  xor     rax, rsp
0x180008e71  mov     [rsp+0D8h+var_18], rax
0x180008e79  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x180008e7e  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x180008e83  test    eax, eax
0x180008e85  js      short loc_180008E99
0x180008e87  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x180008e8c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180008e93  call    cs:__imp_RegDeleteTreeW
0x180008e99  mov     rcx, [rsp+0D8h+var_18]
0x180008ea1  xor     rcx, rsp; StackCookie
0x180008ea4  call    __security_check_cookie
0x180008ea9  add     rsp, 0D8h
0x180008eb0  retn
```
