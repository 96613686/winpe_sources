# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x18001e528`
- end: `0x18001e5d6`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `174`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d33c`
- `0x18001ea90`
- `0x18001ec4c`

## callees

- `0x180004626`
- `0x180004688`
- `0x1800046a0`
- `0x18001e508`
- `0x18001e528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e5a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e5a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e570`

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
0x18001e528  push    rbx
0x18001e52a  push    rbp
0x18001e52b  push    rsi
0x18001e52c  push    rdi
0x18001e52d  push    r14
0x18001e52f  push    r15
0x18001e531  sub     rsp, 28h
0x18001e535  xor     r15d, r15d
0x18001e538  mov     rsi, rdx
0x18001e53b  mov     r14, rcx
0x18001e53e  test    rdx, rdx
0x18001e541  jz      loc_18001E5CB
0x18001e547  mov     ecx, 7FFFFFFFh
0x18001e54c  mov     rax, rdx
0x18001e54f  cmp     [rax], r15w
0x18001e553  jz      short loc_18001E55F
0x18001e555  add     rax, 2
0x18001e559  sub     rcx, 1
0x18001e55d  jnz     short loc_18001E54F
0x18001e55f  sub     rax, rsi
0x18001e562  sar     rax, 1
0x18001e565  lea     rbx, [rax+rax]
0x18001e569  lea     rbp, [rbx+2]
0x18001e56d  mov     rcx, rbp; cb
0x18001e570  call    cs:__imp_CoTaskMemAlloc
0x18001e576  mov     rdi, rax
0x18001e579  test    rax, rax
0x18001e57c  jz      short loc_18001E5B8
0x18001e57e  test    rbx, rbx
0x18001e581  jz      short loc_18001E5B3
0x18001e583  mov     rcx, rax; void *
0x18001e586  cmp     rbp, rbx
0x18001e589  jb      short loc_18001E598
0x18001e58b  mov     r8, rbx; Size
0x18001e58e  mov     rdx, rsi; Src
0x18001e591  call    memcpy_0
0x18001e596  jmp     short loc_18001E5B3
0x18001e598  mov     r8, rbp; Size
0x18001e59b  xor     edx, edx; Val
0x18001e59d  call    memset_0
0x18001e5a2  call    cs:__imp__o__errno
0x18001e5a8  mov     dword ptr [rax], 22h ; '"'
0x18001e5ae  call    _invalid_parameter_noinfo
0x18001e5b3  mov     [rbx+rdi], r15w
0x18001e5b8  mov     [r14], rdi
0x18001e5bb  mov     rax, r14
0x18001e5be  add     rsp, 28h
0x18001e5c2  pop     r15
0x18001e5c4  pop     r14
0x18001e5c6  pop     rdi
0x18001e5c7  pop     rsi
0x18001e5c8  pop     rbp
0x18001e5c9  pop     rbx
0x18001e5ca  retn
0x18001e5cb  mov     rcx, [rsp+58h]; this
0x18001e5d0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
