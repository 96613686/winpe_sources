# ServiceMain

- ea: `0x18000d3b0`
- end: `0x18000d3c1`
- name: `ServiceMain`
- size: `17`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000e9e8`

## pseudocode

```c
__int64 __fastcall ServiceMain(unsigned int a1, const unsigned __int16 **a2)
{
  return ServiceBase::ServiceMain((ServiceBase *)&g_wpnUserService, a1, a2);
}

```

## disassembly

```asm
0x18000d3b0  mov     r8, rdx; unsigned __int16 **
0x18000d3b3  mov     edx, ecx; unsigned int
0x18000d3b5  lea     rcx, ?g_wpnUserService@@3V?$object_without_destructor_on_shutdown@VWpnUserService@@@wil@@A; this
0x18000d3bc  jmp     ?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z; ServiceBase::ServiceMain(ulong,ushort const * *)
```
