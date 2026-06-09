# PiiFilterEmbeddedPathsExecute

- ea: `0x180013144`
- end: `0x1800136ee`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1450`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800136f4`

## callees

- `0x180001f72`
- `0x18001301c`
- `0x180013094`
- `0x180013144`
- `0x180015c88`

## import_xrefs

- `msvcrt!wcschr` at `0x180013688`
- `msvcrt!wcschr` at `0x180013688`
- `msvcrt!iswspace` at `0x1800135e4`
- `msvcrt!iswspace` at `0x180013649`
- `msvcrt!iswspace` at `0x1800135e4`
- `msvcrt!iswspace` at `0x180013649`
- `ntdll!RtlFreeHeap` at `0x1800136b4`
- `ntdll!RtlFreeHeap` at `0x1800136d1`
- `ntdll!RtlFreeHeap` at `0x1800136b4`
- `ntdll!RtlFreeHeap` at `0x1800136d1`
- `ntdll!RtlAllocateHeap` at `0x180013182`
- `ntdll!RtlAllocateHeap` at `0x1800131b1`
- `ntdll!RtlAllocateHeap` at `0x180013182`
- `ntdll!RtlAllocateHeap` at `0x1800131b1`

## pseudocode

```c
__int64 __fastcall PiiFilterEmbeddedPathsExecute(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned __int16 *a4)
{
  signed int v7; // edi
  wchar_t *Heap; // rbp
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rcx
  _QWORD *v15; // r8
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  wchar_t **v18; // rax
  wchar_t *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  wchar_t **v24; // rax
  __int64 *v25; // rax
  __int64 v26; // r13
  unsigned __int16 *v27; // rdi
  __int64 v28; // rcx
  wchar_t *v29; // rax
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  __int64 v32; // r8
  wchar_t *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  __int64 v37; // rbx
  wchar_t *v38; // rax
  __int64 v39; // rcx
  unsigned __int16 *v40; // r8
  __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  wchar_t *v43; // rax
  wchar_t *v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int16 *v46; // rax
  wchar_t *v47; // rdx
  wchar_t *v48; // rcx
  wchar_t *i; // rax
  const wchar_t *v50; // rcx
  wchar_t v51; // dx
  unsigned __int16 *v52; // rdi
  const wchar_t *j; // rcx
  wint_t *v54; // rdi
  wint_t *v55; // rbx
  int v56; // esi
  unsigned __int16 v57; // ax
  BOOL v58; // eax
  char *v59; // rdi
  unsigned __int64 v60; // rcx
  wchar_t *v61; // rax
  __int64 v63; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp+18h]

  v63 = a2;
  SubStr = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( !SubStr )
    return (unsigned int)-1073741801;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( Heap )
  {
    v9 = 2147483646;
    v10 = 260;
    v11 = 2147483646;
    v12 = 260;
    v13 = a1;
    do
    {
      if ( !v11 )
        break;
      if ( !*a4 )
        break;
      *v13++ = *a4++;
      --v11;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v7 = v12 == 0 ? 0x80000005 : 0;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( !v12 )
      goto LABEL_112;
    v15 = (_QWORD *)a3[8];
    v16 = a3[2];
    if ( !(_QWORD *)((char *)v15 + v16) )
    {
LABEL_67:
      v46 = a1;
      v47 = Heap;
      do
      {
        if ( !v9 )
          break;
        if ( !*v46 )
          break;
        *v47++ = *v46++;
        --v9;
        --v10;
      }
      while ( v10 );
      v48 = v47 - 1;
      v7 = v10 == 0 ? 0x80000005 : 0;
      if ( v10 )
        v48 = v47;
      *v48 = 0;
      if ( v10 )
      {
        AslStringUpper(Heap, v47, v15, 0);
        for ( i = wcsstr_0(Heap, L"\\USERS\\"); i; i = wcsstr_0(v50, L"\\USERS\\") )
        {
          v50 = i + 7;
          v51 = i[7];
          if ( v51 )
          {
            v52 = &a1[v50 - Heap];
            do
            {
              if ( v51 == 92 )
                break;
              if ( v52 >= a1 + 260 )
                break;
              ++v50;
              *v52++ = 120;
              v51 = *v50;
            }
            while ( *v50 );
          }
        }
        for ( j = a1; ; j = v55 )
        {
          v61 = wcschr(j, 0x40u);
          if ( !v61 || !*v61 )
            break;
          v54 = v61 - 1;
          LODWORD(v63) = 0;
          v55 = v61 + 1;
          v56 = 0;
          v57 = v61[1];
          if ( v57 )
          {
            do
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(v57, 0, (int *)&v63) )
                break;
              if ( *v55 == 46 )
                v56 = 1;
              v57 = *++v55;
            }
            while ( *v55 );
          }
          v58 = iswspace(*v55) || !*v55 || *v55 == 62;
          if ( v56 && v58 )
          {
            --v55;
            LODWORD(v63) = 0;
            while ( v54 >= a1 )
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(*v54, 1, (int *)&v63) )
              {
                if ( *v54 != 60 && !iswspace(*v54) )
                  goto LABEL_109;
                break;
              }
              --v54;
            }
            if ( !(_DWORD)v63 )
            {
              v59 = (char *)(v54 + 1);
              v60 = (unsigned __int64)((char *)v55 - v59 + 2) >> 1;
              if ( v59 > (char *)v55 )
                v60 = 0;
              if ( v60 )
              {
                while ( v60 )
                {
                  *(_WORD *)v59 = 35;
                  v59 += 2;
                  --v60;
                }
              }
            }
          }
LABEL_109:
          ;
        }
        v7 = 0;
      }
      goto LABEL_112;
    }
    v17 = 0;
    LODWORD(v63) = 0;
    while ( v17 < v16 )
    {
      v15 = a3 + 5;
      if ( !is_mul_ok(a3[1], v17) || (v18 = (wchar_t **)(*v15 + a3[1] * v17), (unsigned __int64)v18 < *v15) )
        v18 = 0;
      v19 = *v18;
      if ( !is_mul_ok(a3[1], v17) || (v20 = (__int64 *)(*v15 + a3[1] * v17), (unsigned __int64)v20 < *v15) )
        v20 = 0;
      v21 = *v20;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
LABEL_36:
      v26 = v21 + 2 * v22;
      v27 = a1;
      v28 = 2147483646;
      v29 = Heap;
      v30 = 260;
      do
      {
        if ( !v28 )
          break;
        v15 = (_QWORD *)*v27;
        if ( !(_WORD)v15 )
          break;
        *v29 = (unsigned __int16)v15;
        ++v27;
        ++v29;
        --v28;
        --v30;
      }
      while ( v30 );
      v31 = v29 - 1;
      if ( v30 )
        v31 = v29;
      *v31 = 0;
      v7 = v30 == 0 ? 0x80000005 : 0;
      if ( !v30 )
        goto LABEL_112;
      AslStringUpper(Heap, v30, v15, 0);
      v33 = SubStr;
      v34 = 2147483646;
      v35 = 260;
      do
      {
        if ( !v34 )
          break;
        if ( !*v19 )
          break;
        *v33++ = *v19++;
        --v34;
        --v35;
      }
      while ( v35 );
      v36 = v33 - 1;
      if ( v35 )
        v36 = v33;
      *v36 = 0;
      v7 = v35 == 0 ? 0x80000005 : 0;
      if ( !v35 )
        goto LABEL_112;
      v37 = -1;
      do
        ++v37;
      while ( SubStr[v37] );
      if ( v37 && (AslStringUpper(SubStr, v35, v32, 0), (v38 = wcsstr_0(Heap, SubStr)) != 0) )
      {
        v39 = v38 - Heap;
        a1[v39] = 0;
        v40 = &a1[v39 + v37];
        if ( v40 >= a1 + 260 )
          goto LABEL_112;
        v41 = 2147483646;
        v42 = 260;
        v43 = Heap;
        do
        {
          if ( !v41 )
            break;
          if ( !*v40 )
            break;
          *v43++ = *v40++;
          --v41;
          --v42;
        }
        while ( v42 );
        v44 = v43 - 1;
        if ( v42 )
          v44 = v43;
        *v44 = 0;
        v7 = v42 == 0 ? 0x80000005 : 0;
        if ( !v42 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, v42, (const unsigned __int16 *)(v26 + 2));
        if ( v7 < 0 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, v45, Heap);
        if ( v7 < 0 )
          goto LABEL_112;
        v17 = (unsigned int)v63;
      }
      else
      {
        v17 = (unsigned int)(v63 + 1);
        LODWORD(v63) = v63 + 1;
      }
      v15 = (_QWORD *)a3[8];
      v16 = a3[2];
      if ( (unsigned int)v17 >= (unsigned __int64)v15 + v16 )
        goto LABEL_67;
    }
    v23 = v17 - v16;
    if ( v23 >= (unsigned __int64)v15 )
    {
      v19 = (wchar_t *)MEMORY[0];
    }
    else
    {
      if ( is_mul_ok(a3[7], v23) && (v24 = (wchar_t **)(a3[11] + a3[7] * v23), (unsigned __int64)v24 >= a3[11]) )
        v19 = *v24;
      else
        v19 = (wchar_t *)MEMORY[0];
      if ( is_mul_ok(a3[7], v23) )
      {
        v25 = (__int64 *)(a3[11] + a3[7] * v23);
        if ( (unsigned __int64)v25 >= a3[11] )
          goto LABEL_34;
      }
    }
    v25 = 0;
LABEL_34:
    v21 = *v25;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
    goto LABEL_36;
  }
  v7 = -1073741801;
LABEL_112:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SubStr);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013144  mov     [rsp+arg_0], rbx
0x180013149  mov     [rsp+arg_8], rdx
0x18001314e  push    rbp
0x18001314f  push    rsi
0x180013150  push    rdi
0x180013151  push    r12
0x180013153  push    r13
0x180013155  push    r14
0x180013157  push    r15
0x180013159  sub     rsp, 30h
0x18001315d  mov     r15, rcx
0x180013160  mov     r14, r8
0x180013163  mov     rcx, gs:60h
0x18001316c  mov     ebx, 208h
0x180013171  mov     esi, 8
0x180013176  mov     r8d, ebx; Size
0x180013179  mov     edx, esi; Flags
0x18001317b  mov     rdi, r9
0x18001317e  mov     rcx, [rcx+30h]; HeapHandle
0x180013182  call    cs:__imp_RtlAllocateHeap
0x180013188  mov     [rsp+68h+SubStr], rax
0x180013190  test    rax, rax
0x180013193  jnz     short loc_18001319F
0x180013195  mov     edi, 0C0000017h
0x18001319a  jmp     loc_1800136D7
0x18001319f  mov     rcx, gs:60h
0x1800131a8  mov     r8, rbx; Size
0x1800131ab  mov     edx, esi; Flags
0x1800131ad  mov     rcx, [rcx+30h]; HeapHandle
0x1800131b1  call    cs:__imp_RtlAllocateHeap
0x1800131b7  xor     r9d, r9d
0x1800131ba  mov     rbp, rax
0x1800131bd  test    rax, rax
0x1800131c0  jnz     short loc_1800131CC
0x1800131c2  mov     edi, 0C0000017h
0x1800131c7  jmp     loc_18001369D
0x1800131cc  mov     r12d, 7FFFFFFEh
0x1800131d2  mov     esi, 104h
0x1800131d7  mov     eax, r12d
0x1800131da  mov     edx, esi
0x1800131dc  mov     r8, r15
0x1800131df  mov     r10d, 1
0x1800131e5  test    rax, rax
0x1800131e8  jz      short loc_180013206
0x1800131ea  movzx   ecx, word ptr [rdi]
0x1800131ed  test    cx, cx
0x1800131f0  jz      short loc_180013206
0x1800131f2  mov     [r8], cx
0x1800131f6  add     rdi, 2
0x1800131fa  add     r8, 2
0x1800131fe  sub     rax, r10
0x180013201  sub     rdx, r10
0x180013204  jnz     short loc_1800131E5
0x180013206  mov     rax, rdx
0x180013209  lea     rcx, [r8-2]
0x18001320d  neg     rax
0x180013210  sbb     edi, edi
0x180013212  not     edi
0x180013214  and     edi, 80000005h
0x18001321a  test    rdx, rdx
0x18001321d  cmovnz  rcx, r8
0x180013221  mov     [rcx], r9w
0x180013225  jz      loc_18001369D
0x18001322b  mov     r8, [r14+40h]
0x18001322f  mov     rdx, [r14+10h]
0x180013233  lea     rax, [rdx+r8]
0x180013237  test    rax, rax
0x18001323a  jz      loc_1800134CE
0x180013240  mov     edi, r9d
0x180013243  mov     dword ptr [rsp+68h+arg_8], edi
0x180013247  cmp     rdi, rdx
0x18001324a  jnb     short loc_180013294
0x18001324c  mov     rax, rdi
0x18001324f  lea     r8, [r14+28h]
0x180013253  mul     qword ptr [r14+8]
0x180013257  test    rdx, rdx
0x18001325a  jnz     short loc_180013264
0x18001325c  add     rax, [r8]
0x18001325f  cmp     rax, [r8]
0x180013262  jnb     short loc_180013267
0x180013264  mov     rax, r9
0x180013267  mov     rbx, [rax]
0x18001326a  mov     rax, rdi
0x18001326d  mul     qword ptr [r14+8]
0x180013271  test    rdx, rdx
0x180013274  jnz     short loc_18001327E
0x180013276  add     rax, [r8]
0x180013279  cmp     rax, [r8]
0x18001327c  jnb     short loc_180013281
0x18001327e  mov     rax, r9
0x180013281  mov     rcx, [rax]
0x180013284  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013288  inc     rax
0x18001328b  cmp     [rcx+rax*2], r9w
0x180013290  jnz     short loc_180013288
0x180013292  jmp     short loc_1800132F3
0x180013294  sub     rdi, rdx
0x180013297  cmp     rdi, r8
0x18001329a  jnb     short loc_1800132D7
0x18001329c  mov     rax, rdi
0x18001329f  mul     qword ptr [r14+38h]
0x1800132a3  test    rdx, rdx
0x1800132a6  jnz     short loc_1800132B7
0x1800132a8  add     rax, [r14+58h]
0x1800132ac  cmp     rax, [r14+58h]
0x1800132b0  jb      short loc_1800132B7
0x1800132b2  mov     rbx, [rax]
0x1800132b5  jmp     short loc_1800132BF
0x1800132b7  mov     rbx, ds:0
0x1800132bf  mov     rax, rdi
0x1800132c2  mul     qword ptr [r14+38h]
0x1800132c6  test    rdx, rdx
0x1800132c9  jnz     short loc_1800132DF
0x1800132cb  add     rax, [r14+58h]
0x1800132cf  cmp     rax, [r14+58h]
0x1800132d3  jnb     short loc_1800132E2
0x1800132d5  jmp     short loc_1800132DF
0x1800132d7  mov     rbx, ds:0
0x1800132df  mov     rax, r9
0x1800132e2  mov     rcx, [rax]
0x1800132e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800132e9  inc     rax
0x1800132ec  cmp     [rcx+rax*2], r9w
0x1800132f1  jnz     short loc_1800132E9
0x1800132f3  lea     r13, [rcx+rax*2]
0x1800132f7  mov     rdi, r15
0x1800132fa  mov     rcx, r12
0x1800132fd  mov     rax, rbp
0x180013300  mov     rdx, rsi
0x180013303  test    rcx, rcx
0x180013306  jz      short loc_180013326
0x180013308  movzx   r8d, word ptr [rdi]
0x18001330c  test    r8w, r8w
0x180013310  jz      short loc_180013326
0x180013312  mov     [rax], r8w
0x180013316  add     rdi, 2
0x18001331a  add     rax, 2
0x18001331e  sub     rcx, r10
0x180013321  sub     rdx, r10
0x180013324  jnz     short loc_180013303
0x180013326  test    rdx, rdx
0x180013329  lea     rcx, [rax-2]
0x18001332d  cmovnz  rcx, rax
0x180013331  mov     rax, rdx
0x180013334  neg     rax
0x180013337  sbb     edi, edi
0x180013339  not     edi
0x18001333b  mov     [rcx], r9w
0x18001333f  and     edi, 80000005h
0x180013345  test    rdx, rdx
0x180013348  jz      loc_18001369D
0x18001334e  mov     rcx, rbp
0x180013351  call    AslStringUpper
0x180013356  mov     rax, [rsp+68h+SubStr]
0x18001335e  xor     r9d, r9d
0x180013361  mov     rcx, r12
0x180013364  mov     rdx, rsi
0x180013367  lea     r10d, [r9+1]
0x18001336b  test    rcx, rcx
0x18001336e  jz      short loc_18001338B
0x180013370  movzx   edi, word ptr [rbx]
0x180013373  test    di, di
0x180013376  jz      short loc_18001338B
0x180013378  mov     [rax], di
0x18001337b  add     rbx, 2
0x18001337f  add     rax, 2
0x180013383  sub     rcx, r10
0x180013386  sub     rdx, r10
0x180013389  jnz     short loc_18001336B
0x18001338b  test    rdx, rdx
0x18001338e  lea     rcx, [rax-2]
0x180013392  cmovnz  rcx, rax
0x180013396  mov     rax, rdx
0x180013399  neg     rax
0x18001339c  sbb     edi, edi
0x18001339e  not     edi
0x1800133a0  mov     [rcx], r9w
0x1800133a4  and     edi, 80000005h
0x1800133aa  test    rdx, rdx
0x1800133ad  jz      loc_18001369D
0x1800133b3  mov     rax, [rsp+68h+SubStr]
0x1800133bb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800133bf  inc     rbx
0x1800133c2  cmp     [rax+rbx*2], r9w
0x1800133c7  jnz     short loc_1800133BF
0x1800133c9  test    rbx, rbx
0x1800133cc  jnz     short loc_1800133DE
0x1800133ce  mov     edi, dword ptr [rsp+68h+arg_8]
0x1800133d2  add     edi, r10d
0x1800133d5  mov     dword ptr [rsp+68h+arg_8], edi
0x1800133d9  jmp     loc_1800134B7
0x1800133de  mov     rcx, rax
0x1800133e1  call    AslStringUpper
0x1800133e6  mov     rdx, [rsp+68h+SubStr]; SubStr
0x1800133ee  mov     rcx, rbp; Str
0x1800133f1  call    wcsstr_0
0x1800133f6  xor     r9d, r9d
0x1800133f9  mov     rcx, rax
0x1800133fc  test    rax, rax
0x1800133ff  jnz     short loc_180013407
0x180013401  lea     r10d, [rax+1]
0x180013405  jmp     short loc_1800133CE
0x180013407  sub     rcx, rbp
0x18001340a  sar     rcx, 1
0x18001340d  lea     rax, [rcx+rbx]
0x180013411  mov     [r15+rcx*2], r9w
0x180013416  lea     r8, [r15+rax*2]
0x18001341a  lea     rax, [r15+208h]
0x180013421  cmp     r8, rax
0x180013424  jnb     loc_18001369D
0x18001342a  mov     rcx, r12
0x18001342d  mov     rdx, rsi
0x180013430  mov     rax, rbp
0x180013433  test    rcx, rcx
0x180013436  jz      short loc_180013459
0x180013438  movzx   edi, word ptr [r8]
0x18001343c  test    di, di
0x18001343f  jz      short loc_180013459
0x180013441  mov     [rax], di
0x180013444  add     r8, 2
0x180013448  mov     edi, 1
0x18001344d  add     rax, 2
0x180013451  sub     rcx, rdi
0x180013454  sub     rdx, rdi; unsigned __int64
0x180013457  jnz     short loc_180013433
0x180013459  test    rdx, rdx
0x18001345c  lea     rcx, [rax-2]
0x180013460  cmovnz  rcx, rax
0x180013464  mov     rax, rdx
0x180013467  neg     rax
0x18001346a  sbb     edi, edi
0x18001346c  not     edi
0x18001346e  mov     [rcx], r9w
0x180013472  and     edi, 80000005h
0x180013478  test    rdx, rdx
0x18001347b  jz      loc_18001369D
0x180013481  lea     r8, [r13+2]; unsigned __int16 *
0x180013485  mov     rcx, r15; unsigned __int16 *
0x180013488  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001348d  mov     edi, eax
0x18001348f  test    eax, eax
0x180013491  js      loc_18001369D
0x180013497  mov     r8, rbp; unsigned __int16 *
0x18001349a  mov     rcx, r15; unsigned __int16 *
0x18001349d  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800134a2  xor     r9d, r9d
0x1800134a5  mov     edi, eax
0x1800134a7  test    eax, eax
0x1800134a9  js      loc_18001369D
0x1800134af  mov     edi, dword ptr [rsp+68h+arg_8]
0x1800134b3  lea     r10d, [r9+1]
0x1800134b7  mov     r8, [r14+40h]
0x1800134bb  mov     rdx, [r14+10h]
0x1800134bf  mov     eax, edi
0x1800134c1  lea     rcx, [rdx+r8]
0x1800134c5  cmp     rax, rcx
0x1800134c8  jb      loc_180013247
0x1800134ce  mov     rax, r15
0x1800134d1  mov     rdx, rbp
0x1800134d4  test    r12, r12
0x1800134d7  jz      short loc_1800134F4
0x1800134d9  movzx   ecx, word ptr [rax]
0x1800134dc  test    cx, cx
0x1800134df  jz      short loc_1800134F4
0x1800134e1  mov     [rdx], cx
0x1800134e4  add     rax, 2
0x1800134e8  add     rdx, 2
0x1800134ec  sub     r12, r10
0x1800134ef  sub     rsi, r10
0x1800134f2  jnz     short loc_1800134D4
0x1800134f4  mov     rax, rsi
0x1800134f7  lea     rcx, [rdx-2]
0x1800134fb  neg     rax
0x1800134fe  sbb     edi, edi
0x180013500  not     edi
0x180013502  and     edi, 80000005h
0x180013508  test    rsi, rsi
0x18001350b  cmovnz  rcx, rdx
0x18001350f  mov     [rcx], r9w
0x180013513  jz      loc_18001369D
0x180013519  mov     rcx, rbp
0x18001351c  call    AslStringUpper
0x180013521  lea     rdx, aUsers; "\\USERS\\"
0x180013528  mov     rcx, rbp; Str
0x18001352b  call    wcsstr_0
0x180013530  xor     r13d, r13d
0x180013533  jmp     short loc_180013581
0x180013535  lea     rcx, [rax+0Eh]
0x180013539  movzx   edx, word ptr [rcx]
0x18001353c  test    dx, dx
0x18001353f  jz      short loc_180013575
0x180013541  mov     rax, rcx
0x180013544  sub     rax, rbp
0x180013547  sar     rax, 1
0x18001354a  lea     rdi, [r15+rax*2]
0x18001354e  cmp     dx, 5Ch ; '\'
0x180013552  jz      short loc_180013575
0x180013554  lea     rax, [r15+208h]
0x18001355b  cmp     rdi, rax
0x18001355e  jnb     short loc_180013575
  ... truncated ...
```
