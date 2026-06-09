# Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback(Windows::Compat::Appraiser::Table *,bool,Windows::Compat::Appraiser::TableCache *,void *)

- ea: `0x1800d5450`
- end: `0x1800d5bda`
- name: `?ValidateAssetCallback@InventoryUtils@Appraiser@Compat@Windows@@SAJPEAVTable@234@_NPEAVTableCache@234@PEAX@Z`
- size: `1930`
- prototype: `static int(struct Windows::Compat::Appraiser::Table *, bool, struct Windows::Compat::Appraiser::TableCache *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800011d0`
- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800ad680`
- `0x1800ad97c`
- `0x1800d5450`
- `0x1800d6434`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800d560a`
- `KERNEL32!GetSystemTime` at `0x1800d5782`
- `KERNEL32!GetSystemTime` at `0x1800d5948`
- `KERNEL32!GetSystemTime` at `0x1800d560a`
- `KERNEL32!GetSystemTime` at `0x1800d5782`
- `KERNEL32!GetSystemTime` at `0x1800d5948`
- `KERNEL32!GetProcessHeap` at `0x1800d54b3`
- `KERNEL32!GetProcessHeap` at `0x1800d54b3`
- `KERNEL32!HeapFree` at `0x1800d5ba8`
- `KERNEL32!HeapFree` at `0x1800d5ba8`

## string_xrefs

