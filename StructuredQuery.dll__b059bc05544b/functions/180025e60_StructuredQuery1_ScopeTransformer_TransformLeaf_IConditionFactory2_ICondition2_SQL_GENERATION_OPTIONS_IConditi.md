# StructuredQuery1::ScopeTransformer::TransformLeaf(IConditionFactory2 *,ICondition2 *,SQL_GENERATION_OPTIONS,ICondition2 * *,int *)

- ea: `0x180025e60`
- end: `0x1800263bd`
- name: `?TransformLeaf@ScopeTransformer@StructuredQuery1@@UEAAJPEAUIConditionFactory2@@PEAUICondition2@@W4SQL_GENERATION_OPTIONS@@PEAPEAU4@PEAH@Z`
- size: `1373`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180025a80`
- `0x180025e60`
- `0x1800263c4`
- `0x1800263e0`
- `0x180026630`
- `0x18002e5c0`
- `0x180034e80`
- `0x18004146c`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026352`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026364`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026364`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ScopeTransformer::TransformLeaf(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        _DWORD *a6)
{
  _QWORD *v6; // rdi
  char v7; // r15
  _DWORD *v8; // rsi
  __int64 v9; // rax
  __int64 (__fastcall *v10)(_QWORD *, __int128 *, int *, PROPVARIANT *); // rax
  signed int v11; // ebx
  _WORD *v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rdi
  char *v16; // r13
  __int64 v17; // rcx
  char *v18; // r10
  const wchar_t *v19; // rax
  unsigned __int64 v20; // r8
  _WORD *v21; // r9
  __int64 v22; // r10
  __int64 v23; // rdx
  _WORD *v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  wchar_t *v28; // r10
  __int64 v29; // rsi
  int v30; // eax
  _WORD *v31; // r8
  char v32; // r12
  unsigned __int64 v33; // rdi
  wchar_t v34; // cx
  __int64 v35; // r8
  wchar_t v36; // cx
  int v37; // eax
  __int128 *v38; // rdi
  __int64 v39; // r8
  __int64 v40; // r15
  signed int v41; // eax
  __int64 result; // rax
  unsigned int v43; // [rsp+28h] [rbp-91h]
  unsigned int v44; // [rsp+28h] [rbp-91h]
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  int v46; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v47[2]; // [rsp+60h] [rbp-59h] BYREF
  _DWORD *v48; // [rsp+68h] [rbp-51h]
  __int64 v49; // [rsp+70h] [rbp-49h] BYREF
  _QWORD *v50; // [rsp+78h] [rbp-41h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v52; // [rsp+90h] [rbp-29h]
  _QWORD v53[2]; // [rsp+98h] [rbp-21h] BYREF
  _QWORD *v54; // [rsp+A8h] [rbp-11h]
  __int128 v55; // [rsp+B0h] [rbp-9h] BYREF
  int v56; // [rsp+C0h] [rbp+7h]

  v6 = a5;
  v7 = 0;
  v8 = a6;
  v54 = a3;
  v53[0] = a2;
  v50 = a5;
  v48 = a6;
  v49 = 0;
  if ( !*(_BYTE *)(a1 + 8) )
    goto LABEL_72;
  v46 = 0;
  v56 = 0;
  v52 = 0;
  v9 = *a3;
  v55 = 0;
  v10 = *(__int64 (__fastcall **)(_QWORD *, __int128 *, int *, PROPVARIANT *))(v9 + 128);
  *(_OWORD *)pvar = 0;
  v11 = v10(a3, &v55, &v46, pvar);
  if ( v11 >= 0 )
  {
    if ( LOWORD(pvar[0]) != 31 )
    {
LABEL_71:
      v11 = 0;
      if ( !v49 )
      {
LABEL_72:
        v11 = 1;
        goto LABEL_73;
      }
      goto LABEL_73;
    }
    v12 = pvar[1];
    if ( v46 != 1 && v46 != 7 && (v46 != 11 || SemanticsUM::Syntax::IsStar(*(_WORD *)pvar[1])) )
    {
LABEL_70:
      PropVariantClear(pvar);
      if ( v11 < 0 )
        goto LABEL_73;
      goto LABEL_71;
    }
    if ( !v12 )
    {
      v11 = -2147024809;
      goto LABEL_69;
    }
    v13 = 30720;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    v11 = v13 == 0 ? 0x80070057 : 0;
    v14 = (30720 - v13) & -(__int64)(v13 != 0);
    if ( !v13 )
      goto LABEL_69;
    v15 = v14 + 6;
    if ( v14 + 6 < v14 )
    {
      v11 = -2147024362;
      goto LABEL_68;
    }
    pv = 0;
    v11 = _AllocArray<wchar_t,CTCoAllocPolicy>(v13, 1, v14 + 6, &pv);
    if ( v11 < 0 )
    {
LABEL_68:
      v6 = v50;
LABEL_69:
      v8 = v48;
      goto LABEL_70;
    }
    v16 = (char *)pv;
    v17 = 2147483646;
    *(_QWORD *)v47 = v14 + 6;
    v18 = (char *)pv;
    if ( v14 + 5 > 0x7FFFFFFE )
    {
      v11 = -2147024809;
      if ( v14 != -6 )
      {
        *(_WORD *)pv = 0;
        goto LABEL_67;
      }
    }
    else
    {
      v19 = L"file:";
      v20 = v14 + 6;
      v21 = pv;
      v22 = 0;
      do
      {
        if ( !v17 )
          break;
        if ( !*v19 )
          break;
        *v21++ = *v19++;
        --v17;
        ++v22;
        --v20;
      }
      while ( v20 );
      v23 = v22 - 1;
      v24 = v21 - 1;
      if ( v20 )
        v23 = v22;
      v11 = v20 == 0 ? 0x8007007A : 0;
      if ( v20 )
        v24 = v21;
      v18 = &v16[2 * v23];
      v15 -= v23;
      pv = v18;
      *(_QWORD *)v47 = v15;
      *v24 = 0;
    }
    if ( v11 >= 0 && v14 >= 2 )
    {
      v25 = *(unsigned __int16 *)pvar[1];
      LOWORD(v25) = v25 - 65;
      if ( (unsigned __int16)v25 <= 0x39u && (v26 = 0x3FFFFFF03FFFFFFLL, _bittest64(&v26, v25))
        || (unsigned __int16)(*(_WORD *)pvar[1] + 223) <= 0x19u
        || (unsigned __int16)(*(_WORD *)pvar[1] + 191) <= 0x19u )
      {
        if ( *((_WORD *)pvar[1] + 1) == 58 || *((_WORD *)pvar[1] + 1) == 0xFF1A )
        {
          v29 = 2;
          v30 = StringCchCopyNExW(
                  (STRSAFE_LPWSTR)v18,
                  v15,
                  (const wchar_t *)pvar[1],
                  2u,
                  (wchar_t **)&pv,
                  (unsigned __int64 *)v47,
                  0);
LABEL_39:
          v11 = v30;
          if ( v30 >= 0 )
          {
            v31 = pvar[1];
            v32 = 0;
            v33 = 2;
            while ( !v7 )
            {
              if ( v33 < v14 )
              {
                if ( SemanticsUM::Syntax::IsReverseSolidus(v31[v33]) )
                {
                  v11 = StringCchCopyNExW(
                          (STRSAFE_LPWSTR)pv,
                          *(unsigned __int64 *)v47,
                          (const wchar_t *)(v35 + 2 * v29),
                          v33 - v29,
                          (wchar_t **)&pv,
                          (unsigned __int64 *)v47,
                          0);
                  if ( v11 >= 0 )
                    v11 = StringCchCopyExW(
                            (wchar_t *)pv,
                            *(unsigned __int64 *)v47,
                            L"/",
                            (wchar_t **)&pv,
                            (unsigned __int64 *)v47,
                            v44);
                  v31 = pvar[1];
                  v29 = v33 + 1;
                }
                else if ( SemanticsUM::Syntax::IsStar(v34) || SemanticsUM::Syntax::IsQuestionMark(v36) )
                {
                  v7 = 1;
                }
                ++v33;
                if ( v11 >= 0 )
                  continue;
              }
              if ( v11 < 0 )
              {
                v37 = v46;
                goto LABEL_54;
              }
              break;
            }
            v37 = v46;
            if ( v46 == 1 )
              goto LABEL_56;
LABEL_54:
            v38 = &PKEY_SCOPE_PSEUDOPROPERTY;
            if ( v37 != 11 || v7 )
              goto LABEL_59;
LABEL_56:
            v38 = &PKEY_DIRECTORY_PSEUDOPROPERTY;
            if ( operator==((__int64)&v55, (__int64)&PKEY_ItemFolderPathDisplay) )
            {
              v11 = StringCchCopyNExW(
                      (STRSAFE_LPWSTR)pv,
                      *(unsigned __int64 *)v47,
                      (const wchar_t *)(v39 + 2 * v29),
                      v14 - v29,
                      (wchar_t **)&pv,
                      (unsigned __int64 *)v47,
                      0);
              if ( v11 < 0 )
                goto LABEL_67;
              v32 = 1;
              v29 = v14;
              goto LABEL_60;
            }
LABEL_59:
            if ( v11 < 0 )
              goto LABEL_67;
LABEL_60:
            if ( v29 )
            {
              pv = 0;
              v40 = v53[0];
              v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, char *, const size_t *, int, GUID *, LPVOID *))(*(_QWORD *)v53[0] + 88LL))(
                      v53[0],
                      v38,
                      1,
                      v16,
                      &cchOriginalDestLength,
                      1,
                      &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                      &pv);
              if ( v11 >= 0 )
              {
                if ( v32 || v29 == v14 )
                {
                  v41 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))pv)(
                          pv,
                          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                          &v49);
                }
                else
                {
                  v53[0] = pv;
                  v53[1] = v54;
                  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, __int64, int, GUID *, __int64 *))(*(_QWORD *)v40 + 80LL))(
                          v40,
                          0,
                          v53,
                          2,
                          1,
                          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                          &v49);
                }
                v11 = v41;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
              }
            }
          }
          goto LABEL_67;
        }
      }
      if ( SemanticsUM::Syntax::IsReverseSolidus(*(_WORD *)pvar[1])
        && SemanticsUM::Syntax::IsReverseSolidus(*(_WORD *)(v27 + 2)) )
      {
        v29 = 2;
        v30 = StringCchCopyExW(v28, v15, L"//", (wchar_t **)&pv, (unsigned __int64 *)v47, v43);
        goto LABEL_39;
      }
    }
