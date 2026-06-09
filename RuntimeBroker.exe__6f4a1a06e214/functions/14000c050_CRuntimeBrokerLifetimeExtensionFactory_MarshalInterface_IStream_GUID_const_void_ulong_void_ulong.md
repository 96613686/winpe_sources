# CRuntimeBrokerLifetimeExtensionFactory::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x14000c050`
- end: `0x14000c09c`
- name: `?MarshalInterface@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `76`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c050`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::MarshalInterface(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  __int64 v7; // rcx

  v7 = *((_QWORD *)this + 2);
  if ( v7 )
    return (*(__int64 (__fastcall **)(__int64, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int))(*(_QWORD *)v7 + 40LL))(
             v7,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x14000c050  sub     rsp, 48h
0x14000c054  mov     rcx, [rcx+10h]
0x14000c058  mov     r11, r8
0x14000c05b  test    rcx, rcx
0x14000c05e  jz      short loc_14000C092
0x14000c060  mov     r10d, [rsp+48h+arg_30]
0x14000c068  mov     rax, [rcx]
0x14000c06b  mov     r8d, [rsp+48h+arg_20]
0x14000c070  mov     [rsp+48h+var_18], r10d
0x14000c075  mov     r10, [rsp+48h+arg_28]
0x14000c07a  mov     rax, [rax+28h]
0x14000c07e  mov     [rsp+48h+var_20], r10
0x14000c083  mov     [rsp+48h+var_28], r8d
0x14000c088  mov     r8, r11
0x14000c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c090  jmp     short loc_14000C097
0x14000c092  mov     eax, 8007000Eh
0x14000c097  add     rsp, 48h
0x14000c09b  retn
```
