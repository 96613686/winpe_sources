# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::~ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>(void)

- ea: `0x18000c870`
- end: `0x18000c889`
- name: `??1?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d950`

## callees

- `0x18000ee90`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::~ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>(
        __int64 *a1)
{
  return Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18000c870  mov     [rsp+arg_0], rcx
0x18000c875  sub     rsp, 28h
0x18000c879  mov     rcx, [rsp+28h+arg_0]
0x18000c87e  call    ?InternalRelease@?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::InternalRelease(void)
0x18000c883  nop
0x18000c884  add     rsp, 28h
0x18000c888  retn
```
