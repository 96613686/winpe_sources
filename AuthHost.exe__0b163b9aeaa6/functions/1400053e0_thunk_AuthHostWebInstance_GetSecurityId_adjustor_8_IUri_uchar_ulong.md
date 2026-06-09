# [thunk]:AuthHostWebInstance::GetSecurityId`adjustor{8}' (IUri *,uchar *,ulong *)

- ea: `0x1400053e0`
- end: `0x1400053e9`
- name: `?GetSecurityId@AuthHostWebInstance@@W7EAAJPEAUIUri@@PEAEPEAK@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010470`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetSecurityId(
        __int64 a1,
        struct IUri *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  return AuthHostWebInstance::GetSecurityId((AuthHostWebInstance *)(a1 - 8), a2, a3, a4);
}

```

## disassembly

```asm
0x1400053e0  sub     rcx, 8; this
0x1400053e4  jmp     ?GetSecurityId@AuthHostWebInstance@@UEAAJPEAUIUri@@PEAEPEAK@Z; AuthHostWebInstance::GetSecurityId(IUri *,uchar *,ulong *)
```
