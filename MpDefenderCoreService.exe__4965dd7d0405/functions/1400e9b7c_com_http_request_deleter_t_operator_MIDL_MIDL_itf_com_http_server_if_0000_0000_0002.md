# com::http::request_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002 *)

- ea: `0x1400e9b7c`
- end: `0x1400e9c0d`
- name: `??Rrequest_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002@@@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400eaa58`
- `0x1400f00e4`

## callees

- `0x1400e9b7c`
- `0x1400ea9b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400e9bbf`
- `ole32!CoTaskMemFree` at `0x1400e9bcd`
- `ole32!CoTaskMemFree` at `0x1400e9bdb`
- `ole32!CoTaskMemFree` at `0x1400e9be9`
- `ole32!CoTaskMemFree` at `0x1400e9bf2`
- `ole32!CoTaskMemFree` at `0x1400e9bbf`
- `ole32!CoTaskMemFree` at `0x1400e9bcd`
- `ole32!CoTaskMemFree` at `0x1400e9bdb`
- `ole32!CoTaskMemFree` at `0x1400e9be9`
- `ole32!CoTaskMemFree` at `0x1400e9bf2`

## pseudocode

```c
void __fastcall com::http::request_deleter_t::operator()(__int64 a1, __int64 a2, __int64 a3, bool a4)
{
  void *v5; // rbx
  void *v6; // rdi
  void *v7; // rbp

  if ( a2 )
  {
    com::http::free_headers(
      *(com::http **)(a2 + 40),
      (struct __MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *)*(unsigned int *)(a2 + 32),
      1u,
      a4);
    v5 = *(void **)(a2 + 56);
    v6 = *(void **)(a2 + 16);
    v7 = *(void **)(a2 + 8);
    if ( *(_QWORD *)a2 )
      CoTaskMemFree(*(LPVOID *)a2);
    if ( v7 )
      CoTaskMemFree(v7);
    if ( v6 )
      CoTaskMemFree(v6);
    if ( v5 )
      CoTaskMemFree(v5);
    CoTaskMemFree((LPVOID)a2);
  }
}

```

## disassembly

```asm
0x1400e9b7c  test    rdx, rdx
0x1400e9b7f  jz      locret_1400E9C0C
0x1400e9b85  mov     [rsp+arg_0], rbx
0x1400e9b8a  mov     [rsp+arg_10], rbp
0x1400e9b8f  mov     [rsp+arg_18], rsi
0x1400e9b94  push    rdi
0x1400e9b95  sub     rsp, 20h
0x1400e9b99  mov     rsi, rdx
0x1400e9b9c  mov     r8b, 1; unsigned int
0x1400e9b9f  mov     edx, [rdx+20h]; struct __MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *
0x1400e9ba2  mov     rcx, [rsi+28h]; this
0x1400e9ba6  call    ?free_headers@http@com@@YAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0001@@K_N@Z; com::http::free_headers(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *,ulong,bool)
0x1400e9bab  mov     rcx, [rsi]; pv
0x1400e9bae  mov     rbx, [rsi+38h]
0x1400e9bb2  mov     rdi, [rsi+10h]
0x1400e9bb6  mov     rbp, [rsi+8]
0x1400e9bba  test    rcx, rcx
0x1400e9bbd  jz      short loc_1400E9BC5
0x1400e9bbf  call    cs:__imp_CoTaskMemFree
0x1400e9bc5  test    rbp, rbp
0x1400e9bc8  jz      short loc_1400E9BD3
0x1400e9bca  mov     rcx, rbp; pv
0x1400e9bcd  call    cs:__imp_CoTaskMemFree
0x1400e9bd3  test    rdi, rdi
0x1400e9bd6  jz      short loc_1400E9BE1
0x1400e9bd8  mov     rcx, rdi; pv
0x1400e9bdb  call    cs:__imp_CoTaskMemFree
0x1400e9be1  test    rbx, rbx
0x1400e9be4  jz      short loc_1400E9BEF
0x1400e9be6  mov     rcx, rbx; pv
0x1400e9be9  call    cs:__imp_CoTaskMemFree
0x1400e9bef  mov     rcx, rsi; pv
0x1400e9bf2  call    cs:__imp_CoTaskMemFree
0x1400e9bf8  mov     rbx, [rsp+28h+arg_0]
0x1400e9bfd  mov     rbp, [rsp+28h+arg_10]
0x1400e9c02  mov     rsi, [rsp+28h+arg_18]
0x1400e9c07  add     rsp, 20h
0x1400e9c0b  pop     rdi
0x1400e9c0c  retn
```
