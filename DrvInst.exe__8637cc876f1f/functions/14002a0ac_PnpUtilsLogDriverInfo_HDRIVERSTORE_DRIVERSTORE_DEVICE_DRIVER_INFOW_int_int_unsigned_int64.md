# PnpUtilsLogDriverInfo(HDRIVERSTORE__ *,_DRIVERSTORE_DEVICE_DRIVER_INFOW *,int,int,unsigned __int64)

- ea: `0x14002a0ac`
- end: `0x14002a8cd`
- name: `?PnpUtilsLogDriverInfo@@YAXPEAUHDRIVERSTORE__@@PEAU_DRIVERSTORE_DEVICE_DRIVER_INFOW@@HH_K@Z`
- size: `2081`
- prototype: `void __fastcall(struct HDRIVERSTORE__ *, struct _DRIVERSTORE_DEVICE_DRIVER_INFOW *, int, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400279d0`

## callees

- `0x140023b08`
- `0x140023b40`
- `0x14002a0ac`
- `0x14002b188`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002a24e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002a24e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a2ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a2ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a231`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002a570`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002a570`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a41c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a480`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a4b9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a4d6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a514`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a55f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a5dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a605`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a639`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a650`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a66d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a690`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a6b6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a6f9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a7db`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a816`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a861`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a89d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a41c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a480`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a4b9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a4d6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a514`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a55f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a5dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a605`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a639`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a650`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a66d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a690`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a6b6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a6f9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a7db`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a816`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a861`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a89d`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a17f`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a1d1`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a223`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a293`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a2fa`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a35a`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a17f`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a1d1`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a223`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a293`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a2fa`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002a35a`

## string_xrefs

- `0x14002a3f7`: `Extension `
- `0x14002a43f`: ` | Installed`
- `0x14002a54d`: `Extension ID   - %ws`
- `0x14002a5f0`: `Computer ID    - %ws`
- `0x14002a646`: `Configuration  - %ws`
- `0x14002a62a`: `Configuration  - %ws [%ws]`

## pseudocode

