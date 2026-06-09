# Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable(bool *,Windows::Compat::Appraiser::Table *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::TableCache *,ushort const *)

- ea: `0x1800b1734`
- end: `0x1800b239e`
- name: `?EvaluateTable@ConstraintTableQuery@Appraiser@Compat@Windows@@SAJPEA_NPEAVTable@234@PEAVIPropertyListEnumerator@234@2222PEAVTableCache@234@PEBG@Z`
- size: `3178`
- prototype: `__int64 __usercall@<rax>(bool *@<rcx>, struct Windows::Compat::Appraiser::Table *@<rdx>, struct Windows::Compat::Appraiser::IPropertyListEnumerator *@<r8>, struct Windows::Compat::Appraiser::IPropertyListEnumerator *@<r9>, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::TableCache *, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180061580`
- `0x180069cb4`
- `0x180069ed8`
- `0x1800b0bd8`
- `0x1800b128c`
- `0x1800b1474`
- `0x1800d5238`
- `0x1800db008`
- `0x1800db694`
- `0x1800dee34`
- `0x1800f8f4c`
- `0x18010d34c`
- `0x180207810`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180008a1c`
- `0x18000a5b8`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800b1080`
- `0x1800b128c`
- `0x1800b1734`
- `0x1800b24c8`
- `0x1800b258c`
- `0x1800b6030`
- `0x1800b62c0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800b2133`
- `KERNEL32!GetSystemTime` at `0x1800b2133`
- `KERNEL32!GetProcessHeap` at `0x1800b17c1`
- `KERNEL32!GetProcessHeap` at `0x1800b192d`
- `KERNEL32!GetProcessHeap` at `0x1800b17c1`
- `KERNEL32!GetProcessHeap` at `0x1800b192d`
- `KERNEL32!HeapFree` at `0x1800b1918`
- `KERNEL32!HeapFree` at `0x1800b2373`
- `KERNEL32!HeapFree` at `0x1800b1918`
- `KERNEL32!HeapFree` at `0x1800b2373`

## string_xrefs

