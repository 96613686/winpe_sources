# CRuntimeBrokerLifetimeExtensionFactory::UnmarshalInterface(IStream *,_GUID const &,void * *)

- ea: `0x14000ca10`
- end: `0x14000ca35`
- name: `?UnmarshalInterface@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `37`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, struct IStream *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000ca10`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::UnmarshalInterface(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, struct IStream *, const struct _GUID *, void **))(*(_QWORD *)v4 + 48LL))(
             v4,
             a2,
             a3,
             a4);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x14000ca10  sub     rsp, 38h
0x14000ca14  mov     rcx, [rcx+10h]
0x14000ca18  test    rcx, rcx
0x14000ca1b  jz      short loc_14000CA2B
0x14000ca1d  mov     rax, [rcx]
0x14000ca20  mov     rax, [rax+30h]
0x14000ca24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca29  jmp     short loc_14000CA30
0x14000ca2b  mov     eax, 8007000Eh
0x14000ca30  add     rsp, 38h
0x14000ca34  retn
```
