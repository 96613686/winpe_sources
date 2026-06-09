# std::_Ref_count_resource<web::http::client::details::winhttp_request_context *,_lambda_499324dff2029233947519212c3cb421_>::_Get_deleter(type_info const &)

- ea: `0x180035a60`
- end: `0x180035a8c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVwinhttp_request_context@details@client@http@web@@V_lambda_499324dff2029233947519212c3cb421_@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180035a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180035a74`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180035a74`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<web::http::client::details::winhttp_request_context *,_lambda_499324dff2029233947519212c3cb421_>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_18008F258) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180035a60  push    rbx
0x180035a62  sub     rsp, 20h
0x180035a66  mov     rbx, rcx
0x180035a69  lea     rcx, [rdx+8]
0x180035a6d  lea     rdx, qword_18008F258
0x180035a74  call    cs:__imp___std_type_info_compare
0x180035a7a  test    eax, eax
0x180035a7c  jnz     short loc_180035A84
0x180035a7e  lea     rax, [rbx+10h]
0x180035a82  jmp     short loc_180035A86
0x180035a84  xor     eax, eax
0x180035a86  add     rsp, 20h
0x180035a8a  pop     rbx
0x180035a8b  retn
```
