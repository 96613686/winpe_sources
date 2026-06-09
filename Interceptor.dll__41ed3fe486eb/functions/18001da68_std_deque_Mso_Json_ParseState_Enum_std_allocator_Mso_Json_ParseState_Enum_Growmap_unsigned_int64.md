# std::deque<Mso::Json::ParseState::Enum,std::allocator<Mso::Json::ParseState::Enum>>::_Growmap(unsigned __int64)

- ea: `0x18001da68`
- end: `0x18001dc56`
- name: `?_Growmap@?$deque@W4Enum@ParseState@Json@Mso@@V?$allocator@W4Enum@ParseState@Json@Mso@@@std@@@std@@AEAAX_K@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001d998`

## callees

- `0x180001b14`
- `0x180005224`
- `0x18000ab0c`
- `0x180015da4`
- `0x18001da68`
- `0x18002b400`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001dc3d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001dc3d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001db1a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001db1a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001dbfd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001dbfd`

## pseudocode

```c
void __fastcall std::deque<enum Mso::Json::ParseState::Enum>::_Growmap(__int64 a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  char *v6; // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rsi
  size_t v11; // rbx
  char *v12; // r12
  size_t v13; // r8
  char *v14; // rcx
  _QWORD *v15; // rcx

  v2 = 1;
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<enum Mso::Json::ParseState::Enum>::_Xlen();
    v2 *= 2LL;
  }
  v4 = *(_QWORD *)(a1 + 24) >> 2;
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    std::_Throw_bad_array_new_length();
  v5 = 8 * v2;
  if ( 8 * v2 )
  {
    _mm_lfence();
    if ( v5 < 0x1000 )
    {
      v6 = (char *)malloc(v5);
      if ( !v6 )
        std::_Xbad_alloc();
    }
    else
    {
      v6 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v5);
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = 8 * v4;
  v8 = v2 >> 1;
  while ( v2 <= v8 )
    v2 *= 2LL;
  v9 = *(_QWORD *)(a1 + 16);
  v10 = v2 - v9;
  v11 = 8 * v9 - v7;
  memmove(&v6[8 * v4], (const void *)(*(_QWORD *)(a1 + 8) + v7), v11);
  v12 = &v6[8 * v4 + v11];
  if ( v4 > v10 )
  {
    _mm_lfence();
    memmove(v12, *(const void **)(a1 + 8), 8 * v10);
    memmove(v6, (const void *)(8 * v10 + *(_QWORD *)(a1 + 8)), v7 - 8 * v10);
    v14 = &v6[v7 - 8 * v10];
    v13 = 8 * v10;
  }
  else
  {
    memmove(v12, *(const void **)(a1 + 8), 8 * v4);
    memset(&v12[v7], 0, 8 * (v10 - v4));
    v13 = 8 * v4;
    v14 = v6;
  }
  memset(v14, 0, v13);
  v15 = *(_QWORD **)(a1 + 8);
  if ( v15 )
  {
    if ( (unsigned __int64)(8LL * *(_QWORD *)(a1 + 16)) >= 0x1000 )
    {
      if ( (unsigned __int64)v15 - *(v15 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v15 = (_QWORD *)*(v15 - 1);
    }
    free(v15);
  }
  *(_QWORD *)(a1 + 16) += v10;
  *(_QWORD *)(a1 + 8) = v6;
}

```

## disassembly

```asm
0x18001da68  mov     rax, rsp
0x18001da6b  mov     [rax+8], rbx
0x18001da6f  mov     [rax+10h], rbp
0x18001da73  mov     [rax+18h], rsi
0x18001da77  mov     [rax+20h], rdi
0x18001da7b  push    r12
0x18001da7d  push    r14
0x18001da7f  push    r15
0x18001da81  sub     rsp, 30h
0x18001da85  mov     rbp, rcx
0x18001da88  mov     esi, 1
0x18001da8d  mov     rcx, [rcx+10h]
0x18001da91  test    rcx, rcx
0x18001da94  cmovnz  rsi, rcx
0x18001da98  mov     rax, rsi
0x18001da9b  sub     rax, rcx
0x18001da9e  cmp     rax, 1
0x18001daa2  jb      short loc_18001DAAA
0x18001daa4  cmp     rsi, 8
0x18001daa8  jnb     short loc_18001DAC5
0x18001daaa  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001dab4  sub     rax, rsi
0x18001dab7  cmp     rax, rsi
0x18001daba  jb      loc_18001DC50
0x18001dac0  add     rsi, rsi
0x18001dac3  jmp     short loc_18001DA98
0x18001dac5  mov     rdi, [rbp+18h]
0x18001dac9  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001dad3  shr     rdi, 2
0x18001dad7  cmp     rsi, rax
0x18001dada  ja      loc_18001DC44
0x18001dae0  lea     rcx, ds:0[rsi*8]; Size
0x18001dae8  test    rcx, rcx
0x18001daeb  jnz     short loc_18001DB04
0x18001daed  xor     r14d, r14d
0x18001daf0  lea     r15, ds:0[rdi*8]
0x18001daf8  mov     rax, rsi
0x18001dafb  lea     r12, [r14+r15]
0x18001daff  shr     rax, 1
0x18001db02  jmp     short loc_18001DB31
0x18001db04  lfence
0x18001db07  cmp     rcx, 1000h
0x18001db0e  jb      short loc_18001DB1A
0x18001db10  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001db15  mov     r14, rax
0x18001db18  jmp     short loc_18001DAF0
0x18001db1a  call    cs:__imp_malloc
0x18001db20  mov     r14, rax
0x18001db23  test    rax, rax
0x18001db26  jz      loc_18001DC4A
0x18001db2c  jmp     short loc_18001DAF0
0x18001db2e  add     rsi, rsi
0x18001db31  cmp     rsi, rax
0x18001db34  jbe     short loc_18001DB2E
0x18001db36  mov     rcx, [rbp+10h]
0x18001db3a  mov     rax, [rbp+8]
0x18001db3e  sub     rsi, rcx
0x18001db41  lea     rbx, ds:0[rcx*8]
0x18001db49  mov     rcx, r12; void *
0x18001db4c  lea     rdx, [rax+r15]; Src
0x18001db50  sub     rbx, rdx
0x18001db53  add     rbx, rax
0x18001db56  mov     r8, rbx; Size
0x18001db59  call    memmove
0x18001db5e  add     r12, rbx
0x18001db61  mov     rcx, r12; void *
0x18001db64  cmp     rdi, rsi
0x18001db67  ja      short loc_18001DB92
0x18001db69  mov     rdx, [rbp+8]; Src
0x18001db6d  mov     r8, r15; Size
0x18001db70  call    memmove
0x18001db75  mov     r8, rsi
0x18001db78  lea     rcx, [r15+r12]; void *
0x18001db7c  sub     r8, rdi
0x18001db7f  xor     edx, edx; Val
0x18001db81  shl     r8, 3; Size
0x18001db85  call    memset
0x18001db8a  mov     r8, r15
0x18001db8d  mov     rcx, r14
0x18001db90  jmp     short loc_18001DBC9
0x18001db92  lfence
0x18001db95  mov     rdx, [rbp+8]; Src
0x18001db99  lea     rdi, ds:0[rsi*8]
0x18001dba1  mov     r8, rdi; Size
0x18001dba4  call    memmove
0x18001dba9  mov     rbx, [rbp+8]
0x18001dbad  mov     rcx, r14; void *
0x18001dbb0  lea     rdx, [rdi+rbx]; Src
0x18001dbb4  sub     rbx, rdx
0x18001dbb7  add     rbx, r15
0x18001dbba  mov     r8, rbx; Size
0x18001dbbd  call    memmove
0x18001dbc2  lea     rcx, [rbx+r14]; void *
0x18001dbc6  mov     r8, rdi; Size
0x18001dbc9  xor     edx, edx; Val
0x18001dbcb  call    memset
0x18001dbd0  mov     rcx, [rbp+8]
0x18001dbd4  test    rcx, rcx
0x18001dbd7  jz      short loc_18001DC03
0x18001dbd9  mov     rax, [rbp+10h]
0x18001dbdd  shl     rax, 3
0x18001dbe1  cmp     rax, 1000h
0x18001dbe7  jb      short loc_18001DBFD
0x18001dbe9  mov     rdx, [rcx-8]
0x18001dbed  sub     rcx, rdx
0x18001dbf0  lea     rax, [rcx-8]
0x18001dbf4  cmp     rax, 1Fh
0x18001dbf8  ja      short loc_18001DC2A
0x18001dbfa  mov     rcx, rdx; Block
0x18001dbfd  call    cs:__imp_free
0x18001dc03  add     [rbp+10h], rsi
0x18001dc07  mov     rsi, [rsp+48h+arg_10]
0x18001dc0c  mov     rbx, [rsp+48h+arg_0]
0x18001dc11  mov     rdi, [rsp+48h+arg_18]
0x18001dc16  mov     [rbp+8], r14
0x18001dc1a  mov     rbp, [rsp+48h+arg_8]
0x18001dc1f  add     rsp, 30h
0x18001dc23  pop     r15
0x18001dc25  pop     r14
0x18001dc27  pop     r12
0x18001dc29  retn
0x18001dc2a  xor     r9d, r9d; LineNo
0x18001dc2d  mov     [rsp+48h+Reserved], 0; Reserved
0x18001dc36  xor     r8d, r8d; FileName
0x18001dc39  xor     edx, edx; FunctionName
0x18001dc3b  xor     ecx, ecx; Expression
0x18001dc3d  call    cs:__imp__invoke_watson
0x18001dc44  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18001dc4a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001dc50  call    ?_Xlen@?$deque@W4Enum@ParseState@Json@Mso@@V?$allocator@W4Enum@ParseState@Json@Mso@@@std@@@std@@CAXXZ; std::deque<Mso::Json::ParseState::Enum>::_Xlen(void)
```
