# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)

- ea: `0x140008920`
- end: `0x140008936`
- name: `??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400055d4`
- `0x140005694`
- `0x140005728`
- `0x1400057bc`
- `0x140005850`
- `0x1400058e8`
- `0x1400059c8`
- `0x140005a78`
- `0x140005b28`
- `0x140005c08`
- `0x140005d0c`
- `0x140005dd4`
- `0x140005f10`

## callees

- `0x1400032f0`
- `0x140008920`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140008920  sub     rsp, 28h
0x140008924  mov     rcx, [rcx]; Block
0x140008927  test    rcx, rcx
0x14000892a  jz      short loc_140008931
0x14000892c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008931  add     rsp, 28h
0x140008935  retn
```
