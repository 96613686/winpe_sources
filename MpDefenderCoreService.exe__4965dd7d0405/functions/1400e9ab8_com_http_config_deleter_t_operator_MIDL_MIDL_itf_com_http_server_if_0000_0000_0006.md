# com::http::config_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006 *)

- ea: `0x1400e9ab8`
- end: `0x1400e9b79`
- name: `??Rconfig_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400ede6c`

## callees

- `0x1400e9ab8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400e9af1`
- `ole32!CoTaskMemFree` at `0x1400e9b1c`
- `ole32!CoTaskMemFree` at `0x1400e9b2a`
- `ole32!CoTaskMemFree` at `0x1400e9b33`
- `ole32!CoTaskMemFree` at `0x1400e9b41`
- `ole32!CoTaskMemFree` at `0x1400e9b4f`
- `ole32!CoTaskMemFree` at `0x1400e9b58`
- `ole32!CoTaskMemFree` at `0x1400e9af1`
- `ole32!CoTaskMemFree` at `0x1400e9b1c`
- `ole32!CoTaskMemFree` at `0x1400e9b2a`
- `ole32!CoTaskMemFree` at `0x1400e9b33`
- `ole32!CoTaskMemFree` at `0x1400e9b41`
- `ole32!CoTaskMemFree` at `0x1400e9b4f`
- `ole32!CoTaskMemFree` at `0x1400e9b58`

## pseudocode

```c
void __fastcall com::http::config_deleter_t::operator()(__int64 a1, __int64 a2)
{
  __int64 i; // rdi
  void *v4; // rcx
  _QWORD *v5; // rbp
  void *v6; // rbx
  void *v7; // rdi
  void *v8; // rcx
  void *v9; // r14

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 16); i = (unsigned int)(i + 1) )
    {
      v4 = *(void **)(*(_QWORD *)(a2 + 24) + 8 * i);
      if ( v4 )
        CoTaskMemFree(v4);
    }
    v5 = *(_QWORD **)(a2 + 8);
    v6 = *(void **)(a2 + 24);
    v7 = *(void **)(a2 + 40);
    if ( v5 )
    {
      v8 = (void *)v5[2];
      v9 = (void *)v5[1];
      if ( v8 )
        CoTaskMemFree(v8);
      if ( v9 )
        CoTaskMemFree(v9);
      CoTaskMemFree(v5);
    }
    if ( v7 )
      CoTaskMemFree(v7);
    if ( v6 )
      CoTaskMemFree(v6);
    CoTaskMemFree((LPVOID)a2);
  }
}

```

## disassembly

```asm
0x1400e9ab8  test    rdx, rdx
0x1400e9abb  jz      locret_1400E9B78
0x1400e9ac1  mov     rax, rsp
0x1400e9ac4  mov     [rax+8], rbx
0x1400e9ac8  mov     [rax+10h], rbp
0x1400e9acc  mov     [rax+18h], rsi
0x1400e9ad0  mov     [rax+20h], rdi
0x1400e9ad4  push    r14
0x1400e9ad6  sub     rsp, 20h
0x1400e9ada  xor     edi, edi
0x1400e9adc  mov     rsi, rdx
0x1400e9adf  cmp     [rdx+10h], edi
0x1400e9ae2  jbe     short loc_1400E9AFE
0x1400e9ae4  mov     rax, [rsi+18h]
0x1400e9ae8  mov     rcx, [rax+rdi*8]; pv
0x1400e9aec  test    rcx, rcx
0x1400e9aef  jz      short loc_1400E9AF7
0x1400e9af1  call    cs:__imp_CoTaskMemFree
0x1400e9af7  inc     edi
0x1400e9af9  cmp     edi, [rsi+10h]
0x1400e9afc  jb      short loc_1400E9AE4
0x1400e9afe  mov     rbp, [rsi+8]
0x1400e9b02  mov     rbx, [rsi+18h]
0x1400e9b06  mov     rdi, [rsi+28h]
0x1400e9b0a  test    rbp, rbp
0x1400e9b0d  jz      short loc_1400E9B39
0x1400e9b0f  mov     rcx, [rbp+10h]; pv
0x1400e9b13  mov     r14, [rbp+8]
0x1400e9b17  test    rcx, rcx
0x1400e9b1a  jz      short loc_1400E9B22
0x1400e9b1c  call    cs:__imp_CoTaskMemFree
0x1400e9b22  test    r14, r14
0x1400e9b25  jz      short loc_1400E9B30
0x1400e9b27  mov     rcx, r14; pv
0x1400e9b2a  call    cs:__imp_CoTaskMemFree
0x1400e9b30  mov     rcx, rbp; pv
0x1400e9b33  call    cs:__imp_CoTaskMemFree
0x1400e9b39  test    rdi, rdi
0x1400e9b3c  jz      short loc_1400E9B47
0x1400e9b3e  mov     rcx, rdi; pv
0x1400e9b41  call    cs:__imp_CoTaskMemFree
0x1400e9b47  test    rbx, rbx
0x1400e9b4a  jz      short loc_1400E9B55
0x1400e9b4c  mov     rcx, rbx; pv
0x1400e9b4f  call    cs:__imp_CoTaskMemFree
0x1400e9b55  mov     rcx, rsi; pv
0x1400e9b58  call    cs:__imp_CoTaskMemFree
0x1400e9b5e  mov     rbx, [rsp+28h+arg_0]
0x1400e9b63  mov     rbp, [rsp+28h+arg_8]
0x1400e9b68  mov     rsi, [rsp+28h+arg_10]
0x1400e9b6d  mov     rdi, [rsp+28h+arg_18]
0x1400e9b72  add     rsp, 20h
0x1400e9b76  pop     r14
0x1400e9b78  retn
```
