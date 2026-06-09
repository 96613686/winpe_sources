# boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_local_deleter(type_info const &)

- ea: `0x18001e6a0`
- end: `0x18001e6bc`
- name: `?get_local_deleter@?$sp_counted_impl_pd@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001e6af`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001e6af`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_local_deleter(
        __int64 a1,
        __int64 a2)
{
  __std_type_info_compare(a2 + 8, &qword_180032358);
  return 0;
}

```

## disassembly

```asm
0x18001e6a0  sub     rsp, 28h
0x18001e6a4  lea     rcx, [rdx+8]
0x18001e6a8  lea     rdx, qword_180032358
0x18001e6af  call    cs:__imp___std_type_info_compare
0x18001e6b5  xor     eax, eax
0x18001e6b7  add     rsp, 28h
0x18001e6bb  retn
```
