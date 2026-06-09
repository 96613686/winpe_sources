# std::deque<ScheduledUmpMessage,std::allocator<ScheduledUmpMessage>>::_Growmap(unsigned __int64)

- ea: `0x18000be34`
- end: `0x18000c000`
- name: `?_Growmap@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@AEAAX_K@Z`
- size: `460`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18000a518`

## callees

- `0x180002024`
- `0x180002050`
- `0x180002a68`
- `0x18000be34`
- `0x18000c178`
- `0x18000c27c`
- `0x18000cc6c`

## pseudocode

```c
void __fastcall std::deque<ScheduledUmpMessage>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  _QWORD *v6; // r14
  void *v7; // rax
  __int64 v8; // r15
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  __int64 v17; // rcx
  void *v18; // rax

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0x666666666666666LL - v2 < v2 )
      std::deque<ScheduledUmpMessage>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_28;
  v5 = 8 * v2;
  if ( !(8 * v2) )
  {
    v6 = 0;
    goto LABEL_15;
  }
  if ( v5 < 0x1000 )
  {
    v6 = operator new(v5);
    goto LABEL_15;
  }
  if ( v5 + 39 < v5 )
LABEL_28:
    __scrt_throw_std_bad_array_new_length();
  v7 = operator new(v5 + 39);
  if ( !v7 )
    goto LABEL_24;
  v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v6 - 1) = v7;
LABEL_15:
  v8 = 8 * v4;
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v8;
  memmove_0(&v6[v4], (const void *)(a1[1] + v8), v12);
  v13 = (const void *)a1[1];
  v14 = (char *)&v6[v4] + v12;
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v8 - 8 * v11);
    v16 = (char *)v6 + v8 - 8 * v11;
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v8], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = (char *)v6;
  }
  memset_0(v16, 0, v15);
  v17 = a1[1];
  if ( v17 )
  {
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v18 = (void *)a1[1];
    }
    else
    {
      v18 = *(void **)(v17 - 8);
      if ( (unsigned __int64)(v17 - (_QWORD)v18 - 8) > 0x1F )
LABEL_24:
        __fastfail(5u);
    }
    operator delete(v18);
  }
  a1[2] += v11;
  a1[1] = v6;
}

