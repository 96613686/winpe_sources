# Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation(Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::AssetProperties *,ulong)

- ea: `0x180206540`
- end: `0x180206b03`
- name: `?DoDecisionAggregation@SummaryAggregator@Appraiser@Compat@Windows@@UEAAJPEAVIPropertyListEnumerator@234@PEAUAssetProperties@234@K@Z`
- size: `1475`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SummaryAggregator *__hidden this, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::AssetProperties *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180013f90`
- `0x1800144c4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180083278`
- `0x180083390`
- `0x18008bc08`
- `0x1800ad71c`
- `0x180206248`
- `0x180206540`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18020657e`
- `KERNEL32!GetProcessHeap` at `0x1802065b9`
- `KERNEL32!GetProcessHeap` at `0x1802065cb`
- `KERNEL32!GetProcessHeap` at `0x18020657e`
- `KERNEL32!GetProcessHeap` at `0x1802065b9`
- `KERNEL32!GetProcessHeap` at `0x1802065cb`
- `KERNEL32!HeapFree` at `0x180206ac8`
- `KERNEL32!HeapFree` at `0x180206ae7`
- `KERNEL32!HeapFree` at `0x180206ac8`
- `KERNEL32!HeapFree` at `0x180206ae7`

## string_xrefs

- `0x18020660d`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x18020666d`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x1802066dc`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206760`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206843`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x1802068da`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x18020698e`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x1802069ec`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206a20`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206a63`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206aa0`: `Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation`
- `0x180206614`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206674`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x1802066e3`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206767`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x18020684a`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x1802068e1`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206995`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x1802069f3`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206a27`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206a6a`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`
- `0x180206aa7`: `onecore\base\appcompat\appraiser\decisionaggregators\summary.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation(
        const unsigned __int16 **this,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a2,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator **a3,
        unsigned int a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  struct Windows::Compat::Appraiser::IPropertyAppender *v8; // r13
  struct Windows::Compat::Appraiser::IPropertyAppender *v9; // r12
  unsigned int v10; // esi
  __int64 v11; // rdi
  int RequiredSingleValue; // eax
  int appended; // ebx
  __int64 v14; // rdi
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *TargetVersionEnumerator; // rdi
  int v16; // eax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rsi
  char *v19; // r14
  unsigned int *v20; // rax
  unsigned int v21; // r10d
  const unsigned __int16 **v22; // rcx
  __int64 v23; // rax
  unsigned int *v24; // rax
  unsigned int v25; // r10d
  const unsigned __int16 **v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  char v29; // dl
  const char *v30; // rax
  int v31; // eax
  char *v33; // [rsp+20h] [rbp-89h]
  const char *v34; // [rsp+28h] [rbp-81h]
  char *v35; // [rsp+30h] [rbp-79h]
  wchar_t *String1[2]; // [rsp+40h] [rbp-69h] BYREF
  HANDLE hHeap[2]; // [rsp+50h] [rbp-59h]
  __int128 v38; // [rsp+60h] [rbp-49h]
  LPVOID lpMem[2]; // [rsp+70h] [rbp-39h]
  HANDLE v40[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v41; // [rsp+90h] [rbp-19h]
  LPVOID v42[2]; // [rsp+A0h] [rbp-9h]
  int v43; // [rsp+B0h] [rbp+7h]
  __int64 v44; // [rsp+B8h] [rbp+Fh]

  v44 = -2;
  String1[0] = 0;
  *(_OWORD *)v42 = 0;
  v40[0] = GetProcessHeap();
  v42[0] = (LPVOID)16;
  v41 = 0;
  v42[1] = 0;
  v40[1] = (HANDLE)16;
  v43 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(v40, v6, v7, 16);
  GetProcessHeap();
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v38 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v8 = 0;
  v9 = 0;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x80u,
      "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
      "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  v10 = 0;
  if ( a4 )
  {
    do
    {
      if ( !v9 )
      {
        v11 = 4LL * v10;
        RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                                (const unsigned __int16 **)String1,
                                L"AssetType",
                                a3[v11]);
        appended = RequiredSingleValue;
        if ( RequiredSingleValue < 0 )
        {
          v30 = "Error getting asset type: [0x%x].";
          v29 = -115;
          goto LABEL_65;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x8Du,
            "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
            "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
            "Error getting asset type: [0x%x].",
            RequiredSingleValue);
        if ( !wcscmp_0(String1[0], L"Summary") )
          v9 = a3[v11 + 3];
      }
      if ( !v8 )
      {
        v14 = 4LL * v10;
        appended = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                     (const unsigned __int16 **)String1,
                     L"AssetType",
                     a3[v14]);
        if ( appended < 0 )
        {
          v30 = "Error getting asset type: [0x%x].";
          v29 = -104;
          goto LABEL_65;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x98u,
            "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
            "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
            "Error getting asset type: [0x%x].",
            appended);
        if ( !wcscmp_0(String1[0], L"GatedState") )
          v8 = a3[v14 + 3];
      }
      TargetVersionEnumerator = Windows::Compat::Appraiser::Utilities::GetTargetVersionEnumerator(
                                  this[2],
                                  a3[4 * v10 + 2]);
      if ( !TargetVersionEnumerator )
      {
        appended = -2147019873;
        LODWORD(v33) = -2147019873;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          163,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
          "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
          v33,
          (int)"Failed to convert to target version property enumerator.",
          v35);
        goto LABEL_67;
      }
      v16 = Windows::Compat::Appraiser::SummaryAggregator::AddDecisionsToList((RtlStringArray *)v40);
      appended = v16;
      if ( v16 < 0 )
      {
        LODWORD(v35) = v16;
        LODWORD(v33) = v16;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          169,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
          "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
          v33,
          (int)"Error adding decisions to list: [0x%x].",
          v35);
        (*(void (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *))(*(_QWORD *)TargetVersionEnumerator
                                                                                             + 32LL))(TargetVersionEnumerator);
        goto LABEL_67;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xA9u,
          "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
          "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
          "Error adding decisions to list: [0x%x].",
          v16);
      (*(void (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *))(*(_QWORD *)TargetVersionEnumerator
                                                                                           + 32LL))(TargetVersionEnumerator);
      ++v10;
    }
    while ( v10 < a4 );
    if ( !v9 )
      goto LABEL_64;
    LODWORD(String1[0]) = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *))(*(_QWORD *)v9 + 8LL))(v9);
    v17 = 0;
    v18 = v41;
    if ( (_QWORD)v41 )
    {
      v19 = (char *)v42[1];
      while ( v17 < (unsigned __int64)v38 )
      {
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v17)
          || (v20 = (unsigned int *)((char *)lpMem[1] + (unsigned __int64)hHeap[1] * v17), v20 < lpMem[1]) )
        {
          v20 = 0;
        }
        v21 = *v20;
        v22 = 0;
        if ( v17 < v18 )
        {
          v23 = (unsigned __int64)v40[1] * v17;
          if ( !is_mul_ok((unsigned __int64)v40[1], v17)
            || (v22 = (const unsigned __int16 **)&v19[v23], &v19[v23] < v19) )
          {
            v22 = 0;
          }
        }
        appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(
                     *v22,
                     v21,
                     (unsigned int *)String1,
                     v9);
        if ( appended < 0 )
        {
          v30 = "Error appending property: [0x%x].";
          v29 = -56;
          goto LABEL_65;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xC8u,
            "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
            "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
            "Error appending property: [0x%x].",
            appended);
        if ( v8 )
        {
          v24 = 0;
          if ( v17 < (unsigned __int64)v38 )
          {
            if ( !is_mul_ok((unsigned __int64)hHeap[1], v17)
              || (v24 = (unsigned int *)((char *)lpMem[1] + (unsigned __int64)hHeap[1] * v17), v24 < lpMem[1]) )
            {
              v24 = 0;
            }
          }
          v25 = *v24;
          v26 = 0;
          if ( v17 < v18 )
          {
            v27 = (unsigned __int64)v40[1] * v17;
            if ( !is_mul_ok((unsigned __int64)v40[1], v17)
              || (v26 = (const unsigned __int16 **)&v19[v27], &v19[v27] < v19) )
            {
              v26 = 0;
            }
          }
          appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(
                       *v26,
                       v25,
                       (unsigned int *)String1,
                       v8);
          if ( appended < 0 )
          {
            v30 = "Error appending property: [0x%x].";
            v29 = -48;
            goto LABEL_65;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xD0u,
              "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
              "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
              "Error appending property: [0x%x].",
              appended);
        }
        if ( ++v17 >= v18 )
          break;
      }
    }
    v28 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
            L"ApplicableTargetVersion",
            this[2],
            (unsigned int *)String1,
            v9);
    appended = v28;
    if ( v28 < 0 )
    {
      LODWORD(v35) = v28;
      v34 = "Error appending property: [0x%x].";
      v29 = -40;
      goto LABEL_66;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xD8u,
        "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
        "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
        "Error appending property: [0x%x].",
        v28);
    if ( v8 )
    {
      v31 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ApplicableTargetVersion",
              this[2],
              (unsigned int *)String1,
              v8);
      appended = v31;
      if ( v31 < 0 )
      {
        LODWORD(v35) = v31;
        v34 = "Error appending property: [0x%x].";
        v29 = -32;
        goto LABEL_66;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xE0u,
          "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
          "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
          "Error appending property: [0x%x].",
          v31);
    }
    appended = 0;
  }
  else
  {
LABEL_64:
    appended = -2147019873;
    v30 = "Missing summary asset: [0x%x].";
    v29 = -75;
LABEL_65:
    LODWORD(v35) = appended;
    LODWORD(v34) = (_DWORD)v30;
LABEL_66:
    LODWORD(v33) = appended;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v29,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\summary.cpp",
      "Windows::Compat::Appraiser::SummaryAggregator::DoDecisionAggregation",
      v33,
      (int)v34,
      v35);
  }
LABEL_67:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  RtlStringArray::Clear((RtlStringArray *)v40);
  if ( v42[1] )
    HeapFree(v40[0], 0, v42[1]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180206540  mov     [rsp-8+arg_0], rcx
0x180206545  push    rbp
0x180206546  push    rbx
0x180206547  push    rsi
0x180206548  push    rdi
0x180206549  push    r12
0x18020654b  push    r13
0x18020654d  push    r14
0x18020654f  push    r15
0x180206551  lea     rbp, [rsp-1Fh]
0x180206556  sub     rsp, 0C8h
0x18020655d  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x180206565  mov     r15d, r9d
0x180206568  mov     r14, r8
0x18020656b  mov     [rbp+57h+String1], 0
0x180206573  xorps   xmm0, xmm0
0x180206576  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18020657a  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18020657e  call    cs:__imp_GetProcessHeap
0x180206584  mov     [rbp+57h+var_80], rax
0x180206588  mov     ebx, 10h
0x18020658d  mov     [rbp+57h+var_60], rbx
0x180206591  xorps   xmm0, xmm0
0x180206594  movdqu  [rbp+57h+var_70], xmm0
0x180206599  mov     [rbp+57h+var_60+8], 0
0x1802065a1  mov     [rbp+57h+var_80+8], rbx
0x1802065a5  mov     [rbp+57h+var_50], 0
0x1802065ac  mov     r9d, ebx
0x1802065af  lea     rcx, [rbp+57h+var_80]
0x1802065b3  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1802065b8  nop
0x1802065b9  call    cs:__imp_GetProcessHeap
0x1802065bf  nop
0x1802065c0  xorps   xmm0, xmm0
0x1802065c3  movups  xmmword ptr [rbp+57h+hHeap], xmm0
0x1802065c7  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x1802065cb  call    cs:__imp_GetProcessHeap
0x1802065d1  mov     [rbp+57h+hHeap], rax
0x1802065d5  mov     [rbp+57h+lpMem], rbx
0x1802065d9  xorps   xmm0, xmm0
0x1802065dc  movdqu  [rbp+57h+var_A0], xmm0
0x1802065e1  mov     [rbp+57h+lpMem+8], 0
0x1802065e9  mov     [rbp+57h+hHeap+8], 8
0x1802065f1  xor     r13d, r13d
0x1802065f4  xor     r12d, r12d
0x1802065f7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802065fd  test    al, 1
0x1802065ff  jz      short loc_180206623
0x180206601  mov     dword ptr [rsp+100h+var_E0], r12d
0x180206606  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x18020660d  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x180206614  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020661b  lea     ecx, [rbx+70h]; unsigned int
0x18020661e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180206623  xor     esi, esi
0x180206625  test    r15d, r15d
0x180206628  jz      loc_180206A82
0x18020662e  test    r12, r12
0x180206631  jnz     short loc_18020669E
0x180206633  mov     edi, esi
0x180206635  shl     rdi, 5
0x180206639  mov     r8, [rdi+r14]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x18020663d  lea     rdx, aAssettype; "AssetType"
0x180206644  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x180206648  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x18020664d  mov     ebx, eax
0x18020664f  test    eax, eax
0x180206651  js      loc_180206939
0x180206657  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020665d  test    cl, 1
0x180206660  jz      short loc_180206685
0x180206662  mov     dword ptr [rsp+100h+var_E0], eax
0x180206666  lea     r9, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x18020666d  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x180206674  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020667b  mov     ecx, 8Dh; unsigned int
0x180206680  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180206685  lea     rdx, aSummary; "Summary"
0x18020668c  mov     rcx, [rbp+57h+String1]; String1
0x180206690  call    wcscmp_0
0x180206695  test    eax, eax
0x180206697  jnz     short loc_18020669E
0x180206699  mov     r12, [rdi+r14+18h]
0x18020669e  test    r13, r13
0x1802066a1  jnz     short loc_18020670D
0x1802066a3  mov     edi, esi
0x1802066a5  shl     rdi, 5
0x1802066a9  mov     r8, [rdi+r14]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1802066ad  lea     rdx, aAssettype; "AssetType"
0x1802066b4  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x1802066b8  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1802066bd  mov     ebx, eax
0x1802066bf  test    eax, eax
0x1802066c1  js      loc_18020694A
0x1802066c7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802066cd  test    al, 1
0x1802066cf  jz      short loc_1802066F4
0x1802066d1  mov     dword ptr [rsp+100h+var_E0], ebx
0x1802066d5  lea     r9, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x1802066dc  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x1802066e3  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x1802066ea  mov     ecx, 98h; unsigned int
0x1802066ef  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1802066f4  lea     rdx, aGatedstate; "GatedState"
0x1802066fb  mov     rcx, [rbp+57h+String1]; String1
0x1802066ff  call    wcscmp_0
0x180206704  test    eax, eax
0x180206706  jnz     short loc_18020670D
0x180206708  mov     r13, [rdi+r14+18h]
0x18020670d  mov     edx, esi
0x18020670f  shl     rdx, 5
0x180206713  mov     rdx, [rdx+r14+10h]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x180206718  mov     rax, [rbp+57h+arg_0]
0x18020671c  mov     rcx, [rax+10h]; unsigned __int16 *
0x180206720  call    ?GetTargetVersionEnumerator@Utilities@Appraiser@Compat@Windows@@SAPEAVIPropertyListEnumerator@234@PEBGPEAV5234@@Z; Windows::Compat::Appraiser::Utilities::GetTargetVersionEnumerator(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x180206725  mov     rdi, rax
0x180206728  test    rax, rax
0x18020672b  jz      loc_180206A4E
0x180206731  mov     r8, rax
0x180206734  lea     rdx, [rbp+57h+hHeap]
0x180206738  lea     rcx, [rbp+57h+var_80]; this
0x18020673c  call    ?AddDecisionsToList@SummaryAggregator@Appraiser@Compat@Windows@@CAJPEAVRtlStringArray@@PEAV?$RtlArray@K@@PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::SummaryAggregator::AddDecisionsToList(RtlStringArray *,RtlArray<ulong> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x180206741  mov     ebx, eax
0x180206743  test    eax, eax
0x180206745  js      loc_180206A0C
0x18020674b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180206751  test    al, 1
0x180206753  jz      short loc_180206778
0x180206755  mov     dword ptr [rsp+100h+var_E0], ebx
0x180206759  lea     r9, aErrorAddingDec; "Error adding decisions to list: [0x%x]."
0x180206760  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x180206767  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020676e  mov     ecx, 0A9h; unsigned int
0x180206773  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180206778  mov     rax, [rdi]
0x18020677b  mov     rcx, rdi
0x18020677e  mov     rax, [rax+20h]
0x180206782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206787  inc     esi
0x180206789  cmp     esi, r15d
0x18020678c  jb      loc_18020662E
0x180206792  xor     r15d, r15d
0x180206795  test    r12, r12
0x180206798  jz      loc_180206A82
0x18020679e  mov     rax, [r12]
0x1802067a2  mov     rcx, r12
0x1802067a5  mov     rax, [rax+8]
0x1802067a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802067ae  mov     dword ptr [rbp+57h+String1], eax
0x1802067b1  mov     edi, r15d
0x1802067b4  lea     r14, aErrorAppending_2; "Error appending property: [0x%x]."
0x1802067bb  mov     rsi, qword ptr [rbp+57h+var_70]
0x1802067bf  test    rsi, rsi
0x1802067c2  jz      loc_180206905
0x1802067c8  mov     r14, [rbp+57h+var_60+8]
0x1802067cc  cmp     rdi, qword ptr [rbp+57h+var_A0]
0x1802067d0  jnb     loc_1802068FE
0x1802067d6  mov     rax, rdi
0x1802067d9  mul     [rbp+57h+hHeap+8]
0x1802067dd  test    rdx, rdx
0x1802067e0  jnz     short loc_1802067EC
0x1802067e2  add     rax, [rbp+57h+lpMem+8]
0x1802067e6  cmp     rax, [rbp+57h+lpMem+8]
0x1802067ea  jnb     short loc_1802067EF
0x1802067ec  mov     rax, r15
0x1802067ef  mov     r10d, [rax]
0x1802067f2  mov     rcx, r15
0x1802067f5  cmp     rdi, rsi
0x1802067f8  jnb     short loc_180206812
0x1802067fa  mov     rax, rdi
0x1802067fd  mul     [rbp+57h+var_80+8]
0x180206801  test    rdx, rdx
0x180206804  jnz     short loc_18020680F
0x180206806  lea     rcx, [r14+rax]
0x18020680a  cmp     rcx, r14
0x18020680d  jnb     short loc_180206812
0x18020680f  mov     rcx, r15
0x180206812  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x180206815  lea     r8, [rbp+57h+String1]; unsigned int *
0x180206819  mov     edx, r10d; unsigned int
0x18020681c  mov     rcx, [rcx]; unsigned __int16 *
0x18020681f  call    ?CreateAndAppendDwordProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBGKPEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(ushort const *,ulong,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x180206824  mov     ebx, eax
0x180206826  test    eax, eax
0x180206828  js      loc_18020696C
0x18020682e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180206834  test    al, 1
0x180206836  jz      short loc_18020685B
0x180206838  mov     dword ptr [rsp+100h+var_E0], ebx
0x18020683c  lea     r9, aErrorAppending_2; "Error appending property: [0x%x]."
0x180206843  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x18020684a  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x180206851  mov     ecx, 0C8h; unsigned int
0x180206856  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020685b  test    r13, r13
0x18020685e  jz      loc_1802068F2
0x180206864  mov     rax, r15
0x180206867  cmp     rdi, qword ptr [rbp+57h+var_A0]
0x18020686b  jnb     short loc_180206886
0x18020686d  mov     rax, rdi
0x180206870  mul     [rbp+57h+hHeap+8]
0x180206874  test    rdx, rdx
0x180206877  jnz     short loc_180206883
0x180206879  add     rax, [rbp+57h+lpMem+8]
0x18020687d  cmp     rax, [rbp+57h+lpMem+8]
0x180206881  jnb     short loc_180206886
0x180206883  mov     rax, r15
0x180206886  mov     r10d, [rax]
0x180206889  mov     rcx, r15
0x18020688c  cmp     rdi, rsi
0x18020688f  jnb     short loc_1802068A9
0x180206891  mov     rax, rdi
0x180206894  mul     [rbp+57h+var_80+8]
0x180206898  test    rdx, rdx
0x18020689b  jnz     short loc_1802068A6
0x18020689d  lea     rcx, [r14+rax]
0x1802068a1  cmp     rcx, r14
0x1802068a4  jnb     short loc_1802068A9
0x1802068a6  mov     rcx, r15
0x1802068a9  mov     r9, r13; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1802068ac  lea     r8, [rbp+57h+String1]; unsigned int *
0x1802068b0  mov     edx, r10d; unsigned int
0x1802068b3  mov     rcx, [rcx]; unsigned __int16 *
0x1802068b6  call    ?CreateAndAppendDwordProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBGKPEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(ushort const *,ulong,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1802068bb  mov     ebx, eax
0x1802068bd  test    eax, eax
0x1802068bf  js      loc_18020695B
0x1802068c5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802068cb  test    al, 1
0x1802068cd  jz      short loc_1802068F2
0x1802068cf  mov     dword ptr [rsp+100h+var_E0], ebx
0x1802068d3  lea     r9, aErrorAppending_2; "Error appending property: [0x%x]."
0x1802068da  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x1802068e1  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x1802068e8  mov     ecx, 0D0h; unsigned int
0x1802068ed  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1802068f2  inc     rdi
0x1802068f5  cmp     rdi, rsi
0x1802068f8  jb      loc_1802067CC
0x1802068fe  lea     r14, aErrorAppending_2; "Error appending property: [0x%x]."
0x180206905  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x180206908  lea     r8, [rbp+57h+String1]; unsigned int *
0x18020690c  mov     rdi, [rbp+57h+arg_0]
0x180206910  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180206914  lea     rcx, aApplicabletarg_0; "ApplicableTargetVersion"
0x18020691b  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x180206920  mov     ebx, eax
0x180206922  test    eax, eax
0x180206924  jns     short loc_18020697D
0x180206926  mov     dword ptr [rsp+100h+var_D0], eax
0x18020692a  mov     qword ptr [rsp+100h+var_D8], r14
0x18020692f  mov     edx, 0D8h
0x180206934  jmp     loc_180206A9C
0x180206939  lea     rax, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x180206940  mov     edx, 8Dh
0x180206945  jmp     loc_180206A93
0x18020694a  lea     rax, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x180206951  mov     edx, 98h
0x180206956  jmp     loc_180206A93
0x18020695b  lea     rax, aErrorAppending_2; "Error appending property: [0x%x]."
0x180206962  mov     edx, 0D0h
0x180206967  jmp     loc_180206A93
0x18020696c  lea     rax, aErrorAppending_2; "Error appending property: [0x%x]."
0x180206973  mov     edx, 0C8h
0x180206978  jmp     loc_180206A93
0x18020697d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180206983  test    al, 1
0x180206985  jz      short loc_1802069A6
0x180206987  mov     dword ptr [rsp+100h+var_E0], ebx
0x18020698b  mov     r9, r14; char *
0x18020698e  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x180206995  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020699c  mov     ecx, 0D8h; unsigned int
0x1802069a1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1802069a6  test    r13, r13
0x1802069a9  jz      short loc_180206A04
0x1802069ab  mov     r9, r13; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1802069ae  lea     r8, [rbp+57h+String1]; unsigned int *
0x1802069b2  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1802069b6  lea     rcx, aApplicabletarg_0; "ApplicableTargetVersion"
0x1802069bd  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1802069c2  mov     ebx, eax
0x1802069c4  test    eax, eax
0x1802069c6  jns     short loc_1802069DB
0x1802069c8  mov     dword ptr [rsp+100h+var_D0], eax
0x1802069cc  mov     qword ptr [rsp+100h+var_D8], r14
0x1802069d1  mov     edx, 0E0h
0x1802069d6  jmp     loc_180206A9C
0x1802069db  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802069e1  test    al, 1
0x1802069e3  jz      short loc_180206A04
0x1802069e5  mov     dword ptr [rsp+100h+var_E0], ebx
0x1802069e9  mov     r9, r14; char *
0x1802069ec  lea     r8, aWindowsCompatA_471; "Windows::Compat::Appraiser::SummaryAggr"...
0x1802069f3  lea     rdx, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\appraiser\\de"...
0x1802069fa  mov     ecx, 0E0h; unsigned int
0x1802069ff  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180206a04  mov     ebx, r15d
0x180206a07  jmp     loc_180206AB9
0x180206a0c  mov     dword ptr [rsp+100h+var_D0], ebx; char *
  ... truncated ...
```
