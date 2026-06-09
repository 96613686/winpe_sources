# CRuntimeBrokerLifetimeExtensionFactory::Release(void)

- ea: `0x1400068a0`
- end: `0x1400068e0`
- name: `?Release@CRuntimeBrokerLifetimeExtensionFactory@@UEAAKXZ`
- size: `64`
- prototype: `unsigned int __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140005770`
- `0x140007838`
- `0x14000c550`

## callees

- `0x1400068a0`
- `0x1400068e8`
- `0x140008f38`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::Release(CRuntimeBrokerLifetimeExtensionFactory *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 3);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1400068a0  mov     [rsp+arg_0], rbx
0x1400068a5  push    rdi
0x1400068a6  sub     rsp, 20h
0x1400068aa  mov     rbx, rcx
0x1400068ad  or      edi, 0FFFFFFFFh
0x1400068b0  lock xadd [rcx+10h], edi
0x1400068b5  sub     edi, 1
0x1400068b8  jnz     short loc_1400068D3
0x1400068ba  test    rcx, rcx
0x1400068bd  jz      short loc_1400068D3
0x1400068bf  add     rcx, 18h
0x1400068c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400068c8  lea     edx, [rdi+20h]
0x1400068cb  mov     rcx, rbx; pv
0x1400068ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400068d3  mov     rbx, [rsp+28h+arg_0]
0x1400068d8  mov     eax, edi
0x1400068da  add     rsp, 20h
0x1400068de  pop     rdi
0x1400068df  retn
```
