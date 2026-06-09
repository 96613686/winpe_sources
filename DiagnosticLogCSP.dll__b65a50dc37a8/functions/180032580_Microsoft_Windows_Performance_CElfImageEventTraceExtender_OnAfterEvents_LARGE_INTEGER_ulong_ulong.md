# Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180032580`
- end: `0x180032d74`
- name: `?OnAfterEvents@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `2036`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b90`
- `0x180001bb4`
- `0x180001bf8`
- `0x18000265c`
- `0x18001138c`
- `0x180011618`
- `0x180011648`
- `0x18001a030`
- `0x18001ebc0`
- `0x18001ec68`
- `0x1800232f0`
- `0x180031568`
- `0x1800316f4`
- `0x180031910`
- `0x180031a88`
- `0x180031c1c`
- `0x180031cac`
- `0x180031dc8`
- `0x180032580`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800328d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180032941`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800328d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180032941`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800329b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800329f2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800329b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800329f2`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800326b0`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800326b0`
- `bcrypt!BCryptGetProperty` at `0x18003289c`
- `bcrypt!BCryptGetProperty` at `0x180032911`
- `bcrypt!BCryptGetProperty` at `0x18003289c`
- `bcrypt!BCryptGetProperty` at `0x180032911`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003285c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003285c`
- `bcrypt!BCryptCreateHash` at `0x180032974`
- `bcrypt!BCryptCreateHash` at `0x180032974`

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
  char *inserted; // rdi
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
  unsigned int v68; // [rsp+6Ch] [rbp-5Dh]
  LPWSTR lpTargetPath[2]; // [rsp+70h] [rbp-59h] BYREF
  WCHAR *v70; // [rsp+80h] [rbp-49h]
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+90h] [rbp-39h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+A0h] [rbp-29h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+A8h] [rbp-21h]
  UCHAR v74[4]; // [rsp+B8h] [rbp-11h] BYREF
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v75; // [rsp+C0h] [rbp-9h]
  WCHAR DeviceName[4]; // [rsp+C8h] [rbp-1h] BYREF

  v68 = a4;
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
  v70 = 0;
  v9 = operator new(0x2027u);
  if ( !v9 )
    __fastfail(5u);
  v10 = (WCHAR *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v10 - 1) = v9;
  lpTargetPath[0] = v10;
  v11 = v10 + 4096;
  v70 = v10 + 4096;
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
      inserted = (char *)phHash;
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
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(pbOutput);
        inserted = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                             &v63,
                             phAlgorithm,
                             v23);
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
          if ( BCryptGetProperty(phAlgorithm[1], L"HashDigestLength", v74, 4u, pcbResult, 0) >= 0 && pcbResult[0] == 4 )
          {
            v27 = *(unsigned int *)v74;
            if ( *(_DWORD *)v74 )
            {
              if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)v74) )
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
          if ( !*((_BYTE *)v70 + 25) )
          {
            v42 = *((_QWORD *)v70 + 4);
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
            if ( v46 >= 0 && v70 != v63 )
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
              v53 = v70;
              v54 = *(_QWORD *)(*((_QWORD *)v70 + 5) - 24LL);
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
    Microsoft::Windows::Performance::CryptographicHasher::~CryptographicHasher((Microsoft::Windows::Performance::CryptographicHasher *)phAlgorithm);
    v4 = v67;
  }
  v60 = *((_QWORD *)v6 + 1);
  if ( v60 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v60 + 96LL))(
           v60,
           a2,
           v4,
           v68);
    if ( v8 == -2147467263 )
      v8 = 0;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
    &v63,
    &v63,
    *((_QWORD *)v63 + 1));
  operator delete(v63, 0x30u);
  return v8;
}

