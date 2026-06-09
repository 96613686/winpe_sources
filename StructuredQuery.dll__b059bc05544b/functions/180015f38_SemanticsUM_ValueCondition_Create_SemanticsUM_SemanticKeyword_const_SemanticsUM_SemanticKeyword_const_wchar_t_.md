# SemanticsUM::ValueCondition::Create(SemanticsUM::SemanticKeyword const &,SemanticsUM::SemanticKeyword const &,wchar_t const *,int,int,SemanticsUM::CompoundCondition *,SemanticsUM::Entity const *,wchar_t const *,ulong,SemanticsUM::ValueCondition * *)

- ea: `0x180015f38`
- end: `0x180016357`
- name: `?Create@ValueCondition@SemanticsUM@@SAJAEBVSemanticKeyword@2@0PEB_WHHPEAVCompoundCondition@2@PEBVEntity@2@1KPEAPEAV12@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(const struct SemanticsUM::SemanticKeyword *, const struct SemanticsUM::SemanticKeyword *, const wchar_t *, int, int, struct CompoundCondition *, const struct SemanticsUM::Entity *, const wchar_t *, unsigned int, struct SemanticsUM::ValueCondition **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001455c`

## callees

- `0x180015f38`
- `0x18005db64`
- `0x18005e740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001628b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001628b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016077`

## pseudocode