- `0x1800b197f`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b19ce`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1a09`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1a44`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1a7f`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1ab6`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1b02`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1b4c`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1ce1`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1dc8`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1df0`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1f4f`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1ff0`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b2062`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b2220`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b2290`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b22bc`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b22f0`: `onecore\base\appcompat\appraiser\helpers\constrainttablequery.cpp`
- `0x1800b1978`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b19c7`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1a02`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1a3d`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1a78`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1aaf`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1b0e`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1b53`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1cf7`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1d3d`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1d6c`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b1fe9`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b2058`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b22b5`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b22e9`: `Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable`
- `0x1800b2048`: `Error cacheing table result: [0x%x].`
- `0x1800b22e2`: `Error cacheing table result: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable(
        bool *a1,
        struct Windows::Compat::Appraiser::Table *a2,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a3,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a4,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a5,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a6,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a7,
        struct Windows::Compat::Appraiser::TableCache *a8,
        wchar_t *a9)
{
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v9; // rbx
  struct Windows::Compat::Appraiser::TableCache *v12; // r14
  bool *v13; // r13
  bool *v14; // rdi
  int *v15; // r13
  int v16; // eax
  char v17; // dl
  int v18; // eax
  char v19; // dl
  int v20; // edi
  unsigned __int64 v21; // rax
  int v22; // ecx
  unsigned __int64 i; // rdi
  __int64 *v24; // rdx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  char *v29; // rdi
  __int64 v30; // r12
  bool ShouldStopEvaluating; // al
  unsigned __int64 v32; // r12
  int v33; // eax
  int v34; // eax
  int v35; // ebx
  volatile signed __int64 *v36; // rcx
  void **v37; // rdx
  int v38; // edi
  int v39; // r8d
  int v40; // r9d
  unsigned __int64 v41; // rax
  __int64 v42; // rax
  unsigned __int64 v43; // kr00_8
  int *v44; // rax
  char *v46; // [rsp+20h] [rbp-E0h]
  const char *String1; // [rsp+28h] [rbp-D8h]
  char *v48; // [rsp+30h] [rbp-D0h]
  char *v49; // [rsp+30h] [rbp-D0h]
  __int64 v50; // [rsp+38h] [rbp-C8h]
  bool *v51; // [rsp+60h] [rbp-A0h]
  bool *v52; // [rsp+68h] [rbp-98h]
  int v53; // [rsp+70h] [rbp-90h] BYREF
  Windows::Compat::Appraiser::TableCache *v54; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h]
  bool *v56; // [rsp+88h] [rbp-78h]
  bool *v57; // [rsp+90h] [rbp-70h]
  bool *v58; // [rsp+98h] [rbp-68h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v60; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v61; // [rsp+B0h] [rbp-50h]
  int v62[2]; // [rsp+B8h] [rbp-48h]
  int v63[2]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v64; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v65; // [rsp+D0h] [rbp-30h] BYREF
  const char *v66; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE hHeap[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v68; // [rsp+F0h] [rbp-10h]
  LPVOID lpMem[2]; // [rsp+100h] [rbp+0h]
  unsigned __int64 v70; // [rsp+110h] [rbp+10h]
  unsigned __int64 v71; // [rsp+118h] [rbp+18h]
  int v72[2]; // [rsp+120h] [rbp+20h]
  int v73[2]; // [rsp+128h] [rbp+28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+130h] [rbp+30h] BYREF
  __int64 v75; // [rsp+140h] [rbp+40h]
  int v76[4]; // [rsp+150h] [rbp+50h] BYREF
  char v77[144]; // [rsp+160h] [rbp+60h] BYREF
  char v78[144]; // [rsp+1F0h] [rbp+F0h] BYREF

  v75 = -2;
  *(_QWORD *)v76 = a4;
  v9 = a3;
  *(_QWORD *)v62 = a3;
  *(_QWORD *)v72 = a5;
  *(_QWORD *)v63 = a6;
  *(_QWORD *)v73 = a7;
  v12 = a8;
  v54 = a8;
  v64 = a9;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v68 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v53 = 0;
  *a1 = 0;
  if ( a8 && Windows::Compat::Appraiser::TableCache::GetTableResult(a8, a1, a2) )
  {
    LODWORD(v9) = 0;
    goto LABEL_132;
  }
  v70 = *((_QWORD *)a2 + 19);
  v59 = *((_QWORD *)a2 + 31);
  v60 = *((_QWORD *)a2 + 37);
  v61 = *((_QWORD *)a2 + 43);
  v71 = *((_QWORD *)a2 + 49);
  v65 = *((_QWORD *)a2 + 55);
  Block = operator new[](v70, (const struct std::nothrow_t *)&std::nothrow);
  v56 = (bool *)operator new[](v59, (const struct std::nothrow_t *)&std::nothrow);
  v57 = (bool *)operator new[](v60, (const struct std::nothrow_t *)&std::nothrow);
  v58 = (bool *)operator new[](v61, (const struct std::nothrow_t *)&std::nothrow);
  v13 = (bool *)operator new[](v71, (const struct std::nothrow_t *)&std::nothrow);
  v51 = v13;
  v14 = (bool *)operator new[](v65, (const struct std::nothrow_t *)&std::nothrow);
  v52 = v14;
  if ( Block )
  {
    if ( !v56 || !v57 || !v58 || !v13 || !v14 )
    {
      LODWORD(v9) = -2147024882;
LABEL_121:
      operator delete(Block);
      goto LABEL_122;
    }
    if ( lpMem[1] )
      HeapFree(hHeap[0], 0, lpMem[1]);
    hHeap[0] = GetProcessHeap();
    lpMem[0] = (LPVOID)16;
    v68 = 0;
    lpMem[1] = 0;
    hHeap[1] = (HANDLE)8;
    v66 = 0;
    v15 = 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x94u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
        "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
        "Failed to initialize RtlArray: [0x%x].",
        0);
    if ( !*((_BYTE *)a2 + 129) )
      goto LABEL_49;
    if ( v9 )
    {
      v16 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, HANDLE *))(*(_QWORD *)v9 + 64LL))(
              v9,
              hHeap);
      LODWORD(v9) = v16;
      if ( v16 < 0 )
      {
        LODWORD(v48) = v16;
        String1 = "Error adding unique ordinals: [0x%x].";
        LODWORD(v46) = v16;
        v17 = -103;
LABEL_39:
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v17,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
          "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
          v46,
          (int)String1,
          v48);
LABEL_119:
        v14 = v52;
