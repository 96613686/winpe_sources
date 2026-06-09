# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x18001f6f8`
- end: `0x18001f7a6`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `174`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d474`
- `0x180045100`
- `0x1800452bc`
- `0x180048b80`
- `0x180048e60`

## callees

- `0x180005e16`
- `0x180005e84`
- `0x180005e9c`
- `0x18001f5a0`
- `0x18001f6f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001f772`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001f772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f740`

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
0x18001f6f8  push    rbx
0x18001f6fa  push    rbp
0x18001f6fb  push    rsi
0x18001f6fc  push    rdi
0x18001f6fd  push    r14
0x18001f6ff  push    r15
0x18001f701  sub     rsp, 28h
0x18001f705  xor     r15d, r15d
0x18001f708  mov     rsi, rdx
0x18001f70b  mov     r14, rcx
0x18001f70e  test    rdx, rdx
0x18001f711  jz      loc_18001F79B
0x18001f717  mov     ecx, 7FFFFFFFh
0x18001f71c  mov     rax, rdx
0x18001f71f  cmp     [rax], r15w
0x18001f723  jz      short loc_18001F72F
0x18001f725  add     rax, 2
0x18001f729  sub     rcx, 1
0x18001f72d  jnz     short loc_18001F71F
0x18001f72f  sub     rax, rsi
0x18001f732  sar     rax, 1
0x18001f735  lea     rbx, [rax+rax]
0x18001f739  lea     rbp, [rbx+2]
0x18001f73d  mov     rcx, rbp; cb
0x18001f740  call    cs:__imp_CoTaskMemAlloc
0x18001f746  mov     rdi, rax
0x18001f749  test    rax, rax
0x18001f74c  jz      short loc_18001F788
0x18001f74e  test    rbx, rbx
0x18001f751  jz      short loc_18001F783
0x18001f753  mov     rcx, rax; void *
0x18001f756  cmp     rbp, rbx
0x18001f759  jb      short loc_18001F768
0x18001f75b  mov     r8, rbx; Size
0x18001f75e  mov     rdx, rsi; Src
0x18001f761  call    memcpy_0
0x18001f766  jmp     short loc_18001F783
0x18001f768  mov     r8, rbp; Size
0x18001f76b  xor     edx, edx; Val
0x18001f76d  call    memset_0
0x18001f772  call    cs:__imp__o__errno
0x18001f778  mov     dword ptr [rax], 22h ; '"'
0x18001f77e  call    _invalid_parameter_noinfo
0x18001f783  mov     [rbx+rdi], r15w
0x18001f788  mov     [r14], rdi
0x18001f78b  mov     rax, r14
0x18001f78e  add     rsp, 28h
0x18001f792  pop     r15
0x18001f794  pop     r14
0x18001f796  pop     rdi
0x18001f797  pop     rsi
0x18001f798  pop     rbp
0x18001f799  pop     rbx
0x18001f79a  retn
0x18001f79b  mov     rcx, [rsp+58h]; this
0x18001f7a0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
