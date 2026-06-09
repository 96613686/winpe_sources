# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x180024cf4`
- end: `0x180024da2`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `174`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800227c4`
- `0x180025250`
- `0x18002540c`
- `0x180028020`
- `0x180028300`

## callees

- `0x1800051e6`
- `0x180005254`
- `0x18000526c`
- `0x180024954`
- `0x180024cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024d6e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d3c`

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
0x180024cf4  push    rbx
0x180024cf6  push    rbp
0x180024cf7  push    rsi
0x180024cf8  push    rdi
0x180024cf9  push    r14
0x180024cfb  push    r15
0x180024cfd  sub     rsp, 28h
0x180024d01  xor     r15d, r15d
0x180024d04  mov     rsi, rdx
0x180024d07  mov     r14, rcx
0x180024d0a  test    rdx, rdx
0x180024d0d  jz      loc_180024D97
0x180024d13  mov     ecx, 7FFFFFFFh
0x180024d18  mov     rax, rdx
0x180024d1b  cmp     [rax], r15w
0x180024d1f  jz      short loc_180024D2B
0x180024d21  add     rax, 2
0x180024d25  sub     rcx, 1
0x180024d29  jnz     short loc_180024D1B
0x180024d2b  sub     rax, rsi
0x180024d2e  sar     rax, 1
0x180024d31  lea     rbx, [rax+rax]
0x180024d35  lea     rbp, [rbx+2]
0x180024d39  mov     rcx, rbp; cb
0x180024d3c  call    cs:__imp_CoTaskMemAlloc
0x180024d42  mov     rdi, rax
0x180024d45  test    rax, rax
0x180024d48  jz      short loc_180024D84
0x180024d4a  test    rbx, rbx
0x180024d4d  jz      short loc_180024D7F
0x180024d4f  mov     rcx, rax; void *
0x180024d52  cmp     rbp, rbx
0x180024d55  jb      short loc_180024D64
0x180024d57  mov     r8, rbx; Size
0x180024d5a  mov     rdx, rsi; Src
0x180024d5d  call    memcpy_0
0x180024d62  jmp     short loc_180024D7F
0x180024d64  mov     r8, rbp; Size
0x180024d67  xor     edx, edx; Val
0x180024d69  call    memset_0
0x180024d6e  call    cs:__imp__o__errno
0x180024d74  mov     dword ptr [rax], 22h ; '"'
0x180024d7a  call    _invalid_parameter_noinfo
0x180024d7f  mov     [rbx+rdi], r15w
0x180024d84  mov     [r14], rdi
0x180024d87  mov     rax, r14
0x180024d8a  add     rsp, 28h
0x180024d8e  pop     r15
0x180024d90  pop     r14
0x180024d92  pop     rdi
0x180024d93  pop     rsi
0x180024d94  pop     rbp
0x180024d95  pop     rbx
0x180024d96  retn
0x180024d97  mov     rcx, [rsp+58h]; this
0x180024d9c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
