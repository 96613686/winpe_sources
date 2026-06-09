# std::unique_ptr<Broker::DeviceServicesEvent,std::default_delete<Broker::DeviceServicesEvent>>::~unique_ptr<Broker::DeviceServicesEvent,std::default_delete<Broker::DeviceServicesEvent>>(void)

- ea: `0x180016b0c`
- end: `0x180016b2d`
- name: `??1?$unique_ptr@VDeviceServicesEvent@Broker@@U?$default_delete@VDeviceServicesEvent@Broker@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021920`
- `0x1800231c0`
- `0x1800231e0`
- `0x1800232a0`
- `0x180024be3`
- `0x180024c10`
- `0x1800261aa`

## callees

- `0x180016b0c`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Broker::DeviceServicesEvent>::~unique_ptr<Broker::DeviceServicesEvent>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180016b0c  sub     rsp, 28h
0x180016b10  mov     rcx, [rcx]
0x180016b13  test    rcx, rcx
0x180016b16  jz      short loc_180016B28
0x180016b18  mov     rax, [rcx]
0x180016b1b  mov     edx, 1
0x180016b20  mov     rax, [rax]
0x180016b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b28  add     rsp, 28h
0x180016b2c  retn
```
