# Kerb3961::Nfold(unsigned __int64,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000e320`
- end: `0x18000e551`
- name: `?Nfold@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_KAEBUReadOnlyBinary@1@@Z`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a34c`
- `0x18001a538`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x1800033f4`
- `0x18000712c`
- `0x18000901c`
- `0x18000e320`
- `0x18001d360`

## string_xrefs

- `0x18000e544`: `One's complement addition should not wrap more than once`

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
    memcpy_0(v27, v5, v3);
    v17 = v3;
    if ( v3 < v11 )
    {
      do
      {
        memcpy_0(&v15[v17], &v15[v17 - 1 % v3], 1 % v3);
        memcpy_0(&v15[1 % v3 + v17], &v15[v17 - v3], v3 - 1 % v3);
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
          v31 = (unsigned __int8)v15[--v24] + HIBYTE(v31);
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
      operator delete(v14, 0);
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
0x18000e320  mov     [rsp+arg_18], rbx
0x18000e325  mov     [rsp+arg_8], rdx
0x18000e32a  mov     [rsp+arg_0], rcx
0x18000e32f  push    rbp
0x18000e330  push    rsi
0x18000e331  push    rdi
0x18000e332  push    r12
0x18000e334  push    r13
0x18000e336  push    r14
0x18000e338  push    r15
0x18000e33a  sub     rsp, 40h
0x18000e33e  mov     rsi, [r8]
0x18000e341  mov     rdi, rdx
0x18000e344  mov     r12, [r8+8]
0x18000e348  mov     r15, rcx
0x18000e34b  cmp     rsi, rdx
0x18000e34e  jbe     short loc_18000E358
0x18000e350  mov     rax, rsi
0x18000e353  mov     r8, rdx
0x18000e356  jmp     short loc_18000E35E
0x18000e358  mov     rax, rdi
0x18000e35b  mov     r8, rsi
0x18000e35e  xor     edx, edx
0x18000e360  div     r8
0x18000e363  jmp     short loc_18000E370
0x18000e365  mov     rax, r8
0x18000e368  xor     edx, edx
0x18000e36a  div     rcx
0x18000e36d  mov     r8, rcx
0x18000e370  mov     rcx, rdx
0x18000e373  test    rdx, rdx
0x18000e376  jnz     short loc_18000E365
0x18000e378  xor     edx, edx
0x18000e37a  lea     rcx, [rsp+78h+var_58]
0x18000e37f  mov     rax, rdi
0x18000e382  div     r8
0x18000e385  mov     rbp, rax
0x18000e388  imul    rbp, rsi
0x18000e38c  mov     rdx, rbp
0x18000e38f  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000e394  mov     ebx, dword ptr [rsp+78h+var_48]
0x18000e398  test    ebx, ebx
0x18000e39a  jns     short loc_18000E3D0
0x18000e39c  mov     edx, ebx; char *
0x18000e39e  lea     rcx, aScratchbuffer; "scratchBuffer"
0x18000e3a5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e3aa  mov     rcx, [rsp+78h+var_50]
0x18000e3af  mov     qword ptr [r15], 0
0x18000e3b6  mov     qword ptr [r15+8], 0
0x18000e3be  mov     [r15+10h], ebx
0x18000e3c2  test    rcx, rcx
0x18000e3c5  jz      loc_18000E51C
0x18000e3cb  jmp     loc_18000E515
0x18000e3d0  mov     r14, [rsp+78h+var_50]
0x18000e3d5  mov     r8, rsi; Size
0x18000e3d8  mov     rcx, r14; void *
0x18000e3db  mov     rdx, r12; Src
0x18000e3de  call    memcpy_0
0x18000e3e3  mov     r12, rsi
0x18000e3e6  cmp     rsi, rbp
0x18000e3e9  jnb     loc_18000E478
0x18000e3ef  xor     edx, edx
0x18000e3f1  mov     r15, rsi
0x18000e3f4  lea     eax, [rdx+1]
0x18000e3f7  div     rsi
0x18000e3fa  mov     r13, rdx
0x18000e3fd  sub     r15, rdx
0x18000e400  lea     rdi, [r14+rdx]
0x18000e404  mov     rbx, r12
0x18000e407  lea     rcx, [r12+r14]; void *
0x18000e40b  sub     rbx, rsi
0x18000e40e  mov     r8, r13; Size
0x18000e411  add     rbx, r14
0x18000e414  mov     rdx, rbx
0x18000e417  sub     rdx, r13
0x18000e41a  add     rdx, rsi; Src
0x18000e41d  call    memcpy_0
0x18000e422  lea     rcx, [rdi+r12]; void *
0x18000e426  mov     r8, r15; Size
0x18000e429  mov     rdx, rbx; Src
0x18000e42c  call    memcpy_0
0x18000e431  xor     edx, edx
0x18000e433  lea     r9, [r12+r14]
0x18000e437  mov     r8b, [rsi+r9-1]
0x18000e43c  test    rsi, rsi
0x18000e43f  jz      short loc_18000E460
0x18000e441  shl     r8b, 3
0x18000e445  mov     cl, r8b
0x18000e448  mov     r8b, [r9+rdx]
0x18000e44c  mov     al, r8b
0x18000e44f  shr     al, 5
0x18000e452  or      al, cl
0x18000e454  mov     [r9+rdx], al
0x18000e458  inc     rdx; unsigned __int16 *
0x18000e45b  cmp     rdx, rsi
0x18000e45e  jb      short loc_18000E441
0x18000e460  add     r12, rsi
0x18000e463  cmp     r12, rbp
0x18000e466  jb      short loc_18000E404
0x18000e468  mov     rdi, [rsp+78h+arg_8]
0x18000e470  mov     r15, [rsp+78h+arg_0]
0x18000e478  cmp     rdi, rbp
0x18000e47b  jnb     short loc_18000E4F6
0x18000e47d  test    rdi, rdi
0x18000e480  jz      loc_18000E537
0x18000e486  mov     r8, rdi
0x18000e489  lea     r9, [r8+r14]
0x18000e48d  xor     eax, eax
0x18000e48f  mov     rdx, rdi
0x18000e492  dec     rdx
0x18000e495  shr     ax, 8
0x18000e499  movzx   ecx, byte ptr [r9+rdx]
0x18000e49e  add     cx, ax
0x18000e4a1  movzx   eax, byte ptr [r14+rdx]
0x18000e4a6  add     cx, ax
0x18000e4a9  mov     word ptr [rsp+78h+arg_8], cx
0x18000e4b1  movzx   eax, cx
0x18000e4b4  mov     [r14+rdx], cl
0x18000e4b8  test    rdx, rdx
0x18000e4bb  jnz     short loc_18000E492
0x18000e4bd  mov     rdx, rdi
0x18000e4c0  movzx   eax, byte ptr [rsp+78h+arg_8+1]
0x18000e4c8  dec     rdx; unsigned __int16 *
0x18000e4cb  movzx   ecx, byte ptr [r14+rdx]
0x18000e4d0  add     ax, cx
0x18000e4d3  mov     word ptr [rsp+78h+arg_8], ax
0x18000e4db  mov     [r14+rdx], al
0x18000e4df  shr     ax, 8
0x18000e4e3  test    al, al
0x18000e4e5  jz      short loc_18000E4EE
0x18000e4e7  test    rdx, rdx
0x18000e4ea  jz      short loc_18000E544
0x18000e4ec  jmp     short loc_18000E4C0
0x18000e4ee  add     r8, rdi
0x18000e4f1  cmp     r8, rbp
0x18000e4f4  jb      short loc_18000E489
0x18000e4f6  lea     rdx, [rsp+78h+var_58]
0x18000e4fb  mov     [rsp+78h+var_58], rdi
0x18000e500  mov     rcx, r15
0x18000e503  mov     [rsp+78h+var_50], r14
0x18000e508  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000e50d  test    r14, r14
0x18000e510  jz      short loc_18000E51C
0x18000e512  mov     rcx, r14; void *
0x18000e515  xor     edx, edx; struct std::nothrow_t *
0x18000e517  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e51c  mov     rbx, [rsp+78h+arg_18]
0x18000e524  mov     rax, r15
0x18000e527  add     rsp, 40h
0x18000e52b  pop     r15
0x18000e52d  pop     r14
0x18000e52f  pop     r13
0x18000e531  pop     r12
0x18000e533  pop     rdi
0x18000e534  pop     rsi
0x18000e535  pop     rbp
0x18000e536  retn
0x18000e537  lea     rcx, aIntegersMustBe; "Integers must be at least one byte in A"...
0x18000e53e  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
0x18000e544  lea     rcx, aOneSComplement; "One's complement addition should not wr"...
0x18000e54b  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
