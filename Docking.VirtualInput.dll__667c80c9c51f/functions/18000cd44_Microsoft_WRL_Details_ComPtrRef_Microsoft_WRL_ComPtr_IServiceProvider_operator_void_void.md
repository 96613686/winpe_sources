# Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)

- ea: `0x18000cd44`
- end: `0x18000cd5f`
- name: `??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ`
- size: `27`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b3d4`
- `0x18000bca8`
- `0x180013bd0`
- `0x1800146a8`
- `0x180014718`
- `0x180014df0`

## callees

- `0x1800108b0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(
        _QWORD *a1)
{
  return Microsoft::WRL::ComPtr<IMarshal>::ReleaseAndGetAddressOf(*a1);
}

```

## disassembly

```asm
0x18000cd44  mov     [rsp+arg_0], rcx
0x18000cd49  sub     rsp, 28h
0x18000cd4d  mov     rax, [rsp+28h+arg_0]
0x18000cd52  mov     rcx, [rax]
0x18000cd55  call    ?ReleaseAndGetAddressOf@?$ComPtr@UIMarshal@@@WRL@Microsoft@@QEAAPEAPEAUIMarshal@@XZ
0x18000cd5a  add     rsp, 28h
0x18000cd5e  retn
```
