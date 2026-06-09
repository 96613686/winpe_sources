# [thunk]:AuthHostWebInstance::QueryCustomPolicy`adjustor{8}' (IUri *,_GUID const &,uchar * *,ulong *,uchar *,ulong)

- ea: `0x140005770`
- end: `0x140005779`
- name: `?QueryCustomPolicy@AuthHostWebInstance@@W7EAAJPEAUIUri@@AEBU_GUID@@PEAPEAEPEAKPEAEK@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011180`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::QueryCustomPolicy(
        __int64 a1,
        struct IUri *a2,
        const struct _GUID *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        IID *a6,
        unsigned int a7)
{
  return AuthHostWebInstance::QueryCustomPolicy((AuthHostWebInstance *)(a1 - 8), a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x140005770  sub     rcx, 8; this
0x140005774  jmp     ?QueryCustomPolicy@AuthHostWebInstance@@UEAAJPEAUIUri@@AEBU_GUID@@PEAPEAEPEAKPEAEK@Z; AuthHostWebInstance::QueryCustomPolicy(IUri *,_GUID const &,uchar * *,ulong *,uchar *,ulong)
```
