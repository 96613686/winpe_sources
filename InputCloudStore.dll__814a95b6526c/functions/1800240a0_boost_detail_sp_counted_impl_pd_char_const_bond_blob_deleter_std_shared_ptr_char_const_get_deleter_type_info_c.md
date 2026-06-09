# boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(type_info const &)

- ea: `0x1800240a0`
- end: `0x1800240cf`
- name: `?get_deleter@?$sp_counted_impl_pd@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800240b4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800240b4`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_1800401C8);
  v4 = a1 + 24;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800240a0  push    rbx
0x1800240a2  sub     rsp, 20h
0x1800240a6  mov     rbx, rcx
0x1800240a9  lea     rcx, [rdx+8]
0x1800240ad  lea     rdx, qword_1800401C8
0x1800240b4  call    cs:__imp___std_type_info_compare
0x1800240ba  xor     ecx, ecx
0x1800240bc  lea     rdx, [rbx+18h]
0x1800240c0  test    eax, eax
0x1800240c2  cmovnz  rdx, rcx
0x1800240c6  mov     rax, rdx
0x1800240c9  add     rsp, 20h
0x1800240cd  pop     rbx
0x1800240ce  retn
```
