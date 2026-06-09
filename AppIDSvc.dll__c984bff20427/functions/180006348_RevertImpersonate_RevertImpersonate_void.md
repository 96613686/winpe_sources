# RevertImpersonate::~RevertImpersonate(void)

- ea: `0x180006348`
- end: `0x180006358`
- name: `??1RevertImpersonate@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(RevertImpersonate *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c7b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000634c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000634c`

## pseudocode

```c
void __fastcall RevertImpersonate::~RevertImpersonate(RevertImpersonate *this)
{
  RevertToSelf();
}

```

## disassembly

```asm
0x180006348  sub     rsp, 28h
0x18000634c  call    cs:__imp_RevertToSelf
0x180006352  nop
0x180006353  add     rsp, 28h
0x180006357  retn
```