LABEL_120:
        v13 = v51;
        goto LABEL_121;
      }
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x99u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
        "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
        "Error adding unique ordinals: [0x%x].",
        (_DWORD)v9);
    if ( *(_QWORD *)v76 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)v76 + 64LL))(*(_QWORD *)v76, hHeap);
      LODWORD(v9) = v18;
      if ( v18 < 0 )
      {
        v19 = -100;
        goto LABEL_42;
      }
    }
    else
    {
      LODWORD(v9) = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9Cu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
        "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
        "Error adding unique ordinals: [0x%x].",
        (_DWORD)v9);
    if ( *(_QWORD *)v72 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)v72 + 64LL))(*(_QWORD *)v72, hHeap);
      LODWORD(v9) = v18;
      if ( v18 < 0 )
      {
        v19 = -97;
        goto LABEL_42;
      }
    }
    else
    {
      LODWORD(v9) = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9Fu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
        "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
        "Error adding unique ordinals: [0x%x].",
        (_DWORD)v9);
    if ( *(_QWORD *)v63 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)v63 + 64LL))(*(_QWORD *)v63, hHeap);
      LODWORD(v9) = v18;
      if ( v18 < 0 )
      {
        v19 = -94;
        goto LABEL_42;
      }
    }
    else
    {
      LODWORD(v9) = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA2u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
        "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
        "Error adding unique ordinals: [0x%x].",
        (_DWORD)v9);
    if ( !a7 )
    {
      LODWORD(v9) = 0;
      goto LABEL_34;
    }
    v18 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, HANDLE *))(*(_QWORD *)a7 + 64LL))(
            a7,
            hHeap);
    LODWORD(v9) = v18;
    if ( v18 >= 0 )
    {
LABEL_34:
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xA5u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
          "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
          "Error adding unique ordinals: [0x%x].",
          (_DWORD)v9);
      v15 = &v53;
      while ( (unsigned __int64)v66 < (unsigned __int64)v68 )
      {
        v41 = (unsigned __int64)v66++;
        *(_QWORD *)&SystemTime.wYear = 0;
        v43 = v41;
        v42 = (unsigned __int64)hHeap[1] * v41;
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v43) || (v44 = (int *)((char *)lpMem[1] + v42), v44 < lpMem[1]) )
          v44 = 0;
        v53 = *v44;
        v9 = *(struct Windows::Compat::Appraiser::IPropertyListEnumerator **)v62;
