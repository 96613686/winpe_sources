# [thunk]:AuthHostWebInstance::ProcessUrlAction`adjustor{8}' (IUri *,ulong,uchar *,ulong,uchar *,ulong,ulong,ulong *)

- ea: `0x140005760`
- end: `0x140005769`
- name: `?ProcessUrlAction@AuthHostWebInstance@@W7EAAJPEAUIUri@@KPEAEK1KKPEAK@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010820`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::ProcessUrlAction(
        __int64 a1,
        struct IUri *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int *a9)
{
  return AuthHostWebInstance::ProcessUrlAction((AuthHostWebInstance *)(a1 - 8), a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x140005760  sub     rcx, 8; this
0x140005764  jmp     ?ProcessUrlAction@AuthHostWebInstance@@UEAAJPEAUIUri@@KPEAEK1KKPEAK@Z; AuthHostWebInstance::ProcessUrlAction(IUri *,ulong,uchar *,ulong,uchar *,ulong,ulong,ulong *)
```
