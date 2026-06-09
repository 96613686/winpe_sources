# Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents(RtlArray<Windows::Compat::Appraiser::IAsset *> *,RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)

- ea: `0x1800ea7c4`
- end: `0x1800eadae`
- name: `?SendTelemetryEvents@TelemetryOutputter@Appraiser@Compat@Windows@@AEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@0PEAVIPropertyListEnumerator@234@@Z`
- size: `1514`
- prototype: `__int64 __fastcall(int, int, int, struct Windows::Compat::Appraiser::IPropertyListEnumerator *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800e7140`

## callees

- `0x18002c360`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800390b0`
- `0x1800ad680`
- `0x1800ad97c`
- `0x1800e7d70`
- `0x1800ea7c4`
- `0x1800ebe6c`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800ea7fe`
- `KERNEL32!GetProcessHeap` at `0x1800ea832`
- `KERNEL32!GetProcessHeap` at `0x1800ea86a`
- `KERNEL32!GetProcessHeap` at `0x1800ea888`
- `KERNEL32!GetProcessHeap` at `0x1800ea89a`
- `KERNEL32!GetProcessHeap` at `0x1800ea7fe`
- `KERNEL32!GetProcessHeap` at `0x1800ea832`
- `KERNEL32!GetProcessHeap` at `0x1800ea86a`
- `KERNEL32!GetProcessHeap` at `0x1800ea888`
- `KERNEL32!GetProcessHeap` at `0x1800ea89a`
- `KERNEL32!HeapFree` at `0x1800ead65`
- `KERNEL32!HeapFree` at `0x1800ead7b`
- `KERNEL32!HeapFree` at `0x1800ead92`
- `KERNEL32!HeapFree` at `0x1800ead65`
- `KERNEL32!HeapFree` at `0x1800ead7b`
- `KERNEL32!HeapFree` at `0x1800ead92`

## string_xrefs