LABEL_67:
    CoTaskMemFree(v16);
    goto LABEL_68;
  }
LABEL_73:
  *v6 = v49;
  result = (unsigned int)v11;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180025e60  mov     [rsp-8+arg_0], rbx
0x180025e65  push    rbp
0x180025e66  push    rsi
0x180025e67  push    rdi
0x180025e68  push    r12
0x180025e6a  push    r13
0x180025e6c  push    r14
0x180025e6e  push    r15
0x180025e70  lea     rbp, [rsp-17h]
0x180025e75  sub     rsp, 0D0h
0x180025e7c  mov     rax, cs:__security_cookie
0x180025e83  xor     rax, rsp
0x180025e86  mov     [rbp+47h+var_38], rax
0x180025e8a  mov     rdi, [rbp+47h+arg_20]
0x180025e8e  xor     r15d, r15d
0x180025e91  mov     r10, r8
0x180025e94  mov     rsi, [rbp+47h+arg_28]
0x180025e98  mov     [rbp+47h+var_58], r8
0x180025e9c  mov     [rbp+47h+var_68], rdx
0x180025ea0  mov     [rbp+47h+var_88], rdi
0x180025ea4  mov     [rbp+47h+var_98], rsi
0x180025ea8  mov     [rbp+47h+var_90], r15
0x180025eac  cmp     [rcx+8], r15b
0x180025eb0  jz      loc_180026377
0x180025eb6  xor     eax, eax
0x180025eb8  mov     [rbp+47h+var_A8], r15d
0x180025ebc  mov     [rbp+47h+var_40], eax
0x180025ebf  lea     r9, [rbp+47h+pvar]
0x180025ec3  mov     [rbp+47h+var_70], rax
0x180025ec7  lea     rdx, [rbp+47h+var_50]
0x180025ecb  mov     rax, [r8]
0x180025ece  xorps   xmm0, xmm0
0x180025ed1  lea     r8, [rbp+47h+var_A8]
0x180025ed5  mov     rcx, r10
0x180025ed8  movups  [rbp+47h+var_50], xmm0
0x180025edc  mov     rax, [rax+80h]
0x180025ee3  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180025ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eec  mov     ebx, eax
0x180025eee  test    eax, eax
0x180025ef0  js      loc_18002637C
0x180025ef6  cmp     word ptr [rbp+47h+pvar], 1Fh
0x180025efb  jnz     loc_18002636E
0x180025f01  mov     eax, [rbp+47h+var_A8]
0x180025f04  mov     rdx, [rbp+47h+pvar+8]
0x180025f08  cmp     eax, 1
0x180025f0b  jz      short loc_180025F2B
0x180025f0d  cmp     eax, 7
0x180025f10  jz      short loc_180025F2B
0x180025f12  cmp     eax, 0Bh
0x180025f15  jnz     loc_180026360
0x180025f1b  movzx   ecx, word ptr [rdx]; wchar_t
0x180025f1e  call    ?IsStar@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsStar(wchar_t)
0x180025f23  test    al, al
0x180025f25  jnz     loc_180026360
0x180025f2b  test    rdx, rdx
0x180025f2e  jz      loc_1800263B6
0x180025f34  mov     r8d, 7800h
0x180025f3a  mov     r12d, 2
0x180025f40  mov     ecx, r8d
0x180025f43  cmp     [rdx], r15w
0x180025f47  jz      short loc_180025F52
0x180025f49  add     rdx, r12
0x180025f4c  sub     rcx, 1
0x180025f50  jnz     short loc_180025F43
0x180025f52  mov     rax, rcx
0x180025f55  mov     esi, 80070057h
0x180025f5a  neg     rax
0x180025f5d  mov     rax, rcx
0x180025f60  sbb     ebx, ebx
0x180025f62  sub     r8, rcx
0x180025f65  not     ebx
0x180025f67  and     ebx, esi
0x180025f69  neg     rax
0x180025f6c  sbb     r14, r14
0x180025f6f  and     r14, r8
0x180025f72  test    rcx, rcx
0x180025f75  jz      loc_18002635C
0x180025f7b  lea     rdi, [r14+6]
0x180025f7f  cmp     rdi, r14
0x180025f82  jb      loc_1800263AF
0x180025f88  lea     r9, [rbp+47h+pv]
0x180025f8c  mov     [rbp+47h+pv], r15
0x180025f90  mov     r8, rdi
0x180025f93  mov     edx, 1
0x180025f98  call    ??$_AllocArray@_WVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEA_W@Z; _AllocArray<wchar_t,CTCoAllocPolicy>(void *,ulong,unsigned __int64,wchar_t * *)
0x180025f9d  mov     ebx, eax
0x180025f9f  test    eax, eax
0x180025fa1  js      loc_180026358
0x180025fa7  mov     r13, [rbp+47h+pv]
0x180025fab  lea     rax, [rdi-1]
0x180025faf  mov     ecx, 7FFFFFFEh
0x180025fb4  mov     [rbp+47h+pv], r13
0x180025fb8  mov     qword ptr [rbp+47h+var_A0], rdi
0x180025fbc  mov     r10, r13
0x180025fbf  cmp     rax, rcx
0x180025fc2  ja      loc_1800260ED
0x180025fc8  lea     rax, aFile; "file:"
0x180025fcf  mov     r8, rdi
0x180025fd2  mov     r9, r13
0x180025fd5  mov     r10, r15
0x180025fd8  test    rcx, rcx
0x180025fdb  jz      short loc_180025FFB
0x180025fdd  movzx   edx, word ptr [rax]
0x180025fe0  test    dx, dx
0x180025fe3  jz      short loc_180025FFB
0x180025fe5  mov     [r9], dx
0x180025fe9  add     rax, r12
0x180025fec  add     r9, r12
0x180025fef  dec     rcx
0x180025ff2  inc     r10
0x180025ff5  sub     r8, 1
0x180025ff9  jnz     short loc_180025FD8
0x180025ffb  test    r8, r8
0x180025ffe  lea     rdx, [r10-1]
0x180026002  mov     rax, r8
0x180026005  lea     rcx, [r9-2]
0x180026009  cmovnz  rdx, r10
0x18002600d  neg     rax
0x180026010  sbb     ebx, ebx
0x180026012  not     ebx
0x180026014  and     ebx, 8007007Ah
0x18002601a  lea     r10, ds:0[rdx*2]
0x180026022  test    r8, r8
0x180026025  cmovnz  rcx, r9
0x180026029  add     r10, r13
0x18002602c  sub     rdi, rdx
0x18002602f  mov     [rbp+47h+pv], r10
0x180026033  mov     qword ptr [rbp+47h+var_A0], rdi
0x180026037  mov     [rcx], r15w
0x18002603b  test    ebx, ebx
0x18002603d  js      loc_18002634F
0x180026043  cmp     r14, r12
0x180026046  jb      loc_18002634F
0x18002604c  mov     r8, [rbp+47h+pvar+8]; wchar_t *
0x180026050  movzx   eax, word ptr [r8]
0x180026054  sub     ax, 41h ; 'A'
0x180026058  cmp     ax, 39h ; '9'
0x18002605c  ja      short loc_18002606E
0x18002605e  mov     rcx, 3FFFFFF03FFFFFFh
0x180026068  bt      rcx, rax
0x18002606c  jb      short loc_180026092
0x18002606e  movzx   eax, word ptr [r8]
0x180026072  mov     ecx, 0DFh
0x180026077  add     ax, cx
0x18002607a  cmp     ax, 19h
0x18002607e  jbe     short loc_180026092
0x180026080  movzx   eax, word ptr [r8]
0x180026084  mov     ecx, 0BFh
0x180026089  add     ax, cx
0x18002608c  cmp     ax, 19h
0x180026090  ja      short loc_1800260A6
0x180026092  cmp     word ptr [r8+2], 3Ah ; ':'
0x180026098  jz      short loc_180026102
0x18002609a  mov     eax, 0FF1Ah
0x18002609f  cmp     [r8+2], ax
0x1800260a4  jz      short loc_180026102
0x1800260a6  movzx   ecx, word ptr [r8]; wchar_t
0x1800260aa  call    ?IsReverseSolidus@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsReverseSolidus(wchar_t)
0x1800260af  test    al, al
0x1800260b1  jz      loc_18002634F
0x1800260b7  movzx   ecx, word ptr [r8+2]; wchar_t
0x1800260bc  call    ?IsReverseSolidus@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsReverseSolidus(wchar_t)
0x1800260c1  test    al, al
0x1800260c3  jz      loc_18002634F
0x1800260c9  lea     rax, [rbp+47h+var_A0]
0x1800260cd  mov     rdx, rdi; unsigned __int64
0x1800260d0  lea     r9, [rbp+47h+pv]; wchar_t **
0x1800260d4  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1800260d9  lea     r8, asc_1800A2A28; "//"
0x1800260e0  mov     rcx, r10; wchar_t *
0x1800260e3  mov     rsi, r12
0x1800260e6  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800260eb  jmp     short loc_18002612A
0x1800260ed  mov     ebx, esi
0x1800260ef  test    rdi, rdi
0x1800260f2  jz      loc_18002603B
0x1800260f8  mov     [r13+0], r15w
0x1800260fd  jmp     loc_18002634F
0x180026102  lea     rax, [rbp+47h+var_A0]
0x180026106  mov     [rsp+100h+var_D0], r15d; unsigned int
0x18002610b  mov     [rsp+100h+var_D8], rax; unsigned __int64 *
0x180026110  mov     r9, r12; unsigned __int64
0x180026113  lea     rax, [rbp+47h+pv]
0x180026117  mov     rdx, rdi; unsigned __int64
0x18002611a  mov     rcx, r10; pszDest
0x18002611d  mov     [rsp+100h+var_E0], rax; wchar_t **
0x180026122  mov     rsi, r12
0x180026125  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x18002612a  mov     ebx, eax
0x18002612c  test    eax, eax
0x18002612e  js      loc_18002634F
0x180026134  mov     r8, [rbp+47h+pvar+8]
0x180026138  mov     r12b, r15b
0x18002613b  mov     rdi, rsi
0x18002613e  test    r15b, r15b
0x180026141  jnz     loc_1800261EB
0x180026147  cmp     rdi, r14
0x18002614a  jnb     loc_1800261E2
0x180026150  movzx   ecx, word ptr [r8+rdi*2]; wchar_t
0x180026155  call    ?IsReverseSolidus@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsReverseSolidus(wchar_t)
0x18002615a  test    al, al
0x18002615c  jz      short loc_1800261C2
0x18002615e  mov     rdx, qword ptr [rbp+47h+var_A0]; unsigned __int64
0x180026162  lea     rax, [rbp+47h+var_A0]
0x180026166  mov     rcx, [rbp+47h+pv]; pszDest
0x18002616a  lea     r8, [r8+rsi*2]; wchar_t *
0x18002616e  mov     [rsp+100h+var_D0], 0; unsigned int
0x180026176  mov     r9, rdi
0x180026179  mov     [rsp+100h+var_D8], rax; unsigned int
0x18002617e  sub     r9, rsi; unsigned __int64
0x180026181  lea     rax, [rbp+47h+pv]
0x180026185  mov     [rsp+100h+var_E0], rax; wchar_t **
0x18002618a  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x18002618f  mov     ebx, eax
0x180026191  test    eax, eax
0x180026193  js      short loc_1800261B8
0x180026195  mov     rdx, qword ptr [rbp+47h+var_A0]; unsigned __int64
0x180026199  lea     rax, [rbp+47h+var_A0]
0x18002619d  mov     rcx, [rbp+47h+pv]; wchar_t *
0x1800261a1  lea     r9, [rbp+47h+pv]; wchar_t **
0x1800261a5  lea     r8, asc_1800A2A80; "/"
0x1800261ac  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1800261b1  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800261b6  mov     ebx, eax
0x1800261b8  mov     r8, [rbp+47h+pvar+8]
0x1800261bc  lea     rsi, [rdi+1]
0x1800261c0  jmp     short loc_1800261D7
0x1800261c2  call    ?IsStar@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsStar(wchar_t)
0x1800261c7  test    al, al
0x1800261c9  jnz     short loc_1800261D4
0x1800261cb  call    ?IsQuestionMark@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsQuestionMark(wchar_t)
0x1800261d0  test    al, al
0x1800261d2  jz      short loc_1800261D7
0x1800261d4  mov     r15b, 1
0x1800261d7  inc     rdi
0x1800261da  test    ebx, ebx
0x1800261dc  jns     loc_18002613E
0x1800261e2  test    ebx, ebx
0x1800261e4  jns     short loc_1800261EB
0x1800261e6  mov     eax, [rbp+47h+var_A8]
0x1800261e9  jmp     short loc_1800261F3
0x1800261eb  mov     eax, [rbp+47h+var_A8]
0x1800261ee  cmp     eax, 1
0x1800261f1  jz      short loc_180026204
0x1800261f3  lea     rdi, PKEY_SCOPE_PSEUDOPROPERTY
0x1800261fa  cmp     eax, 0Bh
0x1800261fd  jnz     short loc_180026262
0x1800261ff  test    r15b, r15b
0x180026202  jnz     short loc_180026262
0x180026204  lea     rdx, PKEY_ItemFolderPathDisplay
0x18002620b  lea     rcx, [rbp+47h+var_50]
0x18002620f  lea     rdi, PKEY_DIRECTORY_PSEUDOPROPERTY
0x180026216  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002621b  xor     r15d, r15d
0x18002621e  test    eax, eax
0x180026220  jz      short loc_180026265
0x180026222  mov     rdx, qword ptr [rbp+47h+var_A0]; unsigned __int64
0x180026226  lea     rax, [rbp+47h+var_A0]
0x18002622a  mov     rcx, [rbp+47h+pv]; pszDest
0x18002622e  lea     r8, [r8+rsi*2]; wchar_t *
0x180026232  mov     [rsp+100h+var_D0], r15d; unsigned int
0x180026237  mov     r9, r14
0x18002623a  mov     [rsp+100h+var_D8], rax; unsigned __int64 *
0x18002623f  sub     r9, rsi; unsigned __int64
0x180026242  lea     rax, [rbp+47h+pv]
0x180026246  mov     [rsp+100h+var_E0], rax; wchar_t **
0x18002624b  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x180026250  mov     ebx, eax
0x180026252  test    eax, eax
0x180026254  js      loc_18002634F
0x18002625a  mov     r12b, 1
0x18002625d  mov     rsi, r14
0x180026260  jmp     short loc_18002626D
0x180026262  xor     r15d, r15d
0x180026265  test    ebx, ebx
0x180026267  js      loc_18002634F
0x18002626d  test    rsi, rsi
0x180026270  jz      loc_18002634F
0x180026276  mov     [rbp+47h+pv], r15
0x18002627a  lea     rcx, [rbp+47h+pv]
0x18002627e  mov     r15, [rbp+47h+var_68]
0x180026282  mov     r9, r13
0x180026285  mov     [rsp+100h+var_C8], rcx
0x18002628a  mov     r8d, 1
0x180026290  lea     rcx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180026297  mov     rdx, rdi
0x18002629a  mov     qword ptr [rsp+100h+var_D0], rcx
0x18002629f  lea     rcx, cchOriginalDestLength
0x1800262a6  mov     rax, [r15]
0x1800262a9  mov     dword ptr [rsp+100h+var_D8], 1
0x1800262b1  mov     [rsp+100h+var_E0], rcx
0x1800262b6  mov     rcx, r15
0x1800262b9  mov     rax, [rax+58h]
0x1800262bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262c2  mov     ebx, eax
0x1800262c4  test    eax, eax
0x1800262c6  js      loc_18002634C
0x1800262cc  test    r12b, r12b
0x1800262cf  jnz     short loc_180026320
  ... truncated ...
```
