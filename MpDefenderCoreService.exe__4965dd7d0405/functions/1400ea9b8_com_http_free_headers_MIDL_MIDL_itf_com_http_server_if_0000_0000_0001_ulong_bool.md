# com::http::free_headers(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *,ulong,bool)

- ea: `0x1400ea9b8`
- end: `0x1400eaa56`
- name: `?free_headers@http@com@@YAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0001@@K_N@Z`
- size: `158`
- prototype: `void __fastcall(com::http *__hidden this, struct __MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e9b7c`

## callees

- `0x1400ea9b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400ea9f3`
- `ole32!CoTaskMemFree` at `0x1400eaa0c`
- `ole32!CoTaskMemFree` at `0x1400eaa1a`
- `ole32!CoTaskMemFree` at `0x1400eaa37`
- `ole32!CoTaskMemFree` at `0x1400ea9f3`
- `ole32!CoTaskMemFree` at `0x1400eaa0c`
- `ole32!CoTaskMemFree` at `0x1400eaa1a`
- `ole32!CoTaskMemFree` at `0x1400eaa37`

## pseudocode

```c
void __fastcall com::http::free_headers(
        com::http *this,
        struct __MIDL___MIDL_itf_com_http_server_if_0000_0000_0001 *a2,
        char a3)
{
  char *v5; // rbx
  __int64 v6; // rbp
  __int64 i; // rsi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rsi

  if ( (_DWORD)a2 )
  {
    v5 = (char *)this + 8;
    v6 = (unsigned int)a2;
    do
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)v5; i = (unsigned int)(i + 1) )
      {
        v8 = *(void **)(*((_QWORD *)v5 + 1) + 8 * i);
        if ( v8 )
          CoTaskMemFree(v8);
      }
      v9 = (void *)*((_QWORD *)v5 - 1);
      v10 = (void *)*((_QWORD *)v5 + 1);
      if ( v9 )
        CoTaskMemFree(v9);
      if ( v10 )
        CoTaskMemFree(v10);
      v5 += 24;
      --v6;
    }
    while ( v6 );
  }
  if ( a3 )
  {
    if ( this )
      CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x1400ea9b8  mov     [rsp+arg_0], rbx
0x1400ea9bd  mov     [rsp+arg_8], rbp
0x1400ea9c2  mov     [rsp+arg_10], rsi
0x1400ea9c7  push    rdi
0x1400ea9c8  push    r14
0x1400ea9ca  push    r15
0x1400ea9cc  sub     rsp, 20h
0x1400ea9d0  mov     r15b, r8b
0x1400ea9d3  mov     rdi, rcx
0x1400ea9d6  test    edx, edx
0x1400ea9d8  jz      short loc_1400EAA2A
0x1400ea9da  lea     rbx, [rcx+8]
0x1400ea9de  mov     ebp, edx
0x1400ea9e0  xor     esi, esi
0x1400ea9e2  cmp     [rbx], esi
0x1400ea9e4  jbe     short loc_1400EA9FF
0x1400ea9e6  mov     rax, [rbx+8]
0x1400ea9ea  mov     rcx, [rax+rsi*8]; pv
0x1400ea9ee  test    rcx, rcx
0x1400ea9f1  jz      short loc_1400EA9F9
0x1400ea9f3  call    cs:__imp_CoTaskMemFree
0x1400ea9f9  inc     esi
0x1400ea9fb  cmp     esi, [rbx]
0x1400ea9fd  jb      short loc_1400EA9E6
0x1400ea9ff  mov     rcx, [rbx-8]; pv
0x1400eaa03  mov     rsi, [rbx+8]
0x1400eaa07  test    rcx, rcx
0x1400eaa0a  jz      short loc_1400EAA12
0x1400eaa0c  call    cs:__imp_CoTaskMemFree
0x1400eaa12  test    rsi, rsi
0x1400eaa15  jz      short loc_1400EAA20
0x1400eaa17  mov     rcx, rsi; pv
0x1400eaa1a  call    cs:__imp_CoTaskMemFree
0x1400eaa20  add     rbx, 18h
0x1400eaa24  sub     rbp, 1
0x1400eaa28  jnz     short loc_1400EA9E0
0x1400eaa2a  test    r15b, r15b
0x1400eaa2d  jz      short loc_1400EAA3D
0x1400eaa2f  test    rdi, rdi
0x1400eaa32  jz      short loc_1400EAA3D
0x1400eaa34  mov     rcx, rdi; pv
0x1400eaa37  call    cs:__imp_CoTaskMemFree
0x1400eaa3d  mov     rbx, [rsp+38h+arg_0]
0x1400eaa42  mov     rbp, [rsp+38h+arg_8]
0x1400eaa47  mov     rsi, [rsp+38h+arg_10]
0x1400eaa4c  add     rsp, 20h
0x1400eaa50  pop     r15
0x1400eaa52  pop     r14
0x1400eaa54  pop     rdi
0x1400eaa55  retn
```