LABEL_49:
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(Block, v70, (char *)a2 + 136);
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(v56, v59, (char *)a2 + 232);
        v20 = (_DWORD)a2 + 280;
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(v57, v60, (char *)a2 + 280);
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(v58, v61, (char *)a2 + 328);
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(v51, v71, (char *)a2 + 376);
        Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(v52, v65, (char *)a2 + 424);
        if ( v9 )
        {
          v21 = *((_QWORD *)a2 + 25);
          if ( v21 )
          {
            for ( i = 0; i < v21; ++i )
            {
              v24 = 0;
              if ( i < v21 )
              {
                *(_QWORD *)&SystemTime.wYear = 0;
                v25 = *((_QWORD *)a2 + 24) * i;
                if ( !is_mul_ok(*((_QWORD *)a2 + 24), i)
                  || (v26 = *((_QWORD *)a2 + 28), v24 = (__int64 *)(v25 + v26), v25 + v26 < v26) )
                {
                  v24 = 0;
                }
              }
              v27 = *v24;
              if ( !*(_QWORD *)(*v24 + 152) )
              {
                v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v62 + 40LL))(
                        *(_QWORD *)v62,
                        *(_QWORD *)(v27 + 144));
                if ( !v28 )
                  goto LABEL_51;
                *(_QWORD *)(v27 + 152) = v28;
              }
              v21 = *((_QWORD *)a2 + 25);
            }
            v22 = 0;
          }
          else
          {
LABEL_51:
            v22 = 1;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xD7u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Failed to resolve variable constraints: [0x%x].",
              v22);
          LODWORD(v9) = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstProperties(
                          (int)Block,
                          v70,
                          v62[0],
                          (int)a2 + 136,
                          (__int64)v15,
                          v64);
          if ( (int)v9 < 0 )
          {
            LODWORD(v48) = (_DWORD)v9;
            String1 = "Failed to enumerate properties and evaluate constraints: [0x%x].";
            LODWORD(v46) = (_DWORD)v9;
            v17 = -33;
            goto LABEL_39;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xDFu,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Failed to enumerate properties and evaluate constraints: [0x%x].",
              (_DWORD)v9);
          v20 = (_DWORD)a2 + 280;
        }
        if ( Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(a1, a2, (bool *)Block, v70) )
          goto LABEL_104;
        if ( *(_QWORD *)v76 )
        {
          LODWORD(v9) = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstProperties(
                          (int)v56,
                          v59,
                          v76[0],
                          (int)a2 + 232,
                          (__int64)v15,
                          0);
          if ( (int)v9 < 0 )
          {
            LODWORD(v48) = (_DWORD)v9;
            String1 = "Failed to enumerate properties and evaluate constraints: [0x%x].";
            LODWORD(v46) = (_DWORD)v9;
            v17 = -12;
            goto LABEL_39;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xF4u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Failed to enumerate properties and evaluate constraints: [0x%x].",
              (_DWORD)v9);
        }
        if ( Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(a1, a2, v56, v59) )
          goto LABEL_104;
        if ( *(_QWORD *)v72 )
        {
          LODWORD(v9) = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstProperties(
                          (int)v57,
                          v60,
                          v72[0],
                          v20,
                          (__int64)v15,
                          0);
          if ( (int)v9 < 0 )
          {
            LODWORD(v48) = (_DWORD)v9;
            String1 = "Failed to enumerate properties and evaluate constraints: [0x%x].";
            LODWORD(v46) = (_DWORD)v9;
            v17 = 9;
            goto LABEL_39;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x109u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Failed to enumerate properties and evaluate constraints: [0x%x].",
              (_DWORD)v9);
        }
        if ( Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(a1, a2, v57, v60) )
          goto LABEL_104;
        v29 = *(char **)v63;
        if ( *(_QWORD *)v63 )
        {
          LODWORD(v9) = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstProperties(
                          (int)v58,
                          v61,
                          v63[0],
                          (int)a2 + 328,
                          (__int64)v15,
                          0);
          if ( (int)v9 < 0 )
          {
            LODWORD(v48) = (_DWORD)v9;
            String1 = "Failed to enumerate properties and evaluate constraints: [0x%x].";
            LODWORD(v46) = (_DWORD)v9;
            v17 = 30;
            goto LABEL_39;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x11Eu,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Failed to enumerate properties and evaluate constraints: [0x%x].",
              (_DWORD)v9);
        }
        if ( Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(a1, a2, v58, v61) )
        {
LABEL_104:
          v12 = v54;
        }
        else
        {
          v30 = *(_QWORD *)v73;
          if ( *(_QWORD *)v73 )
          {
            LODWORD(v9) = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstProperties(
                            (int)v51,
                            v71,
                            v73[0],
                            (int)a2 + 376,
                            (__int64)v15,
                            0);
            if ( (int)v9 < 0 )
            {
              LODWORD(v48) = (_DWORD)v9;
              String1 = "Failed to enumerate properties and evaluate constraints: [0x%x].";
              LODWORD(v46) = (_DWORD)v9;
              v17 = 51;
              goto LABEL_39;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x133u,
                "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
                "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
                "Failed to enumerate properties and evaluate constraints: [0x%x].",
                (_DWORD)v9);
          }
          ShouldStopEvaluating = Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(
                                   a1,
                                   a2,
                                   v51,
                                   v71);
          v12 = v54;
          if ( !ShouldStopEvaluating )
          {
            v50 = v30;
            v49 = v29;
            v32 = v65;
            v14 = v52;
            v33 = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateConstraintsAgainstTables(
                    v52,
                    v65,
                    (char *)a2 + 424,
                    *(_QWORD *)v62,
                    *(_QWORD *)v76,
                    *(_QWORD *)v72,
                    v49,
                    v50,
                    v54,
                    v64);
            LODWORD(v9) = v33;
            if ( v33 < 0 )
            {
              LODWORD(v48) = v33;
              LODWORD(v46) = v33;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                75,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
                "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
                v46,
                (int)"Failed to evaluate table reference constraints: [0x%x].",
                v48);
              goto LABEL_120;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x14Bu,
                "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
                "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
                "Failed to evaluate table reference constraints: [0x%x].",
                v33);
            if ( !Windows::Compat::Appraiser::ConstraintTableQuery::ShouldStopEvaluating(a1, a2, v52, v32) )
            {
              *a1 = *((_BYTE *)a2 + 128);
              break;
            }
          }
        }
      }
      if ( v12 )
      {
        v34 = Windows::Compat::Appraiser::TableCache::Insert(v12, *a1, a2);
        v35 = v34;
        if ( v34 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x16Cu,
              "onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
              "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
              "Error cacheing table result: [0x%x].",
              v34);
        }
        else
        {
          LODWORD(v48) = v34;
          LODWORD(v46) = v34;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            108,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
            "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
            v46,
            (int)"Error cacheing table result: [0x%x].",
            v48);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v77);
          v36 = (volatile signed __int64 *)v77;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v36 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v36,
            _InterlockedExchangeAdd64(v36 + 17, 0),
            v78);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v37);
          v38 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            *(_QWORD *)v73 = v78;
            v53 = v35;
            v66 = "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable";
            v65 = (unsigned __int64)"onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp";
            LODWORD(v54) = 364;
            v64 = (wchar_t *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            *(struct _SYSTEMTIME *)v76 = SystemTime;
            *(_QWORD *)v63 = v76;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v38,
              (unsigned int)&unk_1802A26B1,
              v39,
              v40,
              (__int64)v63,
              (__int64)&v64,
              (__int64)&v54,
              (__int64)&v65,
              (__int64)&v66,
              (__int64)&v53,
              (__int64)v73);
          }
        }
      }
      LODWORD(v9) = 0;
      goto LABEL_119;
    }
    v19 = -91;