- `0x1800d550e`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d55e1`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d56a7`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5759`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5836`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5894`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5aba`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5af3`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5b68`: `onecore\base\appcompat\appraiser\inventory\inventoryutils.cpp`
- `0x1800d5507`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d55d6`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d5673`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d574e`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d588d`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d5aae`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`
- `0x1800d5ada`: `Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback(
        const size_t *a1,
        char a2,
        struct Windows::Compat::Appraiser::TableCache *a3,
        struct Windows::Compat::Appraiser::IAsset *a4)
{
  unsigned int v8; // ebx
  int RequiredSingleValue; // eax
  __int64 v10; // rdx
  struct Windows::Compat::Appraiser::UniqueIdentifierTable *v11; // r8
  int v12; // edi
  volatile signed __int64 *v13; // rcx
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  int UniqueIdentifier; // eax
  int v18; // edi
  volatile signed __int64 *v19; // rcx
  void **v20; // rdx
  int v21; // ebx
  int v22; // r8d
  int v23; // r9d
  char *v24; // rdi
  unsigned __int16 *v25; // rsi
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  const size_t *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const size_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const size_t *v37; // rax
  int v38; // ecx
  int v39; // eax
  int v40; // r9d
  char v41; // dl
  int v42; // eax
  char *v44; // [rsp+28h] [rbp-E0h]
  char *v45; // [rsp+28h] [rbp-E0h]
  const char *v46; // [rsp+30h] [rbp-D8h]
  char *v47; // [rsp+38h] [rbp-D0h]
  char *v48; // [rsp+38h] [rbp-D0h]
  int v49; // [rsp+68h] [rbp-A0h] BYREF
  int v50; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v51; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v52[2]; // [rsp+78h] [rbp-90h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-80h] BYREF
  char *v54; // [rsp+98h] [rbp-70h] BYREF
  const char *v55; // [rsp+A0h] [rbp-68h] BYREF
  const char *v56; // [rsp+A8h] [rbp-60h] BYREF
  const char *v57; // [rsp+B0h] [rbp-58h] BYREF
  char *v58; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v59; // [rsp+C0h] [rbp-48h] BYREF
  HANDLE hHeap[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v61; // [rsp+D8h] [rbp-30h]
  LPVOID lpMem[2]; // [rsp+E8h] [rbp-20h]
  __int64 v63; // [rsp+F8h] [rbp-10h]
  struct _SYSTEMTIME v64; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v65[32]; // [rsp+118h] [rbp+10h] BYREF
  struct _SYSTEMTIME *v66; // [rsp+138h] [rbp+30h]
  __int64 v67; // [rsp+140h] [rbp+38h]
  const size_t *v68; // [rsp+148h] [rbp+40h]
  __int64 v69; // [rsp+150h] [rbp+48h]
  const size_t *v70; // [rsp+158h] [rbp+50h]
  int v71; // [rsp+160h] [rbp+58h]
  int v72; // [rsp+164h] [rbp+5Ch]
  const size_t *v73; // [rsp+168h] [rbp+60h]
  int v74; // [rsp+170h] [rbp+68h]
  int v75; // [rsp+174h] [rbp+6Ch]
  const size_t *v76; // [rsp+178h] [rbp+70h]
  int v77; // [rsp+180h] [rbp+78h]
  int v78; // [rsp+184h] [rbp+7Ch]
  _QWORD *v79; // [rsp+188h] [rbp+80h]
  __int64 v80; // [rsp+190h] [rbp+88h]
  char *v81; // [rsp+198h] [rbp+90h]
  int v82; // [rsp+1A0h] [rbp+98h]
  int v83; // [rsp+1A4h] [rbp+9Ch]
  char v84[144]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v85[144]; // [rsp+238h] [rbp+130h] BYREF

  v63 = -2;
  v58 = 0;
  v59 = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v61 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v51 = 0;
  if ( a2 )
  {
    v8 = 0;
    goto LABEL_66;
  }
  RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(&v58, L"AssetType", a4, 1);
  v12 = RequiredSingleValue;
  if ( RequiredSingleValue >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x10Du,
        "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
        "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
        "Failed to get asset type from invalid asset, swallowing: [0x%x].",
        RequiredSingleValue);
  }
  else
  {
    LODWORD(v47) = RequiredSingleValue;
    LODWORD(v44) = RequiredSingleValue;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      13,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
      "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
      v44,
      (int)"Failed to get asset type from invalid asset, swallowing: [0x%x].",
      v47);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v65);
    v13 = (volatile signed __int64 *)v65;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v13 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v13,
      _InterlockedExchangeAdd64(v13 + 17, 0),
      v85);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, (void **)v10);
    v14 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u )
    {
      v10 = 0x200000000000LL;
      if ( (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v54 = v85;
        v49 = v12;
        v55 = "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback";
        v56 = "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp";
        v50 = 269;
        v57 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v64 = SystemTime;
        v52[0] = &v64;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&unk_1802A3C2D,
          v15,
          v16,
          (__int64)v52,
          (__int64)&v57,
          (__int64)&v50,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v49,
          (__int64)&v54);
      }
    }
  }
  UniqueIdentifier = Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(
                       (const unsigned __int16 **)&v59,
                       (const unsigned __int16 **)v10,
                       v11,
                       a4);
  v18 = UniqueIdentifier;
  if ( UniqueIdentifier >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x110u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
        "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
        "Failed to get unique id from invalid asset, swallowing: [0x%x].",
        UniqueIdentifier);
  }
  else
  {
    LODWORD(v47) = UniqueIdentifier;
    LODWORD(v44) = UniqueIdentifier;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      16,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
      "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
      v44,
      (int)"Failed to get unique id from invalid asset, swallowing: [0x%x].",
      v47);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v65);
    v19 = (volatile signed __int64 *)v65;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v19 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v19,
      _InterlockedExchangeAdd64(v19 + 17, 0),
      v85);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v20);
    v21 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v52[0] = v85;
      v50 = v18;
      v57 = "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback";
      v56 = "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp";
      v49 = 272;
      v55 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v64 = SystemTime;
      v54 = (char *)&v64;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v21,
        (unsigned int)&unk_1802A3C90,
        v22,
        v23,
        (__int64)&v54,
        (__int64)&v55,
        (__int64)&v49,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v50,
        (__int64)v52);
    }
  }
  v24 = (char *)&szValueBuf;
  if ( v58 )
    v24 = v58;
  v25 = (unsigned __int16 *)&szValueBuf;
  if ( v59 )
    v25 = v59;
  LODWORD(v44) = 13;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    28,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
    "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
    v44,
    (int)"Asset with type [%ls] and unique id [%ls] failed validation table [%ls]. Check later info events for details.",
    v24,
    v25,
    a1);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v84);
  v26 = (volatile signed __int64 *)v84;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v26,
    _InterlockedExchangeAdd64(v26 + 17, 0),
    v85);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
  v28 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v52[0] = 0x1000000;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v64 = SystemTime;
    v29 = -1;
    v30 = -1;
    do
      ++v30;
    while ( v85[v30] );
    v81 = v85;
    v82 = v30 + 1;
    v83 = 0;
    v79 = v52;
    v80 = 8;
    if ( a1 )
    {
      v31 = a1;
      v32 = -1;
      do
        ++v32;
      while ( *((_WORD *)a1 + v32) );
      v33 = 2 * v32 + 2;
    }
    else
    {
      v31 = &szValueBuf;
      v33 = 2;
    }
    v76 = v31;
    v77 = v33;
    v78 = 0;
    if ( v25 )
    {
      v34 = (const size_t *)v25;
      v35 = -1;
      do
        ++v35;
      while ( v25[v35] );
      v36 = 2 * v35 + 2;
    }
    else
    {
      v34 = &szValueBuf;
      v36 = 2;
    }
    v73 = v34;
    v74 = v36;
    v75 = 0;
    if ( v24 )
    {
      v37 = (const size_t *)v24;
      do
        ++v29;
      while ( *(_WORD *)&v24[2 * v29] );
      v38 = 2 * v29 + 2;
    }
    else
    {
      v37 = &szValueBuf;
      v38 = 2;
    }
    v70 = v37;
    v71 = v38;
    v72 = 0;
    v68 = &szValueBuf;
    v69 = 2;
    v66 = &v64;
    v67 = 16;
    tlgWriteTransfer_EventWriteTransfer(v28, &unk_1802A3CF3, 0, 0, 9, v65);
  }
  v39 = (**(__int64 (__fastcall ***)(struct Windows::Compat::Appraiser::IAsset *, __int64 *, __int64))a4)(a4, &v51, 1);
  v8 = v39;
  if ( v39 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x121u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
        "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
        "Failed to get property list enumerator: [0x%x].",
        v39);
    LOBYTE(v40) = 1;
    v42 = Windows::Compat::Appraiser::InventoryUtils::ValidateIncorrectSubtable(
            (_DWORD)v24,
            (_DWORD)v25,
            (_DWORD)a1,
            v40,
            (__int64)a3,
            (__int64)hHeap,
            v51);
    v8 = v42;
    if ( v42 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x124u,
          "onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
          "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
          "Failed to validate incorrect tables: [0x%x].",
          v42);
      v8 = -2147024883;
      goto LABEL_64;
    }
    LODWORD(v48) = v42;
    v46 = "Failed to validate incorrect tables: [0x%x].";
    v41 = 36;
  }
  else
  {
    LODWORD(v48) = v39;
    v46 = "Failed to get property list enumerator: [0x%x].";
    v41 = 33;
  }
  LODWORD(v45) = v8;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v41,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inventoryutils.cpp",
    "Windows::Compat::Appraiser::InventoryUtils::ValidateAssetCallback",
    v45,
    (int)v46,
    v48);
LABEL_64:
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51);
    v51 = 0;
  }
LABEL_66:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return v8;
}

```

