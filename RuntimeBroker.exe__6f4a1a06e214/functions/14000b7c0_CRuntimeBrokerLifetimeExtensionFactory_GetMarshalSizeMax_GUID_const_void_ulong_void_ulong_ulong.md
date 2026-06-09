# CRuntimeBrokerLifetimeExtensionFactory::GetMarshalSizeMax(_GUID const &,void *,ulong,void *,ulong,ulong *)

- ea: `0x14000b7c0`
- end: `0x14000b80c`
- name: `?GetMarshalSizeMax@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJAEBU_GUID@@PEAXK1KPEAK@Z`
- size: `76`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, const struct _GUID *, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b7c0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::GetMarshalSizeMax(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        const struct _GUID *a2,
        void *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 2);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void *))(*(_QWORD *)v3 + 32LL))(v3, a2, a3);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x14000b7c0  sub     rsp, 48h
0x14000b7c4  mov     rcx, [rcx+10h]
0x14000b7c8  mov     r11, r8
0x14000b7cb  test    rcx, rcx
0x14000b7ce  jz      short loc_14000B802
0x14000b7d0  mov     r10, [rsp+48h+arg_30]
0x14000b7d8  mov     rax, [rcx]
0x14000b7db  mov     r8, [rsp+48h+arg_20]
0x14000b7e0  mov     [rsp+48h+var_18], r10
0x14000b7e5  mov     r10d, [rsp+48h+arg_28]
0x14000b7ea  mov     rax, [rax+20h]
0x14000b7ee  mov     [rsp+48h+var_20], r10d
0x14000b7f3  mov     [rsp+48h+var_28], r8
0x14000b7f8  mov     r8, r11
0x14000b7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b800  jmp     short loc_14000B807
0x14000b802  mov     eax, 8007000Eh
0x14000b807  add     rsp, 48h
0x14000b80b  retn
```
