# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x140035ae0`
- end: `0x140035b64`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `132`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140029640`
- `0x14002c6b0`
- `0x14003b784`

## callees

- `0x14000cd78`
- `0x140035790`
- `0x140035ae0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140035b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140035b21`

## pseudocode

```c
wil *__fastcall wil::make_cotaskmem_string_nothrow(wil *this, const unsigned __int16 *a2, __int64 a3, const char *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
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
  v9 = (char *)CoTaskMemAlloc(v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *(_QWORD *)this = v10;
  return this;
}

```

## disassembly

```asm
0x140035ae0  push    rbx
0x140035ae2  push    rbp
0x140035ae3  push    rsi
0x140035ae4  push    rdi
0x140035ae5  push    r14
0x140035ae7  push    r15
0x140035ae9  sub     rsp, 28h
0x140035aed  xor     r15d, r15d
0x140035af0  mov     rbx, rdx
0x140035af3  mov     rsi, rcx
0x140035af6  test    rdx, rdx
0x140035af9  jz      short loc_140035B59
0x140035afb  mov     ecx, 7FFFFFFFh
0x140035b00  mov     rax, rdx
0x140035b03  cmp     [rax], r15w
0x140035b07  jz      short loc_140035B13
0x140035b09  add     rax, 2
0x140035b0d  sub     rcx, 1
0x140035b11  jnz     short loc_140035B03
0x140035b13  sub     rax, rbx
0x140035b16  sar     rax, 1
0x140035b19  lea     r14, [rax+rax]
0x140035b1d  lea     rcx, [r14+2]; cb
0x140035b21  call    cs:__imp_CoTaskMemAlloc
0x140035b27  mov     rdi, rax
0x140035b2a  test    rax, rax
0x140035b2d  jz      short loc_140035B46
0x140035b2f  mov     r9, r14; SourceSize
0x140035b32  lea     rdx, [r14+2]; DestinationSize
0x140035b36  mov     r8, rbx; Source
0x140035b39  mov     rcx, rax; Destination
0x140035b3c  call    memcpy_s
0x140035b41  mov     [r14+rdi], r15w
0x140035b46  mov     [rsi], rdi
0x140035b49  mov     rax, rsi
0x140035b4c  add     rsp, 28h
0x140035b50  pop     r15
0x140035b52  pop     r14
0x140035b54  pop     rdi
0x140035b55  pop     rsi
0x140035b56  pop     rbp
0x140035b57  pop     rbx
0x140035b58  retn
0x140035b59  mov     rcx, [rsp+58h]; this
0x140035b5e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
