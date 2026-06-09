# CTreeWalker::GetTopFolders(_DATA_TYPE_NODE,ulong,_STORAGE_TOP_FOLDER *,ulong *)

- ea: `0x18004545c`
- end: `0x180045b11`
- name: `?GetTopFolders@CTreeWalker@@QEAAJW4_DATA_TYPE_NODE@@KPEAU_STORAGE_TOP_FOLDER@@PEAK@Z`
- size: `1717`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037750`

## callees

- `0x18000d030`
- `0x18000dda4`
- `0x18000ddb0`
- `0x180018fb8`
- `0x18003d5b4`
- `0x18003dbc8`
- `0x18003df84`
- `0x18003fb50`
- `0x180042084`
- `0x180042360`
- `0x18004264c`
- `0x180042c64`
- `0x180043104`
- `0x1800437c8`
- `0x1800450e0`
- `0x18004545c`
- `0x18004b098`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045523`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045523`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTreeWalker::GetTopFolders(__int64 a1, int a2, unsigned int a3, void *a4, unsigned int *a5)
{
  int v5; // r12d
  __int64 v7; // rcx
  HANDLE FileW; // r15
  __int64 *v10; // r14
  __int64 i; // rsi
  unsigned __int64 *v12; // rbx
  _QWORD *v13; // rcx
  _QWORD *j; // rax
  _QWORD *v15; // rcx
  _QWORD *k; // rax
  __int64 *v17; // r10
  __int64 v18; // r11
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  unsigned __int64 v24; // r14
  _QWORD *v25; // rsi
  __int64 v26; // rax
  unsigned __int8 *v27; // rbx
  _QWORD *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r15
  _BYTE *v31; // rcx
  __int64 v32; // r15
  char v33; // al
  __int64 v34; // rax
  _BYTE *v35; // rcx
  __int64 v36; // r15
  unsigned __int8 *v37; // rdx
  unsigned int v38; // edi
  char *v39; // r14
  unsigned __int8 *v40; // rbx
  unsigned int v41; // r15d
  HANDLE v42; // rsi
  __int64 v43; // rdi
  _QWORD *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  char v48; // [rsp+40h] [rbp-C0h]
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v52; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v53; // [rsp+6Ch] [rbp-94h]
  int v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v57[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v58; // [rsp+90h] [rbp-70h]
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  union _LARGE_INTEGER v60; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v61; // [rsp+A8h] [rbp-58h] BYREF
  void *v62; // [rsp+B0h] [rbp-50h]
  unsigned int *v63; // [rsp+B8h] [rbp-48h]
  _BYTE *v64; // [rsp+C0h] [rbp-40h]
  _BYTE v65[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v66[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v67[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v68[16]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v69; // [rsp+108h] [rbp+8h]
  char v70[16]; // [rsp+110h] [rbp+10h] BYREF
  char v71[16]; // [rsp+120h] [rbp+20h] BYREF
  char v72[8]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v73; // [rsp+138h] [rbp+38h]
  char v74[24]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v75[80]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v76[264]; // [rsp+1D0h] [rbp+D0h] BYREF

  v62 = a4;
  v53 = a3;
  v5 = a2;
  v63 = a5;
  if ( !*(_BYTE *)(a1 + 313) )
  {
    if ( !a2 || a2 == 23 )
      goto LABEL_9;
    return 2147500033LL;
  }
  if ( !a2 || a2 == 2 || a2 == 3 || a2 == 4 || a2 == 9 || a2 == 12 )
    goto LABEL_10;
  if ( a2 != 23 )
    return 2147500033LL;
LABEL_9:
  v5 = 0;
LABEL_10:
  v52 = 0;
  *(_OWORD *)Src = 0;
  v50 = 0;
  v60.QuadPart = 0;
  std::list<__int64>::list<__int64>(v57);
  FileW = CreateFileW((LPCWSTR)(a1 + 328), 0x100u, 3u, 0, 3u, 0x2000080u, 0);
  hObject = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    std::_List_node<__int64,void *>::_Free_non_head<std::allocator<std::_List_node<__int64,void *>>>(v7, v57[0]);
    std::_Deallocate<16>(v57[0], (const struct std::nothrow_t *)0x18);
    if ( Src[0] )
    {
      std::_Deallocate<16>(
        (_QWORD *)Src[0],
        (const struct std::nothrow_t *)(((unsigned __int64)v50 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFF8uLL));
      *(_OWORD *)Src = 0;
      v50 = 0;
    }
    return 2147500037LL;
  }
  v58 = 0;
  v56 = 0x5000000000005LL;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::find(
                    a1 + 64,
                    &v61,
                    &v56) != *(_QWORD *)(a1 + 72) )
  {
    v56 = 0x5000000000005LL;
    if ( Src[1] == v50 )
    {
      std::vector<__int64>::_Emplace_reallocate<__int64 const &>(Src, Src[1], &v56);
    }
    else
    {
      *(_QWORD *)Src[1] = 0x5000000000005LL;
      Src[1] = (char *)Src[1] + 8;
    }
  }
  v10 = *(__int64 **)(a1 + 72);
  v61 = v10;
  for ( i = *v10; ; i = *(_QWORD *)i )
  {
    v56 = i;
    if ( (__int64 *)i == v10 )
      break;
    v12 = (unsigned __int64 *)(i + 16);
    v13 = *(_QWORD **)(a1 + 128);
    for ( j = (_QWORD *)*v13; j != v13; j = (_QWORD *)*j )
    {
      if ( j[2] == *v12 )
        goto LABEL_75;
    }
    if ( !*(_DWORD *)(i + 40) && *(_QWORD *)(i + 32) )
    {
      v15 = *(_QWORD **)(a1 + 144);
      for ( k = (_QWORD *)*v15; ; k = (_QWORD *)*k )
      {
        if ( k == v15 )
          goto LABEL_75;
        if ( k[2] == *(_QWORD *)(i + 24) )
          break;
      }
      v54 = v5;
      std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Find_lower_bound<int>(
        i + 80,
        v68,
        &v54);
      v19 = v69;
      if ( *(_BYTE *)(v69 + 25) != (_BYTE)v18 || v5 < *(_DWORD *)(v69 + 32) )
        v19 = *v17;
      if ( (*(_BYTE *)(a1 + 313) == (_BYTE)v18 || v19 != *v17 && *(_QWORD *)(v19 + 40) != v18)
        && (int)CTreeWalker::GetFolderPath((CTreeWalker *)a1, FileW, *v12, &v52, v76, &v60) >= 0 )
      {
        std::_List_node<__int64,void *>::_Free_non_head<std::allocator<std::_List_node<__int64,void *>>>(v20, v57[0]);
        *v57[0] = v57[0];
        *((_QWORD **)v57[0] + 1) = v57[0];
        v57[1] = 0;
        if ( *(_BYTE *)(a1 + 313) )
        {
          v64 = v75;
          v21 = (unsigned int)FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v75, (const struct FOLDER_USAGE *)(i + 24));
          CTreeWalker::_ReturnInterestingFolderIds(a1, *v12, v21, v5, (__int64)v57);
        }
        else
        {
          std::list<__int64>::_Emplace<__int64>(v57, v57[0], i + 16);
        }
        v22 = v57[0];
        v23 = (_QWORD *)*v57[0];
        v24 = v53;
        v25 = (_QWORD *)(a1 + 64);
        while ( 1 )
        {
          if ( v23 == v22 )
          {
            i = v56;
            v10 = v61;
            break;
          }
          v51 = v23[2];
          v26 = std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(
                  v25,
                  (__int64)v70,
                  (unsigned __int8 *)&v51);
          FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v72, (const struct FOLDER_USAGE *)(*(_QWORD *)v26 + 24LL));
          if ( *(_BYTE *)(a1 + 313)
            && (int)CTreeWalker::GetFolderPath((CTreeWalker *)a1, FileW, v23[2], &v52, v76, &v60) < 0 )
          {
            goto LABEL_69;
          }
          v48 = 0;
          v27 = (unsigned __int8 *)Src[0];
          while ( 1 )
          {
            if ( v27 == Src[1] )
            {
              v37 = (unsigned __int8 *)Src[1];
              if ( ((char *)Src[1] - (char *)Src[0]) >> 3 >= v24 )
                goto LABEL_67;
              if ( Src[1] != v50 )
              {
                *(_QWORD *)Src[1] = v51;
                goto LABEL_73;
              }
LABEL_66:
              std::vector<__int64>::_Emplace_reallocate<__int64 const &>(Src, v37, &v51);
              goto LABEL_67;
            }
            v28 = (_QWORD *)(a1 + 64);
            if ( !*(_BYTE *)(a1 + 313) )
              break;
            v54 = v5;
            v29 = *(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(
                               v28,
                               (__int64)v71,
                               v27)
                + 80LL;
            v55 = v5;
            v30 = *(_QWORD *)std::map<int,unsigned __int64>::_Try_emplace<int const &,>(v29, v65, &v55);
            if ( *(_QWORD *)(*(_QWORD *)std::map<int,unsigned __int64>::_Try_emplace<int const &,>(v74, v66, &v54) + 40LL) > *(_QWORD *)(v30 + 40) )
            {
              v31 = Src[1];
              if ( Src[1] == v50 )
              {
                std::vector<__int64>::_Emplace_reallocate<__int64 const &>(Src, v27, &v51);
              }
              else if ( v27 == Src[1] )
              {
                *(_QWORD *)Src[1] = v51;
                Src[1] = (char *)Src[1] + 8;
              }
              else
              {
                v32 = v51;
                *(_QWORD *)Src[1] = *((_QWORD *)Src[1] - 1);
                Src[1] = (char *)Src[1] + 8;
                memmove_0(v27 + 8, v27, v31 - v27 - 8);
                *(_QWORD *)v27 = v32;
              }
              v33 = 1;
              v48 = 1;
              goto LABEL_59;
            }
LABEL_58:
            v33 = v48;
LABEL_59:
            v27 += 8;
            if ( v33 )
              goto LABEL_67;
          }
          v34 = std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(
                  v28,
                  (__int64)v67,
                  v27);
          if ( v73 <= *(_QWORD *)(*(_QWORD *)v34 + 32LL) )
            goto LABEL_58;
          v35 = Src[1];
          if ( Src[1] == v50 )
          {
            v37 = v27;
            goto LABEL_66;
          }
          if ( v27 != Src[1] )
          {
            v36 = v51;
            *(_QWORD *)Src[1] = *((_QWORD *)Src[1] - 1);
            Src[1] = (char *)Src[1] + 8;
            memmove_0(v27 + 8, v27, v35 - v27 - 8);
            *(_QWORD *)v27 = v36;
            goto LABEL_67;
          }
          *(_QWORD *)Src[1] = v51;
LABEL_73:
          Src[1] = (char *)Src[1] + 8;
LABEL_67:
          FileW = hObject;
          v25 = (_QWORD *)(a1 + 64);
          if ( ((char *)Src[1] - (char *)Src[0]) >> 3 > v24 )
            Src[1] = (char *)Src[1] - 8;
LABEL_69:
          FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v72);
          v23 = (_QWORD *)*v23;
          v22 = v57[0];
        }
      }
    }
LABEL_75:
    ;
  }
  v38 = v53;
  v39 = (char *)v62;
  memset_0(v62, 0, 544LL * v53);
  v40 = (unsigned __int8 *)Src[0];
  v41 = v58;
  v42 = hObject;
  if ( v38 )
  {
    do
    {
      if ( v40 == Src[1] )
        break;
      v43 = 544LL * v41;
      *(_DWORD *)&v39[v43] = 544;
      v44 = (_QWORD *)(a1 + 64);
      if ( *(_BYTE *)(a1 + 313) )
      {
        v45 = *(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(
                           v44,
                           (__int64)v67,
                           v40)
            + 80LL;
        v55 = v5;
        v46 = *(_QWORD *)(*(_QWORD *)std::map<int,unsigned __int64>::_Try_emplace<int const &,>(v45, v66, &v55) + 40LL);
      }
      else
      {
        v46 = *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(
                                       v44,
                                       (__int64)v65,
                                       v40)
                        + 32LL);
      }
      *(_QWORD *)&v39[v43 + 528] = v46;
      if ( v46
        && (int)CTreeWalker::GetFolderPath(
                  (CTreeWalker *)a1,
                  v42,
                  *(_QWORD *)v40,
                  &v52,
                  (unsigned __int16 *)&v39[v43 + 4],
                  (union _LARGE_INTEGER *)&v39[v43 + 536]) >= 0 )
      {
        ++v41;
      }
      v40 += 8;
    }
    while ( v41 < v53 );
  }
  CloseHandle(v42);
  *v63 = v41;
  std::_List_node<__int64,void *>::_Free_non_head<std::allocator<std::_List_node<__int64,void *>>>(v47, v57[0]);
  std::_Deallocate<16>(v57[0], (const struct std::nothrow_t *)0x18);
  if ( Src[0] )
  {
    std::_Deallocate<16>(
      (_QWORD *)Src[0],
      (const struct std::nothrow_t *)(((unsigned __int64)v50 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFF8uLL));
    *(_OWORD *)Src = 0;
    v50 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18004545c  push    rbp
0x18004545e  push    rbx
0x18004545f  push    rsi
0x180045460  push    rdi
0x180045461  push    r12
0x180045463  push    r13
0x180045465  push    r14
0x180045467  push    r15
0x180045469  lea     rbp, [rsp-2F8h]
0x180045471  sub     rsp, 3F8h
0x180045478  mov     rax, cs:__security_cookie
0x18004547f  xor     rax, rsp
0x180045482  mov     [rbp+330h+var_50], rax
0x180045489  mov     [rbp+330h+var_380], r9
0x18004548d  mov     [rsp+430h+var_3C4], r8d
0x180045492  mov     r12d, edx
0x180045495  mov     r13, rcx
0x180045498  mov     rax, [rbp+330h+arg_20]
0x18004549f  mov     [rbp+330h+var_378], rax
0x1800454a3  mov     edi, 3
0x1800454a8  xor     ebx, ebx
0x1800454aa  cmp     [rcx+139h], bl
0x1800454b0  jz      loc_180045580
0x1800454b6  mov     ecx, edx
0x1800454b8  test    edx, edx
0x1800454ba  jz      short loc_1800454E0
0x1800454bc  sub     ecx, 2
0x1800454bf  jz      short loc_1800454E0
0x1800454c1  sub     ecx, 1
0x1800454c4  jz      short loc_1800454E0
0x1800454c6  sub     ecx, 1
0x1800454c9  jz      short loc_1800454E0
0x1800454cb  sub     ecx, 5
0x1800454ce  jz      short loc_1800454E0
0x1800454d0  sub     ecx, edi
0x1800454d2  jz      short loc_1800454E0
0x1800454d4  cmp     ecx, 0Bh
0x1800454d7  jnz     loc_180045591
0x1800454dd  mov     r12d, ebx
0x1800454e0  mov     [rsp+430h+var_3C8], ebx
0x1800454e4  xorps   xmm0, xmm0
0x1800454e7  movdqu  xmmword ptr [rsp+430h+Src], xmm0
0x1800454ed  mov     [rsp+430h+var_3D8], rbx
0x1800454f2  mov     qword ptr [rbp+330h+var_390], rbx
0x1800454f6  lea     rcx, [rbp+330h+var_3B0]
0x1800454fa  call    ??0?$list@_JV?$allocator@_J@std@@@std@@QEAA@XZ; std::list<__int64>::list<__int64>(void)
0x1800454ff  nop
0x180045500  lea     rcx, [r13+148h]; lpFileName
0x180045507  mov     [rsp+430h+hTemplateFile], rbx; unsigned int
0x18004550c  mov     [rsp+430h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180045514  mov     [rsp+430h+dwCreationDisposition], edi; dwCreationDisposition
0x180045518  xor     r9d, r9d; lpSecurityAttributes
0x18004551b  mov     r8d, edi; dwShareMode
0x18004551e  mov     edx, 100h; dwDesiredAccess
0x180045523  call    cs:__imp_CreateFileW
0x180045529  mov     r15, rax
0x18004552c  mov     [rbp+330h+hObject], rax
0x180045530  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045534  jnz     short loc_18004559B
0x180045536  mov     rdx, [rbp+330h+var_3B0]
0x18004553a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@_JPEAX@std@@@std@@@?$_List_node@_JPEAX@std@@SAXAEAV?$allocator@U?$_List_node@_JPEAX@std@@@1@PEAU01@@Z; std::_List_node<__int64,void *>::_Free_non_head<std::allocator<std::_List_node<__int64,void *>>>(std::allocator<std::_List_node<__int64,void *>> &,std::_List_node<__int64,void *> *)
0x18004553f  lea     edx, [r15+19h]
0x180045543  mov     rcx, [rbp+330h+var_3B0]
0x180045547  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004554c  nop
0x18004554d  mov     rcx, [rsp+430h+Src]
0x180045552  test    rcx, rcx
0x180045555  jz      short loc_180045576
0x180045557  mov     rdx, [rsp+430h+var_3D8]
0x18004555c  sub     rdx, rcx
0x18004555f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180045563  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180045568  xorps   xmm0, xmm0
0x18004556b  movdqu  xmmword ptr [rsp+430h+Src], xmm0
0x180045571  mov     [rsp+430h+var_3D8], rbx
0x180045576  mov     eax, 80004005h
0x18004557b  jmp     loc_180045AEE
0x180045580  test    edx, edx
0x180045582  jz      loc_1800454DD
0x180045588  cmp     edx, 17h
0x18004558b  jz      loc_1800454DD
0x180045591  mov     eax, 80004001h
0x180045596  jmp     loc_180045AEE
0x18004559b  mov     [rbp+330h+var_3A0], ebx
0x18004559e  mov     rbx, 5000000000005h
0x1800455a8  mov     [rsp+430h+var_3B8], rbx
0x1800455ad  lea     rcx, [r13+40h]
0x1800455b1  lea     r8, [rsp+430h+var_3B8]
0x1800455b6  lea     rdx, [rbp+330h+var_388]
0x1800455ba  call    ?find@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@2@AEB_J@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::find(__int64 const &)
0x1800455bf  mov     rcx, [r13+48h]
0x1800455c3  cmp     [rax], rcx
0x1800455c6  jz      short loc_1800455F3
0x1800455c8  mov     [rsp+430h+var_3B8], rbx
0x1800455cd  mov     rdx, [rsp+430h+Src+8]
0x1800455d2  cmp     rdx, [rsp+430h+var_3D8]
0x1800455d7  jz      short loc_1800455E4
0x1800455d9  mov     [rdx], rbx
0x1800455dc  add     [rsp+430h+Src+8], 8
0x1800455e2  jmp     short loc_1800455F3
0x1800455e4  lea     r8, [rsp+430h+var_3B8]
0x1800455e9  lea     rcx, [rsp+430h+Src]
0x1800455ee  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x1800455f3  mov     r14, [r13+48h]
0x1800455f7  mov     [rbp+330h+var_388], r14
0x1800455fb  mov     rsi, [r14]
0x1800455fe  mov     [rsp+430h+var_3B8], rsi
0x180045603  cmp     rsi, r14
0x180045606  jz      loc_1800459AE
0x18004560c  lea     rbx, [rsi+10h]
0x180045610  mov     rcx, [r13+80h]
0x180045617  mov     rax, [rcx]
0x18004561a  cmp     rax, rcx
0x18004561d  jz      short loc_180045631
0x18004561f  mov     rdx, [rbx]
0x180045622  cmp     [rax+10h], rdx
0x180045626  jz      loc_1800459A6
0x18004562c  mov     rax, [rax]
0x18004562f  jmp     short loc_18004561A
0x180045631  xor     r11d, r11d
0x180045634  cmp     [rbx+18h], r11d
0x180045638  jnz     loc_1800459A6
0x18004563e  cmp     [rsi+20h], r11
0x180045642  jz      loc_1800459A6
0x180045648  mov     rcx, [r13+90h]
0x18004564f  mov     rax, [rcx]
0x180045652  cmp     rax, rcx
0x180045655  jz      loc_1800459A6
0x18004565b  mov     rdx, [rbx+8]
0x18004565f  cmp     [rax+10h], rdx
0x180045663  jz      short loc_18004566A
0x180045665  mov     rax, [rax]
0x180045668  jmp     short loc_180045652
0x18004566a  lea     r10, [rsi+50h]
0x18004566e  mov     [rsp+430h+var_3C0], r12d
0x180045673  lea     r8, [rsp+430h+var_3C0]
0x180045678  lea     rdx, [rbp+330h+var_338]
0x18004567c  mov     rcx, r10
0x18004567f  call    ??$_Find_lower_bound@H@?$_Tree@V?$_Tmap_traits@HV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@1@AEBH@Z; std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Find_lower_bound<int>(int const &)
0x180045684  mov     rdx, [rbp+330h+var_328]
0x180045688  cmp     [rdx+19h], r11b
0x18004568c  jnz     short loc_180045694
0x18004568e  cmp     r12d, [rdx+20h]
0x180045692  jge     short loc_180045697
0x180045694  mov     rdx, [r10]
0x180045697  cmp     [r13+139h], r11b
0x18004569e  jz      short loc_1800456B3
0x1800456a0  cmp     rdx, [r10]
0x1800456a3  jz      loc_1800459A6
0x1800456a9  cmp     [rdx+28h], r11
0x1800456ad  jz      loc_1800459A6
0x1800456b3  lea     rax, [rbp+330h+var_390]
0x1800456b7  mov     qword ptr [rsp+430h+dwFlagsAndAttributes], rax; union _LARGE_INTEGER *
0x1800456bc  lea     rax, [rbp+330h+var_260]
0x1800456c3  mov     qword ptr [rsp+430h+dwCreationDisposition], rax; unsigned __int16 *
0x1800456c8  lea     r9, [rsp+430h+var_3C8]; unsigned int *
0x1800456cd  mov     r8, [rbx]; __int64
0x1800456d0  mov     rdx, r15; void *
0x1800456d3  mov     rcx, r13; this
0x1800456d6  call    ?GetFolderPath@CTreeWalker@@AEAAJPEAX_JPEAKPEAGPEAT_LARGE_INTEGER@@K@Z; CTreeWalker::GetFolderPath(void *,__int64,ulong *,ushort *,_LARGE_INTEGER *,ulong)
0x1800456db  test    eax, eax
0x1800456dd  js      loc_1800459A6
0x1800456e3  mov     rdx, [rbp+330h+var_3B0]
0x1800456e7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@_JPEAX@std@@@std@@@?$_List_node@_JPEAX@std@@SAXAEAV?$allocator@U?$_List_node@_JPEAX@std@@@1@PEAU01@@Z; std::_List_node<__int64,void *>::_Free_non_head<std::allocator<std::_List_node<__int64,void *>>>(std::allocator<std::_List_node<__int64,void *>> &,std::_List_node<__int64,void *> *)
0x1800456ec  mov     rax, [rbp+330h+var_3B0]
0x1800456f0  mov     [rax], rax
0x1800456f3  mov     rax, [rbp+330h+var_3B0]
0x1800456f7  mov     [rax+8], rax
0x1800456fb  mov     [rbp+330h+var_3A8], 0
0x180045703  cmp     byte ptr [r13+139h], 0
0x18004570b  jz      short loc_180045745
0x18004570d  lea     rax, [rbp+330h+var_2B0]
0x180045714  mov     [rbp+330h+var_370], rax
0x180045718  lea     rdx, [rbx+8]; struct FOLDER_USAGE *
0x18004571c  lea     rcx, [rbp+330h+var_2B0]; this
0x180045723  call    ??0FOLDER_USAGE@@QEAA@AEBV0@@Z; FOLDER_USAGE::FOLDER_USAGE(FOLDER_USAGE const &)
0x180045728  nop
0x180045729  mov     rdx, [rbx]
0x18004572c  lea     rcx, [rbp+330h+var_3B0]
0x180045730  mov     qword ptr [rsp+430h+dwCreationDisposition], rcx
0x180045735  mov     r9d, r12d
0x180045738  mov     r8, rax
0x18004573b  mov     rcx, r13
0x18004573e  call    ?_ReturnInterestingFolderIds@CTreeWalker@@AEAAX_JVFOLDER_USAGE@@HPEAV?$list@_JV?$allocator@_J@std@@@std@@@Z; CTreeWalker::_ReturnInterestingFolderIds(__int64,FOLDER_USAGE,int,std::list<__int64> *)
0x180045743  jmp     short loc_180045755
0x180045745  mov     r8, rbx
0x180045748  mov     rdx, [rbp+330h+var_3B0]
0x18004574c  lea     rcx, [rbp+330h+var_3B0]
0x180045750  call    ??$_Emplace@_J@?$list@_JV?$allocator@_J@std@@@std@@QEAAPEAU?$_List_node@_JPEAX@1@QEAU21@$$QEA_J@Z; std::list<__int64>::_Emplace<__int64>(std::_List_node<__int64,void *> * const,__int64 &&)
0x180045755  mov     rax, [rbp+330h+var_3B0]
0x180045759  mov     rdi, [rax]
0x18004575c  mov     r14d, [rsp+430h+var_3C4]
0x180045761  lea     rsi, [r13+40h]
0x180045765  cmp     rdi, rax
0x180045768  jz      loc_18004599D
0x18004576e  mov     rax, [rdi+10h]
0x180045772  mov     [rsp+430h+var_3D0], rax
0x180045777  lea     r8, [rsp+430h+var_3D0]
0x18004577c  lea     rdx, [rbp+330h+var_320]
0x180045780  mov     rcx, rsi
0x180045783  call    ??$_Try_emplace@AEB_J$$V@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(__int64 const &)
0x180045788  mov     rdx, [rax]
0x18004578b  add     rdx, 18h; struct FOLDER_USAGE *
0x18004578f  lea     rcx, [rbp+330h+var_300]; this
0x180045793  call    ??0FOLDER_USAGE@@QEAA@AEBV0@@Z; FOLDER_USAGE::FOLDER_USAGE(FOLDER_USAGE const &)
0x180045798  nop
0x180045799  cmp     byte ptr [r13+139h], 0
0x1800457a1  jz      short loc_1800457D4
0x1800457a3  lea     rax, [rbp+330h+var_390]
0x1800457a7  mov     qword ptr [rsp+430h+dwFlagsAndAttributes], rax; union _LARGE_INTEGER *
0x1800457ac  lea     rax, [rbp+330h+var_260]
0x1800457b3  mov     qword ptr [rsp+430h+dwCreationDisposition], rax; unsigned __int16 *
0x1800457b8  lea     r9, [rsp+430h+var_3C8]; unsigned int *
0x1800457bd  mov     r8, [rdi+10h]; __int64
0x1800457c1  mov     rdx, r15; void *
0x1800457c4  mov     rcx, r13; this
0x1800457c7  call    ?GetFolderPath@CTreeWalker@@AEAAJPEAX_JPEAKPEAGPEAT_LARGE_INTEGER@@K@Z; CTreeWalker::GetFolderPath(void *,__int64,ulong *,ushort *,_LARGE_INTEGER *,ulong)
0x1800457cc  test    eax, eax
0x1800457ce  js      loc_18004595B
0x1800457d4  xor     al, al
0x1800457d6  mov     [rsp+430h+var_3F0], al
0x1800457da  mov     rbx, [rsp+430h+Src]
0x1800457df  cmp     rbx, [rsp+430h+Src+8]
0x1800457e4  jz      loc_180045970
0x1800457ea  mov     r8, rbx
0x1800457ed  lea     rcx, [r13+40h]
0x1800457f1  cmp     byte ptr [r13+139h], 0
0x1800457f9  jz      loc_1800458B0
0x1800457ff  mov     [rsp+430h+var_3C0], r12d
0x180045804  lea     rdx, [rbp+330h+var_310]
0x180045808  call    ??$_Try_emplace@AEB_J$$V@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18004580d  mov     rcx, [rax]
0x180045810  add     rcx, 50h ; 'P'
0x180045814  mov     [rsp+430h+var_3BC], r12d
0x180045819  lea     r8, [rsp+430h+var_3BC]
0x18004581e  lea     rdx, [rbp+330h+var_368]
0x180045822  call    ??$_Try_emplace@AEBH$$V@?$map@H_KU?$less@H@std@@V?$allocator@U?$pair@$$CBH_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBH_K@std@@PEAX@std@@_N@1@AEBH@Z; std::map<int,unsigned __int64>::_Try_emplace<int const &,>(int const &)
0x180045827  mov     r15, [rax]
0x18004582a  lea     r8, [rsp+430h+var_3C0]
0x18004582f  lea     rdx, [rbp+330h+var_358]
0x180045833  lea     rcx, [rbp+330h+var_2C8]
0x180045837  call    ??$_Try_emplace@AEBH$$V@?$map@H_KU?$less@H@std@@V?$allocator@U?$pair@$$CBH_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBH_K@std@@PEAX@std@@_N@1@AEBH@Z; std::map<int,unsigned __int64>::_Try_emplace<int const &,>(int const &)
0x18004583c  mov     rcx, [rax]
0x18004583f  mov     rax, [r15+28h]
0x180045843  cmp     [rcx+28h], rax
0x180045847  jbe     short loc_1800458C6
0x180045849  mov     rcx, [rsp+430h+Src+8]
0x18004584e  cmp     rcx, [rsp+430h+var_3D8]
0x180045853  jz      short loc_180045896
0x180045855  cmp     rbx, rcx
0x180045858  jnz     short loc_18004586A
0x18004585a  mov     rax, [rsp+430h+var_3D0]
0x18004585f  mov     [rcx], rax
0x180045862  add     [rsp+430h+Src+8], 8
0x180045868  jmp     short loc_1800458A8
0x18004586a  mov     r15, [rsp+430h+var_3D0]
0x18004586f  mov     rax, [rcx-8]
0x180045873  mov     [rcx], rax
0x180045876  add     [rsp+430h+Src+8], 8
0x18004587c  mov     r8, rcx
0x18004587f  sub     r8, rbx
0x180045882  add     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180045886  sub     rcx, r8; void *
0x180045889  mov     rdx, rbx; Src
0x18004588c  call    memmove_0
0x180045891  mov     [rbx], r15
0x180045894  jmp     short loc_1800458A8
0x180045896  lea     r8, [rsp+430h+var_3D0]
0x18004589b  mov     rdx, rbx
0x18004589e  lea     rcx, [rsp+430h+Src]
0x1800458a3  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x1800458a8  mov     al, 1
0x1800458aa  mov     [rsp+430h+var_3F0], al
0x1800458ae  jmp     short loc_1800458CA
0x1800458b0  lea     rdx, [rbp+330h+var_348]
0x1800458b4  call    ??$_Try_emplace@AEB_J$$V@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::_Try_emplace<__int64 const &,>(__int64 const &)
0x1800458b9  mov     rcx, [rax]
0x1800458bc  mov     rax, [rcx+20h]
0x1800458c0  cmp     [rbp+330h+var_2F8], rax
0x1800458c4  ja      short loc_1800458D8
0x1800458c6  mov     al, [rsp+430h+var_3F0]
0x1800458ca  add     rbx, 8
0x1800458ce  test    al, al
0x1800458d0  jz      loc_1800457DF
0x1800458d6  jmp     short loc_180045934
0x1800458d8  mov     rcx, [rsp+430h+Src+8]
0x1800458dd  cmp     rcx, [rsp+430h+var_3D8]
0x1800458e2  jz      short loc_180045922
0x1800458e4  cmp     rbx, rcx
0x1800458e7  jnz     short loc_1800458F6
0x1800458e9  mov     rax, [rsp+430h+var_3D0]
0x1800458ee  mov     [rcx], rax
0x1800458f1  jmp     loc_180045995
0x1800458f6  mov     r15, [rsp+430h+var_3D0]
0x1800458fb  mov     rax, [rcx-8]
0x1800458ff  mov     [rcx], rax
0x180045902  add     [rsp+430h+Src+8], 8
0x180045908  mov     r8, rcx
0x18004590b  sub     r8, rbx
0x18004590e  add     r8, 0FFFFFFFFFFFFFFF8h; Size
  ... truncated ...
```