```c
void __fastcall PnpUtilsLogDriverInfo(
        struct HDRIVERSTORE__ *a1,
        struct _DRIVERSTORE_DEVICE_DRIVER_INFOW *a2,
        int a3,
        int a4,
        unsigned __int64 a5)
{
  char *v5; // r12
  __int64 v6; // rax
  int v7; // r13d
  __int64 v8; // rax
  char *v11; // r15
  void *v12; // r14
  const wchar_t *v13; // rax
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // eax
  const wchar_t *v20; // rsi
  unsigned int v21; // r14d
  int v22; // edi
  char IsEnabled; // al
  const wchar_t *v24; // rcx
  const wchar_t *v25; // rdx
  const wchar_t *v26; // rax
  _QWORD *v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+6Ch] [rbp-94h] BYREF
  BOOL v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+84h] [rbp-7Ch]
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v36[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[80]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v38[264]; // [rsp+140h] [rbp+40h] BYREF

  v5 = (char *)a2 + 1056;
  v6 = *((_QWORD *)a2 + 132);
  v7 = *((_DWORD *)a2 + 1) & 1;
  v33 = a4;
  v8 = v6 - *(_QWORD *)&GUID_DEVCLASS_EXTENSION.Data1;
  v34 = a3;
  v30 = 0;
  SystemTime = 0;
  v32 = -1;
  if ( !v8 )
    v8 = *((_QWORD *)a2 + 133) - *(_QWORD *)GUID_DEVCLASS_EXTENSION.Data4;
  v11 = (char *)a2 + 12;
  v31 = v8 == 0;
  DriverStoreGetObjectPropertyW(a1, 2, (char *)a2 + 12, DEVPKEY_DriverPackage_SignerScore);
  DriverStoreGetObjectPropertyW(a1, 2, v11, DEVPKEY_DriverPackage_SubmissionId);
  v38[0] = 0;
  if ( !(unsigned int)DriverStoreGetObjectPropertyW(a1, 2, v11, DEVPKEY_DriverPackage_DriverFlightIds)
    && GetLastError() == 122 )
  {
    v12 = HeapAlloc(hHeap, 0, 0);
    if ( v12 )
    {
      DriverStoreGetObjectPropertyW(a1, 2, v11, DEVPKEY_DriverPackage_DriverFlightIds);
      HeapFree(hHeap, 0, v12);
    }
  }
  v29 = 4;
  v27 = &v30;
  DriverStoreGetObjectPropertyW(a1, 2, v11, DEVPKEY_DriverPackage_CatalogAttributes);
  v30 = -1;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::GetImpl'::`2'::impl) )
  {
    v29 = 8;
    v27 = &v32;
    DriverStoreGetObjectPropertyW(a1, 2, v11, DEVPKEY_DriverPackage_CertificationVersion);
    v32 = -1;
  }
  v13 = L"Extension ";
  if ( !v31 )
    v13 = &qword_14004E980;
  DevRtlWriteTextLog(a5, 512, 4, "Driver %wsNode:", v13, v27, v29, 0, 0);
  v14 = L" | Designated";
  if ( !v33 )
    v14 = &qword_14004E980;
  v15 = L" | Installed";
  if ( !v34 )
    v15 = &qword_14004E980;
  v16 = L"Selected";
  if ( !v7 )
    v16 = L"Outranked";
  DevRtlWriteTextLog(a5, 512, 524292, "Status         - %ws%ws%ws", v16, v15, v14);
  if ( *((_WORD *)a2 + 267) )
    DevRtlWriteTextLog(a5, 512, 524292, "Driver INF     - %ws (%ws)", (char *)a2 + 534, v11);
  else
    DevRtlWriteTextLog(a5, 512, 524292, "Driver INF     - %ws", v11);
  if ( !(unsigned int)SpUtilsIsGuidNull(v5) && !(unsigned int)SpUtilsStringFromGuid(v17, v36) )
    DevRtlWriteTextLog(a5, 512, 524292, "Class GUID     - %ws", v36);
  if ( v31 && !(unsigned int)SpUtilsIsGuidNull((char *)a2 + 1088) && !(unsigned int)SpUtilsStringFromGuid(v18, v37) )
    DevRtlWriteTextLog(a5, 512, 524292, "Extension ID   - %ws", v37);
  if ( !FileTimeToSystemTime((const FILETIME *)a2 + 134, &SystemTime) )
    SystemTime = 0;
  DevRtlWriteTextLog(
    a5,
    512,
    524292,
    "Driver Version - %02hu/%02hu/%04hu,%hu.%hu.%hu.%hu",
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wYear,
    *((unsigned __int16 *)a2 + 543),
    *((unsigned __int16 *)a2 + 542),
    *((unsigned __int16 *)a2 + 541),
    *((unsigned __int16 *)a2 + 540));
  if ( *((_WORD *)a2 + 552) )
    DevRtlWriteTextLog(a5, 512, 524292, "Computer ID    - %ws", (char *)a2 + 1104);
  if ( *((_WORD *)a2 + 1072) )
    DevRtlWriteTextLog(a5, 512, 524292, "Configuration  - %ws [%ws]", (char *)a2 + 1624, (char *)a2 + 2144);
  else
    DevRtlWriteTextLog(a5, 512, 524292, "Configuration  - %ws", (char *)a2 + 1624);
  DevRtlWriteTextLog(a5, 512, 524292, "Driver Rank    - %08X", *((_DWORD *)a2 + 2));
  LODWORD(v28) = -16777216;
  DevRtlWriteTextLog(a5, 512, 524292, "Signer Score   - %ws (%08X)", L"Unknown", v28);
  if ( v38[0] )
    DevRtlWriteTextLog(a5, 512, 524292, "Submission ID  - %ws", v38);
  if ( v30 != -1 )
  {
    v19 = 0;
    while ( (v30 & qword_1400489E0[2 * v19]) == 0 )
    {
      if ( ++v19 >= 2 )
        goto LABEL_42;
    }
    v20 = (const wchar_t *)qword_1400489E0[2 * v19 + 1];
    if ( v20 )
      goto LABEL_43;
LABEL_42:
    v20 = L"Legacy";
LABEL_43:
    v21 = v30 & 0x80000000;
    v22 = v30 & 4;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::GetImpl'::`2'::impl);
    v24 = L" | Preprod";
    v25 = L" | Attested";
    if ( IsEnabled )
    {
      v26 = L" | Kernel";
      if ( (v30 & 8) == 0 )
        v26 = &qword_14004E980;
      if ( !v22 )
        v24 = &qword_14004E980;
      if ( !v21 )
        v25 = &qword_14004E980;
      DevRtlWriteTextLog(a5, 512, 524292, "Attributes     - %ws%ws%ws%ws", v20, v25, v24, v26);
    }
    else
    {
      if ( !v22 )
        v24 = &qword_14004E980;
      if ( !v21 )
        v25 = &qword_14004E980;
      DevRtlWriteTextLog(a5, 512, 524292, "Attributes     - %ws%ws%ws", v20, v25, v24);
    }
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::GetImpl'::`2'::impl)
    && v32 != -1 )
  {
    if ( (_DWORD)v32 )
      DevRtlWriteTextLog(
        a5,
        512,
        524292,
        "WHCP Version   - %hu.%hu.%hu.%hu",
        HIWORD(HIDWORD(v32)),
        WORD2(v32),
        WORD1(v32),
        (unsigned __int16)v32);
    else
      DevRtlWriteTextLog(a5, 512, 524292, "WHCP Version   - %hu.%hu", HIWORD(HIDWORD(v32)), WORD2(v32));
  }
}

