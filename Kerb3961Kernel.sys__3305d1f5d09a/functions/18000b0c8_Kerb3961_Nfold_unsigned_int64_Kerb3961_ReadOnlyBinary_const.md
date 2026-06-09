# Kerb3961::Nfold(unsigned __int64,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000b0c8`
- end: `0x18000b2f8`
- name: `?Nfold@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_KAEBUReadOnlyBinary@1@@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800041a0`

## callees

- `0x180003a38`
- `0x180003a54`
- `0x180005b1c`
- `0x18000b0c8`
- `0x1800118cc`
- `0x180011b40`
- `0x180012300`

## string_xrefs

- `0x18000b2eb`: `One's complement addition should not wrap more than once`

## pseudocode

```c
__int64 __fastcall Kerb3961::Nfold(__int64 a1, size_t a2, size_t *a3)
{
  size_t v3; // rsi
  size_t v4; // rdi
  const void *v5; // r12
  __int64 v6; // r15
  size_t v7; // rax
  size_t v8; // r8
  size_t v9; // rdx
  size_t v10; // rcx
  size_t v11; // rbp
  int v12; // r8d
  int v13; // ebx
  void *v14; // rcx
  _BYTE *v15; // r14
  const unsigned __int16 *v16; // rdx
  size_t v17; // r12
  char *v18; // r9
  unsigned __int8 v19; // r8
  char v20; // cl
  size_t v21; // r8
  unsigned __int16 v22; // ax
  size_t v23; // rdx
  size_t v24; // rdx
  size_t v26; // [rsp+20h] [rbp-58h] BYREF
  void *v27; // [rsp+28h] [rbp-50h]
  char *v28; // [rsp+30h] [rbp-48h]
  unsigned __int16 v31; // [rsp+88h] [rbp+10h]

  v3 = *a3;
  v4 = a2;
  v5 = (const void *)a3[1];
  v6 = a1;
  if ( *a3 <= a2 )
  {
    v7 = a2;
    v8 = *a3;
  }
  else
  {
    v7 = *a3;
    v8 = a2;
  }
  v9 = v7 % v8;
  while ( 1 )
  {
    v10 = v9;
    if ( !v9 )
      break;
    v9 = v8 % v9;
    v8 = v10;
  }
  v11 = v3 * (v4 / v8);
  Kerb3961::MakeBuffer(&v26);
  v13 = (int)v28;
  if ( (int)v28 >= 0 )
  {
    v15 = v27;
    memmove(v27, v5, v3);
    v17 = v3;
    if ( v3 < v11 )
    {
      do
      {
        memmove(&v15[v17], &v15[v17 - 1 % v3], 1 % v3);
        memmove(&v15[1 % v3 + v17], &v15[v17 - v3], v3 - 1 % v3);
        v16 = 0;
        v18 = &v15[v17];
        v19 = v15[v17 - 1 + v3];
        do
        {
          v20 = 8 * v19;
          v19 = *((_BYTE *)v16 + (_QWORD)v18);
          *((_BYTE *)v16 + (_QWORD)v18) = v20 | (v19 >> 5);
          v16 = (const unsigned __int16 *)((char *)v16 + 1);
        }
        while ( (unsigned __int64)v16 < v3 );
        v17 += v3;
      }
      while ( v17 < v11 );
      v4 = a2;
      v6 = a1;
    }
    if ( v4 < v11 )
    {
      if ( !v4 )
        Kerb3961::ConsistencyFail((Kerb3961 *)L"Integers must be at least one byte in AccumulateOnes", v16);
      v21 = v4;
      do
      {
        v22 = 0;
        v23 = v4;
        do
        {
          --v23;
          v31 = (unsigned __int8)v15[v23] + HIBYTE(v22) + (unsigned __int8)v15[v21 + v23];
          v22 = v31;
          v15[v23] = v31;
        }
        while ( v23 );
        v24 = v4;
        while ( 1 )
        {
          v31 = HIBYTE(v31) + (unsigned __int8)v15[--v24];
          v15[v24] = v31;
          if ( !HIBYTE(v31) )
            break;
          if ( !v24 )
            Kerb3961::ConsistencyFail((Kerb3961 *)L"One's complement addition should not wrap more than once", 0);
        }
        v21 += v4;
      }
      while ( v21 < v11 );
    }
    v26 = v4;
    v27 = v15;
    Kerb3961::CopyBuffer(v6, &v26);
    if ( v15 )
    {
      v14 = v15;
LABEL_27:
      Kerb3961Free(v14);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"scratchBuffer",
      (const char *)(unsigned int)v28,
      v12);
    v14 = v27;
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = v13;
    if ( v14 )
      goto LABEL_27;
  }
  return v6;
}

```

