# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x140002ee4`
- end: `0x140002fb6`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `210`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004d3c`
- `0x140005e44`
- `0x14000812c`

## callees

- `0x140002ee4`
- `0x1400073e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002f84`
- `msvcrt!memcpy_s` at `0x140002f84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002f5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002f5c`

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
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, -1, a4);
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
0x140002ee4  push    rbx
0x140002ee6  push    rbp
0x140002ee7  push    rsi
0x140002ee8  push    rdi
0x140002ee9  push    r12
0x140002eeb  push    r14
0x140002eed  push    r15
0x140002eef  sub     rsp, 20h
0x140002ef3  xor     r12d, r12d
0x140002ef6  mov     rdi, r8
0x140002ef9  mov     rbp, rdx
0x140002efc  mov     r14, rcx
0x140002eff  test    rdx, rdx
0x140002f02  jnz     short loc_140002F1A
0x140002f04  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140002f08  jnz     short loc_140002F15
0x140002f0a  mov     rcx, [rsp+58h]; this
0x140002f0f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140002f15  mov     rbx, rdi
0x140002f18  jmp     short loc_140002F4F
0x140002f1a  mov     ecx, 7FFFFFFFh
0x140002f1f  mov     rax, rdi
0x140002f22  cmp     rdi, rcx
0x140002f25  mov     rbx, rbp
0x140002f28  cmovnb  rax, rcx
0x140002f2c  test    rax, rax
0x140002f2f  jz      short loc_140002F41
0x140002f31  cmp     [rbx], r12w
0x140002f35  jz      short loc_140002F41
0x140002f37  add     rbx, 2
0x140002f3b  sub     rax, 1
0x140002f3f  jnz     short loc_140002F31
0x140002f41  sub     rbx, rbp
0x140002f44  sar     rbx, 1
0x140002f47  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140002f4b  cmovz   rdi, rbx
0x140002f4f  lea     r15, ds:2[rdi*2]
0x140002f57  xor     ecx, ecx; uFlags
0x140002f59  mov     rdx, r15; uBytes
0x140002f5c  call    cs:__imp_LocalAlloc
0x140002f63  nop     dword ptr [rax+rax+00h]
0x140002f68  mov     rsi, rax
0x140002f6b  test    rax, rax
0x140002f6e  jz      short loc_140002FA0
0x140002f70  test    rbp, rbp
0x140002f73  jz      short loc_140002F97
0x140002f75  add     rbx, rbx
0x140002f78  mov     r8, rbp; Source
0x140002f7b  mov     r9, rbx; SourceSize
0x140002f7e  mov     rdx, r15; DestinationSize
0x140002f81  mov     rcx, rax; Destination
0x140002f84  call    cs:__imp_memcpy_s
0x140002f8b  nop     dword ptr [rax+rax+00h]
0x140002f90  mov     [rbx+rsi], r12w
0x140002f95  jmp     short loc_140002F9B
0x140002f97  mov     [rax], r12w
0x140002f9b  mov     [rsi+rdi*2], r12w
0x140002fa0  mov     [r14], rsi
0x140002fa3  mov     rax, r14
0x140002fa6  add     rsp, 20h
0x140002faa  pop     r15
0x140002fac  pop     r14
0x140002fae  pop     r12
0x140002fb0  pop     rdi
0x140002fb1  pop     rsi
0x140002fb2  pop     rbp
0x140002fb3  pop     rbx
0x140002fb4  retn
```
