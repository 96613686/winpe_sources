# Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>::operator IUnknown * *(void)

- ea: `0x18000cd68`
- end: `0x18000cd83`
- name: `??B?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAPEAUIUnknown@@XZ`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c464`

## callees

- `0x1800108d4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>::operator IUnknown * *(
        _QWORD *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::ReleaseAndGetAddressOf(*a1);
}

```

## disassembly

```asm
0x18000cd68  mov     [rsp+arg_0], rcx
0x18000cd6d  sub     rsp, 28h
0x18000cd71  mov     rax, [rsp+28h+arg_0]
0x18000cd76  mov     rcx, [rax]
0x18000cd79  call    ?ReleaseAndGetAddressOf@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAPEAPEAUIUnknown@@XZ
0x18000cd7e  add     rsp, 28h
0x18000cd82  retn
```
