# Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800239c0`
- end: `0x18002424d`
- name: `?OnAfterEvents@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `2189`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001870`
- `0x180001894`
- `0x1800018a0`
- `0x1800023d8`
- `0x1800023e4`
- `0x180002420`
- `0x180003bb8`
- `0x180007da8`
- `0x18000cf40`
- `0x18000cfe4`
- `0x180011774`
- `0x180015920`
- `0x180015b50`
- `0x180022b28`
- `0x180022e08`
- `0x180022f78`
- `0x18002310c`
- `0x18002319c`
- `0x1800239c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e2b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e65`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e2b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e65`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180023af5`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180023af5`
- `bcrypt!BCryptCreateHash` at `0x180023df1`
- `bcrypt!BCryptCreateHash` at `0x180023df1`
- `bcrypt!BCryptGetProperty` at `0x180023d2f`
- `bcrypt!BCryptGetProperty` at `0x180023d99`
- `bcrypt!BCryptGetProperty` at `0x180023d2f`
- `bcrypt!BCryptGetProperty` at `0x180023d99`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180023cf1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180023cf1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180024192`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180024192`
- `bcrypt!BCryptDestroyHash` at `0x180024186`
- `bcrypt!BCryptDestroyHash` at `0x180024186`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  _QWORD *v5; // rax
  unsigned int v6; // r12d
  void *v7; // rax
  WCHAR *v8; // rcx
  WCHAR *v9; // rbx
  int v10; // eax
  WCHAR *v11; // rdi
  __int64 v12; // rdx
  __int64 i; // rcx
  DWORD DosDeviceW; // eax
  void *v15; // r13
  unsigned __int16 *v16; // rax
  int v17; // esi
  _BYTE *inserted; // r8
  _QWORD *v19; // r15
  _QWORD *v20; // rcx
  unsigned __int16 *v21; // rdx
  __int64 v22; // r10
  int v23; // edi
  int v24; // r9d
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // edx
  int v28; // edi
  _QWORD *v29; // rbx
  char *v30; // rcx
  __int64 v31; // r8
  _QWORD *v32; // rdx
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v33; // rdi
  size_t v34; // rcx
  size_t v35; // rcx
  NTSTATUS v36; // eax
  char v37; // cl
  _QWORD *v38; // rbx
  _QWORD *v39; // r15
  __int64 v40; // rcx
  wchar_t *v41; // rax
  __int64 v42; // rax
  int v43; // eax
  wchar_t *v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rcx
  unsigned int v47; // esi
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned __int16 *v50; // rsi
  _BYTE *v51; // r11
  _QWORD *v52; // rcx
  unsigned __int16 *v53; // rdx
  __int64 v54; // r10
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rdx
  unsigned __int16 *v58; // rcx
  __int64 v59; // rdx
  int v60; // r8d
  int v61; // r9d
  int v62; // r13d
  int v63; // eax
  int v64; // edi
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // r15
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rdi
  _QWORD *v73; // rdx
  __int64 **v74; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  __int64 v77; // rcx
  ULONG pcbResult[2]; // [rsp+40h] [rbp-C0h] BYREF
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v80; // [rsp+48h] [rbp-B8h]
  _QWORD v81[2]; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbOutput[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v83; // [rsp+68h] [rbp-98h]
  int v84; // [rsp+6Ch] [rbp-94h]
  unsigned int v85; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  __int64 v87; // [rsp+80h] [rbp-80h]
  unsigned int v88; // [rsp+88h] [rbp-78h]
  LPWSTR lpTargetPath[2]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v90; // [rsp+A0h] [rbp-60h]
  char v91[8]; // [rsp+A8h] [rbp-58h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+B0h] [rbp-50h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+B8h] [rbp-48h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+C0h] [rbp-40h]
  UCHAR v95[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v96[2]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR DeviceName[4]; // [rsp+E8h] [rbp-18h] BYREF

  v80 = this;
  v88 = a4;
  v85 = a3;
  v87 = 0;
  v5 = operator new(0x30u);
  wcscpy(&DeviceName[1], L":");
  v90 = 0;
  *(_WORD *)pbOutput = 0;
  *v5 = v5;
  v6 = 1;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  Block = v5;
  DeviceName[0] = 95;
  *(_OWORD *)lpTargetPath = 0;
  v7 = operator new(0x2027u);
  if ( !v7 )
    __fastfail(5u);
  LOWORD(pcbResult[0]) = 0;
  v8 = (WCHAR *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v8 - 1) = v7;
  v9 = v8 + 4096;
  lpTargetPath[0] = v8;
  v90 = v8 + 4096;
  if ( pbOutput[1] == BYTE1(pcbResult[0]) )
    v10 = 0;
  else
    v10 = pbOutput[1] < BYTE1(pcbResult[0]) ? -1 : 1;
  if ( v10 )
  {
    v9 = v8;
    v11 = v8;
    v12 = 4096;
    for ( i = 4096; i; --i )
      *v11++ = 0;
    do
    {
      ++v9;
      --v12;
    }
    while ( v12 );
  }
  else
  {
    memset_0(v8, 0, 0x2000u);
  }
  lpTargetPath[1] = v9;
  v81[0] = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(v81);
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
      v15 = Block;
      v81[0] = 0;
      v16 = *(unsigned __int16 **)pcbResult;
      v17 = 0;
      inserted = Block;
      v19 = (_QWORD *)*((_QWORD *)Block + 1);
      v20 = v19;
      if ( !*((_BYTE *)v19 + 25) )
      {
        while ( 1 )
        {
          v19 = v20;
          if ( !*(_QWORD *)pcbResult )
            break;
          v21 = (unsigned __int16 *)v20[4];
          v22 = *(_QWORD *)pcbResult - (_QWORD)v21;
          do
          {
            v23 = *(unsigned __int16 *)((char *)v21 + v22);
            v24 = *v21 - v23;
            if ( v24 )
              break;
            ++v21;
          }
          while ( v23 );
          if ( v24 >= 0 )
          {
            inserted = v20;
            v17 = 1;
            v20 = (_QWORD *)*v20;
          }
          else
          {
            v20 = (_QWORD *)v20[2];
            v17 = 0;
          }
          if ( *((_BYTE *)v20 + 25) )
            goto LABEL_23;
        }
LABEL_127:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_23:
      if ( inserted[25] )
        goto LABEL_29;
      v25 = *((_QWORD *)inserted + 4);
      if ( !v25 )
        goto LABEL_127;
      v26 = v25 - *(_QWORD *)pcbResult;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v16 + v26);
        v28 = *v16 - v27;
        if ( v28 )
          break;
        ++v16;
      }
      while ( v27 );
      if ( v28 < 0 )
      {
LABEL_29:
        if ( v87 == 0x555555555555555LL )
          std::_Throw_tree_length_error();
        v96[0] = &Block;
        v29 = operator new(0x30u);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          v29 + 4,
          pcbResult);
        v29[5] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        *v29 = v15;
        v29[1] = v15;
        v29[2] = v15;
        *((_WORD *)v29 + 12) = 0;
        v96[1] = 0;
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(v96);
        v84 = v81[0];
        *(_QWORD *)pbOutput = v19;
        v83 = v17;
        inserted = (_BYTE *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                              &Block,
                              pbOutput,
                              v29);
      }
      v30 = inserted + 40;
      v31 = -1;
      do
        ++v31;
      while ( DeviceName[v31] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v30, DeviceName, v31);
      v32 = (_QWORD *)(*(_QWORD *)pcbResult - 24LL);
      if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)pcbResult - 24LL + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 8LL))(*v32);
    }
    ++DeviceName[0];
  }
  while ( DeviceName[0] != 91 );
  std::vector<unsigned short>::~vector<unsigned short>(lpTargetPath);
  v33 = v80;
  if ( *((_QWORD *)v80 + 9) )
  {
    v91[0] = 0;
    *(_OWORD *)pbHashObject = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0x20u) < 0 )
      goto LABEL_53;
    *(_DWORD *)pbOutput = 0;
    pcbResult[0] = 0;
    if ( BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, pcbResult, 0) < 0 || pcbResult[0] != 4 )
      goto LABEL_53;
    v34 = *(unsigned int *)pbOutput;
    if ( *(_DWORD *)pbOutput )
    {
      if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)pbOutput) )
        goto LABEL_53;
    }
    else
    {
      v34 = 0;
    }
    pbHashObject[0] = (PUCHAR)o_malloc_0(v34);
    if ( pbHashObject[0]
      && BCryptGetProperty(phAlgorithm, L"HashDigestLength", v95, 4u, pcbResult, 0) >= 0
      && pcbResult[0] == 4 )
    {
      v35 = *(unsigned int *)v95;
      if ( !*(_DWORD *)v95 )
      {
        v35 = 0;
        goto LABEL_49;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)v95 )
      {
LABEL_49:
        pbHashObject[1] = (PUCHAR)o_malloc_0(v35);
        if ( pbHashObject[1] )
        {
          v36 = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0x20u);
          v37 = v91[0];
          if ( v36 >= 0 )
            v37 = 1;
          v91[0] = v37;
        }
      }
    }
LABEL_53:
    v38 = (_QWORD *)**((_QWORD **)v33 + 8);
    while ( 1 )
    {
      if ( v38 == *((_QWORD **)v33 + 8) )
      {
        BCryptDestroyHash(phHash);
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        free(pbHashObject[1]);
        pbHashObject[1] = 0;
        free(pbHashObject[0]);
        break;
      }
      v39 = v38 + 4;
      v40 = v38[4];
      if ( *(int *)(v40 - 16) <= 1 )
      {
        v43 = 0;
      }
      else
      {
        v41 = wcschr((const wchar_t *)(v40 + 2), 0x5Cu);
        if ( v41 )
          v42 = ((__int64)v41 - *v39) >> 1;
        else
          LODWORD(v42) = -1;
        v43 = v42 + 1;
        if ( v43 < 0 )
          goto LABEL_112;
      }
      if ( v43 < *(_DWORD *)(*v39 - 16LL) )
      {
        v44 = wcschr((const wchar_t *)(*v39 + 2LL * v43), 0x5Cu);
        if ( v44 )
          v45 = ((__int64)v44 - *v39) >> 1;
        else
          LODWORD(v45) = -1;
        if ( (_DWORD)v45 == -1 )
        {
          v33 = v80;
        }
        else
        {
          v46 = *v39;
          v47 = v45;
          if ( (int)v45 < 0 )
            v47 = 0;
          if ( (signed int)v47 < *(_DWORD *)(v46 - 16) )
          {
            v48 = *(_QWORD *)(v46 - 24);
            if ( !v48 || (v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 32LL))(v48)) == 0 )
              v49 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
            ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(pcbResult, *v39, v47, v49);
          }
          else
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              pcbResult,
              v38 + 4);
          }
          v50 = *(unsigned __int16 **)pcbResult;
          v51 = Block;
          HIDWORD(lpTargetPath[1]) = 0;
          *(_QWORD *)pbOutput = Block;
          v52 = (_QWORD *)*((_QWORD *)Block + 1);
          while ( !*((_BYTE *)v52 + 25) )
          {
            if ( !*(_QWORD *)pcbResult )
              goto LABEL_126;
            v53 = (unsigned __int16 *)v52[4];
            v54 = *(_QWORD *)pcbResult - (_QWORD)v53;
            do
            {
              v55 = *(unsigned __int16 *)((char *)v53 + v54);
              v56 = *v53 - v55;
              if ( v56 )
                break;
              ++v53;
            }
            while ( v55 );
            if ( v56 >= 0 )
            {
              v51 = v52;
              *(_QWORD *)pbOutput = v52;
              v52 = (_QWORD *)*v52;
            }
            else
            {
              v52 = (_QWORD *)v52[2];
            }
          }
          if ( v51[25] )
            goto LABEL_108;
          v57 = *((_QWORD *)v51 + 4);
          if ( !v57 )
LABEL_126:
            ATL::AtlThrowImpl(-2147467259);
          v58 = *(unsigned __int16 **)pcbResult;
          v59 = v57 - *(_QWORD *)pcbResult;
          do
          {
            v60 = *(unsigned __int16 *)((char *)v58 + v59);
            v61 = *v58 - v60;
            if ( v61 )
              break;
            ++v58;
          }
          while ( v60 );
          if ( v61 < 0 || v51 == Block )
          {
LABEL_108:
            v33 = v80;
          }
          else
          {
            v62 = *(_DWORD *)(*v39 - 16LL);
            v63 = v62 - v45;
            v64 = 0;
            if ( v63 >= 0 )
              v64 = v63;
            if ( v62 < 0 )
              v62 = 0;
            if ( v64 < v62 )
            {
              v65 = *(_QWORD *)(*v39 - 24LL);
              if ( !v65 || (v66 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 32LL))(v65)) == 0 )
                v66 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(
                v81,
                *v39 + 2 * ((unsigned int)v62 - (__int64)v64),
                (unsigned int)v64,
                v66);
            }
            else
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v81,
                v38 + 4);
            }
            v67 = *(_QWORD *)pbOutput;
            v68 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)pbOutput + 40LL) - 24LL);
            if ( !v68 || (v69 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 32LL))(v68)) == 0 )
            {
              v69 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              if ( !v69 )
                ATL::AtlThrowImpl(-2147467259);
            }
            v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 24LL))(v69);
            v71 = *(_QWORD *)(v67 + 40);
            v72 = v81[0];
            *(_QWORD *)DeviceName = v70 + 24;
            ATL::CSimpleStringT<unsigned short,0>::Concatenate(
              (unsigned int)DeviceName,
              v71,
              *(_DWORD *)(v71 - 16),
              v81[0],
              *(_DWORD *)(v81[0] - 16LL));
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v72 - 24 + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v72 - 24) + 8LL))(*(_QWORD *)(v72 - 24));
            v33 = v80;
            (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, WCHAR *, char *, union _LARGE_INTEGER, unsigned int))(*(_QWORD *)v80 + 152LL))(
              v80,
              DeviceName,
              v91,
              a2,
              v85);
            v73 = (_QWORD *)(*(_QWORD *)DeviceName - 24LL);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)DeviceName - 24LL + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v73 + 8LL))(*v73);
          }
          if ( _InterlockedDecrement((volatile signed __int32 *)v50 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v50 - 3) + 8LL))(*((_QWORD *)v50 - 3));
        }
      }
LABEL_112:
      v74 = (__int64 **)v38[2];
      if ( *((_BYTE *)v74 + 25) )
      {
        for ( j = v38[1]; !*(_BYTE *)(j + 25) && v38 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v38 = (_QWORD *)j;
        v38 = (_QWORD *)j;
      }
      else
      {
        v38 = (_QWORD *)v38[2];
        for ( k = *v74; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v38 = k;
      }
    }
  }
  v77 = *((_QWORD *)v33 + 1);
  if ( v77 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v77 + 96LL))(
           v77,
           a2,
           v85,
           v88);
    if ( v6 == -2147467263 )
      v6 = 0;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
    &Block,
    &Block,
    *((_QWORD *)Block + 1));
  operator delete(Block);
  return v6;
}

```

