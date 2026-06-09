# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(void)

- ea: `0x180003b84`
- end: `0x180003b9f`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800032fc`
- `0x180006db8`
- `0x180007418`

## callees

- `0x180003c7c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(a1 + 8));
  return a1;
}

```

## disassembly

```asm
0x180003b84  push    rbx
0x180003b86  sub     rsp, 20h
0x180003b8a  mov     rbx, rcx
0x180003b8d  add     rcx, 8; this
0x180003b91  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180003b96  mov     rax, rbx
0x180003b99  add     rsp, 20h
0x180003b9d  pop     rbx
0x180003b9e  retn
```
