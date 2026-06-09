# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x140002e60`
- end: `0x140002f25`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `197`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004a60`
- `0x140005b1c`
- `0x140007cf4`

## callees

- `0x140002e60`
- `0x140006fe8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002efa`
- `msvcrt!memcpy_s` at `0x140002efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002ed8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002ed8`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  rsize_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
    v7 = a3;
  }
  v10 = LocalAlloc(0, 2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = v7;
      memcpy_s(v10, 2 * v4 + 2, a2, v12 * 2);
      v11[v12] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x140002e60  push    rbx
0x140002e62  push    rbp
0x140002e63  push    rsi
0x140002e64  push    rdi
0x140002e65  push    r12
0x140002e67  push    r14
0x140002e69  push    r15
0x140002e6b  sub     rsp, 20h
0x140002e6f  xor     r12d, r12d
0x140002e72  mov     rdi, r8
0x140002e75  mov     rbp, rdx
0x140002e78  mov     r14, rcx
0x140002e7b  test    rdx, rdx
0x140002e7e  jnz     short loc_140002E96
0x140002e80  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140002e84  jnz     short loc_140002E91
0x140002e86  mov     rcx, [rsp+58h]; this
0x140002e8b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140002e91  mov     rbx, rdi
0x140002e94  jmp     short loc_140002ECB
0x140002e96  mov     ecx, 7FFFFFFFh
0x140002e9b  mov     rax, rdi
0x140002e9e  cmp     rdi, rcx
0x140002ea1  mov     rbx, rbp
0x140002ea4  cmovnb  rax, rcx
0x140002ea8  test    rax, rax
0x140002eab  jz      short loc_140002EBD
0x140002ead  cmp     [rbx], r12w
0x140002eb1  jz      short loc_140002EBD
0x140002eb3  add     rbx, 2
0x140002eb7  sub     rax, 1
0x140002ebb  jnz     short loc_140002EAD
0x140002ebd  sub     rbx, rbp
0x140002ec0  sar     rbx, 1
0x140002ec3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140002ec7  cmovz   rdi, rbx
0x140002ecb  lea     r15, ds:2[rdi*2]
0x140002ed3  xor     ecx, ecx; uFlags
0x140002ed5  mov     rdx, r15; uBytes
0x140002ed8  call    cs:__imp_LocalAlloc
0x140002ede  mov     rsi, rax
0x140002ee1  test    rax, rax
0x140002ee4  jz      short loc_140002F10
0x140002ee6  test    rbp, rbp
0x140002ee9  jz      short loc_140002F07
0x140002eeb  add     rbx, rbx
0x140002eee  mov     r8, rbp; Source
0x140002ef1  mov     r9, rbx; SourceSize
0x140002ef4  mov     rdx, r15; DestinationSize
0x140002ef7  mov     rcx, rax; Destination
0x140002efa  call    cs:__imp_memcpy_s
0x140002f00  mov     [rbx+rsi], r12w
0x140002f05  jmp     short loc_140002F0B
0x140002f07  mov     [rax], r12w
0x140002f0b  mov     [rsi+rdi*2], r12w
0x140002f10  mov     [r14], rsi
0x140002f13  mov     rax, r14
0x140002f16  add     rsp, 20h
0x140002f1a  pop     r15
0x140002f1c  pop     r14
0x140002f1e  pop     r12
0x140002f20  pop     rdi
0x140002f21  pop     rsi
0x140002f22  pop     rbp
0x140002f23  pop     rbx
0x140002f24  retn
```
