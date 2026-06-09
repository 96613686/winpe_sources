# Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180031020`
- end: `0x180031802`
- name: `?OnAfterEvents@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `2018`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x180001bc8`
- `0x18000262c`
- `0x180010b08`
- `0x180010d94`
- `0x180010db8`
- `0x180019260`
- `0x18001dc28`
- `0x18001dccc`
- `0x1800223a4`
- `0x1800300d8`
- `0x180030258`
- `0x180030470`
- `0x1800305e0`
- `0x180030774`
- `0x180030804`
- `0x180031020`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003174d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003175b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003174d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003175b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031366`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800313c3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031366`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800313c3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003142b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180031462`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003142b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180031462`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180031150`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180031150`
- `bcrypt!BCryptDestroyHash` at `0x180031737`
- `bcrypt!BCryptDestroyHash` at `0x180031737`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031743`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031743`
- `bcrypt!BCryptGetProperty` at `0x180031330`
- `bcrypt!BCryptGetProperty` at `0x180031399`
- `bcrypt!BCryptGetProperty` at `0x180031330`
- `bcrypt!BCryptGetProperty` at `0x180031399`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800312f6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800312f6`
- `bcrypt!BCryptCreateHash` at `0x1800313f0`
- `bcrypt!BCryptCreateHash` at `0x1800313f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v6; // r13
  _QWORD *v7; // rax
  unsigned int v8; // r15d
  void *v9; // rax
  WCHAR *v10; // rcx
  WCHAR *v11; // rbx
  __int64 v12; // rdx
  WCHAR *v13; // rdi
  __int64 i; // rcx
  DWORD DosDeviceW; // eax
  __int64 inserted; // rdi
  __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  unsigned __int16 v20; // dx
  int v21; // eax
  void *v22; // rbx
  _QWORD *v23; // rsi
  __int64 v24; // r8
  _QWORD *v25; // rdx
  size_t v26; // rcx
  size_t v27; // rcx
  NTSTATUS v28; // eax
  char v29; // cl
  _QWORD *v30; // rbx
  _QWORD *v31; // r12
  __int64 v32; // rcx
  wchar_t *v33; // rax
  __int64 v34; // rax
  int v35; // eax
  wchar_t *v36; // rax
  __int64 v37; // rdi
  unsigned int v38; // esi
  __int64 v39; // rcx
  __int64 v40; // rax
  unsigned __int16 *v41; // rsi
  __int64 v42; // rcx
  unsigned __int16 *v43; // rax
  __int64 v44; // rcx
  unsigned __int16 v45; // dx
  int v46; // eax
  int v47; // r13d
  int v48; // eax
  int v49; // edi
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  WCHAR *v53; // r13
  __int64 v54; // rcx
  __int64 v55; // rdi
  _QWORD *v56; // rdx
  __int64 **v57; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  __int64 v60; // rcx
  ULONG pcbResult[2]; // [rsp+40h] [rbp-89h] BYREF
  void *v63; // [rsp+48h] [rbp-81h] BYREF
  __int64 v64; // [rsp+50h] [rbp-79h]
  UCHAR pbOutput[8]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v66; // [rsp+60h] [rbp-69h]
  unsigned int v67; // [rsp+68h] [rbp-61h]
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+70h] [rbp-59h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp-49h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+88h] [rbp-41h]
  UCHAR v71[4]; // [rsp+98h] [rbp-31h] BYREF
  unsigned int v72; // [rsp+A0h] [rbp-29h]
  LPWSTR lpTargetPath[2]; // [rsp+A8h] [rbp-21h] BYREF
  WCHAR *v74; // [rsp+B8h] [rbp-11h]
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v75; // [rsp+C0h] [rbp-9h]
  WCHAR DeviceName[4]; // [rsp+C8h] [rbp-1h] BYREF

  v72 = a4;
  v4 = a3;
  v67 = a3;
  v6 = this;
  v75 = this;
  v64 = 0;
  v7 = operator new(0x30u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  v8 = 1;
  *((_WORD *)v7 + 12) = 257;
  v63 = v7;
  wcscpy(DeviceName, L"_:");
  *(_WORD *)pbOutput = 0;
  *(_OWORD *)lpTargetPath = 0;
  v74 = 0;
  v9 = operator new(0x2027u);
  if ( !v9 )
    __fastfail(5u);
  v10 = (WCHAR *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v10 - 1) = v9;
  lpTargetPath[0] = v10;
  v11 = v10 + 4096;
  v74 = v10 + 4096;
  LOWORD(pcbResult[0]) = 0;
  if ( pbOutput[1] )
  {
    v12 = 4096;
    v11 = (WCHAR *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    v13 = v11;
    for ( i = 4096; i; --i )
      *v13++ = 0;
    do
    {
      ++v11;
      --v12;
    }
    while ( v12 );
  }
  else
  {
    memset_0(v10, 0, 0x2000u);
  }
  lpTargetPath[1] = v11;
  *(_QWORD *)pcbResult = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(pcbResult);
  DeviceName[0] = 65;
  do
  {
    DosDeviceW = QueryDosDeviceW(DeviceName, lpTargetPath[0], lpTargetPath[1] - lpTargetPath[0]);
    if ( DosDeviceW > 1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        pcbResult,
        lpTargetPath[0],
        DosDeviceW - 2);
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::_Find_lower_bound<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
        &v63,
        phAlgorithm,
        pcbResult);
      inserted = (__int64)phHash;
      if ( *((_BYTE *)phHash + 25) )
        goto LABEL_19;
      v17 = *((_QWORD *)phHash + 4);
      if ( !v17 )
        ATL::AtlThrowImpl(-2147467259);
      v18 = *(unsigned __int16 **)pcbResult;
      v19 = v17 - *(_QWORD *)pcbResult;
      while ( 1 )
      {
        v20 = *v18;
        if ( *v18 != *(unsigned __int16 *)((char *)v18 + v19) )
          break;
        ++v18;
        if ( !v20 )
        {
          v21 = 0;
          goto LABEL_18;
        }
      }
      v21 = v20 < *(unsigned __int16 *)((char *)v18 + v19) ? -1 : 1;
LABEL_18:
      if ( v21 < 0 )
      {
LABEL_19:
        if ( v64 == 0x555555555555555LL )
          std::_Throw_tree_length_error();
        v22 = v63;
        *(_QWORD *)pbOutput = &v63;
        v23 = operator new(0x30u);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          v23 + 4,
          pcbResult);
        v23[5] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        *v23 = v22;
        v23[1] = v22;
        v23[2] = v22;
        *((_WORD *)v23 + 12) = 0;
        v66 = 0;
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>((__int64)pbOutput);
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                     &v63,
                     (__int64)phAlgorithm,
                     (__int64)v23);
      }
      v24 = -1;
      do
        ++v24;
      while ( DeviceName[v24] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(inserted + 40, DeviceName, v24);
      v25 = (_QWORD *)(*(_QWORD *)pcbResult - 24LL);
      if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)pcbResult - 24LL + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
    }
    ++DeviceName[0];
  }
  while ( DeviceName[0] != 91 );
  std::vector<unsigned short>::~vector<unsigned short>(lpTargetPath);
  if ( *((_QWORD *)v6 + 9) )
  {
    LOBYTE(phAlgorithm[0]) = 0;
    *(_OWORD *)pbHashObject = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm[1], L"SHA256", 0, 0x20u) >= 0 )
    {
      *(_DWORD *)pbOutput = 0;
      pcbResult[0] = 0;
      if ( BCryptGetProperty(phAlgorithm[1], L"ObjectLength", pbOutput, 4u, pcbResult, 0) >= 0 && pcbResult[0] == 4 )
      {
        v26 = *(unsigned int *)pbOutput;
        if ( *(_DWORD *)pbOutput )
        {
          if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)pbOutput) )
            goto LABEL_43;
        }
        else
        {
          v26 = 0;
        }
        pbHashObject[0] = (PUCHAR)malloc(v26);
        if ( pbHashObject[0] )
        {
          if ( BCryptGetProperty(phAlgorithm[1], L"HashDigestLength", v71, 4u, pcbResult, 0) >= 0 && pcbResult[0] == 4 )
          {
            v27 = *(unsigned int *)v71;
            if ( *(_DWORD *)v71 )
            {
              if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)v71) )
                goto LABEL_43;
            }
            else
            {
              v27 = 0;
            }
            pbHashObject[1] = (PUCHAR)malloc(v27);
            if ( pbHashObject[1] )
            {
              v28 = BCryptCreateHash(phAlgorithm[1], &phHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0x20u);
              v29 = (char)phAlgorithm[0];
              if ( v28 >= 0 )
                v29 = 1;
              LOBYTE(phAlgorithm[0]) = v29;
            }
          }
        }
      }
    }
