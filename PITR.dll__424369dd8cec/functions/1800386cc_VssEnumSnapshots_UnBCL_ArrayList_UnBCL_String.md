# VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x1800386cc`
- end: `0x180038de8`
- name: `?VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z`
- size: `1820`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a6fc`

## callees

- `0x18000253c`
- `0x180009e04`
- `0x18001d540`
- `0x18001de74`
- `0x180037074`
- `0x1800386cc`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d51`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180038925`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180038925`
- `WDSCORE!CurrentIP` at `0x180038a22`
- `WDSCORE!CurrentIP` at `0x180038ab4`
- `WDSCORE!CurrentIP` at `0x180038b46`
- `WDSCORE!CurrentIP` at `0x180038bd9`
- `WDSCORE!CurrentIP` at `0x180038c6e`
- `WDSCORE!CurrentIP` at `0x180038d59`
- `WDSCORE!CurrentIP` at `0x180038a22`
- `WDSCORE!CurrentIP` at `0x180038ab4`
- `WDSCORE!CurrentIP` at `0x180038b46`
- `WDSCORE!CurrentIP` at `0x180038bd9`
- `WDSCORE!CurrentIP` at `0x180038c6e`
- `WDSCORE!CurrentIP` at `0x180038d59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038a80`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038b12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038ba4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038c37`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038ccc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038db7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038a80`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038b12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038ba4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038c37`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038ccc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038db7`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800389c4`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800389c4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003894c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003894c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003896d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18003896d`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18003872a`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18003872a`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x1800389b1`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x1800389b1`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18003875b`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18003875b`

## string_xrefs

