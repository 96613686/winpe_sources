# MultipleUseOutOfProcModule::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x140008420`
- end: `0x14000843b`
- name: `?RegisterCOMObject@MultipleUseOutOfProcModule@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `27`
- prototype: `__int64 __fastcall(MultipleUseOutOfProcModule *__hidden this, const unsigned __int16 *, struct _GUID *, struct IClassFactory **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006960`

## pseudocode

```c
__int64 __fastcall MultipleUseOutOfProcModule::RegisterCOMObject(
        MultipleUseOutOfProcModule *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct IClassFactory **a4,
        unsigned int *a5,
        unsigned int a6)
{
  return Microsoft::WRL::Details::RegisterCOMObject<1>((__int64)this, (__int64)a3, (__int64)a4, (__int64)a5, a6);
}

```

## disassembly

```asm
0x140008420  mov     eax, [rsp+arg_28]
0x140008424  mov     r10, r9
0x140008427  mov     r9, [rsp+arg_20]
0x14000842c  mov     rdx, r8
0x14000842f  mov     r8, r10
0x140008432  mov     dword ptr [rsp+arg_20], eax
0x140008436  jmp     ??$RegisterCOMObject@$00@Details@WRL@Microsoft@@YAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z; Microsoft::WRL::Details::RegisterCOMObject<1>(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)
```
