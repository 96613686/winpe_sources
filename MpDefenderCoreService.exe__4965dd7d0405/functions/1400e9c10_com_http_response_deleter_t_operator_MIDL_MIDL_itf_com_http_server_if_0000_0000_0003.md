# com::http::response_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0003 *)

- ea: `0x1400e9c10`
- end: `0x1400e9cbe`
- name: `??Rresponse_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0003@@@Z`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e9808`
- `0x1400ea340`

## callees

- `0x1400e9c10`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400e9c55`
- `ole32!CoTaskMemFree` at `0x1400e9c6e`
- `ole32!CoTaskMemFree` at `0x1400e9c7c`
- `ole32!CoTaskMemFree` at `0x1400e9c94`
- `ole32!CoTaskMemFree` at `0x1400e9c9d`
- `ole32!CoTaskMemFree` at `0x1400e9c55`
- `ole32!CoTaskMemFree` at `0x1400e9c6e`
- `ole32!CoTaskMemFree` at `0x1400e9c7c`
- `ole32!CoTaskMemFree` at `0x1400e9c94`
- `ole32!CoTaskMemFree` at `0x1400e9c9d`

## pseudocode

```c
void __fastcall com::http::response_deleter_t::operator()(__int64 a1, __int64 a2)
{
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 i; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rsi

  if ( a2 )
  {
    if ( *(_DWORD *)(a2 + 16) )
    {
      v3 = *(unsigned int *)(a2 + 16);
      v4 = a2 + 32;
      do
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)v4; i = (unsigned int)(i + 1) )
        {
          v6 = *(void **)(*(_QWORD *)(v4 + 8) + 8 * i);
          if ( v6 )
            CoTaskMemFree(v6);
        }
        v7 = *(void **)(v4 - 8);
        v8 = *(void **)(v4 + 8);
        if ( v7 )
          CoTaskMemFree(v7);
        if ( v8 )
          CoTaskMemFree(v8);
        v4 += 24;
        --v3;
      }
      while ( v3 );
    }
    if ( *(_QWORD *)a2 )
      CoTaskMemFree(*(LPVOID *)a2);
    CoTaskMemFree((LPVOID)a2);
  }
}

```

## disassembly

```asm
0x1400e9c10  test    rdx, rdx
0x1400e9c13  jz      locret_1400E9CBD
0x1400e9c19  mov     rax, rsp
0x1400e9c1c  mov     [rax+8], rbx
0x1400e9c20  mov     [rax+10h], rbp
0x1400e9c24  mov     [rax+18h], rsi
0x1400e9c28  mov     [rax+20h], rdi
0x1400e9c2c  push    r14
0x1400e9c2e  sub     rsp, 20h
0x1400e9c32  cmp     dword ptr [rdx+10h], 0
0x1400e9c36  mov     rbx, rdx
0x1400e9c39  jbe     short loc_1400E9C8C
0x1400e9c3b  mov     ebp, [rdx+10h]
0x1400e9c3e  lea     rdi, [rdx+20h]
0x1400e9c42  xor     esi, esi
0x1400e9c44  cmp     [rdi], esi
0x1400e9c46  jbe     short loc_1400E9C61
0x1400e9c48  mov     rax, [rdi+8]
0x1400e9c4c  mov     rcx, [rax+rsi*8]; pv
0x1400e9c50  test    rcx, rcx
0x1400e9c53  jz      short loc_1400E9C5B
0x1400e9c55  call    cs:__imp_CoTaskMemFree
0x1400e9c5b  inc     esi
0x1400e9c5d  cmp     esi, [rdi]
0x1400e9c5f  jb      short loc_1400E9C48
0x1400e9c61  mov     rcx, [rdi-8]; pv
0x1400e9c65  mov     rsi, [rdi+8]
0x1400e9c69  test    rcx, rcx
0x1400e9c6c  jz      short loc_1400E9C74
0x1400e9c6e  call    cs:__imp_CoTaskMemFree
0x1400e9c74  test    rsi, rsi
0x1400e9c77  jz      short loc_1400E9C82
0x1400e9c79  mov     rcx, rsi; pv
0x1400e9c7c  call    cs:__imp_CoTaskMemFree
0x1400e9c82  add     rdi, 18h
0x1400e9c86  sub     rbp, 1
0x1400e9c8a  jnz     short loc_1400E9C42
0x1400e9c8c  mov     rcx, [rbx]; pv
0x1400e9c8f  test    rcx, rcx
0x1400e9c92  jz      short loc_1400E9C9A
0x1400e9c94  call    cs:__imp_CoTaskMemFree
0x1400e9c9a  mov     rcx, rbx; pv
0x1400e9c9d  call    cs:__imp_CoTaskMemFree
0x1400e9ca3  mov     rbx, [rsp+28h+arg_0]
0x1400e9ca8  mov     rbp, [rsp+28h+arg_8]
0x1400e9cad  mov     rsi, [rsp+28h+arg_10]
0x1400e9cb2  mov     rdi, [rsp+28h+arg_18]
0x1400e9cb7  add     rsp, 20h
0x1400e9cbb  pop     r14
0x1400e9cbd  retn
```