LABEL_43:
    v30 = (_QWORD *)**((_QWORD **)v6 + 8);
    while ( v30 != *((_QWORD **)v6 + 8) )
    {
      v31 = v30 + 4;
      v32 = v30[4];
      if ( *(int *)(v32 - 16) > 1 && (v33 = wcschr((const wchar_t *)(v32 + 2), 0x5Cu), v32 = *v31, v33) )
        v34 = ((__int64)v33 - v32) >> 1;
      else
        LODWORD(v34) = -1;
      v35 = v34 + 1;
      if ( v35 >= 0 && v35 < *(_DWORD *)(v32 - 16) )
      {
        v36 = wcschr((const wchar_t *)(v32 + 2LL * v35), 0x5Cu);
        if ( v36 )
          v37 = ((__int64)v36 - *v31) >> 1;
        else
          LODWORD(v37) = -1;
        if ( (_DWORD)v37 != -1 )
        {
          v38 = v37;
          if ( (int)v37 < 0 )
            v38 = 0;
          if ( (signed int)v38 < *(_DWORD *)(*v31 - 16LL) )
          {
            v39 = *(_QWORD *)(*v31 - 24LL);
            if ( !v39 || (v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39)) == 0 )
              v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
            ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(DeviceName, *v31, v38, v40);
          }
          else
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              DeviceName,
              v30 + 4);
          }
          std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::_Find_lower_bound<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
            &v63,
            lpTargetPath,
            DeviceName);
          v41 = *(unsigned __int16 **)DeviceName;
          if ( !*((_BYTE *)v74 + 25) )
          {
            v42 = *((_QWORD *)v74 + 4);
            if ( !v42 )
              ATL::AtlThrowImpl(-2147467259);
            v43 = *(unsigned __int16 **)DeviceName;
            v44 = v42 - *(_QWORD *)DeviceName;
            while ( 1 )
            {
              v45 = *v43;
              if ( *v43 != *(unsigned __int16 *)((char *)v43 + v44) )
                break;
              ++v43;
              if ( !v45 )
              {
                v46 = 0;
                goto LABEL_70;
              }
            }
            v46 = v45 < *(unsigned __int16 *)((char *)v43 + v44) ? -1 : 1;
LABEL_70:
            if ( v46 >= 0 && v74 != v63 )
            {
              v47 = *(_DWORD *)(*v31 - 16LL);
              v48 = v47 - v37;
              v49 = 0;
              if ( v48 >= 0 )
                v49 = v48;
              if ( v47 < 0 )
                v47 = 0;
              if ( v49 < v47 )
              {
                v51 = *(_QWORD *)(*v31 - 24LL);
                if ( !v51 || (v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51)) == 0 )
                  v52 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
                ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(
                  pbOutput,
                  *v31 + 2 * ((unsigned int)v47 - (__int64)v49),
                  (unsigned int)v49,
                  v52);
              }
              else
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  pbOutput,
                  v30 + 4);
              }
              v53 = v74;
              v54 = *(_QWORD *)(*((_QWORD *)v74 + 5) - 24LL);
              if ( !v54 || (v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 32LL))(v54)) == 0 )
                v50 = ((__int64 (__fastcall *)(void ***, __int64))ATL::g_strmgr[4])(&ATL::g_strmgr, v50);
              if ( !v50 )
                ATL::AtlThrowImpl(-2147467259);
              *(_QWORD *)pcbResult = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50) + 24;
              v55 = *(_QWORD *)pbOutput;
              ATL::CSimpleStringT<unsigned short,0>::Concatenate(
                (unsigned int)pcbResult,
                *((_QWORD *)v53 + 5),
                *(_DWORD *)(*((_QWORD *)v53 + 5) - 16LL),
                *(_DWORD *)pbOutput,
                *(_DWORD *)(*(_QWORD *)pbOutput - 16LL));
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v55 - 24 + 16), 0xFFFFFFFF) <= 1 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v55 - 24) + 8LL))(*(_QWORD *)(v55 - 24));
              v6 = v75;
              (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, ULONG *, BCRYPT_ALG_HANDLE *, union _LARGE_INTEGER, unsigned int))(*(_QWORD *)v75 + 152LL))(
                v75,
                pcbResult,
                phAlgorithm,
                a2,
                v67);
              v56 = (_QWORD *)(*(_QWORD *)pcbResult - 24LL);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)pcbResult - 24LL + 16), 0xFFFFFFFF) <= 1 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 8LL))(*v56);
            }
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v41 - 3) + 8LL))(*((_QWORD *)v41 - 3));
        }
      }
      v57 = (__int64 **)v30[2];
      if ( *((_BYTE *)v57 + 25) )
      {
        for ( j = v30[1]; !*(_BYTE *)(j + 25) && v30 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v30 = (_QWORD *)j;
        v30 = (_QWORD *)j;
      }
      else
      {
        v30 = (_QWORD *)v30[2];
        for ( k = *v57; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v30 = k;
      }
    }
    BCryptDestroyHash(phHash);
    BCryptCloseAlgorithmProvider(phAlgorithm[1], 0);
    free(pbHashObject[1]);
    pbHashObject[1] = 0;
    free(pbHashObject[0]);
    v4 = v67;
  }
  v60 = *((_QWORD *)v6 + 1);
  if ( v60 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v60 + 96LL))(
           v60,
           a2,
           v4,
           v72);
    if ( v8 == -2147467263 )
      v8 = 0;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
    &v63,
    &v63,
    *((_QWORD *)v63 + 1));
  operator delete(v63);
  return v8;
}