## disassembly

```asm
0x1800d5450  mov     rax, rsp
0x1800d5453  push    rbp
0x1800d5454  push    rsi
0x1800d5455  push    rdi
0x1800d5456  push    r12
0x1800d5458  push    r13
0x1800d545a  push    r14
0x1800d545c  push    r15
0x1800d545e  lea     rbp, [rax-208h]
0x1800d5465  sub     rsp, 2D0h
0x1800d546c  mov     [rbp+200h+var_210], 0FFFFFFFFFFFFFFFEh
0x1800d5474  mov     [rax+10h], rbx
0x1800d5478  mov     rax, cs:__security_cookie
0x1800d547f  xor     rax, rsp
0x1800d5482  mov     [rbp+200h+var_40], rax
0x1800d5489  mov     r15, r9
0x1800d548c  mov     r12, r8
0x1800d548f  mov     bl, dl
0x1800d5491  mov     r14, rcx
0x1800d5494  xor     r13d, r13d
0x1800d5497  mov     [rbp+200h+var_250], r13
0x1800d549b  mov     [rbp+200h+var_248], r13
0x1800d549f  mov     [rsp+300h+var_298], r13
0x1800d54a4  xorps   xmm0, xmm0
0x1800d54a7  movups  xmmword ptr [rbp+200h+hHeap], xmm0
0x1800d54ab  movups  [rbp+200h+var_230], xmm0
0x1800d54af  movups  xmmword ptr [rbp+200h+lpMem], xmm0
0x1800d54b3  call    cs:__imp_GetProcessHeap
0x1800d54b9  mov     [rbp+200h+hHeap], rax
0x1800d54bd  mov     [rbp+200h+lpMem], 10h
0x1800d54c5  xorps   xmm0, xmm0
0x1800d54c8  movdqu  [rbp+200h+var_230], xmm0
0x1800d54cd  mov     [rbp+200h+lpMem+8], r13
0x1800d54d1  mov     [rbp+200h+hHeap+8], 8
0x1800d54d9  mov     [rsp+300h+var_298], r13
0x1800d54de  test    bl, bl
0x1800d54e0  jz      short loc_1800D54EA
0x1800d54e2  mov     ebx, r13d
0x1800d54e5  jmp     loc_1800D5B99
0x1800d54ea  mov     esi, 1
0x1800d54ef  mov     r9d, esi
0x1800d54f2  mov     r8, r15
0x1800d54f5  lea     rdx, aAssettype; "AssetType"
0x1800d54fc  lea     rcx, [rbp+200h+var_250]
0x1800d5500  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x1800d5505  mov     edi, eax
0x1800d5507  lea     rbx, aWindowsCompatA_39; "Windows::Compat::Appraiser::InventoryUt"...
0x1800d550e  lea     rcx, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d5515  test    eax, eax
0x1800d5517  jns     loc_1800D57EC
0x1800d551d  mov     dword ptr [rsp+300h+var_2D0], eax; char *
0x1800d5521  lea     r9, aFailedToGetAss; "Failed to get asset type from invalid a"...
0x1800d5528  mov     qword ptr [rsp+300h+var_2D8], r9; int
0x1800d552d  mov     dword ptr [rsp+300h+var_2E0], eax; char *
0x1800d5531  mov     r9, rbx; char *
0x1800d5534  mov     r8, rcx; unsigned int
0x1800d5537  mov     edx, 10Dh; bool
0x1800d553c  mov     ecx, esi; this
0x1800d553e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800d5543  lea     rcx, [rbp+200h+var_1F0]; this
0x1800d5547  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800d554c  lea     rcx, [rbp+200h+var_1F0]
0x1800d5550  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800d5557  test    rax, rax
0x1800d555a  cmovnz  rcx, rax; this
0x1800d555e  mov     rdx, r13
0x1800d5561  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800d556a  lea     r8, [rbp+200h+var_D0]; char *
0x1800d5571  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800d5576  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800d557d  jz      short loc_1800D558B
0x1800d557f  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800d5586  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800d558b  mov     rbx, cs:qword_1802C9628
0x1800d5592  mov     eax, [rbx]
0x1800d5594  cmp     eax, 5
0x1800d5597  jbe     loc_1800D5673
0x1800d559d  mov     rcx, [rbx+18h]
0x1800d55a1  mov     rax, [rbx+10h]
0x1800d55a5  mov     rdx, 200000000000h
0x1800d55af  test    rdx, rax
0x1800d55b2  jz      loc_1800D5673
0x1800d55b8  mov     rax, rcx
0x1800d55bb  and     rax, rdx
0x1800d55be  cmp     rax, rcx
0x1800d55c1  jnz     loc_1800D5673
0x1800d55c7  lea     rax, [rbp+200h+var_D0]
0x1800d55ce  mov     [rbp+200h+var_270], rax
0x1800d55d2  mov     dword ptr [rsp+300h+var_2A0], edi
0x1800d55d6  lea     rax, aWindowsCompatA_39; "Windows::Compat::Appraiser::InventoryUt"...
0x1800d55dd  mov     [rbp+200h+var_268], rax
0x1800d55e1  lea     rax, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d55e8  mov     [rbp+200h+var_260], rax
0x1800d55ec  mov     dword ptr [rsp+300h+var_2A0+4], 10Dh
0x1800d55f4  lea     rax, szValueBuf
0x1800d55fb  mov     [rbp+200h+var_258], rax
0x1800d55ff  xorps   xmm0, xmm0
0x1800d5602  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1800d5606  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1800d560a  call    cs:__imp_GetSystemTime
0x1800d5610  movaps  xmm0, xmmword ptr [rbp+200h+SystemTime.wYear]
0x1800d5614  movdqa  [rbp+200h+var_200], xmm0
0x1800d5619  lea     rax, [rbp+200h+var_200]
0x1800d561d  mov     [rsp+70h], rax
0x1800d5622  lea     rax, [rbp+200h+var_270]
0x1800d5626  mov     [rsp+50h], rax
0x1800d562b  lea     rax, [rsp+300h+var_2A0]
0x1800d5630  mov     [rsp+300h+var_2B8], rax
0x1800d5635  lea     rax, [rbp+200h+var_268]
0x1800d5639  mov     [rsp+300h+var_2C0], rax
0x1800d563e  lea     rax, [rbp+200h+var_260]
0x1800d5642  mov     [rsp+300h+var_2C8], rax
0x1800d5647  lea     rax, [rsp+300h+var_2A0+4]
0x1800d564c  mov     [rsp+300h+var_2D0], rax
0x1800d5651  lea     rax, [rbp+200h+var_258]
0x1800d5655  mov     qword ptr [rsp+300h+var_2D8], rax
0x1800d565a  lea     rax, [rsp+70h]
0x1800d565f  mov     [rsp+300h+var_2E0], rax
0x1800d5664  lea     rdx, unk_1802A3C2D
0x1800d566b  mov     rcx, rbx
0x1800d566e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800d5673  lea     rbx, aWindowsCompatA_39; "Windows::Compat::Appraiser::InventoryUt"...
0x1800d567a  mov     r9, r15; struct Windows::Compat::Appraiser::IAsset *
0x1800d567d  lea     rcx, [rbp+200h+var_248]; unsigned __int16 **
0x1800d5681  call    ?GetUniqueIdentifier@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBG0PEAUUniqueIdentifierTable@234@PEAVIAsset@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(ushort const * *,ushort const * *,Windows::Compat::Appraiser::UniqueIdentifierTable *,Windows::Compat::Appraiser::IAsset *)
0x1800d5686  mov     edi, eax
0x1800d5688  test    eax, eax
0x1800d568a  jns     loc_1800D581C
0x1800d5690  mov     dword ptr [rsp+300h+var_2D0], eax; char *
0x1800d5694  lea     r9, aFailedToGetUni_0; "Failed to get unique id from invalid as"...
0x1800d569b  mov     qword ptr [rsp+300h+var_2D8], r9; int
0x1800d56a0  mov     dword ptr [rsp+300h+var_2E0], eax; char *
0x1800d56a4  mov     r9, rbx; char *
0x1800d56a7  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d56ae  mov     edx, 110h; bool
0x1800d56b3  mov     ecx, esi; this
0x1800d56b5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800d56ba  lea     rcx, [rbp+200h+var_1F0]; this
0x1800d56be  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800d56c3  lea     rcx, [rbp+200h+var_1F0]
0x1800d56c7  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800d56ce  test    rax, rax
0x1800d56d1  cmovnz  rcx, rax; this
0x1800d56d5  mov     rdx, r13
0x1800d56d8  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800d56e1  lea     r8, [rbp+200h+var_D0]; char *
0x1800d56e8  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800d56ed  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800d56f4  jz      short loc_1800D5702
0x1800d56f6  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800d56fd  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800d5702  mov     rbx, cs:qword_1802C9628
0x1800d5709  mov     eax, [rbx]
0x1800d570b  cmp     eax, 5
0x1800d570e  jbe     loc_1800D5847
0x1800d5714  mov     rcx, [rbx+18h]
0x1800d5718  mov     rax, [rbx+10h]
0x1800d571c  mov     rdx, 200000000000h
0x1800d5726  test    rdx, rax
0x1800d5729  jz      loc_1800D5847
0x1800d572f  mov     rax, rcx
0x1800d5732  and     rax, rdx
0x1800d5735  cmp     rax, rcx
0x1800d5738  jnz     loc_1800D5847
0x1800d573e  lea     rax, [rbp+200h+var_D0]
0x1800d5745  mov     [rsp+70h], rax
0x1800d574a  mov     dword ptr [rsp+300h+var_2A0+4], edi
0x1800d574e  lea     rax, aWindowsCompatA_39; "Windows::Compat::Appraiser::InventoryUt"...
0x1800d5755  mov     [rbp+200h+var_258], rax
0x1800d5759  lea     rax, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d5760  mov     [rbp+200h+var_260], rax
0x1800d5764  mov     dword ptr [rsp+300h+var_2A0], 110h
0x1800d576c  lea     rax, szValueBuf
0x1800d5773  mov     [rbp+200h+var_268], rax
0x1800d5777  xorps   xmm0, xmm0
0x1800d577a  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1800d577e  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1800d5782  call    cs:__imp_GetSystemTime
0x1800d5788  movaps  xmm0, xmmword ptr [rbp+200h+SystemTime.wYear]
0x1800d578c  movdqa  [rbp+200h+var_200], xmm0
0x1800d5791  lea     rax, [rbp+200h+var_200]
0x1800d5795  mov     [rbp+200h+var_270], rax
0x1800d5799  lea     rax, [rsp+70h]
0x1800d579e  mov     [rsp+50h], rax
0x1800d57a3  lea     rax, [rsp+300h+var_2A0+4]
0x1800d57a8  mov     [rsp+300h+var_2B8], rax
0x1800d57ad  lea     rax, [rbp+200h+var_258]
0x1800d57b1  mov     [rsp+300h+var_2C0], rax
0x1800d57b6  lea     rax, [rbp+200h+var_260]
0x1800d57ba  mov     [rsp+300h+var_2C8], rax
0x1800d57bf  lea     rax, [rsp+300h+var_2A0]
0x1800d57c4  mov     [rsp+300h+var_2D0], rax
0x1800d57c9  lea     rax, [rbp+200h+var_268]
0x1800d57cd  mov     qword ptr [rsp+300h+var_2D8], rax
0x1800d57d2  lea     rax, [rbp+200h+var_270]
0x1800d57d6  mov     [rsp+300h+var_2E0], rax
0x1800d57db  lea     rdx, unk_1802A3C90
0x1800d57e2  mov     rcx, rbx
0x1800d57e5  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800d57ea  jmp     short loc_1800D5847
0x1800d57ec  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800d57f2  and     eax, esi
0x1800d57f4  test    al, al
0x1800d57f6  jz      loc_1800D567A
0x1800d57fc  mov     dword ptr [rsp+300h+var_2E0], edi
0x1800d5800  lea     r9, aFailedToGetAss; "Failed to get asset type from invalid a"...
0x1800d5807  mov     r8, rbx; char *
0x1800d580a  mov     rdx, rcx; char *
0x1800d580d  mov     ecx, 10Dh; unsigned int
0x1800d5812  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800d5817  jmp     loc_1800D567A
0x1800d581c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800d5822  and     eax, esi
0x1800d5824  test    al, al
0x1800d5826  jz      short loc_1800D5847
0x1800d5828  mov     dword ptr [rsp+300h+var_2E0], edi
0x1800d582c  lea     r9, aFailedToGetUni_0; "Failed to get unique id from invalid as"...
0x1800d5833  mov     r8, rbx; char *
0x1800d5836  lea     rdx, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d583d  mov     ecx, 110h; unsigned int
0x1800d5842  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800d5847  lea     rcx, szValueBuf
0x1800d584e  mov     rdi, rcx
0x1800d5851  mov     rax, [rbp+200h+var_250]
0x1800d5855  test    rax, rax
0x1800d5858  cmovnz  rdi, rax
0x1800d585c  mov     rsi, rcx
0x1800d585f  mov     rax, [rbp+200h+var_248]
0x1800d5863  test    rax, rax
0x1800d5866  cmovnz  rsi, rax
0x1800d586a  mov     [rsp+300h+var_2C0], r14
0x1800d586f  mov     [rsp+300h+var_2C8], rsi
0x1800d5874  mov     [rsp+300h+var_2D0], rdi; char *
0x1800d5879  lea     rax, aAssetWithTypeL_0; "Asset with type [%ls] and unique id [%l"...
0x1800d5880  mov     qword ptr [rsp+300h+var_2D8], rax; int
0x1800d5885  mov     dword ptr [rsp+300h+var_2E0], 0Dh; char *
0x1800d588d  lea     r9, aWindowsCompatA_39; "Windows::Compat::Appraiser::InventoryUt"...
0x1800d5894  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800d589b  mov     edx, 11Ch; bool
0x1800d58a0  mov     ecx, 1; this
0x1800d58a5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800d58aa  lea     rcx, [rbp+200h+var_160]; this
0x1800d58b1  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800d58b6  lea     rcx, [rbp+200h+var_160]
0x1800d58bd  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800d58c4  test    rax, rax
0x1800d58c7  cmovnz  rcx, rax; this
0x1800d58cb  mov     rdx, r13
0x1800d58ce  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800d58d7  lea     r8, [rbp+200h+var_D0]; char *
0x1800d58de  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800d58e3  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800d58ea  jz      short loc_1800D58F8
0x1800d58ec  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800d58f3  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800d58f8  mov     rbx, cs:qword_1802C9628
0x1800d58ff  mov     eax, [rbx]
0x1800d5901  cmp     eax, 5
0x1800d5904  jbe     loc_1800D5A7E
0x1800d590a  mov     rcx, [rbx+18h]
0x1800d590e  mov     rax, [rbx+10h]
0x1800d5912  mov     rdx, 200000000000h
0x1800d591c  test    rdx, rax
0x1800d591f  jz      loc_1800D5A7E
0x1800d5925  mov     rax, rcx
0x1800d5928  and     rax, rdx
0x1800d592b  cmp     rax, rcx
0x1800d592e  jnz     loc_1800D5A7E
0x1800d5934  mov     qword ptr [rsp+70h], 1000000h
0x1800d593d  xorps   xmm0, xmm0
0x1800d5940  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1800d5944  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1800d5948  call    cs:__imp_GetSystemTime
0x1800d594e  movaps  xmm0, xmmword ptr [rbp+200h+SystemTime.wYear]
0x1800d5952  movdqa  [rbp+200h+var_200], xmm0
0x1800d5957  lea     rdx, [rbp+200h+var_D0]
0x1800d595e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d5962  mov     rax, rcx
0x1800d5965  inc     rax
0x1800d5968  cmp     [rdx+rax], r13b
0x1800d596c  jnz     short loc_1800D5965
0x1800d596e  lea     rdx, [rbp+200h+var_D0]
0x1800d5975  mov     [rbp+200h+var_170], rdx
0x1800d597c  inc     eax
0x1800d597e  mov     [rbp+200h+var_168], eax
0x1800d5984  mov     [rbp+200h+var_164], r13d
0x1800d598b  lea     rax, [rsp+70h]
0x1800d5990  mov     [rbp+200h+var_180], rax
0x1800d5997  mov     [rbp+200h+var_178], 8
0x1800d59a2  mov     r8d, 2
0x1800d59a8  test    r14, r14
0x1800d59ab  jz      short loc_1800D59CD
0x1800d59ad  mov     rdx, r14
0x1800d59b0  mov     rax, rcx
0x1800d59b3  inc     rax
0x1800d59b6  cmp     [r14+rax*2], r13w
0x1800d59bb  jnz     short loc_1800D59B3
0x1800d59bd  lea     eax, ds:2[rax*2]
0x1800d59c4  lea     r9, szValueBuf
0x1800d59cb  jmp     short loc_1800D59DA
  ... truncated ...
```
