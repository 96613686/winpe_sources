# CredentialUpdateRegister2(_UNICODE_STRING *)

- ea: `0x180004470`
- end: `0x180004488`
- name: `?CredentialUpdateRegister2@@YAEPEAU_UNICODE_STRING@@@Z`
- size: `24`
- prototype: `unsigned __int8 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000447b`
- `ntdll!RtlInitUnicodeString` at `0x18000447b`

## pseudocode

```c
unsigned __int8 __fastcall CredentialUpdateRegister2(struct _UNICODE_STRING *a1)
{
  RtlInitUnicodeString(a1, L"Kerberos-Newer-Keys");
  return 1;
}

```

## disassembly

```asm
0x180004470  sub     rsp, 28h
0x180004474  lea     rdx, SourceString; "Kerberos-Newer-Keys"
0x18000447b  call    cs:__imp_RtlInitUnicodeString
0x180004481  mov     al, 1
0x180004483  add     rsp, 28h
0x180004487  retn
```