```

## disassembly

```asm
0x180031020  push    rbp
0x180031022  push    rbx
0x180031023  push    rsi
0x180031024  push    rdi
0x180031025  push    r12
0x180031027  push    r13
0x180031029  push    r14
0x18003102b  push    r15
0x18003102d  lea     rbp, [rsp-1Fh]
0x180031032  sub     rsp, 0E8h
0x180031039  mov     rax, cs:__security_cookie
0x180031040  xor     rax, rsp
0x180031043  mov     [rbp+57h+var_50], rax
0x180031047  mov     [rbp+57h+var_80], r9d
0x18003104b  mov     r12d, r8d
0x18003104e  mov     [rbp+57h+var_B8], r8d
0x180031052  mov     r14, rdx
0x180031055  mov     r13, rcx
0x180031058  mov     [rbp+57h+var_60], rcx
0x18003105c  xor     esi, esi
0x18003105e  mov     [rsp+120h+var_D8], rsi
0x180031063  mov     [rbp+57h+var_D0], rsi
0x180031067  lea     ecx, [rsi+30h]; Size
0x18003106a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003106f  mov     [rax], rax
0x180031072  mov     [rax+8], rax
0x180031076  mov     [rax+10h], rax
0x18003107a  lea     r15d, [rsi+1]
0x18003107e  mov     word ptr [rax+18h], 101h
0x180031084  mov     [rsp+120h+var_D8], rax
0x180031089  lea     eax, [rsi+5Fh]
0x18003108c  mov     [rbp+57h+DeviceName], ax
0x180031090  mov     dword ptr [rbp+57h+DeviceName+2], 3Ah ; ':'
0x180031097  mov     edi, esi
0x180031099  mov     word ptr [rbp+57h+pbOutput], di
0x18003109d  xorps   xmm0, xmm0
0x1800310a0  movdqu  xmmword ptr [rbp+57h+lpTargetPath], xmm0
0x1800310a5  mov     [rbp+57h+var_68], rsi
0x1800310a9  mov     ecx, 2027h; Size
0x1800310ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800310b3  test    rax, rax
0x1800310b6  jnz     short loc_1800310BD
0x1800310b8  lea     ecx, [rsi+5]
0x1800310bb  int     29h; Win8: RtlFailFast(ecx)
0x1800310bd  lea     rcx, [rax+27h]
0x1800310c1  and     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x1800310c5  mov     [rcx-8], rax
0x1800310c9  mov     [rbp+57h+lpTargetPath], rcx
0x1800310cd  lea     rbx, [rcx+2000h]
0x1800310d4  mov     [rbp+57h+var_68], rbx
0x1800310d8  mov     word ptr [rsp+120h+var_E0], si
0x1800310dd  mov     al, [rbp+57h+pbOutput+1]
0x1800310e0  cmp     al, byte ptr [rsp+120h+var_E0+1]
0x1800310e4  jnz     short loc_1800310EA
0x1800310e6  mov     eax, esi
0x1800310e8  jmp     short loc_1800310EF
0x1800310ea  sbb     eax, eax
0x1800310ec  or      eax, r15d
0x1800310ef  test    eax, eax
0x1800310f1  jnz     short loc_180031102
0x1800310f3  xor     edx, edx; Val
0x1800310f5  mov     r8d, 2000h; Size
0x1800310fb  call    memset_0
0x180031100  jmp     short loc_18003111E
0x180031102  mov     edx, 1000h
0x180031107  mov     rbx, rcx
0x18003110a  movzx   eax, si
0x18003110d  mov     rdi, rcx
0x180031110  mov     ecx, edx
0x180031112  rep stosw
0x180031115  add     rbx, 2
0x180031119  sub     rdx, r15
0x18003111c  jnz     short loc_180031115
0x18003111e  mov     [rbp+57h+lpTargetPath+8], rbx
0x180031122  mov     qword ptr [rsp+120h+var_E0], rsi
0x180031127  lea     rcx, [rsp+120h+var_E0]
0x18003112c  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x180031131  mov     eax, 41h ; 'A'
0x180031136  mov     [rbp+57h+DeviceName], ax
0x18003113a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003113e  mov     rdx, [rbp+57h+lpTargetPath]; lpTargetPath
0x180031142  mov     r8, [rbp+57h+lpTargetPath+8]
0x180031146  sub     r8, rdx
0x180031149  sar     r8, 1; ucchMax
0x18003114c  lea     rcx, [rbp+57h+DeviceName]; lpDeviceName
0x180031150  call    cs:__imp_QueryDosDeviceW
0x180031156  cmp     eax, r15d
0x180031159  jbe     loc_1800312AA
0x18003115f  lea     r8d, [rax-2]
0x180031163  mov     rdx, [rbp+57h+lpTargetPath]
0x180031167  lea     rcx, [rsp+120h+var_E0]
0x18003116c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x180031171  lea     r8, [rsp+120h+var_E0]
0x180031176  lea     rdx, [rbp+57h+phAlgorithm]
0x18003117a  lea     rcx, [rsp+120h+var_D8]
0x18003117f  call    ??$_Find_lower_bound@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::_Find_lower_bound<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031184  mov     rdi, [rbp+57h+phHash]
0x180031188  cmp     [rdi+19h], sil
0x18003118c  jnz     short loc_1800311C9
0x18003118e  mov     rcx, [rdi+20h]
0x180031192  test    rcx, rcx
0x180031195  jz      loc_1800317E6
0x18003119b  mov     rax, qword ptr [rsp+120h+var_E0]
0x1800311a0  sub     rcx, rax
0x1800311a3  movzx   edx, word ptr [rax]
0x1800311a6  cmp     dx, [rax+rcx]
0x1800311aa  jnz     short loc_1800311B9
0x1800311ac  add     rax, 2
0x1800311b0  test    dx, dx
0x1800311b3  jnz     short loc_1800311A3
0x1800311b5  mov     eax, esi
0x1800311b7  jmp     short loc_1800311BE
0x1800311b9  sbb     eax, eax
0x1800311bb  or      eax, r15d
0x1800311be  shr     eax, 1Fh
0x1800311c1  test    al, al
0x1800311c3  jz      loc_180031267
0x1800311c9  mov     rax, 555555555555555h
0x1800311d3  cmp     [rbp+57h+var_D0], rax
0x1800311d7  jz      loc_1800317F1
0x1800311dd  mov     rbx, [rsp+120h+var_D8]
0x1800311e2  lea     rax, [rsp+120h+var_D8]
0x1800311e7  mov     qword ptr [rbp+57h+pbOutput], rax
0x1800311eb  mov     ecx, 30h ; '0'; Size
0x1800311f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800311f5  mov     rsi, rax
0x1800311f8  lea     rdx, [rsp+120h+var_E0]
0x1800311fd  lea     rcx, [rax+20h]
0x180031201  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031206  nop
0x180031207  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003120e  mov     rax, [rcx+18h]
0x180031212  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180031219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003121e  add     rax, 18h
0x180031222  mov     [rsi+28h], rax
0x180031226  mov     [rsi], rbx
0x180031229  mov     [rsi+8], rbx
0x18003122d  mov     [rsi+10h], rbx
0x180031231  xor     eax, eax
0x180031233  mov     [rsi+18h], ax
0x180031237  mov     [rbp+57h+var_C0], rax
0x18003123b  lea     rcx, [rbp+57h+pbOutput]
0x18003123f  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)
0x180031244  movups  xmm0, xmmword ptr [rbp+57h+phAlgorithm]
0x180031248  movdqu  xmmword ptr [rbp+57h+phAlgorithm], xmm0
0x18003124d  mov     r8, rsi
0x180031250  lea     rdx, [rbp+57h+phAlgorithm]
0x180031254  lea     rcx, [rsp+120h+var_D8]
0x180031259  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18003125e  mov     rdi, rax
0x180031261  xor     esi, esi
0x180031263  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031267  lea     rcx, [rdi+28h]
0x18003126b  lea     rax, [rbp+57h+DeviceName]
0x18003126f  mov     r8, rbx
0x180031272  inc     r8
0x180031275  cmp     [rax+r8*2], si
0x18003127a  jnz     short loc_180031272
0x18003127c  lea     rdx, [rbp+57h+DeviceName]
0x180031280  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180031285  mov     rdx, qword ptr [rsp+120h+var_E0]
0x18003128a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003128e  mov     eax, ebx
0x180031290  lock xadd [rdx+10h], eax
0x180031295  add     eax, ebx
0x180031297  test    eax, eax
0x180031299  jg      short loc_1800312AA
0x18003129b  mov     rcx, [rdx]
0x18003129e  mov     rax, [rcx]
0x1800312a1  mov     rax, [rax+8]
0x1800312a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312aa  movzx   eax, [rbp+57h+DeviceName]
0x1800312ae  add     ax, r15w
0x1800312b2  mov     [rbp+57h+DeviceName], ax
0x1800312b6  cmp     ax, 5Bh ; '['
0x1800312ba  jnz     loc_18003113E
0x1800312c0  lea     rcx, [rbp+57h+lpTargetPath]
0x1800312c4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800312c9  cmp     [r13+48h], rsi
0x1800312cd  jz      loc_180031765
0x1800312d3  mov     byte ptr [rbp+57h+phAlgorithm], sil
0x1800312d7  xorps   xmm0, xmm0
0x1800312da  movdqu  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x1800312df  mov     r12d, 20h ; ' '
0x1800312e5  mov     r9d, r12d; dwFlags
0x1800312e8  xor     r8d, r8d; pszImplementation
0x1800312eb  lea     rdx, pszAlgId; "SHA256"
0x1800312f2  lea     rcx, [rbp+57h+phAlgorithm+8]; phAlgorithm
0x1800312f6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800312fc  test    eax, eax
0x1800312fe  js      loc_180031403
0x180031304  mov     dword ptr [rbp+57h+pbOutput], esi
0x180031307  mov     [rsp+120h+var_E0], esi
0x18003130b  mov     [rsp+120h+dwFlags], esi; dwFlags
0x18003130f  lea     rax, [rsp+120h+var_E0]
0x180031314  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180031319  lea     edi, [r12-1Ch]
0x18003131e  mov     r9d, edi; cbOutput
0x180031321  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180031325  lea     rdx, pszProperty; "ObjectLength"
0x18003132c  mov     rcx, [rbp+57h+phAlgorithm+8]; hObject
0x180031330  call    cs:__imp_BCryptGetProperty
0x180031336  test    eax, eax
0x180031338  js      loc_180031403
0x18003133e  cmp     [rsp+120h+var_E0], edi
0x180031342  jnz     loc_180031403
0x180031348  mov     ecx, dword ptr [rbp+57h+pbOutput]; Size
0x18003134b  test    rcx, rcx
0x18003134e  jnz     short loc_180031355
0x180031350  mov     rcx, rsi
0x180031353  jmp     short loc_180031366
0x180031355  xor     edx, edx
0x180031357  mov     rax, rbx
0x18003135a  div     rcx
0x18003135d  cmp     rax, r15
0x180031360  jb      loc_180031403
0x180031366  call    cs:__imp_malloc
0x18003136c  mov     [rbp+57h+pbHashObject], rax
0x180031370  test    rax, rax
0x180031373  jz      loc_180031403
0x180031379  mov     [rsp+120h+dwFlags], esi; dwFlags
0x18003137d  lea     rax, [rsp+120h+var_E0]
0x180031382  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180031387  mov     r9d, edi; cbOutput
0x18003138a  lea     r8, [rbp+57h+var_88]; pbOutput
0x18003138e  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180031395  mov     rcx, [rbp+57h+phAlgorithm+8]; hObject
0x180031399  call    cs:__imp_BCryptGetProperty
0x18003139f  test    eax, eax
0x1800313a1  js      short loc_180031403
0x1800313a3  cmp     [rsp+120h+var_E0], edi
0x1800313a7  jnz     short loc_180031403
0x1800313a9  mov     ecx, dword ptr [rbp+57h+var_88]; Size
0x1800313ac  test    rcx, rcx
0x1800313af  jnz     short loc_1800313B6
0x1800313b1  mov     rcx, rsi
0x1800313b4  jmp     short loc_1800313C3
0x1800313b6  xor     edx, edx
0x1800313b8  mov     rax, rbx
0x1800313bb  div     rcx
0x1800313be  cmp     rax, r15
0x1800313c1  jb      short loc_180031403
0x1800313c3  call    cs:__imp_malloc
0x1800313c9  mov     [rbp+57h+pbHashObject+8], rax
0x1800313cd  test    rax, rax
0x1800313d0  jz      short loc_180031403
0x1800313d2  mov     [rsp+120h+var_F0], r12d; dwFlags
0x1800313d7  mov     [rsp+120h+dwFlags], esi; cbSecret
0x1800313db  mov     [rsp+120h+pcbResult], rsi; pbSecret
0x1800313e0  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800313e4  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x1800313e8  lea     rdx, [rbp+57h+phHash]; phHash
0x1800313ec  mov     rcx, [rbp+57h+phAlgorithm+8]; hAlgorithm
0x1800313f0  call    cs:__imp_BCryptCreateHash
0x1800313f6  movzx   ecx, byte ptr [rbp+57h+phAlgorithm]
0x1800313fa  test    eax, eax
0x1800313fc  cmovns  ecx, r15d
0x180031400  mov     byte ptr [rbp+57h+phAlgorithm], cl
0x180031403  mov     rbx, [r13+40h]
0x180031407  mov     rbx, [rbx]
0x18003140a  cmp     rbx, [r13+40h]
0x18003140e  jz      loc_180031733
0x180031414  lea     r12, [rbx+20h]
0x180031418  mov     rcx, [r12]
0x18003141c  cmp     [rcx-10h], r15d
0x180031420  jle     short loc_180031442
0x180031422  mov     edx, 5Ch ; '\'; Ch
0x180031427  add     rcx, 2; Str
0x18003142b  call    cs:__imp_wcschr
0x180031431  mov     rcx, [r12]
0x180031435  test    rax, rax
0x180031438  jz      short loc_180031442
0x18003143a  sub     rax, rcx
0x18003143d  sar     rax, 1
0x180031440  jmp     short loc_180031445
0x180031442  or      eax, 0FFFFFFFFh
0x180031445  add     eax, 1
0x180031448  js      loc_1800316E4
0x18003144e  cmp     eax, [rcx-10h]
0x180031451  jge     loc_1800316E4
0x180031457  mov     edx, 5Ch ; '\'; Ch
0x18003145c  cdqe
0x18003145e  lea     rcx, [rcx+rax*2]; Str
0x180031462  call    cs:__imp_wcschr
0x180031468  mov     rdi, rax
0x18003146b  test    rax, rax
0x18003146e  jnz     short loc_180031475
0x180031470  or      edi, 0FFFFFFFFh
0x180031473  jmp     short loc_18003147C
0x180031475  sub     rdi, [r12]
0x180031479  sar     rdi, 1
0x18003147c  cmp     edi, 0FFFFFFFFh
0x18003147f  jz      loc_1800316E4
0x180031485  mov     esi, edi
0x180031487  xor     eax, eax
0x180031489  test    edi, edi
0x18003148b  cmovs   esi, eax
0x18003148e  mov     rcx, [r12]
0x180031492  cmp     esi, [rcx-10h]
  ... truncated ...
```
