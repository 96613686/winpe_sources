# CTreeWalker::ProcessFileAllocation(_FILE_LAYOUT_NAME_ENTRY *,unsigned __int64,unsigned __int64,unsigned __int64,ulong,ulong,_STORAGE_RESERVE_ID)

- ea: `0x180047e08`
- end: `0x180048702`
- name: `?ProcessFileAllocation@CTreeWalker@@QEAAJPEAU_FILE_LAYOUT_NAME_ENTRY@@_K11KKW4_STORAGE_RESERVE_ID@@@Z`
- size: `2298`
- prototype: `__int64 __usercall@<rax>(CTreeWalker *__hidden this@<rcx>, struct _FILE_LAYOUT_NAME_ENTRY *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned __int64, unsigned int, unsigned int, enum _STORAGE_RESERVE_ID)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040684`
- `0x18004bb10`

## callees

- `0x18000d030`
- `0x18000dd98`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x18003487c`
- `0x180039fa0`
- `0x18003dc28`
- `0x18003dd14`
- `0x18003df68`
- `0x18003df84`
- `0x18003fb50`
- `0x18003fba8`
- `0x18003fbc8`
- `0x180040658`
- `0x180041414`
- `0x180041450`
- `0x180042084`
- `0x18004264c`
- `0x1800437c8`
- `0x180047e08`
- `0x180049280`
- `0x1800497e0`
- `0x18004b074`
- `0x18004b6e8`
- `0x18004b74c`
- `0x18007d4e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800481a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800481a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800483a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800486c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800483a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800486c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004818d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004818d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CTreeWalker::ProcessFileAllocation(
        CTreeWalker *this,
        struct _FILE_LAYOUT_NAME_ENTRY *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        char a6,
        unsigned int a7,
        enum _STORAGE_RESERVE_ID a8)
{
  __int64 v10; // rdi
  unsigned int v11; // esi
  unsigned __int64 v12; // rdx
  __int64 v13; // r11
  int v14; // r15d
  __int64 v15; // rcx
  __int64 *v16; // r10
  unsigned int v17; // r11d
  __int64 v18; // rbx
  unsigned int v19; // r15d
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r13
  struct _FILE_LAYOUT_NAME_ENTRY *v22; // r12
  size_t v23; // r8
  size_t v24; // r8
  int *v25; // r8
  __int64 v26; // rbx
  WCHAR *p_pszPath; // r15
  LPWSTR ExtensionW; // rax
  char v29; // dl
  __int16 v30; // r8
  int v31; // r9d
  const wchar_t *v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rdx
  int v35; // r15d
  int v36; // r12d
  __int64 v37; // rax
  __int64 v39; // rdx
  unsigned __int64 v40; // rbx
  FOLDER_USAGE *v41; // rax
  int v42; // eax
  __int64 v43; // rdx
  int v44; // r8d
  __int64 v45; // rdx
  struct _FILE_LAYOUT_NAME_ENTRY *v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 *v49; // r8
  __int64 v50; // rax
  wchar_t v51; // [rsp+20h] [rbp-448h]
  long double v52; // [rsp+28h] [rbp-440h]
  int v53; // [rsp+54h] [rbp-414h] BYREF
  __int64 v54; // [rsp+58h] [rbp-410h] BYREF
  int v55; // [rsp+60h] [rbp-408h] BYREF
  struct _FILE_LAYOUT_NAME_ENTRY *i; // [rsp+68h] [rbp-400h] BYREF
  int v57; // [rsp+70h] [rbp-3F8h] BYREF
  int v58; // [rsp+74h] [rbp-3F4h]
  __int64 v59; // [rsp+78h] [rbp-3F0h] BYREF
  char v60; // [rsp+80h] [rbp-3E8h]
  __int64 v61; // [rsp+88h] [rbp-3E0h]
  __int64 v62; // [rsp+90h] [rbp-3D8h] BYREF
  unsigned __int64 v63; // [rsp+98h] [rbp-3D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-3C8h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-3C0h]
  _BYTE v66[80]; // [rsp+B0h] [rbp-3B8h] BYREF
  __int64 v67; // [rsp+100h] [rbp-368h] BYREF
  char v68[72]; // [rsp+108h] [rbp-360h] BYREF
  __int64 v69; // [rsp+150h] [rbp-318h] BYREF
  char v70[72]; // [rsp+158h] [rbp-310h] BYREF
  __int128 v71; // [rsp+1A0h] [rbp-2C8h] BYREF
  __int64 v72; // [rsp+1B0h] [rbp-2B8h]
  __int64 v73; // [rsp+1B8h] [rbp-2B0h]
  _DWORD v74[6]; // [rsp+1C0h] [rbp-2A8h] BYREF
  const wchar_t *v75; // [rsp+1D8h] [rbp-290h]
  __int64 v76; // [rsp+1E0h] [rbp-288h]
  int v77; // [rsp+1E8h] [rbp-280h] BYREF
  const wchar_t *v78; // [rsp+200h] [rbp-268h]
  __int64 v79; // [rsp+208h] [rbp-260h]
  WCHAR pszPath; // [rsp+210h] [rbp-258h] BYREF

