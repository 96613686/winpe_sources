# CMapi2DirFilter::OpenFolderByName(IMAPIFolder *,TLMString<192,64,32767> const &,IMAPIFolder * *)

- ea: `0x180025190`
- end: `0x180025589`
- name: `?OpenFolderByName@CMapi2DirFilter@@QEAAJPEAUIMAPIFolder@@AEBV?$TLMString@$0MA@$0EA@$0HPPP@@@PEAPEAU2@@Z`
- size: `1017`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180024824`

## callees

- `0x180002300`
- `0x18000e684`
- `0x18000ea18`
- `0x18000f930`
- `0x18000fd58`
- `0x180011884`
- `0x18001269c`
- `0x180014014`
- `0x180014448`
- `0x1800228c0`
- `0x180025190`
- `0x18002837c`
- `0x180028b94`
- `0x180036e7c`
- `0x180037388`
- `0x18003f010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18002555b`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18002555b`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800253d8`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800253d8`

## string_xrefs

- `0x180025257`: `OpenFolderbyName failure from GetHierarchyTable`
- `0x18002528d`: `OpenFolderbyName failure from SetColumns`
- `0x180025305`: `OpenFolderbyName failure from FindRow(BOOKMARK_BEGINING)`
- `0x1800253aa`: `OpenFolderbyName failure from QueryRows`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMapi2DirFilter::OpenFolderByName(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rax
  __int64 *v8; // rax
  unsigned int v9; // eax
  int v10; // ebx
  unsigned int v11; // eax
  int v12; // eax
  struct _SRowSet *v13; // rcx
  unsigned int v14; // eax
  bool v15; // zf
  int v16; // ebx
  LPSPropValue lpProps; // rdx
  struct _SPropValue *v19; // rcx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  LPSRowSet lpRows; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v27[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  _QWORD *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  _DWORD v34[4]; // [rsp+C0h] [rbp-40h] BYREF
  void **v35; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v36; // [rsp+D8h] [rbp-28h]
  __int64 v37; // [rsp+E0h] [rbp-20h]
  __int16 v38; // [rsp+E8h] [rbp-18h] BYREF

  v36 = &v38;
  v37 = 193;
  v38 = 0;
  v35 = &TLMString<192,64,32767>::`vftable';
  *a4 = 0;
  v7 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         (__int64)&v26,
         *(const wchar_t **)(a3 + 8));
  v8 = (__int64 *)DecodeFolderName(&pv, v7);
  CLMString::operator=((__int64)&v35, *v8);
  ATL::CStringData::Release((ATL::CStringData *)((char *)pv - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  v21 = 0;
  v24 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 120LL))(a2, 0, &v21);
  v10 = v9;
  if ( !v9 || (CLogger::Error(v9, L"OpenFolderbyName failure from GetHierarchyTable"), v10 >= 0) )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v21 + 56LL))(v21, qword_180048CB0, 2);
    v10 = v11;
    if ( v11 )
      CLogger::Error(v11, L"OpenFolderbyName failure from SetColumns");
    else
      v10 = 0;
  }
  v29 = 4;
  v33 = 0;
  v27[0] = 805371935;
  v27[2] = 0;
  v32 = v27;
  v30 = 4;
  v31 = 805371935;
  v27[1] = v36;
  if ( v10 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 104LL))(v21, &v29, 0, 0);
    v10 = v12;
    if ( !v12 )
    {
      v10 = 0;
      goto LABEL_11;
    }
    CLogger::Warning(v12, L"OpenFolderbyName failure from FindRow(BOOKMARK_BEGINING)");
  }
  if ( v10 == -2147221233 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pv);
    LODWORD(v29) = 4;
    v30 = 4;
    v31 = 805371934;
    *(_DWORD *)v32 = 805371934;
    v32[1] = pv;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 104LL))(v21, &v29, 0, 0);
    ATL::CStringData::Release((ATL::CStringData *)((char *)pv - 24));
  }
LABEL_11:
  v13 = 0;
  lpRows = 0;
  if ( v10 < 0 )
    goto LABEL_15;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v21 + 152LL))(v21, 1, 0, &lpRows);
  v10 = v14;
  if ( v14 )
  {
    CLogger::Error(v14, L"OpenFolderbyName failure from QueryRows");
    if ( v10 < 0 )
    {
      v13 = lpRows;
LABEL_15:
      v15 = v10 == -2147221237;
      v16 = -2147216895;
      if ( !v15 )
        goto LABEL_17;
      goto LABEL_16;
    }
  }
  v13 = lpRows;
  if ( !lpRows || !lpRows->cRows )
  {
LABEL_16:
    v16 = -2147216890;
    goto LABEL_17;
  }
  lpProps = lpRows->aRow[0].lpProps;
  if ( lpProps[1].ulPropTag == 268370178 )
  {
    v25 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPBYTE, _QWORD, int, int *, __int64 *))(*(_QWORD *)a2 + 128LL))(
            a2,
            lpProps[1].Value.ul,
            lpProps[1].Value.bin.lpb,
            0,
            8,
            &v25,
            &v24);
    if ( v16 >= 0 )
    {
      LODWORD(v26) = 0;
      pv = 0;
      v34[0] = 2;
      v34[1] = 245563650;
      v34[2] = 268370178;
      v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, __int64 *, LPVOID *))(*(_QWORD *)v24 + 40LL))(
              v24,
              v34,
              0,
              &v26,
              &pv);
      v22 = v16;
      v19 = (struct _SPropValue *)pv;
      if ( v16 >= 0 )
      {
        if ( *(_DWORD *)pv == 245563650 )
        {
          TextizeBinary(*((_QWORD *)pv + 2), *((unsigned int *)pv + 2), a1 + 9400);
          v19 = (struct _SPropValue *)pv;
        }
        if ( v19[1].ulPropTag == 268370178 && !*(_DWORD *)(a1 + 9700) )
        {
          CEntryId::CEntryId((CEntryId *)v28, v19 + 1, &v22);
          v16 = v22;
          if ( v22 >= 0 )
            v16 = ComputeItemDeletedAndHiddenState(
                    *(struct CMapiStore **)(a1 + 9336),
                    (struct CEntryId *)v28,
                    (int *)(a1 + 9700),
                    (unsigned int *)(a1 + 9704));
          CEntryId::FreeBuffer((CEntryId *)v28);
          v19 = (struct _SPropValue *)pv;
        }
      }
      MAPIFreeBuffer(v19);
    }
    if ( v16 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      *a4 = v24;
    }
    v13 = lpRows;
  }
  else
  {
    v16 = -2147467259;
  }
LABEL_17:
  if ( v13 )
    FreeProws(v13);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v24);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v21);
  TLMString<192,64,32767>::~TLMString<192,64,32767>((wchar_t *)&v35);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180025190  push    rbp
0x180025192  push    rbx
0x180025193  push    rsi
0x180025194  push    rdi
0x180025195  push    r12
0x180025197  push    r14
0x180025199  push    r15
0x18002519b  lea     rbp, [rsp-180h]
0x1800251a3  sub     rsp, 280h
0x1800251aa  mov     rax, cs:__security_cookie
0x1800251b1  xor     rax, rsp
0x1800251b4  mov     [rbp+1B0h+var_40], rax
0x1800251bb  mov     r14, r9
0x1800251be  mov     rsi, rdx
0x1800251c1  mov     rdi, rcx
0x1800251c4  lea     rax, [rbp+1B0h+var_1C8]
0x1800251c8  mov     [rbp+1B0h+var_1D8], rax
0x1800251cc  mov     [rbp+1B0h+var_1D0], 0C1h
0x1800251d4  xor     r15d, r15d
0x1800251d7  mov     [rbp+1B0h+var_1C8], r15w
0x1800251dc  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x1800251e3  mov     [rbp+1B0h+var_1E0], rax
0x1800251e7  mov     [r9], r15
0x1800251ea  mov     rdx, [r8+8]
0x1800251ee  lea     rcx, [rsp+2B0h+var_240]
0x1800251f3  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1800251f8  nop
0x1800251f9  mov     rdx, rax
0x1800251fc  lea     rcx, [rsp+2B0h+pv]
0x180025201  call    ?DecodeFolderName@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEBV12@@Z; DecodeFolderName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180025206  nop
0x180025207  mov     rdx, [rax]
0x18002520a  lea     rcx, [rbp+1B0h+var_1E0]
0x18002520e  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180025213  nop
0x180025214  mov     rcx, [rsp+2B0h+pv]
0x180025219  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002521d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025222  nop
0x180025223  mov     rcx, [rsp+2B0h+var_240]
0x180025228  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002522c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025231  mov     [rsp+2B0h+var_268], r15
0x180025236  mov     [rsp+2B0h+var_250], r15
0x18002523b  mov     rax, [rsi]
0x18002523e  lea     r8, [rsp+2B0h+var_268]
0x180025243  xor     edx, edx
0x180025245  mov     rcx, rsi
0x180025248  mov     rax, [rax+78h]
0x18002524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025251  mov     ebx, eax
0x180025253  test    eax, eax
0x180025255  jz      short loc_180025269
0x180025257  lea     rdx, aOpenfolderbyna; "OpenFolderbyName failure from GetHierar"...
0x18002525e  mov     ecx, eax; int
0x180025260  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180025265  test    ebx, ebx
0x180025267  js      short loc_1800252A0
0x180025269  mov     rcx, [rsp+2B0h+var_268]
0x18002526e  mov     rax, [rcx]
0x180025271  mov     r8d, 2
0x180025277  lea     rdx, qword_180048CB0
0x18002527e  mov     rax, [rax+38h]
0x180025282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025287  mov     ebx, eax
0x180025289  test    eax, eax
0x18002528b  jz      short loc_18002529D
0x18002528d  lea     rdx, aOpenfolderbyna_2; "OpenFolderbyName failure from SetColumn"...
0x180025294  mov     ecx, eax; int
0x180025296  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002529b  jmp     short loc_1800252A0
0x18002529d  mov     ebx, r15d
0x1800252a0  mov     [rbp+1B0h+var_210], 4
0x1800252a8  mov     [rbp+1B0h+var_1F8], r15
0x1800252ac  mov     [rsp+2B0h+var_238], 3001001Fh
0x1800252b5  mov     [rbp+1B0h+var_228], r15
0x1800252b9  lea     rax, [rsp+2B0h+var_238]
0x1800252be  mov     [rbp+1B0h+var_200], rax
0x1800252c2  mov     r12d, 4
0x1800252c8  mov     [rbp+1B0h+var_208], r12d
0x1800252cc  mov     eax, 3001001Fh
0x1800252d1  mov     [rbp+1B0h+var_204], eax
0x1800252d4  mov     rdx, [rbp+1B0h+var_1D8]
0x1800252d8  mov     [rbp+1B0h+var_230], rdx
0x1800252dc  test    ebx, ebx
0x1800252de  js      short loc_180025317
0x1800252e0  mov     rcx, [rsp+2B0h+var_268]
0x1800252e5  mov     rax, [rcx]
0x1800252e8  xor     r9d, r9d
0x1800252eb  xor     r8d, r8d
0x1800252ee  lea     rdx, [rbp+1B0h+var_210]
0x1800252f2  mov     rax, [rax+68h]
0x1800252f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252fb  mov     ebx, eax
0x1800252fd  test    eax, eax
0x1800252ff  jz      loc_180025421
0x180025305  lea     rdx, aOpenfolderbyna_0; "OpenFolderbyName failure from FindRow(B"...
0x18002530c  mov     ecx, eax; int
0x18002530e  call    ?Warning@CLogger@@SAXJPEB_WZZ; CLogger::Warning(long,wchar_t const *,...)
0x180025313  mov     rdx, [rbp+1B0h+var_1D8]
0x180025317  cmp     ebx, 8004010Fh
0x18002531d  jnz     short loc_180025378
0x18002531f  lea     rcx, [rsp+2B0h+pv]
0x180025324  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(wchar_t const *)
0x180025329  nop
0x18002532a  mov     dword ptr [rbp+1B0h+var_210], r12d
0x18002532e  mov     [rbp+1B0h+var_208], r12d
0x180025332  mov     ecx, 3001001Eh
0x180025337  mov     [rbp+1B0h+var_204], ecx
0x18002533a  mov     rax, [rbp+1B0h+var_200]
0x18002533e  mov     [rax], ecx
0x180025340  mov     rcx, [rbp+1B0h+var_200]
0x180025344  mov     rax, [rsp+2B0h+pv]
0x180025349  mov     [rcx+8], rax
0x18002534d  mov     rcx, [rsp+2B0h+var_268]
0x180025352  mov     rax, [rcx]
0x180025355  xor     r9d, r9d
0x180025358  xor     r8d, r8d
0x18002535b  lea     rdx, [rbp+1B0h+var_210]
0x18002535f  mov     rax, [rax+68h]
0x180025363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025368  mov     ebx, eax
0x18002536a  mov     rcx, [rsp+2B0h+pv]
0x18002536f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025373  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025378  mov     rcx, r15
0x18002537b  mov     [rsp+2B0h+lpRows], rcx
0x180025380  test    ebx, ebx
0x180025382  js      short loc_1800253C1
0x180025384  mov     rcx, [rsp+2B0h+var_268]
0x180025389  mov     rax, [rcx]
0x18002538c  lea     r9, [rsp+2B0h+lpRows]
0x180025391  xor     r8d, r8d
0x180025394  lea     edx, [r8+1]
0x180025398  mov     rax, [rax+98h]
0x18002539f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253a4  mov     ebx, eax
0x1800253a6  test    eax, eax
0x1800253a8  jz      short loc_180025429
0x1800253aa  lea     rdx, aOpenfolderbyna_1; "OpenFolderbyName failure from QueryRows"
0x1800253b1  mov     ecx, eax; int
0x1800253b3  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800253b8  test    ebx, ebx
0x1800253ba  jns     short loc_180025429
0x1800253bc  mov     rcx, [rsp+2B0h+lpRows]; lpRows
0x1800253c1  cmp     ebx, 8004010Bh
0x1800253c7  mov     ebx, 80041201h
0x1800253cc  jnz     short loc_1800253D3
0x1800253ce  mov     ebx, 80041206h
0x1800253d3  test    rcx, rcx
0x1800253d6  jz      short loc_1800253DF
0x1800253d8  call    cs:__imp_FreeProws
0x1800253de  nop
0x1800253df  lea     rcx, [rsp+2B0h+var_250]
0x1800253e4  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800253e9  nop
0x1800253ea  lea     rcx, [rsp+2B0h+var_268]
0x1800253ef  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800253f4  nop
0x1800253f5  lea     rcx, [rbp+1B0h+var_1E0]
0x1800253f9  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x1800253fe  mov     eax, ebx
0x180025400  mov     rcx, [rbp+1B0h+var_40]
0x180025407  xor     rcx, rsp; StackCookie
0x18002540a  call    __security_check_cookie
0x18002540f  add     rsp, 280h
0x180025416  pop     r15
0x180025418  pop     r14
0x18002541a  pop     r12
0x18002541c  pop     rdi
0x18002541d  pop     rsi
0x18002541e  pop     rbx
0x18002541f  pop     rbp
0x180025420  retn
0x180025421  mov     ebx, r15d
0x180025424  jmp     loc_180025378
0x180025429  mov     rcx, [rsp+2B0h+lpRows]
0x18002542e  test    rcx, rcx
0x180025431  jz      short loc_1800253CE
0x180025433  cmp     [rcx], r15d
0x180025436  jz      short loc_1800253CE
0x180025438  mov     rdx, [rcx+10h]
0x18002543c  mov     r12d, 0FFF0102h
0x180025442  cmp     [rdx+18h], r12d
0x180025446  jz      short loc_18002544F
0x180025448  mov     ebx, 80004005h
0x18002544d  jmp     short loc_1800253D3
0x18002544f  mov     [rsp+2B0h+var_248], r15d
0x180025454  mov     rax, [rsi]
0x180025457  lea     rcx, [rsp+2B0h+var_250]
0x18002545c  mov     [rsp+2B0h+var_280], rcx
0x180025461  lea     rcx, [rsp+2B0h+var_248]
0x180025466  mov     [rsp+2B0h+var_288], rcx
0x18002546b  mov     dword ptr [rsp+2B0h+var_290], 8
0x180025473  xor     r9d, r9d
0x180025476  mov     r8, [rdx+28h]
0x18002547a  mov     edx, [rdx+20h]
0x18002547d  mov     rcx, rsi
0x180025480  mov     rax, [rax+80h]
0x180025487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002548c  mov     ebx, eax
0x18002548e  test    eax, eax
0x180025490  js      loc_180025561
0x180025496  mov     dword ptr [rsp+2B0h+var_240], r15d
0x18002549b  mov     [rsp+2B0h+pv], r15
0x1800254a0  mov     [rbp+1B0h+var_1F0], 2
0x1800254a7  mov     esi, 0EA30102h
0x1800254ac  mov     [rbp+1B0h+var_1EC], esi
0x1800254af  mov     [rbp+1B0h+var_1E8], r12d
0x1800254b3  mov     rcx, [rsp+2B0h+var_250]
0x1800254b8  mov     rax, [rcx]
0x1800254bb  lea     rdx, [rsp+2B0h+pv]
0x1800254c0  mov     [rsp+2B0h+var_290], rdx
0x1800254c5  lea     r9, [rsp+2B0h+var_240]
0x1800254ca  xor     r8d, r8d
0x1800254cd  lea     rdx, [rbp+1B0h+var_1F0]
0x1800254d1  mov     rax, [rax+28h]
0x1800254d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254da  mov     ebx, eax
0x1800254dc  mov     [rsp+2B0h+var_260], eax
0x1800254e0  mov     rcx, [rsp+2B0h+pv]
0x1800254e5  test    eax, eax
0x1800254e7  js      short loc_18002555B
0x1800254e9  cmp     [rcx], esi
0x1800254eb  jnz     short loc_180025505
0x1800254ed  lea     r8, [rdi+24B8h]
0x1800254f4  mov     edx, [rcx+8]
0x1800254f7  mov     rcx, [rcx+10h]
0x1800254fb  call    ?TextizeBinary@@YAXPEAEKAEAV?$TLMString@$0IA@$0IA@$0CAAA@@@@Z; TextizeBinary(uchar *,ulong,TLMString<128,128,8192> &)
0x180025500  mov     rcx, [rsp+2B0h+pv]
0x180025505  lea     rdx, [rcx+18h]; struct _SPropValue *
0x180025509  cmp     [rdx], r12d
0x18002550c  jnz     short loc_18002555B
0x18002550e  lea     rsi, [rdi+25E4h]
0x180025515  cmp     [rsi], r15d
0x180025518  jnz     short loc_18002555B
0x18002551a  lea     r8, [rsp+2B0h+var_260]; int *
0x18002551f  lea     rcx, [rbp+1B0h+var_220]; this
0x180025523  call    ??0CEntryId@@QEAA@PEAU_SPropValue@@PEAJ@Z; CEntryId::CEntryId(_SPropValue *,long *)
0x180025528  nop
0x180025529  mov     ebx, [rsp+2B0h+var_260]
0x18002552d  test    ebx, ebx
0x18002552f  js      short loc_18002554D
0x180025531  lea     r9, [rdi+25E8h]; unsigned int *
0x180025538  mov     r8, rsi; int *
0x18002553b  lea     rdx, [rbp+1B0h+var_220]; struct CEntryId *
0x18002553f  mov     rcx, [rdi+2478h]; this
0x180025546  call    ?ComputeItemDeletedAndHiddenState@@YAJPEAVCMapiStore@@AEAVCEntryId@@PEAHPEAK@Z; ComputeItemDeletedAndHiddenState(CMapiStore *,CEntryId &,int *,ulong *)
0x18002554b  mov     ebx, eax
0x18002554d  lea     rcx, [rbp+1B0h+var_220]; this
0x180025551  call    ?FreeBuffer@CEntryId@@AEAAXXZ; CEntryId::FreeBuffer(void)
0x180025556  mov     rcx, [rsp+2B0h+pv]; pv
0x18002555b  call    cs:__imp_MAPIFreeBuffer
0x180025561  test    ebx, ebx
0x180025563  js      short loc_18002557E
0x180025565  mov     rcx, [rsp+2B0h+var_250]
0x18002556a  mov     rax, [rcx]
0x18002556d  mov     rax, [rax+8]
0x180025571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025576  mov     rax, [rsp+2B0h+var_250]
0x18002557b  mov     [r14], rax
0x18002557e  mov     rcx, [rsp+2B0h+lpRows]
0x180025583  jmp     loc_1800253D3
```
