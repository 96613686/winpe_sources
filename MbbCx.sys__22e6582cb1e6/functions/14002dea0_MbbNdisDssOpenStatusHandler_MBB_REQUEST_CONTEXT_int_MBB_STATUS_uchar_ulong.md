# MbbNdisDssOpenStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002dea0`
- end: `0x14002deaf`
- name: `?MbbNdisDssOpenStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `15`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14002deb8`

## pseudocode

```c
__int64 __fastcall MbbNdisDssOpenStatusHandler(__int64 a1, int a2, unsigned int a3)
{
  return MbbNdisDssStateStatusHandler(a1, a2, a3);
}

```

## disassembly

```asm
0x14002dea0  sub     rsp, 38h
0x14002dea4  call    ?MbbNdisDssStateStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEKW4_WWAN_DEVICE_SERVICE_SESSION_STATE@@@Z; MbbNdisDssStateStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong,_WWAN_DEVICE_SERVICE_SESSION_STATE)
0x14002dea9  add     rsp, 38h
0x14002dead  retn
```
