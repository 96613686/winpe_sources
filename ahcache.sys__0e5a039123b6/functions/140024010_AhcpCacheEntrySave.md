# AhcpCacheEntrySave

- ea: `0x140024010`
- end: `0x1400244d6`
- name: `AhcpCacheEntrySave`
- size: `1222`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007b40`
- `0x140007e40`
- `0x140024010`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024125`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024281`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400243e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024125`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024281`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400243e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024079`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400240c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400241cd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002421a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024331`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024383`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024079`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400240c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400241cd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002421a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024331`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024383`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024096`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400240e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400241ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024237`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024353`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400243a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024096`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400240e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400241ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024237`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024353`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400243a6`

## string_xrefs

- `0x1400244aa`: `AhcpCacheEntrySave`
- `0x140024453`: `Failed to write custom data [%x]`
- `0x140024475`: `Failed to write custom data size. [%x]`
- `0x140024497`: `Failed to write file time [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntrySave(__int64 a1, _QWORD *a2)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 v4; // rax
  unsigned __int64 v6; // rdx
  POOL_TYPE v7; // r15d
  __int64 v8; // rsi
  _QWORD *v9; // r14
  void *v10; // r12
  SIZE_T v11; // rsi
  KIRQL v12; // al
  POOL_TYPE v13; // ecx
  PVOID v14; // rax
  void *v15; // rbp
  KIRQL CurrentIrql; // al
  POOL_TYPE v17; // ecx
  PVOID PoolWithTag; // rax
  size_t v19; // r8
  unsigned __int64 *v20; // rcx
  int v21; // eax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  _QWORD *v25; // r12
  __int64 v26; // rsi
  SIZE_T v27; // rsi
  KIRQL v28; // al
  POOL_TYPE v29; // ecx
  PVOID v30; // rax
  void *v31; // rbp
  KIRQL v32; // al
  POOL_TYPE v33; // ecx
  PVOID v34; // rax
  size_t v35; // r8
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rax
  size_t v38; // r12
  unsigned int v39; // ebx
  size_t v40; // rax
  unsigned __int64 v41; // rcx
  int v42; // eax
  const void *v43; // rax
  __int64 v44; // rsi
  void *v45; // r13
  SIZE_T v46; // rsi
  PVOID v47; // rax
  void *v48; // rbp
  PVOID v49; // rax
  size_t v50; // r8
  size_t v51; // rcx
  size_t v52; // rax
  unsigned int v53; // ecx
  const char *v54; // r9
  __int64 v55; // r8
  size_t Size; // [rsp+70h] [rbp+8h]
  void *Sizea; // [rsp+70h] [rbp+8h]
  size_t Sizeb; // [rsp+70h] [rbp+8h]
  size_t v60; // [rsp+78h] [rbp+10h]
  size_t v61; // [rsp+78h] [rbp+10h]

  v2 = a2 + 4;
  v4 = a2[4];
  v6 = v4 + 8;
  if ( v4 + 8 < v4 )
  {
    v21 = -1073741811;
    goto LABEL_75;
  }
  v7 = 512;
  if ( v6 > a2[2] )
  {
    v8 = a2[3] - 1LL;
    if ( v8 + v6 < v6 )
    {
LABEL_73:
      v21 = -1073741675;
      goto LABEL_75;
    }
    v9 = a2 + 5;
    v10 = (void *)a2[5];
    v11 = (v8 + v6) & ~v8;
    if ( v10 )
    {
      Size = a2[1];
      CurrentIrql = KeGetCurrentIrql();
      v17 = 512;
      if ( CurrentIrql != 2 )
        v17 = PagedPool;
      PoolWithTag = ExAllocatePoolWithTag(v17, v11, 0x7274534Du);
      v15 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, v11);
        v19 = v11;
        if ( Size < v11 )
          v19 = Size;
        memmove(v15, v10, v19);
        ExFreePoolWithTag(v10, 0x7274534Du);
        goto LABEL_15;
      }
    }
    else
    {
      v12 = KeGetCurrentIrql();
      v13 = 512;
      if ( v12 != 2 )
        v13 = PagedPool;
      v14 = ExAllocatePoolWithTag(v13, v11, 0x7274534Du);
      v15 = v14;
      if ( v14 )
      {
        memset(v14, 0, v11);
LABEL_15:
        *v9 = v15;
        v20 = a2 + 4;
        a2[2] = v11;
        goto LABEL_18;
      }
    }
    v21 = -1073741801;
LABEL_75:
    v54 = "Failed to write file time [%x]";
    v55 = 1579;
    goto LABEL_76;
  }
  v9 = a2 + 5;
  v20 = v2;
LABEL_18:
  *(_QWORD *)(*v9 + *v20) = *(_QWORD *)(a1 + 8);
  v22 = *v2 + 8;
  if ( v22 < *v2 )
  {
    *v2 = -1;
    goto LABEL_73;
  }
  *v2 = v22;
  v23 = a2[1];
  if ( v23 <= v22 )
    v23 = v22;
  a2[1] = v23;
  v24 = *v2 + 4;
  if ( v24 < *v2 )
  {
    v21 = -1073741811;
    goto LABEL_71;
  }
  v25 = v9;
  if ( v24 > a2[2] )
  {
    v26 = a2[3] - 1LL;
    if ( v26 + v24 < v24 )
    {
LABEL_69:
      v21 = -1073741675;
      goto LABEL_71;
    }
    v25 = a2 + 5;
    v27 = (v26 + v24) & ~v26;
    Sizea = (void *)a2[5];
    if ( Sizea )
    {
      v60 = a2[1];
      v32 = KeGetCurrentIrql();
      v33 = 512;
      if ( v32 != 2 )
        v33 = PagedPool;
      v34 = ExAllocatePoolWithTag(v33, v27, 0x7274534Du);
      v31 = v34;
      if ( v34 )
      {
        memset(v34, 0, v27);
        v35 = v27;
        if ( v60 < v27 )
          v35 = v60;
        memmove(v31, Sizea, v35);
        ExFreePoolWithTag(Sizea, 0x7274534Du);
        goto LABEL_35;
      }
    }
    else
    {
      v28 = KeGetCurrentIrql();
      v29 = 512;
      if ( v28 != 2 )
        v29 = PagedPool;
      v30 = ExAllocatePoolWithTag(v29, v27, 0x7274534Du);
      v31 = v30;
      if ( v30 )
      {
        memset(v30, 0, v27);
LABEL_35:
        *v25 = v31;
        a2[2] = v27;
        goto LABEL_36;
      }
    }
    v21 = -1073741801;
LABEL_71:
    v54 = "Failed to write custom data size. [%x]";
    v55 = 1585;
LABEL_76:
    v39 = v21;
    AslLogCallPrintf(1, "AhcpCacheEntrySave", v55, v54, v21);
    return v39;
  }
LABEL_36:
  *(_DWORD *)(*v25 + *v2) = *(_DWORD *)(a1 + 16);
  v36 = *v2 + 4;
  if ( v36 < *v2 )
  {
    *v2 = -1;
    goto LABEL_69;
  }
  *v2 = v36;
  v37 = a2[1];
  if ( v37 <= v36 )
    v37 = v36;
  a2[1] = v37;
  v38 = *(unsigned int *)(a1 + 16);
  if ( !*(_DWORD *)(a1 + 16) )
    return 0;
  v40 = a2[4];
  v41 = v40 + v38;
  if ( v40 + v38 < v40 )
  {
    v42 = -1073741811;
LABEL_66:
    v39 = v42;
    v53 = v42;
    goto LABEL_67;
  }
  v43 = *(const void **)(a1 + 24);
  v61 = (size_t)v43;
  if ( v41 > a2[2] )
  {
    v44 = a2[3] - 1LL;
    if ( v44 + v41 < v41 )
    {
      v39 = -1073741675;
LABEL_64:
      v53 = v39;
LABEL_67:
      AslLogCallPrintf(1, "AhcpCacheEntrySave", 1591, "Failed to write custom data [%x]", v53);
      return v39;
    }
    v45 = (void *)*v9;
    v46 = (v44 + v41) & ~v44;
    if ( *v9 )
    {
      Sizeb = a2[1];
      if ( KeGetCurrentIrql() != 2 )
        v7 = PagedPool;
      v49 = ExAllocatePoolWithTag(v7, v46, 0x7274534Du);
      v48 = v49;
      if ( v49 )
      {
        memset(v49, 0, v46);
        v50 = v46;
        if ( Sizeb < v46 )
          v50 = Sizeb;
        memmove(v48, v45, v50);
        ExFreePoolWithTag(v45, 0x7274534Du);
        goto LABEL_58;
      }
    }
    else
    {
      if ( KeGetCurrentIrql() != 2 )
        v7 = PagedPool;
      v47 = ExAllocatePoolWithTag(v7, v46, 0x7274534Du);
      v48 = v47;
      if ( v47 )
      {
        memset(v47, 0, v46);
LABEL_58:
        v43 = (const void *)v61;
        *v9 = v48;
        a2[2] = v46;
        goto LABEL_59;
      }
    }
    v39 = -1073741801;
    goto LABEL_64;
  }
LABEL_59:
  memmove((void *)(*v2 + *v9), v43, v38);
  v51 = *v2 + v38;
  if ( v51 < *v2 )
  {
    a2[4] = -1;
    v42 = -1073741675;
    goto LABEL_66;
  }
  a2[4] = v51;
  v52 = a2[1];
  if ( v52 <= v51 )
    v52 = v51;
  a2[1] = v52;
  return 0;
}

```

