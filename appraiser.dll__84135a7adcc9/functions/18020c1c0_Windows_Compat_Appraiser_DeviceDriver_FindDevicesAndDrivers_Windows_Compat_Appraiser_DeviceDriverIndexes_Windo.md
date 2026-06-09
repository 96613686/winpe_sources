# Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers(Windows::Compat::Appraiser::DeviceDriverIndexes &,Windows::Compat::Appraiser::AssetProperties *,ulong)

- ea: `0x18020c1c0`
- end: `0x18020c634`
- name: `?FindDevicesAndDrivers@DeviceDriver@Appraiser@Compat@Windows@@CAJAEAUDeviceDriverIndexes@234@PEAUAssetProperties@234@K@Z`
- size: `1140`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::DeviceDriverIndexes *, struct Windows::Compat::Appraiser::AssetProperties *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18020b5c0`

## callees

- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18009606c`
- `0x1800ad71c`
- `0x18020a098`
- `0x18020c1c0`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18020c217`
- `KERNEL32!GetProcessHeap` at `0x18020c293`
- `KERNEL32!GetProcessHeap` at `0x18020c304`
- `KERNEL32!GetProcessHeap` at `0x18020c217`
- `KERNEL32!GetProcessHeap` at `0x18020c293`
- `KERNEL32!GetProcessHeap` at `0x18020c304`
- `KERNEL32!HeapFree` at `0x18020c203`
- `KERNEL32!HeapFree` at `0x18020c27c`
- `KERNEL32!HeapFree` at `0x18020c2f0`
- `KERNEL32!HeapFree` at `0x18020c203`
- `KERNEL32!HeapFree` at `0x18020c27c`
- `KERNEL32!HeapFree` at `0x18020c2f0`

## string_xrefs

- `0x18020c259`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c2cd`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c342`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c3ba`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c475`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c553`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c5b4`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c5fb`: `onecore\base\appcompat\appraiser\decisionaggregators\devicedriver.cpp`
- `0x18020c229`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`
- `0x18020c3ae`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`
- `0x18020c469`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`
- `0x18020c54c`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`
- `0x18020c5c0`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`
- `0x18020c5f4`: `Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers(
        struct Windows::Compat::Appraiser::DeviceDriverIndexes *a1,
        struct Windows::Compat::Appraiser::AssetProperties *a2,
        unsigned int a3)
{
  unsigned int v3; // r12d
  void *v5; // r8
  struct Windows::Compat::Appraiser::AssetProperties *v6; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE *v9; // r14
  void *v10; // r8
  char v11; // al
  HANDLE *v12; // rsi
  void *v13; // r8
  char v14; // al
  unsigned int v15; // r15d
  unsigned int v16; // eax
  int RequiredSingleValue; // eax
  int v18; // ebx
  wchar_t *v19; // rbx
  __int64 v20; // rcx
  unsigned int v21; // ecx
  struct Windows::Compat::Appraiser::AssetProperties *v22; // rbx
  __int64 v23; // r12
  const wchar_t *v24; // rax
  int v25; // eax
  const char *v26; // rax
  char v27; // dl
  char *v29; // [rsp+20h] [rbp-40h]
  char *v30; // [rsp+30h] [rbp-30h]
  _DWORD v31[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h] BYREF
  int v33; // [rsp+50h] [rbp-10h]
  int v34; // [rsp+A0h] [rbp+40h] BYREF
  struct Windows::Compat::Appraiser::AssetProperties *v35; // [rsp+A8h] [rbp+48h]
  wchar_t *String1; // [rsp+B8h] [rbp+58h] BYREF

  v35 = a2;
  v3 = 0;
  String1 = 0;
  v5 = (void *)*((_QWORD *)a1 + 5);
  v6 = a2;
  v32 = 0;
  v33 = 0;
  if ( v5 )
    HeapFree(*(HANDLE *)a1, 0, v5);
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *((_OWORD *)a1 + 2) = 0;
  ProcessHeap = GetProcessHeap();
  *((_QWORD *)a1 + 2) = 0;
  *(_QWORD *)a1 = ProcessHeap;
  LOBYTE(ProcessHeap) = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  *((_QWORD *)a1 + 4) = 16;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *((_QWORD *)a1 + 1) = 16;
  if ( ((unsigned __int8)ProcessHeap & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x112u,
      "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
      "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  v9 = (HANDLE *)((char *)a1 + 48);
  v10 = (void *)*((_QWORD *)a1 + 11);
  if ( v10 )
    HeapFree(*v9, 0, v10);
  *(_OWORD *)v9 = 0;
  *((_OWORD *)a1 + 4) = 0;
  *((_OWORD *)a1 + 5) = 0;
  *v9 = GetProcessHeap();
  v11 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  *((_QWORD *)a1 + 10) = 16;
  *((_QWORD *)a1 + 8) = 0;
  *((_QWORD *)a1 + 9) = 0;
  *((_QWORD *)a1 + 11) = 0;
  *((_QWORD *)a1 + 7) = 8;
  if ( (v11 & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x113u,
      "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
      "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  v12 = (HANDLE *)((char *)a1 + 96);
  v13 = (void *)*((_QWORD *)a1 + 17);
  if ( v13 )
    HeapFree(*v12, 0, v13);
  *(_OWORD *)v12 = 0;
  *((_OWORD *)a1 + 7) = 0;
  *((_OWORD *)a1 + 8) = 0;
  *v12 = GetProcessHeap();
  v14 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  *((_QWORD *)a1 + 16) = 16;
  *((_QWORD *)a1 + 14) = 0;
  *((_QWORD *)a1 + 15) = 0;
  *((_QWORD *)a1 + 17) = 0;
  *((_QWORD *)a1 + 13) = 8;
  if ( (v14 & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x114u,
      "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
      "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  *((_DWORD *)a1 + 36) = -1;
  v15 = 0;
  v34 = 0;
  if ( !a3 )
  {
LABEL_44:
    if ( *((_DWORD *)a1 + 36) == -1 )
    {
      v18 = -2147024809;
      LODWORD(v29) = -2147024809;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        68,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
        "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
        v29,
        (int)"InboxBddMarker Asset not found.",
        v30);
    }
    else
    {
      return 0;
    }
    return (unsigned int)v18;
  }
  v16 = 0;
  while ( 1 )
  {
    RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                            (const unsigned __int16 **)&String1,
                            L"AssetType",
                            *((struct Windows::Compat::Appraiser::IPropertyListEnumerator **)v6 + 4 * v16));
    v18 = RequiredSingleValue;
    if ( RequiredSingleValue < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x11Au,
        "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
        "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
        "Error getting type: [0x%x].",
        RequiredSingleValue);
    v19 = String1;
    if ( !wcscmp_0(String1, L"Driver") )
    {
      v31[0] = v15;
      v20 = *((_QWORD *)v35 + 4 * v3 + 3);
      v31[1] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      v18 = RtlArray<JsonValue *>::Append((char *)a1 + 48, v31);
      if ( v18 < 0 )
      {
        v26 = "RtlArray append error: [0x%x].";
        v27 = 37;
        goto LABEL_43;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        v21 = 293;
LABEL_36:
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          v21,
          "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
          "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
          "RtlArray append error: [0x%x].",
          v18);
      }
    }
    else if ( !wcscmp_0(v19, L"DriverUplevel") )
    {
      v18 = RtlArray<unsigned int>::Append((char *)a1 + 96, &v34);
      if ( v18 < 0 )
      {
        v26 = "RtlArray append error: [0x%x].";
        v27 = 42;
        goto LABEL_43;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x12Au,
          "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
          "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
          "RtlArray append error: [0x%x].",
          v18);
      v15 = v34;
    }
    else
    {
      if ( !wcscmp_0(v19, L"BddMarker") )
      {
        *((_DWORD *)a1 + 36) = v15;
        goto LABEL_37;
      }
      if ( !wcscmp_0(v19, L"Device") )
      {
        v22 = v35;
        v23 = 32LL * v3;
        v33 = 0;
        v32 = v15;
        v24 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)((char *)v35 + v23)
                                                                                           + 40LL))(
                                 *(_QWORD *)((char *)v35 + v23),
                                 L"Class");
        if ( !v24 || (v25 = wcscmp_0(L"display", v24), BYTE1(v33) = 1, v25) )
          BYTE1(v33) = 0;
        HIDWORD(v32) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)((char *)v22 + v23 + 24) + 8LL))(*(_QWORD *)((char *)v22 + v23 + 24));
        v18 = RtlArray<Windows::Compat::Appraiser::DeviceData>::Append(a1, &v32);
        if ( v18 < 0 )
        {
          v26 = "RtlArray append error: [0x%x].";
          v27 = 61;
          goto LABEL_43;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        {
          v21 = 317;
          goto LABEL_36;
        }
      }
    }
