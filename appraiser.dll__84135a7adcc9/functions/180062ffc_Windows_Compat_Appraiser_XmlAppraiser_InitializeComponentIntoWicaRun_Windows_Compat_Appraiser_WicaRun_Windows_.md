# Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun(Windows::Compat::Appraiser::WicaRun *,Windows::Compat::Appraiser::RunInfoData *,Windows::Compat::Appraiser::ComponentInfo *,Windows::Compat::Appraiser::RunInfoDataStruct *,void *)

- ea: `0x180062ffc`
- end: `0x180063a69`
- name: `?InitializeComponentIntoWicaRun@XmlAppraiser@Appraiser@Compat@Windows@@AEAAJPEAUWicaRun@234@PEAVRunInfoData@234@PEAUComponentInfo@234@PEAURunInfoDataStruct@234@PEAX@Z`
- size: `2669`
- prototype: `__int64 __usercall@<rax>(Windows::Compat::Appraiser::XmlAppraiser *__hidden this@<rcx>, struct Windows::Compat::Appraiser::WicaRun *@<rdx>, struct Windows::Compat::Appraiser::RunInfoData *@<r8>, struct Windows::Compat::Appraiser::ComponentInfo *@<r9>, struct Windows::Compat::Appraiser::RunInfoDataStruct *, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180063c20`

## callees

