# ServiceMain

- ea: `0x180002f50`
- end: `0x180002f58`
- name: `ServiceMain`
- size: `8`
- prototype: `__int64 __fastcall(ServiceBase *, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005d98`

## pseudocode

```c
__int64 __fastcall ServiceMain(ServiceBase *a1, const unsigned __int16 **a2)
{
  return ServiceBase::ServiceMain(a1, (unsigned int)a2, a2);
}

```

## disassembly

```asm
0x180002f50  mov     r8, rdx; unsigned __int16 **
0x180002f53  jmp     ?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z; ServiceBase::ServiceMain(ulong,ushort const * *)
```
