# Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)

- ea: `0x1800a555c`
- end: `0x1800a55b4`
- name: `??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a42c0`
- `0x1800ad600`

## callees

- `0x18009c44c`
- `0x1800a555c`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::ComPtr<IStream>::operator=(__int64 *a1, __int64 a2)
{
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *a1;
    *a1 = a2;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1800a555c  push    rdi
0x1800a555e  sub     rsp, 30h
0x1800a5562  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a556b  mov     [rsp+38h+arg_8], rbx
0x1800a5570  mov     rbx, rdx
0x1800a5573  mov     rdi, rcx
0x1800a5576  cmp     [rcx], rdx
0x1800a5579  jz      short loc_1800A55A5
0x1800a557b  test    rdx, rdx
0x1800a557e  jz      short loc_1800A5590
0x1800a5580  mov     rax, [rdx]
0x1800a5583  mov     rcx, rdx
0x1800a5586  mov     rax, [rax+8]
0x1800a558a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a558f  nop
0x1800a5590  mov     rax, [rdi]
0x1800a5593  mov     [rsp+38h+arg_0], rax
0x1800a5598  mov     [rdi], rbx
0x1800a559b  lea     rcx, [rsp+38h+arg_0]
0x1800a55a0  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a55a5  mov     rax, rdi
0x1800a55a8  mov     rbx, [rsp+38h+arg_8]
0x1800a55ad  add     rsp, 30h
0x1800a55b1  pop     rdi
0x1800a55b2  retn
```
