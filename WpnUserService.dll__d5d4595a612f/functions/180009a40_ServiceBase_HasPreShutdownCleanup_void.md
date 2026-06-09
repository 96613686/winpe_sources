# ServiceBase::HasPreShutdownCleanup(void)

- ea: `0x180009a40`
- end: `0x180009a43`
- name: `?HasPreShutdownCleanup@ServiceBase@@UEAA_NXZ`
- size: `3`
- prototype: `bool __fastcall(ServiceBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
bool __fastcall ServiceBase::HasPreShutdownCleanup(ServiceBase *this)
{
  return 0;
}

```

## disassembly

```asm
0x180009a40  xor     al, al
0x180009a42  retn
```