- `0x1800ea8d6`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ea91d`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ea950`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ea9a0`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ea9ce`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800eaa2d`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800eaa7e`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800eaaff`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800eac94`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ea8cf`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800ea916`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800ea949`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800ea999`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800ea9c7`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800eaa26`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800eaa77`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800eab06`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`
- `0x1800eac8d`: `Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents(
        Windows::Compat::Appraiser::TelemetryOutputter *a1,
        unsigned __int64 *a2,
        int a3,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a4)
{
  __int64 v8; // rdx
  char *v9; // rdi
  int v10; // eax
  int VersionedAssets; // ebx
  __int64 v12; // rdx
  char v13; // dl
  int v14; // eax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rsi
  struct Windows::Compat::Appraiser::IAsset **v18; // rdx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  struct Windows::Compat::Appraiser::IAsset *v21; // r12
  int UniqueIdentifier; // eax
  const unsigned __int16 **v23; // rdx
  struct Windows::Compat::Appraiser::UniqueIdentifierTable *v24; // r8
  const char *v25; // rcx
  char v26; // dl
  unsigned __int64 v27; // rdi
  struct Windows::Compat::Appraiser::IAsset **v28; // rax
  struct Windows::Compat::Appraiser::IAsset *v29; // r15
  unsigned __int16 *v30; // rax
  struct Windows::Compat::Appraiser::UniqueIdentifierTable *v31; // r8
  int v32; // ecx
  const unsigned __int16 **v33; // rdx
  unsigned __int16 *v34; // rax
  int v35; // ecx
  int v36; // edx
  unsigned __int64 i; // rdi
  struct Windows::Compat::Appraiser::IAsset **v38; // rax
  struct Windows::Compat::Appraiser::IAsset *v39; // rsi
  int RequiredSingleValue; // eax
  unsigned __int64 v41; // rsi
  unsigned __int64 j; // r14
  char *v43; // rax
  char *v44; // rcx
  __int64 v45; // rax
  char *v46; // rax
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v48; // [rsp+20h] [rbp-E0h]
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v49; // [rsp+20h] [rbp-E0h]
  const char *v50; // [rsp+28h] [rbp-D8h]
  char *v51; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v53; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v54[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v55; // [rsp+68h] [rbp-98h]
  LPVOID v56[2]; // [rsp+78h] [rbp-88h]
  HANDLE hHeap[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v58; // [rsp+98h] [rbp-68h]
  __int128 v59; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v60; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v61; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v62[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v63; // [rsp+D8h] [rbp-28h]
  LPVOID lpMem[2]; // [rsp+E8h] [rbp-18h]
  HANDLE ProcessHeap; // [rsp+F8h] [rbp-8h]
  __int64 v66; // [rsp+100h] [rbp+0h]
  __int128 v67; // [rsp+108h] [rbp+8h]
  __int128 v68; // [rsp+118h] [rbp+18h]
  __int64 v69; // [rsp+128h] [rbp+28h]

  v69 = -2;
  v54[0] = GetProcessHeap();
  v56[0] = (LPVOID)16;
  v55 = 0;
  v56[1] = 0;
  v54[1] = (HANDLE)8;
  v62[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v63 = 0;
  lpMem[1] = 0;
  v62[1] = (HANDLE)8;
  v53 = 0;
  v52 = 0;
  v60 = 0;
  v61 = 0;
  ProcessHeap = GetProcessHeap();
  v68 = 0x10u;
  v67 = 0;
  v66 = 8;
  GetProcessHeap();
  hHeap[0] = GetProcessHeap();
  v59 = 0x10u;
  v58 = 0;
  v9 = 0;
  hHeap[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x589u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
      "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  v10 = RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(v54, v8, 256, 256);
  VersionedAssets = v10;
  if ( v10 < 0 )
  {
    LODWORD(v51) = v10;
    LODWORD(v48) = v10;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      149,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
      "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
      (const char *)v48,
      (int)"RtlArary init failure: [0x%x].",
      v51);
    goto LABEL_66;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x595u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
      "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
      "RtlArary init failure: [0x%x].",
      v10);
  VersionedAssets = Windows::Compat::Appraiser::TelemetryOutputter::GetVersionedAssets(
                      (int)a1,
                      (int)v54,
                      (int)hHeap,
                      a3,
                      a4);
  if ( VersionedAssets >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x598u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
        "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
        "Error getting versioned telemetry assets: [0x%x].",
        VersionedAssets);
    if ( *((_BYTE *)a1 + 1353) )
    {
      v14 = RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(v62, v12, 256, 256);
      VersionedAssets = v14;
      if ( v14 < 0 )
      {
        LODWORD(v51) = v14;
        v50 = "RtlArary init failure: [0x%x].";
        v13 = -99;
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x59Du,
          "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
          "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
          "RtlArary init failure: [0x%x].",
          v14);
      VersionedAssets = Windows::Compat::Appraiser::TelemetryOutputter::GetVersionedAssets(
                          (int)a1,
                          (int)v62,
                          (int)hHeap,
                          (int)a2,
                          a4);
      if ( VersionedAssets < 0 )
      {
        v13 = -96;
        goto LABEL_9;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x5A0u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
          "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
          "Error getting versioned telemetry assets: [0x%x].",
          VersionedAssets);
      a2 = (unsigned __int64 *)v62;
    }
    v15 = a2[2];
    v16 = v55;
    if ( !v15 )
    {
LABEL_55:
      for ( i = 0; i < v16; ++i )
      {
        v38 = 0;
        if ( i < v16 )
        {
          if ( !is_mul_ok((unsigned __int64)v54[1], i)
            || (v38 = (struct Windows::Compat::Appraiser::IAsset **)((char *)v56[1] + (unsigned __int64)v54[1] * i),
                v38 < v56[1]) )
          {
            v38 = 0;
          }
        }
        v39 = *v38;
        RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                                &v52,
                                L"AssetType",
                                *v38,
                                1);
        if ( RequiredSingleValue >= 0 )
        {
          Windows::Compat::Appraiser::TelemetryOutputter::WriteAllDiffEventsForAsset(a1, 0, v39, v52);
        }
        else
        {
          LODWORD(v51) = RequiredSingleValue;
          LODWORD(v49) = RequiredSingleValue;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            3,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
            "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
            (const char *)v49,
            (int)"Asset is missing a Type: [0x%x]",
            v51);
        }
      }
      VersionedAssets = 0;
      goto LABEL_65;
    }
    v17 = 0;
    while ( 1 )
    {
      v18 = 0;
      if ( v17 < v15 )
      {
        v19 = a2[1] * v17;
        if ( !is_mul_ok(a2[1], v17)
          || (v20 = a2[5], v18 = (struct Windows::Compat::Appraiser::IAsset **)(v20 + v19), v20 + v19 < v20) )
        {
          v18 = 0;
        }
      }
      v21 = *v18;
      UniqueIdentifier = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(&v53, L"AssetType", *v18, 1);
      if ( UniqueIdentifier >= 0 )
      {
        UniqueIdentifier = Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(
                             (const unsigned __int16 **)&v60,
                             v23,
                             v24,
                             v21);
        if ( UniqueIdentifier >= 0 )
        {
          v27 = 0;
          if ( !v16 )
            goto LABEL_52;
          do
          {
            v28 = 0;
            if ( v27 < v16 )
            {
              if ( !is_mul_ok((unsigned __int64)v54[1], v27)
                || (v28 = (struct Windows::Compat::Appraiser::IAsset **)((char *)v56[1] + (unsigned __int64)v54[1] * v27),
                    v28 < v56[1]) )
              {
                v28 = 0;
              }
            }
            v29 = *v28;
            if ( (int)Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(&v52, L"AssetType", *v28, 1) >= 0 )
            {
              v30 = v53;
              v31 = (struct Windows::Compat::Appraiser::UniqueIdentifierTable *)((char *)v52 - (char *)v53);
              do
              {
                v32 = *(unsigned __int16 *)((char *)v31 + (_QWORD)v30);
                v33 = (const unsigned __int16 **)((unsigned int)*v30 - v32);
                if ( (_DWORD)v33 )
                  break;
                ++v30;
              }
              while ( v32 );
              if ( !(_DWORD)v33
                && (int)Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(
                          (const unsigned __int16 **)&v61,
                          v33,
                          v31,
                          v29) >= 0 )
              {
                v34 = v60;
                do
                {
                  v35 = *(unsigned __int16 *)((char *)v34 + (char *)v61 - (char *)v60);
                  v36 = *v34 - v35;
                  if ( v36 )
                    break;
                  ++v34;
                }
                while ( v35 );
                if ( !v36 )
                  break;
              }
            }
            ++v27;
          }
          while ( v27 < v16 );
          if ( v27 < v16 )
          {
            RtlArray<Windows::Compat::Appraiser::Table *>::Delete(v54, v27);
            v16 = v55;
          }
          else
          {
LABEL_52:
            v29 = 0;
          }
          Windows::Compat::Appraiser::TelemetryOutputter::WriteAllDiffEventsForAsset(a1, v21, v29, v53);
          goto LABEL_54;
        }
        v25 = "Asset is missing a Unique Identifier: [0x%x]";
        v26 = -68;
      }
      else
      {
        v25 = "Asset is missing a Type: [0x%x].";
        v26 = -76;
      }
      LODWORD(v51) = UniqueIdentifier;
      LODWORD(v49) = UniqueIdentifier;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v26,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
        "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
        (const char *)v49,
        (int)v25,
        v51);
LABEL_54:
      ++v17;
      v15 = a2[2];
      if ( v17 >= v15 )
        goto LABEL_55;
    }
  }
  v13 = -104;
LABEL_9:
  LODWORD(v51) = VersionedAssets;
  v50 = "Error getting versioned telemetry assets: [0x%x].";
LABEL_10:
  LODWORD(v49) = VersionedAssets;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v13,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
    "Windows::Compat::Appraiser::TelemetryOutputter::SendTelemetryEvents",
    (const char *)v49,
    (int)v50,
    v51);