LABEL_37:
    v34 = ++v15;
    v16 = v15;
    v3 = v15;
    if ( v15 >= a3 )
      goto LABEL_44;
    v6 = v35;
  }
  v26 = "Error getting type: [0x%x].";
  v27 = 26;
LABEL_43:
  LODWORD(v30) = v18;
  LODWORD(v29) = v18;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v27,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\devicedriver.cpp",
    "Windows::Compat::Appraiser::DeviceDriver::FindDevicesAndDrivers",
    v29,
    (int)v26,
    v30);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18020c1c0  mov     [rsp-38h+arg_10], rbx
0x18020c1c5  mov     [rsp-38h+arg_8], rdx
0x18020c1ca  push    rbp
0x18020c1cb  push    rsi
0x18020c1cc  push    rdi
0x18020c1cd  push    r12
0x18020c1cf  push    r13
0x18020c1d1  push    r14
0x18020c1d3  push    r15
0x18020c1d5  mov     rbp, rsp
0x18020c1d8  sub     rsp, 60h
0x18020c1dc  xor     eax, eax
0x18020c1de  xor     r12d, r12d
0x18020c1e1  mov     r13d, r8d
0x18020c1e4  mov     [rbp+String1], r12
0x18020c1e8  mov     r8, [rcx+28h]; lpMem
0x18020c1ec  mov     rbx, rdx
0x18020c1ef  mov     [rbp+var_18], rax
0x18020c1f3  mov     rdi, rcx
0x18020c1f6  mov     [rbp+var_10], eax
0x18020c1f9  test    r8, r8
0x18020c1fc  jz      short loc_18020C209
0x18020c1fe  mov     rcx, [rcx]; hHeap
0x18020c201  xor     edx, edx; dwFlags
0x18020c203  call    cs:__imp_HeapFree
0x18020c209  xorps   xmm0, xmm0
0x18020c20c  movups  xmmword ptr [rdi], xmm0
0x18020c20f  movups  xmmword ptr [rdi+10h], xmm0
0x18020c213  movups  xmmword ptr [rdi+20h], xmm0
0x18020c217  call    cs:__imp_GetProcessHeap
0x18020c21d  mov     esi, 10h
0x18020c222  mov     [rdi+10h], r12
0x18020c226  mov     [rdi], rax
0x18020c229  lea     r15, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c230  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c236  mov     [rdi+20h], rsi
0x18020c23a  mov     [rdi+18h], r12
0x18020c23e  mov     [rdi+28h], r12
0x18020c242  mov     [rdi+8], rsi
0x18020c246  test    al, 1
0x18020c248  jz      short loc_18020C26A
0x18020c24a  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x18020c251  mov     dword ptr [rsp+60h+var_40], r12d
0x18020c256  mov     r8, r15; char *
0x18020c259  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c260  mov     ecx, 112h; unsigned int
0x18020c265  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c26a  lea     r14, [rdi+30h]
0x18020c26e  mov     r8, [r14+28h]; lpMem
0x18020c272  test    r8, r8
0x18020c275  jz      short loc_18020C282
0x18020c277  mov     rcx, [r14]; hHeap
0x18020c27a  xor     edx, edx; dwFlags
0x18020c27c  call    cs:__imp_HeapFree
0x18020c282  xorps   xmm0, xmm0
0x18020c285  movups  xmmword ptr [r14], xmm0
0x18020c289  movups  xmmword ptr [r14+10h], xmm0
0x18020c28e  movups  xmmword ptr [r14+20h], xmm0
0x18020c293  call    cs:__imp_GetProcessHeap
0x18020c299  mov     [r14], rax
0x18020c29c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c2a2  mov     [r14+20h], rsi
0x18020c2a6  mov     [r14+10h], r12
0x18020c2aa  mov     [r14+18h], r12
0x18020c2ae  mov     [r14+28h], r12
0x18020c2b2  mov     qword ptr [r14+8], 8
0x18020c2ba  test    al, 1
0x18020c2bc  jz      short loc_18020C2DE
0x18020c2be  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x18020c2c5  mov     dword ptr [rsp+60h+var_40], r12d
0x18020c2ca  mov     r8, r15; char *
0x18020c2cd  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c2d4  mov     ecx, 113h; unsigned int
0x18020c2d9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c2de  lea     rsi, [rdi+60h]
0x18020c2e2  mov     r8, [rsi+28h]; lpMem
0x18020c2e6  test    r8, r8
0x18020c2e9  jz      short loc_18020C2F6
0x18020c2eb  mov     rcx, [rsi]; hHeap
0x18020c2ee  xor     edx, edx; dwFlags
0x18020c2f0  call    cs:__imp_HeapFree
0x18020c2f6  xorps   xmm0, xmm0
0x18020c2f9  movups  xmmword ptr [rsi], xmm0
0x18020c2fc  movups  xmmword ptr [rsi+10h], xmm0
0x18020c300  movups  xmmword ptr [rsi+20h], xmm0
0x18020c304  call    cs:__imp_GetProcessHeap
0x18020c30a  mov     [rsi], rax
0x18020c30d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c313  mov     qword ptr [rsi+20h], 10h
0x18020c31b  mov     [rsi+10h], r12
0x18020c31f  mov     [rsi+18h], r12
0x18020c323  mov     [rsi+28h], r12
0x18020c327  mov     qword ptr [rsi+8], 8
0x18020c32f  test    al, 1
0x18020c331  jz      short loc_18020C353
0x18020c333  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x18020c33a  mov     dword ptr [rsp+60h+var_40], r12d
0x18020c33f  mov     r8, r15; char *
0x18020c342  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c349  mov     ecx, 114h; unsigned int
0x18020c34e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c353  mov     dword ptr [rdi+90h], 0FFFFFFFFh
0x18020c35d  mov     r15d, r12d
0x18020c360  mov     [rbp+arg_0], r12d
0x18020c364  test    r13d, r13d
0x18020c367  jz      loc_18020C5DA
0x18020c36d  mov     eax, r12d
0x18020c370  mov     r8d, eax
0x18020c373  lea     rdx, aAssettype; "AssetType"
0x18020c37a  shl     r8, 5
0x18020c37e  lea     rcx, [rbp+String1]; unsigned __int16 **
0x18020c382  mov     r8, [r8+rbx]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x18020c386  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x18020c38b  mov     ebx, eax
0x18020c38d  test    eax, eax
0x18020c38f  js      loc_18020C5A4
0x18020c395  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c39b  mov     r12d, r12d
0x18020c39e  test    cl, 1
0x18020c3a1  jz      short loc_18020C3C6
0x18020c3a3  lea     r9, aErrorGettingTy_0; "Error getting type: [0x%x]."
0x18020c3aa  mov     dword ptr [rsp+60h+var_40], eax
0x18020c3ae  lea     r8, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c3b5  mov     ecx, 11Ah; unsigned int
0x18020c3ba  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c3c1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c3c6  mov     rbx, [rbp+String1]
0x18020c3ca  lea     rdx, aDriver; "Driver"
0x18020c3d1  mov     rcx, rbx; String1
0x18020c3d4  call    wcscmp_0
0x18020c3d9  test    eax, eax
0x18020c3db  jnz     short loc_18020C42B
0x18020c3dd  mov     rbx, [rbp+arg_8]
0x18020c3e1  shl     r12, 5
0x18020c3e5  mov     [rbp+var_20], r15d
0x18020c3e9  mov     rcx, [r12+rbx+18h]
0x18020c3ee  mov     rax, [rcx]
0x18020c3f1  mov     rax, [rax+8]
0x18020c3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c3fa  lea     rdx, [rbp+var_20]
0x18020c3fe  mov     [rbp+var_1C], eax
0x18020c401  mov     rcx, r14
0x18020c404  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x18020c409  mov     ebx, eax
0x18020c40b  test    eax, eax
0x18020c40d  js      loc_18020C57A
0x18020c413  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c419  test    al, 1
0x18020c41b  jz      loc_18020C55F
0x18020c421  mov     ecx, 125h
0x18020c426  jmp     loc_18020C541
0x18020c42b  lea     rdx, aDriveruplevel; "DriverUplevel"
0x18020c432  mov     rcx, rbx; String1
0x18020c435  call    wcscmp_0
0x18020c43a  test    eax, eax
0x18020c43c  jnz     short loc_18020C48A
0x18020c43e  lea     rdx, [rbp+arg_0]
0x18020c442  mov     rcx, rsi
0x18020c445  call    ?Append@?$RtlArray@I@@QEAAJAEBI@Z; RtlArray<uint>::Append(uint const &)
0x18020c44a  mov     ebx, eax
0x18020c44c  test    eax, eax
0x18020c44e  js      loc_18020C588
0x18020c454  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c45a  test    al, 1
0x18020c45c  jz      short loc_18020C481
0x18020c45e  lea     r9, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x18020c465  mov     dword ptr [rsp+60h+var_40], ebx
0x18020c469  lea     r8, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c470  mov     ecx, 12Ah; unsigned int
0x18020c475  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c47c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c481  mov     r15d, [rbp+arg_0]
0x18020c485  jmp     loc_18020C55F
0x18020c48a  lea     rdx, aBddmarker; "BddMarker"
0x18020c491  mov     rcx, rbx; String1
0x18020c494  call    wcscmp_0
0x18020c499  test    eax, eax
0x18020c49b  jnz     short loc_18020C4A9
0x18020c49d  mov     [rdi+90h], r15d
0x18020c4a4  jmp     loc_18020C55F
0x18020c4a9  lea     rdx, aDevice_0; "Device"
0x18020c4b0  mov     rcx, rbx; String1
0x18020c4b3  call    wcscmp_0
0x18020c4b8  test    eax, eax
0x18020c4ba  jnz     loc_18020C55F
0x18020c4c0  mov     rbx, [rbp+arg_8]
0x18020c4c4  lea     rdx, aClass; "Class"
0x18020c4cb  xor     eax, eax
0x18020c4cd  shl     r12, 5
0x18020c4d1  mov     [rbp+var_18], rax
0x18020c4d5  mov     [rbp+var_10], eax
0x18020c4d8  mov     dword ptr [rbp+var_18], r15d
0x18020c4dc  mov     rcx, [r12+rbx]
0x18020c4e0  mov     rax, [rcx]
0x18020c4e3  mov     rax, [rax+28h]
0x18020c4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c4ec  test    rax, rax
0x18020c4ef  jz      short loc_18020C508
0x18020c4f1  mov     rdx, rax; String2
0x18020c4f4  lea     rcx, aDisplay; "display"
0x18020c4fb  call    wcscmp_0
0x18020c500  mov     byte ptr [rbp+var_10+1], 1
0x18020c504  test    eax, eax
0x18020c506  jz      short loc_18020C50C
0x18020c508  mov     byte ptr [rbp+var_10+1], 0
0x18020c50c  mov     rcx, [r12+rbx+18h]
0x18020c511  mov     rax, [rcx]
0x18020c514  mov     rax, [rax+8]
0x18020c518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c51d  lea     rdx, [rbp+var_18]
0x18020c521  mov     dword ptr [rbp+var_18+4], eax
0x18020c524  mov     rcx, rdi
0x18020c527  call    ?Append@?$RtlArray@UDeviceData@Appraiser@Compat@Windows@@@@QEAAJAEBUDeviceData@Appraiser@Compat@Windows@@@Z; RtlArray<Windows::Compat::Appraiser::DeviceData>::Append(Windows::Compat::Appraiser::DeviceData const &)
0x18020c52c  mov     ebx, eax
0x18020c52e  test    eax, eax
0x18020c530  js      short loc_18020C596
0x18020c532  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18020c538  test    al, 1
0x18020c53a  jz      short loc_18020C55F
0x18020c53c  mov     ecx, 13Dh; unsigned int
0x18020c541  lea     r9, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x18020c548  mov     dword ptr [rsp+60h+var_40], ebx
0x18020c54c  lea     r8, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c553  lea     rdx, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c55a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020c55f  inc     r15d
0x18020c562  mov     [rbp+arg_0], r15d
0x18020c566  mov     eax, r15d
0x18020c569  mov     r12d, r15d
0x18020c56c  cmp     r15d, r13d
0x18020c56f  jnb     short loc_18020C5D7
0x18020c571  mov     rbx, [rbp+arg_8]
0x18020c575  jmp     loc_18020C370
0x18020c57a  lea     rax, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x18020c581  mov     edx, 125h
0x18020c586  jmp     short loc_18020C5B0
0x18020c588  lea     rax, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x18020c58f  mov     edx, 12Ah
0x18020c594  jmp     short loc_18020C5B0
0x18020c596  lea     rax, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x18020c59d  mov     edx, 13Dh
0x18020c5a2  jmp     short loc_18020C5B0
0x18020c5a4  lea     rax, aErrorGettingTy_0; "Error getting type: [0x%x]."
0x18020c5ab  mov     edx, 11Ah; bool
0x18020c5b0  mov     dword ptr [rsp+60h+var_30], ebx; char *
0x18020c5b4  lea     r8, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c5bb  mov     qword ptr [rsp+60h+var_38], rax; int
0x18020c5c0  lea     r9, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c5c7  mov     ecx, 1; this
0x18020c5cc  mov     dword ptr [rsp+60h+var_40], ebx; char *
0x18020c5d0  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18020c5d5  jmp     short loc_18020C61A
0x18020c5d7  xor     r12d, r12d
0x18020c5da  cmp     dword ptr [rdi+90h], 0FFFFFFFFh
0x18020c5e1  jnz     short loc_18020C617
0x18020c5e3  lea     rax, aInboxbddmarker_0; "InboxBddMarker Asset not found."
0x18020c5ea  mov     ebx, 80070057h
0x18020c5ef  mov     qword ptr [rsp+60h+var_38], rax; int
0x18020c5f4  lea     r9, aWindowsCompatA_349; "Windows::Compat::Appraiser::DeviceDrive"...
0x18020c5fb  lea     r8, aOnecoreBaseApp_86; "onecore\\base\\appcompat\\appraiser\\de"...
0x18020c602  mov     dword ptr [rsp+60h+var_40], ebx; char *
0x18020c606  mov     edx, 144h; bool
0x18020c60b  mov     ecx, 1; this
0x18020c610  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18020c615  jmp     short loc_18020C61A
0x18020c617  mov     ebx, r12d
0x18020c61a  mov     eax, ebx
0x18020c61c  mov     rbx, [rsp+60h+arg_10]
0x18020c624  add     rsp, 60h
0x18020c628  pop     r15
0x18020c62a  pop     r14
0x18020c62c  pop     r13
0x18020c62e  pop     r12
0x18020c630  pop     rdi
0x18020c631  pop     rsi
0x18020c632  pop     rbp
0x18020c633  retn
```
