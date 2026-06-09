# Concurrency::create_async__lambda_012995b310defc0ef83a366488a71671___

- ea: `0x140013958`
- end: `0x1400139f0`
- name: `Concurrency::create_async__lambda_012995b310defc0ef83a366488a71671___`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400234e0`

## callees

- `0x140013958`
- `0x140014108`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013969`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013969`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Concurrency::create_async__lambda_012995b310defc0ef83a366488a71671___(__int64 a1)
{
  void *v2; // rax
  __int64 v3; // rax
  _QWORD *v4; // rbx
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h]

  v2 = Platform::Details::Heap::Allocate(0xB0u, 0xF8u);
  v3 = Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___(
         (__int64)v2,
         a1);
  v4 = (_QWORD *)v3;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  *(_QWORD *)(v4[16] + 152LL) = retaddr;
  (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return v4;
}

```

## disassembly

```asm
0x140013958  push    rbx
0x14001395a  sub     rsp, 20h
0x14001395e  mov     rbx, rcx
0x140013961  mov     edx, 0F8h
0x140013966  lea     ecx, [rdx-48h]
0x140013969  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14001396f  mov     [rsp+28h+arg_8], rax
0x140013974  mov     rdx, rbx
0x140013977  mov     rcx, rax
0x14001397a  call    Concurrency__details___AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671______AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___
0x14001397f  mov     rbx, rax
0x140013982  mov     [rsp+28h+arg_8], rax
0x140013987  test    rax, rax
0x14001398a  jz      short loc_14001399B
0x14001398c  mov     rcx, [rax]
0x14001398f  mov     rax, [rcx+8]
0x140013993  mov     rcx, rbx
0x140013996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001399b  mov     [rsp+28h+arg_8], rbx
0x1400139a0  test    rbx, rbx
0x1400139a3  jz      short loc_1400139B5
0x1400139a5  mov     rax, [rbx]
0x1400139a8  mov     rcx, rbx
0x1400139ab  mov     rax, [rax+10h]
0x1400139af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139b4  nop
0x1400139b5  mov     rcx, [rsp+28h]
0x1400139ba  mov     rax, [rbx+80h]
0x1400139c1  mov     [rax+98h], rcx
0x1400139c8  mov     rax, [rbx]
0x1400139cb  mov     rcx, rbx
0x1400139ce  mov     rax, [rax+8]
0x1400139d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139d7  nop
0x1400139d8  mov     rax, [rbx]
0x1400139db  mov     rcx, rbx
0x1400139de  mov     rax, [rax+10h]
0x1400139e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139e7  mov     rax, rbx
0x1400139ea  add     rsp, 20h
0x1400139ee  pop     rbx
0x1400139ef  retn
```
