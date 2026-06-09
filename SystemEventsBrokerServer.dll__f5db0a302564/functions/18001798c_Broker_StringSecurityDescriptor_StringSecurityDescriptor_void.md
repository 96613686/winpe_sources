# Broker::StringSecurityDescriptor::~StringSecurityDescriptor(void)

- ea: `0x18001798c`
- end: `0x180017996`
- name: `??1StringSecurityDescriptor@Broker@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(HLOCAL *this)`
- caller_count: `5`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022cc0`
- `0x1800233b0`
- `0x1800243e0`
- `0x1800260b9`
- `0x1800260f1`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001798f`

## pseudocode

```c
void __fastcall Broker::StringSecurityDescriptor::~StringSecurityDescriptor(HLOCAL *this)
{
  LocalFree(*this);
}

```

## disassembly

```asm
0x18001798c  mov     rcx, [rcx]
0x18001798f  jmp     cs:__imp_LocalFree
```
