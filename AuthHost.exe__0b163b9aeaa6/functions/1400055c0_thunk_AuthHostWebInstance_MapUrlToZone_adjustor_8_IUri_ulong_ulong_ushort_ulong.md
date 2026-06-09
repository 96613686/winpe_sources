# [thunk]:AuthHostWebInstance::MapUrlToZone`adjustor{8}' (IUri *,ulong *,ulong,ushort * *,ulong *)

- ea: `0x1400055c0`
- end: `0x1400055c9`
- name: `?MapUrlToZone@AuthHostWebInstance@@W7EAAJPEAUIUri@@PEAKKPEAPEAG1@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400107d0`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::MapUrlToZone(
        __int64 a1,
        struct IUri *a2,
        unsigned int *a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  return AuthHostWebInstance::MapUrlToZone((AuthHostWebInstance *)(a1 - 8), a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1400055c0  sub     rcx, 8; this
0x1400055c4  jmp     ?MapUrlToZone@AuthHostWebInstance@@UEAAJPEAUIUri@@PEAKKPEAPEAG1@Z; AuthHostWebInstance::MapUrlToZone(IUri *,ulong *,ulong,ushort * *,ulong *)
```
