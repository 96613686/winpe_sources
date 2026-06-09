# CMapi2DirFilter::EnumerateFolders(IMAPIFolder *,CMapiUrl &,long (*)(void *,TLMString<192,64,32767> const &,int,POLICY_RESULT_ID,int,int),void *)

- ea: `0x1800231d4`
- end: `0x1800235dd`
- name: `?EnumerateFolders@CMapi2DirFilter@@SAJPEAUIMAPIFolder@@AEAVCMapiUrl@@P6AJPEAXAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HW4POLICY_RESULT_ID@@HH@Z2@Z`
- size: `1033`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024824`

## callees

- `0x180002300`
- `0x18000da40`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000e8ac`
- `0x18000ea18`
- `0x18000ebac`
- `0x18000f1c4`
- `0x18000fd58`
- `0x1800113ec`
- `0x180011884`
- `0x1800122d8`
- `0x18001359c`
- `0x180014014`
- `0x180014448`
- `0x1800185d8`
- `0x180022b28`
- `0x180022cd0`
- `0x1800230d4`
- `0x1800231d4`
- `0x180029fb4`
- `0x18002b6f4`
- `0x18002beb0`
- `0x18003f010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18002356e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18002356e`

## string_xrefs

- `0x180023598`: `OpenFolderbyName failure from QueryRows`
- `0x180023586`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMapi2DirFilter::EnumerateFolders(__int64 a1, _QWORD *a2, __int64 a3, int a4)
{
  int v7; // eax
  int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  ULONG v12; // r14d
  struct _SRowSet *v13; // rcx
  ULONG cRows; // eax
  LPSPropValue lpProps; // rbx
  const CHAR *lpszA; // r15
  wchar_t *v17; // r8
  __int64 v18; // rbx
  unsigned int v19; // esi
  __int64 v20; // rax
  __int64 v21; // rdx
  volatile signed __int32 *v22; // rcx
  wchar_t *v23; // rbx
  int *v24; // rsi
  volatile signed __int32 *v25; // rbx
  const wchar_t **URL; // rax
  _QWORD *v27; // rax
  ATL::CStringData *v28; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  LPSRowSet lpRows; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v39[12]; // [rsp+70h] [rbp-90h] BYREF
  void **v40; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int16 v43; // [rsp+E8h] [rbp-18h] BYREF
  void **v44; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v45; // [rsp+138h] [rbp+38h]
  int v46; // [rsp+140h] [rbp+40h]
  int v47; // [rsp+144h] [rbp+44h]
  _BYTE v48[72]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t v49; // [rsp+190h] [rbp+90h] BYREF
  __int64 v50; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  v33 = 0;
  CLogger::Info(L"CMapi2DirFilter::EnumerateFolders");
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a1 + 120LL))(a1, 0, &v33);
  v8 = v7;
  if ( !v7 || (CLogger::Error(v7, L"EnumerateFolders failure from GetHierarchyTable"), v8 >= 0) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v33 + 56LL))(v33, qword_180048CA0, 2);
    v8 = v9;
    if ( v9 )
      CLogger::Error(v9, L"EnumerateFolders failure from SetColumns");
  }
  v31 = 0;
  if ( v8 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v33 + 72LL))(v33, 0, &v31);
    v8 = v10;
    if ( v10 )
      CLogger::Error(v10, L"EnumerateFolders failure from GetRowCount");
  }
  CLogger::Info(L"CMapi2DirFilter::EnumerateFolders cRowCount=%d", v31);
  lpRows = 0;
  while ( v8 >= 0 && v31 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPSRowSet *))(*(_QWORD *)v33 + 152LL))(
            v33,
            v31,
            0,
            &lpRows);
    v8 = v11;
    if ( v11 < 0 )
    {
      CLogger::Error(v11, L"OpenFolderbyName failure from QueryRows");
      break;
    }
    v12 = 0;
    v13 = lpRows;
    cRows = lpRows->cRows;
    if ( lpRows->cRows )
    {
      while ( 1 )
      {
        lpProps = v13->aRow[v12].lpProps;
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v32);
        v41 = (const wchar_t *)&v43;
        v42 = 33;
        v43 = 0;
        v40 = &TLMString<32,32,256>::`vftable';
        if ( lpProps[1].ulPropTag == 805371935 )
          break;
        if ( lpProps->ulPropTag == 805371934 )
        {
          lpszA = lpProps->Value.lpszA;
          v44 = &CLMString::`vftable';
          v17 = (wchar_t *)v48;
          v45 = (wchar_t *)v48;
          v46 = 33;
          if ( !lpszA )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
              (const char *)0x80004003LL,
              v30);
          v18 = -1;
          do
            ++v18;
          while ( lpszA[v18] );
          v19 = v18 + 1;
          if ( (unsigned int)(v18 + 1) > 0x21 )
          {
            CLMString::GrowInConstructor((CLMString *)&v44, v19);
            v17 = v45;
          }
          v47 = MultiByteToWideCharSZ(lpszA, v18, v17, v19);
          v44 = &TLMString<32,32,256>::`vftable';
          CLMString::operator=((__int64)&v40, (__int64)v45);
          TLMString<32,32,256>::~TLMString<32,32,256>(&v44);
          goto LABEL_22;
        }
        TLMString<32,32,256>::~TLMString<32,32,256>(&v40);
        v28 = (ATL::CStringData *)(v32 - 12);
LABEL_29:
        ATL::CStringData::Release(v28);
        ++v12;
        v13 = lpRows;
        cRows = lpRows->cRows;
        if ( v12 >= lpRows->cRows )
          goto LABEL_30;
      }
      CLMString::operator=((__int64)&v40, lpProps[1].Value.cur.int64);
LABEL_22:
      v20 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
              (__int64)&v36,
              v41);
      v21 = *(_QWORD *)EncodeFolderName(&v35, v20);
      v22 = (volatile signed __int32 *)(v21 - 24);
      v23 = v32;
      v24 = (int *)(v32 - 12);
      if ( (wchar_t *)(v21 - 24) != v32 - 12 )
      {
        if ( v24[4] >= 0 && *(_QWORD *)v22 == *(_QWORD *)v24 )
        {
          v25 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v22);
          ATL::CStringData::Release((ATL::CStringData *)v24);
          v23 = (wchar_t *)(v25 + 6);
          v32 = v23;
        }
        else
        {
          ATL::CSimpleStringT<wchar_t,0>::SetString(&v32, v21, *(unsigned int *)(v21 - 16));
          v23 = v32;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      TLMString<32,32,256>::~TLMString<32,32,256>(&v40);
      URL = (const wchar_t **)CMapiUrl::GetURL(a2, &v37);
      CMapiUrl::CMapiUrl((CMapiUrl *)v39, *URL);
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      CMapiUrl::AddFolder((CMapiUrl *)v39, v23);
      v27 = CMapiUrl::GetURL(v39, &v38);
      TLMString<192,64,32767>::TLMString<192,64,32767>(&v49, *v27);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      CMapi2DirFilter::AddUrlCallback(a4, (unsigned int)&v49, 1, 0, 0);
      CLogger::Info(L"CMapi2DirFilter::EnumerateFolders i=%d, url=%s", v12, v50);
      TLMString<192,64,32767>::~TLMString<192,64,32767>(&v49);
      CMapiUrl::~CMapiUrl((CMapiUrl *)v39);
      v28 = (ATL::CStringData *)(v23 - 12);
      goto LABEL_29;
    }
LABEL_30:
    v31 -= cRows;
    FreeProws(v13);
  }
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v33);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800231d4  mov     [rsp-8+arg_10], rbx
0x1800231d9  push    rbp
0x1800231da  push    rsi
0x1800231db  push    rdi
0x1800231dc  push    r12
0x1800231de  push    r13
0x1800231e0  push    r14
0x1800231e2  push    r15
0x1800231e4  lea     rbp, [rsp-240h]
0x1800231ec  sub     rsp, 340h
0x1800231f3  mov     rax, cs:__security_cookie
0x1800231fa  xor     rax, rsp
0x1800231fd  mov     [rbp+270h+var_40], rax
0x180023204  mov     r13, r9
0x180023207  mov     r12, rdx
0x18002320a  mov     rbx, rcx
0x18002320d  xor     esi, esi
0x18002320f  mov     [rsp+370h+var_330], rsi
0x180023214  lea     rcx, aCmapi2dirfilte_1; "CMapi2DirFilter::EnumerateFolders"
0x18002321b  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180023220  mov     rax, [rbx]
0x180023223  lea     r8, [rsp+370h+var_330]
0x180023228  xor     edx, edx
0x18002322a  mov     rcx, rbx
0x18002322d  mov     rax, [rax+78h]
0x180023231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023236  mov     edi, eax
0x180023238  test    eax, eax
0x18002323a  jz      short loc_18002324E
0x18002323c  lea     rdx, aEnumeratefolde; "EnumerateFolders failure from GetHierar"...
0x180023243  mov     ecx, eax; int
0x180023245  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002324a  test    edi, edi
0x18002324c  js      short loc_180023280
0x18002324e  mov     rcx, [rsp+370h+var_330]
0x180023253  mov     rax, [rcx]
0x180023256  mov     r8d, 2
0x18002325c  lea     rdx, qword_180048CA0
0x180023263  mov     rax, [rax+38h]
0x180023267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002326c  mov     edi, eax
0x18002326e  test    eax, eax
0x180023270  jz      short loc_180023280
0x180023272  lea     rdx, aEnumeratefolde_1; "EnumerateFolders failure from SetColumn"...
0x180023279  mov     ecx, eax; int
0x18002327b  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180023280  mov     [rsp+370h+var_340], esi
0x180023284  test    edi, edi
0x180023286  js      short loc_1800232B4
0x180023288  mov     rcx, [rsp+370h+var_330]
0x18002328d  mov     rax, [rcx]
0x180023290  lea     r8, [rsp+370h+var_340]
0x180023295  xor     edx, edx
0x180023297  mov     rax, [rax+48h]
0x18002329b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232a0  mov     edi, eax
0x1800232a2  test    eax, eax
0x1800232a4  jz      short loc_1800232B4
0x1800232a6  lea     rdx, aEnumeratefolde_0; "EnumerateFolders failure from GetRowCou"...
0x1800232ad  mov     ecx, eax; int
0x1800232af  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800232b4  mov     edx, [rsp+370h+var_340]
0x1800232b8  lea     rcx, aCmapi2dirfilte_5; "CMapi2DirFilter::EnumerateFolders cRowC"...
0x1800232bf  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800232c4  mov     [rsp+370h+lpRows], rsi
0x1800232c9  lea     r15, ??_7?$TLMString@$0CA@$0CA@$0BAA@@@6B@; const TLMString<32,32,256>::`vftable'
0x1800232d0  test    edi, edi
0x1800232d2  js      loc_1800235A7
0x1800232d8  mov     edx, [rsp+370h+var_340]
0x1800232dc  test    edx, edx
0x1800232de  jz      loc_1800235A7
0x1800232e4  mov     rcx, [rsp+370h+var_330]
0x1800232e9  mov     rax, [rcx]
0x1800232ec  lea     r9, [rsp+370h+lpRows]
0x1800232f1  xor     r8d, r8d
0x1800232f4  mov     rax, [rax+98h]
0x1800232fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023300  mov     edi, eax
0x180023302  test    eax, eax
0x180023304  js      loc_180023598
0x18002330a  mov     r14d, esi
0x18002330d  mov     rcx, [rsp+370h+lpRows]
0x180023312  mov     eax, [rcx]
0x180023314  test    eax, eax
0x180023316  jz      loc_18002356A
0x18002331c  mov     eax, r14d
0x18002331f  inc     rax
0x180023322  add     rax, rax
0x180023325  mov     rbx, [rcx+rax*8]
0x180023329  lea     rcx, [rsp+370h+var_338]
0x18002332e  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180023333  nop
0x180023334  lea     rax, [rbp+270h+var_288]
0x180023338  mov     [rbp+270h+var_298], rax
0x18002333c  mov     ecx, 21h ; '!'
0x180023341  mov     [rbp+270h+var_290], rcx
0x180023345  mov     [rbp+270h+var_288], si
0x180023349  mov     [rbp+270h+var_2A0], r15
0x18002334d  cmp     dword ptr [rbx+18h], 3001001Fh
0x180023354  jnz     short loc_180023368
0x180023356  mov     rdx, [rbx+20h]
0x18002335a  lea     rcx, [rbp+270h+var_2A0]
0x18002335e  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180023363  jmp     loc_1800233EC
0x180023368  cmp     dword ptr [rbx], 3001001Eh
0x18002336e  jnz     loc_18002353F
0x180023374  mov     r15, [rbx+8]
0x180023378  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18002337f  mov     [rbp+270h+var_240], rax
0x180023383  lea     r8, [rbp+270h+var_228]
0x180023387  mov     [rbp+270h+var_238], r8
0x18002338b  mov     [rbp+270h+var_230], ecx
0x18002338e  test    r15, r15
0x180023391  jz      loc_180023579
0x180023397  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002339b  inc     rbx
0x18002339e  cmp     [r15+rbx], sil
0x1800233a2  jnz     short loc_18002339B
0x1800233a4  lea     esi, [rbx+1]
0x1800233a7  cmp     esi, ecx
0x1800233a9  jbe     short loc_1800233BA
0x1800233ab  mov     edx, esi; unsigned int
0x1800233ad  lea     rcx, [rbp+270h+var_240]; this
0x1800233b1  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x1800233b6  mov     r8, [rbp+270h+var_238]; wchar_t *
0x1800233ba  mov     r9d, esi; int
0x1800233bd  mov     edx, ebx; cbMultiByte
0x1800233bf  mov     rcx, r15; lpMultiByteStr
0x1800233c2  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x1800233c7  mov     [rbp+270h+var_22C], eax
0x1800233ca  lea     r15, ??_7?$TLMString@$0CA@$0CA@$0BAA@@@6B@; const TLMString<32,32,256>::`vftable'
0x1800233d1  mov     [rbp+270h+var_240], r15
0x1800233d5  mov     rdx, [rbp+270h+var_238]
0x1800233d9  lea     rcx, [rbp+270h+var_2A0]
0x1800233dd  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800233e2  nop
0x1800233e3  lea     rcx, [rbp+270h+var_240]
0x1800233e7  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x1800233ec  mov     rdx, [rbp+270h+var_298]
0x1800233f0  lea     rcx, [rsp+370h+var_318]
0x1800233f5  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1800233fa  nop
0x1800233fb  mov     rdx, rax
0x1800233fe  lea     rcx, [rsp+370h+var_320]
0x180023403  call    ?EncodeFolderName@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEBV12@@Z; EncodeFolderName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180023408  nop
0x180023409  mov     rdx, [rax]
0x18002340c  lea     rcx, [rdx-18h]
0x180023410  mov     rbx, [rsp+370h+var_338]
0x180023415  lea     rsi, [rbx-18h]
0x180023419  cmp     rcx, rsi
0x18002341c  jz      short loc_18002345A
0x18002341e  cmp     dword ptr [rsi+10h], 0
0x180023422  jl      short loc_180023447
0x180023424  mov     rax, [rsi]
0x180023427  cmp     [rcx], rax
0x18002342a  jnz     short loc_180023447
0x18002342c  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180023431  mov     rbx, rax
0x180023434  mov     rcx, rsi; this
0x180023437  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002343c  add     rbx, 18h
0x180023440  mov     [rsp+370h+var_338], rbx
0x180023445  jmp     short loc_18002345A
0x180023447  mov     r8d, [rdx-10h]
0x18002344b  lea     rcx, [rsp+370h+var_338]
0x180023450  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180023455  mov     rbx, [rsp+370h+var_338]
0x18002345a  mov     rcx, [rsp+370h+var_320]
0x18002345f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023463  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023468  nop
0x180023469  mov     rcx, [rsp+370h+var_318]
0x18002346e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023472  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023477  nop
0x180023478  lea     rcx, [rbp+270h+var_2A0]
0x18002347c  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x180023481  lea     rdx, [rsp+370h+var_310]
0x180023486  mov     rcx, r12
0x180023489  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18002348e  nop
0x18002348f  mov     rdx, [rax]; wchar_t *
0x180023492  lea     rcx, [rsp+370h+var_300]; this
0x180023497  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x18002349c  nop
0x18002349d  mov     rcx, [rsp+370h+var_310]
0x1800234a2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800234a6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800234ab  mov     rdx, rbx; wchar_t *
0x1800234ae  lea     rcx, [rsp+370h+var_300]; this
0x1800234b3  call    ?AddFolder@CMapiUrl@@QEAAXPEB_W@Z; CMapiUrl::AddFolder(wchar_t const *)
0x1800234b8  lea     rdx, [rsp+370h+var_308]
0x1800234bd  lea     rcx, [rsp+370h+var_300]
0x1800234c2  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x1800234c7  nop
0x1800234c8  mov     rdx, [rax]
0x1800234cb  lea     rcx, [rbp+270h+var_1E0]
0x1800234d2  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(wchar_t const *)
0x1800234d7  nop
0x1800234d8  mov     rcx, [rsp+370h+var_308]
0x1800234dd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800234e1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800234e6  mov     [rsp+370h+var_348], 1
0x1800234ee  xor     esi, esi
0x1800234f0  mov     [rsp+370h+var_350], esi
0x1800234f4  xor     r9d, r9d
0x1800234f7  lea     r8d, [rsi+1]
0x1800234fb  lea     rdx, [rbp+270h+var_1E0]
0x180023502  mov     rcx, r13
0x180023505  call    ?AddUrlCallback@CMapi2DirFilter@@SAJPEAXAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HW4POLICY_RESULT_ID@@HH@Z; CMapi2DirFilter::AddUrlCallback(void *,TLMString<192,64,32767> const &,int,POLICY_RESULT_ID,int,int)
0x18002350a  mov     r8, [rbp+270h+var_1D8]
0x180023511  mov     edx, r14d
0x180023514  lea     rcx, aCmapi2dirfilte_2; "CMapi2DirFilter::EnumerateFolders i=%d,"...
0x18002351b  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180023520  nop
0x180023521  lea     rcx, [rbp+270h+var_1E0]
0x180023528  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x18002352d  nop
0x18002352e  lea     rcx, [rsp+370h+var_300]; this
0x180023533  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x180023538  nop
0x180023539  lea     rcx, [rbx-18h]
0x18002353d  jmp     short loc_180023552
0x18002353f  lea     rcx, [rbp+270h+var_2A0]
0x180023543  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x180023548  nop
0x180023549  mov     rcx, [rsp+370h+var_338]
0x18002354e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023552  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023557  inc     r14d
0x18002355a  mov     rcx, [rsp+370h+lpRows]; lpRows
0x18002355f  mov     eax, [rcx]
0x180023561  cmp     r14d, eax
0x180023564  jb      loc_18002331C
0x18002356a  sub     [rsp+370h+var_340], eax
0x18002356e  call    cs:__imp_FreeProws
0x180023574  jmp     loc_1800232D0
0x180023579  mov     rcx, [rbp+278h]; this
0x180023580  mov     r9d, 80004003h; char *
0x180023586  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002358d  mov     edx, 0B6h; void *
0x180023592  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023598  lea     rdx, aOpenfolderbyna_1; "OpenFolderbyName failure from QueryRows"
0x18002359f  mov     ecx, eax; int
0x1800235a1  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800235a6  nop
0x1800235a7  lea     rcx, [rsp+370h+var_330]
0x1800235ac  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800235b1  mov     eax, edi
0x1800235b3  mov     rcx, [rbp+270h+var_40]
0x1800235ba  xor     rcx, rsp; StackCookie
0x1800235bd  call    __security_check_cookie
0x1800235c2  mov     rbx, [rsp+370h+arg_10]
0x1800235ca  add     rsp, 340h
0x1800235d1  pop     r15
0x1800235d3  pop     r14
0x1800235d5  pop     r13
0x1800235d7  pop     r12
0x1800235d9  pop     rdi
0x1800235da  pop     rsi
0x1800235db  pop     rbp
0x1800235dc  retn
```
