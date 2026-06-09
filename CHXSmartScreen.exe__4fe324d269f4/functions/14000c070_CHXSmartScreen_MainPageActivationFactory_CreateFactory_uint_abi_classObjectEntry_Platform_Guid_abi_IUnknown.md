# CHXSmartScreen::__MainPageActivationFactory::CreateFactory(uint *,__abi___classObjectEntry *,Platform::Guid &,__abi_IUnknown * *)

- ea: `0x14000c070`
- end: `0x14000c113`
- name: `?CreateFactory@__MainPageActivationFactory@CHXSmartScreen@@SAJPEAIPEAU__abi___classObjectEntry@@AEAVGuid@Platform@@PEAPEAU__abi_IUnknown@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(unsigned int *, struct __abi___classObjectEntry *, struct Platform::Guid *, struct __abi_IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000b898`
- `0x14000c070`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000c08d`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000c08d`

## pseudocode

```c
__int64 __fastcall CHXSmartScreen::__MainPageActivationFactory::CreateFactory(
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
  v7 = CHXSmartScreen::__MainPageActivationFactory::__MainPageActivationFactory(v6);
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
0x14000c070  mov     [rsp+arg_0], rbx
0x14000c075  mov     [rsp+arg_8], rsi
0x14000c07a  push    rdi
0x14000c07b  sub     rsp, 30h
0x14000c07f  mov     rdi, r9
0x14000c082  mov     rsi, r8
0x14000c085  mov     edx, 20h ; ' '
0x14000c08a  lea     ecx, [rdx-10h]
0x14000c08d  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14000c093  mov     [rsp+38h+var_18], rax
0x14000c098  mov     rcx, rax
0x14000c09b  call    ??0__MainPageActivationFactory@CHXSmartScreen@@QE$AAA@XZ; CHXSmartScreen::__MainPageActivationFactory::__MainPageActivationFactory(void)
0x14000c0a0  mov     rbx, rax
0x14000c0a3  mov     [rsp+38h+var_18], rax
0x14000c0a8  test    rax, rax
0x14000c0ab  jz      short loc_14000C0BC
0x14000c0ad  mov     rcx, [rax]
0x14000c0b0  mov     rax, [rcx+8]
0x14000c0b4  mov     rcx, rbx
0x14000c0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0bc  mov     [rsp+38h+var_18], rbx
0x14000c0c1  test    rbx, rbx
0x14000c0c4  jz      short loc_14000C0D6
0x14000c0c6  mov     rax, [rbx]
0x14000c0c9  mov     rcx, rbx
0x14000c0cc  mov     rax, [rax+10h]
0x14000c0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0d5  nop
0x14000c0d6  lea     rcx, [rbx+8]
0x14000c0da  mov     rax, [rcx]
0x14000c0dd  mov     r8, rdi
0x14000c0e0  mov     rdx, rsi
0x14000c0e3  mov     rax, [rax]
0x14000c0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0eb  mov     edi, eax
0x14000c0ed  test    rbx, rbx
0x14000c0f0  jz      short loc_14000C101
0x14000c0f2  mov     rcx, [rbx]
0x14000c0f5  mov     rax, [rcx+10h]
0x14000c0f9  mov     rcx, rbx
0x14000c0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c101  mov     eax, edi
0x14000c103  mov     rbx, [rsp+38h+arg_0]
0x14000c108  mov     rsi, [rsp+38h+arg_8]
0x14000c10d  add     rsp, 30h
0x14000c111  pop     rdi
0x14000c112  retn
```
