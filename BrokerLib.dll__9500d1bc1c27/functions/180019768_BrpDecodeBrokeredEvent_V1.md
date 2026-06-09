# BrpDecodeBrokeredEvent_V1

- ea: `0x180019768`
- end: `0x180019cf6`
- name: `BrpDecodeBrokeredEvent_V1`
- size: `1422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019660`

## callees

- `0x1800165aa`
- `0x180019768`
- `0x180019cfc`
- `0x180019d24`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019870`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019ae4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019870`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019ae4`

## pseudocode

```c
__int64 __fastcall BrpDecodeBrokeredEvent_V1(__int64 a1, unsigned __int16 a2, USHORT a3, __int64 a4, USHORT *a5)
{
  size_t v5; // r9
  USHORT v7; // cx
  unsigned __int16 v8; // r8
  int v9; // r11d
  int v10; // r12d
  unsigned __int16 v11; // si
  __int64 v12; // r14
  int v13; // r10d
  int v14; // ebx
  unsigned __int16 *v15; // rdi
  unsigned __int16 i; // r13
  _OWORD *v17; // rax
  unsigned __int64 v18; // rsi
  __int64 v19; // rcx
  const void *v20; // rbx
  size_t v21; // rax
  __int64 v22; // r9
  _DWORD *v23; // rdi
  int v24; // eax
  unsigned __int16 *v25; // rdi
  int v26; // eax
  int v27; // eax
  int v28; // eax
  size_t v29; // rbx
  __int64 v30; // r10
  __int64 v31; // r9
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // r9
  USHORT v35; // dx
  __int64 v36; // rcx
  const void *v37; // rbx
  size_t v38; // rax
  __int64 v39; // r9
  __int64 v40; // rax
  int v41; // eax
  USHORT v42; // r11
  int v43; // r10d
  USHORT v45[2]; // [rsp+20h] [rbp-20h] BYREF
  USHORT pusResult[2]; // [rsp+24h] [rbp-1Ch] BYREF
  USHORT v47[2]; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 v48; // [rsp+2Ch] [rbp-14h]
  int v49; // [rsp+30h] [rbp-10h]
  USHORT usAugend[2]; // [rsp+34h] [rbp-Ch]
  int v51; // [rsp+38h] [rbp-8h]
  int v52; // [rsp+3Ch] [rbp-4h]

  v5 = 0;
  v7 = 0;
  pusResult[0] = 0;
  v8 = a2;
  v51 = 0;
  LOWORD(v9) = 0;
  *(_DWORD *)usAugend = 0;
  v47[0] = 0;
  v45[0] = 0;
  v10 = 0;
  if ( a2 < 4u || !a1 || *(_BYTE *)a1 != 1 )
    return 3221225485LL;
  v11 = *(_WORD *)(a1 + 2);
  v48 = v11;
  v12 = 0;
  v13 = 0;
  v49 = 0;
  v14 = 0;
  while ( 2 )
  {
    v52 = v14;
    if ( (unsigned __int16)v14 >= 2u )
    {
      *a5 = v7;
      return (unsigned int)v5;
    }
    v15 = (unsigned __int16 *)(a1 + 4);
    for ( i = v5; i < v11; ++i )
    {
      if ( v12 )
      {
        v17 = (_OWORD *)(*(_QWORD *)(v12 + 8) + 32LL * i);
        *v17 = 0;
        v17[1] = 0;
      }
      v18 = v8;
      if ( a1 + v8 - (unsigned __int64)v15 < 2 )
        return 3221225485LL;
      v19 = *v15;
      if ( v8 < (unsigned __int64)(v19 + 2) )
        return 3221225485LL;
      if ( (_WORD)v19 )
      {
        v20 = (const void *)(v19 + a1);
        if ( v19 + a1 )
          v21 = wcsnlen((const wchar_t *)(v19 + a1), ((unsigned __int64)v8 - v19) >> 1);
        else
          v21 = v5;
        if ( UIntPtrToUShort(2 * v21 + 2, pusResult) < 0 )
          return 3221225621LL;
        if ( v12 )
        {
          v22 = 32LL * i;
          *(_QWORD *)(v22 + *(_QWORD *)(v12 + 8)) = v12 + (unsigned __int16)v10;
          memcpy_0(*(void **)(v22 + *(_QWORD *)(v12 + 8)), v20, pusResult[0]);
        }
        if ( UShortAdd(v10, pusResult[0], v45) < 0 )
          return 3221225621LL;
        v10 = v45[0];
        v13 = v49;
        LOWORD(v9) = usAugend[0];
        v8 = a2;
      }
      v23 = v15 + 1;
      if ( a1 + v18 - (unsigned __int64)v23 < 4 )
        return 3221225485LL;
      v24 = *v23;
      v25 = (unsigned __int16 *)(v23 + 1);
      if ( v12 )
        *(_DWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 8) = v24;
      if ( v24 )
      {
        v26 = v24 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              if ( v28 != 1 )
                return 3221225701LL;
              if ( a1 + v18 - (unsigned __int64)v25 < 2 )
                return 3221225485LL;
              v29 = *v25++;
              if ( v12 )
                *(_WORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v29;
              if ( a1 + v18 - (unsigned __int64)v25 < 2 )
                return 3221225485LL;
              v30 = *v25;
              if ( v8 < (unsigned __int16)v30 )
                return 3221225485LL;
              if ( (_WORD)v30 )
              {
                if ( v12 )
                {
                  v31 = 32LL * i;
                  *(_QWORD *)(v31 + *(_QWORD *)(v12 + 8) + 24) = v12 + (unsigned __int16)v9;
                  memcpy_0(*(void **)(v31 + *(_QWORD *)(v12 + 8) + 24), (const void *)(a1 + v30), v29);
                }
                if ( UShortAdd(usAugend[0], v29, v47) < 0 )
                  return 3221225621LL;
                *(_DWORD *)usAugend = v47[0];
              }
              goto LABEL_60;
            }
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v32 = *v25++;
            if ( v12 )
              *(_WORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v32;
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v33 = *v25;
            if ( v8 < (unsigned __int16)v33 )
              return 3221225485LL;
            if ( (_WORD)v33 )
            {
              if ( v12 )
              {
                v34 = 32LL * i;
                *(_QWORD *)(v34 + *(_QWORD *)(v12 + 8) + 24) = v12 + (unsigned __int16)v10;
                memcpy_0(*(void **)(v34 + *(_QWORD *)(v12 + 8) + 24), (const void *)(a1 + v33), 2 * v32);
              }
              v35 = 2 * v32;
              goto LABEL_58;
            }
          }
          else
          {
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v36 = *v25;
            if ( v18 < v36 + 2 )
              return 3221225485LL;
            if ( (_WORD)v36 )
            {
              v37 = (const void *)(v36 + a1);
              if ( v36 + a1 )
                v38 = wcsnlen((const wchar_t *)(v36 + a1), ((unsigned __int64)v8 - v36) >> 1);
              else
                v38 = v5;
              if ( UIntPtrToUShort(2 * v38 + 2, pusResult) < 0 )
                return 3221225621LL;
              if ( v12 )
              {
                v39 = 32LL * i;
                *(_QWORD *)(v39 + *(_QWORD *)(v12 + 8) + 16) = v12 + (unsigned __int16)v10;
                memcpy_0(*(void **)(v39 + *(_QWORD *)(v12 + 8) + 16), v37, pusResult[0]);
              }
              v35 = pusResult[0];
LABEL_58:
              if ( UShortAdd(v10, v35, v45) < 0 )
                return 3221225621LL;
              v10 = v45[0];
            }
          }
LABEL_60:
          v13 = v49;
          v15 = v25 + 1;
          goto LABEL_67;
        }
        if ( a1 + v18 - (unsigned __int64)v25 < 8 )
          return 3221225485LL;
        v40 = *(_QWORD *)v25;
        v15 = v25 + 4;
        if ( v12 )
          *(_QWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v40;
      }
      else
      {
        if ( a1 + v18 - (unsigned __int64)v25 < 4 )
          return 3221225485LL;
        v41 = *(_DWORD *)v25;
        v15 = v25 + 2;
        if ( v12 )
          *(_DWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v41;
      }
LABEL_67:
      LOWORD(v9) = usAugend[0];
      LOWORD(v13) = v13 + 32;
      v8 = a2;
      v11 = v48;
      v49 = v13;
    }
    if ( v12 )
    {
      v7 = v51;
LABEL_78:
      HIWORD(v14) = HIWORD(v52);
      LOWORD(v14) = v52 + 1;
      continue;
    }
    break;
  }
  v45[0] = 16;
  if ( UShortAdd(0x10u, v13, v45) < 0 || UShortAdd(v45[0], v10, v45) < 0 || UShortAdd(v45[0], v42, v45) < 0 )
    return 3221225621LL;
  v7 = v45[0];
  v51 = v45[0];
  if ( a4 && a3 >= v45[0] )
  {
    *(_QWORD *)(a4 + 8) = 0;
    v12 = a4;
    *(_WORD *)a4 = 0;
    if ( v11 )
    {
      *(_WORD *)a4 = v11;
      *(_QWORD *)(a4 + 8) = a4 + 16;
    }
    v8 = a2;
    v9 = v43 + v10;
    LOWORD(v9) = v43 + v10 + 16;
    v5 = 0;
    v45[0] = v43 + 16;
    v10 = (unsigned __int16)(v43 + 16);
    *(_DWORD *)usAugend = v9;
    v47[0] = v9;
    v13 = 0;
    v49 = 0;
    goto LABEL_78;
  }
  *a5 = v45[0];
  return 3221225507LL;
}

```

## disassembly

```asm
0x180019768  mov     rax, rsp
0x18001976b  mov     [rax+8], rbx
0x18001976f  mov     [rax+20h], r9
0x180019773  mov     [rax+18h], r8w
0x180019778  mov     [rax+10h], dx
0x18001977c  push    rbp
0x18001977d  push    rsi
0x18001977e  push    rdi
0x18001977f  push    r12
0x180019781  push    r13
0x180019783  push    r14
0x180019785  push    r15
0x180019787  mov     rbp, rsp
0x18001978a  sub     rsp, 40h
0x18001978e  xor     r9d, r9d
0x180019791  mov     r15, rcx
0x180019794  mov     ecx, r9d
0x180019797  mov     [rbp+pusResult], r9w
0x18001979c  movzx   r8d, dx
0x1800197a0  mov     [rbp+var_8], ecx
0x1800197a3  mov     r11d, r9d
0x1800197a6  mov     dword ptr [rbp+usAugend], r9d
0x1800197aa  lea     eax, [r9+4]
0x1800197ae  mov     [rbp+var_18], r9w
0x1800197b3  mov     [rbp+var_20], r9w
0x1800197b8  mov     r12d, r9d
0x1800197bb  cmp     dx, ax
0x1800197be  jb      loc_180019CD9
0x1800197c4  test    r15, r15
0x1800197c7  jz      loc_180019CD9
0x1800197cd  cmp     byte ptr [r15], 1
0x1800197d1  jnz     loc_180019CD9
0x1800197d7  movzx   esi, word ptr [r15+2]
0x1800197dc  lea     edx, [rax-2]
0x1800197df  mov     [rbp+var_14], si
0x1800197e3  mov     r14d, r9d
0x1800197e6  mov     r10d, r9d
0x1800197e9  mov     [rbp+var_10], r9d
0x1800197ed  mov     ebx, r9d
0x1800197f0  mov     [rbp+var_4], ebx
0x1800197f3  cmp     bx, dx
0x1800197f6  jnb     loc_180019CCD
0x1800197fc  lea     rdi, [r15+4]
0x180019800  mov     r13d, r9d
0x180019803  cmp     r13w, si
0x180019807  jnb     loc_180019BE6
0x18001980d  test    r14, r14
0x180019810  jz      short loc_180019828
0x180019812  xorps   xmm0, xmm0
0x180019815  movzx   eax, r13w
0x180019819  shl     rax, 5
0x18001981d  add     rax, [r14+8]
0x180019821  movups  xmmword ptr [rax], xmm0
0x180019824  movups  xmmword ptr [rax+10h], xmm0
0x180019828  movzx   esi, r8w
0x18001982c  mov     eax, esi
0x18001982e  sub     rax, rdi
0x180019831  add     rax, r15
0x180019834  cmp     rax, rdx
0x180019837  jb      loc_180019CD9
0x18001983d  movzx   ecx, word ptr [rdi]
0x180019840  lea     rax, [rcx+2]
0x180019844  cmp     rsi, rax
0x180019847  jb      loc_180019CD9
0x18001984d  test    cx, cx
0x180019850  jz      loc_1800198F1
0x180019856  lea     rbx, [rcx+r15]
0x18001985a  test    rbx, rbx
0x18001985d  jnz     short loc_180019864
0x18001985f  mov     rax, r9
0x180019862  jmp     short loc_180019879
0x180019864  mov     rdx, rsi
0x180019867  sub     rdx, rcx
0x18001986a  mov     rcx, rbx; Source
0x18001986d  shr     rdx, 1; MaxCount
0x180019870  call    cs:__imp_wcsnlen
0x180019876  xor     r9d, r9d
0x180019879  lea     rcx, ds:2[rax*2]; uOperand
0x180019881  lea     rdx, [rbp+pusResult]; pusResult
0x180019885  call    UIntPtrToUShort
0x18001988a  test    eax, eax
0x18001988c  js      loc_180019CB1
0x180019892  test    r14, r14
0x180019895  jz      short loc_1800198C6
0x180019897  mov     rax, [r14+8]
0x18001989b  mov     rdx, rbx; Src
0x18001989e  movzx   r9d, r13w
0x1800198a2  shl     r9, 5
0x1800198a6  movzx   r8d, r12w
0x1800198aa  add     r8, r14
0x1800198ad  mov     [r9+rax], r8
0x1800198b1  mov     rcx, [r14+8]
0x1800198b5  movzx   r8d, [rbp+pusResult]; Size
0x1800198ba  mov     rcx, [r9+rcx]; void *
0x1800198be  call    memcpy_0
0x1800198c3  xor     r9d, r9d
0x1800198c6  movzx   edx, [rbp+pusResult]; usAddend
0x1800198ca  lea     r8, [rbp+var_20]; pusResult
0x1800198ce  movzx   ecx, r12w; usAugend
0x1800198d2  call    UShortAdd
0x1800198d7  test    eax, eax
0x1800198d9  js      loc_180019CB1
0x1800198df  movzx   r12d, [rbp+var_20]
0x1800198e4  mov     r10d, [rbp+var_10]
0x1800198e8  mov     r11d, dword ptr [rbp+usAugend]
0x1800198ec  movzx   r8d, [rbp+arg_8]
0x1800198f1  add     rdi, 2
0x1800198f5  mov     rax, rsi
0x1800198f8  sub     rax, rdi
0x1800198fb  add     rax, r15
0x1800198fe  cmp     rax, 4
0x180019902  jb      loc_180019CD9
0x180019908  mov     eax, [rdi]
0x18001990a  add     rdi, 4
0x18001990e  test    r14, r14
0x180019911  jz      short loc_180019923
0x180019913  mov     rcx, [r14+8]
0x180019917  movzx   edx, r13w
0x18001991b  shl     rdx, 5
0x18001991f  mov     [rdx+rcx+8], eax
0x180019923  test    eax, eax
0x180019925  jz      loc_180019B97
0x18001992b  sub     eax, 1
0x18001992e  jz      loc_180019B68
0x180019934  sub     eax, 1
0x180019937  jz      loc_180019A99
0x18001993d  sub     eax, 1
0x180019940  jz      loc_180019A01
0x180019946  cmp     eax, 1
0x180019949  jnz     loc_180019CB8
0x18001994f  mov     rax, rsi
0x180019952  mov     edx, 2
0x180019957  sub     rax, rdi
0x18001995a  add     rax, r15
0x18001995d  cmp     rax, rdx
0x180019960  jb      loc_180019CD9
0x180019966  movzx   ebx, word ptr [rdi]
0x180019969  add     rdi, rdx
0x18001996c  test    r14, r14
0x18001996f  jz      short loc_180019982
0x180019971  mov     rax, [r14+8]
0x180019975  movzx   ecx, r13w
0x180019979  shl     rcx, 5
0x18001997d  mov     [rcx+rax+10h], bx
0x180019982  sub     rsi, rdi
0x180019985  add     rsi, r15
0x180019988  cmp     rsi, rdx
0x18001998b  jb      loc_180019CD9
0x180019991  movzx   r10d, word ptr [rdi]
0x180019995  cmp     r8w, r10w
0x180019999  jb      loc_180019CD9
0x18001999f  test    r10w, r10w
0x1800199a3  jz      loc_180019B5F
0x1800199a9  test    r14, r14
0x1800199ac  jz      short loc_1800199DE
0x1800199ae  mov     rax, [r14+8]
0x1800199b2  mov     r8, rbx; Size
0x1800199b5  movzx   edx, r11w
0x1800199b9  add     rdx, r14
0x1800199bc  movzx   r9d, r13w
0x1800199c0  shl     r9, 5
0x1800199c4  mov     [r9+rax+18h], rdx
0x1800199c9  lea     rdx, [r15+r10]; Src
0x1800199cd  mov     rcx, [r14+8]
0x1800199d1  mov     rcx, [r9+rcx+18h]; void *
0x1800199d6  call    memcpy_0
0x1800199db  xor     r9d, r9d
0x1800199de  mov     ecx, dword ptr [rbp+usAugend]; usAugend
0x1800199e1  lea     r8, [rbp+var_18]; pusResult
0x1800199e5  movzx   edx, bx; usAddend
0x1800199e8  call    UShortAdd
0x1800199ed  test    eax, eax
0x1800199ef  js      loc_180019CB1
0x1800199f5  movzx   ecx, [rbp+var_18]
0x1800199f9  mov     dword ptr [rbp+usAugend], ecx
0x1800199fc  jmp     loc_180019B5A
0x180019a01  mov     rax, rsi
0x180019a04  mov     edx, 2
0x180019a09  sub     rax, rdi
0x180019a0c  add     rax, r15
0x180019a0f  cmp     rax, rdx
0x180019a12  jb      loc_180019CD9
0x180019a18  movzx   ebx, word ptr [rdi]
0x180019a1b  add     rdi, rdx
0x180019a1e  test    r14, r14
0x180019a21  jz      short loc_180019A34
0x180019a23  mov     rax, [r14+8]
0x180019a27  movzx   ecx, r13w
0x180019a2b  shl     rcx, 5
0x180019a2f  mov     [rcx+rax+10h], bx
0x180019a34  sub     rsi, rdi
0x180019a37  add     rsi, r15
0x180019a3a  cmp     rsi, rdx
0x180019a3d  jb      loc_180019CD9
0x180019a43  movzx   ecx, word ptr [rdi]
0x180019a46  cmp     r8w, cx
0x180019a4a  jb      loc_180019CD9
0x180019a50  test    cx, cx
0x180019a53  jz      loc_180019B5F
0x180019a59  test    r14, r14
0x180019a5c  jz      short loc_180019A91
0x180019a5e  mov     rax, [r14+8]
0x180019a62  mov     r8, rbx
0x180019a65  movzx   r9d, r13w
0x180019a69  add     r8, r8; Size
0x180019a6c  shl     r9, 5
0x180019a70  movzx   edx, r12w
0x180019a74  add     rdx, r14
0x180019a77  mov     [r9+rax+18h], rdx
0x180019a7c  lea     rdx, [r15+rcx]; Src
0x180019a80  mov     rcx, [r14+8]
0x180019a84  mov     rcx, [r9+rcx+18h]; void *
0x180019a89  call    memcpy_0
0x180019a8e  xor     r9d, r9d
0x180019a91  lea     edx, [rbx+rbx]
0x180019a94  jmp     loc_180019B40
0x180019a99  mov     rax, rsi
0x180019a9c  mov     edx, 2
0x180019aa1  sub     rax, rdi
0x180019aa4  add     rax, r15
0x180019aa7  cmp     rax, rdx
0x180019aaa  jb      loc_180019CD9
0x180019ab0  movzx   ecx, word ptr [rdi]
0x180019ab3  lea     rax, [rcx+2]
0x180019ab7  cmp     rsi, rax
0x180019aba  jb      loc_180019CD9
0x180019ac0  test    cx, cx
0x180019ac3  jz      loc_180019B5F
0x180019ac9  lea     rbx, [rcx+r15]
0x180019acd  test    rbx, rbx
0x180019ad0  jnz     short loc_180019AD7
0x180019ad2  mov     rax, r9
0x180019ad5  jmp     short loc_180019AED
0x180019ad7  movzx   edx, r8w
0x180019adb  sub     rdx, rcx
0x180019ade  mov     rcx, rbx; Source
0x180019ae1  shr     rdx, 1; MaxCount
0x180019ae4  call    cs:__imp_wcsnlen
0x180019aea  xor     r9d, r9d
0x180019aed  lea     rcx, ds:2[rax*2]; uOperand
0x180019af5  lea     rdx, [rbp+pusResult]; pusResult
0x180019af9  call    UIntPtrToUShort
0x180019afe  test    eax, eax
0x180019b00  js      loc_180019CB1
0x180019b06  test    r14, r14
0x180019b09  jz      short loc_180019B3C
0x180019b0b  mov     rax, [r14+8]
0x180019b0f  mov     rdx, rbx; Src
0x180019b12  movzx   r9d, r13w
0x180019b16  shl     r9, 5
0x180019b1a  movzx   r8d, r12w
0x180019b1e  add     r8, r14
0x180019b21  mov     [r9+rax+10h], r8
0x180019b26  mov     rcx, [r14+8]
0x180019b2a  movzx   r8d, [rbp+pusResult]; Size
0x180019b2f  mov     rcx, [r9+rcx+10h]; void *
0x180019b34  call    memcpy_0
0x180019b39  xor     r9d, r9d
0x180019b3c  movzx   edx, [rbp+pusResult]; usAddend
0x180019b40  lea     r8, [rbp+var_20]; pusResult
0x180019b44  movzx   ecx, r12w; usAugend
0x180019b48  call    UShortAdd
0x180019b4d  test    eax, eax
0x180019b4f  js      loc_180019CB1
0x180019b55  movzx   r12d, [rbp+var_20]
0x180019b5a  mov     edx, 2
0x180019b5f  mov     r10d, [rbp+var_10]
0x180019b63  add     rdi, rdx
0x180019b66  jmp     short loc_180019BC7
0x180019b68  sub     rsi, rdi
0x180019b6b  add     rsi, r15
0x180019b6e  cmp     rsi, 8
0x180019b72  jb      loc_180019CD9
0x180019b78  mov     rax, [rdi]
0x180019b7b  add     rdi, 8
0x180019b7f  test    r14, r14
0x180019b82  jz      short loc_180019BC2
0x180019b84  mov     rcx, [r14+8]
0x180019b88  movzx   edx, r13w
0x180019b8c  shl     rdx, 5
0x180019b90  mov     [rdx+rcx+10h], rax
0x180019b95  jmp     short loc_180019BC2
0x180019b97  sub     rsi, rdi
0x180019b9a  add     rsi, r15
0x180019b9d  cmp     rsi, 4
0x180019ba1  jb      loc_180019CD9
0x180019ba7  mov     eax, [rdi]
0x180019ba9  add     rdi, 4
0x180019bad  test    r14, r14
0x180019bb0  jz      short loc_180019BC2
0x180019bb2  mov     rcx, [r14+8]
0x180019bb6  movzx   edx, r13w
0x180019bba  shl     rdx, 5
0x180019bbe  mov     [rdx+rcx+10h], eax
0x180019bc2  mov     edx, 2
0x180019bc7  mov     r11d, dword ptr [rbp+usAugend]
0x180019bcb  add     r10w, 20h ; ' '
0x180019bd0  movzx   r8d, [rbp+arg_8]
0x180019bd5  inc     r13w
0x180019bd9  movzx   esi, [rbp+var_14]
  ... truncated ...
```