LABEL_65:
  v9 = (char *)*((_QWORD *)&v59 + 1);
LABEL_66:
  v41 = 0;
  for ( j = v58; v41 < j; ++v41 )
  {
    v43 = 0;
    if ( v41 < j )
    {
      if ( !is_mul_ok((unsigned __int64)hHeap[1], v41) || (v43 = &v9[(unsigned __int64)hHeap[1] * v41], v43 < v9) )
        v43 = 0;
    }
    if ( *(_QWORD *)v43 )
    {
      v44 = 0;
      if ( v41 < j )
      {
        v45 = (unsigned __int64)hHeap[1] * v41;
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v41) || (v44 = &v9[v45], &v9[v45] < v9) )
          v44 = 0;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 32LL))(*(_QWORD *)v44);
      v46 = 0;
      if ( v41 < j )
      {
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v41) || (v46 = &v9[(unsigned __int64)hHeap[1] * v41], v46 < v9) )
          v46 = 0;
      }
      *(_QWORD *)v46 = 0;
    }
  }
  if ( v9 )
    HeapFree(hHeap[0], 0, v9);
  if ( lpMem[1] )
    HeapFree(v62[0], 0, lpMem[1]);
  if ( v56[1] )
    HeapFree(v54[0], 0, v56[1]);
  return (unsigned int)VersionedAssets;
}

