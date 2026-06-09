# DeleteCLSIDRegKey

- ea: `0x180008f20`
- end: `0x180008f71`
- name: `DeleteCLSIDRegKey`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008740`

## callees

- `0x1800018b0`
- `0x180008c90`
- `0x180008f20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008f53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008f53`

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
0x180008f20  sub     rsp, 0D8h
0x180008f27  mov     rax, cs:__security_cookie
0x180008f2e  xor     rax, rsp
0x180008f31  mov     [rsp+0D8h+var_18], rax
0x180008f39  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x180008f3e  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x180008f43  test    eax, eax
0x180008f45  js      short loc_180008F59
0x180008f47  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x180008f4c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180008f53  call    cs:__imp_RegDeleteTreeW
0x180008f59  mov     rcx, [rsp+0D8h+var_18]
0x180008f61  xor     rcx, rsp; StackCookie
0x180008f64  call    __security_check_cookie
0x180008f69  add     rsp, 0D8h
0x180008f70  retn
```
