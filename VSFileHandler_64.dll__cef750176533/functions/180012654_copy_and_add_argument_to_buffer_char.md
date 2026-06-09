# copy_and_add_argument_to_buffer_char_

- ea: `0x180012654`
- end: `0x1800127db`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `391`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180012448`
- `0x1800127dc`

## callees

- `0x18000bebc`
- `0x18000bfe4`
- `0x18000fe3c`
- `0x1800120b0`
- `0x180012654`
- `0x180017470`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer_char_(char *Source, char *a2, rsize_t MaxCount, __int64 a4)
{
  __int64 v4; // rbp
  unsigned int v6; // esi
  rsize_t v10; // rbp
  size_t v12; // r15
  char *v13; // rax
  char *v14; // rbx
  _QWORD *v15; // rcx
  _QWORD *v16; // r14
  unsigned __int64 v17; // r14
  char *v18; // rax

  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( Source[v4] );
  v10 = v4 + 1;
  if ( v10 > ~MaxCount )
    return 12;
  v12 = v10 + MaxCount + 1;
  v13 = (char *)calloc_base(v12, 1u);
  v14 = v13;
  if ( MaxCount && strncpy_s(v13, v12, a2, MaxCount) || strncpy_s(&v14[MaxCount], v12 - MaxCount, Source, v10) )
    invoke_watson(0, 0, 0, 0, 0);
  v15 = *(_QWORD **)(a4 + 8);
  v16 = *(_QWORD **)(a4 + 16);
  if ( v15 != v16 )
    goto LABEL_18;
  if ( *(_QWORD *)a4 )
  {
    v17 = ((__int64)v16 - *(_QWORD *)a4) >> 3;
    if ( v17 <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v18 = (char *)recalloc_base(*(void **)a4, 2 * v17, 8u);
      if ( v18 )
      {
        *(_QWORD *)a4 = v18;
        *(_QWORD *)(a4 + 8) = &v18[8 * v17];
        *(_QWORD *)(a4 + 16) = &v18[16 * v17];
        free_base(0);
        v15 = *(_QWORD **)(a4 + 8);
        goto LABEL_18;
      }
      free_base(0);
    }
  }
  else
  {
    *(_QWORD *)a4 = calloc_base(4u, 8u);
    free_base(0);
    v15 = *(_QWORD **)a4;
    if ( *(_QWORD *)a4 )
    {
      *(_QWORD *)(a4 + 8) = v15;
      *(_QWORD *)(a4 + 16) = v15 + 4;
LABEL_18:
      *v15 = v14;
      *(_QWORD *)(a4 + 8) += 8LL;
      goto LABEL_16;
    }
  }
  free_base(v14);
  v6 = 12;
LABEL_16:
  free_base(0);
  return v6;
}

```

## disassembly

