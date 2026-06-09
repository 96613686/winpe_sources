# CRuntimeBrokerLifetimeExtensionFactory::GetUnmarshalClass(_GUID const &,void *,ulong,void *,ulong,_GUID *)

- ea: `0x140007080`
- end: `0x1400070cc`
- name: `?GetUnmarshalClass@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJAEBU_GUID@@PEAXK1KPEAU2@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, const struct _GUID *, void *, unsigned int, void *, unsigned int, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007080`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::GetUnmarshalClass(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        const struct _GUID *a2,
        void *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 2);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void *))(*(_QWORD *)v3 + 24LL))(v3, a2, a3);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x140007080  sub     rsp, 48h
0x140007084  mov     rcx, [rcx+10h]
0x140007088  mov     r11, r8
0x14000708b  test    rcx, rcx
0x14000708e  jz      short loc_1400070C5
0x140007090  mov     r10, [rsp+48h+arg_30]
0x140007098  mov     rax, [rcx]
0x14000709b  mov     r8, [rsp+48h+arg_20]
0x1400070a0  mov     [rsp+48h+var_18], r10
0x1400070a5  mov     r10d, [rsp+48h+arg_28]
0x1400070aa  mov     rax, [rax+18h]
0x1400070ae  mov     [rsp+48h+var_20], r10d
0x1400070b3  mov     [rsp+48h+var_28], r8
0x1400070b8  mov     r8, r11
0x1400070bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070c0  add     rsp, 48h
0x1400070c4  retn
0x1400070c5  mov     eax, 8007000Eh
0x1400070ca  jmp     short loc_1400070C0
```