  v62 = a3;
  i = a2;
  v63 = 0;
  v10 = 0;
  v65 = 0;
  v54 = 0;
  v11 = a7;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive((char *)this + 288, &SRWLock);
  v13 = -2;
  if ( a7 == -1 )
    v13 = a4;
  v54 = v13;
  v55 = 0;
  v57 = 0;
  v58 = 0;
  if ( (a6 & 0x10) != 0 )
  {
    v14 = 1;
    v53 = 1;
  }
  else
  {
    v14 = 0;
    v53 = 0;
    if ( (unsigned int)(a8 - 1) <= 2 )
    {
      std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Find_lower_bound<int>(
        (char *)this + 248,
        &v59,
        &a8);
      v18 = v61;
      if ( *(_BYTE *)(v61 + 25) || (signed int)v17 < *(_DWORD *)(v61 + 32) )
        v18 = *v16;
      v59 = v18;
      v59 = *v16;
      if ( v18 != v59 )
      {
        v19 = CTreeWalker::DataTypeNodeFromReserveID(v15, v17);
        LODWORD(v63) = v19;
        std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(
          this,
          &v59,
          &v63);
        v12 = *((_QWORD *)this + 1);
        v63 = v12;
        if ( v59 != v12 )
        {
          v20 = *(_QWORD *)(v18 + 40);
          v12 = *(_QWORD *)(v59 + 48);
          v21 = a5;
          if ( v12 + a5 > v20 )
          {
            if ( v12 < v20 )
            {
              v12 -= v20;
              v21 = v12 + a5;
              *(_QWORD *)(v59 + 48) = v20;
            }
          }
          else
          {
            v11 = v19;
          }
          v14 = v53;
          LODWORD(v13) = v54;
          goto LABEL_19;
        }
        v14 = v53;
      }
    }
    LODWORD(v13) = v54;
  }
  v21 = a5;
LABEL_19:
  if ( v11 != -1 )
    goto LABEL_31;
  if ( (v62 & 0xFFFFFFuLL) <= 0xF )
    goto LABEL_24;
  if ( (v13 & 0xFFFFFF) != 5 || (a6 & 6) != 6 )
  {
LABEL_31:
    v22 = i;
    goto LABEL_32;
  }
  if ( v14 )
    goto LABEL_57;
LABEL_24:
  v11 = 1;
  v22 = i;
  if ( *((_DWORD *)i + 4) == 24 )
  {
    if ( !wmemcmp((const wchar_t *)i + 12, L"pagefile.sys", 0xCu)
      || !wmemcmp((const wchar_t *)i + 12, L"swapfile.sys", v23) )
    {
      v11 = 24;
      v77 = 24;
      v78 = L"System Pagefile";
      v79 = 0;
      v25 = &v77;
      goto LABEL_29;
    }
    if ( !wmemcmp((const wchar_t *)i + 12, L"hiberfil.sys", v24) )
    {
      v11 = 25;
      v74[0] = 25;
      v75 = L"System Hiberfile";
      v76 = 0;
      v25 = v74;
LABEL_29:
      std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::insert(
        this,
        &v59,
        v25);
    }
  }
LABEL_32:
  if ( !v14 && v11 == -1 )
  {
    if ( !*((_BYTE *)this + 313) )
    {
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
        v12);
    }
    v26 = *((_DWORD *)v22 + 4) >> 1;
    v71 = 0;
    v72 = 0;
    v73 = 7;
    LOWORD(v71) = 0;
    if ( (unsigned int)v26 >= 0x104 )
    {
      std::wstring::resize(&v71, (unsigned int)(v26 + 1));
      p_pszPath = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v71);
      if ( !p_pszPath )
      {
LABEL_56:
        std::wstring::_Tidy_deallocate(&v71);
        goto LABEL_57;
      }
    }
    else
    {
      p_pszPath = &pszPath;
    }
    memcpy_0(p_pszPath, (char *)v22 + 24, *((unsigned int *)v22 + 4));
    p_pszPath[v26] = 0;
    ExtensionW = PathFindExtensionW(p_pszPath);
    v32 = ExtensionW;
    if ( ExtensionW )
    {
      o((wchar_t)ExtensionW, v29, v30, v31, v51, v52);
      v33 = std::wstring::wstring((__int64)v74, (__int64)v32);
      std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(
        (char *)this + 184,
        &v59,
        v33);
      std::wstring::_Tidy_deallocate(v74);
      i = (struct _FILE_LAYOUT_NAME_ENTRY *)*((_QWORD *)this + 24);
      if ( (struct _FILE_LAYOUT_NAME_ENTRY *)v59 == i )
      {
        v35 = v57;
      }
      else
      {
        v35 = *(_DWORD *)(v59 + 48);
        v57 = v35;
      }
      LOBYTE(v34) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
        v34);
      switch ( v35 )
      {
        case 3:
          v55 = 2;
          if ( v21 > 0x19000 && (!wcscmp_0(v32, L".jpg") || !wcscmp_0(v32, L".jpeg")) )
            v55 = 1;
          break;
        case 4:
          if ( v21 > 0x100000 )
            v55 = 4;
          break;
        case 2:
          if ( v21 > 0x32000 )
            v55 = 3;
          break;
        case 9:
          v55 = 5;
          break;
      }
    }
    goto LABEL_56;
  }
