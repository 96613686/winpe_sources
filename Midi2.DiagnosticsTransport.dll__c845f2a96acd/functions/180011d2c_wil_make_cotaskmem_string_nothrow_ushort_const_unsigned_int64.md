# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x180011d2c`
- end: `0x180011dda`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `174`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800119a0`
- `0x180011b5c`

## callees

- `0x1800040f6`
- `0x180004158`
- `0x180004170`
- `0x180011cf4`
- `0x180011d2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011da6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d74`

## pseudocode

```c
wil *__fastcall wil::make_cotaskmem_string_nothrow(
        wil *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const char *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, a3, a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = 2 * (v7 - a2);
  v9 = v8 + 2;
  v10 = (char *)CoTaskMemAlloc(v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *(_QWORD *)this = v11;
  return this;
}

```

## disassembly

```asm
0x180011d2c  push    rbx
0x180011d2e  push    rbp
0x180011d2f  push    rsi
0x180011d30  push    rdi
0x180011d31  push    r14
0x180011d33  push    r15
0x180011d35  sub     rsp, 28h
0x180011d39  xor     r15d, r15d
0x180011d3c  mov     rsi, rdx
0x180011d3f  mov     r14, rcx
0x180011d42  test    rdx, rdx
0x180011d45  jz      loc_180011DCF
0x180011d4b  mov     ecx, 7FFFFFFFh
0x180011d50  mov     rax, rdx
0x180011d53  cmp     [rax], r15w
0x180011d57  jz      short loc_180011D63
0x180011d59  add     rax, 2
0x180011d5d  sub     rcx, 1
0x180011d61  jnz     short loc_180011D53
0x180011d63  sub     rax, rsi
0x180011d66  sar     rax, 1
0x180011d69  lea     rbx, [rax+rax]
0x180011d6d  lea     rbp, [rbx+2]
0x180011d71  mov     rcx, rbp; cb
0x180011d74  call    cs:__imp_CoTaskMemAlloc
0x180011d7a  mov     rdi, rax
0x180011d7d  test    rax, rax
0x180011d80  jz      short loc_180011DBC
0x180011d82  test    rbx, rbx
0x180011d85  jz      short loc_180011DB7
0x180011d87  mov     rcx, rax; void *
0x180011d8a  cmp     rbp, rbx
0x180011d8d  jb      short loc_180011D9C
0x180011d8f  mov     r8, rbx; Size
0x180011d92  mov     rdx, rsi; Src
0x180011d95  call    memcpy_0
0x180011d9a  jmp     short loc_180011DB7
0x180011d9c  mov     r8, rbp; Size
0x180011d9f  xor     edx, edx; Val
0x180011da1  call    memset_0
0x180011da6  call    cs:__imp__o__errno
0x180011dac  mov     dword ptr [rax], 22h ; '"'
0x180011db2  call    _invalid_parameter_noinfo
0x180011db7  mov     [rbx+rdi], r15w
0x180011dbc  mov     [r14], rdi
0x180011dbf  mov     rax, r14
0x180011dc2  add     rsp, 28h
0x180011dc6  pop     r15
0x180011dc8  pop     r14
0x180011dca  pop     rdi
0x180011dcb  pop     rsi
0x180011dcc  pop     rbp
0x180011dcd  pop     rbx
0x180011dce  retn
0x180011dcf  mov     rcx, [rsp+58h]; this
0x180011dd4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
