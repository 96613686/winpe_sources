# Broker::StringSecurityDescriptor::~StringSecurityDescriptor(void)

- ea: `0x18000edcc`
- end: `0x18000edd6`
- name: `??1StringSecurityDescriptor@Broker@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(HLOCAL *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a14a`
- `0x18001abec`
- `0x18001bebd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000edcf`

## pseudocode

```c
void __fastcall Broker::StringSecurityDescriptor::~StringSecurityDescriptor(HLOCAL *this)
{
  LocalFree(*this);
}

```

## disassembly

```asm
0x18000edcc  mov     rcx, [rcx]
0x18000edcf  jmp     cs:__imp_LocalFree
```