## disassembly

```asm
0x140024010  mov     [rsp+arg_10], rbx
0x140024015  push    rbp
0x140024016  push    rsi
0x140024017  push    rdi
0x140024018  push    r12
0x14002401a  push    r13
0x14002401c  push    r14
0x14002401e  push    r15
0x140024020  sub     rsp, 30h
0x140024024  lea     rdi, [rdx+20h]
0x140024028  mov     rbx, rdx
0x14002402b  mov     rax, [rdi]
0x14002402e  mov     r13, rcx
0x140024031  mov     ebp, 1
0x140024036  lea     rdx, [rax+8]
0x14002403a  cmp     rdx, rax
0x14002403d  jb      loc_140024492
0x140024043  mov     r15d, 200h
0x140024049  cmp     rdx, [rbx+10h]
0x14002404d  jbe     loc_14002414D
0x140024053  mov     rsi, [rbx+18h]
0x140024057  dec     rsi
0x14002405a  lea     rax, [rsi+rdx]
0x14002405e  cmp     rax, rdx
0x140024061  jb      loc_14002448B
0x140024067  not     rsi
0x14002406a  lea     r14, [rbx+28h]
0x14002406e  mov     r12, [r14]
0x140024071  and     rsi, rax
0x140024074  test    r12, r12
0x140024077  jnz     short loc_1400240BD
0x140024079  call    cs:__imp_KeGetCurrentIrql
0x140024080  nop     dword ptr [rax+rax+00h]
0x140024085  mov     ecx, r15d
0x140024088  mov     r8d, 7274534Dh; Tag
0x14002408e  cmp     al, 2
0x140024090  mov     rdx, rsi; NumberOfBytes
0x140024093  cmovnz  ecx, ebp; PoolType
0x140024096  call    cs:__imp_ExAllocatePoolWithTag
0x14002409d  nop     dword ptr [rax+rax+00h]
0x1400240a2  mov     rbp, rax
0x1400240a5  test    rax, rax
0x1400240a8  jz      loc_140024143
0x1400240ae  mov     r8, rsi; Size
0x1400240b1  xor     edx, edx; Val
0x1400240b3  mov     rcx, rax; void *
0x1400240b6  call    memset
0x1400240bb  jmp     short loc_140024131
0x1400240bd  mov     rax, [rbx+8]
0x1400240c1  mov     [rsp+68h+Size], rax
0x1400240c6  call    cs:__imp_KeGetCurrentIrql
0x1400240cd  nop     dword ptr [rax+rax+00h]
0x1400240d2  mov     ecx, r15d
0x1400240d5  mov     r8d, 7274534Dh; Tag
0x1400240db  cmp     al, 2
0x1400240dd  mov     rdx, rsi; NumberOfBytes
0x1400240e0  cmovnz  ecx, ebp; PoolType
0x1400240e3  call    cs:__imp_ExAllocatePoolWithTag
0x1400240ea  nop     dword ptr [rax+rax+00h]
0x1400240ef  mov     rbp, rax
0x1400240f2  test    rax, rax
0x1400240f5  jz      short loc_140024143
0x1400240f7  mov     r8, rsi; Size
0x1400240fa  xor     edx, edx; Val
0x1400240fc  mov     rcx, rax; void *
0x1400240ff  call    memset
0x140024104  cmp     [rsp+68h+Size], rsi
0x140024109  mov     r8, rsi
0x14002410c  mov     rdx, r12; Src
0x14002410f  mov     rcx, rbp; void *
0x140024112  cmovb   r8, [rsp+68h+Size]; Size
0x140024118  call    memmove
0x14002411d  mov     edx, 7274534Dh; Tag
0x140024122  mov     rcx, r12; P
0x140024125  call    cs:__imp_ExFreePoolWithTag
0x14002412c  nop     dword ptr [rax+rax+00h]
0x140024131  mov     [r14], rbp
0x140024134  lea     rcx, [rbx+20h]
0x140024138  mov     ebp, 1
0x14002413d  mov     [rbx+10h], rsi
0x140024141  jmp     short loc_140024154
0x140024143  mov     eax, 0C0000017h
0x140024148  jmp     loc_140024497
0x14002414d  lea     r14, [rbx+28h]
0x140024151  mov     rcx, rdi
0x140024154  mov     rcx, [rcx]
0x140024157  mov     rax, [r13+8]
0x14002415b  mov     rdx, [r14]
0x14002415e  mov     [rdx+rcx], rax
0x140024162  mov     rax, [rdi]
0x140024165  lea     rcx, [rax+8]
0x140024169  cmp     rcx, rax
0x14002416c  jb      loc_140024484
0x140024172  mov     [rdi], rcx
0x140024175  mov     rax, [rbx+8]
0x140024179  cmp     rax, rcx
0x14002417c  cmovbe  rax, rcx
0x140024180  mov     [rbx+8], rax
0x140024184  mov     rax, [rdi]
0x140024187  lea     rcx, [rax+4]
0x14002418b  cmp     rcx, rax
0x14002418e  jb      loc_140024470
0x140024194  mov     r12, r14
0x140024197  cmp     rcx, [rbx+10h]
0x14002419b  jbe     loc_140024295
0x1400241a1  mov     rsi, [rbx+18h]
0x1400241a5  dec     rsi
0x1400241a8  lea     rax, [rsi+rcx]
0x1400241ac  cmp     rax, rcx
0x1400241af  jb      loc_140024469
0x1400241b5  not     rsi
0x1400241b8  lea     r12, [rbx+28h]
0x1400241bc  and     rsi, rax
0x1400241bf  mov     rax, [r12]
0x1400241c3  mov     [rsp+68h+Size], rax
0x1400241c8  test    rax, rax
0x1400241cb  jnz     short loc_140024211
0x1400241cd  call    cs:__imp_KeGetCurrentIrql
0x1400241d4  nop     dword ptr [rax+rax+00h]
0x1400241d9  mov     ecx, r15d
0x1400241dc  mov     r8d, 7274534Dh; Tag
0x1400241e2  cmp     al, 2
0x1400241e4  mov     rdx, rsi; NumberOfBytes
0x1400241e7  cmovnz  ecx, ebp; PoolType
0x1400241ea  call    cs:__imp_ExAllocatePoolWithTag
0x1400241f1  nop     dword ptr [rax+rax+00h]
0x1400241f6  mov     rbp, rax
0x1400241f9  test    rax, rax
0x1400241fc  jz      loc_1400242D5
0x140024202  mov     r8, rsi; Size
0x140024205  xor     edx, edx; Val
0x140024207  mov     rcx, rax; void *
0x14002420a  call    memset
0x14002420f  jmp     short loc_14002428D
0x140024211  mov     rax, [rbx+8]
0x140024215  mov     [rsp+68h+arg_8], rax
0x14002421a  call    cs:__imp_KeGetCurrentIrql
0x140024221  nop     dword ptr [rax+rax+00h]
0x140024226  mov     ecx, r15d
0x140024229  mov     r8d, 7274534Dh; Tag
0x14002422f  cmp     al, 2
0x140024231  mov     rdx, rsi; NumberOfBytes
0x140024234  cmovnz  ecx, ebp; PoolType
0x140024237  call    cs:__imp_ExAllocatePoolWithTag
0x14002423e  nop     dword ptr [rax+rax+00h]
0x140024243  mov     rbp, rax
0x140024246  test    rax, rax
0x140024249  jz      loc_1400242D5
0x14002424f  mov     r8, rsi; Size
0x140024252  xor     edx, edx; Val
0x140024254  mov     rcx, rax; void *
0x140024257  call    memset
0x14002425c  cmp     [rsp+68h+arg_8], rsi
0x140024261  mov     r8, rsi
0x140024264  mov     rdx, [rsp+68h+Size]; Src
0x140024269  mov     rcx, rbp; void *
0x14002426c  cmovb   r8, [rsp+68h+arg_8]; Size
0x140024272  call    memmove
0x140024277  mov     rcx, [rsp+68h+Size]; P
0x14002427c  mov     edx, 7274534Dh; Tag
0x140024281  call    cs:__imp_ExFreePoolWithTag
0x140024288  nop     dword ptr [rax+rax+00h]
0x14002428d  mov     [r12], rbp
0x140024291  mov     [rbx+10h], rsi
0x140024295  mov     rcx, [rdi]
0x140024298  mov     eax, [r13+10h]
0x14002429c  mov     rdx, [r12]
0x1400242a0  mov     [rdx+rcx], eax
0x1400242a3  mov     rax, [rdi]
0x1400242a6  lea     rcx, [rax+4]
0x1400242aa  cmp     rcx, rax
0x1400242ad  jb      loc_140024462
0x1400242b3  mov     [rdi], rcx
0x1400242b6  mov     rax, [rbx+8]
0x1400242ba  cmp     rax, rcx
0x1400242bd  cmovbe  rax, rcx
0x1400242c1  mov     [rbx+8], rax
0x1400242c5  mov     r12d, [r13+10h]
0x1400242c9  test    r12, r12
0x1400242cc  jnz     short loc_1400242DF
0x1400242ce  xor     ebx, ebx
0x1400242d0  jmp     loc_1400244BB
0x1400242d5  mov     eax, 0C0000017h
0x1400242da  jmp     loc_140024475
0x1400242df  mov     rax, [rbx+20h]
0x1400242e3  lea     rcx, [rax+r12]
0x1400242e7  cmp     rcx, rax
0x1400242ea  jnb     short loc_1400242F6
0x1400242ec  mov     eax, 0C000000Dh
0x1400242f1  jmp     loc_14002444B
0x1400242f6  mov     rax, [r13+18h]
0x1400242fa  mov     [rsp+68h+arg_8], rax
0x1400242ff  cmp     rcx, [rbx+10h]
0x140024303  jbe     loc_140024400
0x140024309  mov     rsi, [rbx+18h]
0x14002430d  dec     rsi
0x140024310  lea     rax, [rsi+rcx]
0x140024314  cmp     rax, rcx
0x140024317  jnb     short loc_140024323
0x140024319  mov     ebx, 0C0000095h
0x14002431e  jmp     loc_14002443A
0x140024323  mov     r13, [r14]
0x140024326  not     rsi
0x140024329  and     rsi, rax
0x14002432c  test    r13, r13
0x14002432f  jnz     short loc_14002437A
0x140024331  call    cs:__imp_KeGetCurrentIrql
0x140024338  nop     dword ptr [rax+rax+00h]
0x14002433d  mov     r8d, 7274534Dh; Tag
0x140024343  mov     rdx, rsi; NumberOfBytes
0x140024346  cmp     al, 2
0x140024348  lea     eax, [r13+1]
0x14002434c  cmovnz  r15d, eax
0x140024350  mov     ecx, r15d; PoolType
0x140024353  call    cs:__imp_ExAllocatePoolWithTag
0x14002435a  nop     dword ptr [rax+rax+00h]
0x14002435f  mov     rbp, rax
0x140024362  test    rax, rax
0x140024365  jz      loc_140024435
0x14002436b  mov     r8, rsi; Size
0x14002436e  xor     edx, edx; Val
0x140024370  mov     rcx, rax; void *
0x140024373  call    memset
0x140024378  jmp     short loc_1400243F4
0x14002437a  mov     rax, [rbx+8]
0x14002437e  mov     [rsp+68h+Size], rax
0x140024383  call    cs:__imp_KeGetCurrentIrql
0x14002438a  nop     dword ptr [rax+rax+00h]
0x14002438f  mov     r8d, 7274534Dh; Tag
0x140024395  mov     rdx, rsi; NumberOfBytes
0x140024398  cmp     al, 2
0x14002439a  mov     eax, 1
0x14002439f  cmovnz  r15d, eax
0x1400243a3  mov     ecx, r15d; PoolType
0x1400243a6  call    cs:__imp_ExAllocatePoolWithTag
0x1400243ad  nop     dword ptr [rax+rax+00h]
0x1400243b2  mov     rbp, rax
0x1400243b5  test    rax, rax
0x1400243b8  jz      short loc_140024435
0x1400243ba  mov     r8, rsi; Size
0x1400243bd  xor     edx, edx; Val
0x1400243bf  mov     rcx, rax; void *
0x1400243c2  call    memset
0x1400243c7  cmp     [rsp+68h+Size], rsi
0x1400243cc  mov     r8, rsi
0x1400243cf  mov     rdx, r13; Src
0x1400243d2  mov     rcx, rbp; void *
0x1400243d5  cmovb   r8, [rsp+68h+Size]; Size
0x1400243db  call    memmove
0x1400243e0  mov     edx, 7274534Dh; Tag
0x1400243e5  mov     rcx, r13; P
0x1400243e8  call    cs:__imp_ExFreePoolWithTag
0x1400243ef  nop     dword ptr [rax+rax+00h]
0x1400243f4  mov     rax, [rsp+68h+arg_8]
0x1400243f9  mov     [r14], rbp
0x1400243fc  mov     [rbx+10h], rsi
0x140024400  mov     rcx, [r14]
0x140024403  mov     r8, r12; Size
0x140024406  add     rcx, [rdi]; void *
0x140024409  mov     rdx, rax; Src
0x14002440c  call    memmove
0x140024411  mov     rax, [rdi]
0x140024414  lea     rcx, [rax+r12]
0x140024418  cmp     rcx, rax
0x14002441b  jb      short loc_14002443E
0x14002441d  mov     [rbx+20h], rcx
0x140024421  mov     rax, [rbx+8]
0x140024425  cmp     rax, rcx
0x140024428  cmovbe  rax, rcx
0x14002442c  mov     [rbx+8], rax
0x140024430  jmp     loc_1400242CE
0x140024435  mov     ebx, 0C0000017h
0x14002443a  mov     ecx, ebx
0x14002443c  jmp     short loc_14002444F
0x14002443e  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x140024446  mov     eax, 0C0000095h
0x14002444b  mov     ebx, eax
0x14002444d  mov     ecx, eax
0x14002444f  mov     [rsp+68h+var_48], ecx
0x140024453  lea     r9, aFailedToWriteC_0; "Failed to write custom data [%x]"
0x14002445a  mov     r8d, 637h
0x140024460  jmp     short loc_1400244AA
0x140024462  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140024469  mov     eax, 0C0000095h
0x14002446e  jmp     short loc_140024475
0x140024470  mov     eax, 0C000000Dh
0x140024475  lea     r9, aFailedToWriteC_1; "Failed to write custom data size. [%x]"
0x14002447c  mov     r8d, 631h
0x140024482  jmp     short loc_1400244A4
0x140024484  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002448b  mov     eax, 0C0000095h
0x140024490  jmp     short loc_140024497
0x140024492  mov     eax, 0C000000Dh
0x140024497  lea     r9, aFailedToWriteF_1; "Failed to write file time [%x]"
0x14002449e  mov     r8d, 62Bh
0x1400244a4  mov     [rsp+68h+var_48], eax
0x1400244a8  mov     ebx, eax
0x1400244aa  lea     rdx, aAhcpcacheentry_6; "AhcpCacheEntrySave"
0x1400244b1  mov     ecx, 1
0x1400244b6  call    AslLogCallPrintf
  ... truncated ...
```
