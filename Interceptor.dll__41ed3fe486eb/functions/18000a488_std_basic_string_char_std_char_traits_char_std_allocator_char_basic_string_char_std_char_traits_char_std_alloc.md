# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(std::_String_constructor_concat_tag,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,char const * const,unsigned __int64,char const * const,unsigned __int64)

- ea: `0x18000a488`
- end: `0x18000a57f`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z`
- size: `247`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, size_t Size, void *Src, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019f74`

## callees

- `0x180005224`
- `0x18000a488`
- `0x18000ab0c`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a56b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a56b`

## string_xrefs

- `0x18000a515`: `StructuredTraceJsonSerializer::Visit failed to write structured field `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::string::string(char *a1, __int64 a2, __int64 a3, __int64 a4, size_t Size, void *Src, size_t a7)
{
  size_t v8; // rbp
  __int64 v9; // rbx
  char *v10; // rdi
  size_t v11; // rcx

  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  v8 = Size + a7;
  v9 = 15;
  v10 = a1;
  if ( Size + a7 > 0xF )
  {
    v9 = 0x7FFFFFFFFFFFFFFFLL;
    if ( (v8 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v9 = v8 | 0xF;
      if ( (v8 | 0xF) < 0x16 )
        v9 = 22;
    }
    v11 = v9 + 1;
    if ( v9 == -1 )
    {
      v10 = 0;
    }
    else
    {
      _mm_lfence();
      if ( v11 < 0x1000 )
      {
        v10 = (char *)malloc(v11);
        if ( !v10 )
          std::_Xbad_alloc();
      }
      else
      {
        v10 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>();
      }
    }
    *(_QWORD *)a1 = v10;
  }
  *((_QWORD *)a1 + 2) = v8;
  *((_QWORD *)a1 + 3) = v9;
  memmove(v10, "StructuredTraceJsonSerializer::Visit failed to write structured field ", Size);
  memmove(&v10[Size], Src, a7);
  v10[v8] = 0;
  return a1;
}

```

## disassembly

```asm
0x18000a488  mov     rax, rsp
0x18000a48b  mov     [rax+10h], rbx
0x18000a48f  mov     [rax+18h], rbp
0x18000a493  mov     [rax+20h], rsi
0x18000a497  mov     [rax+8], rcx
0x18000a49b  push    rdi
0x18000a49c  push    r14
0x18000a49e  push    r15
0x18000a4a0  sub     rsp, 20h
0x18000a4a4  mov     rsi, rcx
0x18000a4a7  xorps   xmm0, xmm0
0x18000a4aa  movups  xmmword ptr [rcx], xmm0
0x18000a4ad  mov     qword ptr [rcx+10h], 0
0x18000a4b5  mov     qword ptr [rcx+18h], 0
0x18000a4bd  mov     r14, [rsp+38h+Size]
0x18000a4c2  mov     r15, [rsp+38h+arg_30]
0x18000a4c7  lea     rbp, [r14+r15]
0x18000a4cb  mov     ebx, 0Fh
0x18000a4d0  mov     rdi, rcx
0x18000a4d3  cmp     rbp, rbx
0x18000a4d6  jbe     short loc_18000A50A
0x18000a4d8  mov     rax, rbp
0x18000a4db  or      rax, rbx
0x18000a4de  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18000a4e8  cmp     rax, rbx
0x18000a4eb  ja      short loc_18000A4FC
0x18000a4ed  mov     rbx, rax
0x18000a4f0  mov     ecx, 16h
0x18000a4f5  cmp     rax, rcx
0x18000a4f8  cmovb   rbx, rcx
0x18000a4fc  lea     rcx, [rbx+1]; Size
0x18000a500  test    rcx, rcx
0x18000a503  jnz     short loc_18000A555
0x18000a505  xor     edi, edi
0x18000a507  mov     [rsi], rdi
0x18000a50a  mov     [rsi+10h], rbp
0x18000a50e  mov     [rsi+18h], rbx
0x18000a512  mov     r8, r14; Size
0x18000a515  lea     rdx, aStructuredtrac_3; "StructuredTraceJsonSerializer::Visit fa"...
0x18000a51c  mov     rcx, rdi; void *
0x18000a51f  call    memmove
0x18000a524  lea     rcx, [rdi+r14]; void *
0x18000a528  mov     r8, r15; Size
0x18000a52b  mov     rdx, [rsp+38h+Src]; Src
0x18000a530  call    memmove
0x18000a535  mov     byte ptr [rdi+rbp], 0
0x18000a539  mov     rax, rsi
0x18000a53c  mov     rbx, [rsp+38h+arg_8]
0x18000a541  mov     rbp, [rsp+38h+arg_10]
0x18000a546  mov     rsi, [rsp+38h+arg_18]
0x18000a54b  add     rsp, 20h
0x18000a54f  pop     r15
0x18000a551  pop     r14
0x18000a553  pop     rdi
0x18000a554  retn
0x18000a555  lfence
0x18000a558  cmp     rcx, 1000h
0x18000a55f  jb      short loc_18000A56B
0x18000a561  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18000a566  mov     rdi, rax
0x18000a569  jmp     short loc_18000A507
0x18000a56b  call    cs:__imp_malloc
0x18000a571  mov     rdi, rax
0x18000a574  test    rax, rax
0x18000a577  jnz     short loc_18000A507
0x18000a579  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
