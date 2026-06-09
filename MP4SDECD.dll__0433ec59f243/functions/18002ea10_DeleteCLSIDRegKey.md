# DeleteCLSIDRegKey

- ea: `0x18002ea10`
- end: `0x18002ea61`
- name: `DeleteCLSIDRegKey`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e450`

## callees

- `0x18002aac0`
- `0x18002e600`
- `0x18002ea10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ea43`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ea43`

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
0x18002ea10  sub     rsp, 0D8h
0x18002ea17  mov     rax, cs:__security_cookie
0x18002ea1e  xor     rax, rsp
0x18002ea21  mov     [rsp+0D8h+var_18], rax
0x18002ea29  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x18002ea2e  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18002ea33  test    eax, eax
0x18002ea35  js      short loc_18002EA49
0x18002ea37  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18002ea3c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002ea43  call    cs:__imp_RegDeleteTreeW
0x18002ea49  mov     rcx, [rsp+0D8h+var_18]
0x18002ea51  xor     rcx, rsp; StackCookie
0x18002ea54  call    __security_check_cookie
0x18002ea59  add     rsp, 0D8h
0x18002ea60  retn
```