LABEL_57:
  *((_QWORD *)this + 22) += v21;
  v36 = v53;
  if ( v53 )
  {
    FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v66, v54, v11, v21);
    v67 = v62;
    FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v68, (const struct FOLDER_USAGE *)v66);
    std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::insert(
      (char *)this + 64,
      &v59,
      &v67);
    std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(&v67);
    v10 = v59;
    v65 = v59;
    if ( !v60 )
    {
      v37 = *(_QWORD *)(v59 + 24);
      if ( v37 == -1 )
      {
        v37 = v54;
        *(_QWORD *)(v59 + 24) = v54;
      }
      if ( v37 == -2 )
      {
        if ( a7 == -1 )
          v11 = *(_DWORD *)(v10 + 40);
        *(_DWORD *)(v10 + 40) = v11;
        if ( v11 == -1 )
        {
          v11 = 1;
        }
        else if ( a7 == -1 )
        {
          v58 = 1;
        }
      }
      else if ( v11 == -1 )
      {
        v11 = *(_DWORD *)(v10 + 40);
      }
    }
    FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v66);
    goto LABEL_78;
  }
  if ( v21 )
  {
    if ( v11 == -1 && v62 == *((_QWORD *)this + 40) )
      v11 = 10;
LABEL_78:
    v59 = v54;
    v40 = *(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::find(
                       (char *)this + 64,
                       &i,
                       &v59);
    v63 = v40;
    v59 = *((_QWORD *)this + 9);
    if ( v40 == v59 )
    {
      v41 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v66, -1, 0xFFFFFFFF, 0);
      v69 = v54;
      FOLDER_USAGE::FOLDER_USAGE(v70, v41);
      v40 = *(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::insert(
                         (char *)this + 64,
                         &v59,
                         &v69);
      v63 = v40;
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(&v69);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v66);
    }
    if ( v11 == -1 )
    {
      if ( v36 )
      {
        if ( *(_DWORD *)(v10 + 40) == -1 )
        {
          v42 = *(_DWORD *)(v40 + 40);
          if ( v42 != -1 )
            *(_DWORD *)(v10 + 40) = v42;
        }
      }
      v11 = *(_DWORD *)(v40 + 40);
      if ( v11 == -1 )
      {
        if ( *(_QWORD *)(v40 + 24) == -1 )
        {
LABEL_94:
          if ( v36 )
          {
            v44 = v10 + 80;
            LOBYTE(v44) = 1;
            CTreeWalker::UpdateParentAllocationSize(
              (_DWORD)this,
              v54,
              v44,
              v11,
              *(_QWORD *)(v10 + 32),
              0,
              v10 + 80,
              0,
              v10 + 48);
            if ( !*((_BYTE *)this + 313) )
            {
              LOBYTE(v45) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
                v45);
            }
            i = (struct _FILE_LAYOUT_NAME_ENTRY *)v62;
            std::list<__int64>::_Emplace<__int64>(v40 + 64, *(_QWORD *)(v40 + 64), &i);
          }
          else
          {
            CTreeWalker::UpdateParentAllocationSize((_DWORD)this, v54, 0, v11, v21, (__int64)&v57, 0, (__int64)&v55, 0);
          }
LABEL_99:
          if ( v11 == -1 || v58 )
          {
LABEL_122:
            if ( SRWLock )
            {
              ReleaseSRWLockExclusive(SRWLock);
              SRWLock = 0;
            }
            return 0;
          }
          if ( v36 )
          {
            if ( !*((_BYTE *)this + 313) )
              goto LABEL_117;
            if ( !v11 )
            {
              v46 = **(struct _FILE_LAYOUT_NAME_ENTRY ***)(v10 + 80);
              for ( i = v46; ; i = (struct _FILE_LAYOUT_NAME_ENTRY *)v48 )
              {
                v59 = *(_QWORD *)(v10 + 80);
                if ( v46 == (struct _FILE_LAYOUT_NAME_ENTRY *)v59 )
                  break;
                v47 = *(_QWORD *)std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(
                                   this,
                                   &v62,
                                   (char *)v46 + 32);
                v54 = v47;
                v59 = *((_QWORD *)this + 1);
                if ( v47 != v59 )
                  *(_QWORD *)(v47 + 48) += *((_QWORD *)v46 + 5);
                if ( *(_BYTE *)(*((_QWORD *)v46 + 2) + 25LL) )
                {
                  while ( 1 )
                  {
                    v48 = *((_QWORD *)v46 + 1);
                    if ( *(_BYTE *)(v48 + 25) || v46 != *(struct _FILE_LAYOUT_NAME_ENTRY **)(v48 + 16) )
                      break;
                    v46 = (struct _FILE_LAYOUT_NAME_ENTRY *)*((_QWORD *)v46 + 1);
                    i = (struct _FILE_LAYOUT_NAME_ENTRY *)v48;
                  }
                }
                else
                {
                  v48 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>::_Min();
                }
                v46 = (struct _FILE_LAYOUT_NAME_ENTRY *)v48;
              }
              goto LABEL_122;
            }
          }
          if ( *((_BYTE *)this + 313) && !v11 )
          {
            v53 = v57;
            v49 = (__int64 *)&v53;
            goto LABEL_118;
          }
LABEL_117:
          LODWORD(v54) = v11;
          v49 = &v54;
LABEL_118:
          v50 = *(_QWORD *)std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(
                             this,
                             &v59,
                             v49);
          v54 = v50;
          v59 = *((_QWORD *)this + 1);
          if ( v50 != v59 )
          {
            if ( v36 )
              *(_QWORD *)(v50 + 48) += *(_QWORD *)(v10 + 32);
            else
              *(_QWORD *)(v50 + 48) += v21;
          }
          goto LABEL_122;
        }
        v43 = v54;
        if ( v36 )
          v43 = v62;
        CTreeWalker::ResolveTopMostParentId(this, v43);
        v11 = *(_DWORD *)(v40 + 40);
      }
    }
    if ( v11 - 1 <= 0xFFFFFFFD && !*((_BYTE *)this + 316) )
    {
      LOBYTE(v39) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
        v39);
      if ( v11 != 28 && v11 != 9 )
        goto LABEL_99;
    }
    goto LABEL_94;
  }
  if ( SRWLock )
  {
    ReleaseSRWLockExclusive(SRWLock);
    SRWLock = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180047e08  push    rbx
0x180047e0a  push    rsi
0x180047e0b  push    rdi
0x180047e0c  push    r12
0x180047e0e  push    r13
0x180047e10  push    r14
0x180047e12  push    r15
0x180047e14  sub     rsp, 430h
0x180047e1b  mov     rax, cs:__security_cookie
0x180047e22  xor     rax, rsp
0x180047e25  mov     [rsp+468h+var_48], rax
0x180047e2d  mov     rbx, r9
0x180047e30  mov     [rsp+468h+var_3D8], r8
0x180047e38  mov     [rsp+468h+var_400], rdx
0x180047e3d  mov     r14, rcx
0x180047e40  xor     r13d, r13d
0x180047e43  mov     [rsp+468h+var_3D0], r13
0x180047e4b  mov     edi, r13d
0x180047e4e  mov     [rsp+468h+var_3C0], r13
0x180047e56  mov     [rsp+468h+var_410], r13
0x180047e5b  mov     esi, [rsp+468h+arg_30]
0x180047e62  mov     [rsp+468h+var_418], esi
0x180047e66  add     rcx, 120h
0x180047e6d  lea     rdx, [rsp+468h+SRWLock]
0x180047e75  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockExclusive@Details@234@XZ; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(void)
0x180047e7a  nop
0x180047e7b  lea     r11, [r13-2]
0x180047e7f  cmp     esi, 0FFFFFFFFh
0x180047e82  cmovz   r11, rbx
0x180047e86  mov     [rsp+468h+var_410], r11
0x180047e8b  mov     [rsp+468h+var_408], r13d
0x180047e90  mov     [rsp+468h+var_3F8], r13d
0x180047e95  mov     r12d, dword ptr [rsp+468h+arg_28]
0x180047e9d  mov     [rsp+468h+var_3F4], r13d
0x180047ea2  test    r12b, 10h
0x180047ea6  jz      short loc_180047EB6
0x180047ea8  lea     r15d, [r13+1]
0x180047eac  mov     [rsp+468h+var_414], r15d
0x180047eb1  jmp     loc_180047FA1
0x180047eb6  mov     r15d, r13d
0x180047eb9  mov     [rsp+468h+var_414], r13d
0x180047ebe  mov     r11d, [rsp+468h+arg_38]
0x180047ec6  lea     eax, [r11-1]
0x180047eca  cmp     eax, 2
0x180047ecd  ja      loc_180047F9C
0x180047ed3  lea     r10, [r14+0F8h]
0x180047eda  lea     r8, [rsp+468h+arg_38]
0x180047ee2  lea     rdx, [rsp+468h+var_3F0]
0x180047ee7  mov     rcx, r10
0x180047eea  call    ??$_Find_lower_bound@H@?$_Tree@V?$_Tmap_traits@HV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@1@AEBH@Z; std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Find_lower_bound<int>(int const &)
0x180047eef  mov     rbx, [rsp+468h+var_3E0]
0x180047ef7  cmp     [rbx+19h], r13b
0x180047efb  jnz     short loc_180047F03
0x180047efd  cmp     r11d, [rbx+20h]
0x180047f01  jge     short loc_180047F06
0x180047f03  mov     rbx, [r10]
0x180047f06  mov     [rsp+468h+var_3F0], rbx
0x180047f0b  mov     rax, [r10]
0x180047f0e  mov     [rsp+468h+var_3F0], rax
0x180047f13  cmp     rbx, rax
0x180047f16  jz      loc_180047F9C
0x180047f1c  mov     edx, r11d
0x180047f1f  call    ?DataTypeNodeFromReserveID@CTreeWalker@@AEAA?AW4_DATA_TYPE_NODE@@W4_STORAGE_RESERVE_ID@@@Z; CTreeWalker::DataTypeNodeFromReserveID(_STORAGE_RESERVE_ID)
0x180047f24  mov     r15d, eax
0x180047f27  mov     dword ptr [rsp+468h+var_3D0], eax
0x180047f2e  lea     r8, [rsp+468h+var_3D0]
0x180047f36  lea     rdx, [rsp+468h+var_3F0]
0x180047f3b  mov     rcx, r14
0x180047f3e  call    ?find@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@2@AEBH@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(int const &)
0x180047f43  mov     rdx, [r14+8]
0x180047f47  mov     [rsp+468h+var_3D0], rdx
0x180047f4f  mov     rcx, [rsp+468h+var_3F0]
0x180047f54  cmp     rcx, rdx
0x180047f57  jz      short loc_180047F97
0x180047f59  mov     r8, [rbx+28h]
0x180047f5d  mov     rdx, [rcx+30h]
0x180047f61  mov     r13, [rsp+468h+arg_20]
0x180047f69  lea     rax, [rdx+r13]
0x180047f6d  cmp     rax, r8
0x180047f70  ja      short loc_180047F86
0x180047f72  mov     esi, r15d
0x180047f75  mov     [rsp+468h+var_418], r15d
0x180047f7a  mov     r15d, [rsp+468h+var_414]
0x180047f7f  mov     r11, [rsp+468h+var_410]
0x180047f84  jmp     short loc_180047FA9
0x180047f86  cmp     rdx, r8
0x180047f89  jnb     short loc_180047F7A
0x180047f8b  sub     rdx, r8
0x180047f8e  add     r13, rdx
0x180047f91  mov     [rcx+30h], r8
0x180047f95  jmp     short loc_180047F7A
0x180047f97  mov     r15d, [rsp+468h+var_414]
0x180047f9c  mov     r11, [rsp+468h+var_410]
0x180047fa1  mov     r13, [rsp+468h+arg_20]
0x180047fa9  cmp     esi, 0FFFFFFFFh
0x180047fac  jnz     loc_1800480BC
0x180047fb2  mov     rax, [rsp+468h+var_3D8]
0x180047fba  mov     ecx, 0FFFFFFh
0x180047fbf  and     rax, rcx
0x180047fc2  cmp     rax, 0Fh
0x180047fc6  jbe     short loc_180047FEF
0x180047fc8  mov     rax, r11
0x180047fcb  and     rax, rcx
0x180047fce  cmp     rax, 5
0x180047fd2  jnz     loc_1800480BC
0x180047fd8  and     r12d, 6
0x180047fdc  cmp     r12b, 6
0x180047fe0  jnz     loc_1800480BC
0x180047fe6  test    r15d, r15d
0x180047fe9  jnz     loc_1800482A0
0x180047fef  mov     esi, 1
0x180047ff4  mov     [rsp+468h+var_418], esi
0x180047ff8  mov     r12, [rsp+468h+var_400]
0x180047ffd  cmp     dword ptr [r12+10h], 18h
0x180048003  jnz     loc_1800480C1
0x180048009  lea     rbx, [r12+18h]
0x18004800e  lea     r8d, [rsi+0Bh]; N
0x180048012  lea     rdx, aPagefileSys; "pagefile.sys"
0x180048019  mov     rcx, rbx; S1
0x18004801c  call    wmemcmp
0x180048021  test    eax, eax
0x180048023  jz      short loc_18004808B
0x180048025  lea     rdx, aSwapfileSys; "swapfile.sys"
0x18004802c  mov     rcx, rbx; S1
0x18004802f  call    wmemcmp
0x180048034  test    eax, eax
0x180048036  jz      short loc_18004808B
0x180048038  lea     rdx, aHiberfilSys; "hiberfil.sys"
0x18004803f  mov     rcx, rbx; S1
0x180048042  call    wmemcmp
0x180048047  test    eax, eax
0x180048049  jnz     short loc_1800480C1
0x18004804b  lea     esi, [rax+19h]
0x18004804e  mov     [rsp+468h+var_2A8], esi
0x180048055  lea     rax, aSystemHiberfil; "System Hiberfile"
0x18004805c  mov     [rsp+468h+var_290], rax
0x180048064  mov     [rsp+468h+var_288], 0
0x180048070  lea     r8, [rsp+468h+var_2A8]
0x180048078  lea     rdx, [rsp+468h+var_3F0]
0x18004807d  mov     rcx, r14
0x180048080  call    ?insert@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@2@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::insert(std::pair<int const,STORAGE_USAGE> &&)
0x180048085  mov     [rsp+468h+var_418], esi
0x180048089  jmp     short loc_1800480C1
0x18004808b  mov     esi, 18h
0x180048090  mov     [rsp+468h+var_280], esi
0x180048097  lea     rax, aSystemPagefile; "System Pagefile"
0x18004809e  mov     [rsp+468h+var_268], rax
0x1800480a6  mov     [rsp+468h+var_260], 0
0x1800480b2  lea     r8, [rsp+468h+var_280]
0x1800480ba  jmp     short loc_180048078
0x1800480bc  mov     r12, [rsp+468h+var_400]
0x1800480c1  test    r15d, r15d
0x1800480c4  jnz     loc_1800482A0
0x1800480ca  cmp     esi, 0FFFFFFFFh
0x1800480cd  jnz     loc_1800482A0
0x1800480d3  cmp     [r14+139h], r15b
0x1800480da  jnz     short loc_1800480EA
0x1800480dc  mov     dl, 1
0x1800480de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions> `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl(void)'::`2'::impl
0x1800480e5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800480ea  mov     ebx, [r12+10h]
0x1800480ef  shr     ebx, 1
0x1800480f1  xorps   xmm0, xmm0
0x1800480f4  movups  [rsp+468h+var_2C8], xmm0
0x1800480fc  mov     [rsp+468h+var_2B8], 0
0x180048108  mov     [rsp+468h+var_2B0], 0
0x180048114  mov     [rsp+468h+var_2B8], 0
0x180048120  mov     [rsp+468h+var_2B0], 7
0x18004812c  xor     eax, eax
0x18004812e  mov     word ptr [rsp+468h+var_2C8], ax
0x180048136  cmp     ebx, 104h
0x18004813c  jnb     short loc_180048148
0x18004813e  lea     r15, [rsp+468h+pszPath]
0x180048146  jmp     short loc_180048171
0x180048148  lea     edx, [rbx+1]
0x18004814b  lea     rcx, [rsp+468h+var_2C8]
0x180048153  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180048158  lea     rcx, [rsp+468h+var_2C8]
0x180048160  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048165  mov     r15, rax
0x180048168  test    rax, rax
0x18004816b  jz      loc_180048293
0x180048171  mov     r8d, [r12+10h]; Size
0x180048176  lea     rdx, [r12+18h]; Src
0x18004817b  mov     rcx, r15; void *
0x18004817e  call    memcpy_0
0x180048183  xor     eax, eax
0x180048185  mov     [r15+rbx*2], ax
0x18004818a  mov     rcx, r15; pszPath
0x18004818d  call    cs:__imp_PathFindExtensionW
0x180048193  mov     rbx, rax
0x180048196  test    rax, rax
0x180048199  jz      loc_180048293
0x18004819f  mov     rcx, rax
0x1800481a2  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800481a8  mov     rdx, rbx
0x1800481ab  lea     rcx, [rsp+468h+var_2A8]
0x1800481b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800481b8  nop
0x1800481b9  lea     rcx, [r14+0B8h]
0x1800481c0  mov     r8, rax
0x1800481c3  lea     rdx, [rsp+468h+var_3F0]
0x1800481c8  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(std::wstring const &)
0x1800481cd  nop
0x1800481ce  lea     rcx, [rsp+468h+var_2A8]
0x1800481d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800481db  mov     rcx, [r14+0C0h]
0x1800481e2  mov     [rsp+468h+var_400], rcx
0x1800481e7  mov     rax, [rsp+468h+var_3F0]
0x1800481ec  cmp     rax, rcx
0x1800481ef  jz      short loc_1800481FC
0x1800481f1  mov     r15d, [rax+30h]
0x1800481f5  mov     [rsp+468h+var_3F8], r15d
0x1800481fa  jmp     short loc_180048201
0x1800481fc  mov     r15d, [rsp+468h+var_3F8]
0x180048201  mov     dl, 1
0x180048203  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions> `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl(void)'::`2'::impl
0x18004820a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004820f  cmp     r15d, 3
0x180048213  jnz     short loc_180048256
0x180048215  mov     [rsp+468h+var_408], 2
0x18004821d  cmp     r13, 19000h
0x180048224  jbe     short loc_180048293
0x180048226  lea     rdx, aJpg; ".jpg"
0x18004822d  mov     rcx, rbx; String1
0x180048230  call    wcscmp_0
0x180048235  test    eax, eax
0x180048237  jz      short loc_18004824C
0x180048239  lea     rdx, aJpeg; ".jpeg"
0x180048240  mov     rcx, rbx; String1
0x180048243  call    wcscmp_0
0x180048248  test    eax, eax
0x18004824a  jnz     short loc_180048293
0x18004824c  mov     [rsp+468h+var_408], 1
0x180048254  jmp     short loc_180048293
0x180048256  cmp     r15d, 4
0x18004825a  jnz     short loc_18004826C
0x18004825c  cmp     r13, 100000h
0x180048263  jbe     short loc_180048293
0x180048265  mov     [rsp+468h+var_408], r15d
0x18004826a  jmp     short loc_180048293
0x18004826c  cmp     r15d, 2
0x180048270  jnz     short loc_180048285
0x180048272  cmp     r13, 32000h
0x180048279  jbe     short loc_180048293
0x18004827b  mov     [rsp+468h+var_408], 3
0x180048283  jmp     short loc_180048293
0x180048285  cmp     r15d, 9
0x180048289  jnz     short loc_180048293
0x18004828b  mov     [rsp+468h+var_408], 5
0x180048293  lea     rcx, [rsp+468h+var_2C8]
0x18004829b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800482a0  add     [r14+0B0h], r13
0x1800482a7  mov     r12d, [rsp+468h+var_414]
0x1800482ac  test    r12d, r12d
0x1800482af  jz      loc_180048397
0x1800482b5  mov     r9, r13; unsigned __int64
0x1800482b8  mov     r8d, esi; unsigned int
0x1800482bb  mov     rdx, [rsp+468h+var_410]; __int64
0x1800482c0  lea     rcx, [rsp+468h+var_3B8]; this
0x1800482c8  call    ??0FOLDER_USAGE@@QEAA@_JK_K@Z; FOLDER_USAGE::FOLDER_USAGE(__int64,ulong,unsigned __int64)
0x1800482cd  nop
0x1800482ce  mov     rax, [rsp+468h+var_3D8]
0x1800482d6  mov     [rsp+468h+var_368], rax
0x1800482de  lea     rdx, [rsp+468h+var_3B8]; struct FOLDER_USAGE *
0x1800482e6  lea     rcx, [rsp+468h+var_360]; this
0x1800482ee  call    ??0FOLDER_USAGE@@QEAA@AEBV0@@Z; FOLDER_USAGE::FOLDER_USAGE(FOLDER_USAGE const &)
0x1800482f3  nop
0x1800482f4  lea     rcx, [r14+40h]
0x1800482f8  lea     r8, [rsp+468h+var_368]
0x180048300  lea     rdx, [rsp+468h+var_3F0]
0x180048305  call    ?insert@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CB_JVFOLDER_USAGE@@@2@@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::insert(std::pair<__int64 const,FOLDER_USAGE> &&)
0x18004830a  nop
0x18004830b  lea     rcx, [rsp+468h+var_368]
0x180048313  call    ??1?$pair@$$CB_JVFOLDER_USAGE@@@std@@QEAA@XZ; std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(void)
0x180048318  mov     rdi, [rsp+468h+var_3F0]
0x18004831d  mov     [rsp+468h+var_3C0], rdi
0x180048325  cmp     [rsp+468h+var_3E8], 0
0x18004832d  jnz     short loc_180048388
0x18004832f  mov     rax, [rdi+18h]
0x180048333  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180048337  jnz     short loc_180048342
0x180048339  mov     rax, [rsp+468h+var_410]
0x18004833e  mov     [rdi+18h], rax
0x180048342  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180048346  jnz     short loc_18004837C
0x180048348  or      eax, 0FFFFFFFFh
0x18004834b  cmp     [rsp+468h+arg_30], eax
0x180048352  jnz     short loc_180048357
0x180048354  mov     esi, [rdi+28h]
0x180048357  mov     [rsp+468h+var_418], esi
0x18004835b  mov     [rdi+28h], esi
0x18004835e  cmp     esi, eax
0x180048360  jnz     short loc_180048369
0x180048362  mov     esi, 1
0x180048367  jmp     short loc_180048384
0x180048369  cmp     [rsp+468h+arg_30], eax
0x180048370  jnz     short loc_180048388
0x180048372  mov     [rsp+468h+var_3F4], 1
0x18004837a  jmp     short loc_180048388
  ... truncated ...
```