- `0x180008a1c`
- `0x18000a594`
- `0x18000a5b8`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18006122c`
- `0x180061580`
- `0x180062ffc`
- `0x180063a70`
- `0x1800648ec`
- `0x18006c818`
- `0x18006cdd0`
- `0x18006cf14`
- `0x18006d2e4`
- `0x18020d728`
- `0x1802174cc`
- `0x18021f010`

## string_xrefs

- `0x1800630a8`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006315b`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063226`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800632d9`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800633d4`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063486`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006353c`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006359e`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006364d`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063703`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063757`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006380d`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006388f`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063919`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800639bb`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063a45`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006331d`: `DecisionMakerComponent`
- `0x18006309c`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006314f`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006321a`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x1800632cd`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x1800633c8`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006347a`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063548`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063592`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063641`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006370f`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006374b`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063801`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006389a`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063924`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x1800639af`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x180063a39`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun`
- `0x18006394f`: `CacheComponent`
- `0x1800638cc`: `ComponentStatus`
- `0x1800638f1`: `Error initializing ComponentStatus: [0x%x].`
- `0x18006390d`: `Error initializing ComponentStatus: [0x%x].`
- `0x180063989`: `Error adding custom component: [0x%x].`
- `0x1800639a4`: `Error adding custom component: [0x%x].`
- `0x180063a13`: `Error adding custom component: [0x%x].`
- `0x180063a2e`: `Error adding custom component: [0x%x].`
- `0x1800639d3`: `TelemetryComponent`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun(
        Windows::Compat::Appraiser::XmlAppraiser *this,
        struct Windows::Compat::Appraiser::WicaRun *a2,
        struct Windows::Compat::Appraiser::RunInfoData *a3,
        struct Windows::Compat::Appraiser::ComponentInfo *a4,
        struct Windows::Compat::Appraiser::RunInfoDataStruct *a5,
        HANDLE hTransaction)
{
  const wchar_t *v6; // rbx
  struct Windows::Compat::Appraiser::IInventory *InventoryInstance; // rax
  struct Windows::Compat::Appraiser::IOutputter *v12; // r14
  int v13; // ebx
  char v14; // dl
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  _QWORD *v17; // rsi
  unsigned __int64 i; // r8
  void *v19; // rcx
  struct IDataSource *DataSourceInstance; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rax
  _QWORD *v23; // rsi
  unsigned __int64 j; // r8
  void *v25; // rcx
  Windows::Compat::Appraiser::DecisionTableQuery *v26; // rax
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rax
  _QWORD *v29; // rsi
  unsigned __int64 k; // rdx
  void *v31; // rcx
  struct Windows::Compat::Appraiser::IDecisionAggregator *DecisionAggregatorInstance; // rax
  __int64 v33; // rax
  struct Windows::Compat::Appraiser::IOutputter *v34; // rcx
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rax
  _QWORD *v37; // rsi
  unsigned __int64 m; // r8
  void *v39; // rcx
  struct Windows::Compat::Appraiser::IOutputter *OutputterInstance; // rax
  struct Windows::Compat::Appraiser::IOutputter *v41; // r15
  int v42; // eax
  unsigned __int64 v43; // rbx
  unsigned __int64 v44; // rax
  _QWORD *v45; // rsi
  unsigned __int64 n; // r8
  void *v47; // rcx
  unsigned int v48; // r8d
  const char *v49; // r9
  char v50; // dl
  const char *v51; // r9
  unsigned int v52; // ecx
  int v53; // eax
  struct Windows::Compat::Appraiser::RunInfoDataStruct *v55; // [rsp+20h] [rbp-58h]
  struct Windows::Compat::Appraiser::RunInfoDataStruct *v56; // [rsp+28h] [rbp-50h]
  char *v57; // [rsp+30h] [rbp-48h]

  v6 = (const wchar_t *)*((_QWORD *)a4 + 1);
  if ( !wcscmp_0(v6, L"Inventory") )
  {
    InventoryInstance = Windows::Compat::Appraiser::AllComponents::CreateInventoryInstance(*(wchar_t **)a4);
    v12 = InventoryInstance;
    if ( !InventoryInstance )
      return (unsigned int)-2147024882;
    v13 = (**((__int64 (__fastcall ***)(__int64, unsigned __int64, struct Windows::Compat::Appraiser::RunInfoDataStruct *))InventoryInstance
            + 1))(
            (__int64)InventoryInstance + 8,
            ((unsigned __int64)a4 + 32)
          & -(__int64)((struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24) != 0),
            a5);
    if ( v13 < 0 )
    {
      v14 = -87;
LABEL_70:
      LODWORD(v57) = v13;
      LODWORD(v55) = v13;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v14,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        (const char *)v55,
        (int)"Error initializing: [0x%x].",
        v57);
      goto LABEL_71;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2A9u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error initializing: [0x%x].",
        v13);
    if ( v13 == 1 )
      goto LABEL_71;
    v15 = *((unsigned int *)a2 + 17);
    if ( v15 != (unsigned int)v15 - (unsigned __int64)(((_BYTE)v15 - 1) & 0x1F) + 31 )
      goto LABEL_18;
    v16 = 8 * (v15 + 32);
    if ( !is_mul_ok(v15 + 32, 8u) )
      v16 = -1;
    v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
    {
      for ( i = 0; i < v15; ++i )
      {
        v17[i] = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * i);
        *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * i) = 0;
      }
      v19 = (void *)*((_QWORD *)a2 + 1);
      if ( v19 )
        operator delete(v19);
      *((_QWORD *)a2 + 1) = v17;
LABEL_18:
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x2B0u,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
          "Failed to increase size of pointer array: [0x%x].",
          0);
      *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * (unsigned int)(*((_DWORD *)a2 + 17))++) = v12;
      return 0;
    }
    LODWORD(v57) = -2147024882;
    v13 = -2147024882;
    LODWORD(v55) = -2147024882;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      176,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
      (const char *)v55,
      (int)"Failed to increase size of pointer array: [0x%x].",
      v57);
LABEL_71:
    (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v12 + 1) + 8LL))((_QWORD *)v12 + 1);
    v33 = *(_QWORD *)v12;
    v34 = v12;
LABEL_72:
    (*(void (__fastcall **)(struct Windows::Compat::Appraiser::IOutputter *, __int64))(v33 + 8))(v34, 1);
    return (unsigned int)v13;
  }
  if ( !wcscmp_0(v6, L"DataSource") )
  {
    DataSourceInstance = Windows::Compat::Appraiser::AllComponents::CreateDataSourceInstance(*(wchar_t **)a4);
    v12 = (struct Windows::Compat::Appraiser::IOutputter *)DataSourceInstance;
    if ( !DataSourceInstance )
      return (unsigned int)-2147024882;
    v13 = ((__int64 (__fastcall *)(struct IDataSource *, unsigned __int64, struct Windows::Compat::Appraiser::RunInfoDataStruct *))DataSourceInstance[1].lpVtbl->QueryInterface)(
            &DataSourceInstance[1],
            ((unsigned __int64)a4 + 32)
          & -(__int64)((struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24) != 0),
            a5);
    if ( v13 < 0 )
    {
      v14 = -64;
      goto LABEL_70;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2C0u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error initializing: [0x%x].",
        v13);
    if ( v13 == 1 )
      goto LABEL_71;
    v21 = *((unsigned int *)a2 + 18);
    if ( v21 == (unsigned int)v21 - (unsigned __int64)(((_BYTE)v21 - 1) & 0x1F) + 31 )
    {
      v22 = 8 * (v21 + 32);
      if ( !is_mul_ok(v21 + 32, 8u) )
        v22 = -1;
      v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v23 )
      {
        LODWORD(v57) = -2147024882;
        v13 = -2147024882;
        LODWORD(v55) = -2147024882;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          199,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
          (const char *)v55,
          (int)"Failed to increase size of pointer array: [0x%x].",
          v57);
        goto LABEL_71;
      }
      for ( j = 0; j < v21; ++j )
      {
        v23[j] = *(_QWORD *)(*((_QWORD *)a2 + 2) + 8 * j);
        *(_QWORD *)(*((_QWORD *)a2 + 2) + 8 * j) = 0;
      }
      v25 = (void *)*((_QWORD *)a2 + 2);
      if ( v25 )
        operator delete(v25);
      *((_QWORD *)a2 + 2) = v23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2C7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Failed to increase size of pointer array: [0x%x].",
        0);
    *(_QWORD *)(*((_QWORD *)a2 + 2) + 8LL * (unsigned int)(*((_DWORD *)a2 + 18))++) = v12;
    return 0;
  }
  if ( !wcscmp_0(v6, L"DecisionMakerComponent") )
  {
    if ( wcscmp_0(L"DecisionTables", *(const wchar_t **)a4) )
      return (unsigned int)-2147024882;
    v26 = (Windows::Compat::Appraiser::DecisionTableQuery *)operator new(
                                                              0x48u,
                                                              (const struct std::nothrow_t *)&std::nothrow);
    v12 = v26
        ? (struct Windows::Compat::Appraiser::IOutputter *)Windows::Compat::Appraiser::DecisionTableQuery::DecisionTableQuery(v26)
        : 0LL;
    if ( !v12 )
      return (unsigned int)-2147024882;
    v13 = (**((__int64 (__fastcall ***)(_QWORD *, unsigned __int64, struct Windows::Compat::Appraiser::RunInfoDataStruct *))v12
            + 1))(
            (_QWORD *)v12 + 1,
            ((unsigned __int64)a4 + 32)
          & -(__int64)((struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24) != 0),
            a5);
    if ( v13 < 0 )
    {
      v14 = -41;
      goto LABEL_70;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2D7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error initializing: [0x%x].",
        v13);
    if ( v13 == 1 )
      goto LABEL_71;
    v27 = *((unsigned int *)a2 + 19);
    if ( v27 == (unsigned int)v27 - (unsigned __int64)(((_BYTE)v27 - 1) & 0x1F) + 31 )
    {
      v28 = 8 * (v27 + 32);
      if ( !is_mul_ok(v27 + 32, 8u) )
        v28 = -1;
      v29 = operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v29 )
      {
        LODWORD(v57) = -2147024882;
        v13 = -2147024882;
        LODWORD(v55) = -2147024882;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          222,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
          (const char *)v55,
          (int)"Failed to increase size of pointer array: [0x%x].",
          v57);
        goto LABEL_71;
      }
      for ( k = 0; k < v27; ++k )
      {
        v29[k] = *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * k);
        *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * k) = 0;
      }
      v31 = (void *)*((_QWORD *)a2 + 3);
      if ( v31 )
        operator delete(v31);
      *((_QWORD *)a2 + 3) = v29;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2DEu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Failed to increase size of pointer array: [0x%x].",
        0);
    *(_QWORD *)(*((_QWORD *)a2 + 3) + 8LL * (unsigned int)(*((_DWORD *)a2 + 19))++) = v12;
    return 0;
  }
  if ( !wcscmp_0(v6, L"DecisionAggregator") )
  {
    DecisionAggregatorInstance = Windows::Compat::Appraiser::AllComponents::CreateDecisionAggregatorInstance(*(wchar_t **)a4);
    v12 = DecisionAggregatorInstance;
    if ( !DecisionAggregatorInstance )
      return (unsigned int)-2147024882;
    v13 = (**((__int64 (__fastcall ***)(__int64, unsigned __int64, struct Windows::Compat::Appraiser::RunInfoDataStruct *))DecisionAggregatorInstance
            + 1))(
            (__int64)DecisionAggregatorInstance + 8,
            ((unsigned __int64)a4 + 32)
          & -(__int64)((struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24) != 0),
            a5);
    if ( v13 < 0 )
    {
      v14 = -18;
      goto LABEL_70;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2EEu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error initializing: [0x%x].",
        v13);
    if ( v13 == 1 )
      goto LABEL_71;
    v35 = *((unsigned int *)a2 + 20);
    if ( v35 == (unsigned int)v35 - (unsigned __int64)(((_BYTE)v35 - 1) & 0x1F) + 31 )
    {
      v36 = 8 * (v35 + 32);
      if ( !is_mul_ok(v35 + 32, 8u) )
        v36 = -1;
      v37 = operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v37 )
      {
        LODWORD(v57) = -2147024882;
        v13 = -2147024882;
        LODWORD(v55) = -2147024882;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          245,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
          (const char *)v55,
          (int)"Failed to increase size of pointer array: [0x%x].",
          v57);
        goto LABEL_71;
      }
      for ( m = 0; m < v35; ++m )
      {
        v37[m] = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * m);
        *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * m) = 0;
      }
      v39 = (void *)*((_QWORD *)a2 + 4);
      if ( v39 )
        operator delete(v39);
      *((_QWORD *)a2 + 4) = v37;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2F5u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Failed to increase size of pointer array: [0x%x].",
        0);
    *(_QWORD *)(*((_QWORD *)a2 + 4) + 8LL * (unsigned int)(*((_DWORD *)a2 + 20))++) = v12;
    return 0;
  }
  if ( !wcscmp_0(v6, L"Outputter") )
  {
    OutputterInstance = Windows::Compat::Appraiser::AllComponents::CreateOutputterInstance(*(wchar_t **)a4);
    v41 = OutputterInstance;
    if ( !OutputterInstance )
      return (unsigned int)-2147024882;
    v42 = (**((__int64 (__fastcall ***)(__int64, unsigned __int64, struct Windows::Compat::Appraiser::RunInfoDataStruct *))OutputterInstance
            + 1))(
            (__int64)OutputterInstance + 8,
            ((unsigned __int64)a4 + 32)
          & -(__int64)((struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24) != 0),
            a5);
    v13 = v42;
    if ( v42 < 0 )
    {
      LODWORD(v57) = v42;
      LODWORD(v55) = v42;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        5,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        (const char *)v55,
        (int)"Error initializing: [0x%x].",
        v57);
LABEL_93:
      (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v41 + 1) + 8LL))((_QWORD *)v41 + 1);
      v33 = *(_QWORD *)v41;
      v34 = v41;
      goto LABEL_72;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x305u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error initializing: [0x%x].",
        v42);
    if ( v13 == 1 )
      goto LABEL_93;
    v43 = *((unsigned int *)a2 + 21);
    if ( v43 == (unsigned int)v43 - (unsigned __int64)(((_BYTE)v43 - 1) & 0x1F) + 31 )
    {
      v44 = 8 * (v43 + 32);
      if ( !is_mul_ok(v43 + 32, 8u) )
        v44 = -1;
      v45 = operator new[](v44, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v45 )
      {
        LODWORD(v57) = -2147024882;
        v13 = -2147024882;
        LODWORD(v55) = -2147024882;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          12,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
          (const char *)v55,
          (int)"Failed to increase size of pointer array: [0x%x].",
          v57);
        goto LABEL_93;
      }
      for ( n = 0; n < v43; ++n )
      {
        v45[n] = *(_QWORD *)(*((_QWORD *)a2 + 5) + 8 * n);
        *(_QWORD *)(*((_QWORD *)a2 + 5) + 8 * n) = 0;
      }
      v47 = (void *)*((_QWORD *)a2 + 5);
      if ( v47 )
        operator delete(v47);
      *((_QWORD *)a2 + 5) = v45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x30Cu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Failed to increase size of pointer array: [0x%x].",
        0);
    *(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL * (unsigned int)(*((_DWORD *)a2 + 21))++) = v41;
    return 0;
  }
  if ( !wcscmp_0(v6, L"Metadata") )
  {
    v13 = Windows::Compat::Appraiser::XmlAppraiser::PropertyBagToPropertyArray(
            (struct Windows::Compat::Appraiser::IProperty ***)a2,
            (unsigned int *)a2 + 16,
            v48,
            (struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24));
    if ( v13 < 0 )
    {
      v49 = "Error populating metadata property array from property bag: [0x%x].";
      v50 = 28;
LABEL_113:
      LODWORD(v57) = v13;
      LODWORD(v56) = (_DWORD)v49;
LABEL_114:
      LODWORD(v55) = v13;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v50,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        (const char *)v55,
        (int)v56,
        v57);
      return (unsigned int)v13;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      return 0;
    v51 = "Error populating metadata property array from property bag: [0x%x].";
    v52 = 796;
    goto LABEL_122;
  }
  if ( !wcscmp_0(v6, L"ComponentStatus") )
  {
    v13 = Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentStatuses(
            a2,
            (struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24));
    if ( v13 < 0 )
    {
      v49 = "Error initializing ComponentStatus: [0x%x].";
      v50 = 38;
      goto LABEL_113;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      return 0;
    v51 = "Error initializing ComponentStatus: [0x%x].";
    v52 = 806;
LABEL_122:
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      v52,
      "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
      v51,
      v13);
    return 0;
  }
  if ( wcscmp_0(v6, L"Custom") )
    return 0;
  if ( wcscmp_0(*(const wchar_t **)a4, L"CacheComponent") )
    goto LABEL_140;
  v13 = Windows::Compat::Appraiser::XmlAppraiser::AddCacheComponentsToRun(
          this,
          hTransaction,
          (struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24),
          a2,
          a5);
  if ( v13 < 0 )
  {
    v49 = "Error adding custom component: [0x%x].";
    v50 = 53;
    goto LABEL_113;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x335u,
      "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
      "Error adding custom component: [0x%x].",
      v13);
  if ( v13 != 1 )
  {
LABEL_140:
    if ( wcscmp_0(*(const wchar_t **)a4, L"TelemetryComponent") )
      return 0;
    v53 = Windows::Compat::Appraiser::XmlAppraiser::AddTelemetryComponentsToRun(
            this,
            a3,
            hTransaction,
            (struct Windows::Compat::Appraiser::ComponentInfo *)((char *)a4 + 24),
            a2,
            a5);
    v13 = v53;
    if ( v53 < 0 )
    {
      LODWORD(v57) = v53;
      v50 = 66;
      v56 = (struct Windows::Compat::Appraiser::RunInfoDataStruct *)"Error adding custom component: [0x%x].";
      goto LABEL_114;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x342u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun",
        "Error adding custom component: [0x%x].",
        v53);
    if ( v13 != 1 )
      return 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180062ffc  push    rbx
0x180062ffe  push    rbp
0x180062fff  push    rsi
0x180063000  push    rdi
0x180063001  push    r12
0x180063003  push    r14
0x180063005  push    r15
0x180063007  sub     rsp, 40h
0x18006300b  mov     rbx, [r9+8]
0x18006300f  mov     rdi, rdx
0x180063012  mov     r15, rcx
0x180063015  lea     rdx, aInventory; "Inventory"
0x18006301c  mov     rcx, rbx; String1
0x18006301f  mov     rsi, r9
0x180063022  mov     r12, r8
0x180063025  call    wcscmp_0
0x18006302a  test    eax, eax
0x18006302c  jnz     loc_18006319F
0x180063032  mov     rcx, [rsi]; String2
0x180063035  call    ?CreateInventoryInstance@AllComponents@Appraiser@Compat@Windows@@SAPEAVIInventory@234@PEBG@Z; Windows::Compat::Appraiser::AllComponents::CreateInventoryInstance(ushort const *)
0x18006303a  mov     r14, rax
0x18006303d  test    rax, rax
0x180063040  jnz     short loc_18006304C
0x180063042  mov     ebx, 8007000Eh
0x180063047  jmp     loc_180063A58
0x18006304c  mov     r8, [rsp+78h+arg_20]
0x180063054  lea     rcx, [rax+8]
0x180063058  mov     r9, [rcx]
0x18006305b  lea     rdx, [rsi+18h]
0x18006305f  lea     rax, [rdx+8]
0x180063063  xor     r15d, r15d
0x180063066  neg     rdx
0x180063069  sbb     rdx, rdx
0x18006306c  and     rdx, rax
0x18006306f  mov     rax, [r9]
0x180063072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063077  mov     ebx, eax
0x180063079  test    eax, eax
0x18006307b  jns     short loc_180063087
0x18006307d  mov     edx, 2A9h
0x180063082  jmp     loc_180063528
0x180063087  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006308d  test    al, 1
0x18006308f  jz      short loc_1800630B4
0x180063091  lea     r9, aErrorInitializ_14; "Error initializing: [0x%x]."
0x180063098  mov     dword ptr [rsp+78h+var_58], ebx
0x18006309c  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800630a3  mov     ecx, 2A9h; unsigned int
0x1800630a8  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800630af  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800630b4  cmp     ebx, 1
0x1800630b7  jz      loc_180063554
0x1800630bd  mov     ebx, [rdi+44h]
0x1800630c0  mov     ecx, ebx
0x1800630c2  lea     rax, [rbx-1]
0x1800630c6  and     eax, 1Fh
0x1800630c9  sub     rcx, rax
0x1800630cc  add     rcx, 1Fh
0x1800630d0  cmp     rbx, rcx
0x1800630d3  jnz     short loc_180063139
0x1800630d5  lea     rcx, [rbx+20h]
0x1800630d9  mov     eax, 8
0x1800630de  mul     rcx
0x1800630e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800630e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800630ef  cmovb   rax, rcx
0x1800630f3  mov     rcx, rax; unsigned __int64
0x1800630f6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800630fb  mov     rsi, rax
0x1800630fe  test    rax, rax
0x180063101  jz      short loc_18006317A
0x180063103  xor     r8d, r8d
0x180063106  test    rbx, rbx
0x180063109  jz      short loc_180063127
0x18006310b  mov     rcx, [rdi+8]
0x18006310f  mov     rdx, [rcx+r8*8]
0x180063113  mov     [rsi+r8*8], rdx
0x180063117  mov     rax, [rdi+8]
0x18006311b  mov     [rax+r8*8], r15
0x18006311f  inc     r8
0x180063122  cmp     r8, rbx
0x180063125  jb      short loc_18006310B
0x180063127  mov     rcx, [rdi+8]; Block
0x18006312b  test    rcx, rcx
0x18006312e  jz      short loc_180063135
0x180063130  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063135  mov     [rdi+8], rsi
0x180063139  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006313f  test    al, 1
0x180063141  jz      short loc_180063167
0x180063143  lea     r9, aFailedToIncrea; "Failed to increase size of pointer arra"...
0x18006314a  mov     dword ptr [rsp+78h+var_58], r15d
0x18006314f  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063156  mov     ecx, 2B0h; unsigned int
0x18006315b  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063162  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180063167  mov     ecx, [rdi+44h]
0x18006316a  mov     rax, [rdi+8]
0x18006316e  mov     [rax+rcx*8], r14
0x180063172  inc     dword ptr [rdi+44h]
0x180063175  jmp     loc_180063A56
0x18006317a  mov     eax, 8007000Eh
0x18006317f  lea     r9, aFailedToIncrea; "Failed to increase size of pointer arra"...
0x180063186  mov     dword ptr [rsp+78h+var_48], eax
0x18006318a  mov     ebx, eax
0x18006318c  mov     [rsp+78h+var_50], r9
0x180063191  mov     edx, 2B0h
0x180063196  mov     dword ptr [rsp+78h+var_58], eax
0x18006319a  jmp     loc_18006353C
0x18006319f  lea     rdx, aDatasource; "DataSource"
0x1800631a6  mov     rcx, rbx; String1
0x1800631a9  call    wcscmp_0
0x1800631ae  test    eax, eax
0x1800631b0  jnz     loc_18006331D
0x1800631b6  mov     rcx, [rsi]; String2
0x1800631b9  call    ?CreateDataSourceInstance@AllComponents@Appraiser@Compat@Windows@@SAPEAVIDataSource@234@PEBG@Z; Windows::Compat::Appraiser::AllComponents::CreateDataSourceInstance(ushort const *)
0x1800631be  mov     r14, rax
0x1800631c1  test    rax, rax
0x1800631c4  jz      loc_180063042
0x1800631ca  mov     r8, [rsp+78h+arg_20]
0x1800631d2  lea     rcx, [rax+8]
0x1800631d6  mov     r9, [rcx]
0x1800631d9  lea     rdx, [rsi+18h]
0x1800631dd  lea     rax, [rdx+8]
0x1800631e1  xor     r15d, r15d
0x1800631e4  neg     rdx
0x1800631e7  sbb     rdx, rdx
0x1800631ea  and     rdx, rax
0x1800631ed  mov     rax, [r9]
0x1800631f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631f5  mov     ebx, eax
0x1800631f7  test    eax, eax
0x1800631f9  jns     short loc_180063205
0x1800631fb  mov     edx, 2C0h
0x180063200  jmp     loc_180063528
0x180063205  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006320b  test    al, 1
0x18006320d  jz      short loc_180063232
0x18006320f  lea     r9, aErrorInitializ_14; "Error initializing: [0x%x]."
0x180063216  mov     dword ptr [rsp+78h+var_58], ebx
0x18006321a  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063221  mov     ecx, 2C0h; unsigned int
0x180063226  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006322d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180063232  cmp     ebx, 1
0x180063235  jz      loc_180063554
0x18006323b  mov     ebx, [rdi+48h]
0x18006323e  mov     ecx, ebx
0x180063240  lea     rax, [rbx-1]
0x180063244  and     eax, 1Fh
0x180063247  sub     rcx, rax
0x18006324a  add     rcx, 1Fh
0x18006324e  cmp     rbx, rcx
0x180063251  jnz     short loc_1800632B7
0x180063253  lea     rcx, [rbx+20h]
0x180063257  mov     eax, 8
0x18006325c  mul     rcx
0x18006325f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180063266  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006326d  cmovb   rax, rcx
0x180063271  mov     rcx, rax; unsigned __int64
0x180063274  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180063279  mov     rsi, rax
0x18006327c  test    rax, rax
0x18006327f  jz      short loc_1800632F8
0x180063281  xor     r8d, r8d
0x180063284  test    rbx, rbx
0x180063287  jz      short loc_1800632A5
0x180063289  mov     rcx, [rdi+10h]
0x18006328d  mov     rdx, [rcx+r8*8]
0x180063291  mov     [rsi+r8*8], rdx
0x180063295  mov     rax, [rdi+10h]
0x180063299  mov     [rax+r8*8], r15
0x18006329d  inc     r8
0x1800632a0  cmp     r8, rbx
0x1800632a3  jb      short loc_180063289
0x1800632a5  mov     rcx, [rdi+10h]; Block
0x1800632a9  test    rcx, rcx
0x1800632ac  jz      short loc_1800632B3
0x1800632ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800632b3  mov     [rdi+10h], rsi
0x1800632b7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800632bd  test    al, 1
0x1800632bf  jz      short loc_1800632E5
0x1800632c1  lea     r9, aFailedToIncrea; "Failed to increase size of pointer arra"...
0x1800632c8  mov     dword ptr [rsp+78h+var_58], r15d
0x1800632cd  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800632d4  mov     ecx, 2C7h; unsigned int
0x1800632d9  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800632e0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800632e5  mov     ecx, [rdi+48h]
0x1800632e8  mov     rax, [rdi+10h]
0x1800632ec  mov     [rax+rcx*8], r14
0x1800632f0  inc     dword ptr [rdi+48h]
0x1800632f3  jmp     loc_180063A56
0x1800632f8  mov     eax, 8007000Eh
0x1800632fd  lea     r9, aFailedToIncrea; "Failed to increase size of pointer arra"...
0x180063304  mov     dword ptr [rsp+78h+var_48], eax
0x180063308  mov     ebx, eax
0x18006330a  mov     [rsp+78h+var_50], r9
0x18006330f  mov     edx, 2C7h
0x180063314  mov     dword ptr [rsp+78h+var_58], eax
0x180063318  jmp     loc_18006353C
0x18006331d  lea     rdx, aDecisionmakerc; "DecisionMakerComponent"
0x180063324  mov     rcx, rbx; String1
0x180063327  call    wcscmp_0
0x18006332c  test    eax, eax
0x18006332e  jnz     loc_1800634C7
0x180063334  mov     rdx, [rsi]; String2
0x180063337  lea     rcx, aDecisiontables; "DecisionTables"
0x18006333e  call    wcscmp_0
0x180063343  test    eax, eax
0x180063345  jnz     loc_180063042
0x18006334b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063352  lea     ecx, [rax+48h]; unsigned __int64
0x180063355  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006335a  test    rax, rax
0x18006335d  jz      short loc_18006336C
0x18006335f  mov     rcx, rax; this
0x180063362  call    ??0DecisionTableQuery@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::DecisionTableQuery::DecisionTableQuery(void)
0x180063367  mov     r14, rax
0x18006336a  jmp     short loc_18006336F
0x18006336c  xor     r14d, r14d
0x18006336f  test    r14, r14
0x180063372  jz      loc_180063042
0x180063378  mov     r8, [rsp+78h+arg_20]
0x180063380  lea     rdx, [rsi+18h]
0x180063384  lea     rax, [rdx+8]
0x180063388  xor     r15d, r15d
0x18006338b  neg     rdx
0x18006338e  lea     rcx, [r14+8]
0x180063392  mov     r9, [rcx]
0x180063395  sbb     rdx, rdx
0x180063398  and     rdx, rax
0x18006339b  mov     rax, [r9]
0x18006339e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633a3  mov     ebx, eax
0x1800633a5  test    eax, eax
0x1800633a7  jns     short loc_1800633B3
0x1800633a9  mov     edx, 2D7h
0x1800633ae  jmp     loc_180063528
0x1800633b3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800633b9  test    al, 1
0x1800633bb  jz      short loc_1800633E0
0x1800633bd  lea     r9, aErrorInitializ_14; "Error initializing: [0x%x]."
0x1800633c4  mov     dword ptr [rsp+78h+var_58], ebx
0x1800633c8  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800633cf  mov     ecx, 2D7h; unsigned int
0x1800633d4  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800633db  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800633e0  cmp     ebx, 1
0x1800633e3  jz      loc_180063554
0x1800633e9  mov     ebx, [rdi+4Ch]
0x1800633ec  mov     ecx, ebx
0x1800633ee  lea     rax, [rbx-1]
0x1800633f2  and     eax, 1Fh
0x1800633f5  sub     rcx, rax
0x1800633f8  add     rcx, 1Fh
0x1800633fc  cmp     rbx, rcx
0x1800633ff  jnz     short loc_180063464
0x180063401  lea     rcx, [rbx+20h]
0x180063405  mov     eax, 8
0x18006340a  mul     rcx
0x18006340d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180063414  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006341b  cmovb   rax, rcx
0x18006341f  mov     rcx, rax; unsigned __int64
0x180063422  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180063427  mov     rsi, rax
0x18006342a  test    rax, rax
0x18006342d  jz      short loc_1800634A5
0x18006342f  xor     edx, edx
0x180063431  test    rbx, rbx
0x180063434  jz      short loc_180063452
0x180063436  mov     rax, [rdi+18h]
0x18006343a  mov     rcx, [rax+rdx*8]
0x18006343e  mov     [rsi+rdx*8], rcx
0x180063442  mov     rax, [rdi+18h]
0x180063446  mov     [rax+rdx*8], r15
0x18006344a  inc     rdx
0x18006344d  cmp     rdx, rbx
0x180063450  jb      short loc_180063436
0x180063452  mov     rcx, [rdi+18h]; Block
0x180063456  test    rcx, rcx
0x180063459  jz      short loc_180063460
0x18006345b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063460  mov     [rdi+18h], rsi
0x180063464  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006346a  test    al, 1
0x18006346c  jz      short loc_180063492
0x18006346e  lea     r9, aFailedToIncrea; "Failed to increase size of pointer arra"...
0x180063475  mov     dword ptr [rsp+78h+var_58], r15d
0x18006347a  lea     r8, aWindowsCompatA_831; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063481  mov     ecx, 2DEh; unsigned int
0x180063486  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006348d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180063492  mov     ecx, [rdi+4Ch]
0x180063495  mov     rax, [rdi+18h]
0x180063499  mov     [rax+rcx*8], r14
0x18006349d  inc     dword ptr [rdi+4Ch]
  ... truncated ...
```
