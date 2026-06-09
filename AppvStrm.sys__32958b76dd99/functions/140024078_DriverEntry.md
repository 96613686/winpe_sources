# DriverEntry

- ea: `0x140024078`
- end: `0x140024095`
- name: `DriverEntry`
- size: `29`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140024010`

## callees

- `0x1400135b4`
- `0x140024044`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  struct _UNICODE_STRING *v3; // rdx

  _security_init_cookie();
  return DriverInitialize(DriverObject, v3);
}

```

## disassembly

```asm
0x140024078  push    rbx
0x14002407a  sub     rsp, 20h
0x14002407e  mov     rbx, rcx
0x140024081  call    __security_init_cookie
0x140024086  mov     rcx, rbx; struct _DRIVER_OBJECT *
0x140024089  call    ?DriverInitialize@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; DriverInitialize(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x14002408e  add     rsp, 20h
0x140024092  pop     rbx
0x140024093  retn
```
