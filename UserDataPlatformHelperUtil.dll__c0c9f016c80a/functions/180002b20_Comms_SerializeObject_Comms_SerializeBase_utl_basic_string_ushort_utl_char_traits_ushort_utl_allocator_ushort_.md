# Comms::SerializeObject(Comms::SerializeBase &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)

- ea: `0x180002b20`
- end: `0x180002b8e`
- name: `?SerializeObject@Comms@@YAXAEAVSerializeBase@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `110`
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

  v5 = (__int64)(a2[1] - *a2) >> 1;
  (*(void (__fastcall **)(__int64, __int64 *, __int64, unsigned __int64 *))(*(_QWORD *)a1 + 8LL))(
    a1,
    &v5,
    8,
    &unsigned __int64 `RTTI Type Descriptor');
  return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, void ***))(*(_QWORD *)a1 + 8LL))(
           a1,
           *a2,
           2 * ((__int64)(a2[1] - *a2) >> 1),
           &utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> `RTTI Type Descriptor');
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_8], rbx
0x180002b25  push    rdi
0x180002b26  sub     rsp, 30h
0x180002b2a  mov     rax, [rdx+8]
0x180002b2e  lea     r9, ??_R0_K@8; unsigned __int64 `RTTI Type Descriptor'
0x180002b35  sub     rax, [rdx]
0x180002b38  mov     rbx, rdx
0x180002b3b  sar     rax, 1
0x180002b3e  lea     rdx, [rsp+38h+arg_0]
0x180002b43  mov     [rsp+38h+arg_0], rax
0x180002b48  mov     r8d, 8
0x180002b4e  mov     rax, [rcx]
0x180002b51  mov     rdi, rcx
0x180002b54  mov     rax, [rax+8]
0x180002b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5d  mov     r8, [rbx+8]
0x180002b61  lea     r9, ??_R0?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@8; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> `RTTI Type Descriptor'
0x180002b68  sub     r8, [rbx]
0x180002b6b  mov     rcx, rdi
0x180002b6e  mov     rax, [rdi]
0x180002b71  mov     rdx, [rbx]
0x180002b74  sar     r8, 1
0x180002b77  add     r8, r8
0x180002b7a  mov     rax, [rax+8]
0x180002b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b83  mov     rbx, [rsp+38h+arg_8]
0x180002b88  add     rsp, 30h
0x180002b8c  pop     rdi
0x180002b8d  retn
```
