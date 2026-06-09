# Comms::SerializeObject(Comms::SerializeBase &,utl::vector<uchar,utl::allocator<uchar>> const &)

- ea: `0x180002ba0`
- end: `0x180002c05`
- name: `?SerializeObject@Comms@@YAXAEAVSerializeBase@1@AEBV?$vector@EV?$allocator@E@utl@@@utl@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Comms::SerializeObject(__int64 a1, _QWORD *a2)
{
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = a2[1] - *a2;
  (*(void (__fastcall **)(__int64, __int64 *, __int64, unsigned __int64 *))(*(_QWORD *)a1 + 8LL))(
    a1,
    &v5,
    8,
    &unsigned __int64 `RTTI Type Descriptor');
  return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void ***))(*(_QWORD *)a1 + 8LL))(
           a1,
           *a2,
           a2[1] - *a2,
           &utl::vector<unsigned char,utl::allocator<unsigned char>> `RTTI Type Descriptor');
}

```

## disassembly

```asm
0x180002ba0  mov     [rsp+arg_8], rbx
0x180002ba5  push    rdi
0x180002ba6  sub     rsp, 30h
0x180002baa  mov     rax, [rdx+8]
0x180002bae  lea     r9, ??_R0_K@8; unsigned __int64 `RTTI Type Descriptor'
0x180002bb5  sub     rax, [rdx]
0x180002bb8  mov     rbx, rdx
0x180002bbb  mov     [rsp+38h+arg_0], rax
0x180002bc0  lea     rdx, [rsp+38h+arg_0]
0x180002bc5  mov     rax, [rcx]
0x180002bc8  mov     r8d, 8
0x180002bce  mov     rdi, rcx
0x180002bd1  mov     rax, [rax+8]
0x180002bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bda  mov     rax, [rdi]
0x180002bdd  lea     r9, ??_R0?AV?$vector@EV?$allocator@E@utl@@@utl@@@8; utl::vector<uchar,utl::allocator<uchar>> `RTTI Type Descriptor'
0x180002be4  mov     r8, [rbx+8]
0x180002be8  mov     rcx, rdi
0x180002beb  sub     r8, [rbx]
0x180002bee  mov     rdx, [rbx]
0x180002bf1  mov     rax, [rax+8]
0x180002bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bfa  mov     rbx, [rsp+38h+arg_8]
0x180002bff  add     rsp, 30h
0x180002c03  pop     rdi
0x180002c04  retn
```
