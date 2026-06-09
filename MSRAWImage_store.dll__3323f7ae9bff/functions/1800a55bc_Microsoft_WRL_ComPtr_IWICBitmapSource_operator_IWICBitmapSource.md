# Microsoft::WRL::ComPtr<IWICBitmapSource>::operator=(IWICBitmapSource *)

- ea: `0x1800a55bc`
- end: `0x1800a5604`
- name: `??4?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICBitmapSource@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a7b28`

## callees

- `0x18009c41c`
- `0x18009c44c`
- `0x1800a55bc`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<IWICBitmapSource>::operator=(__int64 *a1, __int64 a2)
{
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 != a2 )
  {
    v5 = a2;
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(&v5);
    v5 = *a1;
    *a1 = a2;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1800a55bc  mov     [rsp+arg_8], rbx
0x1800a55c1  push    rdi
0x1800a55c2  sub     rsp, 20h
0x1800a55c6  mov     rdi, rdx
0x1800a55c9  mov     rbx, rcx
0x1800a55cc  cmp     [rcx], rdx
0x1800a55cf  jz      short loc_1800A55F5
0x1800a55d1  lea     rcx, [rsp+28h+arg_0]
0x1800a55d6  mov     [rsp+28h+arg_0], rdx
0x1800a55db  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800a55e0  mov     rax, [rbx]
0x1800a55e3  lea     rcx, [rsp+28h+arg_0]
0x1800a55e8  mov     [rsp+28h+arg_0], rax
0x1800a55ed  mov     [rbx], rdi
0x1800a55f0  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a55f5  mov     rax, rbx
0x1800a55f8  mov     rbx, [rsp+28h+arg_8]
0x1800a55fd  add     rsp, 20h
0x1800a5601  pop     rdi
0x1800a5602  retn
```
