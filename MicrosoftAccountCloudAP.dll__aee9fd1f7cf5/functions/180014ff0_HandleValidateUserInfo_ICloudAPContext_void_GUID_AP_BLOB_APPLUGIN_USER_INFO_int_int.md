# HandleValidateUserInfo(ICloudAPContext *,void *,_GUID *,_AP_BLOB *,_APPLUGIN_USER_INFO * *,int *,int *)

- ea: `0x180014ff0`
- end: `0x180015330`
- name: `?HandleValidateUserInfo@@YAJPEAVICloudAPContext@@PEAXPEAU_GUID@@PEAU_AP_BLOB@@PEAPEAU_APPLUGIN_USER_INFO@@PEAH5@Z`
- size: `832`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, __int64, struct _GUID *, struct _AP_BLOB *, struct _APPLUGIN_USER_INFO **, int *, int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000a070`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d824`
- `0x18000d980`
- `0x18000e0c4`
- `0x18000e0f0`
- `0x18000f420`
- `0x18000f84c`
- `0x180010320`
- `0x180010830`
- `0x180010db0`
- `0x180010e70`
- `0x1800110e0`
- `0x180012578`
- `0x180014ff0`
- `0x180015d64`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180015192`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180015192`

## string_xrefs

- `0x18001508e`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800151cb`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800151ef`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x18001526e`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180015261`: `ShouldUpdateDefaultCreds updateDefaultCreds=%d status=%d, continuing...`

## pseudocode