## disassembly

```asm
0x1800239c0  push    rbp
0x1800239c2  push    rbx
0x1800239c3  push    rsi
0x1800239c4  push    rdi
0x1800239c5  push    r12
0x1800239c7  push    r13
0x1800239c9  push    r14
0x1800239cb  push    r15
0x1800239cd  lea     rbp, [rsp-8]
0x1800239d2  sub     rsp, 108h
0x1800239d9  mov     rax, cs:__security_cookie
0x1800239e0  xor     rax, rsp
0x1800239e3  mov     [rbp+40h+var_50], rax
0x1800239e7  xor     r13d, r13d
0x1800239ea  mov     [rsp+140h+var_F8], rcx
0x1800239ef  mov     [rbp+40h+var_B8], r9d
0x1800239f3  mov     r14, rdx
0x1800239f6  mov     [rsp+140h+var_D0], r8d
0x1800239fb  mov     [rsp+140h+Block], r13
0x180023a00  lea     ecx, [r13+30h]; Size
0x180023a04  mov     [rbp+40h+var_C0], r13
0x180023a08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a0d  xorps   xmm0, xmm0
0x180023a10  mov     dword ptr [rbp+40h+DeviceName+2], 3Ah ; ':'
0x180023a17  mov     edi, r13d
0x180023a1a  mov     [rbp+40h+var_A0], r13
0x180023a1e  mov     ecx, 2027h; Size
0x180023a23  mov     word ptr [rsp+140h+pbOutput], di
0x180023a28  mov     [rax], rax
0x180023a2b  lea     r12d, [r13+1]
0x180023a2f  mov     [rax+8], rax
0x180023a33  mov     [rax+10h], rax
0x180023a37  mov     word ptr [rax+18h], 101h
0x180023a3d  mov     [rsp+140h+Block], rax
0x180023a42  lea     eax, [r13+5Fh]
0x180023a46  mov     [rbp+40h+DeviceName], ax
0x180023a4a  movdqu  xmmword ptr [rbp+40h+lpTargetPath], xmm0
0x180023a4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a54  test    rax, rax
0x180023a57  jnz     short loc_180023A5E
0x180023a59  lea     ecx, [rax+5]
0x180023a5c  int     29h; Win8: RtlFailFast(ecx)
0x180023a5e  lea     rcx, [rax+27h]
0x180023a62  mov     word ptr [rsp+140h+var_100], r13w
0x180023a68  and     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x180023a6c  mov     [rcx-8], rax
0x180023a70  lea     rbx, [rcx+2000h]
0x180023a77  mov     al, [rsp+140h+pbOutput+1]
0x180023a7b  mov     [rbp+40h+lpTargetPath], rcx
0x180023a7f  mov     [rbp+40h+var_A0], rbx
0x180023a83  cmp     al, byte ptr [rsp+140h+var_100+1]
0x180023a87  jnz     short loc_180023A8E
0x180023a89  mov     eax, r13d
0x180023a8c  jmp     short loc_180023A93
0x180023a8e  sbb     eax, eax
0x180023a90  or      eax, r12d
0x180023a93  test    eax, eax
0x180023a95  jnz     short loc_180023AA6
0x180023a97  xor     edx, edx; Val
0x180023a99  mov     r8d, 2000h; Size
0x180023a9f  call    memset_0
0x180023aa4  jmp     short loc_180023AC3
0x180023aa6  mov     rbx, rcx
0x180023aa9  movzx   eax, r13w
0x180023aad  mov     rdi, rcx
0x180023ab0  mov     edx, 1000h
0x180023ab5  mov     ecx, edx
0x180023ab7  rep stosw
0x180023aba  add     rbx, 2
0x180023abe  sub     rdx, r12
0x180023ac1  jnz     short loc_180023ABA
0x180023ac3  lea     rcx, [rsp+140h+var_F0]
0x180023ac8  mov     [rbp+40h+lpTargetPath+8], rbx
0x180023acc  mov     [rsp+140h+var_F0], r13
0x180023ad1  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x180023ad6  mov     eax, 41h ; 'A'
0x180023adb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023adf  mov     [rbp+40h+DeviceName], ax
0x180023ae3  mov     rdx, [rbp+40h+lpTargetPath]; lpTargetPath
0x180023ae7  lea     rcx, [rbp+40h+DeviceName]; lpDeviceName
0x180023aeb  mov     r8, [rbp+40h+lpTargetPath+8]
0x180023aef  sub     r8, rdx
0x180023af2  sar     r8, 1; ucchMax
0x180023af5  call    cs:__imp_QueryDosDeviceW
0x180023afb  cmp     eax, r12d
0x180023afe  jbe     loc_180023CA0
0x180023b04  mov     rdx, [rbp+40h+lpTargetPath]
0x180023b08  lea     r8d, [rax-2]
0x180023b0c  lea     rcx, [rsp+140h+var_100]
0x180023b11  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x180023b16  mov     r13, [rsp+140h+Block]
0x180023b1b  xor     eax, eax
0x180023b1d  xor     r11d, r11d
0x180023b20  mov     [rsp+140h+var_F0], rax
0x180023b25  mov     rax, qword ptr [rsp+140h+var_100]
0x180023b2a  mov     esi, r11d
0x180023b2d  mov     r8, r13
0x180023b30  mov     r15, [r13+8]
0x180023b34  mov     rcx, r15
0x180023b37  cmp     [r15+19h], r11b
0x180023b3b  jnz     short loc_180023B86
0x180023b3d  mov     r15, rcx
0x180023b40  test    rax, rax
0x180023b43  jz      loc_180024231
0x180023b49  mov     rdx, [rcx+20h]
0x180023b4d  mov     r10, rax
0x180023b50  sub     r10, rdx
0x180023b53  movzx   r9d, word ptr [rdx]
0x180023b57  movzx   edi, word ptr [rdx+r10]
0x180023b5c  sub     r9d, edi
0x180023b5f  jnz     short loc_180023B69
0x180023b61  add     rdx, 2
0x180023b65  test    edi, edi
0x180023b67  jnz     short loc_180023B53
0x180023b69  test    r9d, r9d
0x180023b6c  jns     short loc_180023B77
0x180023b6e  mov     rcx, [rcx+10h]
0x180023b72  mov     esi, r11d
0x180023b75  jmp     short loc_180023B80
0x180023b77  mov     r8, rcx
0x180023b7a  mov     esi, r12d
0x180023b7d  mov     rcx, [rcx]
0x180023b80  cmp     [rcx+19h], r11b
0x180023b84  jz      short loc_180023B3D
0x180023b86  cmp     [r8+19h], r11b
0x180023b8a  jnz     short loc_180023BBB
0x180023b8c  mov     rcx, [r8+20h]
0x180023b90  test    rcx, rcx
0x180023b93  jz      loc_180024231
0x180023b99  sub     rcx, rax
0x180023b9c  movzx   edi, word ptr [rax]
0x180023b9f  movzx   edx, word ptr [rax+rcx]
0x180023ba3  sub     edi, edx
0x180023ba5  jnz     short loc_180023BAF
0x180023ba7  add     rax, 2
0x180023bab  test    edx, edx
0x180023bad  jnz     short loc_180023B9C
0x180023baf  test    edi, edi
0x180023bb1  js      short loc_180023BBB
0x180023bb3  xor     r13d, r13d
0x180023bb6  jmp     loc_180023C59
0x180023bbb  mov     rax, 555555555555555h
0x180023bc5  cmp     [rbp+40h+var_C0], rax
0x180023bc9  jz      loc_18002423C
0x180023bcf  lea     rax, [rsp+140h+Block]
0x180023bd4  mov     ecx, 30h ; '0'; Size
0x180023bd9  mov     [rbp+40h+var_68], rax
0x180023bdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023be2  lea     rdx, [rsp+140h+var_100]
0x180023be7  mov     rbx, rax
0x180023bea  lea     rcx, [rax+20h]
0x180023bee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023bf3  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180023bfa  mov     rax, [rcx+18h]
0x180023bfe  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180023c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c0a  add     rax, 18h
0x180023c0e  lea     rcx, [rbp+40h+var_68]
0x180023c12  mov     [rbx+28h], rax
0x180023c16  mov     [rbx], r13
0x180023c19  mov     [rbx+8], r13
0x180023c1d  mov     [rbx+10h], r13
0x180023c21  xor     r13d, r13d
0x180023c24  mov     [rbx+18h], r13w
0x180023c29  mov     [rbp+40h+var_60], r13
0x180023c2d  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)
0x180023c32  mov     rax, [rsp+140h+var_F0]
0x180023c37  lea     rdx, [rsp+140h+pbOutput]
0x180023c3c  mov     r8, rbx
0x180023c3f  mov     [rsp+140h+var_D4], eax
0x180023c43  lea     rcx, [rsp+140h+Block]
0x180023c48  mov     qword ptr [rsp+140h+pbOutput], r15
0x180023c4d  mov     [rsp+140h+var_D8], esi
0x180023c51  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180023c56  mov     r8, rax
0x180023c59  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023c5d  lea     rcx, [r8+28h]
0x180023c61  mov     r8, rsi
0x180023c64  lea     rax, [rbp+40h+DeviceName]
0x180023c68  inc     r8
0x180023c6b  cmp     [rax+r8*2], r13w
0x180023c70  jnz     short loc_180023C68
0x180023c72  lea     rdx, [rbp+40h+DeviceName]
0x180023c76  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180023c7b  mov     rdx, qword ptr [rsp+140h+var_100]
0x180023c80  mov     eax, esi
0x180023c82  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180023c86  lock xadd [rdx+10h], eax
0x180023c8b  add     eax, esi
0x180023c8d  test    eax, eax
0x180023c8f  jg      short loc_180023CA0
0x180023c91  mov     rcx, [rdx]
0x180023c94  mov     rax, [rcx]
0x180023c97  mov     rax, [rax+8]
0x180023c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ca0  movzx   eax, [rbp+40h+DeviceName]
0x180023ca4  add     ax, r12w
0x180023ca8  mov     [rbp+40h+DeviceName], ax
0x180023cac  cmp     ax, 5Bh ; '['
0x180023cb0  jnz     loc_180023AE3
0x180023cb6  lea     rcx, [rbp+40h+lpTargetPath]
0x180023cba  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180023cbf  mov     rdi, [rsp+140h+var_F8]
0x180023cc4  cmp     [rdi+48h], r13
0x180023cc8  jz      loc_1800241AE
0x180023cce  xorps   xmm0, xmm0
0x180023cd1  mov     [rbp+40h+var_98], r13b
0x180023cd5  mov     r15d, 20h ; ' '
0x180023cdb  lea     rdx, pszAlgId; "SHA256"
0x180023ce2  mov     r9d, r15d; dwFlags
0x180023ce5  lea     rcx, [rbp+40h+phAlgorithm]; phAlgorithm
0x180023ce9  xor     r8d, r8d; pszImplementation
0x180023cec  movdqu  xmmword ptr [rbp+40h+pbHashObject], xmm0
0x180023cf1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180023cf7  test    eax, eax
0x180023cf9  js      loc_180023E04
0x180023cff  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x180023d03  lea     rax, [rsp+140h+var_100]
0x180023d08  lea     ebx, [r15-1Ch]
0x180023d0c  mov     [rsp+140h+dwFlags], r13d; dwFlags
0x180023d11  mov     r9d, ebx; cbOutput
0x180023d14  mov     dword ptr [rsp+140h+pbOutput], r13d
0x180023d19  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x180023d1e  mov     [rsp+140h+var_100], r13d
0x180023d23  lea     rdx, pszProperty; "ObjectLength"
0x180023d2a  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180023d2f  call    cs:__imp_BCryptGetProperty
0x180023d35  test    eax, eax
0x180023d37  js      loc_180023E04
0x180023d3d  cmp     [rsp+140h+var_100], ebx
0x180023d41  jnz     loc_180023E04
0x180023d47  mov     ecx, dword ptr [rsp+140h+pbOutput]; Size
0x180023d4b  test    rcx, rcx
0x180023d4e  jnz     short loc_180023D55
0x180023d50  mov     rcx, r13
0x180023d53  jmp     short loc_180023D66
0x180023d55  xor     edx, edx
0x180023d57  mov     rax, rsi
0x180023d5a  div     rcx
0x180023d5d  cmp     rax, r12
0x180023d60  jb      loc_180023E04
0x180023d66  call    _o_malloc_0
0x180023d6b  mov     [rbp+40h+pbHashObject], rax
0x180023d6f  test    rax, rax
0x180023d72  jz      loc_180023E04
0x180023d78  mov     rcx, [rbp+40h+phAlgorithm]; hObject
0x180023d7c  lea     rax, [rsp+140h+var_100]
0x180023d81  mov     [rsp+140h+dwFlags], r13d; dwFlags
0x180023d86  lea     r8, [rbp+40h+var_70]; pbOutput
0x180023d8a  mov     r9d, ebx; cbOutput
0x180023d8d  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180023d92  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180023d99  call    cs:__imp_BCryptGetProperty
0x180023d9f  test    eax, eax
0x180023da1  js      short loc_180023E04
0x180023da3  cmp     [rsp+140h+var_100], ebx
0x180023da7  jnz     short loc_180023E04
0x180023da9  mov     ecx, dword ptr [rbp+40h+var_70]; Size
0x180023dac  test    rcx, rcx
0x180023daf  jnz     short loc_180023DB6
0x180023db1  mov     rcx, r13
0x180023db4  jmp     short loc_180023DC3
0x180023db6  xor     edx, edx
0x180023db8  mov     rax, rsi
0x180023dbb  div     rcx
0x180023dbe  cmp     rax, r12
0x180023dc1  jb      short loc_180023E04
0x180023dc3  call    _o_malloc_0
0x180023dc8  mov     [rbp+40h+pbHashObject+8], rax
0x180023dcc  test    rax, rax
0x180023dcf  jz      short loc_180023E04
0x180023dd1  mov     r9d, dword ptr [rsp+140h+pbOutput]; cbHashObject
0x180023dd6  lea     rdx, [rbp+40h+phHash]; phHash
0x180023dda  mov     r8, [rbp+40h+pbHashObject]; pbHashObject
0x180023dde  mov     rcx, [rbp+40h+phAlgorithm]; hAlgorithm
0x180023de2  mov     [rsp+140h+var_110], r15d; dwFlags
0x180023de7  mov     [rsp+140h+dwFlags], r13d; cbSecret
0x180023dec  mov     [rsp+140h+pcbResult], r13; pbSecret
0x180023df1  call    cs:__imp_BCryptCreateHash
0x180023df7  movzx   ecx, [rbp+40h+var_98]
0x180023dfb  test    eax, eax
0x180023dfd  cmovns  ecx, r12d
0x180023e01  mov     [rbp+40h+var_98], cl
0x180023e04  mov     rbx, [rdi+40h]
0x180023e08  mov     rbx, [rbx]
0x180023e0b  cmp     rbx, [rdi+40h]
0x180023e0f  jz      loc_180024182
0x180023e15  lea     r15, [rbx+20h]
0x180023e19  mov     rcx, [r15]
0x180023e1c  cmp     [rcx-10h], r12d
0x180023e20  jle     short loc_180023E4B
0x180023e22  mov     edx, 5Ch ; '\'; Ch
0x180023e27  add     rcx, 2; Str
0x180023e2b  call    cs:__imp_wcschr
0x180023e31  test    rax, rax
0x180023e34  jnz     short loc_180023E3A
0x180023e36  mov     eax, esi
0x180023e38  jmp     short loc_180023E40
0x180023e3a  sub     rax, [r15]
0x180023e3d  sar     rax, 1
  ... truncated ...
```
