# CredentialUpdateRegister(_UNICODE_STRING *)

- ea: `0x180004490`
- end: `0x1800044a8`
- name: `?CredentialUpdateRegister@@YAEPEAU_UNICODE_STRING@@@Z`
- size: `24`
- prototype: `unsigned __int8 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000449b`
- `ntdll!RtlInitUnicodeString` at `0x18000449b`

## pseudocode

```c
unsigned __int8 __fastcall CredentialUpdateRegister(struct _UNICODE_STRING *a1)
{
  RtlInitUnicodeString(a1, L"Kerberos");
  return 1;
}

```

## disassembly

```asm
0x180004490  sub     rsp, 28h
0x180004494  lea     rdx, aKerberos; "Kerberos"
0x18000449b  call    cs:__imp_RtlInitUnicodeString
0x1800044a1  mov     al, 1
0x1800044a3  add     rsp, 28h
0x1800044a7  retn
```