```asm
0x180012654  mov     [rsp+arg_0], rbx
0x180012659  mov     [rsp+arg_8], rbp
0x18001265e  mov     [rsp+arg_10], rsi
0x180012663  push    rdi
0x180012664  push    r12
0x180012666  push    r13
0x180012668  push    r14
0x18001266a  push    r15
0x18001266c  sub     rsp, 30h
0x180012670  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180012674  mov     rdi, r9
0x180012677  xor     esi, esi
0x180012679  mov     r14, r8
0x18001267c  mov     r13, rdx
0x18001267f  mov     r12, rcx
0x180012682  inc     rbp
0x180012685  cmp     [rcx+rbp], sil
0x180012689  jnz     short loc_180012682
0x18001268b  mov     edx, 1; Size
0x180012690  mov     rax, r14
0x180012693  add     rbp, rdx
0x180012696  not     rax
0x180012699  cmp     rbp, rax
0x18001269c  jbe     short loc_1800126BE
0x18001269e  lea     eax, [rdx+0Bh]
0x1800126a1  mov     rbx, [rsp+58h+arg_0]
0x1800126a6  mov     rbp, [rsp+58h+arg_8]
0x1800126ab  mov     rsi, [rsp+58h+arg_10]
0x1800126b0  add     rsp, 30h
0x1800126b4  pop     r15
0x1800126b6  pop     r14
0x1800126b8  pop     r13
0x1800126ba  pop     r12
0x1800126bc  pop     rdi
0x1800126bd  retn
0x1800126be  lea     r15, [r8+1]
0x1800126c2  add     r15, rbp
0x1800126c5  mov     rcx, r15; Count
0x1800126c8  call    _calloc_base
0x1800126cd  mov     rbx, rax
0x1800126d0  test    r14, r14
0x1800126d3  jz      short loc_1800126EE
0x1800126d5  mov     r9, r14; MaxCount
0x1800126d8  mov     r8, r13; Source
0x1800126db  mov     rdx, r15; SizeInBytes
0x1800126de  mov     rcx, rax; Destination
0x1800126e1  call    strncpy_s
0x1800126e6  test    eax, eax
0x1800126e8  jnz     loc_1800127C6
0x1800126ee  sub     r15, r14
0x1800126f1  lea     rcx, [rbx+r14]; Destination
0x1800126f5  mov     rdx, r15; SizeInBytes
0x1800126f8  mov     r9, rbp; MaxCount
0x1800126fb  mov     r8, r12; Source
0x1800126fe  call    strncpy_s
0x180012703  test    eax, eax
0x180012705  jnz     loc_1800127C6
0x18001270b  mov     rcx, [rdi+8]
0x18001270f  lea     r15d, [rax+8]
0x180012713  mov     r14, [rdi+10h]
0x180012717  cmp     rcx, r14
0x18001271a  jnz     loc_1800127BD
0x180012720  cmp     [rdi], rsi
0x180012723  jnz     short loc_180012750
0x180012725  mov     edx, r15d; Size
0x180012728  lea     ecx, [rax+4]; Count
0x18001272b  call    _calloc_base
0x180012730  xor     ecx, ecx; Block
0x180012732  mov     [rdi], rax
0x180012735  call    _free_base
0x18001273a  mov     rcx, [rdi]
0x18001273d  test    rcx, rcx
0x180012740  jz      short loc_180012784
0x180012742  lea     rax, [rcx+20h]
0x180012746  mov     [rdi+8], rcx
0x18001274a  mov     [rdi+10h], rax
0x18001274e  jmp     short loc_1800127BD
0x180012750  sub     r14, [rdi]
0x180012753  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001275d  sar     r14, 3
0x180012761  cmp     r14, rax
0x180012764  ja      short loc_180012784
0x180012766  mov     rcx, [rdi]; Block
0x180012769  lea     rbp, [r14+r14]
0x18001276d  mov     rdx, rbp; Count
0x180012770  mov     r8, r15; Size
0x180012773  call    _recalloc_base
0x180012778  test    rax, rax
0x18001277b  jnz     short loc_18001279F
0x18001277d  xor     ecx, ecx; Block
0x18001277f  call    _free_base
0x180012784  mov     rcx, rbx; Block
0x180012787  call    _free_base
0x18001278c  mov     esi, 0Ch
0x180012791  xor     ecx, ecx; Block
0x180012793  call    _free_base
0x180012798  mov     eax, esi
0x18001279a  jmp     loc_1800126A1
0x18001279f  lea     rcx, [rax+r14*8]
0x1800127a3  mov     [rdi], rax
0x1800127a6  mov     [rdi+8], rcx
0x1800127aa  lea     rcx, [rax+rbp*8]
0x1800127ae  mov     [rdi+10h], rcx
0x1800127b2  xor     ecx, ecx; Block
0x1800127b4  call    _free_base
0x1800127b9  mov     rcx, [rdi+8]
0x1800127bd  mov     [rcx], rbx
0x1800127c0  add     [rdi+8], r15
0x1800127c4  jmp     short loc_180012791
0x1800127c6  xor     r9d, r9d; LineNo
0x1800127c9  mov     [rsp+58h+Reserved], rsi; Reserved
0x1800127ce  xor     r8d, r8d; FileName
0x1800127d1  xor     edx, edx; FunctionName
0x1800127d3  xor     ecx, ecx; Expression
0x1800127d5  call    _invoke_watson
```
