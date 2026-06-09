# CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::Release(void)

- ea: `0x140006fb0`
- end: `0x140006ff0`
- name: `?Release@CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@EEAAKXZ`
- size: `64`
- prototype: `unsigned int __fastcall(CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140006fb0`
- `0x140007838`
- `0x140008f38`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::Release(
        CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::~CLifetimeExtension(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x140006fb0  mov     [rsp+arg_0], rbx
0x140006fb5  push    rdi
0x140006fb6  sub     rsp, 20h
0x140006fba  mov     rbx, rcx
0x140006fbd  or      edi, 0FFFFFFFFh
0x140006fc0  lock xadd [rcx+8], edi
0x140006fc5  sub     edi, 1
0x140006fc8  jz      short loc_140006FD7
0x140006fca  mov     rbx, [rsp+28h+arg_0]
0x140006fcf  mov     eax, edi
0x140006fd1  add     rsp, 20h
0x140006fd5  pop     rdi
0x140006fd6  retn
0x140006fd7  test    rbx, rbx
0x140006fda  jz      short loc_140006FCA
0x140006fdc  call    ??1CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@AEAA@XZ; CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::~CLifetimeExtension(void)
0x140006fe1  mov     edx, 18h
0x140006fe6  mov     rcx, rbx; pv
0x140006fe9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006fee  jmp     short loc_140006FCA
```
