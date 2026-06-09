# CHXSmartScreen::__CssTemplateInfoActivationFactory::CreateFactory(uint *,__abi___classObjectEntry *,Platform::Guid &,__abi_IUnknown * *)

- ea: `0x1400060a0`
- end: `0x140006143`
- name: `?CreateFactory@__CssTemplateInfoActivationFactory@CHXSmartScreen@@SAJPEAIPEAU__abi___classObjectEntry@@AEAVGuid@Platform@@PEAPEAU__abi_IUnknown@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(unsigned int *, struct __abi___classObjectEntry *, struct Platform::Guid *, struct __abi_IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004bb8`
- `0x1400060a0`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1400060bd`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1400060bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHXSmartScreen::__CssTemplateInfoActivationFactory::CreateFactory(
        unsigned int *a1,
        struct __abi___classObjectEntry *a2,
        struct Platform::Guid *a3,
        struct __abi_IUnknown **a4)
{
  void *v6; // rax
  __int64 v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned int v9; // edi

  v6 = Platform::Details::Heap::Allocate(0x10u, 0x20u);
  v7 = CHXSmartScreen::__CssTemplateInfoActivationFactory::__CssTemplateInfoActivationFactory(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  if ( v8 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v8)[2])(v8);
  v9 = (*v8[1])(v8 + 1, a3, a4);
  if ( v8 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v8)[2])(v8);
  return v9;
}

```

## disassembly

```asm
0x1400060a0  mov     [rsp+arg_0], rbx
0x1400060a5  mov     [rsp+arg_8], rsi
0x1400060aa  push    rdi
0x1400060ab  sub     rsp, 30h
0x1400060af  mov     rdi, r9
0x1400060b2  mov     rsi, r8
0x1400060b5  mov     edx, 20h ; ' '
0x1400060ba  lea     ecx, [rdx-10h]
0x1400060bd  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1400060c3  mov     [rsp+38h+var_18], rax
0x1400060c8  mov     rcx, rax
0x1400060cb  call    ??0__CssTemplateInfoActivationFactory@CHXSmartScreen@@QE$AAA@XZ; CHXSmartScreen::__CssTemplateInfoActivationFactory::__CssTemplateInfoActivationFactory(void)
0x1400060d0  mov     rbx, rax
0x1400060d3  mov     [rsp+38h+var_18], rax
0x1400060d8  test    rax, rax
0x1400060db  jz      short loc_1400060EC
0x1400060dd  mov     rcx, [rax]
0x1400060e0  mov     rax, [rcx+8]
0x1400060e4  mov     rcx, rbx
0x1400060e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060ec  mov     [rsp+38h+var_18], rbx
0x1400060f1  test    rbx, rbx
0x1400060f4  jz      short loc_140006106
0x1400060f6  mov     rax, [rbx]
0x1400060f9  mov     rcx, rbx
0x1400060fc  mov     rax, [rax+10h]
0x140006100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006105  nop
0x140006106  lea     rcx, [rbx+8]
0x14000610a  mov     rax, [rcx]
0x14000610d  mov     r8, rdi
0x140006110  mov     rdx, rsi
0x140006113  mov     rax, [rax]
0x140006116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000611b  mov     edi, eax
0x14000611d  test    rbx, rbx
0x140006120  jz      short loc_140006131
0x140006122  mov     rcx, [rbx]
0x140006125  mov     rax, [rcx+10h]
0x140006129  mov     rcx, rbx
0x14000612c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006131  mov     eax, edi
0x140006133  mov     rbx, [rsp+38h+arg_0]
0x140006138  mov     rsi, [rsp+38h+arg_8]
0x14000613d  add     rsp, 30h
0x140006141  pop     rdi
0x140006142  retn
```
