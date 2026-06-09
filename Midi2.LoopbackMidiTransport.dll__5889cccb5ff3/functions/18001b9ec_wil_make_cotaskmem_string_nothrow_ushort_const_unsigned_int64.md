# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x18001b9ec`
- end: `0x18001ba9a`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `174`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017584`
- `0x1800220d0`
- `0x18002228c`

## callees

- `0x180004f86`
- `0x180004ff4`
- `0x18000500c`
- `0x18001b430`
- `0x18001b9ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ba66`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ba66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ba34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ba34`

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
0x18001b9ec  push    rbx
0x18001b9ee  push    rbp
0x18001b9ef  push    rsi
0x18001b9f0  push    rdi
0x18001b9f1  push    r14
0x18001b9f3  push    r15
0x18001b9f5  sub     rsp, 28h
0x18001b9f9  xor     r15d, r15d
0x18001b9fc  mov     rsi, rdx
0x18001b9ff  mov     r14, rcx
0x18001ba02  test    rdx, rdx
0x18001ba05  jz      loc_18001BA8F
0x18001ba0b  mov     ecx, 7FFFFFFFh
0x18001ba10  mov     rax, rdx
0x18001ba13  cmp     [rax], r15w
0x18001ba17  jz      short loc_18001BA23
0x18001ba19  add     rax, 2
0x18001ba1d  sub     rcx, 1
0x18001ba21  jnz     short loc_18001BA13
0x18001ba23  sub     rax, rsi
0x18001ba26  sar     rax, 1
0x18001ba29  lea     rbx, [rax+rax]
0x18001ba2d  lea     rbp, [rbx+2]
0x18001ba31  mov     rcx, rbp; cb
0x18001ba34  call    cs:__imp_CoTaskMemAlloc
0x18001ba3a  mov     rdi, rax
0x18001ba3d  test    rax, rax
0x18001ba40  jz      short loc_18001BA7C
0x18001ba42  test    rbx, rbx
0x18001ba45  jz      short loc_18001BA77
0x18001ba47  mov     rcx, rax; void *
0x18001ba4a  cmp     rbp, rbx
0x18001ba4d  jb      short loc_18001BA5C
0x18001ba4f  mov     r8, rbx; Size
0x18001ba52  mov     rdx, rsi; Src
0x18001ba55  call    memcpy_0
0x18001ba5a  jmp     short loc_18001BA77
0x18001ba5c  mov     r8, rbp; Size
0x18001ba5f  xor     edx, edx; Val
0x18001ba61  call    memset_0
0x18001ba66  call    cs:__imp__o__errno
0x18001ba6c  mov     dword ptr [rax], 22h ; '"'
0x18001ba72  call    _invalid_parameter_noinfo
0x18001ba77  mov     [rbx+rdi], r15w
0x18001ba7c  mov     [r14], rdi
0x18001ba7f  mov     rax, r14
0x18001ba82  add     rsp, 28h
0x18001ba86  pop     r15
0x18001ba88  pop     r14
0x18001ba8a  pop     rdi
0x18001ba8b  pop     rsi
0x18001ba8c  pop     rbp
0x18001ba8d  pop     rbx
0x18001ba8e  retn
0x18001ba8f  mov     rcx, [rsp+58h]; this
0x18001ba94  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
