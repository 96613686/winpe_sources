# CMapi2DirFilter::InitDirFilter(CMapi2Accessor *,_FILETIME const &,ulong)

- ea: `0x180024824`
- end: `0x180025025`
- name: `?InitDirFilter@CMapi2DirFilter@@QEAAJPEAVCMapi2Accessor@@AEBU_FILETIME@@K@Z`
- size: `2049`
- prototype: `__int64 __fastcall(CMapi2DirFilter *__hidden this, struct CMapi2Accessor *, const struct _FILETIME *, unsigned int)`
- caller_count: `1`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x180002300`
- `0x18000e658`
- `0x18000e684`
- `0x18000e8ac`
- `0x18000ea18`
- `0x18000ebac`
- `0x18000ec50`
- `0x18000ec8c`
- `0x18000ee48`
- `0x18000f1c4`
- `0x18000f930`
- `0x18000fd58`
- `0x1800113ac`
- `0x1800113ec`
- `0x18001148c`
- `0x180011884`
- `0x1800122d8`
- `0x180012398`
- `0x18001241c`
- `0x18001359c`
- `0x180014014`
- `0x180014448`
- `0x1800151b4`
- `0x1800151f4`
- `0x180015884`
- `0x180015970`
- `0x180016948`
- `0x180016970`
- `0x180022bcc`
- `0x1800231d4`
- `0x1800235e4`
- `0x1800236d4`
- `0x180023a88`
- `0x180024824`
- `0x18002502c`
- `0x180025190`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024aa2`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024b2a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024ca6`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024aa2`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024b2a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180024ca6`

## string_xrefs

- `0x180024e98`: `InitDirFilter Could not open folder %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CMapi2DirFilter::InitDirFilter(
        CMapi2DirFilter *this,
        struct CMapi2Accessor *a2,
        const struct _FILETIME *a3,
        unsigned int a4)
{
  CLMString *v5; // rbx
  wchar_t v6; // dx
  int v7; // eax
  wchar_t v8; // dx
  int v9; // eax
  wchar_t v10; // dx
  int v11; // eax
  struct IMAPIFolder *v12; // rdi
  int v13; // r12d
  ATL::CStringData *v14; // rbx
  const wchar_t *v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // r14
  unsigned int v18; // ebx
  __int64 v19; // rbx
  _QWORD *v20; // rax
  __int64 *v21; // r13
  int MsgStore; // eax
  __int64 v23; // rcx
  unsigned int v24; // edx
  HANDLE *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx
  _QWORD *v28; // rax
  int IPMSubTree; // eax
  __int64 v30; // rbx
  bool v31; // zf
  int v32; // ecx
  int v33; // r12d
  unsigned int v34; // eax
  int v35; // eax
  unsigned int v36; // edi
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 *v39; // rax
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rdx
  volatile signed __int32 *v43; // rcx
  int *v44; // rsi
  volatile signed __int32 *v45; // rbx
  __int64 v46; // r8
  unsigned int v49; // [rsp+20h] [rbp-E0h]
  char *v50; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+38h] [rbp-C8h] BYREF
  struct IMAPIFolder *v53; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-B8h]
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  ATL::CStringData *v56; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A0h] BYREF
  void *v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v61[12]; // [rsp+80h] [rbp-80h] BYREF
  void **v62; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v63; // [rsp+E8h] [rbp-18h]
  __int64 v64; // [rsp+F0h] [rbp-10h]
  __int16 v65; // [rsp+F8h] [rbp-8h] BYREF

  *(struct _FILETIME *)((char *)this + 9692) = *a3;
  *((_QWORD *)this + 1094) = a2;
  v5 = (CMapi2DirFilter *)((char *)this + 8760);
  CLMString::operator=((__int64)this + 8760, *((_QWORD *)a2 + 13));
  *(_QWORD *)((char *)this + 9388) = 0;
  v7 = CLMString::Find(v5, v6, 8u);
  if ( v7 > 0 )
  {
    v9 = CLMString::Find(v5, v8, v7 + 1);
    if ( v9 > 0 )
    {
      if ( v9 == *((_DWORD *)this + 2195) - 1 )
      {
        *((_DWORD *)this + 2347) = 1;
      }
      else
      {
        *((_DWORD *)this + 2347) = 0;
        v11 = CLMString::Find(v5, v10, v9 + 1);
        if ( v11 > 0 )
          *((_DWORD *)this + 2348) = v11 == *((_DWORD *)this + 2195) - 1;
      }
    }
  }
  v12 = 0;
  v53 = 0;
  v58 = 0;
  *(_QWORD *)((char *)this + 9700) = 0;
  *((_DWORD *)this + 2340) = 0;
  ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 9368, &dword_1800444C4, 0);
  v13 = CMapiUrl::SetURL((CMapi2DirFilter *)((char *)this + 9176), *((const wchar_t **)this + 1096));
  if ( v13 < 0 )
    goto LABEL_81;
  CMapiUrl::Store((__int64)this + 9176, (__int64)&v52);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v60,
    (_QWORD *)this + 1151);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v55,
    (_QWORD *)this + 1154);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v56,
    (_QWORD *)(*((_QWORD *)this + 1094) + 528LL));
  v14 = v56;
  CLMString::operator=((__int64)this + 9400, (__int64)v56);
  ATL::CStringData::Release((ATL::CStringData *)((char *)v14 - 24));
  v16 = v55;
  v56 = (ATL::CStringData *)(v55 - 24);
  v17 = v60;
  if ( *(int *)(v55 - 24 + 8) <= 0 || *(_DWORD *)(v52 - 16) && *(_DWORD *)(v60 - 16) )
  {
    *((_QWORD *)this + 1172) = 0;
    *((_DWORD *)this + 2346) = 0;
    if ( *(int *)(v52 - 16) <= 0 )
      goto LABEL_19;
    *((_DWORD *)this + 2344) = CMapiUrl::GetCachedStoreValue((CMapi2DirFilter *)((char *)this + 9176), v15);
    v19 = *((_QWORD *)this + 1094);
    v20 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
            &v51,
            &v52);
    v21 = (__int64 *)((char *)this + 9336);
    MsgStore = CMapi2Accessor::GetMsgStore(v19, v20, (char *)this + 9336);
    v13 = MsgStore;
    v18 = 266755;
    if ( MsgStore == 266755 )
      goto LABEL_29;
    if ( MsgStore )
    {
LABEL_19:
      v24 = a4;
    }
    else
    {
      v23 = *v21;
      if ( !*v21 )
      {
        CLogger::Info(
          L"CMapi2DirFilter::InitDirFilter GetMsgStore returned with success but the store was NULL, returning PRTH_E_SERVER_ERROR",
          2147750406LL);
        v18 = -2147216890;
        goto LABEL_29;
      }
      *((_DWORD *)this + 2346) = *(_DWORD *)(v23 + 104);
      v24 = a4;
      if ( a4 >= 0xC )
        *((_DWORD *)this + 2345) = *(_DWORD *)(v23 + 100);
    }
    if ( !*(_DWORD *)(v52 - 16) )
    {
      v50 = (char *)OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
      if ( !(unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v50) )
      {
        CLogger::Info(
          -2147216890,
          L"Not enumerating stores since Outlook is not running, returning PRTH_E_SERVER_ERROR");
LABEL_28:
        OutlookSync::~OutlookSync((OutlookSync *)&v50);
        v18 = -2147216890;
        goto LABEL_29;
      }
      v13 = CMapi2DirFilter::EnumerateStores(
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1094) + 64LL) + 208LL),
              CMapi2DirFilter::AddUrlCallback,
              this,
              2);
      v25 = (HANDLE *)&v50;
      goto LABEL_78;
    }
    if ( *((_DWORD *)this + 2355) )
      goto LABEL_79;
    if ( v24 < 0xC )
    {
      v50 = (char *)OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
      if ( !(unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v50) )
      {
        CLogger::Info(
          -2147216890,
          L"Not enumerating folders since Outlook is not running, returning PRTH_E_SERVER_ERROR");
        goto LABEL_28;
      }
      OutlookSync::~OutlookSync((OutlookSync *)&v50);
    }
    if ( *((_DWORD *)this + 2347) )
    {
      v26 = *((_QWORD *)this + 1167);
      if ( !v26 || !*(_DWORD *)(v26 + 100) )
      {
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          (__int64)&v50,
          *(const wchar_t **)(*((_QWORD *)this + 1094) + 104LL));
        ATL::CSimpleStringT<wchar_t,0>::Append(&v50, L"X");
        ATL::CSimpleStringT<wchar_t,0>::Append(&v50, L"/");
        TLMString<192,64,32767>::TLMString<192,64,32767>(&v62, v50);
        CMapi2DirFilter::AddURL((__int64)this, (__int64)&v62, 1, 0);
        TLMString<192,64,32767>::~TLMString<192,64,32767>((wchar_t *)&v62);
        ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
        goto LABEL_79;
      }
    }
    if ( v13 )
      goto LABEL_39;
    v27 = *((_QWORD *)this + 1094);
    v28 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
            &v51,
            &v52);
    IPMSubTree = CMapi2Accessor::GetIPMSubTree(v27, v28, &v58);
    v13 = IPMSubTree;
    v30 = (__int64)v58;
    v31 = IPMSubTree == 0;
    if ( IPMSubTree >= 0 )
    {
      if ( !v58 )
      {
        v13 = -2147216890;
        goto LABEL_39;
      }
      v31 = IPMSubTree == 0;
    }
    if ( v31 )
    {
      if ( *(_DWORD *)(v16 - 16) )
      {
        v32 = 0;
        v49 = 0;
        v63 = (const wchar_t *)&v65;
        v64 = 193;
        v65 = 0;
        v62 = &TLMString<192,64,32767>::`vftable';
        v51 = v58;
        if ( v58 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v58 + 8LL))(v58);
          v32 = 0;
        }
        while ( v32 < *(_DWORD *)(v16 - 16) )
        {
          v33 = 0;
          v34 = v32;
          while ( 1 )
          {
            v35 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(&v55, 47, v34);
            LODWORD(v50) = v35;
            v36 = v35 + 1;
            v54 = v35 + 1;
            if ( v35 == -1 )
              break;
            v34 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(&v55, 47, v36);
            if ( v34 == -1 || v34 != v36 )
              v33 = 1;
            else
              ++v34;
            if ( v33 )
            {
              v35 = (int)v50;
              goto LABEL_61;
            }
          }
          v54 = 0;
LABEL_61:
          if ( v35 == -1 )
          {
            v39 = (__int64 *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
                               &v55,
                               &v57,
                               v49);
            CLMString::operator=((__int64)&v62, *v39);
            v38 = v57;
          }
          else
          {
            v37 = (__int64 *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
                               &v55,
                               &v59,
                               v49,
                               v35 - v49,
                               v49);
            CLMString::operator=((__int64)&v62, *v37);
            v38 = v59;
          }
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
          TComPointer<IFilter>::operator=(&v53, 0);
          CLMString::operator=((__int64)this + 9400, (__int64)&dword_1800444C4);
          v40 = CMapi2DirFilter::OpenFolderByName(this, v30, &v62, &v53);
          v13 = v40;
          if ( v40 < 0 )
          {
            CLogger::Error((unsigned int)v40, L"InitDirFilter Could not open folder %s", v63);
            v12 = v53;
            break;
          }
          v12 = v53;
          TComPointer<IFilter>::operator=(&v51, (__int64)v53);
          v32 = v54;
          v49 = v54;
          if ( (_DWORD)v50 == -1 )
            break;
          v30 = (__int64)v51;
        }
        v41 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                (__int64)&v59,
                v63);
        v42 = *(_QWORD *)DecodeFolderName(&v57, v41);
        v43 = (volatile signed __int32 *)(v42 - 24);
        v44 = (int *)(*((_QWORD *)this + 1171) - 24LL);
        if ( (int *)(v42 - 24) != v44 )
        {
          if ( v44[4] >= 0 && *(_QWORD *)v43 == *(_QWORD *)v44 )
          {
            v45 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v43);
            ATL::CStringData::Release((ATL::CStringData *)v44);
            *((_QWORD *)this + 1171) = v45 + 6;
          }
          else
          {
            ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 9368, v42, *(unsigned int *)(v42 - 16));
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
        TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v51);
        TLMString<192,64,32767>::~TLMString<192,64,32767>((wchar_t *)&v62);
      }
      else
      {
        TComPointer<IFilter>::operator=(&v53, (__int64)v58);
        v12 = v53;
      }
      goto LABEL_41;
    }
LABEL_39:
    CLogger::Error((unsigned int)v13, L"Could not get root folder for store %s", v52);
    if ( v13 == -2147221233 )
      v13 = -2147216895;
LABEL_41:
    if ( (unsigned int)CMapi2DirFilter::IsGatherContained(this) )
      goto LABEL_79;
    v51 = OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
    if ( !(unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v51) )
    {
      CLogger::Info(-2147216890, L"Not enumerating folders since Outlook is not running, returning PRTH_E_SERVER_ERROR");
      OutlookSync::~OutlookSync((OutlookSync *)&v51);
      ATL::CStringData::Release(v56);
      v18 = -2147216890;
      goto LABEL_44;
    }
    if ( v13 >= 0 )
    {
      CMapiUrl::CMapiUrl((CMapiUrl *)v61, *((const wchar_t **)this + 1096));
      v13 = CMapi2DirFilter::EnumerateFolders((__int64)v12, v61, v46, (int)this);
      CMapiUrl::~CMapiUrl((CMapiUrl *)v61);
      if ( v13 >= 0 )
        v13 = CMapi2DirFilter::EnumerateMessages(this, v12);
    }
    v25 = &v51;
LABEL_78:
    OutlookSync::~OutlookSync((OutlookSync *)v25);
LABEL_79:
    ATL::CStringData::Release(v56);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
    if ( v13 >= 0 )
    {
      *((_QWORD *)this + 1163) = (char *)this + 9264;
      *((_QWORD *)this + 1164) = (char *)this + 9272;
      *((_QWORD *)this + 1165) = 0;
    }
LABEL_81:
    v18 = v13;
    goto LABEL_82;
  }
  v18 = -2147216895;
LABEL_29:
  ATL::CStringData::Release(v56);
LABEL_44:
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
LABEL_82:
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v58);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v53);
  return v18;
}

```

## disassembly

```asm
0x180024824  push    rbp
0x180024826  push    rbx
0x180024827  push    rsi
0x180024828  push    rdi
0x180024829  push    r12
0x18002482b  push    r13
0x18002482d  push    r14
0x18002482f  push    r15
0x180024831  lea     rbp, [rsp-198h]
0x180024839  sub     rsp, 298h
0x180024840  mov     rax, cs:__security_cookie
0x180024847  xor     rax, rsp
0x18002484a  mov     [rbp+1D0h+var_50], rax
0x180024851  mov     [rsp+2D0h+var_2B0], r9d
0x180024856  mov     r15, rcx
0x180024859  xor     esi, esi
0x18002485b  mov     rax, [r8]
0x18002485e  mov     [rcx+25DCh], rax
0x180024865  mov     [rcx+2230h], rdx
0x18002486c  lea     rbx, [rcx+2238h]
0x180024873  mov     rdx, [rdx+68h]
0x180024877  mov     rcx, rbx
0x18002487a  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18002487f  mov     [r15+24ACh], rsi
0x180024886  lea     r8d, [rsi+8]; unsigned int
0x18002488a  mov     rcx, rbx; this
0x18002488d  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x180024892  test    eax, eax
0x180024894  jle     short loc_1800248EE
0x180024896  lea     r8d, [rax+1]; unsigned int
0x18002489a  mov     rcx, rbx; this
0x18002489d  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x1800248a2  test    eax, eax
0x1800248a4  jle     short loc_1800248EE
0x1800248a6  mov     ecx, [r15+224Ch]
0x1800248ad  dec     ecx
0x1800248af  cmp     eax, ecx
0x1800248b1  jnz     short loc_1800248C0
0x1800248b3  mov     dword ptr [r15+24ACh], 1
0x1800248be  jmp     short loc_1800248EE
0x1800248c0  mov     [r15+24ACh], esi
0x1800248c7  lea     r8d, [rax+1]; unsigned int
0x1800248cb  mov     rcx, rbx; this
0x1800248ce  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x1800248d3  test    eax, eax
0x1800248d5  jle     short loc_1800248EE
0x1800248d7  mov     ecx, [r15+224Ch]
0x1800248de  dec     ecx
0x1800248e0  mov     edx, esi
0x1800248e2  cmp     eax, ecx
0x1800248e4  setz    dl
0x1800248e7  mov     [r15+24B0h], edx
0x1800248ee  mov     rdi, rsi
0x1800248f1  mov     [rsp+2D0h+var_290], rsi
0x1800248f6  mov     [rsp+2D0h+var_268], rsi
0x1800248fb  mov     [r15+25E4h], rsi
0x180024902  mov     [r15+2490h], esi
0x180024909  lea     rcx, [r15+2498h]
0x180024910  xor     r8d, r8d
0x180024913  lea     rdx, dword_1800444C4
0x18002491a  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002491f  lea     r13, [r15+23D8h]
0x180024926  mov     rdx, [r15+2240h]; wchar_t *
0x18002492d  mov     rcx, r13; this
0x180024930  call    ?SetURL@CMapiUrl@@QEAAJPEB_W@Z; CMapiUrl::SetURL(wchar_t const *)
0x180024935  mov     r12d, eax
0x180024938  test    eax, eax
0x18002493a  js      loc_180024FE8
0x180024940  lea     rdx, [rsp+2D0h+var_298]
0x180024945  mov     rcx, r13
0x180024948  call    ?Store@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::Store(void)
0x18002494d  nop
0x18002494e  lea     rdx, [r13+20h]
0x180024952  lea     rcx, [rsp+2D0h+var_258]
0x180024957  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002495c  nop
0x18002495d  lea     rdx, [r13+38h]
0x180024961  lea     rcx, [rsp+2D0h+var_280]
0x180024966  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002496b  nop
0x18002496c  mov     rdx, [r15+2230h]
0x180024973  add     rdx, 210h
0x18002497a  lea     rcx, [rsp+2D0h+var_278]
0x18002497f  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180024984  nop
0x180024985  mov     rbx, [rsp+2D0h+var_278]
0x18002498a  lea     rcx, [r15+24B8h]
0x180024991  mov     rdx, rbx
0x180024994  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180024999  nop
0x18002499a  lea     rcx, [rbx-18h]; this
0x18002499e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800249a3  mov     rsi, [rsp+2D0h+var_280]
0x1800249a8  lea     rax, [rsi-18h]
0x1800249ac  mov     [rsp+2D0h+var_278], rax
0x1800249b1  mov     r14, [rsp+2D0h+var_258]
0x1800249b6  xor     ebx, ebx
0x1800249b8  cmp     [rax+8], ebx
0x1800249bb  jle     short loc_1800249D7
0x1800249bd  mov     rax, [rsp+2D0h+var_298]
0x1800249c2  cmp     [rax-10h], ebx
0x1800249c5  jz      short loc_1800249CD
0x1800249c7  cmp     [r14-10h], ebx
0x1800249cb  jnz     short loc_1800249D7
0x1800249cd  mov     ebx, 80041201h
0x1800249d2  jmp     loc_180024B66
0x1800249d7  mov     [r15+24A0h], rbx
0x1800249de  mov     [r15+24A8h], ebx
0x1800249e5  mov     rax, [rsp+2D0h+var_298]
0x1800249ea  cmp     [rax-10h], ebx
0x1800249ed  jle     loc_180024A86
0x1800249f3  mov     rcx, r13; this
0x1800249f6  call    ?GetCachedStoreValue@CMapiUrl@@AEAAHPEB_W@Z; CMapiUrl::GetCachedStoreValue(wchar_t const *)
0x1800249fb  mov     [r15+24A0h], eax
0x180024a02  mov     rbx, [r15+2230h]
0x180024a09  lea     rdx, [rsp+2D0h+var_298]
0x180024a0e  lea     rcx, [rsp+2D0h+var_2A0]
0x180024a13  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180024a18  lea     r13, [r15+2478h]
0x180024a1f  mov     r8, r13
0x180024a22  mov     rdx, rax
0x180024a25  mov     rcx, rbx
0x180024a28  call    ?GetMsgStore@CMapi2Accessor@@QEAAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAPEAVCMapiStore@@@Z; CMapi2Accessor::GetMsgStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore * *)
0x180024a2d  mov     r12d, eax
0x180024a30  mov     ebx, 41203h
0x180024a35  cmp     eax, ebx
0x180024a37  jz      loc_180024B66
0x180024a3d  xor     ebx, ebx
0x180024a3f  test    eax, eax
0x180024a41  jnz     short loc_180024A86
0x180024a43  mov     rcx, [r13+0]
0x180024a47  test    rcx, rcx
0x180024a4a  jz      short loc_180024A6B
0x180024a4c  mov     eax, [rcx+68h]
0x180024a4f  mov     [r15+24A8h], eax
0x180024a56  mov     edx, [rsp+2D0h+var_2B0]
0x180024a5a  cmp     edx, 0Ch
0x180024a5d  jb      short loc_180024A8A
0x180024a5f  mov     eax, [rcx+64h]
0x180024a62  mov     [r15+24A4h], eax
0x180024a69  jmp     short loc_180024A8A
0x180024a6b  mov     edx, 80041206h
0x180024a70  lea     rcx, aCmapi2dirfilte_6; "CMapi2DirFilter::InitDirFilter GetMsgSt"...
0x180024a77  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180024a7c  mov     ebx, 80041206h
0x180024a81  jmp     loc_180024B66
0x180024a86  mov     edx, [rsp+2D0h+var_2B0]
0x180024a8a  mov     rax, [rsp+2D0h+var_298]
0x180024a8f  cmp     [rax-10h], ebx
0x180024a92  jnz     short loc_180024B0A
0x180024a94  lea     r8, Name; "MSSPHTB_Alive"
0x180024a9b  xor     edx, edx; bInheritHandle
0x180024a9d  mov     ecx, 1F0001h; dwDesiredAccess
0x180024aa2  call    cs:__imp_OpenMutexW
0x180024aa8  mov     [rsp+2D0h+var_2A8], rax
0x180024aad  lea     rcx, [rsp+2D0h+var_2A8]; this
0x180024ab2  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x180024ab7  test    eax, eax
0x180024ab9  jnz     short loc_180024AD6
0x180024abb  lea     rdx, aNotEnumerating_0; "Not enumerating stores since Outlook is"...
0x180024ac2  mov     r13d, 80041206h
0x180024ac8  mov     ecx, r13d; int
0x180024acb  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180024ad0  nop
0x180024ad1  jmp     loc_180024B59
0x180024ad6  mov     rax, [r15+2230h]
0x180024add  mov     rcx, [rax+40h]
0x180024ae1  mov     r9d, 2
0x180024ae7  mov     r8, r15
0x180024aea  lea     rdx, ?AddUrlCallback@CMapi2DirFilter@@SAJPEAXAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HW4POLICY_RESULT_ID@@HH@Z; CMapi2DirFilter::AddUrlCallback(void *,TLMString<192,64,32767> const &,int,POLICY_RESULT_ID,int,int)
0x180024af1  mov     rcx, [rcx+0D0h]
0x180024af8  call    ?EnumerateStores@CMapi2DirFilter@@SAJPEAVCMapiManager@@P6AJPEAXAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HW4POLICY_RESULT_ID@@HH@Z1K@Z; CMapi2DirFilter::EnumerateStores(CMapiManager *,long (*)(void *,TLMString<192,64,32767> const &,int,POLICY_RESULT_ID,int,int),void *,ulong)
0x180024afd  mov     r12d, eax
0x180024b00  lea     rcx, [rsp+2D0h+var_2A8]
0x180024b05  jmp     loc_180024F9A
0x180024b0a  cmp     [r15+24CCh], ebx
0x180024b11  jnz     loc_180024FA0
0x180024b17  cmp     edx, 0Ch
0x180024b1a  jnb     short loc_180024B7F
0x180024b1c  lea     r8, Name; "MSSPHTB_Alive"
0x180024b23  xor     edx, edx; bInheritHandle
0x180024b25  mov     ecx, 1F0001h; dwDesiredAccess
0x180024b2a  call    cs:__imp_OpenMutexW
0x180024b30  mov     [rsp+2D0h+var_2A8], rax
0x180024b35  lea     rcx, [rsp+2D0h+var_2A8]; this
0x180024b3a  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x180024b3f  test    eax, eax
0x180024b41  jnz     short loc_180024B75
0x180024b43  lea     rdx, aNotEnumerating; "Not enumerating folders since Outlook i"...
0x180024b4a  mov     r13d, 80041206h
0x180024b50  mov     ecx, r13d; int
0x180024b53  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180024b58  nop
0x180024b59  lea     rcx, [rsp+2D0h+var_2A8]; this
0x180024b5e  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x180024b63  mov     ebx, r13d
0x180024b66  mov     rcx, [rsp+2D0h+var_278]; this
0x180024b6b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024b70  jmp     loc_180024CEB
0x180024b75  lea     rcx, [rsp+2D0h+var_2A8]; this
0x180024b7a  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x180024b7f  cmp     [r15+24ACh], ebx
0x180024b86  jz      loc_180024C15
0x180024b8c  mov     rax, [r15+2478h]
0x180024b93  test    rax, rax
0x180024b96  jz      short loc_180024B9D
0x180024b98  cmp     [rax+64h], ebx
0x180024b9b  jnz     short loc_180024C15
0x180024b9d  mov     rdx, [r15+2230h]
0x180024ba4  mov     rdx, [rdx+68h]
0x180024ba8  lea     rcx, [rsp+2D0h+var_2A8]
0x180024bad  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180024bb2  nop
0x180024bb3  lea     rdx, asc_1800482B8; "X"
0x180024bba  lea     rcx, [rsp+2D0h+var_2A8]
0x180024bbf  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180024bc4  lea     rdx, asc_1800444BC; "/"
0x180024bcb  lea     rcx, [rsp+2D0h+var_2A8]
0x180024bd0  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180024bd5  mov     rdx, [rsp+2D0h+var_2A8]
0x180024bda  lea     rcx, [rbp+1D0h+var_1F0]
0x180024bde  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(wchar_t const *)
0x180024be3  nop
0x180024be4  xor     r9d, r9d
0x180024be7  lea     r8d, [r9+1]
0x180024beb  lea     rdx, [rbp+1D0h+var_1F0]
0x180024bef  mov     rcx, r15
0x180024bf2  call    ?AddURL@CMapi2DirFilter@@QEAAJAEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HH@Z; CMapi2DirFilter::AddURL(TLMString<192,64,32767> const &,int,int)
0x180024bf7  nop
0x180024bf8  lea     rcx, [rbp+1D0h+var_1F0]
0x180024bfc  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x180024c01  nop
0x180024c02  mov     rcx, [rsp+2D0h+var_2A8]
0x180024c07  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024c0b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024c10  jmp     loc_180024FA0
0x180024c15  mov     r13d, 80041206h
0x180024c1b  test    r12d, r12d
0x180024c1e  jnz     short loc_180024C62
0x180024c20  mov     rbx, [r15+2230h]
0x180024c27  lea     rdx, [rsp+2D0h+var_298]
0x180024c2c  lea     rcx, [rsp+2D0h+var_2A0]
0x180024c31  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180024c36  lea     r8, [rsp+2D0h+var_268]
0x180024c3b  mov     rdx, rax
0x180024c3e  mov     rcx, rbx
0x180024c41  call    ?GetIPMSubTree@CMapi2Accessor@@QEAAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAPEAUIMAPIFolder@@@Z; CMapi2Accessor::GetIPMSubTree(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,IMAPIFolder * *)
0x180024c46  mov     r12d, eax
0x180024c49  mov     rbx, [rsp+2D0h+var_268]
0x180024c4e  test    eax, eax
0x180024c50  js      loc_180024D0A
0x180024c56  test    rbx, rbx
0x180024c59  jnz     loc_180024D08
0x180024c5f  mov     r12d, r13d
0x180024c62  mov     r8, [rsp+2D0h+var_298]
0x180024c67  lea     rdx, aCouldNotGetRoo; "Could not get root folder for store %s"
0x180024c6e  mov     ecx, r12d; int
0x180024c71  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180024c76  mov     ebx, 80041201h
0x180024c7b  cmp     r12d, 8004010Fh
0x180024c82  cmovz   r12d, ebx
0x180024c86  mov     rcx, r15; this
0x180024c89  call    ?IsGatherContained@CMapi2DirFilter@@AEAAHXZ; CMapi2DirFilter::IsGatherContained(void)
0x180024c8e  xor     ebx, ebx
0x180024c90  test    eax, eax
0x180024c92  jnz     loc_180024FA0
0x180024c98  lea     r8, Name; "MSSPHTB_Alive"
0x180024c9f  xor     edx, edx; bInheritHandle
0x180024ca1  mov     ecx, 1F0001h; dwDesiredAccess
0x180024ca6  call    cs:__imp_OpenMutexW
0x180024cac  mov     [rsp+2D0h+var_2A0], rax
0x180024cb1  lea     rcx, [rsp+2D0h+var_2A0]; this
0x180024cb6  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x180024cbb  test    eax, eax
0x180024cbd  jnz     loc_180024F51
0x180024cc3  lea     rdx, aNotEnumerating; "Not enumerating folders since Outlook i"...
0x180024cca  mov     ecx, r13d; int
0x180024ccd  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180024cd2  nop
0x180024cd3  lea     rcx, [rsp+2D0h+var_2A0]; this
0x180024cd8  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x180024cdd  nop
0x180024cde  mov     rcx, [rsp+2D0h+var_278]; this
0x180024ce3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024ce8  mov     ebx, r13d
0x180024ceb  lea     rcx, [r14-18h]; this
0x180024cef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024cf4  nop
0x180024cf5  mov     rcx, [rsp+2D0h+var_298]
0x180024cfa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024cfe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024d03  jmp     loc_180024FEB
0x180024d08  test    eax, eax
0x180024d0a  jnz     loc_180024C62
0x180024d10  cmp     dword ptr [rsi-10h], 0
0x180024d14  jnz     short loc_180024D2D
0x180024d16  mov     rdx, rbx
0x180024d19  lea     rcx, [rsp+2D0h+var_290]
0x180024d1e  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x180024d23  mov     rdi, [rsp+2D0h+var_290]
  ... truncated ...
```