```c
__int64 __fastcall SemanticsUM::ValueCondition::Create(
        const struct SemanticsUM::SemanticKeyword *a1,
        const struct SemanticsUM::SemanticKeyword *a2,
        const wchar_t *a3,
        int a4,
        int a5,
        struct CompoundCondition *a6,
        const struct SemanticsUM::Entity *a7,
        const wchar_t *a8,
        unsigned int a9,
        struct SemanticsUM::ValueCondition **a10)
{
  unsigned __int64 v10; // r13
  _QWORD *v11; // r15
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // rdi
  _WORD *v14; // rsi
  unsigned int v15; // ebx
  const size_t *v16; // r12
  const size_t *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  _WORD *v20; // r8
  __int64 v21; // r10
  _WORD *v22; // rcx
  __int64 v23; // r9
  unsigned __int64 v24; // r14
  _WORD *v25; // rdi
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  _WORD *v28; // rax
  __int64 v29; // r8
  _WORD *v30; // rcx
  __int64 v31; // r9
  _QWORD *v32; // rax
  __int64 v33; // rcx
  __int128 v34; // xmm1
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 result; // rax
  __int64 v39; // rdi
  bool v40; // cf
  __int64 v41; // r14

  v10 = -1;
  v11 = 0;
  v12 = -1;
  do
    ++v12;
  while ( a8[v12] );
  v13 = v12 + 1;
  if ( v12 + 1 < v12 || !is_mul_ok(v13, 2u) )
  {
    v15 = -2147024362;
    goto LABEL_36;
  }
  v14 = CoTaskMemAlloc(2 * v13);
  v15 = v14 == 0 ? 0x8007000E : 0;
  if ( v14 )
  {
    v16 = &cchOriginalDestLength;
    if ( v13 > 0x7FFFFFFF )
      goto LABEL_46;
    if ( v12 < 0x7FFFFFFF )
    {
      v17 = &cchOriginalDestLength;
      v18 = v12 & -(__int64)(a8 != 0);
      if ( a8 )
        v17 = (const size_t *)a8;
      v19 = v12 + 1;
      v20 = v14;
      v21 = 0;
      do
      {
        if ( !v18 )
          break;
        if ( !*(_WORD *)v17 )
          break;
        *v20 = *(_WORD *)v17;
        v17 = (const size_t *)((char *)v17 + 2);
        ++v20;
        --v18;
        ++v21;
        --v19;
      }
      while ( v19 );
      v22 = v20 - 1;
      v23 = v21 - 1;
      if ( v19 )
      {
        v22 = v20;
        v23 = v21;
      }
      *v22 = 0;
      if ( v19 )
      {
        v40 = v13 == v23;
        v39 = v13 - v23;
        if ( !v40 && v39 != 1 && (unsigned __int64)(2 * v39) > 2 )
          memset_0(&v14[v23 + 1], 0, 2 * v39 - 2);
      }
      goto LABEL_17;
    }
    if ( v12 != -1 )
LABEL_46:
      *v14 = 0;
    do
LABEL_17:
      ++v10;
    while ( a3[v10] );
    v24 = v10 + 1;
    if ( v10 + 1 < v10 || !is_mul_ok(v24, 2u) )
    {
      v15 = -2147024362;
      goto LABEL_35;
    }
    v25 = CoTaskMemAlloc(2 * v24);
    v15 = v25 == 0 ? 0x8007000E : 0;
    if ( !v25 )
    {
LABEL_35:
      CoTaskMemFree(v14);
      goto LABEL_36;
    }
    if ( v24 > 0x7FFFFFFF )
      goto LABEL_48;
    if ( v10 < 0x7FFFFFFF )
    {
      v26 = v10 & -(__int64)(a3 != 0);
      if ( a3 )
        v16 = (const size_t *)a3;
      v27 = v10 + 1;
      v28 = v25;
      v29 = 0;
      do
      {
        if ( !v26 )
          break;
        if ( !*(_WORD *)v16 )
          break;
        *v28 = *(_WORD *)v16;
        v16 = (const size_t *)((char *)v16 + 2);
        ++v28;
        --v26;
        ++v29;
        --v27;
      }
      while ( v27 );
      v30 = v28 - 1;
      v31 = v29 - 1;
      if ( v27 )
      {
        v30 = v28;
        v31 = v29;
      }
      *v30 = 0;
      if ( v27 )
      {
        v40 = v24 == v31;
        v41 = v24 - v31;
        if ( !v40 && v41 != 1 && (unsigned __int64)(2 * v41) > 2 )
          memset_0(&v25[v31 + 1], 0, 2 * v41 - 2);
      }
      goto LABEL_32;
    }
    if ( v10 != -1 )
LABEL_48:
      *v25 = 0;
LABEL_32:
    v32 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v32;
    if ( v32 )
    {
      v32[1] = SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::SemanticCondition'};
      v32[17] = &SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::IValueCondition'};
      v32[14] = &SemanticsUM::ISemanticCondition::`vftable';
      v32[16] = &SemanticsUM::IEntityCondition::`vftable';
      *(_QWORD *)((char *)v32 + *(int *)(v32[17] + 4LL) + 136) = &SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
      *v32 = &SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::SemanticCondition'};
      *(_QWORD *)((char *)v32 + *(int *)(v32[1] + 4LL) + 8) = &SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
      v33 = *(int *)(v32[1] + 4LL);
      *(_DWORD *)((char *)v32 + v33 + 4) = v33 - 72;
      *((_OWORD *)v32 + 1) = *(_OWORD *)a1;
      v34 = *(_OWORD *)a2;
      v32[6] = a6;
      *((_DWORD *)v32 + 16) = a4;
      *((_DWORD *)v32 + 17) = a5;
      *v32 = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::SemanticCondition'};
      v35 = v32[1];
      v11[7] = 0;
      *((_OWORD *)v11 + 2) = v34;
      *(_QWORD *)((char *)v11 + *(int *)(v35 + 4) + 8) = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
      *(_QWORD *)((char *)v11 + *(int *)(v11[1] + 8LL) + 8) = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::IValueCondition'};
      v36 = *(int *)(v11[1] + 4LL);
      *(_DWORD *)((char *)v11 + v36 + 4) = v36 - 104;
      v37 = *(int *)(v11[1] + 8LL);
      *(_DWORD *)((char *)v11 + v37 + 4) = v37 - 120;
      v11[10] = a7;
      *((_DWORD *)v11 + 24) = a9;
      v11[9] = v25;
      v11[11] = v14;
      goto LABEL_36;
    }
    v11 = 0;
    CoTaskMemFree(v25);
    v15 = -2147024882;
    goto LABEL_35;
  }
LABEL_36:
  result = v15;
  *a10 = (struct SemanticsUM::ValueCondition *)v11;
  return result;
}

```

## disassembly