- `0x180038a5d`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038aef`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038b81`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038c14`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038ca9`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038d94`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038a2e`: `VssEnumSnapshots: Failed to create backup components. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall VssEnumSnapshots(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rax
  int VssBackupComponentsInternal; // r14d
  __int64 v5; // rax
  int v6; // r14d
  __int64 v7; // rax
  int v8; // r14d
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, GUID *, __int64); // r15
  __int64 v11; // rax
  int v12; // r15d
  __int64 v13; // rax
  int v14; // r15d
  int v15; // r15d
  __int64 v16; // r15
  __int64 v17; // r13
  UnBCL::String *v18; // rax
  UnBCL::String *v19; // rbx
  __int64 v20; // rcx
  DWORD LastError; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  _QWORD *v39; // rdx
  _QWORD v40[5]; // [rsp+0h] [rbp-238h] BYREF
  int v41; // [rsp+60h] [rbp-1D8h]
  unsigned int v42; // [rsp+64h] [rbp-1D4h]
  _QWORD *pExceptionObject; // [rsp+68h] [rbp-1D0h] BYREF
  _QWORD *v44; // [rsp+70h] [rbp-1C8h] BYREF
  _QWORD *v45; // [rsp+78h] [rbp-1C0h] BYREF
  _QWORD *v46; // [rsp+80h] [rbp-1B8h] BYREF
  _QWORD *v47; // [rsp+88h] [rbp-1B0h] BYREF
  _QWORD *v48; // [rsp+90h] [rbp-1A8h] BYREF
  _QWORD *v49; // [rsp+98h] [rbp-1A0h] BYREF
  GUID v50; // [rsp+A0h] [rbp-198h] BYREF
  void **v51; // [rsp+B0h] [rbp-188h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-180h]
  _QWORD v53[2]; // [rsp+C0h] [rbp-178h] BYREF
  int v54; // [rsp+D0h] [rbp-168h] BYREF
  _QWORD v55[7]; // [rsp+D8h] [rbp-160h] BYREF
  _BYTE v56[8]; // [rsp+110h] [rbp-128h] BYREF
  struct _VSS_SNAPSHOT_PROP rguid; // [rsp+118h] [rbp-120h] BYREF
  OLECHAR sz[40]; // [rsp+1A0h] [rbp-98h] BYREF

  v42 = 0;
  v52 = 0;
  v51 = &RAII::CAutoRelease<IVssBackupComponents *>::`vftable';
  if ( !a1 )
    return 2147942487LL;
  v41 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v55);
  try
  {
    try
    {
      v55[0] = &`VssEnumSnapshots'::`6'::CXXXXXHandledException::`vftable';
      v3 = ((__int64 (__fastcall *)(void ***))v51[1])(&v51);
      VssBackupComponentsInternal = CreateVssBackupComponentsInternal(v3);
      v42 = VssBackupComponentsInternal;
      if ( VssBackupComponentsInternal < 0 )
      {
        LastError = GetLastError();
        v22 = CurrentIP();
        v23 = ConstructPartialMsgW(
                0x2000000,
                "VssEnumSnapshots: Failed to create backup components. Error: 0x%08X",
                VssBackupComponentsInternal);
        WdsSetupLogMessageW(
          v23,
          0,
          L"D",
          0,
          452,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssEnumSnapshots",
          v22,
          LastError,
          0,
          0);
        v41 = 1;
        pExceptionObject = v55;
        throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&pExceptionObject;
      }
      v5 = ((__int64 (__fastcall *)(void ***))v51[3])(&v51);
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 40LL))(v5, 0);
      v42 = v6;
      if ( v6 < 0 )
      {
        v24 = GetLastError();
        v25 = CurrentIP();
        v26 = ConstructPartialMsgW(
                0x2000000,
                "VssEnumSnapshots: Failed to initialize VSS for backup. Error: 0x%08X",
                v6);
        WdsSetupLogMessageW(
          v26,
          0,
          L"D",
          0,
          459,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssEnumSnapshots",
          v25,
          v24,
          0,
          0);
        v41 = 1;
        v44 = v55;
        throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v44;
      }
      v7 = ((__int64 (__fastcall *)(void ***))v51[3])(&v51);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 280LL))(v7, 0xFFFFFFFFLL);
      v42 = v8;
      if ( v8 < 0 )
      {
        v27 = GetLastError();
        v28 = CurrentIP();
        v29 = ConstructPartialMsgW(0x2000000, "VssEnumSnapshots: Failed to set backup context. Error: 0x%08X", v8);
        WdsSetupLogMessageW(
          v29,
          0,
          L"D",
          0,
          466,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssEnumSnapshots",
          v28,
          v27,
          0,
          0);
        v41 = 1;
        v45 = v55;
        throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v45;
      }
      v53[1] = 0;
      v53[0] = &RAII::CAutoRelease<IVssEnumObject *>::`vftable';
      v9 = ((__int64 (__fastcall *)(void ***))v51[3])(&v51);
      v10 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v9 + 344LL);
      v11 = (*(__int64 (__fastcall **)(_QWORD *))(v53[0] + 8LL))(v53);
      v50 = GUID_NULL;
      v40[4] = v11;
      v12 = v10(v9, &v50, 1);
      v42 = v12;
      if ( v12 < 0 )
      {
        v30 = GetLastError();
        v31 = CurrentIP();
        v32 = ConstructPartialMsgW(0x2000000, "VssEnumSnapshots: Failed to enumerate snapshots. Error: 0x%08X", v12);
        WdsSetupLogMessageW(
          v32,
          0,
          L"D",
          0,
          474,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssEnumSnapshots",
          v31,
          v30,
          0,
          0);
        v41 = 1;
        v46 = v55;
        throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v46;
      }
      while ( 1 )
      {
        memset_0(v56, 0, 0x88u);
        v54 = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD *))(v53[0] + 24LL))(v53);
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, int *))(*(_QWORD *)v13 + 24LL))(v13, 1, v56, &v54);
        v42 = v14;
        if ( v14 < 0 )
        {
          v33 = GetLastError();
          v34 = CurrentIP();
          v35 = ConstructPartialMsgW(
                  0x2000000,
                  "VssEnumSnapshots: Failed to iterate over snapshots. Error: 0x%08X",
                  v14);
          WdsSetupLogMessageW(
            v35,
            0,
            L"D",
            0,
            486,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssEnumSnapshots",
            v34,
            v33,
            0,
            0);
          v41 = 1;
          v47 = v55;
          throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v47;
        }
        if ( !v54 )
          break;
        memset_0(sz, 0, 0x4Eu);
        v15 = StringFromGUID2(&rguid.m_SnapshotId, sz, 39);
        v42 = v15;
        if ( v15 < 0 )
        {
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
            VssFreeSnapshotProperties(&rguid);
          v36 = GetLastError();
          v37 = CurrentIP();
          v38 = ConstructPartialMsgW(
                  0x2000000,
                  "VssEnumSnapshots: Failed to convert snapshot ID to GUID string. Error: 0x%08X",
                  v15);
          WdsSetupLogMessageW(
            v38,
            0,
            L"D",
            0,
            505,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssEnumSnapshots",
            v37,
            v36,
            0,
            0);
          v41 = 1;
          v49 = v55;
          throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v49;
        }
        v16 = *(int *)(*(_QWORD *)(a1 + 8) + 16LL);
        v17 = *(_QWORD *)(v16 + a1 + 8);
        v18 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v19 = v18;
        *(_QWORD *)&v50.Data1 = v18;
        if ( v18 )
        {
          UnBCL::String::String(v18, sz);
          *(_QWORD *)v19 = &UnBCL::String::`local vftable';
        }
        else
        {
          v19 = 0;
        }
        (*(void (__fastcall **)(__int64, UnBCL::String *))(v17 + 40))(v16 + a1 + 8, v19);
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
          VssFreeSnapshotPropertiesInternal(&rguid);
      }
      RAII::CAutoRelease<IVssEnumObject *>::~CAutoRelease<IVssEnumObject *>(v53);
    }
    catch ( ___R0PEAVCXXXXXTemp__6__VssEnumSnapshots__YAJPEAV__ArrayList_PEAVString_UnBCL___UnBCL___Z__8 )
    {
      JUMPOUT(0x18005242CLL);
    }
    v41 = 1;
    v48 = v55;
    throw (`VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException **)&v48;
  }
  catch ( UnBCL::Exception * )
  {
    v39 = v40;
    if ( !*((_DWORD *)v39 + 24) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v55);
    v51 = &RAII::CAutoRelease<IVssBackupComponents *>::`vftable';
    v20 = v52;
    if ( v52 )
      (*(void (**)(void))(*(_QWORD *)v20 + 16LL))();
    return v42;
  }
  return result;
}