LABEL_42:
    LODWORD(v48) = v18;
    LODWORD(v46) = v18;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v19,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\constrainttablequery.cpp",
      "Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable",
      v46,
      (int)"Error adding unique ordinals: [0x%x].",
      v48);
    goto LABEL_119;
  }
  LODWORD(v9) = -2147024882;
LABEL_122:
  if ( v56 )
    operator delete(v56);
  if ( v57 )
    operator delete(v57);
  if ( v58 )
    operator delete(v58);
  if ( v13 )
    operator delete(v13);
  if ( v14 )
    operator delete(v14);
LABEL_132:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b1734  push    rbp
0x1800b1736  push    rbx
0x1800b1737  push    rsi
0x1800b1738  push    rdi
0x1800b1739  push    r12
0x1800b173b  push    r13
0x1800b173d  push    r14
0x1800b173f  push    r15
0x1800b1741  lea     rbp, [rsp-198h]
0x1800b1749  sub     rsp, 298h
0x1800b1750  mov     [rbp+1D0h+var_190], 0FFFFFFFFFFFFFFFEh
0x1800b1758  mov     rax, cs:__security_cookie
0x1800b175f  xor     rax, rsp
0x1800b1762  mov     [rbp+1D0h+var_50], rax
0x1800b1769  mov     qword ptr [rbp+1D0h+var_180], r9
0x1800b176d  mov     rbx, r8
0x1800b1770  mov     qword ptr [rbp+1D0h+var_218], rbx
0x1800b1774  mov     rsi, rdx
0x1800b1777  mov     r15, rcx
0x1800b177a  mov     rax, [rbp+1D0h+arg_20]
0x1800b1781  mov     qword ptr [rbp+1D0h+var_1B0], rax
0x1800b1785  mov     rax, [rbp+1D0h+arg_28]
0x1800b178c  mov     qword ptr [rbp+1D0h+var_210], rax
0x1800b1790  mov     r12, [rbp+1D0h+arg_30]
0x1800b1797  mov     qword ptr [rbp+1D0h+var_1A8], r12
0x1800b179b  mov     r14, [rbp+1D0h+arg_38]
0x1800b17a2  mov     [rsp+2D0h+var_258], r14
0x1800b17a7  mov     rax, [rbp+1D0h+arg_40]
0x1800b17ae  mov     [rbp+1D0h+var_208], rax
0x1800b17b2  xorps   xmm0, xmm0
0x1800b17b5  movups  xmmword ptr [rbp+1D0h+hHeap], xmm0
0x1800b17b9  movups  [rbp+1D0h+var_1E0], xmm0
0x1800b17bd  movups  xmmword ptr [rbp+1D0h+lpMem], xmm0
0x1800b17c1  call    cs:__imp_GetProcessHeap
0x1800b17c7  mov     [rbp+1D0h+hHeap], rax
0x1800b17cb  mov     [rbp+1D0h+lpMem], 10h
0x1800b17d3  xorps   xmm0, xmm0
0x1800b17d6  movdqu  [rbp+1D0h+var_1E0], xmm0
0x1800b17db  mov     [rbp+1D0h+lpMem+8], 0
0x1800b17e3  mov     [rbp+1D0h+hHeap+8], 8
0x1800b17eb  mov     [rsp+2D0h+var_260], 0
0x1800b17f3  mov     byte ptr [r15], 0
0x1800b17f7  test    r14, r14
0x1800b17fa  jz      short loc_1800B1815
0x1800b17fc  mov     r8, rsi; struct Windows::Compat::Appraiser::Table *
0x1800b17ff  mov     rdx, r15; bool *
0x1800b1802  mov     rcx, r14; this
0x1800b1805  call    ?GetTableResult@TableCache@Appraiser@Compat@Windows@@QEAA_NAEA_NPEBVTable@234@@Z; Windows::Compat::Appraiser::TableCache::GetTableResult(bool &,Windows::Compat::Appraiser::Table const *)
0x1800b180a  test    al, al
0x1800b180c  jz      short loc_1800B1815
0x1800b180e  xor     ebx, ebx
0x1800b1810  jmp     loc_1800B2364
0x1800b1815  mov     rcx, [rsi+98h]; unsigned __int64
0x1800b181c  mov     [rbp+1D0h+var_1C0], rcx
0x1800b1820  mov     rax, [rsi+0F8h]
0x1800b1827  mov     [rbp+1D0h+var_230], rax
0x1800b182b  mov     rax, [rsi+128h]
0x1800b1832  mov     [rbp+1D0h+var_228], rax
0x1800b1836  mov     rax, [rsi+158h]
0x1800b183d  mov     [rbp+1D0h+var_220], rax
0x1800b1841  mov     r13, [rsi+188h]
0x1800b1848  mov     [rbp+1D0h+var_1B8], r13
0x1800b184c  mov     rdi, [rsi+1B8h]
0x1800b1853  mov     [rbp+1D0h+var_200], rdi
0x1800b1857  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b185e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b1863  mov     [rbp+1D0h+Block], rax
0x1800b1867  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b186e  mov     rcx, [rbp+1D0h+var_230]; unsigned __int64
0x1800b1872  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b1877  mov     [rbp+1D0h+var_248], rax
0x1800b187b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b1882  mov     rcx, [rbp+1D0h+var_228]; unsigned __int64
0x1800b1886  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b188b  mov     [rbp+1D0h+var_240], rax
0x1800b188f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b1896  mov     rcx, [rbp+1D0h+var_220]; unsigned __int64
0x1800b189a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b189f  mov     [rbp+1D0h+var_238], rax
0x1800b18a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b18aa  mov     rcx, r13; unsigned __int64
0x1800b18ad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b18b2  mov     r13, rax
0x1800b18b5  mov     [rsp+2D0h+var_270], rax
0x1800b18ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b18c1  mov     rcx, rdi; unsigned __int64
0x1800b18c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b18c9  mov     rdi, rax
0x1800b18cc  mov     [rsp+2D0h+var_268], rax
0x1800b18d1  xor     eax, eax
0x1800b18d3  cmp     [rbp+1D0h+Block], rax
0x1800b18d7  jnz     short loc_1800B18E3
0x1800b18d9  mov     ebx, 8007000Eh
0x1800b18de  jmp     loc_1800B2316
0x1800b18e3  cmp     [rbp+1D0h+var_248], rax
0x1800b18e7  jnz     short loc_1800B18F3
0x1800b18e9  mov     ebx, 8007000Eh
0x1800b18ee  jmp     loc_1800B230D
0x1800b18f3  cmp     [rbp+1D0h+var_240], rax
0x1800b18f7  jz      short loc_1800B18E9
0x1800b18f9  cmp     [rbp+1D0h+var_238], rax
0x1800b18fd  jz      short loc_1800B18E9
0x1800b18ff  test    r13, r13
0x1800b1902  jz      short loc_1800B18E9
0x1800b1904  test    rdi, rdi
0x1800b1907  jz      short loc_1800B18E9
0x1800b1909  mov     r8, [rbp+1D0h+lpMem+8]; lpMem
0x1800b190d  test    r8, r8
0x1800b1910  jz      short loc_1800B191E
0x1800b1912  xor     edx, edx; dwFlags
0x1800b1914  mov     rcx, [rbp+1D0h+hHeap]; hHeap
0x1800b1918  call    cs:__imp_HeapFree
0x1800b191e  xorps   xmm0, xmm0
0x1800b1921  movups  xmmword ptr [rbp+1D0h+hHeap], xmm0
0x1800b1925  movups  [rbp+1D0h+var_1E0], xmm0
0x1800b1929  movups  xmmword ptr [rbp+1D0h+lpMem], xmm0
0x1800b192d  call    cs:__imp_GetProcessHeap
0x1800b1933  mov     [rbp+1D0h+hHeap], rax
0x1800b1937  mov     [rbp+1D0h+lpMem], 10h
0x1800b193f  xorps   xmm0, xmm0
0x1800b1942  movdqu  [rbp+1D0h+var_1E0], xmm0
0x1800b1947  mov     [rbp+1D0h+lpMem+8], 0
0x1800b194f  mov     [rbp+1D0h+hHeap+8], 8
0x1800b1957  mov     [rbp+1D0h+var_1F8], 0
0x1800b195f  xor     r13d, r13d
0x1800b1962  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b1968  test    al, 1
0x1800b196a  jz      short loc_1800B1990
0x1800b196c  mov     dword ptr [rsp+2D0h+var_2B0], r13d
0x1800b1971  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800b1978  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b197f  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1986  mov     ecx, 94h; unsigned int
0x1800b198b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b1990  cmp     [rsi+81h], r13b
0x1800b1997  jz      loc_1800B1BCD
0x1800b199d  test    rbx, rbx
0x1800b19a0  jnz     loc_1800B1AD1
0x1800b19a6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b19ac  mov     r13d, 1
0x1800b19b2  and     eax, r13d
0x1800b19b5  lea     rdi, aErrorAddingUni; "Error adding unique ordinals: [0x%x]."
0x1800b19bc  test    al, al
0x1800b19be  jz      short loc_1800B19DF
0x1800b19c0  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x1800b19c4  mov     r9, rdi; char *
0x1800b19c7  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b19ce  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b19d5  mov     ecx, 99h; unsigned int
0x1800b19da  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b19df  mov     rcx, qword ptr [rbp+1D0h+var_180]
0x1800b19e3  test    rcx, rcx
0x1800b19e6  jnz     loc_1800B1B24
0x1800b19ec  xor     ebx, ebx
0x1800b19ee  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b19f4  and     eax, r13d
0x1800b19f7  test    al, al
0x1800b19f9  jz      short loc_1800B1A1A
0x1800b19fb  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x1800b19ff  mov     r9, rdi; char *
0x1800b1a02  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1a09  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1a10  mov     ecx, 9Ch; unsigned int
0x1800b1a15  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b1a1a  mov     rcx, qword ptr [rbp+1D0h+var_1B0]
0x1800b1a1e  test    rcx, rcx
0x1800b1a21  jnz     loc_1800B1B63
0x1800b1a27  xor     ebx, ebx
0x1800b1a29  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b1a2f  and     eax, r13d
0x1800b1a32  test    al, al
0x1800b1a34  jz      short loc_1800B1A55
0x1800b1a36  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x1800b1a3a  mov     r9, rdi; char *
0x1800b1a3d  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1a44  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1a4b  mov     ecx, 9Fh; unsigned int
0x1800b1a50  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b1a55  mov     rcx, qword ptr [rbp+1D0h+var_210]
0x1800b1a59  test    rcx, rcx
0x1800b1a5c  jnz     loc_1800B1B84
0x1800b1a62  xor     ebx, ebx
0x1800b1a64  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b1a6a  and     eax, r13d
0x1800b1a6d  test    al, al
0x1800b1a6f  jz      short loc_1800B1A90
0x1800b1a71  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x1800b1a75  mov     r9, rdi; char *
0x1800b1a78  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1a7f  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1a86  mov     ecx, 0A2h; unsigned int
0x1800b1a8b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b1a90  test    r12, r12
0x1800b1a93  jnz     loc_1800B1BA5
0x1800b1a99  xor     ebx, ebx
0x1800b1a9b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b1aa1  and     eax, r13d
0x1800b1aa4  test    al, al
0x1800b1aa6  jz      short loc_1800B1AC7
0x1800b1aa8  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x1800b1aac  mov     r9, rdi; char *
0x1800b1aaf  lea     r8, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1ab6  lea     rdx, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1abd  mov     ecx, 0A5h; unsigned int
0x1800b1ac2  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b1ac7  lea     r13, [rsp+2D0h+var_260]
0x1800b1acc  jmp     loc_1800B21A4
0x1800b1ad1  mov     rax, [rbx]
0x1800b1ad4  lea     rdx, [rbp+1D0h+hHeap]
0x1800b1ad8  mov     rcx, rbx
0x1800b1adb  mov     rax, [rax+40h]
0x1800b1adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ae4  mov     ebx, eax
0x1800b1ae6  test    eax, eax
0x1800b1ae8  jns     loc_1800B19A6
0x1800b1aee  mov     dword ptr [rsp+2D0h+var_2A0], eax; char *
0x1800b1af2  lea     rdi, aErrorAddingUni; "Error adding unique ordinals: [0x%x]."
0x1800b1af9  mov     [rsp+2D0h+String1], rdi; int
0x1800b1afe  mov     dword ptr [rsp+2D0h+var_2B0], eax; char *
0x1800b1b02  lea     r8, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1b09  mov     edx, 99h; bool
0x1800b1b0e  lea     r9, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1b15  mov     ecx, 1; this
0x1800b1b1a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800b1b1f  jmp     loc_1800B2303
0x1800b1b24  mov     rax, [rcx]
0x1800b1b27  lea     rdx, [rbp+1D0h+hHeap]
0x1800b1b2b  mov     rax, [rax+40h]
0x1800b1b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b34  mov     ebx, eax
0x1800b1b36  test    eax, eax
0x1800b1b38  jns     loc_1800B19EE
0x1800b1b3e  mov     edx, 9Ch
0x1800b1b43  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x1800b1b47  mov     [rsp+2D0h+String1], rdi
0x1800b1b4c  lea     r8, aOnecoreBaseApp_74; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b1b53  lea     r9, aWindowsCompatA_427; "Windows::Compat::Appraiser::ConstraintT"...
0x1800b1b5a  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x1800b1b5e  mov     ecx, r13d
0x1800b1b61  jmp     short loc_1800B1B1A
0x1800b1b63  mov     rax, [rcx]
0x1800b1b66  lea     rdx, [rbp+1D0h+hHeap]
0x1800b1b6a  mov     rax, [rax+40h]
0x1800b1b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b73  mov     ebx, eax
0x1800b1b75  test    eax, eax
0x1800b1b77  jns     loc_1800B1A29
0x1800b1b7d  mov     edx, 9Fh
0x1800b1b82  jmp     short loc_1800B1B43
0x1800b1b84  mov     rax, [rcx]
0x1800b1b87  lea     rdx, [rbp+1D0h+hHeap]
0x1800b1b8b  mov     rax, [rax+40h]
0x1800b1b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b94  mov     ebx, eax
0x1800b1b96  test    eax, eax
0x1800b1b98  jns     loc_1800B1A64
0x1800b1b9e  mov     edx, 0A2h
0x1800b1ba3  jmp     short loc_1800B1B43
0x1800b1ba5  mov     rax, [r12]
0x1800b1ba9  lea     rdx, [rbp+1D0h+hHeap]
0x1800b1bad  mov     rcx, r12
0x1800b1bb0  mov     rax, [rax+40h]
0x1800b1bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1bb9  mov     ebx, eax
0x1800b1bbb  test    eax, eax
0x1800b1bbd  jns     loc_1800B1A9B
0x1800b1bc3  mov     edx, 0A5h
0x1800b1bc8  jmp     loc_1800B1B43
0x1800b1bcd  lea     r14, [rsi+88h]
0x1800b1bd4  mov     r8, r14
0x1800b1bd7  mov     rdx, [rbp+1D0h+var_1C0]
0x1800b1bdb  mov     rcx, [rbp+1D0h+Block]
0x1800b1bdf  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1be4  lea     r12, [rsi+0E8h]
0x1800b1beb  mov     r8, r12
0x1800b1bee  mov     rdx, [rbp+1D0h+var_230]
0x1800b1bf2  mov     rcx, [rbp+1D0h+var_248]
0x1800b1bf6  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1bfb  lea     rdi, [rsi+118h]
0x1800b1c02  mov     r8, rdi
0x1800b1c05  mov     rdx, [rbp+1D0h+var_228]
0x1800b1c09  mov     rcx, [rbp+1D0h+var_240]
0x1800b1c0d  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1c12  lea     r8, [rsi+148h]
0x1800b1c19  mov     rdx, [rbp+1D0h+var_220]
0x1800b1c1d  mov     rcx, [rbp+1D0h+var_238]
0x1800b1c21  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1c26  lea     r8, [rsi+178h]
0x1800b1c2d  mov     rdx, [rbp+1D0h+var_1B8]
0x1800b1c31  mov     rcx, [rsp+2D0h+var_270]
0x1800b1c36  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1c3b  lea     r8, [rsi+1A8h]
0x1800b1c42  mov     rdx, [rbp+1D0h+var_200]
0x1800b1c46  mov     rcx, [rsp+2D0h+var_268]
0x1800b1c4b  call    ?InitializeResults@ConstraintTableQuery@Appraiser@Compat@Windows@@SAXPEA_N_KPEAV?$RtlArray@PEAUConstraint@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::ConstraintTableQuery::InitializeResults(bool *,unsigned __int64,RtlArray<Windows::Compat::Appraiser::Constraint *> *)
0x1800b1c50  test    rbx, rbx
0x1800b1c53  jz      loc_1800B1D6C
0x1800b1c59  mov     rax, [rsi+0C8h]
0x1800b1c60  test    rax, rax
0x1800b1c63  jnz     short loc_1800B1C6C
  ... truncated ...
```
