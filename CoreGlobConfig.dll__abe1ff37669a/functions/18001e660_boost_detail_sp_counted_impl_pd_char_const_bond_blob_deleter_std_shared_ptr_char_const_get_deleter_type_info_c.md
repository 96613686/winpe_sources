# boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(type_info const &)

- ea: `0x18001e660`
- end: `0x18001e68f`
- name: `?get_deleter@?$sp_counted_impl_pd@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001e674`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001e674`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180032358);
  v4 = a1 + 24;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18001e660  push    rbx
0x18001e662  sub     rsp, 20h
0x18001e666  mov     rbx, rcx
0x18001e669  lea     rcx, [rdx+8]
0x18001e66d  lea     rdx, qword_180032358
0x18001e674  call    cs:__imp___std_type_info_compare
0x18001e67a  xor     ecx, ecx
0x18001e67c  lea     rdx, [rbx+18h]
0x18001e680  test    eax, eax
0x18001e682  cmovnz  rdx, rcx
0x18001e686  mov     rax, rdx
0x18001e689  add     rsp, 20h
0x18001e68d  pop     rbx
0x18001e68e  retn
```
