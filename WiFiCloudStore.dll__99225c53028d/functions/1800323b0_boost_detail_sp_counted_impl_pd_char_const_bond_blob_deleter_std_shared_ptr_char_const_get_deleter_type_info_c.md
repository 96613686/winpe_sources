# boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(type_info const &)

- ea: `0x1800323b0`
- end: `0x1800323df`
- name: `?get_deleter@?$sp_counted_impl_pd@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@detail@boost@@UEAAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800323c4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800323c4`

## pseudocode

```c
__int64 __fastcall boost::detail::sp_counted_impl_pd<char const *,bond::blob::deleter<std::shared_ptr<char const>>>::get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180052278);
  v4 = a1 + 24;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800323b0  push    rbx
0x1800323b2  sub     rsp, 20h
0x1800323b6  mov     rbx, rcx
0x1800323b9  lea     rcx, [rdx+8]
0x1800323bd  lea     rdx, qword_180052278
0x1800323c4  call    cs:__imp___std_type_info_compare
0x1800323ca  xor     ecx, ecx
0x1800323cc  lea     rdx, [rbx+18h]
0x1800323d0  test    eax, eax
0x1800323d2  cmovnz  rdx, rcx
0x1800323d6  mov     rax, rdx
0x1800323d9  add     rsp, 20h
0x1800323dd  pop     rbx
0x1800323de  retn
```
