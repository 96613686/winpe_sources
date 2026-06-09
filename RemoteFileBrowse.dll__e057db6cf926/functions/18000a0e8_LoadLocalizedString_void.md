# LoadLocalizedString(void)

- ea: `0x18000a0e8`
- end: `0x18000abdb`
- name: `?LoadLocalizedString@@YAHXZ`
- size: `2803`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000b0b4`

## callees

- `0x180002030`
- `0x180002054`
- `0x180002db8`
- `0x1800054a4`
- `0x18000591c`
- `0x18000798c`
- `0x180009c2c`
- `0x18000a0e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a176`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a176`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a194`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a214`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a290`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a30c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a388`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a404`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a480`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a4fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a670`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a6ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a768`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a7e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a860`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a8dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a958`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a9d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aa50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aacc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ab48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a194`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a214`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a290`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a30c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a388`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a404`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a480`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a4fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a670`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a6ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a768`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a7e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a860`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a8dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a958`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a9d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aa50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000aacc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ab48`

## string_xrefs

- `0x18000a16f`: `RemoteFileBrowse.dll`

## pseudocode

```c
__int64 LoadLocalizedString(void)
{
  unsigned int v0; // r12d
  _QWORD *v1; // rsi
  _QWORD *v2; // rdi
  void *v3; // rbx
  char **v4; // rcx
  HMODULE ModuleHandleW; // r15
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  char *v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  char *v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // rdx
  char *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r8
  unsigned __int64 v33; // rdx
  char *v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r8
  unsigned __int64 v39; // rdx
  char *v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rdx
  char *v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r8
  unsigned __int64 v51; // rdx
  char *v52; // rdi
  __int64 v53; // rbx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // r8
  unsigned __int64 v57; // rdx
  char *v58; // rdi
  __int64 v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // r8
  unsigned __int64 v63; // rdx
  char *v64; // rdi
  __int64 v65; // rbx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // r8
  unsigned __int64 v69; // rdx
  char *v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rcx
  __int64 v73; // rax
  __int64 v74; // r8
  unsigned __int64 v75; // rdx
  char *v76; // rdi
  __int64 v77; // rbx
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // r8
  unsigned __int64 v81; // rdx
  char *v82; // rdi
  __int64 v83; // rbx
  __int64 v84; // rcx
  __int64 v85; // rax
  __int64 v86; // r8
  unsigned __int64 v87; // rdx
  char *v88; // rdi
  __int64 v89; // rbx
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // r8
  unsigned __int64 v93; // rdx
  char *v94; // rdi
  __int64 v95; // rbx
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // r8
  unsigned __int64 v99; // rdx
  char *v100; // rdi
  __int64 v101; // rbx
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // r8
  unsigned __int64 v105; // rdx
  char *v106; // rdi
  __int64 v107; // rbx
  __int64 v108; // rcx
  __int64 v109; // rax
  __int64 v110; // r8
  unsigned __int64 v111; // rdx
  char *v112; // rdi
  __int64 v113; // rbx
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // r8
  unsigned __int64 v117; // rdx
  char *v118; // rdi
  __int64 v119; // rbx
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // r8
  unsigned __int64 v123; // rdx
  char *v124; // rdi
  __int64 v125; // rbx
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // r8
  unsigned __int64 v129; // rsi
  char *v130; // rdi
  _DWORD v132[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  v0 = 1;
  v1 = (_QWORD *)LocalizedStringCache;
  v2 = *(_QWORD **)(LocalizedStringCache + 8);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<int const,std::wstring>,void *>>>(
      &LocalizedStringCache,
      &LocalizedStringCache,
      v2[2]);
    v3 = v2;
    v4 = (char **)v2;
    v2 = (_QWORD *)*v2;
    std::wstring::~wstring(v4 + 5);
    operator delete(v3);
  }
  v1[1] = v1;
  *v1 = v1;
  v1[2] = v1;
  qword_180023690 = 0;
  ModuleHandleW = GetModuleHandleW(L"RemoteFileBrowse.dll");
  LoadStringW(ModuleHandleW, 0x64u, Buffer, 260);
  v132[0] = 100;
  try
  {
    v7 = std::map<int,std::wstring>::operator[](v6, v132);
    v129 = -1;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    if ( v9 > *(_QWORD *)(v7 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v7,
        v9,
        v8,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v7 + 24) <= 7u )
        v10 = (char *)v7;
      else
        v10 = *(char **)v7;
      *(_QWORD *)(v7 + 16) = v9;
      v11 = 2 * v9;
      memmove_0(v10, Buffer, 2 * v9);
      *(_WORD *)&v10[v11] = 0;
    }
    LoadStringW(ModuleHandleW, 0x65u, Buffer, 260);
    v132[0] = 101;
    v13 = std::map<int,std::wstring>::operator[](v12, v132);
    v15 = -1;
    do
      ++v15;
    while ( Buffer[v15] );
    if ( v15 > *(_QWORD *)(v13 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v13,
        v15,
        v14,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v13 + 24) <= 7u )
        v16 = (char *)v13;
      else
        v16 = *(char **)v13;
      *(_QWORD *)(v13 + 16) = v15;
      v17 = 2 * v15;
      memmove_0(v16, Buffer, 2 * v15);
      *(_WORD *)&v16[v17] = 0;
    }
    LoadStringW(ModuleHandleW, 0x66u, Buffer, 260);
    v132[0] = 102;
    v19 = std::map<int,std::wstring>::operator[](v18, v132);
    v21 = -1;
    do
      ++v21;
    while ( Buffer[v21] );
    if ( v21 > *(_QWORD *)(v19 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v19,
        v21,
        v20,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v19 + 24) <= 7u )
        v22 = (char *)v19;
      else
        v22 = *(char **)v19;
      *(_QWORD *)(v19 + 16) = v21;
      v23 = 2 * v21;
      memmove_0(v22, Buffer, 2 * v21);
      *(_WORD *)&v22[v23] = 0;
    }
    LoadStringW(ModuleHandleW, 0x67u, Buffer, 260);
    v132[0] = 103;
    v25 = std::map<int,std::wstring>::operator[](v24, v132);
    v27 = -1;
    do
      ++v27;
    while ( Buffer[v27] );
    if ( v27 > *(_QWORD *)(v25 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v25,
        v27,
        v26,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v25 + 24) <= 7u )
        v28 = (char *)v25;
      else
        v28 = *(char **)v25;
      *(_QWORD *)(v25 + 16) = v27;
      v29 = 2 * v27;
      memmove_0(v28, Buffer, 2 * v27);
      *(_WORD *)&v28[v29] = 0;
    }
    LoadStringW(ModuleHandleW, 0x68u, Buffer, 260);
    v132[0] = 104;
    v31 = std::map<int,std::wstring>::operator[](v30, v132);
    v33 = -1;
    do
      ++v33;
    while ( Buffer[v33] );
    if ( v33 > *(_QWORD *)(v31 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v31,
        v33,
        v32,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v31 + 24) <= 7u )
        v34 = (char *)v31;
      else
        v34 = *(char **)v31;
      *(_QWORD *)(v31 + 16) = v33;
      v35 = 2 * v33;
      memmove_0(v34, Buffer, 2 * v33);
      *(_WORD *)&v34[v35] = 0;
    }
    LoadStringW(ModuleHandleW, 0x69u, Buffer, 260);
    v132[0] = 105;
    v37 = std::map<int,std::wstring>::operator[](v36, v132);
    v39 = -1;
    do
      ++v39;
    while ( Buffer[v39] );
    if ( v39 > *(_QWORD *)(v37 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v37,
        v39,
        v38,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v37 + 24) <= 7u )
        v40 = (char *)v37;
      else
        v40 = *(char **)v37;
      *(_QWORD *)(v37 + 16) = v39;
      v41 = 2 * v39;
      memmove_0(v40, Buffer, 2 * v39);
      *(_WORD *)&v40[v41] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Au, Buffer, 260);
    v132[0] = 106;
    v43 = std::map<int,std::wstring>::operator[](v42, v132);
    v45 = -1;
    do
      ++v45;
    while ( Buffer[v45] );
    if ( v45 > *(_QWORD *)(v43 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v43,
        v45,
        v44,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v43 + 24) <= 7u )
        v46 = (char *)v43;
      else
        v46 = *(char **)v43;
      *(_QWORD *)(v43 + 16) = v45;
      v47 = 2 * v45;
      memmove_0(v46, Buffer, 2 * v45);
      *(_WORD *)&v46[v47] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Bu, Buffer, 260);
    v132[0] = 107;
    v49 = std::map<int,std::wstring>::operator[](v48, v132);
    v51 = -1;
    do
      ++v51;
    while ( Buffer[v51] );
    if ( v51 > *(_QWORD *)(v49 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v49,
        v51,
        v50,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v49 + 24) <= 7u )
        v52 = (char *)v49;
      else
        v52 = *(char **)v49;
      *(_QWORD *)(v49 + 16) = v51;
      v53 = 2 * v51;
      memmove_0(v52, Buffer, 2 * v51);
      *(_WORD *)&v52[v53] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Cu, Buffer, 260);
    v132[0] = 108;
    v55 = std::map<int,std::wstring>::operator[](v54, v132);
    v57 = -1;
    do
      ++v57;
    while ( Buffer[v57] );
    if ( v57 > *(_QWORD *)(v55 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v55,
        v57,
        v56,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v55 + 24) <= 7u )
        v58 = (char *)v55;
      else
        v58 = *(char **)v55;
      *(_QWORD *)(v55 + 16) = v57;
      v59 = 2 * v57;
      memmove_0(v58, Buffer, 2 * v57);
      *(_WORD *)&v58[v59] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Du, Buffer, 260);
    v132[0] = 109;
    v61 = std::map<int,std::wstring>::operator[](v60, v132);
    v63 = -1;
    do
      ++v63;
    while ( Buffer[v63] );
    if ( v63 > *(_QWORD *)(v61 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v61,
        v63,
        v62,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v61 + 24) <= 7u )
        v64 = (char *)v61;
      else
        v64 = *(char **)v61;
      *(_QWORD *)(v61 + 16) = v63;
      v65 = 2 * v63;
      memmove_0(v64, Buffer, 2 * v63);
      *(_WORD *)&v64[v65] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Eu, Buffer, 260);
    v132[0] = 110;
    v67 = std::map<int,std::wstring>::operator[](v66, v132);
    v69 = -1;
    do
      ++v69;
    while ( Buffer[v69] );
    if ( v69 > *(_QWORD *)(v67 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v67,
        v69,
        v68,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v67 + 24) <= 7u )
        v70 = (char *)v67;
      else
        v70 = *(char **)v67;
      *(_QWORD *)(v67 + 16) = v69;
      v71 = 2 * v69;
      memmove_0(v70, Buffer, 2 * v69);
      *(_WORD *)&v70[v71] = 0;
    }
    LoadStringW(ModuleHandleW, 0x6Fu, Buffer, 260);
    v132[0] = 111;
    v73 = std::map<int,std::wstring>::operator[](v72, v132);
    v75 = -1;
    do
      ++v75;
    while ( Buffer[v75] );
    if ( v75 > *(_QWORD *)(v73 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v73,
        v75,
        v74,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v73 + 24) <= 7u )
        v76 = (char *)v73;
      else
        v76 = *(char **)v73;
      *(_QWORD *)(v73 + 16) = v75;
      v77 = 2 * v75;
      memmove_0(v76, Buffer, 2 * v75);
      *(_WORD *)&v76[v77] = 0;
    }
    LoadStringW(ModuleHandleW, 0x70u, Buffer, 260);
    v132[0] = 112;
    v79 = std::map<int,std::wstring>::operator[](v78, v132);
    v81 = -1;
    do
      ++v81;
    while ( Buffer[v81] );
    if ( v81 > *(_QWORD *)(v79 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v79,
        v81,
        v80,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v79 + 24) <= 7u )
        v82 = (char *)v79;
      else
        v82 = *(char **)v79;
      *(_QWORD *)(v79 + 16) = v81;
      v83 = 2 * v81;
      memmove_0(v82, Buffer, 2 * v81);
      *(_WORD *)&v82[v83] = 0;
    }
    LoadStringW(ModuleHandleW, 0x71u, Buffer, 260);
    v132[0] = 113;
    v85 = std::map<int,std::wstring>::operator[](v84, v132);
    v87 = -1;
    do
      ++v87;
    while ( Buffer[v87] );
    if ( v87 > *(_QWORD *)(v85 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v85,
        v87,
        v86,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v85 + 24) <= 7u )
        v88 = (char *)v85;
      else
        v88 = *(char **)v85;
      *(_QWORD *)(v85 + 16) = v87;
      v89 = 2 * v87;
      memmove_0(v88, Buffer, 2 * v87);
      *(_WORD *)&v88[v89] = 0;
    }
    LoadStringW(ModuleHandleW, 0x73u, Buffer, 260);
    v132[0] = 115;
    v91 = std::map<int,std::wstring>::operator[](v90, v132);
    v93 = -1;
    do
      ++v93;
    while ( Buffer[v93] );
    if ( v93 > *(_QWORD *)(v91 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v91,
        v93,
        v92,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v91 + 24) <= 7u )
        v94 = (char *)v91;
      else
        v94 = *(char **)v91;
      *(_QWORD *)(v91 + 16) = v93;
      v95 = 2 * v93;
      memmove_0(v94, Buffer, 2 * v93);
      *(_WORD *)&v94[v95] = 0;
    }
    LoadStringW(ModuleHandleW, 0x74u, Buffer, 260);
    v132[0] = 116;
    v97 = std::map<int,std::wstring>::operator[](v96, v132);
    v99 = -1;
    do
      ++v99;
    while ( Buffer[v99] );
    if ( v99 > *(_QWORD *)(v97 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v97,
        v99,
        v98,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v97 + 24) <= 7u )
        v100 = (char *)v97;
      else
        v100 = *(char **)v97;
      *(_QWORD *)(v97 + 16) = v99;
      v101 = 2 * v99;
      memmove_0(v100, Buffer, 2 * v99);
      *(_WORD *)&v100[v101] = 0;
    }
    LoadStringW(ModuleHandleW, 0x75u, Buffer, 260);
    v132[0] = 117;
    v103 = std::map<int,std::wstring>::operator[](v102, v132);
    v105 = -1;
    do
      ++v105;
    while ( Buffer[v105] );
    if ( v105 > *(_QWORD *)(v103 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v103,
        v105,
        v104,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v103 + 24) <= 7u )
        v106 = (char *)v103;
      else
        v106 = *(char **)v103;
      *(_QWORD *)(v103 + 16) = v105;
      v107 = 2 * v105;
      memmove_0(v106, Buffer, 2 * v105);
      *(_WORD *)&v106[v107] = 0;
    }
    LoadStringW(ModuleHandleW, 0x76u, Buffer, 260);
    v132[0] = 118;
    v109 = std::map<int,std::wstring>::operator[](v108, v132);
    v111 = -1;
    do
      ++v111;
    while ( Buffer[v111] );
    if ( v111 > *(_QWORD *)(v109 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v109,
        v111,
        v110,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v109 + 24) <= 7u )
        v112 = (char *)v109;
      else
        v112 = *(char **)v109;
      *(_QWORD *)(v109 + 16) = v111;
      v113 = 2 * v111;
      memmove_0(v112, Buffer, 2 * v111);
      *(_WORD *)&v112[v113] = 0;
    }
    LoadStringW(ModuleHandleW, 0x77u, Buffer, 260);
    v132[0] = 119;
    v115 = std::map<int,std::wstring>::operator[](v114, v132);
    v117 = -1;
    do
      ++v117;
    while ( Buffer[v117] );
    if ( v117 > *(_QWORD *)(v115 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v115,
        v117,
        v116,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v115 + 24) <= 7u )
        v118 = (char *)v115;
      else
        v118 = *(char **)v115;
      *(_QWORD *)(v115 + 16) = v117;
      v119 = 2 * v117;
      memmove_0(v118, Buffer, 2 * v117);
      *(_WORD *)&v118[v119] = 0;
    }
    LoadStringW(ModuleHandleW, 0x78u, Buffer, 260);
    v132[0] = 120;
    v121 = std::map<int,std::wstring>::operator[](v120, v132);
    v123 = -1;
    do
      ++v123;
    while ( Buffer[v123] );
    if ( v123 > *(_QWORD *)(v121 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v121,
        v123,
        v122,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v121 + 24) <= 7u )
        v124 = (char *)v121;
      else
        v124 = *(char **)v121;
      *(_QWORD *)(v121 + 16) = v123;
      v125 = 2 * v123;
      memmove_0(v124, Buffer, 2 * v123);
      *(_WORD *)&v124[v125] = 0;
    }
    LoadStringW(ModuleHandleW, 0x79u, Buffer, 260);
    v132[0] = 121;
    v127 = std::map<int,std::wstring>::operator[](v126, v132);
    do
      ++v129;
    while ( Buffer[v129] );
    if ( v129 > *(_QWORD *)(v127 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v127,
        v129,
        v128,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(v127 + 24) <= 7u )
        v130 = (char *)v127;
      else
        v130 = *(char **)v127;
      *(_QWORD *)(v127 + 16) = v129;
      memmove_0(v130, Buffer, 2 * v129);
      *(_WORD *)&v130[2 * v129] = 0;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x18000a0e8  push    rbx
0x18000a0ea  push    rsi
0x18000a0eb  push    rdi
0x18000a0ec  push    r12
0x18000a0ee  push    r13
0x18000a0f0  push    r15
0x18000a0f2  sub     rsp, 258h
0x18000a0f9  mov     rax, cs:__security_cookie
0x18000a100  xor     rax, rsp
0x18000a103  mov     [rsp+288h+var_48], rax
0x18000a10b  mov     r12d, 1
0x18000a111  mov     rsi, cs:?LocalizedStringCache@@3V?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@A; std::map<int,std::wstring> LocalizedStringCache
0x18000a118  mov     rdi, [rsi+8]
0x18000a11c  xor     r13d, r13d
0x18000a11f  jmp     short loc_18000A157
0x18000a121  mov     r8, [rdi+10h]
0x18000a125  lea     rdx, ?LocalizedStringCache@@3V?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@A; std::map<int,std::wstring> LocalizedStringCache
0x18000a12c  lea     rcx, ?LocalizedStringCache@@3V?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@A; std::map<int,std::wstring> LocalizedStringCache
0x18000a133  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<int const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<int const,std::wstring>,void *>> &,std::_Tree_node<std::pair<int const,std::wstring>,void *> *)
0x18000a138  mov     rbx, rdi
0x18000a13b  mov     rcx, rdi
0x18000a13e  mov     rdi, [rdi]
0x18000a141  add     rcx, 28h ; '('
0x18000a145  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a14a  mov     edx, 48h ; 'H'; unsigned __int64
0x18000a14f  mov     rcx, rbx; void *
0x18000a152  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a157  cmp     [rdi+19h], r13b
0x18000a15b  jz      short loc_18000A121
0x18000a15d  mov     [rsi+8], rsi
0x18000a161  mov     [rsi], rsi
0x18000a164  mov     [rsi+10h], rsi
0x18000a168  mov     cs:qword_180023690, r13
0x18000a16f  lea     rcx, aRemotefilebrow_0; "RemoteFileBrowse.dll"
0x18000a176  call    cs:__imp_GetModuleHandleW
0x18000a17c  mov     r15, rax
0x18000a17f  mov     r9d, 104h; cchBufferMax
0x18000a185  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a18a  mov     ebx, 64h ; 'd'
0x18000a18f  mov     edx, ebx; uID
0x18000a191  mov     rcx, rax; hInstance
0x18000a194  call    cs:__imp_LoadStringW
0x18000a19a  mov     [rsp+288h+var_268], ebx
0x18000a19e  lea     rdx, [rsp+288h+var_268]
0x18000a1a3  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a1a8  lea     rcx, [rsp+288h+Buffer]
0x18000a1ad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a1b1  mov     rdx, rsi
0x18000a1b4  inc     rdx
0x18000a1b7  cmp     [rcx+rdx*2], r13w
0x18000a1bc  jnz     short loc_18000A1B4
0x18000a1be  cmp     rdx, [rax+18h]
0x18000a1c2  ja      short loc_18000A1F2
0x18000a1c4  cmp     qword ptr [rax+18h], 7
0x18000a1c9  jbe     short loc_18000A1D0
0x18000a1cb  mov     rdi, [rax]
0x18000a1ce  jmp     short loc_18000A1D3
0x18000a1d0  mov     rdi, rax
0x18000a1d3  mov     [rax+10h], rdx
0x18000a1d7  lea     rbx, [rdx+rdx]
0x18000a1db  mov     r8, rbx; Size
0x18000a1de  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a1e3  mov     rcx, rdi; void *
0x18000a1e6  call    memmove_0
0x18000a1eb  mov     [rbx+rdi], r13w
0x18000a1f0  jmp     short loc_18000A1FF
0x18000a1f2  lea     r9, [rsp+288h+Buffer]
0x18000a1f7  mov     rcx, rax
0x18000a1fa  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a1ff  mov     r9d, 104h; cchBufferMax
0x18000a205  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a20a  mov     ebx, 65h ; 'e'
0x18000a20f  mov     edx, ebx; uID
0x18000a211  mov     rcx, r15; hInstance
0x18000a214  call    cs:__imp_LoadStringW
0x18000a21a  mov     [rsp+288h+var_268], ebx
0x18000a21e  lea     rdx, [rsp+288h+var_268]
0x18000a223  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a228  lea     rcx, [rsp+288h+Buffer]
0x18000a22d  mov     rdx, rsi
0x18000a230  inc     rdx
0x18000a233  cmp     [rcx+rdx*2], r13w
0x18000a238  jnz     short loc_18000A230
0x18000a23a  cmp     rdx, [rax+18h]
0x18000a23e  ja      short loc_18000A26E
0x18000a240  cmp     qword ptr [rax+18h], 7
0x18000a245  jbe     short loc_18000A24C
0x18000a247  mov     rdi, [rax]
0x18000a24a  jmp     short loc_18000A24F
0x18000a24c  mov     rdi, rax
0x18000a24f  mov     [rax+10h], rdx
0x18000a253  lea     rbx, [rdx+rdx]
0x18000a257  mov     r8, rbx; Size
0x18000a25a  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a25f  mov     rcx, rdi; void *
0x18000a262  call    memmove_0
0x18000a267  mov     [rbx+rdi], r13w
0x18000a26c  jmp     short loc_18000A27B
0x18000a26e  lea     r9, [rsp+288h+Buffer]
0x18000a273  mov     rcx, rax
0x18000a276  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a27b  mov     r9d, 104h; cchBufferMax
0x18000a281  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a286  mov     ebx, 66h ; 'f'
0x18000a28b  mov     edx, ebx; uID
0x18000a28d  mov     rcx, r15; hInstance
0x18000a290  call    cs:__imp_LoadStringW
0x18000a296  mov     [rsp+288h+var_268], ebx
0x18000a29a  lea     rdx, [rsp+288h+var_268]
0x18000a29f  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a2a4  lea     rcx, [rsp+288h+Buffer]
0x18000a2a9  mov     rdx, rsi
0x18000a2ac  inc     rdx
0x18000a2af  cmp     [rcx+rdx*2], r13w
0x18000a2b4  jnz     short loc_18000A2AC
0x18000a2b6  cmp     rdx, [rax+18h]
0x18000a2ba  ja      short loc_18000A2EA
0x18000a2bc  cmp     qword ptr [rax+18h], 7
0x18000a2c1  jbe     short loc_18000A2C8
0x18000a2c3  mov     rdi, [rax]
0x18000a2c6  jmp     short loc_18000A2CB
0x18000a2c8  mov     rdi, rax
0x18000a2cb  mov     [rax+10h], rdx
0x18000a2cf  lea     rbx, [rdx+rdx]
0x18000a2d3  mov     r8, rbx; Size
0x18000a2d6  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a2db  mov     rcx, rdi; void *
0x18000a2de  call    memmove_0
0x18000a2e3  mov     [rbx+rdi], r13w
0x18000a2e8  jmp     short loc_18000A2F7
0x18000a2ea  lea     r9, [rsp+288h+Buffer]
0x18000a2ef  mov     rcx, rax
0x18000a2f2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a2f7  mov     r9d, 104h; cchBufferMax
0x18000a2fd  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a302  mov     ebx, 67h ; 'g'
0x18000a307  mov     edx, ebx; uID
0x18000a309  mov     rcx, r15; hInstance
0x18000a30c  call    cs:__imp_LoadStringW
0x18000a312  mov     [rsp+288h+var_268], ebx
0x18000a316  lea     rdx, [rsp+288h+var_268]
0x18000a31b  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a320  lea     rcx, [rsp+288h+Buffer]
0x18000a325  mov     rdx, rsi
0x18000a328  inc     rdx
0x18000a32b  cmp     [rcx+rdx*2], r13w
0x18000a330  jnz     short loc_18000A328
0x18000a332  cmp     rdx, [rax+18h]
0x18000a336  ja      short loc_18000A366
0x18000a338  cmp     qword ptr [rax+18h], 7
0x18000a33d  jbe     short loc_18000A344
0x18000a33f  mov     rdi, [rax]
0x18000a342  jmp     short loc_18000A347
0x18000a344  mov     rdi, rax
0x18000a347  mov     [rax+10h], rdx
0x18000a34b  lea     rbx, [rdx+rdx]
0x18000a34f  mov     r8, rbx; Size
0x18000a352  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a357  mov     rcx, rdi; void *
0x18000a35a  call    memmove_0
0x18000a35f  mov     [rbx+rdi], r13w
0x18000a364  jmp     short loc_18000A373
0x18000a366  lea     r9, [rsp+288h+Buffer]
0x18000a36b  mov     rcx, rax
0x18000a36e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a373  mov     r9d, 104h; cchBufferMax
0x18000a379  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a37e  mov     ebx, 68h ; 'h'
0x18000a383  mov     edx, ebx; uID
0x18000a385  mov     rcx, r15; hInstance
0x18000a388  call    cs:__imp_LoadStringW
0x18000a38e  mov     [rsp+288h+var_268], ebx
0x18000a392  lea     rdx, [rsp+288h+var_268]
0x18000a397  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a39c  lea     rcx, [rsp+288h+Buffer]
0x18000a3a1  mov     rdx, rsi
0x18000a3a4  inc     rdx
0x18000a3a7  cmp     [rcx+rdx*2], r13w
0x18000a3ac  jnz     short loc_18000A3A4
0x18000a3ae  cmp     rdx, [rax+18h]
0x18000a3b2  ja      short loc_18000A3E2
0x18000a3b4  cmp     qword ptr [rax+18h], 7
0x18000a3b9  jbe     short loc_18000A3C0
0x18000a3bb  mov     rdi, [rax]
0x18000a3be  jmp     short loc_18000A3C3
0x18000a3c0  mov     rdi, rax
0x18000a3c3  mov     [rax+10h], rdx
0x18000a3c7  lea     rbx, [rdx+rdx]
0x18000a3cb  mov     r8, rbx; Size
0x18000a3ce  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a3d3  mov     rcx, rdi; void *
0x18000a3d6  call    memmove_0
0x18000a3db  mov     [rbx+rdi], r13w
0x18000a3e0  jmp     short loc_18000A3EF
0x18000a3e2  lea     r9, [rsp+288h+Buffer]
0x18000a3e7  mov     rcx, rax
0x18000a3ea  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a3ef  mov     r9d, 104h; cchBufferMax
0x18000a3f5  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a3fa  mov     ebx, 69h ; 'i'
0x18000a3ff  mov     edx, ebx; uID
0x18000a401  mov     rcx, r15; hInstance
0x18000a404  call    cs:__imp_LoadStringW
0x18000a40a  mov     [rsp+288h+var_268], ebx
0x18000a40e  lea     rdx, [rsp+288h+var_268]
0x18000a413  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a418  lea     rcx, [rsp+288h+Buffer]
0x18000a41d  mov     rdx, rsi
0x18000a420  inc     rdx
0x18000a423  cmp     [rcx+rdx*2], r13w
0x18000a428  jnz     short loc_18000A420
0x18000a42a  cmp     rdx, [rax+18h]
0x18000a42e  ja      short loc_18000A45E
0x18000a430  cmp     qword ptr [rax+18h], 7
0x18000a435  jbe     short loc_18000A43C
0x18000a437  mov     rdi, [rax]
0x18000a43a  jmp     short loc_18000A43F
0x18000a43c  mov     rdi, rax
0x18000a43f  mov     [rax+10h], rdx
0x18000a443  lea     rbx, [rdx+rdx]
0x18000a447  mov     r8, rbx; Size
0x18000a44a  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a44f  mov     rcx, rdi; void *
0x18000a452  call    memmove_0
0x18000a457  mov     [rbx+rdi], r13w
0x18000a45c  jmp     short loc_18000A46B
0x18000a45e  lea     r9, [rsp+288h+Buffer]
0x18000a463  mov     rcx, rax
0x18000a466  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a46b  mov     r9d, 104h; cchBufferMax
0x18000a471  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a476  mov     ebx, 6Ah ; 'j'
0x18000a47b  mov     edx, ebx; uID
0x18000a47d  mov     rcx, r15; hInstance
0x18000a480  call    cs:__imp_LoadStringW
0x18000a486  mov     [rsp+288h+var_268], ebx
0x18000a48a  lea     rdx, [rsp+288h+var_268]
0x18000a48f  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a494  lea     rcx, [rsp+288h+Buffer]
0x18000a499  mov     rdx, rsi
0x18000a49c  inc     rdx
0x18000a49f  cmp     [rcx+rdx*2], r13w
0x18000a4a4  jnz     short loc_18000A49C
0x18000a4a6  cmp     rdx, [rax+18h]
0x18000a4aa  ja      short loc_18000A4DA
0x18000a4ac  cmp     qword ptr [rax+18h], 7
0x18000a4b1  jbe     short loc_18000A4B8
0x18000a4b3  mov     rdi, [rax]
0x18000a4b6  jmp     short loc_18000A4BB
0x18000a4b8  mov     rdi, rax
0x18000a4bb  mov     [rax+10h], rdx
0x18000a4bf  lea     rbx, [rdx+rdx]
0x18000a4c3  mov     r8, rbx; Size
0x18000a4c6  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a4cb  mov     rcx, rdi; void *
0x18000a4ce  call    memmove_0
0x18000a4d3  mov     [rbx+rdi], r13w
0x18000a4d8  jmp     short loc_18000A4E7
0x18000a4da  lea     r9, [rsp+288h+Buffer]
0x18000a4df  mov     rcx, rax
0x18000a4e2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a4e7  mov     r9d, 104h; cchBufferMax
0x18000a4ed  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a4f2  mov     ebx, 6Bh ; 'k'
0x18000a4f7  mov     edx, ebx; uID
0x18000a4f9  mov     rcx, r15; hInstance
0x18000a4fc  call    cs:__imp_LoadStringW
0x18000a502  mov     [rsp+288h+var_268], ebx
0x18000a506  lea     rdx, [rsp+288h+var_268]
0x18000a50b  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000a510  lea     rcx, [rsp+288h+Buffer]
0x18000a515  mov     rdx, rsi
0x18000a518  inc     rdx
0x18000a51b  cmp     [rcx+rdx*2], r13w
0x18000a520  jnz     short loc_18000A518
0x18000a522  cmp     rdx, [rax+18h]
0x18000a526  ja      short loc_18000A556
0x18000a528  cmp     qword ptr [rax+18h], 7
0x18000a52d  jbe     short loc_18000A534
0x18000a52f  mov     rdi, [rax]
0x18000a532  jmp     short loc_18000A537
0x18000a534  mov     rdi, rax
0x18000a537  mov     [rax+10h], rdx
0x18000a53b  lea     rbx, [rdx+rdx]
0x18000a53f  mov     r8, rbx; Size
0x18000a542  lea     rdx, [rsp+288h+Buffer]; Src
0x18000a547  mov     rcx, rdi; void *
0x18000a54a  call    memmove_0
0x18000a54f  mov     [rbx+rdi], r13w
0x18000a554  jmp     short loc_18000A563
0x18000a556  lea     r9, [rsp+288h+Buffer]
0x18000a55b  mov     rcx, rax
0x18000a55e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000a563  mov     r9d, 104h; cchBufferMax
0x18000a569  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000a56e  mov     ebx, 6Ch ; 'l'
0x18000a573  mov     edx, ebx; uID
0x18000a575  mov     rcx, r15; hInstance
0x18000a578  call    cs:__imp_LoadStringW
0x18000a57e  mov     [rsp+288h+var_268], ebx
  ... truncated ...
```