```c
__int64 __fastcall HandleValidateUserInfo(
        struct ICloudAPContext *a1,
        __int64 a2,
        struct _GUID *a3,
        struct _AP_BLOB *a4,
        struct _APPLUGIN_USER_INFO **a5,
        int *a6,
        int *a7)
{
  __int64 v10; // rdx
  int v11; // r8d
  struct _APPLUGIN_USER_INFO **v12; // r15
  int v13; // edi
  unsigned __int16 *v14; // rbx
  int *v15; // rsi
  int *v16; // r14
  struct MSACloudAPValidationInfo *v17; // rdi
  int SystemStoreEntryFromCID; // eax
  __int64 (__fastcall *v19)(__int64, _QWORD *, const wchar_t *, __int64, int *); // rbx
  __int64 BufferSetLength; // rax
  int v21; // ebx
  __int64 v22; // rbx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int updated; // eax
  int v26; // ecx
  const unsigned __int16 *SourceString; // [rsp+20h] [rbp-71h]
  PCWSTR SourceStringa; // [rsp+20h] [rbp-71h]
  PCWSTR SourceStringb; // [rsp+20h] [rbp-71h]
  unsigned __int16 *v31; // [rsp+30h] [rbp-61h] BYREF
  wchar_t *String; // [rsp+38h] [rbp-59h] BYREF
  int v33; // [rsp+40h] [rbp-51h] BYREF
  __int64 v34; // [rsp+48h] [rbp-49h] BYREF
  struct MSACloudAPValidationInfo *v35[3]; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v36[3]; // [rsp+68h] [rbp-29h] BYREF
  _QWORD v37[10]; // [rsp+80h] [rbp-11h] BYREF
  int v38; // [rsp+E0h] [rbp+4Fh] BYREF
  __int64 v39; // [rsp+E8h] [rbp+57h] BYREF

  v39 = a2;
  v38 = 0;
  memset(v36, 0, sizeof(v36));
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&String);
  v33 = 0x2000;
  v34 = 0;
  memset(v35, 0, sizeof(v35));
  v39 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 16LL))(a1);
  v37[0] = "HandleValidateUserInfo";
  v37[1] = &v38;
  v37[2] = 0;
  v37[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleValidateUserInfo",
    (const char *)0x207,
    0,
    SourceString);
  v12 = a5;
  if ( !a5 )
  {
    v13 = -1073741811;
    v38 = -1073741811;
    v14 = v31;
    goto LABEL_31;
  }
  *a5 = 0;
  v15 = a6;
  if ( !a6 || (v16 = a7) == 0 || (*a6 = 0, *v16 = 0, !a4) || !*((_QWORD *)a4 + 1) || *(_DWORD *)a4 <= 0x38u )
  {
    v13 = -1073741811;
    v38 = -1073741811;
    goto LABEL_28;
  }
  v13 = DeserializeOpaqueBlob(a4, v35);
  v38 = v13;
  if ( v13 < 0 )
  {
LABEL_28:
    v14 = v31;
LABEL_29:
    if ( *v12 )
    {
      (*((void (**)(void))g_MSACloudAPPluginLsaFunctions + 7))();
      *v12 = 0;
      v13 = v38;
    }
    goto LABEL_31;
  }
  v17 = v35[0];
  if ( *(_DWORD *)v35[0] == 2 )
    *v15 = 1;
  SystemStoreEntryFromCID = GetSystemStoreEntryFromCID((__int64)a1, (__int64)v17 + 8, (ATL::CRegKey *)v36, &v31);
  v38 = SystemStoreEntryFromCID;
  if ( SystemStoreEntryFromCID < 0 )
  {
    LODWORD(SourceStringa) = SystemStoreEntryFromCID;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      0x255u,
      L"GetSystemStoreEntryFromCID failed with %d, continuing...",
      SourceStringa);
    v38 = 0;
    v23 = ATL::CSimpleStringT<unsigned short,0>::StringLength(*((_QWORD *)v17 + 28));
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, v24, v23);
  }
  else
  {
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD *, const wchar_t *, __int64, int *))(*(_QWORD *)v39 + 56LL);
    BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&String, 0x2000);
    v21 = v19(v39, v36, L"LatestDPAPIKeyVersion", BufferSetLength, &v33);
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&String);
    if ( v21 )
    {
      LODWORD(SourceStringb) = v21;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        0x250u,
        L"Query for DPAPI Key version failed with %d, continuing...",
        SourceStringb);
    }
    else if ( a3 )
    {
      v22 = _wtoi64(String);
      if ( (int)GetVersionTimeStamp(a3, &v34) >= 0 && v22 > v34 )
        *v16 = 1;
    }
  }
  v14 = v31;
  if ( *((_DWORD *)v31 - 4) && !*v15 )
  {
    LOBYTE(v39) = 0;
    updated = ShouldUpdateDefaultCreds(a1, v31, (bool *)&v39);
    v38 = updated;
    v26 = (unsigned __int8)v39;
    if ( !updated && (_BYTE)v39 )
      *v15 = 1;
    LODWORD(SourceStringb) = v26;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      0x266u,
      L"ShouldUpdateDefaultCreds updateDefaultCreds=%d status=%d, continuing...",
      SourceStringb,
      updated);
    v38 = 0;
  }
  v13 = PopulateUserInfo(a1, v17, 0, v14, (PCWSTR)v17 + 4, v12);
  v38 = v13;
  if ( v13 < 0 )
    goto LABEL_29;
LABEL_31:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v37, v10, v11);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>((__int64)v35);
  ATL::CStringData::Release((ATL::CStringData *)(String - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
  ATL::CRegKey::Close((ATL::CRegKey *)v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180014ff0  mov     [rsp-8+arg_10], rbx
0x180014ff5  mov     [rsp-8+arg_8], rdx
0x180014ffa  push    rbp
0x180014ffb  push    rsi
0x180014ffc  push    rdi
0x180014ffd  push    r12
0x180014fff  push    r13
0x180015001  push    r14
0x180015003  push    r15
0x180015005  lea     rbp, [rsp-0Fh]
0x18001500a  sub     rsp, 0A0h
0x180015011  mov     rbx, r9
0x180015014  mov     r13, r8
0x180015017  mov     r12, rcx
0x18001501a  xor     edi, edi
0x18001501c  mov     [rbp+3Fh+arg_0], edi
0x18001501f  mov     [rbp+3Fh+var_68], rdi
0x180015023  mov     [rbp+3Fh+var_60], rdi
0x180015027  mov     [rbp+3Fh+var_58], rdi
0x18001502b  lea     rcx, [rbp+3Fh+var_A0]
0x18001502f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180015034  nop
0x180015035  lea     rcx, [rbp+3Fh+String]
0x180015039  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001503e  nop
0x18001503f  mov     [rbp+3Fh+var_90], 2000h
0x180015046  mov     [rbp+3Fh+var_88], rdi
0x18001504a  mov     [rbp+3Fh+var_80], rdi
0x18001504e  mov     [rbp+3Fh+var_70], rdi
0x180015052  mov     [rbp+3Fh+var_78], rdi
0x180015056  mov     rax, [r12]
0x18001505a  mov     rcx, r12
0x18001505d  mov     rax, [rax+10h]
0x180015061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015066  mov     [rbp+3Fh+arg_8], rax
0x18001506a  lea     rdx, aHandlevalidate; "HandleValidateUserInfo"
0x180015071  mov     [rbp+3Fh+var_50], rdx
0x180015075  lea     rax, [rbp+3Fh+arg_0]
0x180015079  mov     [rbp+3Fh+var_48], rax
0x18001507d  mov     [rbp+3Fh+var_40], rdi
0x180015081  mov     [rbp+3Fh+var_38], rdi
0x180015085  xor     r9d, r9d; unsigned int
0x180015088  mov     r8d, 207h; char *
0x18001508e  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180015095  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001509a  nop
0x18001509b  mov     r15, [rbp+3Fh+arg_20]
0x18001509f  test    r15, r15
0x1800150a2  jnz     short loc_1800150B5
0x1800150a4  mov     edi, 0C000000Dh
0x1800150a9  mov     [rbp+3Fh+arg_0], edi
0x1800150ac  mov     rbx, [rbp+3Fh+var_A0]
0x1800150b0  jmp     loc_1800152DE
0x1800150b5  mov     [r15], rdi
0x1800150b8  mov     rsi, [rbp+3Fh+arg_28]
0x1800150bc  test    rsi, rsi
0x1800150bf  jz      loc_1800152B0
0x1800150c5  mov     r14, [rbp+3Fh+arg_30]
0x1800150c9  test    r14, r14
0x1800150cc  jz      loc_1800152B0
0x1800150d2  mov     [rsi], edi
0x1800150d4  mov     [r14], edi
0x1800150d7  test    rbx, rbx
0x1800150da  jz      loc_1800152B0
0x1800150e0  cmp     [rbx+8], rdi
0x1800150e4  jz      loc_1800152B0
0x1800150ea  cmp     dword ptr [rbx], 38h ; '8'
0x1800150ed  jbe     loc_1800152B0
0x1800150f3  lea     rdx, [rbp+3Fh+var_80]; struct MSACloudAPValidationInfo **
0x1800150f7  mov     rcx, rbx; struct _AP_BLOB *
0x1800150fa  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x1800150ff  mov     edi, eax
0x180015101  mov     [rbp+3Fh+arg_0], eax
0x180015104  test    eax, eax
0x180015106  js      loc_1800152B8
0x18001510c  mov     rdi, [rbp+3Fh+var_80]
0x180015110  cmp     dword ptr [rdi], 2
0x180015113  jnz     short loc_18001511B
0x180015115  mov     dword ptr [rsi], 1
0x18001511b  lea     rdx, [rdi+8]
0x18001511f  lea     r9, [rbp+3Fh+var_A0]
0x180015123  lea     r8, [rbp+3Fh+var_68]
0x180015127  mov     rcx, r12
0x18001512a  call    ?GetSystemStoreEntryFromCID@@YAJPEAVICloudAPContext@@PEBGAEAVCRegKey@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; GetSystemStoreEntryFromCID(ICloudAPContext *,ushort const *,ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001512f  mov     [rbp+3Fh+arg_0], eax
0x180015132  test    eax, eax
0x180015134  js      loc_1800151DE
0x18001513a  mov     rax, [rbp+3Fh+arg_8]
0x18001513e  mov     rax, [rax]
0x180015141  mov     rbx, [rax+38h]
0x180015145  mov     edx, 2000h
0x18001514a  lea     rcx, [rbp+3Fh+String]
0x18001514e  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180015153  lea     rcx, [rbp+3Fh+var_90]
0x180015157  mov     [rsp+0D0h+SourceString], rcx
0x18001515c  mov     r9, rax
0x18001515f  lea     r8, aLatestdpapikey; "LatestDPAPIKeyVersion"
0x180015166  lea     rdx, [rbp+3Fh+var_68]
0x18001516a  mov     rcx, [rbp+3Fh+arg_8]
0x18001516e  mov     rax, rbx
0x180015171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015176  mov     ebx, eax
0x180015178  lea     rcx, [rbp+3Fh+String]
0x18001517c  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180015181  test    ebx, ebx
0x180015183  jnz     short loc_1800151BA
0x180015185  test    r13, r13
0x180015188  jz      loc_180015222
0x18001518e  mov     rcx, [rbp+3Fh+String]; String
0x180015192  call    cs:__imp__wtoi64
0x180015198  mov     rbx, rax
0x18001519b  lea     rdx, [rbp+3Fh+var_88]; __int64 *
0x18001519f  mov     rcx, r13; struct _GUID *
0x1800151a2  call    ?GetVersionTimeStamp@@YAJAEBU_GUID@@AEA_J@Z; GetVersionTimeStamp(_GUID const &,__int64 &)
0x1800151a7  test    eax, eax
0x1800151a9  js      short loc_180015222
0x1800151ab  cmp     rbx, [rbp+3Fh+var_88]
0x1800151af  jle     short loc_180015222
0x1800151b1  mov     dword ptr [r14], 1
0x1800151b8  jmp     short loc_180015222
0x1800151ba  mov     dword ptr [rsp+0D0h+SourceString], ebx
0x1800151be  lea     r9, aQueryForDpapiK; "Query for DPAPI Key version failed with"...
0x1800151c5  mov     r8d, 250h; unsigned int
0x1800151cb  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800151d2  mov     ecx, 2; unsigned __int8
0x1800151d7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800151dc  jmp     short loc_180015222
0x1800151de  mov     dword ptr [rsp+0D0h+SourceString], eax
0x1800151e2  lea     r9, aGetsystemstore; "GetSystemStoreEntryFromCID failed with "...
0x1800151e9  mov     r8d, 255h; unsigned int
0x1800151ef  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800151f6  mov     ecx, 2; unsigned __int8
0x1800151fb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180015200  mov     [rbp+3Fh+arg_0], 0
0x180015207  mov     rcx, [rdi+0E0h]
0x18001520e  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180015213  mov     r8d, eax
0x180015216  mov     rdx, rcx
0x180015219  lea     rcx, [rbp+3Fh+var_A0]
0x18001521d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180015222  mov     rbx, [rbp+3Fh+var_A0]
0x180015226  cmp     dword ptr [rbx-10h], 0
0x18001522a  jz      short loc_180015286
0x18001522c  cmp     dword ptr [rsi], 0
0x18001522f  jnz     short loc_180015286
0x180015231  mov     byte ptr [rbp+3Fh+arg_8], 0
0x180015235  lea     r8, [rbp+3Fh+arg_8]; bool *
0x180015239  mov     rdx, rbx; unsigned __int16 *
0x18001523c  mov     rcx, r12; struct ICloudAPContext *
0x18001523f  call    ?ShouldUpdateDefaultCreds@@YAJPEAVICloudAPContext@@PEBGPEA_N@Z; ShouldUpdateDefaultCreds(ICloudAPContext *,ushort const *,bool *)
0x180015244  mov     [rbp+3Fh+arg_0], eax
0x180015247  movzx   ecx, byte ptr [rbp+3Fh+arg_8]
0x18001524b  test    eax, eax
0x18001524d  jnz     short loc_180015259
0x18001524f  test    cl, cl
0x180015251  jz      short loc_180015259
0x180015253  mov     dword ptr [rsi], 1
0x180015259  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001525d  mov     dword ptr [rsp+0D0h+SourceString], ecx
0x180015261  lea     r9, aShouldupdatede; "ShouldUpdateDefaultCreds updateDefaultC"...
0x180015268  mov     r8d, 266h; unsigned int
0x18001526e  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180015275  mov     ecx, 5; unsigned __int8
0x18001527a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001527f  mov     [rbp+3Fh+arg_0], 0
0x180015286  mov     [rsp+0D0h+var_A8], r15; struct _APPLUGIN_USER_INFO **
0x18001528b  lea     rax, [rdi+8]
0x18001528f  mov     [rsp+0D0h+SourceString], rax; SourceString
0x180015294  mov     r9, rbx; unsigned __int16 *
0x180015297  xor     r8d, r8d; void *
0x18001529a  mov     rdx, rdi; struct MSACloudAPValidationInfo *
0x18001529d  mov     rcx, r12; struct ICloudAPContext *
0x1800152a0  call    ?PopulateUserInfo@@YAJPEAVICloudAPContext@@PEAUMSACloudAPValidationInfo@@PEAXPEBG3PEAPEAU_APPLUGIN_USER_INFO@@@Z; PopulateUserInfo(ICloudAPContext *,MSACloudAPValidationInfo *,void *,ushort const *,ushort const *,_APPLUGIN_USER_INFO * *)
0x1800152a5  mov     edi, eax
0x1800152a7  mov     [rbp+3Fh+arg_0], eax
0x1800152aa  test    eax, eax
0x1800152ac  jns     short loc_1800152DE
0x1800152ae  jmp     short loc_1800152BC
0x1800152b0  mov     edi, 0C000000Dh
0x1800152b5  mov     [rbp+3Fh+arg_0], edi
0x1800152b8  mov     rbx, [rbp+3Fh+var_A0]
0x1800152bc  mov     rcx, [r15]
0x1800152bf  test    rcx, rcx
0x1800152c2  jz      short loc_1800152DE
0x1800152c4  mov     rax, cs:?g_MSACloudAPPluginLsaFunctions@@3PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@EA; _CLOUDAP_SECPKG_FUNCTION_TABLE * g_MSACloudAPPluginLsaFunctions
0x1800152cb  mov     rax, [rax+38h]
0x1800152cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152d4  mov     qword ptr [r15], 0
0x1800152db  mov     edi, [rbp+3Fh+arg_0]
0x1800152de  lea     rcx, [rbp+3Fh+var_50]
0x1800152e2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800152e7  nop
0x1800152e8  lea     rcx, [rbp+3Fh+var_80]
0x1800152ec  call    ??1?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAA@XZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(void)
0x1800152f1  nop
0x1800152f2  mov     rcx, [rbp+3Fh+String]
0x1800152f6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800152fa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800152ff  nop
0x180015300  lea     rcx, [rbx-18h]; this
0x180015304  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180015309  nop
0x18001530a  lea     rcx, [rbp+3Fh+var_68]; this
0x18001530e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015313  mov     eax, edi
0x180015315  mov     rbx, [rsp+0D0h+arg_10]
0x18001531d  add     rsp, 0A0h
0x180015324  pop     r15
0x180015326  pop     r14
0x180015328  pop     r13
0x18001532a  pop     r12
0x18001532c  pop     rdi
0x18001532d  pop     rsi
0x18001532e  pop     rbp
0x18001532f  retn
```
