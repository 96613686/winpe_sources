# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,unsigned __int64,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x14001da84`
- end: `0x14001dc0a`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001d684`

## callees

- `0x1400160bc`
- `0x140019930`
- `0x14001b910`
- `0x14001d520`
- `0x14001da84`
- `0x14001ef20`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer<wchar_t>(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  unsigned __int64 v10; // rbp
  size_t v12; // r15
  char *v13; // rax
  char *v14; // rbx
  char *v15; // r14
  char *v16; // rax
  unsigned __int64 v17; // r14
  char *v18; // rax

  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v10 = v4 + 1;
  if ( v10 > ~a3 )
    return 12;
  v12 = v10 + a3 + 1;
  v13 = (char *)calloc_base(v12, 2u);
  v14 = v13;
  if ( a3 && (unsigned int)sub_14001D520(v13, v12, a2, a3)
    || (unsigned int)sub_14001D520(&v14[2 * a3], v12 - a3, a1, v10) )
  {
    invoke_watson(0, 0, 0, 0, 0);
  }
  v15 = (char *)a4[2];
  if ( a4[1] != v15 )
    goto LABEL_17;
  if ( *a4 )
  {
    v17 = (v15 - (_BYTE *)*a4) >> 3;
    if ( v17 <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v18 = (char *)recalloc_base(*a4, 2 * v17, 8u);
      if ( v18 )
      {
        *a4 = v18;
        a4[1] = &v18[8 * v17];
        a4[2] = &v18[16 * v17];
        free_base(0);
        goto LABEL_17;
      }
      free_base(0);
    }
  }
  else
  {
    *a4 = calloc_base(4u, 8u);
    free_base(0);
    v16 = (char *)*a4;
    if ( *a4 )
    {
      a4[1] = v16;
      a4[2] = v16 + 32;
LABEL_17:
      *(_QWORD *)a4[1] = v14;
      a4[1] = (char *)a4[1] + 8;
      goto LABEL_18;
    }
  }
  v6 = 12;
  free_base(v14);
LABEL_18:
  free_base(0);
  return v6;
}

```

## disassembly

```asm
0x14001da84  mov     [rsp+arg_0], rbx
0x14001da89  mov     [rsp+arg_8], rbp
0x14001da8e  mov     [rsp+arg_10], rsi
0x14001da93  push    rdi
0x14001da94  push    r12
0x14001da96  push    r13
0x14001da98  push    r14
0x14001da9a  push    r15
0x14001da9c  sub     rsp, 30h
0x14001daa0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001daa4  mov     rsi, r9
0x14001daa7  xor     edi, edi
0x14001daa9  mov     r14, r8
0x14001daac  mov     r13, rdx
0x14001daaf  mov     r12, rcx
0x14001dab2  inc     rbp
0x14001dab5  cmp     [rcx+rbp*2], di
0x14001dab9  jnz     short loc_14001DAB2
0x14001dabb  mov     rax, r14
0x14001dabe  inc     rbp
0x14001dac1  not     rax
0x14001dac4  cmp     rbp, rax
0x14001dac7  jbe     short loc_14001DAEB
0x14001dac9  mov     eax, 0Ch
0x14001dace  mov     rbx, [rsp+58h+arg_0]
0x14001dad3  mov     rbp, [rsp+58h+arg_8]
0x14001dad8  mov     rsi, [rsp+58h+arg_10]
0x14001dadd  add     rsp, 30h
0x14001dae1  pop     r15
0x14001dae3  pop     r14
0x14001dae5  pop     r13
0x14001dae7  pop     r12
0x14001dae9  pop     rdi
0x14001daea  retn
0x14001daeb  lea     r15, [r8+1]
0x14001daef  mov     edx, 2; Size
0x14001daf4  add     r15, rbp
0x14001daf7  mov     rcx, r15; Count
0x14001dafa  call    _calloc_base
0x14001daff  mov     rbx, rax
0x14001db02  test    r14, r14
0x14001db05  jz      short loc_14001DB20
0x14001db07  mov     r9, r14
0x14001db0a  mov     r8, r13
0x14001db0d  mov     rdx, r15
0x14001db10  mov     rcx, rax
0x14001db13  call    sub_14001D520
0x14001db18  test    eax, eax
0x14001db1a  jnz     loc_14001DBF5
0x14001db20  sub     r15, r14
0x14001db23  lea     rcx, [rbx+r14*2]
0x14001db27  mov     rdx, r15
0x14001db2a  mov     r9, rbp
0x14001db2d  mov     r8, r12
0x14001db30  call    sub_14001D520
0x14001db35  test    eax, eax
0x14001db37  jnz     loc_14001DBF5
0x14001db3d  mov     r14, [rsi+10h]
0x14001db41  lea     r15d, [rax+8]
0x14001db45  cmp     [rsi+8], r14
0x14001db49  jnz     loc_14001DBDC
0x14001db4f  cmp     [rsi], rdi
0x14001db52  jnz     short loc_14001DB7F
0x14001db54  mov     edx, r15d; Size
0x14001db57  lea     ecx, [rax+4]; Count
0x14001db5a  call    _calloc_base
0x14001db5f  xor     ecx, ecx; Block
0x14001db61  mov     [rsi], rax
0x14001db64  call    _free_base
0x14001db69  mov     rax, [rsi]
0x14001db6c  test    rax, rax
0x14001db6f  jz      short loc_14001DBB3
0x14001db71  mov     [rsi+8], rax
0x14001db75  add     rax, 20h ; ' '
0x14001db79  mov     [rsi+10h], rax
0x14001db7d  jmp     short loc_14001DBDC
0x14001db7f  sub     r14, [rsi]
0x14001db82  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001db8c  sar     r14, 3
0x14001db90  cmp     r14, rax
0x14001db93  ja      short loc_14001DBB3
0x14001db95  mov     rcx, [rsi]; Block
0x14001db98  lea     rbp, [r14+r14]
0x14001db9c  mov     rdx, rbp; Count
0x14001db9f  mov     r8, r15; Size
0x14001dba2  call    _recalloc_base
0x14001dba7  test    rax, rax
0x14001dbaa  jnz     short loc_14001DBC2
0x14001dbac  xor     ecx, ecx; Block
0x14001dbae  call    _free_base
0x14001dbb3  mov     rcx, rbx; Block
0x14001dbb6  mov     edi, 0Ch
0x14001dbbb  call    _free_base
0x14001dbc0  jmp     short loc_14001DBE7
0x14001dbc2  lea     rcx, [rax+r14*8]
0x14001dbc6  mov     [rsi], rax
0x14001dbc9  mov     [rsi+8], rcx
0x14001dbcd  lea     rcx, [rax+rbp*8]
0x14001dbd1  mov     [rsi+10h], rcx
0x14001dbd5  xor     ecx, ecx; Block
0x14001dbd7  call    _free_base
0x14001dbdc  mov     rcx, [rsi+8]
0x14001dbe0  mov     [rcx], rbx
0x14001dbe3  add     [rsi+8], r15
0x14001dbe7  xor     ecx, ecx; Block
0x14001dbe9  call    _free_base
0x14001dbee  mov     eax, edi
0x14001dbf0  jmp     loc_14001DACE
0x14001dbf5  xor     r9d, r9d; LineNo
0x14001dbf8  mov     [rsp+58h+Reserved], rdi; Reserved
0x14001dbfd  xor     r8d, r8d; FileName
0x14001dc00  xor     edx, edx; FunctionName
0x14001dc02  xor     ecx, ecx; Expression
0x14001dc04  call    _invoke_watson
```