## disassembly

```asm
0x18000b0c8  mov     [rsp+arg_18], rbx
0x18000b0cd  mov     [rsp+arg_8], rdx
0x18000b0d2  mov     [rsp+arg_0], rcx
0x18000b0d7  push    rbp
0x18000b0d8  push    rsi
0x18000b0d9  push    rdi
0x18000b0da  push    r12
0x18000b0dc  push    r13
0x18000b0de  push    r14
0x18000b0e0  push    r15
0x18000b0e2  sub     rsp, 40h
0x18000b0e6  mov     rsi, [r8]
0x18000b0e9  mov     rdi, rdx
0x18000b0ec  mov     r12, [r8+8]
0x18000b0f0  mov     r15, rcx
0x18000b0f3  cmp     rsi, rdx
0x18000b0f6  jbe     short loc_18000B100
0x18000b0f8  mov     rax, rsi
0x18000b0fb  mov     r8, rdx
0x18000b0fe  jmp     short loc_18000B106
0x18000b100  mov     rax, rdi
0x18000b103  mov     r8, rsi
0x18000b106  xor     edx, edx
0x18000b108  div     r8
0x18000b10b  jmp     short loc_18000B118
0x18000b10d  mov     rax, r8
0x18000b110  xor     edx, edx
0x18000b112  div     rcx
0x18000b115  mov     r8, rcx
0x18000b118  mov     rcx, rdx
0x18000b11b  test    rdx, rdx
0x18000b11e  jnz     short loc_18000B10D
0x18000b120  xor     edx, edx
0x18000b122  lea     rcx, [rsp+78h+var_58]
0x18000b127  mov     rax, rdi
0x18000b12a  div     r8
0x18000b12d  mov     rbp, rax
0x18000b130  imul    rbp, rsi
0x18000b134  mov     rdx, rbp
0x18000b137  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000b13c  mov     ebx, dword ptr [rsp+78h+var_48]
0x18000b140  test    ebx, ebx
0x18000b142  jns     short loc_18000B178
0x18000b144  mov     edx, ebx; char *
0x18000b146  lea     rcx, aScratchbuffer; "scratchBuffer"
0x18000b14d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000b152  mov     rcx, [rsp+78h+var_50]
0x18000b157  mov     qword ptr [r15], 0
0x18000b15e  mov     qword ptr [r15+8], 0
0x18000b166  mov     [r15+10h], ebx
0x18000b16a  test    rcx, rcx
0x18000b16d  jz      loc_18000B2C2
0x18000b173  jmp     loc_18000B2BD
0x18000b178  mov     r14, [rsp+78h+var_50]
0x18000b17d  mov     r8, rsi; Size
0x18000b180  mov     rcx, r14; void *
0x18000b183  mov     rdx, r12; Src
0x18000b186  call    memmove
0x18000b18b  mov     r12, rsi
0x18000b18e  cmp     rsi, rbp
0x18000b191  jnb     loc_18000B220
0x18000b197  xor     edx, edx
0x18000b199  mov     r15, rsi
0x18000b19c  lea     eax, [rdx+1]
0x18000b19f  div     rsi
0x18000b1a2  mov     r13, rdx
0x18000b1a5  sub     r15, rdx
0x18000b1a8  lea     rdi, [r14+rdx]
0x18000b1ac  mov     rbx, r12
0x18000b1af  lea     rcx, [r12+r14]; void *
0x18000b1b3  sub     rbx, rsi
0x18000b1b6  mov     r8, r13; Size
0x18000b1b9  add     rbx, r14
0x18000b1bc  mov     rdx, rbx
0x18000b1bf  sub     rdx, r13
0x18000b1c2  add     rdx, rsi; Src
0x18000b1c5  call    memmove
0x18000b1ca  lea     rcx, [rdi+r12]; void *
0x18000b1ce  mov     r8, r15; Size
0x18000b1d1  mov     rdx, rbx; Src
0x18000b1d4  call    memmove
0x18000b1d9  xor     edx, edx
0x18000b1db  lea     r9, [r12+r14]
0x18000b1df  mov     r8b, [rsi+r9-1]
0x18000b1e4  test    rsi, rsi
0x18000b1e7  jz      short loc_18000B208
0x18000b1e9  shl     r8b, 3
0x18000b1ed  mov     cl, r8b
0x18000b1f0  mov     r8b, [r9+rdx]
0x18000b1f4  mov     al, r8b
0x18000b1f7  shr     al, 5
0x18000b1fa  or      al, cl
0x18000b1fc  mov     [r9+rdx], al
0x18000b200  inc     rdx; unsigned __int16 *
0x18000b203  cmp     rdx, rsi
0x18000b206  jb      short loc_18000B1E9
0x18000b208  add     r12, rsi
0x18000b20b  cmp     r12, rbp
0x18000b20e  jb      short loc_18000B1AC
0x18000b210  mov     rdi, [rsp+78h+arg_8]
0x18000b218  mov     r15, [rsp+78h+arg_0]
0x18000b220  cmp     rdi, rbp
0x18000b223  jnb     short loc_18000B29E
0x18000b225  test    rdi, rdi
0x18000b228  jz      loc_18000B2DE
0x18000b22e  mov     r8, rdi
0x18000b231  lea     r9, [r8+r14]
0x18000b235  xor     eax, eax
0x18000b237  mov     rdx, rdi
0x18000b23a  dec     rdx
0x18000b23d  shr     ax, 8
0x18000b241  movzx   ecx, byte ptr [r9+rdx]
0x18000b246  add     cx, ax
0x18000b249  movzx   eax, byte ptr [r14+rdx]
0x18000b24e  add     cx, ax
0x18000b251  mov     word ptr [rsp+78h+arg_8], cx
0x18000b259  movzx   eax, cx
0x18000b25c  mov     [r14+rdx], cl
0x18000b260  test    rdx, rdx
0x18000b263  jnz     short loc_18000B23A
0x18000b265  mov     rdx, rdi
0x18000b268  movzx   ecx, byte ptr [rsp+78h+arg_8+1]
0x18000b270  dec     rdx; unsigned __int16 *
0x18000b273  movzx   eax, byte ptr [r14+rdx]
0x18000b278  add     ax, cx
0x18000b27b  mov     word ptr [rsp+78h+arg_8], ax
0x18000b283  mov     [r14+rdx], al
0x18000b287  shr     ax, 8
0x18000b28b  test    al, al
0x18000b28d  jz      short loc_18000B296
0x18000b28f  test    rdx, rdx
0x18000b292  jz      short loc_18000B2EB
0x18000b294  jmp     short loc_18000B268
0x18000b296  add     r8, rdi
0x18000b299  cmp     r8, rbp
0x18000b29c  jb      short loc_18000B231
0x18000b29e  lea     rdx, [rsp+78h+var_58]
0x18000b2a3  mov     [rsp+78h+var_58], rdi
0x18000b2a8  mov     rcx, r15
0x18000b2ab  mov     [rsp+78h+var_50], r14
0x18000b2b0  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000b2b5  test    r14, r14
0x18000b2b8  jz      short loc_18000B2C2
0x18000b2ba  mov     rcx, r14
0x18000b2bd  call    Kerb3961Free
0x18000b2c2  mov     rbx, [rsp+78h+arg_18]
0x18000b2ca  mov     rax, r15
0x18000b2cd  add     rsp, 40h
0x18000b2d1  pop     r15
0x18000b2d3  pop     r14
0x18000b2d5  pop     r13
0x18000b2d7  pop     r12
0x18000b2d9  pop     rdi
0x18000b2da  pop     rsi
0x18000b2db  pop     rbp
0x18000b2dc  retn
0x18000b2de  lea     rcx, aIntegersMustBe; "Integers must be at least one byte in A"...
0x18000b2e5  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
0x18000b2eb  lea     rcx, aOneSComplement; "One's complement addition should not wr"...
0x18000b2f2  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
