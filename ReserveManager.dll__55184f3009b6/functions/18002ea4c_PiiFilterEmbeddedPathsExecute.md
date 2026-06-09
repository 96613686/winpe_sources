# PiiFilterEmbeddedPathsExecute

- ea: `0x18002ea4c`
- end: `0x18002f002`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1462`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002f008`

## callees

- `0x180003870`
- `0x180004294`
- `0x18002e924`
- `0x18002e99c`
- `0x18002ea4c`
- `0x180031720`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ecf7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ee32`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ee84`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ecf7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ee32`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002ee84`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002ef8f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002ef8f`
- `ntdll!RtlAllocateHeap` at `0x18002ea94`
- `ntdll!RtlAllocateHeap` at `0x18002eac0`
- `ntdll!RtlAllocateHeap` at `0x18002ea94`
- `ntdll!RtlAllocateHeap` at `0x18002eac0`
- `ntdll!RtlFreeHeap` at `0x18002efb8`
- `ntdll!RtlFreeHeap` at `0x18002efd5`
- `ntdll!RtlFreeHeap` at `0x18002efb8`
- `ntdll!RtlFreeHeap` at `0x18002efd5`

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
  unsigned __int16 *v54; // rdi
  const wchar_t *v55; // rbx
  int v56; // esi
  unsigned __int16 v57; // ax
  BOOL v58; // eax
  char *v59; // rdi
  unsigned __int64 v60; // rcx
  wchar_t *v61; // rax
  int v63; // [rsp+20h] [rbp-58h] BYREF
  wchar_t *SubStr; // [rsp+28h] [rbp-50h]

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
        for ( i = wcsstr(Heap, L"\\USERS\\"); i; i = wcsstr(v50, L"\\USERS\\") )
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
          v63 = 0;
          v55 = v61 + 1;
          v56 = 0;
          v57 = v61[1];
          if ( v57 )
          {
            do
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(v57, 0, &v63) )
                break;
              if ( *v55 == 46 )
                v56 = 1;
              v57 = *++v55;
            }
            while ( *v55 );
          }
          v58 = (unsigned int)o_iswspace_0(*v55) || !*v55 || *v55 == 62;
          if ( v56 && v58 )
          {
            --v55;
            v63 = 0;
            while ( v54 >= a1 )
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(*v54, 1, &v63) )
              {
                if ( *v54 != 60 && !(unsigned int)o_iswspace_0(*v54) )
                  goto LABEL_109;
                break;
              }
              --v54;
            }
            if ( !v63 )
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
    v63 = 0;
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
      if ( v37 && (AslStringUpper(SubStr, v35, v32, 0), (v38 = wcsstr(Heap, SubStr)) != 0) )
      {
        v39 = v38 - Heap;
        a1[v39] = 0;
        v40 = &a1[v37 + v39];
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
        v17 = (unsigned int)++v63;
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
0x18002ea4c  mov     [rsp+arg_8], rbx
0x18002ea51  push    rbp
0x18002ea52  push    rsi
0x18002ea53  push    rdi
0x18002ea54  push    r12
0x18002ea56  push    r13
0x18002ea58  push    r14
0x18002ea5a  push    r15
0x18002ea5c  sub     rsp, 40h
0x18002ea60  mov     rax, cs:__security_cookie
0x18002ea67  xor     rax, rsp
0x18002ea6a  mov     [rsp+78h+var_40], rax
0x18002ea6f  mov     r15, rcx
0x18002ea72  mov     r14, r8
0x18002ea75  mov     rcx, gs:60h
0x18002ea7e  mov     ebx, 208h
0x18002ea83  mov     esi, 8
0x18002ea88  mov     r8d, ebx; Size
0x18002ea8b  mov     edx, esi; Flags
0x18002ea8d  mov     rdi, r9
0x18002ea90  mov     rcx, [rcx+30h]; HeapHandle
0x18002ea94  call    cs:__imp_RtlAllocateHeap
0x18002ea9a  mov     [rsp+78h+SubStr], rax
0x18002ea9f  test    rax, rax
0x18002eaa2  jnz     short loc_18002EAAE
0x18002eaa4  mov     edi, 0C0000017h
0x18002eaa9  jmp     loc_18002EFDB
0x18002eaae  mov     rcx, gs:60h
0x18002eab7  mov     r8, rbx; Size
0x18002eaba  mov     edx, esi; Flags
0x18002eabc  mov     rcx, [rcx+30h]; HeapHandle
0x18002eac0  call    cs:__imp_RtlAllocateHeap
0x18002eac6  xor     r9d, r9d
0x18002eac9  mov     rbp, rax
0x18002eacc  test    rax, rax
0x18002eacf  jnz     short loc_18002EADB
0x18002ead1  mov     edi, 0C0000017h
0x18002ead6  jmp     loc_18002EFA4
0x18002eadb  mov     r12d, 7FFFFFFEh
0x18002eae1  mov     esi, 104h
0x18002eae6  mov     eax, r12d
0x18002eae9  mov     edx, esi
0x18002eaeb  mov     r8, r15
0x18002eaee  mov     r10d, 1
0x18002eaf4  test    rax, rax
0x18002eaf7  jz      short loc_18002EB15
0x18002eaf9  movzx   ecx, word ptr [rdi]
0x18002eafc  test    cx, cx
0x18002eaff  jz      short loc_18002EB15
0x18002eb01  mov     [r8], cx
0x18002eb05  add     rdi, 2
0x18002eb09  add     r8, 2
0x18002eb0d  sub     rax, r10
0x18002eb10  sub     rdx, r10
0x18002eb13  jnz     short loc_18002EAF4
0x18002eb15  mov     rax, rdx
0x18002eb18  lea     rcx, [r8-2]
0x18002eb1c  neg     rax
0x18002eb1f  sbb     edi, edi
0x18002eb21  not     edi
0x18002eb23  and     edi, 80000005h
0x18002eb29  test    rdx, rdx
0x18002eb2c  cmovnz  rcx, r8
0x18002eb30  mov     [rcx], r9w
0x18002eb34  jz      loc_18002EFA4
0x18002eb3a  mov     r8, [r14+40h]
0x18002eb3e  mov     rdx, [r14+10h]
0x18002eb42  lea     rax, [rdx+r8]
0x18002eb46  test    rax, rax
0x18002eb49  jz      loc_18002EDD5
0x18002eb4f  mov     edi, r9d
0x18002eb52  mov     [rsp+78h+var_58], edi
0x18002eb56  cmp     rdi, rdx
0x18002eb59  jnb     short loc_18002EBA3
0x18002eb5b  mov     rax, rdi
0x18002eb5e  lea     r8, [r14+28h]
0x18002eb62  mul     qword ptr [r14+8]
0x18002eb66  test    rdx, rdx
0x18002eb69  jnz     short loc_18002EB73
0x18002eb6b  add     rax, [r8]
0x18002eb6e  cmp     rax, [r8]
0x18002eb71  jnb     short loc_18002EB76
0x18002eb73  mov     rax, r9
0x18002eb76  mov     rbx, [rax]
0x18002eb79  mov     rax, rdi
0x18002eb7c  mul     qword ptr [r14+8]
0x18002eb80  test    rdx, rdx
0x18002eb83  jnz     short loc_18002EB8D
0x18002eb85  add     rax, [r8]
0x18002eb88  cmp     rax, [r8]
0x18002eb8b  jnb     short loc_18002EB90
0x18002eb8d  mov     rax, r9
0x18002eb90  mov     rcx, [rax]
0x18002eb93  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb97  inc     rax
0x18002eb9a  cmp     [rcx+rax*2], r9w
0x18002eb9f  jnz     short loc_18002EB97
0x18002eba1  jmp     short loc_18002EC02
0x18002eba3  sub     rdi, rdx
0x18002eba6  cmp     rdi, r8
0x18002eba9  jnb     short loc_18002EBE6
0x18002ebab  mov     rax, rdi
0x18002ebae  mul     qword ptr [r14+38h]
0x18002ebb2  test    rdx, rdx
0x18002ebb5  jnz     short loc_18002EBC6
0x18002ebb7  add     rax, [r14+58h]
0x18002ebbb  cmp     rax, [r14+58h]
0x18002ebbf  jb      short loc_18002EBC6
0x18002ebc1  mov     rbx, [rax]
0x18002ebc4  jmp     short loc_18002EBCE
0x18002ebc6  mov     rbx, ds:0
0x18002ebce  mov     rax, rdi
0x18002ebd1  mul     qword ptr [r14+38h]
0x18002ebd5  test    rdx, rdx
0x18002ebd8  jnz     short loc_18002EBEE
0x18002ebda  add     rax, [r14+58h]
0x18002ebde  cmp     rax, [r14+58h]
0x18002ebe2  jnb     short loc_18002EBF1
0x18002ebe4  jmp     short loc_18002EBEE
0x18002ebe6  mov     rbx, ds:0
0x18002ebee  mov     rax, r9
0x18002ebf1  mov     rcx, [rax]
0x18002ebf4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ebf8  inc     rax
0x18002ebfb  cmp     [rcx+rax*2], r9w
0x18002ec00  jnz     short loc_18002EBF8
0x18002ec02  lea     r13, [rcx+rax*2]
0x18002ec06  mov     rdi, r15
0x18002ec09  mov     rcx, r12
0x18002ec0c  mov     rax, rbp
0x18002ec0f  mov     rdx, rsi
0x18002ec12  test    rcx, rcx
0x18002ec15  jz      short loc_18002EC35
0x18002ec17  movzx   r8d, word ptr [rdi]
0x18002ec1b  test    r8w, r8w
0x18002ec1f  jz      short loc_18002EC35
0x18002ec21  mov     [rax], r8w
0x18002ec25  add     rdi, 2
0x18002ec29  add     rax, 2
0x18002ec2d  sub     rcx, r10
0x18002ec30  sub     rdx, r10
0x18002ec33  jnz     short loc_18002EC12
0x18002ec35  test    rdx, rdx
0x18002ec38  lea     rcx, [rax-2]
0x18002ec3c  cmovnz  rcx, rax
0x18002ec40  mov     rax, rdx
0x18002ec43  neg     rax
0x18002ec46  sbb     edi, edi
0x18002ec48  not     edi
0x18002ec4a  mov     [rcx], r9w
0x18002ec4e  and     edi, 80000005h
0x18002ec54  test    rdx, rdx
0x18002ec57  jz      loc_18002EFA4
0x18002ec5d  mov     rcx, rbp
0x18002ec60  call    AslStringUpper
0x18002ec65  mov     rax, [rsp+78h+SubStr]
0x18002ec6a  xor     r9d, r9d
0x18002ec6d  mov     rcx, r12
0x18002ec70  mov     rdx, rsi
0x18002ec73  lea     r10d, [r9+1]
0x18002ec77  test    rcx, rcx
0x18002ec7a  jz      short loc_18002EC97
0x18002ec7c  movzx   edi, word ptr [rbx]
0x18002ec7f  test    di, di
0x18002ec82  jz      short loc_18002EC97
0x18002ec84  mov     [rax], di
0x18002ec87  add     rbx, 2
0x18002ec8b  add     rax, 2
0x18002ec8f  sub     rcx, r10
0x18002ec92  sub     rdx, r10
0x18002ec95  jnz     short loc_18002EC77
0x18002ec97  test    rdx, rdx
0x18002ec9a  lea     rcx, [rax-2]
0x18002ec9e  cmovnz  rcx, rax
0x18002eca2  mov     rax, rdx
0x18002eca5  neg     rax
0x18002eca8  sbb     edi, edi
0x18002ecaa  not     edi
0x18002ecac  mov     [rcx], r9w
0x18002ecb0  and     edi, 80000005h
0x18002ecb6  test    rdx, rdx
0x18002ecb9  jz      loc_18002EFA4
0x18002ecbf  mov     rax, [rsp+78h+SubStr]
0x18002ecc4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ecc8  inc     rbx
0x18002eccb  cmp     [rax+rbx*2], r9w
0x18002ecd0  jnz     short loc_18002ECC8
0x18002ecd2  test    rbx, rbx
0x18002ecd5  jnz     short loc_18002ECE7
0x18002ecd7  mov     edi, [rsp+78h+var_58]
0x18002ecdb  add     edi, r10d
0x18002ecde  mov     [rsp+78h+var_58], edi
0x18002ece2  jmp     loc_18002EDBE
0x18002ece7  mov     rcx, rax
0x18002ecea  call    AslStringUpper
0x18002ecef  mov     rdx, [rsp+78h+SubStr]; SubStr
0x18002ecf4  mov     rcx, rbp; Str
0x18002ecf7  call    cs:__imp_wcsstr
0x18002ecfd  xor     r9d, r9d
0x18002ed00  mov     rcx, rax
0x18002ed03  test    rax, rax
0x18002ed06  jnz     short loc_18002ED0E
0x18002ed08  lea     r10d, [rax+1]
0x18002ed0c  jmp     short loc_18002ECD7
0x18002ed0e  sub     rcx, rbp
0x18002ed11  sar     rcx, 1
0x18002ed14  lea     rax, [rbx+rcx]
0x18002ed18  mov     [r15+rcx*2], r9w
0x18002ed1d  lea     r8, [r15+rax*2]
0x18002ed21  lea     rax, [r15+208h]
0x18002ed28  cmp     r8, rax
0x18002ed2b  jnb     loc_18002EFA4
0x18002ed31  mov     rcx, r12
0x18002ed34  mov     rdx, rsi
0x18002ed37  mov     rax, rbp
0x18002ed3a  test    rcx, rcx
0x18002ed3d  jz      short loc_18002ED60
0x18002ed3f  movzx   edi, word ptr [r8]
0x18002ed43  test    di, di
0x18002ed46  jz      short loc_18002ED60
0x18002ed48  mov     [rax], di
0x18002ed4b  add     r8, 2
0x18002ed4f  mov     edi, 1
0x18002ed54  add     rax, 2
0x18002ed58  sub     rcx, rdi
0x18002ed5b  sub     rdx, rdi; unsigned __int64
0x18002ed5e  jnz     short loc_18002ED3A
0x18002ed60  test    rdx, rdx
0x18002ed63  lea     rcx, [rax-2]
0x18002ed67  cmovnz  rcx, rax
0x18002ed6b  mov     rax, rdx
0x18002ed6e  neg     rax
0x18002ed71  sbb     edi, edi
0x18002ed73  not     edi
0x18002ed75  mov     [rcx], r9w
0x18002ed79  and     edi, 80000005h
0x18002ed7f  test    rdx, rdx
0x18002ed82  jz      loc_18002EFA4
0x18002ed88  lea     r8, [r13+2]; unsigned __int16 *
0x18002ed8c  mov     rcx, r15; unsigned __int16 *
0x18002ed8f  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ed94  mov     edi, eax
0x18002ed96  test    eax, eax
0x18002ed98  js      loc_18002EFA4
0x18002ed9e  mov     r8, rbp; unsigned __int16 *
0x18002eda1  mov     rcx, r15; unsigned __int16 *
0x18002eda4  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002eda9  xor     r9d, r9d
0x18002edac  mov     edi, eax
0x18002edae  test    eax, eax
0x18002edb0  js      loc_18002EFA4
0x18002edb6  mov     edi, [rsp+78h+var_58]
0x18002edba  lea     r10d, [r9+1]
0x18002edbe  mov     r8, [r14+40h]
0x18002edc2  mov     rdx, [r14+10h]
0x18002edc6  mov     eax, edi
0x18002edc8  lea     rcx, [rdx+r8]
0x18002edcc  cmp     rax, rcx
0x18002edcf  jb      loc_18002EB56
0x18002edd5  mov     rax, r15
0x18002edd8  mov     rdx, rbp
0x18002eddb  test    r12, r12
0x18002edde  jz      short loc_18002EDFB
0x18002ede0  movzx   ecx, word ptr [rax]
0x18002ede3  test    cx, cx
0x18002ede6  jz      short loc_18002EDFB
0x18002ede8  mov     [rdx], cx
0x18002edeb  add     rax, 2
0x18002edef  add     rdx, 2
0x18002edf3  sub     r12, r10
0x18002edf6  sub     rsi, r10
0x18002edf9  jnz     short loc_18002EDDB
0x18002edfb  mov     rax, rsi
0x18002edfe  lea     rcx, [rdx-2]
0x18002ee02  neg     rax
0x18002ee05  sbb     edi, edi
0x18002ee07  not     edi
0x18002ee09  and     edi, 80000005h
0x18002ee0f  test    rsi, rsi
0x18002ee12  cmovnz  rcx, rdx
0x18002ee16  mov     [rcx], r9w
0x18002ee1a  jz      loc_18002EFA4
0x18002ee20  mov     rcx, rbp
0x18002ee23  call    AslStringUpper
0x18002ee28  lea     rdx, aUsers; "\\USERS\\"
0x18002ee2f  mov     rcx, rbp; Str
0x18002ee32  call    cs:__imp_wcsstr
0x18002ee38  xor     r13d, r13d
0x18002ee3b  jmp     short loc_18002EE8A
0x18002ee3d  lea     rcx, [rax+0Eh]
0x18002ee41  movzx   edx, word ptr [rcx]
0x18002ee44  test    dx, dx
0x18002ee47  jz      short loc_18002EE7D
0x18002ee49  mov     rax, rcx
0x18002ee4c  sub     rax, rbp
0x18002ee4f  sar     rax, 1
0x18002ee52  lea     rdi, [r15+rax*2]
0x18002ee56  cmp     dx, 5Ch ; '\'
0x18002ee5a  jz      short loc_18002EE7D
0x18002ee5c  lea     rax, [r15+208h]
  ... truncated ...
```
