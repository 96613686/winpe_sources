# DriverEntry

- ea: `0x180016204`
- end: `0x180016221`
- name: `DriverEntry`
- size: `29`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e010`

## callees

- `0x180015fa4`
- `0x18002e044`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  struct _DEVICE_OBJECT *v3; // rdx

  _security_init_cookie();
  return DriverInitialize(DriverObject, v3);
}

```

## disassembly

```asm
0x180016204  push    rbx
0x180016206  sub     rsp, 20h
0x18001620a  mov     rbx, rcx
0x18001620d  call    __security_init_cookie
0x180016212  mov     rcx, rbx; Driver
0x180016215  call    ?DriverInitialize@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; DriverInitialize(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x18001621a  add     rsp, 20h
0x18001621e  pop     rbx
0x18001621f  retn
```