```

## disassembly

```asm
0x18000be34  push    rbx
0x18000be36  push    rbp
0x18000be37  push    rsi
0x18000be38  push    rdi
0x18000be39  push    r12
0x18000be3b  push    r14
0x18000be3d  push    r15
0x18000be3f  sub     rsp, 20h
0x18000be43  mov     rbp, rcx
0x18000be46  mov     esi, 1
0x18000be4b  mov     rcx, [rcx+10h]
0x18000be4f  test    rcx, rcx
0x18000be52  cmovnz  rsi, rcx
0x18000be56  mov     rax, rsi
0x18000be59  sub     rax, rcx
0x18000be5c  cmp     rax, 1
0x18000be60  jb      short loc_18000BE68
0x18000be62  cmp     rsi, 8
0x18000be66  jnb     short loc_18000BE83
0x18000be68  mov     rax, 666666666666666h
0x18000be72  sub     rax, rsi
0x18000be75  cmp     rax, rsi
0x18000be78  jb      loc_18000BFFA
0x18000be7e  add     rsi, rsi
0x18000be81  jmp     short loc_18000BE56
0x18000be83  mov     rdi, [rbp+18h]
0x18000be87  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000be91  cmp     rsi, rax
0x18000be94  ja      loc_18000BFF4
0x18000be9a  lea     rcx, ds:0[rsi*8]; Size
0x18000bea2  test    rcx, rcx
0x18000bea5  jnz     short loc_18000BEAC
0x18000bea7  xor     r14d, r14d
0x18000beaa  jmp     short loc_18000BEE9
0x18000beac  cmp     rcx, 1000h
0x18000beb3  jb      short loc_18000BEE1
0x18000beb5  lea     rax, [rcx+27h]
0x18000beb9  cmp     rax, rcx
0x18000bebc  jbe     loc_18000BFF4
0x18000bec2  mov     rcx, rax; Size
0x18000bec5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000beca  test    rax, rax
0x18000becd  jz      loc_18000BFCB
0x18000bed3  lea     r14, [rax+27h]
0x18000bed7  and     r14, 0FFFFFFFFFFFFFFE0h
0x18000bedb  mov     [r14-8], rax
0x18000bedf  jmp     short loc_18000BEE9
0x18000bee1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bee6  mov     r14, rax
0x18000bee9  lea     r15, ds:0[rdi*8]
0x18000bef1  mov     rax, rsi
0x18000bef4  lea     r12, [r15+r14]
0x18000bef8  shr     rax, 1
0x18000befb  jmp     short loc_18000BF00
0x18000befd  add     rsi, rsi
0x18000bf00  cmp     rsi, rax
0x18000bf03  jbe     short loc_18000BEFD
0x18000bf05  mov     rcx, [rbp+8]
0x18000bf09  mov     rax, [rbp+10h]
0x18000bf0d  sub     rsi, rax
0x18000bf10  shl     rax, 3
0x18000bf14  lea     rdx, [rcx+r15]; Src
0x18000bf18  sub     rax, rdx
0x18000bf1b  lea     rbx, [rax+rcx]
0x18000bf1f  mov     rcx, r12; void *
0x18000bf22  mov     r8, rbx; Size
0x18000bf25  call    memmove_0
0x18000bf2a  mov     rdx, [rbp+8]; Src
0x18000bf2e  add     rbx, r12
0x18000bf31  mov     rcx, rbx; void *
0x18000bf34  cmp     rdi, rsi
0x18000bf37  ja      short loc_18000BF5E
0x18000bf39  mov     r8, r15; Size
0x18000bf3c  call    memmove_0
0x18000bf41  mov     r8, rsi
0x18000bf44  lea     rcx, [rbx+r15]; void *
0x18000bf48  sub     r8, rdi
0x18000bf4b  xor     edx, edx; Val
0x18000bf4d  shl     r8, 3; Size
0x18000bf51  call    memset_0
0x18000bf56  mov     r8, r15
0x18000bf59  mov     rcx, r14
0x18000bf5c  jmp     short loc_18000BF8F
0x18000bf5e  lea     rdi, ds:0[rsi*8]
0x18000bf66  mov     r8, rdi; Size
0x18000bf69  call    memmove_0
0x18000bf6e  mov     rax, [rbp+8]
0x18000bf72  mov     rcx, r14; void *
0x18000bf75  lea     rdx, [rdi+rax]; Src
0x18000bf79  sub     rax, rdx
0x18000bf7c  lea     rbx, [rax+r15]
0x18000bf80  mov     r8, rbx; Size
0x18000bf83  call    memmove_0
0x18000bf88  lea     rcx, [rbx+r14]; void *
0x18000bf8c  mov     r8, rdi; Size
0x18000bf8f  xor     edx, edx; Val
0x18000bf91  call    memset_0
0x18000bf96  mov     rcx, [rbp+8]
0x18000bf9a  test    rcx, rcx
0x18000bf9d  jz      short loc_18000BFDD
0x18000bf9f  mov     rax, [rbp+10h]
0x18000bfa3  lea     rdx, ds:0[rax*8]
0x18000bfab  cmp     rdx, 1000h
0x18000bfb2  jb      short loc_18000BFD2
0x18000bfb4  mov     rax, [rcx-8]
0x18000bfb8  sub     rcx, rax
0x18000bfbb  sub     rcx, 8
0x18000bfbf  cmp     rcx, 1Fh
0x18000bfc3  ja      short loc_18000BFCB
0x18000bfc5  add     rdx, 27h ; '''
0x18000bfc9  jmp     short loc_18000BFD5
0x18000bfcb  mov     ecx, 5
0x18000bfd0  int     29h; Win8: RtlFailFast(ecx)
0x18000bfd2  mov     rax, rcx
0x18000bfd5  mov     rcx, rax; Block
0x18000bfd8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bfdd  add     [rbp+10h], rsi
0x18000bfe1  mov     [rbp+8], r14
0x18000bfe5  add     rsp, 20h
0x18000bfe9  pop     r15
0x18000bfeb  pop     r14
0x18000bfed  pop     r12
0x18000bfef  pop     rdi
0x18000bff0  pop     rsi
0x18000bff1  pop     rbp
0x18000bff2  pop     rbx
0x18000bff3  retn
0x18000bff4  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18000bffa  call    ?_Xlen@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@CAXXZ; std::deque<ScheduledUmpMessage>::_Xlen(void)
```