```

## disassembly

```asm
0x1800386cc  push    rbx
0x1800386ce  push    rsi
0x1800386cf  push    rdi
0x1800386d0  push    r13
0x1800386d2  push    r14
0x1800386d4  push    r15
0x1800386d6  sub     rsp, 208h
0x1800386dd  mov     rax, cs:__security_cookie
0x1800386e4  xor     rax, rsp
0x1800386e7  mov     [rsp+238h+var_48], rax
0x1800386ef  mov     rdi, rcx
0x1800386f2  xor     esi, esi
0x1800386f4  mov     [rsp+238h+var_1D4], esi
0x1800386f8  mov     [rsp+238h+var_180], rsi
0x180038700  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x180038707  mov     [rsp+238h+var_188], rax
0x18003870f  test    rcx, rcx
0x180038712  jnz     short loc_18003871E
0x180038714  mov     eax, 80070057h
0x180038719  jmp     loc_1800389F8
0x18003871e  mov     [rsp+238h+var_1D8], esi
0x180038722  lea     rcx, [rsp+238h+var_160]
0x18003872a  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180038730  lea     rax, ??_7CXXXXXHandledException@?5??VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@6B@; const `VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)'::`6'::CXXXXXHandledException::`vftable'
0x180038737  mov     [rsp+238h+var_160], rax
0x18003873f  mov     rax, [rsp+238h+var_188]
0x180038747  lea     rcx, [rsp+238h+var_188]
0x18003874f  mov     rax, [rax+8]
0x180038753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038758  mov     rcx, rax
0x18003875b  call    cs:__imp_CreateVssBackupComponentsInternal
0x180038761  mov     r14d, eax
0x180038764  mov     [rsp+238h+var_1D4], eax
0x180038768  test    eax, eax
0x18003876a  js      loc_180038A19
0x180038770  mov     rax, [rsp+238h+var_188]
0x180038778  lea     rcx, [rsp+238h+var_188]
0x180038780  mov     rax, [rax+18h]
0x180038784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038789  mov     r8, rax
0x18003878c  mov     rcx, [rax]
0x18003878f  mov     rax, [rcx+28h]
0x180038793  xor     edx, edx
0x180038795  mov     rcx, r8
0x180038798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003879d  mov     r14d, eax
0x1800387a0  mov     [rsp+238h+var_1D4], eax
0x1800387a4  test    eax, eax
0x1800387a6  js      loc_180038AAC
0x1800387ac  mov     rax, [rsp+238h+var_188]
0x1800387b4  lea     rcx, [rsp+238h+var_188]
0x1800387bc  mov     rax, [rax+18h]
0x1800387c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387c5  mov     r8, rax
0x1800387c8  mov     rcx, [rax]
0x1800387cb  mov     rax, [rcx+118h]
0x1800387d2  or      edx, 0FFFFFFFFh
0x1800387d5  mov     rcx, r8
0x1800387d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387dd  mov     r14d, eax
0x1800387e0  mov     [rsp+238h+var_1D4], eax
0x1800387e4  test    eax, eax
0x1800387e6  js      loc_180038B3E
0x1800387ec  mov     [rsp+238h+var_170], rsi
0x1800387f4  lea     rax, ??_7?$CAutoRelease@PEAUIVssEnumObject@@@RAII@@6B@; const RAII::CAutoRelease<IVssEnumObject *>::`vftable'
0x1800387fb  mov     [rsp+238h+var_178], rax
0x180038803  mov     rax, [rsp+238h+var_188]
0x18003880b  lea     rcx, [rsp+238h+var_188]
0x180038813  mov     rax, [rax+18h]
0x180038817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003881c  mov     rbx, rax
0x18003881f  mov     rcx, [rax]
0x180038822  mov     r15, [rcx+158h]
0x180038829  mov     rcx, [rsp+238h+var_178]
0x180038831  mov     rax, [rcx+8]
0x180038835  lea     rcx, [rsp+238h+var_178]
0x18003883d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038842  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180038849  movdqu  [rsp+238h+var_198], xmm0
0x180038852  mov     [rsp+238h+var_218], rax
0x180038857  mov     r9d, 3
0x18003885d  lea     r14d, [r9-2]
0x180038861  mov     r8d, r14d
0x180038864  lea     rdx, [rsp+238h+var_198]
0x18003886c  mov     rcx, rbx
0x18003886f  mov     rax, r15
0x180038872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038877  mov     r15d, eax
0x18003887a  mov     [rsp+238h+var_1D4], eax
0x18003887e  test    eax, eax
0x180038880  js      loc_180038BD1
0x180038886  xor     edx, edx; Val
0x180038888  mov     r8d, 88h; Size
0x18003888e  lea     rcx, [rsp+238h+var_128]; void *
0x180038896  call    memset_0
0x18003889b  mov     [rsp+238h+var_168], esi
0x1800388a2  mov     rax, [rsp+238h+var_178]
0x1800388aa  lea     rcx, [rsp+238h+var_178]
0x1800388b2  mov     rax, [rax+18h]
0x1800388b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388bb  mov     r10, rax
0x1800388be  mov     rcx, [rax]
0x1800388c1  mov     rax, [rcx+18h]
0x1800388c5  lea     r9, [rsp+238h+var_168]
0x1800388cd  lea     r8, [rsp+238h+var_128]
0x1800388d5  mov     edx, r14d
0x1800388d8  mov     rcx, r10
0x1800388db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388e0  mov     r15d, eax
0x1800388e3  mov     [rsp+238h+var_1D4], eax
0x1800388e7  test    eax, eax
0x1800388e9  js      loc_180038C66
0x1800388ef  cmp     [rsp+238h+var_168], esi
0x1800388f6  jz      loc_180038CFC
0x1800388fc  xor     edx, edx; Val
0x1800388fe  lea     r8d, [rdx+4Eh]; Size
0x180038902  lea     rcx, [rsp+238h+sz]; void *
0x18003890a  call    memset_0
0x18003890f  mov     r8d, 27h ; '''; cchMax
0x180038915  lea     rdx, [rsp+238h+sz]; lpsz
0x18003891d  lea     rcx, [rsp+238h+rguid]; rguid
0x180038925  call    cs:__imp_StringFromGUID2
0x18003892b  mov     r15d, eax
0x18003892e  mov     [rsp+238h+var_1D4], eax
0x180038932  test    eax, eax
0x180038934  js      loc_180038D34
0x18003893a  mov     rax, [rdi+8]
0x18003893e  movsxd  r15, dword ptr [rax+10h]
0x180038942  mov     r13, [r15+rdi+8]
0x180038947  mov     ecx, 18h
0x18003894c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180038952  mov     rbx, rax
0x180038955  mov     qword ptr [rsp+238h+var_198], rax
0x18003895d  test    rax, rax
0x180038960  jz      short loc_18003897F
0x180038962  lea     rdx, [rsp+238h+sz]
0x18003896a  mov     rcx, rax
0x18003896d  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180038973  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18003897a  mov     [rbx], rax
0x18003897d  jmp     short loc_180038982
0x18003897f  mov     rbx, rsi
0x180038982  mov     rdx, rbx
0x180038985  lea     rcx, [rdi+8]
0x180038989  add     rcx, r15
0x18003898c  mov     rax, [r13+28h]
0x180038990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038995  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl(void)'::`2'::impl
0x18003899c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled(void)
0x1800389a1  test    al, al
0x1800389a3  jz      loc_180038886
0x1800389a9  lea     rcx, [rsp+238h+rguid]
0x1800389b1  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x1800389b7  jmp     loc_180038886
0x1800389bc  lea     rcx, [rsp+238h+var_160]
0x1800389c4  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x1800389ca  nop
0x1800389cb  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x1800389d2  mov     [rsp+238h+var_188], rax
0x1800389da  mov     rcx, [rsp+238h+var_180]
0x1800389e2  test    rcx, rcx
0x1800389e5  jz      short loc_1800389F4
0x1800389e7  mov     rax, [rcx]
0x1800389ea  mov     rax, [rax+10h]
0x1800389ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389f3  nop
0x1800389f4  mov     eax, [rsp+238h+var_1D4]
0x1800389f8  mov     rcx, [rsp+238h+var_48]
0x180038a00  xor     rcx, rsp; StackCookie
0x180038a03  call    __security_check_cookie
0x180038a08  add     rsp, 208h
0x180038a0f  pop     r15
0x180038a11  pop     r14
0x180038a13  pop     r13
0x180038a15  pop     rdi
0x180038a16  pop     rsi
0x180038a17  pop     rbx
0x180038a18  retn
0x180038a19  call    cs:__imp_GetLastError
0x180038a1f  nop
0x180038a20  mov     edi, eax
0x180038a22  call    cs:__imp_CurrentIP
0x180038a28  mov     rbx, rax
0x180038a2b  mov     r8d, r14d
0x180038a2e  lea     rdx, aVssenumsnapsho_5; "VssEnumSnapshots: Failed to create back"...
0x180038a35  mov     ecx, 2000000h; unsigned int
0x180038a3a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038a3f  mov     [rsp+238h+var_1E8], esi
0x180038a43  mov     [rsp+238h+var_1F0], rsi
0x180038a48  mov     [rsp+238h+var_1F8], edi
0x180038a4c  mov     [rsp+238h+var_200], rbx
0x180038a51  lea     rcx, aVssenumsnapsho_0; "VssEnumSnapshots"
0x180038a58  mov     [rsp+238h+var_208], rcx
0x180038a5d  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180038a64  mov     [rsp+238h+var_210], rcx
0x180038a69  mov     dword ptr [rsp+238h+var_218], 1C4h
0x180038a71  xor     r9d, r9d
0x180038a74  lea     r8, aD; "D"
0x180038a7b  xor     edx, edx
0x180038a7d  mov     rcx, rax
0x180038a80  call    cs:__imp_WdsSetupLogMessageW
0x180038a86  mov     [rsp+238h+var_1D8], 1
0x180038a8e  lea     rax, [rsp+238h+var_160]
0x180038a96  mov     [rsp+238h+pExceptionObject], rax
0x180038a9b  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@; pThrowInfo
0x180038aa2  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x180038aa7  call    _CxxThrowException_0
0x180038aac  call    cs:__imp_GetLastError
0x180038ab2  mov     edi, eax
0x180038ab4  call    cs:__imp_CurrentIP
0x180038aba  mov     rbx, rax
0x180038abd  mov     r8d, r14d
0x180038ac0  lea     rdx, aVssenumsnapsho_3; "VssEnumSnapshots: Failed to initialize "...
0x180038ac7  mov     ecx, 2000000h; unsigned int
0x180038acc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038ad1  mov     [rsp+238h+var_1E8], esi
0x180038ad5  mov     [rsp+238h+var_1F0], rsi
0x180038ada  mov     [rsp+238h+var_1F8], edi
0x180038ade  mov     [rsp+238h+var_200], rbx
0x180038ae3  lea     rcx, aVssenumsnapsho_0; "VssEnumSnapshots"
0x180038aea  mov     [rsp+238h+var_208], rcx
0x180038aef  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180038af6  mov     [rsp+238h+var_210], rcx
0x180038afb  mov     dword ptr [rsp+238h+var_218], 1CBh
0x180038b03  xor     r9d, r9d
0x180038b06  lea     r8, aD; "D"
0x180038b0d  xor     edx, edx
0x180038b0f  mov     rcx, rax
0x180038b12  call    cs:__imp_WdsSetupLogMessageW
0x180038b18  mov     [rsp+238h+var_1D8], 1
0x180038b20  lea     rax, [rsp+238h+var_160]
0x180038b28  mov     [rsp+238h+var_1C8], rax
0x180038b2d  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@; pThrowInfo
0x180038b34  lea     rcx, [rsp+238h+var_1C8]; pExceptionObject
0x180038b39  call    _CxxThrowException_0
0x180038b3e  call    cs:__imp_GetLastError
0x180038b44  mov     edi, eax
0x180038b46  call    cs:__imp_CurrentIP
0x180038b4c  mov     rbx, rax
0x180038b4f  mov     r8d, r14d
0x180038b52  lea     rdx, aVssenumsnapsho_4; "VssEnumSnapshots: Failed to set backup "...
0x180038b59  mov     ecx, 2000000h; unsigned int
0x180038b5e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038b63  mov     [rsp+238h+var_1E8], esi
0x180038b67  mov     [rsp+238h+var_1F0], rsi
0x180038b6c  mov     [rsp+238h+var_1F8], edi
0x180038b70  mov     [rsp+238h+var_200], rbx
0x180038b75  lea     rcx, aVssenumsnapsho_0; "VssEnumSnapshots"
0x180038b7c  mov     [rsp+238h+var_208], rcx
0x180038b81  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180038b88  mov     [rsp+238h+var_210], rcx
0x180038b8d  mov     dword ptr [rsp+238h+var_218], 1D2h
0x180038b95  xor     r9d, r9d
0x180038b98  lea     r8, aD; "D"
0x180038b9f  xor     edx, edx
0x180038ba1  mov     rcx, rax
0x180038ba4  call    cs:__imp_WdsSetupLogMessageW
0x180038baa  mov     [rsp+238h+var_1D8], 1
0x180038bb2  lea     rax, [rsp+238h+var_160]
0x180038bba  mov     [rsp+238h+var_1C0], rax
0x180038bbf  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@; pThrowInfo
0x180038bc6  lea     rcx, [rsp+238h+var_1C0]; pExceptionObject
0x180038bcb  call    _CxxThrowException_0
0x180038bd1  call    cs:__imp_GetLastError
0x180038bd7  mov     edi, eax
0x180038bd9  call    cs:__imp_CurrentIP
0x180038bdf  mov     rbx, rax
0x180038be2  mov     r8d, r15d
0x180038be5  lea     rdx, aVssenumsnapsho_1; "VssEnumSnapshots: Failed to enumerate s"...
0x180038bec  mov     ecx, 2000000h; unsigned int
0x180038bf1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038bf6  mov     [rsp+238h+var_1E8], esi
0x180038bfa  mov     [rsp+238h+var_1F0], rsi
0x180038bff  mov     [rsp+238h+var_1F8], edi
0x180038c03  mov     [rsp+238h+var_200], rbx
0x180038c08  lea     rcx, aVssenumsnapsho_0; "VssEnumSnapshots"
0x180038c0f  mov     [rsp+238h+var_208], rcx
0x180038c14  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180038c1b  mov     [rsp+238h+var_210], rcx
0x180038c20  mov     dword ptr [rsp+238h+var_218], 1DAh
0x180038c28  xor     r9d, r9d
0x180038c2b  lea     r8, aD; "D"
0x180038c32  xor     edx, edx
0x180038c34  mov     rcx, rax
0x180038c37  call    cs:__imp_WdsSetupLogMessageW
0x180038c3d  mov     [rsp+238h+var_1D8], r14d
0x180038c42  lea     rax, [rsp+238h+var_160]
0x180038c4a  mov     [rsp+238h+var_1B8], rax
0x180038c52  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@; pThrowInfo
0x180038c59  lea     rcx, [rsp+238h+var_1B8]; pExceptionObject
0x180038c61  call    _CxxThrowException_0
0x180038c66  call    cs:__imp_GetLastError
0x180038c6c  mov     edi, eax
0x180038c6e  call    cs:__imp_CurrentIP
0x180038c74  mov     rbx, rax
0x180038c77  mov     r8d, r15d
0x180038c7a  lea     rdx, aVssenumsnapsho; "VssEnumSnapshots: Failed to iterate ove"...
0x180038c81  mov     ecx, 2000000h; unsigned int
0x180038c86  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038c8b  mov     [rsp+238h+var_1E8], esi
  ... truncated ...
```