```asm
0x180015f38  mov     rax, rsp
0x180015f3b  mov     [rax+20h], r9d
0x180015f3f  mov     [rax+18h], r8
0x180015f43  mov     [rax+10h], rdx
0x180015f47  mov     [rax+8], rcx
0x180015f4b  push    rbx
0x180015f4c  push    rbp
0x180015f4d  push    rsi
0x180015f4e  push    rdi
0x180015f4f  push    r12
0x180015f51  push    r13
0x180015f53  push    r14
0x180015f55  push    r15
0x180015f57  sub     rsp, 38h
0x180015f5b  mov     r14, [rsp+78h+arg_38]
0x180015f63  xor     r8d, r8d
0x180015f66  or      r13, 0FFFFFFFFFFFFFFFFh
0x180015f6a  mov     r15d, r8d
0x180015f6d  mov     rbp, r13
0x180015f70  inc     rbp
0x180015f73  cmp     [r14+rbp*2], r8w
0x180015f78  jnz     short loc_180015F70
0x180015f7a  lea     rdi, [rbp+1]
0x180015f7e  cmp     rdi, rbp
0x180015f81  jb      loc_1800162AF
0x180015f87  mov     eax, 2
0x180015f8c  mul     rdi
0x180015f8f  test    rdx, rdx
0x180015f92  jnz     loc_1800162AF
0x180015f98  mov     rcx, rax; cb
0x180015f9b  call    cs:__imp_CoTaskMemAlloc
0x180015fa1  mov     rsi, rax
0x180015fa4  neg     rax
0x180015fa7  sbb     ebx, ebx
0x180015fa9  xor     r11d, r11d
0x180015fac  not     ebx
0x180015fae  and     ebx, 8007000Eh
0x180015fb4  test    rsi, rsi
0x180015fb7  jz      loc_180016291
0x180015fbd  mov     eax, 7FFFFFFFh
0x180015fc2  lea     r12, cchOriginalDestLength
0x180015fc9  cmp     rdi, rax
0x180015fcc  ja      loc_18001633C
0x180015fd2  cmp     rbp, rax
0x180015fd5  jnb     loc_180016333
0x180015fdb  mov     rax, r14
0x180015fde  neg     rax
0x180015fe1  mov     rax, r12
0x180015fe4  sbb     rcx, rcx
0x180015fe7  and     rcx, rbp
0x180015fea  test    r14, r14
0x180015fed  cmovnz  rax, r14
0x180015ff1  test    rdi, rdi
0x180015ff4  jz      short loc_180016043
0x180015ff6  mov     rdx, rdi
0x180015ff9  mov     r8, rsi
0x180015ffc  mov     r10d, r11d
0x180015fff  test    rcx, rcx
0x180016002  jz      short loc_180016026
0x180016004  movzx   r9d, word ptr [rax]
0x180016008  test    r9w, r9w
0x18001600c  jz      short loc_180016026
0x18001600e  mov     [r8], r9w
0x180016012  add     rax, 2
0x180016016  add     r8, 2
0x18001601a  dec     rcx
0x18001601d  inc     r10
0x180016020  sub     rdx, 1
0x180016024  jnz     short loc_180015FFF
0x180016026  test    rdx, rdx
0x180016029  lea     rcx, [r8-2]
0x18001602d  lea     r9, [r10-1]
0x180016031  cmovnz  rcx, r8
0x180016035  cmovnz  r9, r10
0x180016039  mov     [rcx], r11w
0x18001603d  jnz     loc_1800162B6
0x180016043  mov     rbp, [rsp+78h+arg_10]
0x18001604b  inc     r13
0x18001604e  cmp     [rbp+r13*2+0], r11w
0x180016054  jnz     short loc_18001604B
0x180016056  lea     r14, [r13+1]
0x18001605a  cmp     r14, r13
0x18001605d  jb      loc_180016279
0x180016063  mov     eax, 2
0x180016068  mul     r14
0x18001606b  test    rdx, rdx
0x18001606e  jnz     loc_180016279
0x180016074  mov     rcx, rax; cb
0x180016077  call    cs:__imp_CoTaskMemAlloc
0x18001607d  mov     rdi, rax
0x180016080  neg     rax
0x180016083  sbb     ebx, ebx
0x180016085  xor     r10d, r10d
0x180016088  not     ebx
0x18001608a  and     ebx, 8007000Eh
0x180016090  test    rdi, rdi
0x180016093  jz      loc_180016280
0x180016099  mov     eax, 7FFFFFFFh
0x18001609e  cmp     r14, rax
0x1800160a1  ja      loc_18001634E
0x1800160a7  cmp     r13, rax
0x1800160aa  jnb     loc_180016345
0x1800160b0  mov     rax, rbp
0x1800160b3  neg     rax
0x1800160b6  sbb     rcx, rcx
0x1800160b9  and     rcx, r13
0x1800160bc  test    rbp, rbp
0x1800160bf  cmovnz  r12, rbp
0x1800160c3  test    r14, r14
0x1800160c6  jz      short loc_180016116
0x1800160c8  mov     rdx, r14
0x1800160cb  mov     rax, rdi
0x1800160ce  mov     r8d, r10d
0x1800160d1  test    rcx, rcx
0x1800160d4  jz      short loc_1800160F9
0x1800160d6  movzx   r9d, word ptr [r12]
0x1800160db  test    r9w, r9w
0x1800160df  jz      short loc_1800160F9
0x1800160e1  mov     [rax], r9w
0x1800160e5  add     r12, 2
0x1800160e9  add     rax, 2
0x1800160ed  dec     rcx
0x1800160f0  inc     r8
0x1800160f3  sub     rdx, 1
0x1800160f7  jnz     short loc_1800160D1
0x1800160f9  test    rdx, rdx
0x1800160fc  lea     rcx, [rax-2]
0x180016100  lea     r9, [r8-1]
0x180016104  cmovnz  rcx, rax
0x180016108  cmovnz  r9, r8
0x18001610c  mov     [rcx], r10w
0x180016110  jnz     loc_1800162EB
0x180016116  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001611d  mov     ecx, 90h; unsigned __int64
0x180016122  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016127  xor     r8d, r8d
0x18001612a  mov     [rsp+78h+var_58], rax
0x18001612f  mov     r15, rax
0x180016132  test    rax, rax
0x180016135  jz      loc_18001631D
0x18001613b  lea     rax, ??_8ValueCondition@SemanticsUM@@7BSemanticCondition@1@@; const SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::SemanticCondition'}
0x180016142  mov     [r15+8], rax
0x180016146  lea     rax, ??_8ValueCondition@SemanticsUM@@7BIValueCondition@1@@; const SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::IValueCondition'}
0x18001614d  mov     [r15+88h], rax
0x180016154  lea     rax, ??_7ISemanticCondition@SemanticsUM@@6B@; const SemanticsUM::ISemanticCondition::`vftable'
0x18001615b  mov     [r15+70h], rax
0x18001615f  lea     rax, ??_7IEntityCondition@SemanticsUM@@6B@; const SemanticsUM::IEntityCondition::`vftable'
0x180016166  mov     [r15+80h], rax
0x18001616d  mov     rax, [r15+88h]
0x180016174  movsxd  rcx, dword ptr [rax+4]
0x180016178  lea     rax, ??_7ICompoundCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x18001617f  mov     [rcx+r15+88h], rax
0x180016187  lea     rax, ??_7SemanticCondition@SemanticsUM@@6B01@@; const SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::SemanticCondition'}
0x18001618e  mov     [r15], rax
0x180016191  mov     rax, [r15+8]
0x180016195  movsxd  rcx, dword ptr [rax+4]
0x180016199  lea     rax, ??_7SemanticCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x1800161a0  mov     [rcx+r15+8], rax
0x1800161a5  mov     rax, [r15+8]
0x1800161a9  movsxd  rcx, dword ptr [rax+4]
0x1800161ad  mov     rax, [rsp+78h+arg_0]
0x1800161b5  lea     edx, [rcx-48h]
0x1800161b8  mov     [rcx+r15+4], edx
0x1800161bd  movups  xmm0, xmmword ptr [rax]
0x1800161c0  mov     rax, [rsp+78h+arg_8]
0x1800161c8  movdqu  xmmword ptr [r15+10h], xmm0
0x1800161ce  movups  xmm1, xmmword ptr [rax]
0x1800161d1  mov     rax, [rsp+78h+arg_28]
0x1800161d9  mov     [r15+30h], rax
0x1800161dd  mov     eax, [rsp+78h+arg_18]
0x1800161e4  mov     [r15+40h], eax
0x1800161e8  mov     eax, [rsp+78h+arg_20]
0x1800161ef  mov     [r15+44h], eax
0x1800161f3  lea     rax, ??_7ValueCondition@SemanticsUM@@6BSemanticCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::SemanticCondition'}
0x1800161fa  mov     [r15], rax
0x1800161fd  mov     rax, [r15+8]
0x180016201  mov     [r15+38h], r8
0x180016205  movdqu  xmmword ptr [r15+20h], xmm1
0x18001620b  movsxd  rcx, dword ptr [rax+4]
0x18001620f  lea     rax, ??_7ValueCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x180016216  mov     [rcx+r15+8], rax
0x18001621b  mov     rax, [r15+8]
0x18001621f  movsxd  rcx, dword ptr [rax+8]
0x180016223  lea     rax, ??_7ValueCondition@SemanticsUM@@6BIValueCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::IValueCondition'}
0x18001622a  mov     [rcx+r15+8], rax
0x18001622f  mov     rax, [r15+8]
0x180016233  movsxd  rcx, dword ptr [rax+4]
0x180016237  lea     edx, [rcx-68h]
0x18001623a  mov     [rcx+r15+4], edx
0x18001623f  mov     rax, [r15+8]
0x180016243  movsxd  rcx, dword ptr [rax+8]
0x180016247  mov     rax, [rsp+78h+arg_30]
0x18001624f  lea     edx, [rcx-78h]
0x180016252  mov     [rcx+r15+4], edx
0x180016257  mov     [r15+50h], rax
0x18001625b  mov     eax, [rsp+78h+arg_40]
0x180016262  mov     [r15+60h], eax
0x180016266  mov     [r15+48h], rdi
0x18001626a  mov     [r15+58h], rsi
0x18001626e  test    r15, r15
0x180016271  jz      loc_180016320
0x180016277  jmp     short loc_180016291
0x180016279  mov     ebx, 80070216h
0x18001627e  jmp     short loc_180016288
0x180016280  test    ebx, ebx
0x180016282  jns     loc_180016116
0x180016288  mov     rcx, rsi; pv
0x18001628b  call    cs:__imp_CoTaskMemFree
0x180016291  mov     rcx, [rsp+78h+arg_48]
0x180016299  mov     eax, ebx
0x18001629b  mov     [rcx], r15
0x18001629e  add     rsp, 38h
0x1800162a2  pop     r15
0x1800162a4  pop     r14
0x1800162a6  pop     r13
0x1800162a8  pop     r12
0x1800162aa  pop     rdi
0x1800162ab  pop     rsi
0x1800162ac  pop     rbp
0x1800162ad  pop     rbx
0x1800162ae  retn
0x1800162af  mov     ebx, 80070216h
0x1800162b4  jmp     short loc_180016291
0x1800162b6  sub     rdi, r9
0x1800162b9  cmp     rdi, 1
0x1800162bd  jbe     loc_180016043
0x1800162c3  lea     r8, [rdi+rdi]
0x1800162c7  cmp     r8, 2
0x1800162cb  jbe     loc_180016043
0x1800162d1  inc     r9
0x1800162d4  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800162d8  xor     edx, edx; Val
0x1800162da  lea     rcx, [rsi+r9*2]; void *
0x1800162de  call    memset_0
0x1800162e3  xor     r11d, r11d
0x1800162e6  jmp     loc_180016043
0x1800162eb  sub     r14, r9
0x1800162ee  cmp     r14, 1
0x1800162f2  jbe     loc_180016116
0x1800162f8  lea     r8, [r14+r14]
0x1800162fc  cmp     r8, 2
0x180016300  jbe     loc_180016116
0x180016306  inc     r9
0x180016309  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001630d  xor     edx, edx; Val
0x18001630f  lea     rcx, [rdi+r9*2]; void *
0x180016313  call    memset_0
0x180016318  jmp     loc_180016116
0x18001631d  mov     r15, r8
0x180016320  mov     rcx, rdi; pv
0x180016323  call    cs:__imp_CoTaskMemFree
0x180016329  mov     ebx, 8007000Eh
0x18001632e  jmp     loc_180016288
0x180016333  test    rdi, rdi
0x180016336  jz      loc_180016043
0x18001633c  mov     [rsi], r11w
0x180016340  jmp     loc_180016043
0x180016345  test    r14, r14
0x180016348  jz      loc_180016116
0x18001634e  mov     [rdi], r10w
0x180016352  jmp     loc_180016116
```
