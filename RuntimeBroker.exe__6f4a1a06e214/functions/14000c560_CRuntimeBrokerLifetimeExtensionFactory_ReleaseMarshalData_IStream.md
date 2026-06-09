# CRuntimeBrokerLifetimeExtensionFactory::ReleaseMarshalData(IStream *)

- ea: `0x14000c560`
- end: `0x14000c57b`
- name: `?ReleaseMarshalData@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJPEAUIStream@@@Z`
- size: `27`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c560`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::ReleaseMarshalData(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        struct IStream *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v2 + 56LL))(v2, a2);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x14000c560  mov     rcx, [rcx+10h]
0x14000c564  test    rcx, rcx
0x14000c567  jz      short loc_14000C575
0x14000c569  mov     rax, [rcx]
0x14000c56c  mov     rax, [rax+38h]
0x14000c570  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14000c575  mov     eax, 8007000Eh
0x14000c57a  retn
```