```

## disassembly

```asm
0x1800ea7c4  push    rbp
0x1800ea7c6  push    rbx
0x1800ea7c7  push    rsi
0x1800ea7c8  push    rdi
0x1800ea7c9  push    r12
0x1800ea7cb  push    r13
0x1800ea7cd  push    r14
0x1800ea7cf  push    r15
0x1800ea7d1  lea     rbp, [rsp-38h]
0x1800ea7d6  sub     rsp, 138h
0x1800ea7dd  mov     [rbp+70h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800ea7e5  mov     r15, r9
0x1800ea7e8  mov     r12, r8
0x1800ea7eb  mov     r14, rdx
0x1800ea7ee  mov     r13, rcx
0x1800ea7f1  xorps   xmm0, xmm0
0x1800ea7f4  movups  xmmword ptr [rsp+170h+var_118], xmm0
0x1800ea7f9  movups  xmmword ptr [rsp+170h+var_F8], xmm0
0x1800ea7fe  call    cs:__imp_GetProcessHeap
0x1800ea804  mov     [rsp+170h+var_118], rax
0x1800ea809  mov     edi, 10h
0x1800ea80e  mov     [rsp+170h+var_F8], rdi
0x1800ea813  xorps   xmm0, xmm0
0x1800ea816  movdqu  [rsp+170h+var_108], xmm0
0x1800ea81c  xor     esi, esi
0x1800ea81e  mov     [rbp+70h+var_F8+8], rsi
0x1800ea822  lea     ebx, [rdi-8]
0x1800ea825  mov     [rsp+170h+var_118+8], rbx
0x1800ea82a  movups  xmmword ptr [rbp+70h+var_A8], xmm0
0x1800ea82e  movups  xmmword ptr [rbp+70h+lpMem], xmm0
0x1800ea832  call    cs:__imp_GetProcessHeap
0x1800ea838  mov     [rbp+70h+var_A8], rax
0x1800ea83c  mov     [rbp+70h+lpMem], rdi
0x1800ea840  xorps   xmm0, xmm0
0x1800ea843  movdqu  [rbp+70h+var_98], xmm0
0x1800ea848  mov     [rbp+70h+lpMem+8], rsi
0x1800ea84c  mov     [rbp+70h+var_A8+8], rbx
0x1800ea850  mov     [rsp+170h+var_120], rsi
0x1800ea855  mov     [rsp+170h+var_128], rsi
0x1800ea85a  mov     [rbp+70h+var_B8], rsi
0x1800ea85e  mov     [rbp+70h+var_B0], rsi
0x1800ea862  movups  [rbp+70h+var_78], xmm0
0x1800ea866  movups  [rbp+70h+var_58], xmm0
0x1800ea86a  call    cs:__imp_GetProcessHeap
0x1800ea870  mov     qword ptr [rbp+70h+var_78], rax
0x1800ea874  mov     qword ptr [rbp+70h+var_58], rdi
0x1800ea878  xorps   xmm0, xmm0
0x1800ea87b  movdqu  [rbp+70h+var_68], xmm0
0x1800ea880  mov     qword ptr [rbp+70h+var_58+8], rsi
0x1800ea884  mov     qword ptr [rbp+70h+var_78+8], rbx
0x1800ea888  call    cs:__imp_GetProcessHeap
0x1800ea88e  nop
0x1800ea88f  xorps   xmm0, xmm0
0x1800ea892  movups  xmmword ptr [rbp+70h+hHeap], xmm0
0x1800ea896  movups  [rbp+70h+var_C8], xmm0
0x1800ea89a  call    cs:__imp_GetProcessHeap
0x1800ea8a0  mov     [rbp+70h+hHeap], rax
0x1800ea8a4  mov     qword ptr [rbp+70h+var_C8], rdi
0x1800ea8a8  xorps   xmm0, xmm0
0x1800ea8ab  movdqu  [rbp+70h+var_D8], xmm0
0x1800ea8b0  mov     edi, esi
0x1800ea8b2  mov     qword ptr [rbp+70h+var_C8+8], rsi
0x1800ea8b6  mov     [rbp+70h+hHeap+8], rbx
0x1800ea8ba  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ea8c0  test    al, 1
0x1800ea8c2  jz      short loc_1800EA8E7
0x1800ea8c4  mov     dword ptr [rsp+170h+var_150], esi
0x1800ea8c8  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800ea8cf  lea     r8, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800ea8d6  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ea8dd  mov     ecx, 589h; unsigned int
0x1800ea8e2  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ea8e7  mov     eax, 100h
0x1800ea8ec  mov     r9d, eax
0x1800ea8ef  mov     r8d, eax
0x1800ea8f2  lea     rcx, [rsp+170h+var_118]
0x1800ea8f7  call    ?Initialize@?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@QEAAJPEAX_K1H@Z; RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800ea8fc  mov     ebx, eax
0x1800ea8fe  lea     rsi, aRtlararyInitFa; "RtlArary init failure: [0x%x]."
0x1800ea905  test    eax, eax
0x1800ea907  jns     short loc_1800EA938
0x1800ea909  mov     dword ptr [rsp+170h+var_140], eax; char *
0x1800ea90d  mov     qword ptr [rsp+170h+var_148], rsi; int
0x1800ea912  mov     dword ptr [rsp+170h+var_150], eax; char *
0x1800ea916  lea     r9, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800ea91d  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ea924  mov     edx, 595h; bool
0x1800ea929  mov     ecx, 1; this
0x1800ea92e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800ea933  jmp     loc_1800EACD0
0x1800ea938  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ea93e  test    al, 1
0x1800ea940  jz      short loc_1800EA961
0x1800ea942  mov     dword ptr [rsp+170h+var_150], ebx
0x1800ea946  mov     r9, rsi; char *
0x1800ea949  lea     r8, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800ea950  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ea957  mov     ecx, 595h; unsigned int
0x1800ea95c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ea961  mov     [rsp+170h+var_150], r15; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ea966  mov     r9, r12; int
0x1800ea969  lea     r8, [rbp+70h+hHeap]; int
0x1800ea96d  lea     rdx, [rsp+170h+var_118]; int
0x1800ea972  mov     rcx, r13; int
0x1800ea975  call    ?GetVersionedAssets@TelemetryOutputter@Appraiser@Compat@Windows@@AEAAJAEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@0PEAV5@PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::TelemetryOutputter::GetVersionedAssets(RtlArray<Windows::Compat::Appraiser::IAsset *> &,RtlArray<Windows::Compat::Appraiser::IAsset *> &,RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ea97a  mov     ebx, eax
0x1800ea97c  lea     rdi, aErrorGettingVe; "Error getting versioned telemetry asset"...
0x1800ea983  test    eax, eax
0x1800ea985  jns     short loc_1800EA9B6
0x1800ea987  mov     edx, 598h; bool
0x1800ea98c  mov     dword ptr [rsp+170h+var_140], ebx; char *
0x1800ea990  mov     qword ptr [rsp+170h+var_148], rdi; int
0x1800ea995  mov     dword ptr [rsp+170h+var_150], ebx; char *
0x1800ea999  lea     r9, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800ea9a0  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ea9a7  mov     ecx, 1; this
0x1800ea9ac  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800ea9b1  jmp     loc_1800EACCC
0x1800ea9b6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ea9bc  test    al, 1
0x1800ea9be  jz      short loc_1800EA9DF
0x1800ea9c0  mov     dword ptr [rsp+170h+var_150], ebx
0x1800ea9c4  mov     r9, rdi; char *
0x1800ea9c7  lea     r8, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800ea9ce  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ea9d5  mov     ecx, 598h; unsigned int
0x1800ea9da  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ea9df  cmp     byte ptr [r13+549h], 0
0x1800ea9e7  jz      loc_1800EAA93
0x1800ea9ed  mov     r8d, 100h
0x1800ea9f3  mov     r9d, r8d
0x1800ea9f6  lea     rcx, [rbp+70h+var_A8]
0x1800ea9fa  call    ?Initialize@?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@QEAAJPEAX_K1H@Z; RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800ea9ff  mov     ebx, eax
0x1800eaa01  test    eax, eax
0x1800eaa03  jns     short loc_1800EAA15
0x1800eaa05  mov     dword ptr [rsp+170h+var_140], eax
0x1800eaa09  mov     qword ptr [rsp+170h+var_148], rsi
0x1800eaa0e  mov     edx, 59Dh
0x1800eaa13  jmp     short loc_1800EA995
0x1800eaa15  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800eaa1b  test    al, 1
0x1800eaa1d  jz      short loc_1800EAA3E
0x1800eaa1f  mov     dword ptr [rsp+170h+var_150], ebx
0x1800eaa23  mov     r9, rsi; char *
0x1800eaa26  lea     r8, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800eaa2d  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800eaa34  mov     ecx, 59Dh; unsigned int
0x1800eaa39  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800eaa3e  mov     [rsp+170h+var_150], r15; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800eaa43  mov     r9, r14; int
0x1800eaa46  lea     r8, [rbp+70h+hHeap]; int
0x1800eaa4a  lea     rdx, [rbp+70h+var_A8]; int
0x1800eaa4e  mov     rcx, r13; int
0x1800eaa51  call    ?GetVersionedAssets@TelemetryOutputter@Appraiser@Compat@Windows@@AEAAJAEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@0PEAV5@PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::TelemetryOutputter::GetVersionedAssets(RtlArray<Windows::Compat::Appraiser::IAsset *> &,RtlArray<Windows::Compat::Appraiser::IAsset *> &,RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800eaa56  mov     ebx, eax
0x1800eaa58  test    eax, eax
0x1800eaa5a  jns     short loc_1800EAA66
0x1800eaa5c  mov     edx, 5A0h
0x1800eaa61  jmp     loc_1800EA98C
0x1800eaa66  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800eaa6c  test    al, 1
0x1800eaa6e  jz      short loc_1800EAA8F
0x1800eaa70  mov     dword ptr [rsp+170h+var_150], ebx
0x1800eaa74  mov     r9, rdi; char *
0x1800eaa77  lea     r8, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800eaa7e  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800eaa85  mov     ecx, 5A0h; unsigned int
0x1800eaa8a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800eaa8f  lea     r14, [rbp+70h+var_A8]
0x1800eaa93  mov     rax, [r14+10h]
0x1800eaa97  mov     rbx, qword ptr [rsp+170h+var_108]
0x1800eaa9c  test    rax, rax
0x1800eaa9f  jz      loc_1800EAC2D
0x1800eaaa5  xor     esi, esi
0x1800eaaa7  xor     edx, edx
0x1800eaaa9  cmp     rsi, rax
0x1800eaaac  jnb     short loc_1800EAAC9
0x1800eaaae  mov     rax, rsi
0x1800eaab1  mul     qword ptr [r14+8]
0x1800eaab5  test    rdx, rdx
0x1800eaab8  jnz     short loc_1800EAAC7
0x1800eaaba  mov     rcx, [r14+28h]
0x1800eaabe  lea     rdx, [rcx+rax]
0x1800eaac2  cmp     rdx, rcx
0x1800eaac5  jnb     short loc_1800EAAC9
0x1800eaac7  xor     edx, edx
0x1800eaac9  mov     r12, [rdx]
0x1800eaacc  mov     r9d, 1
0x1800eaad2  mov     r8, r12
0x1800eaad5  lea     rdx, aAssettype; "AssetType"
0x1800eaadc  lea     rcx, [rsp+170h+var_120]
0x1800eaae1  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x1800eaae6  test    eax, eax
0x1800eaae8  jns     short loc_1800EAB20
0x1800eaaea  lea     rcx, aAssetIsMissing_0; "Asset is missing a Type: [0x%x]."
0x1800eaaf1  mov     edx, 5B4h; bool
0x1800eaaf6  mov     dword ptr [rsp+170h+var_140], eax; char *
0x1800eaafa  mov     qword ptr [rsp+170h+var_148], rcx; int
0x1800eaaff  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800eab06  lea     r9, aWindowsCompatA_789; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800eab0d  mov     dword ptr [rsp+170h+var_150], eax; char *
0x1800eab11  mov     ecx, 1; this
0x1800eab16  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800eab1b  jmp     loc_1800EAC1D
0x1800eab20  mov     r9, r12; struct Windows::Compat::Appraiser::IAsset *
0x1800eab23  lea     rcx, [rbp+70h+var_B8]; unsigned __int16 **
0x1800eab27  call    ?GetUniqueIdentifier@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBG0PEAUUniqueIdentifierTable@234@PEAVIAsset@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(ushort const * *,ushort const * *,Windows::Compat::Appraiser::UniqueIdentifierTable *,Windows::Compat::Appraiser::IAsset *)
0x1800eab2c  test    eax, eax
0x1800eab2e  jns     short loc_1800EAB3E
0x1800eab30  lea     rcx, aAssetIsMissing_1; "Asset is missing a Unique Identifier: ["...
0x1800eab37  mov     edx, 5BCh
0x1800eab3c  jmp     short loc_1800EAAF6
0x1800eab3e  xor     edi, edi
0x1800eab40  test    rbx, rbx
0x1800eab43  jz      loc_1800EAC07
0x1800eab49  xor     eax, eax
0x1800eab4b  cmp     rdi, rbx
0x1800eab4e  jnb     short loc_1800EAB69
0x1800eab50  mov     rax, rdi
0x1800eab53  mul     [rsp+170h+var_118+8]
0x1800eab58  test    rdx, rdx
0x1800eab5b  jnz     short loc_1800EAB67
0x1800eab5d  add     rax, [rbp+70h+var_F8+8]
0x1800eab61  cmp     rax, [rbp+70h+var_F8+8]
0x1800eab65  jnb     short loc_1800EAB69
0x1800eab67  xor     eax, eax
0x1800eab69  mov     r15, [rax]
0x1800eab6c  mov     r9d, 1
0x1800eab72  mov     r8, r15
0x1800eab75  lea     rdx, aAssettype; "AssetType"
0x1800eab7c  lea     rcx, [rsp+170h+var_128]
0x1800eab81  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x1800eab86  test    eax, eax
0x1800eab88  js      short loc_1800EABE2
0x1800eab8a  mov     rax, [rsp+170h+var_120]
0x1800eab8f  mov     r8, [rsp+170h+var_128]
0x1800eab94  sub     r8, rax; struct Windows::Compat::Appraiser::UniqueIdentifierTable *
0x1800eab97  movzx   edx, word ptr [rax]
0x1800eab9a  movzx   ecx, word ptr [rax+r8]
0x1800eab9f  sub     edx, ecx; unsigned __int16 **
0x1800eaba1  jnz     short loc_1800EABAB
0x1800eaba3  add     rax, 2
0x1800eaba7  test    ecx, ecx
0x1800eaba9  jnz     short loc_1800EAB97
0x1800eabab  test    edx, edx
0x1800eabad  jnz     short loc_1800EABE2
0x1800eabaf  mov     r9, r15; struct Windows::Compat::Appraiser::IAsset *
0x1800eabb2  lea     rcx, [rbp+70h+var_B0]; unsigned __int16 **
0x1800eabb6  call    ?GetUniqueIdentifier@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBG0PEAUUniqueIdentifierTable@234@PEAVIAsset@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(ushort const * *,ushort const * *,Windows::Compat::Appraiser::UniqueIdentifierTable *,Windows::Compat::Appraiser::IAsset *)
0x1800eabbb  test    eax, eax
0x1800eabbd  js      short loc_1800EABE2
0x1800eabbf  mov     rax, [rbp+70h+var_B8]
0x1800eabc3  mov     r8, [rbp+70h+var_B0]
0x1800eabc7  sub     r8, rax
0x1800eabca  movzx   edx, word ptr [rax]
0x1800eabcd  movzx   ecx, word ptr [rax+r8]
0x1800eabd2  sub     edx, ecx
0x1800eabd4  jnz     short loc_1800EABDE
0x1800eabd6  add     rax, 2
0x1800eabda  test    ecx, ecx
0x1800eabdc  jnz     short loc_1800EABCA
0x1800eabde  test    edx, edx
0x1800eabe0  jz      short loc_1800EABEE
0x1800eabe2  inc     rdi
0x1800eabe5  cmp     rdi, rbx
0x1800eabe8  jb      loc_1800EAB49
0x1800eabee  cmp     rdi, rbx
0x1800eabf1  jnb     short loc_1800EAC07
0x1800eabf3  mov     rdx, rdi
0x1800eabf6  lea     rcx, [rsp+170h+var_118]
0x1800eabfb  call    ?Delete@?$RtlArray@PEAVTable@Appraiser@Compat@Windows@@@@QEAAX_K@Z; RtlArray<Windows::Compat::Appraiser::Table *>::Delete(unsigned __int64)
0x1800eac00  mov     rbx, qword ptr [rsp+170h+var_108]
0x1800eac05  jmp     short loc_1800EAC0A
0x1800eac07  xor     r15d, r15d
0x1800eac0a  mov     r9, [rsp+170h+var_120]; unsigned __int16 *
0x1800eac0f  mov     r8, r15; struct Windows::Compat::Appraiser::IAsset *
0x1800eac12  mov     rdx, r12; struct Windows::Compat::Appraiser::IAsset *
0x1800eac15  mov     rcx, r13; this
0x1800eac18  call    ?WriteAllDiffEventsForAsset@TelemetryOutputter@Appraiser@Compat@Windows@@AEAAXPEAVIAsset@234@0PEBG@Z; Windows::Compat::Appraiser::TelemetryOutputter::WriteAllDiffEventsForAsset(Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::IAsset *,ushort const *)
0x1800eac1d  inc     rsi
0x1800eac20  mov     rax, [r14+10h]
0x1800eac24  cmp     rsi, rax
0x1800eac27  jb      loc_1800EAAA7
0x1800eac2d  xor     edi, edi
0x1800eac2f  test    rbx, rbx
0x1800eac32  jz      loc_1800EACCA
0x1800eac38  xor     eax, eax
0x1800eac3a  cmp     rdi, rbx
0x1800eac3d  jnb     short loc_1800EAC58
0x1800eac3f  mov     rax, rdi
0x1800eac42  mul     [rsp+170h+var_118+8]
0x1800eac47  test    rdx, rdx
0x1800eac4a  jnz     short loc_1800EAC56
0x1800eac4c  add     rax, [rbp+70h+var_F8+8]
0x1800eac50  cmp     rax, [rbp+70h+var_F8+8]
0x1800eac54  jnb     short loc_1800EAC58
0x1800eac56  xor     eax, eax
0x1800eac58  mov     rsi, [rax]
0x1800eac5b  mov     r9d, 1
  ... truncated ...
```
