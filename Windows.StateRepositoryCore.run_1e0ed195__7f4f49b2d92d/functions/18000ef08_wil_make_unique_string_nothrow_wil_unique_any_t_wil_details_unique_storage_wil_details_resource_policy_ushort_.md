# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000ef08`
- end: `0x18000eff9`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f53c`

## callees

- `0x18000281a`
- `0x180002878`
- `0x18000a8b0`
- `0x18000ef08`
- `0x180010070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000efc3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000efc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef8c`

## string_xrefs

- `0x18000ef33`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  size_t v12; // rbx
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = LocalAlloc(0, 2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
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
0x18000ef08  push    rbx
0x18000ef0a  push    rbp
0x18000ef0b  push    rsi
0x18000ef0c  push    rdi
0x18000ef0d  push    r12
0x18000ef0f  push    r14
0x18000ef11  push    r15
0x18000ef13  sub     rsp, 20h
0x18000ef17  xor     r12d, r12d
0x18000ef1a  mov     rdi, r8
0x18000ef1d  mov     rbp, rdx
0x18000ef20  mov     r15, rcx
0x18000ef23  test    rdx, rdx
0x18000ef26  jnz     short loc_18000EF4A
0x18000ef28  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ef2c  jnz     short loc_18000EF45
0x18000ef2e  mov     rcx, [rsp+58h]; this
0x18000ef33  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ef3a  mov     edx, 0F89h; void *
0x18000ef3f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ef45  mov     rbx, rdi
0x18000ef48  jmp     short loc_18000EF7F
0x18000ef4a  mov     ecx, 7FFFFFFFh
0x18000ef4f  mov     rax, rdi
0x18000ef52  cmp     rdi, rcx
0x18000ef55  mov     rbx, rbp
0x18000ef58  cmovnb  rax, rcx
0x18000ef5c  test    rax, rax
0x18000ef5f  jz      short loc_18000EF71
0x18000ef61  cmp     [rbx], r12w
0x18000ef65  jz      short loc_18000EF71
0x18000ef67  add     rbx, 2
0x18000ef6b  sub     rax, 1
0x18000ef6f  jnz     short loc_18000EF61
0x18000ef71  sub     rbx, rbp
0x18000ef74  sar     rbx, 1
0x18000ef77  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ef7b  cmovz   rdi, rbx
0x18000ef7f  lea     r14, ds:2[rdi*2]
0x18000ef87  xor     ecx, ecx; uFlags
0x18000ef89  mov     rdx, r14; uBytes
0x18000ef8c  call    cs:__imp_LocalAlloc
0x18000ef92  mov     rsi, rax
0x18000ef95  test    rax, rax
0x18000ef98  jz      short loc_18000EFE4
0x18000ef9a  test    rbp, rbp
0x18000ef9d  jz      short loc_18000EFDB
0x18000ef9f  add     rbx, rbx
0x18000efa2  jz      short loc_18000EFD4
0x18000efa4  mov     rcx, rax; void *
0x18000efa7  cmp     r14, rbx
0x18000efaa  jb      short loc_18000EFB9
0x18000efac  mov     r8, rbx; Size
0x18000efaf  mov     rdx, rbp; Src
0x18000efb2  call    memcpy_0
0x18000efb7  jmp     short loc_18000EFD4
0x18000efb9  mov     r8, r14; Size
0x18000efbc  xor     edx, edx; Val
0x18000efbe  call    memset_0
0x18000efc3  call    cs:__imp__o__errno
0x18000efc9  mov     dword ptr [rax], 22h ; '"'
0x18000efcf  call    _invalid_parameter_noinfo
0x18000efd4  mov     [rbx+rsi], r12w
0x18000efd9  jmp     short loc_18000EFDF
0x18000efdb  mov     [rax], r12w
0x18000efdf  mov     [rsi+rdi*2], r12w
0x18000efe4  mov     [r15], rsi
0x18000efe7  mov     rax, r15
0x18000efea  add     rsp, 20h
0x18000efee  pop     r15
0x18000eff0  pop     r14
0x18000eff2  pop     r12
0x18000eff4  pop     rdi
0x18000eff5  pop     rsi
0x18000eff6  pop     rbp
0x18000eff7  pop     rbx
0x18000eff8  retn
```