```

## disassembly

```asm
0x180032580  push    rbp
0x180032582  push    rbx
0x180032583  push    rsi
0x180032584  push    rdi
0x180032585  push    r12
0x180032587  push    r13
0x180032589  push    r14
0x18003258b  push    r15
0x18003258d  lea     rbp, [rsp-1Fh]
0x180032592  sub     rsp, 0E8h
0x180032599  mov     rax, cs:__security_cookie
0x1800325a0  xor     rax, rsp
0x1800325a3  mov     [rbp+57h+var_50], rax
0x1800325a7  mov     [rbp+57h+var_B4], r9d
0x1800325ab  mov     r12d, r8d
0x1800325ae  mov     [rbp+57h+var_B8], r8d
0x1800325b2  mov     r14, rdx
0x1800325b5  mov     r13, rcx
0x1800325b8  mov     [rbp+57h+var_60], rcx
0x1800325bc  xor     esi, esi
0x1800325be  mov     [rsp+120h+var_D8], rsi
0x1800325c3  mov     [rbp+57h+var_D0], rsi
0x1800325c7  lea     ecx, [rsi+30h]; Size
0x1800325ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800325cf  mov     [rax], rax
0x1800325d2  mov     [rax+8], rax
0x1800325d6  mov     [rax+10h], rax
0x1800325da  lea     r15d, [rsi+1]
0x1800325de  mov     word ptr [rax+18h], 101h
0x1800325e4  mov     [rsp+120h+var_D8], rax
0x1800325e9  lea     eax, [rsi+5Fh]
0x1800325ec  mov     [rbp+57h+DeviceName], ax
0x1800325f0  mov     dword ptr [rbp+57h+DeviceName+2], 3Ah ; ':'
0x1800325f7  mov     edi, esi
0x1800325f9  mov     word ptr [rbp+57h+pbOutput], di
0x1800325fd  xorps   xmm0, xmm0
0x180032600  movdqu  xmmword ptr [rbp+57h+lpTargetPath], xmm0
0x180032605  mov     [rbp+57h+var_A0], rsi
0x180032609  mov     ecx, 2027h; Size
0x18003260e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032613  test    rax, rax
0x180032616  jnz     short loc_18003261D
0x180032618  lea     ecx, [rsi+5]
0x18003261b  int     29h; Win8: RtlFailFast(ecx)
0x18003261d  lea     rcx, [rax+27h]
0x180032621  and     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x180032625  mov     [rcx-8], rax
0x180032629  mov     [rbp+57h+lpTargetPath], rcx
0x18003262d  lea     rbx, [rcx+2000h]
0x180032634  mov     [rbp+57h+var_A0], rbx
0x180032638  mov     word ptr [rsp+120h+var_E0], si
0x18003263d  mov     al, [rbp+57h+pbOutput+1]
0x180032640  cmp     al, byte ptr [rsp+120h+var_E0+1]
0x180032644  jnz     short loc_18003264A
0x180032646  mov     eax, esi
0x180032648  jmp     short loc_18003264F
0x18003264a  sbb     eax, eax
0x18003264c  or      eax, r15d
0x18003264f  test    eax, eax
0x180032651  jnz     short loc_180032662
0x180032653  xor     edx, edx; Val
0x180032655  mov     r8d, 2000h; Size
0x18003265b  call    memset_0
0x180032660  jmp     short loc_18003267E
0x180032662  mov     edx, 1000h
0x180032667  mov     rbx, rcx
0x18003266a  movzx   eax, si
0x18003266d  mov     rdi, rcx
0x180032670  mov     ecx, edx
0x180032672  rep stosw
0x180032675  add     rbx, 2
0x180032679  sub     rdx, r15
0x18003267c  jnz     short loc_180032675
0x18003267e  mov     [rbp+57h+lpTargetPath+8], rbx
0x180032682  mov     qword ptr [rsp+120h+var_E0], rsi
0x180032687  lea     rcx, [rsp+120h+var_E0]
0x18003268c  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x180032691  mov     eax, 41h ; 'A'
0x180032696  mov     [rbp+57h+DeviceName], ax
0x18003269a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003269e  mov     rdx, [rbp+57h+lpTargetPath]; lpTargetPath
0x1800326a2  mov     r8, [rbp+57h+lpTargetPath+8]
0x1800326a6  sub     r8, rdx
0x1800326a9  sar     r8, 1; ucchMax
0x1800326ac  lea     rcx, [rbp+57h+DeviceName]; lpDeviceName
0x1800326b0  call    cs:__imp_QueryDosDeviceW
0x1800326b7  nop     dword ptr [rax+rax+00h]
0x1800326bc  cmp     eax, r15d
0x1800326bf  jbe     loc_180032810
0x1800326c5  lea     r8d, [rax-2]
0x1800326c9  mov     rdx, [rbp+57h+lpTargetPath]
0x1800326cd  lea     rcx, [rsp+120h+var_E0]
0x1800326d2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x1800326d7  lea     r8, [rsp+120h+var_E0]
0x1800326dc  lea     rdx, [rbp+57h+phAlgorithm]
0x1800326e0  lea     rcx, [rsp+120h+var_D8]
0x1800326e5  call    ??$_Find_lower_bound@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::_Find_lower_bound<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800326ea  mov     rdi, [rbp+57h+phHash]
0x1800326ee  cmp     [rdi+19h], sil
0x1800326f2  jnz     short loc_18003272F
0x1800326f4  mov     rcx, [rdi+20h]
0x1800326f8  test    rcx, rcx
0x1800326fb  jz      loc_180032D58
0x180032701  mov     rax, qword ptr [rsp+120h+var_E0]
0x180032706  sub     rcx, rax
0x180032709  movzx   edx, word ptr [rax]
0x18003270c  cmp     dx, [rax+rcx]
0x180032710  jnz     short loc_18003271F
0x180032712  add     rax, 2
0x180032716  test    dx, dx
0x180032719  jnz     short loc_180032709
0x18003271b  mov     eax, esi
0x18003271d  jmp     short loc_180032724
0x18003271f  sbb     eax, eax
0x180032721  or      eax, r15d
0x180032724  shr     eax, 1Fh
0x180032727  test    al, al
0x180032729  jz      loc_1800327CD
0x18003272f  mov     rax, 555555555555555h
0x180032739  cmp     [rbp+57h+var_D0], rax
0x18003273d  jz      loc_180032D63
0x180032743  mov     rbx, [rsp+120h+var_D8]
0x180032748  lea     rax, [rsp+120h+var_D8]
0x18003274d  mov     qword ptr [rbp+57h+pbOutput], rax
0x180032751  mov     ecx, 30h ; '0'; Size
0x180032756  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003275b  mov     rsi, rax
0x18003275e  lea     rdx, [rsp+120h+var_E0]
0x180032763  lea     rcx, [rax+20h]
0x180032767  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003276c  nop
0x18003276d  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180032774  mov     rax, [rcx+18h]
0x180032778  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032784  add     rax, 18h
0x180032788  mov     [rsi+28h], rax
0x18003278c  mov     [rsi], rbx
0x18003278f  mov     [rsi+8], rbx
0x180032793  mov     [rsi+10h], rbx
0x180032797  xor     eax, eax
0x180032799  mov     [rsi+18h], ax
0x18003279d  mov     [rbp+57h+var_C0], rax
0x1800327a1  lea     rcx, [rbp+57h+pbOutput]
0x1800327a5  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)
0x1800327aa  movups  xmm0, xmmword ptr [rbp+57h+phAlgorithm]
0x1800327ae  movdqu  xmmword ptr [rbp+57h+phAlgorithm], xmm0
0x1800327b3  mov     r8, rsi
0x1800327b6  lea     rdx, [rbp+57h+phAlgorithm]
0x1800327ba  lea     rcx, [rsp+120h+var_D8]
0x1800327bf  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x1800327c4  mov     rdi, rax
0x1800327c7  xor     esi, esi
0x1800327c9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800327cd  lea     rcx, [rdi+28h]
0x1800327d1  lea     rax, [rbp+57h+DeviceName]
0x1800327d5  mov     r8, rbx
0x1800327d8  inc     r8
0x1800327db  cmp     [rax+r8*2], si
0x1800327e0  jnz     short loc_1800327D8
0x1800327e2  lea     rdx, [rbp+57h+DeviceName]
0x1800327e6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800327eb  mov     rdx, qword ptr [rsp+120h+var_E0]
0x1800327f0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800327f4  mov     eax, ebx
0x1800327f6  lock xadd [rdx+10h], eax
0x1800327fb  add     eax, ebx
0x1800327fd  test    eax, eax
0x1800327ff  jg      short loc_180032810
0x180032801  mov     rcx, [rdx]
0x180032804  mov     rax, [rcx]
0x180032807  mov     rax, [rax+8]
0x18003280b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032810  movzx   eax, [rbp+57h+DeviceName]
0x180032814  add     ax, r15w
0x180032818  mov     [rbp+57h+DeviceName], ax
0x18003281c  cmp     ax, 5Bh ; '['
0x180032820  jnz     loc_18003269E
0x180032826  lea     rcx, [rbp+57h+lpTargetPath]
0x18003282a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003282f  cmp     [r13+48h], rsi
0x180032833  jz      loc_180032CD6
0x180032839  mov     byte ptr [rbp+57h+phAlgorithm], sil
0x18003283d  xorps   xmm0, xmm0
0x180032840  movdqu  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x180032845  mov     r12d, 20h ; ' '
0x18003284b  mov     r9d, r12d; dwFlags
0x18003284e  xor     r8d, r8d; pszImplementation
0x180032851  lea     rdx, pszAlgId; "SHA256"
0x180032858  lea     rcx, [rbp+57h+phAlgorithm+8]; phAlgorithm
0x18003285c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180032863  nop     dword ptr [rax+rax+00h]
0x180032868  test    eax, eax
0x18003286a  js      loc_18003298D
0x180032870  mov     dword ptr [rbp+57h+pbOutput], esi
0x180032873  mov     [rsp+120h+var_E0], esi
0x180032877  mov     [rsp+120h+dwFlags], esi; dwFlags
0x18003287b  lea     rax, [rsp+120h+var_E0]
0x180032880  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180032885  lea     edi, [r12-1Ch]
0x18003288a  mov     r9d, edi; cbOutput
0x18003288d  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180032891  lea     rdx, pszProperty; "ObjectLength"
0x180032898  mov     rcx, [rbp+57h+phAlgorithm+8]; hObject
0x18003289c  call    cs:__imp_BCryptGetProperty
0x1800328a3  nop     dword ptr [rax+rax+00h]
0x1800328a8  test    eax, eax
0x1800328aa  js      loc_18003298D
0x1800328b0  cmp     [rsp+120h+var_E0], edi
0x1800328b4  jnz     loc_18003298D
0x1800328ba  mov     ecx, dword ptr [rbp+57h+pbOutput]; Size
0x1800328bd  test    rcx, rcx
0x1800328c0  jnz     short loc_1800328C7
0x1800328c2  mov     rcx, rsi
0x1800328c5  jmp     short loc_1800328D8
0x1800328c7  xor     edx, edx
0x1800328c9  mov     rax, rbx
0x1800328cc  div     rcx
0x1800328cf  cmp     rax, r15
0x1800328d2  jb      loc_18003298D
0x1800328d8  call    cs:__imp_malloc
0x1800328df  nop     dword ptr [rax+rax+00h]
0x1800328e4  mov     [rbp+57h+pbHashObject], rax
0x1800328e8  test    rax, rax
0x1800328eb  jz      loc_18003298D
0x1800328f1  mov     [rsp+120h+dwFlags], esi; dwFlags
0x1800328f5  lea     rax, [rsp+120h+var_E0]
0x1800328fa  mov     [rsp+120h+pcbResult], rax; pcbResult
0x1800328ff  mov     r9d, edi; cbOutput
0x180032902  lea     r8, [rbp+57h+var_68]; pbOutput
0x180032906  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003290d  mov     rcx, [rbp+57h+phAlgorithm+8]; hObject
0x180032911  call    cs:__imp_BCryptGetProperty
0x180032918  nop     dword ptr [rax+rax+00h]
0x18003291d  test    eax, eax
0x18003291f  js      short loc_18003298D
0x180032921  cmp     [rsp+120h+var_E0], edi
0x180032925  jnz     short loc_18003298D
0x180032927  mov     ecx, dword ptr [rbp+57h+var_68]; Size
0x18003292a  test    rcx, rcx
0x18003292d  jnz     short loc_180032934
0x18003292f  mov     rcx, rsi
0x180032932  jmp     short loc_180032941
0x180032934  xor     edx, edx
0x180032936  mov     rax, rbx
0x180032939  div     rcx
0x18003293c  cmp     rax, r15
0x18003293f  jb      short loc_18003298D
0x180032941  call    cs:__imp_malloc
0x180032948  nop     dword ptr [rax+rax+00h]
0x18003294d  mov     [rbp+57h+pbHashObject+8], rax
0x180032951  test    rax, rax
0x180032954  jz      short loc_18003298D
0x180032956  mov     [rsp+120h+var_F0], r12d; dwFlags
0x18003295b  mov     [rsp+120h+dwFlags], esi; cbSecret
0x18003295f  mov     [rsp+120h+pcbResult], rsi; pbSecret
0x180032964  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x180032968  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x18003296c  lea     rdx, [rbp+57h+phHash]; phHash
0x180032970  mov     rcx, [rbp+57h+phAlgorithm+8]; hAlgorithm
0x180032974  call    cs:__imp_BCryptCreateHash
0x18003297b  nop     dword ptr [rax+rax+00h]
0x180032980  movzx   ecx, byte ptr [rbp+57h+phAlgorithm]
0x180032984  test    eax, eax
0x180032986  cmovns  ecx, r15d
0x18003298a  mov     byte ptr [rbp+57h+phAlgorithm], cl
0x18003298d  mov     rbx, [r13+40h]
0x180032991  mov     rbx, [rbx]
0x180032994  cmp     rbx, [r13+40h]
0x180032998  jz      loc_180032CC9
0x18003299e  lea     r12, [rbx+20h]
0x1800329a2  mov     rcx, [r12]
0x1800329a6  cmp     [rcx-10h], r15d
0x1800329aa  jle     short loc_1800329D2
0x1800329ac  mov     edx, 5Ch ; '\'; Ch
0x1800329b1  add     rcx, 2; Str
0x1800329b5  call    cs:__imp_wcschr
0x1800329bc  nop     dword ptr [rax+rax+00h]
0x1800329c1  mov     rcx, [r12]
0x1800329c5  test    rax, rax
0x1800329c8  jz      short loc_1800329D2
0x1800329ca  sub     rax, rcx
0x1800329cd  sar     rax, 1
0x1800329d0  jmp     short loc_1800329D5
0x1800329d2  or      eax, 0FFFFFFFFh
0x1800329d5  add     eax, 1
0x1800329d8  js      loc_180032C7A
0x1800329de  cmp     eax, [rcx-10h]
0x1800329e1  jge     loc_180032C7A
0x1800329e7  mov     edx, 5Ch ; '\'; Ch
0x1800329ec  cdqe
0x1800329ee  lea     rcx, [rcx+rax*2]; Str
0x1800329f2  call    cs:__imp_wcschr
0x1800329f9  nop     dword ptr [rax+rax+00h]
0x1800329fe  mov     rdi, rax
0x180032a01  test    rax, rax
0x180032a04  jnz     short loc_180032A0B
0x180032a06  or      edi, 0FFFFFFFFh
0x180032a09  jmp     short loc_180032A12
0x180032a0b  sub     rdi, [r12]
  ... truncated ...
```