```

## disassembly

```asm
0x14002a0ac  mov     [rsp-8+arg_10], rbx
0x14002a0b1  push    rbp
0x14002a0b2  push    rsi
0x14002a0b3  push    rdi
0x14002a0b4  push    r12
0x14002a0b6  push    r13
0x14002a0b8  push    r14
0x14002a0ba  push    r15
0x14002a0bc  lea     rbp, [rsp-260h]
0x14002a0c4  sub     rsp, 360h
0x14002a0cb  mov     rax, cs:__security_cookie
0x14002a0d2  xor     rax, rsp
0x14002a0d5  mov     [rbp+290h+var_40], rax
0x14002a0dc  mov     r13d, [rdx+4]
0x14002a0e0  lea     r12, [rdx+420h]
0x14002a0e7  mov     rax, [r12]
0x14002a0eb  xor     esi, esi
0x14002a0ed  and     r13d, 1
0x14002a0f1  mov     [rbp+290h+var_310], r9d
0x14002a0f5  sub     rax, qword ptr cs:GUID_DEVCLASS_EXTENSION.Data1
0x14002a0fc  xorps   xmm0, xmm0
0x14002a0ff  mov     [rbp+290h+var_30C], r8d
0x14002a103  mov     rdi, rdx
0x14002a106  mov     rbx, rcx
0x14002a109  mov     [rsp+390h+var_324], esi
0x14002a10d  mov     [rsp+390h+var_330], esi
0x14002a111  mov     dword ptr [rsp+390h+dwBytes], esi
0x14002a115  mov     dword ptr [rsp+390h+dwBytes+4], esi
0x14002a119  movups  xmmword ptr [rbp+290h+SystemTime.wYear], xmm0
0x14002a11d  mov     [rsp+390h+var_318], 0FFFFFFFFFFFFFFFFh
0x14002a126  jnz     short loc_14002A134
0x14002a128  mov     rax, [r12+8]
0x14002a12d  sub     rax, qword ptr cs:GUID_DEVCLASS_EXTENSION.Data4
0x14002a134  test    rax, rax
0x14002a137  mov     [rsp+390h+var_350], esi
0x14002a13b  mov     ecx, esi
0x14002a13d  mov     [rsp+390h+var_358], rsi
0x14002a142  setz    cl
0x14002a145  mov     dword ptr [rsp+390h+var_360], 4
0x14002a14d  lea     r15, [rdx+0Ch]
0x14002a151  mov     [rsp+390h+var_320], ecx
0x14002a155  lea     rax, [rsp+390h+dwBytes+4]
0x14002a15a  mov     r14d, 2
0x14002a160  mov     [rsp+390h+var_368], rax
0x14002a165  lea     r9, DEVPKEY_DriverPackage_SignerScore
0x14002a16c  lea     rax, [rsp+390h+var_330]
0x14002a171  mov     rcx, rbx
0x14002a174  mov     r8, r15
0x14002a177  mov     [rsp+390h+var_370], rax
0x14002a17c  mov     edx, r14d
0x14002a17f  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a185  test    eax, eax
0x14002a187  jz      short loc_14002A190
0x14002a189  cmp     [rsp+390h+var_330], 7
0x14002a18e  jz      short loc_14002A198
0x14002a190  mov     dword ptr [rsp+390h+dwBytes+4], 0FF000000h
0x14002a198  mov     [rsp+390h+var_350], esi
0x14002a19c  lea     rax, [rsp+390h+dwBytes]
0x14002a1a1  mov     [rsp+390h+var_358], rax
0x14002a1a6  lea     r9, DEVPKEY_DriverPackage_SubmissionId
0x14002a1ad  lea     rax, [rbp+290h+var_250]
0x14002a1b1  mov     dword ptr [rsp+390h+var_360], 208h
0x14002a1b9  mov     [rsp+390h+var_368], rax
0x14002a1be  mov     r8, r15
0x14002a1c1  lea     rax, [rsp+390h+var_330]
0x14002a1c6  mov     edx, r14d
0x14002a1c9  mov     rcx, rbx
0x14002a1cc  mov     [rsp+390h+var_370], rax
0x14002a1d1  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a1d7  test    eax, eax
0x14002a1d9  jz      short loc_14002A1E9
0x14002a1db  cmp     [rsp+390h+var_330], 12h
0x14002a1e0  jnz     short loc_14002A1E9
0x14002a1e2  cmp     dword ptr [rsp+390h+dwBytes], r14d
0x14002a1e7  jnb     short loc_14002A1ED
0x14002a1e9  mov     [rbp+290h+var_250], si
0x14002a1ed  mov     [rsp+390h+var_350], esi
0x14002a1f1  lea     rax, [rsp+390h+dwBytes]
0x14002a1f6  mov     [rsp+390h+var_358], rax
0x14002a1fb  lea     r9, DEVPKEY_DriverPackage_DriverFlightIds
0x14002a202  mov     dword ptr [rsp+390h+var_360], esi
0x14002a206  lea     rax, [rsp+390h+var_330]
0x14002a20b  mov     [rsp+390h+var_368], rsi
0x14002a210  mov     r8, r15
0x14002a213  mov     edx, 2
0x14002a218  mov     [rsp+390h+var_370], rax
0x14002a21d  mov     rcx, rbx
0x14002a220  mov     r14, rsi
0x14002a223  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a229  test    eax, eax
0x14002a22b  jnz     loc_14002A2C3
0x14002a231  call    cs:__imp_GetLastError
0x14002a237  cmp     eax, 7Ah ; 'z'
0x14002a23a  jnz     loc_14002A2C3
0x14002a240  mov     r8d, dword ptr [rsp+390h+dwBytes]; dwBytes
0x14002a245  xor     edx, edx; dwFlags
0x14002a247  mov     rcx, cs:hHeap; hHeap
0x14002a24e  call    cs:__imp_HeapAlloc
0x14002a254  mov     r14, rax
0x14002a257  test    rax, rax
0x14002a25a  jz      short loc_14002A2C3
0x14002a25c  mov     ecx, dword ptr [rsp+390h+dwBytes]
0x14002a260  lea     rax, [rsp+390h+dwBytes]
0x14002a265  mov     [rsp+390h+var_350], esi
0x14002a269  lea     r9, DEVPKEY_DriverPackage_DriverFlightIds
0x14002a270  mov     [rsp+390h+var_358], rax
0x14002a275  mov     r8, r15
0x14002a278  mov     dword ptr [rsp+390h+var_360], ecx
0x14002a27c  lea     rax, [rsp+390h+var_330]
0x14002a281  mov     [rsp+390h+var_368], r14
0x14002a286  mov     rcx, rbx
0x14002a289  mov     edx, 2
0x14002a28e  mov     [rsp+390h+var_370], rax
0x14002a293  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a299  test    eax, eax
0x14002a29b  jz      short loc_14002A2AE
0x14002a29d  cmp     [rsp+390h+var_330], 2012h
0x14002a2a5  jnz     short loc_14002A2AE
0x14002a2a7  cmp     dword ptr [rsp+390h+dwBytes], 2
0x14002a2ac  jnb     short loc_14002A2C3
0x14002a2ae  mov     rcx, cs:hHeap; hHeap
0x14002a2b5  mov     r8, r14; lpMem
0x14002a2b8  xor     edx, edx; dwFlags
0x14002a2ba  call    cs:__imp_HeapFree
0x14002a2c0  mov     r14, rsi
0x14002a2c3  mov     [rsp+390h+var_350], esi
0x14002a2c7  lea     rax, [rsp+390h+var_324]
0x14002a2cc  mov     [rsp+390h+var_358], rsi
0x14002a2d1  lea     r9, DEVPKEY_DriverPackage_CatalogAttributes
0x14002a2d8  mov     dword ptr [rsp+390h+var_360], 4
0x14002a2e0  mov     r8, r15
0x14002a2e3  mov     [rsp+390h+var_368], rax
0x14002a2e8  mov     edx, 2
0x14002a2ed  lea     rax, [rsp+390h+var_330]
0x14002a2f2  mov     rcx, rbx
0x14002a2f5  mov     [rsp+390h+var_370], rax
0x14002a2fa  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a300  test    eax, eax
0x14002a302  jz      short loc_14002A30B
0x14002a304  cmp     [rsp+390h+var_330], 7
0x14002a309  jz      short loc_14002A313
0x14002a30b  mov     [rsp+390h+var_324], 0FFFFFFFFh
0x14002a313  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging> `wil::Feature<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::GetImpl(void)'::`2'::impl
0x14002a31a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceInstall_AdditionalCatalogAttributeLogging>::__private_IsEnabled(void)
0x14002a31f  test    al, al
0x14002a321  jz      short loc_14002A374
0x14002a323  mov     [rsp+390h+var_350], esi
0x14002a327  lea     rax, [rsp+390h+var_318]
0x14002a32c  mov     [rsp+390h+var_358], rsi
0x14002a331  lea     r9, DEVPKEY_DriverPackage_CertificationVersion
0x14002a338  mov     dword ptr [rsp+390h+var_360], 8
0x14002a340  mov     r8, r15
0x14002a343  mov     [rsp+390h+var_368], rax
0x14002a348  mov     edx, 2
0x14002a34d  lea     rax, [rsp+390h+var_330]
0x14002a352  mov     rcx, rbx
0x14002a355  mov     [rsp+390h+var_370], rax
0x14002a35a  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002a360  test    eax, eax
0x14002a362  jz      short loc_14002A36B
0x14002a364  cmp     [rsp+390h+var_330], 9
0x14002a369  jz      short loc_14002A374
0x14002a36b  mov     [rsp+390h+var_318], 0FFFFFFFFFFFFFFFFh
0x14002a374  mov     eax, dword ptr [rsp+390h+dwBytes+4]
0x14002a378  cmp     eax, 0D000003h
0x14002a37d  jz      short loc_14002A3DD
0x14002a37f  cmp     eax, 0D000004h
0x14002a384  jz      short loc_14002A3D4
0x14002a386  cmp     eax, 0D000005h
0x14002a38b  jz      short loc_14002A3CB
0x14002a38d  cmp     eax, 0F000000h
0x14002a392  jz      short loc_14002A3C2
0x14002a394  cmp     eax, 80000000h
0x14002a399  jz      short loc_14002A3B9
0x14002a39b  and     eax, 0FF000000h
0x14002a3a0  lea     rsi, aMsft; "MSFT"
0x14002a3a7  cmp     eax, 0D000000h
0x14002a3ac  lea     rcx, aUnknown; "Unknown"
0x14002a3b3  cmovnz  rsi, rcx
0x14002a3b7  jmp     short loc_14002A3E4
0x14002a3b9  lea     rsi, aUnsigned; "Unsigned"
0x14002a3c0  jmp     short loc_14002A3E4
0x14002a3c2  lea     rsi, aAuthenticode; "Authenticode"
0x14002a3c9  jmp     short loc_14002A3E4
0x14002a3cb  lea     rsi, aWhql; "WHQL"
0x14002a3d2  jmp     short loc_14002A3E4
0x14002a3d4  lea     rsi, aUnclassified; "Unclassified"
0x14002a3db  jmp     short loc_14002A3E4
0x14002a3dd  lea     rsi, aInbox; "Inbox"
0x14002a3e4  cmp     [rsp+390h+var_320], 0
0x14002a3e9  lea     rcx, qword_14004E980
0x14002a3f0  mov     rbx, [rbp+290h+arg_20]
0x14002a3f7  lea     rax, aExtension; "Extension "
0x14002a3fe  cmovz   rax, rcx
0x14002a402  lea     r9, aDriverWsnode; "Driver %wsNode:"
0x14002a409  mov     rcx, rbx
0x14002a40c  mov     [rsp+390h+var_370], rax
0x14002a411  mov     edx, 200h
0x14002a416  mov     r8d, 4
0x14002a41c  call    cs:__imp_DevRtlWriteTextLog
0x14002a422  cmp     [rbp+290h+var_310], 0
0x14002a426  lea     rax, qword_14004E980
0x14002a42d  lea     r8, aOutranked; "Outranked"
0x14002a434  lea     rdx, aDesignated; " | Designated"
0x14002a43b  cmovz   rdx, rax
0x14002a43f  lea     rcx, aInstalled; " | Installed"
0x14002a446  cmp     [rbp+290h+var_30C], 0
0x14002a44a  lea     r9, aStatusWsWsWs; "Status         - %ws%ws%ws"
0x14002a451  mov     [rsp+390h+var_360], rdx
0x14002a456  mov     edx, 200h
0x14002a45b  cmovz   rcx, rax
0x14002a45f  test    r13d, r13d
0x14002a462  mov     [rsp+390h+var_368], rcx
0x14002a467  lea     rax, aSelected; "Selected"
0x14002a46e  cmovz   rax, r8
0x14002a472  mov     rcx, rbx
0x14002a475  mov     r8d, 80004h
0x14002a47b  mov     [rsp+390h+var_370], rax
0x14002a480  call    cs:__imp_DevRtlWriteTextLog
0x14002a486  lea     rax, [rdi+216h]
0x14002a48d  xor     r13d, r13d
0x14002a490  mov     r8d, 80004h
0x14002a496  mov     rcx, rbx
0x14002a499  cmp     [rax], r13w
0x14002a49d  jz      short loc_14002A4C1
0x14002a49f  mov     [rsp+390h+var_368], r15
0x14002a4a4  lea     r9, aDriverInfWsWs; "Driver INF     - %ws (%ws)"
0x14002a4ab  mov     r15d, 200h
0x14002a4b1  mov     [rsp+390h+var_370], rax
0x14002a4b6  mov     edx, r15d
0x14002a4b9  call    cs:__imp_DevRtlWriteTextLog
0x14002a4bf  jmp     short loc_14002A4DC
0x14002a4c1  mov     [rsp+390h+var_370], r15
0x14002a4c6  lea     r9, aDriverInfWs; "Driver INF     - %ws"
0x14002a4cd  mov     r15d, 200h
0x14002a4d3  mov     edx, r15d
0x14002a4d6  call    cs:__imp_DevRtlWriteTextLog
0x14002a4dc  mov     rcx, r12
0x14002a4df  call    SpUtilsIsGuidNull
0x14002a4e4  test    eax, eax
0x14002a4e6  jnz     short loc_14002A51C
0x14002a4e8  lea     rdx, [rbp+290h+var_2F0]
0x14002a4ec  call    SpUtilsStringFromGuid
0x14002a4f1  mov     r12d, 80004h
0x14002a4f7  test    eax, eax
0x14002a4f9  jnz     short loc_14002A522
0x14002a4fb  lea     rax, [rbp+290h+var_2F0]
0x14002a4ff  mov     r8d, r12d
0x14002a502  lea     r9, aClassGuidWs; "Class GUID     - %ws"
0x14002a509  mov     [rsp+390h+var_370], rax
0x14002a50e  mov     edx, r15d
0x14002a511  mov     rcx, rbx
0x14002a514  call    cs:__imp_DevRtlWriteTextLog
0x14002a51a  jmp     short loc_14002A522
0x14002a51c  mov     r12d, 80004h
0x14002a522  cmp     [rsp+390h+var_320], r13d
0x14002a527  jz      short loc_14002A565
0x14002a529  lea     rcx, [rdi+440h]
0x14002a530  call    SpUtilsIsGuidNull
0x14002a535  test    eax, eax
0x14002a537  jnz     short loc_14002A565
0x14002a539  lea     rdx, [rbp+290h+var_2A0]
0x14002a53d  call    SpUtilsStringFromGuid
0x14002a542  test    eax, eax
0x14002a544  jnz     short loc_14002A565
0x14002a546  lea     rax, [rbp+290h+var_2A0]
0x14002a54a  mov     r8d, r12d
0x14002a54d  lea     r9, aExtensionIdWs; "Extension ID   - %ws"
0x14002a554  mov     [rsp+390h+var_370], rax
0x14002a559  mov     edx, r15d
0x14002a55c  mov     rcx, rbx
0x14002a55f  call    cs:__imp_DevRtlWriteTextLog
0x14002a565  lea     rcx, [rdi+430h]; lpFileTime
0x14002a56c  lea     rdx, [rbp+290h+SystemTime]; lpSystemTime
0x14002a570  call    cs:__imp_FileTimeToSystemTime
0x14002a576  test    eax, eax
0x14002a578  jnz     short loc_14002A581
0x14002a57a  xorps   xmm0, xmm0
0x14002a57d  movups  xmmword ptr [rbp+290h+SystemTime.wYear], xmm0
0x14002a581  movzx   ecx, word ptr [rdi+43Ah]
0x14002a588  movzx   edx, word ptr [rdi+43Ch]
0x14002a58f  movzx   r8d, word ptr [rdi+43Eh]
0x14002a597  movzx   r9d, [rbp+290h+SystemTime.wYear]
0x14002a59c  movzx   eax, word ptr [rdi+438h]
0x14002a5a3  movzx   r10d, [rbp+290h+SystemTime.wDay]
0x14002a5a8  movzx   r11d, [rbp+290h+SystemTime.wMonth]
0x14002a5ad  mov     [rsp+390h+var_340], eax
0x14002a5b1  mov     [rsp+390h+var_348], ecx
0x14002a5b5  mov     rcx, rbx
0x14002a5b8  mov     [rsp+390h+var_350], edx
0x14002a5bc  mov     edx, r15d
0x14002a5bf  mov     dword ptr [rsp+390h+var_358], r8d
0x14002a5c4  mov     r8d, r12d
0x14002a5c7  mov     dword ptr [rsp+390h+var_360], r9d
0x14002a5cc  lea     r9, aDriverVersion0; "Driver Version - %02hu/%02hu/%04hu,%hu."...
0x14002a5d3  mov     dword ptr [rsp+390h+var_368], r10d
0x14002a5d8  mov     dword ptr [rsp+390h+var_370], r11d
0x14002a5dd  call    cs:__imp_DevRtlWriteTextLog
0x14002a5e3  lea     rax, [rdi+450h]
0x14002a5ea  cmp     [rax], r13w
  ... truncated ...
```
