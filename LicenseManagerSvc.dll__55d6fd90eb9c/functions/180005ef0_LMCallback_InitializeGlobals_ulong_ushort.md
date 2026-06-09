# LMCallback::InitializeGlobals(ulong,ushort * *)

- ea: `0x180005ef0`
- end: `0x180005ef7`
- name: `?InitializeGlobals@LMCallback@@UEAAJKPEAPEAG@Z`
- size: `7`
- prototype: `__int64 __fastcall(LMCallback *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `LicenseManager!ServiceInitialize` at `0x180005ef0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall LMCallback::InitializeGlobals(LMCallback *this, unsigned int a2, unsigned __int16 **a3)
{
  return ServiceInitialize(this, a2, a3);
}

```

## disassembly

```asm
0x180005ef0  jmp     cs:__imp_ServiceInitialize
```
