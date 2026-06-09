# CRuntimeBrokerLifetimeExtensionFactory::DisconnectObject(ulong)

- ea: `0x1400075f0`
- end: `0x14000760b`
- name: `?DisconnectObject@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJK@Z`
- size: `27`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400075f0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::DisconnectObject(
        CRuntimeBrokerLifetimeExtensionFactory *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 64LL))(v1);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x1400075f0  mov     rcx, [rcx+10h]
0x1400075f4  test    rcx, rcx
0x1400075f7  jz      short loc_140007605
0x1400075f9  mov     rax, [rcx]
0x1400075fc  mov     rax, [rax+40h]
0x140007600  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140007605  mov     eax, 8007000Eh
0x14000760a  retn
```
