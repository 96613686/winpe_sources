# MbbNdisSetDeviceServiceCommand(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140010db0`
- end: `0x140010dbf`
- name: `?MbbNdisSetDeviceServiceCommand@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `15`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001e7b8`

## pseudocode

```c
__int64 __fastcall MbbNdisSetDeviceServiceCommand(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  return MbbUtilDeviceServiceCommand(a1, a2, a3);
}

```

## disassembly

```asm
0x140010db0  sub     rsp, 28h
0x140010db4  call    ?MbbUtilDeviceServiceCommand@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z; MbbUtilDeviceServiceCommand(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)
0x140010db9  add     rsp, 28h
0x140010dbd  retn
```
