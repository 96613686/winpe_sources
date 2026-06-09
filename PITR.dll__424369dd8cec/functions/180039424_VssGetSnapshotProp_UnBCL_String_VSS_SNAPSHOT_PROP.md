# VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)

- ea: `0x180039424`
- end: `0x1800399c1`
- name: `?VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z`
- size: `1437`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct _VSS_SNAPSHOT_PROP *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a5f0`
- `0x18000fab0`
- `0x1800131c4`
- `0x1800170f0`
- `0x18002a6fc`
- `0x1800399c8`

## callees

- `0x18000253c`
- `0x180009e04`
- `0x18001def0`
- `0x180039424`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003975a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003975a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398fa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800394ae`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800394ae`
- `WDSCORE!CurrentIP` at `0x18003963e`
- `WDSCORE!CurrentIP` at `0x1800396d0`
- `WDSCORE!CurrentIP` at `0x180039762`
- `WDSCORE!CurrentIP` at `0x1800397f4`
- `WDSCORE!CurrentIP` at `0x1800398a9`
- `WDSCORE!CurrentIP` at `0x180039902`
- `WDSCORE!CurrentIP` at `0x18003963e`
- `WDSCORE!CurrentIP` at `0x1800396d0`
- `WDSCORE!CurrentIP` at `0x180039762`
- `WDSCORE!CurrentIP` at `0x1800397f4`
- `WDSCORE!CurrentIP` at `0x1800398a9`
- `WDSCORE!CurrentIP` at `0x180039902`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003969c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003972e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800397c0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039852`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039960`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003969c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003972e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800397c0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039852`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039960`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800395d6`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800395d6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003949d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003949d`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180039485`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180039485`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800394df`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800394df`

## string_xrefs

- `0x180039679`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x18003970b`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x18003979d`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x18003982f`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x1800398e4`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x18003993d`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x1800396dc`: `VssGetSnapshotProp: Failed to create backup components. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall VssGetSnapshotProp(struct UnBCL::String *a1, struct _VSS_SNAPSHOT_PROP *a2)
{
  const OLECHAR *CString; // rax
  HRESULT v5; // r14d
  __int64 v6; // rax
  int VssBackupComponentsInternal; // r14d
  __int64 v8; // rax
  int v9; // r14d
  __int64 v10; // rax
  int v11; // r14d
  __int64 v12; // rax
  int v13; // eax
  int v14; // r14d
  DWORD LastError; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  _QWORD *pExceptionObject; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD *v35; // [rsp+70h] [rbp-B8h] BYREF
  _QWORD *v36; // [rsp+78h] [rbp-B0h] BYREF
  _QWORD *v37; // [rsp+80h] [rbp-A8h] BYREF
  _QWORD *v38; // [rsp+88h] [rbp-A0h] BYREF
  _QWORD *v39; // [rsp+90h] [rbp-98h] BYREF
  GUID v40; // [rsp+A0h] [rbp-88h] BYREF
  _QWORD v41[2]; // [rsp+B0h] [rbp-78h] BYREF
  GUID pclsid; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD v43[7]; // [rsp+D0h] [rbp-58h] BYREF

  v41[1] = 0;
  v41[0] = &RAII::CAutoRelease<IVssBackupComponents *>::`vftable';
  pclsid = 0;
  if ( a1 && a2 )
  {
    UnBCL::Exception::Exception((UnBCL::Exception *)v43);
    try
    {
      try
      {
        v43[0] = &`VssGetSnapshotProp'::`6'::CXXXXXHandledException::`vftable';
        CString = UnBCL::String::get_CString(a1);
        v5 = CLSIDFromString(CString, &pclsid);
        if ( v5 < 0 )
        {
          LastError = GetLastError();
          v17 = CurrentIP();
          v18 = ConstructPartialMsgW(0x2000000, "VssGetSnapshotProp: Failed to convert ID to VSS_ID. Error: 0x%08X", v5);
          WdsSetupLogMessageW(
            v18,
            0,
            L"D",
            0,
            276,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssGetSnapshotProp",
            v17,
            LastError,
            0,
            0);
          pExceptionObject = v43;
          throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&pExceptionObject;
        }
        v6 = (*(__int64 (__fastcall **)(_QWORD *))(v41[0] + 8LL))(v41);
        VssBackupComponentsInternal = CreateVssBackupComponentsInternal(v6);
        if ( VssBackupComponentsInternal < 0 )
        {
          v19 = GetLastError();
          v20 = CurrentIP();
          v21 = ConstructPartialMsgW(
                  0x2000000,
                  "VssGetSnapshotProp: Failed to create backup components. Error: 0x%08X",
                  VssBackupComponentsInternal);
          WdsSetupLogMessageW(
            v21,
            0,
            L"D",
            0,
            284,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssGetSnapshotProp",
            v20,
            v19,
            0,
            0);
          v35 = v43;
          throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&v35;
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD *))(v41[0] + 24LL))(v41);
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, 0);
        if ( v9 < 0 )
        {
          v22 = GetLastError();
          v23 = CurrentIP();
          v24 = ConstructPartialMsgW(
                  0x2000000,
                  "VssGetSnapshotProp: Failed to initialize VSS for backup. Error: 0x%08X",
                  v9);
          WdsSetupLogMessageW(
            v24,
            0,
            L"D",
            0,
            291,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssGetSnapshotProp",
            v23,
            v22,
            0,
            0);
          v36 = v43;
          throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&v36;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD *))(v41[0] + 24LL))(v41);
        v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 280LL))(v10, 0xFFFFFFFFLL);
        if ( v11 < 0 )
        {
          v25 = GetLastError();
          v26 = CurrentIP();
          v27 = ConstructPartialMsgW(0x2000000, "VssGetSnapshotProp: Failed to set backup context. Error: 0x%08X", v11);
          WdsSetupLogMessageW(
            v27,
            0,
            L"D",
            0,
            298,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssGetSnapshotProp",
            v26,
            v25,
            0,
            0);
          v37 = v43;
          throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&v37;
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD *))(v41[0] + 24LL))(v41);
        v40 = pclsid;
        v13 = (*(__int64 (__fastcall **)(__int64, GUID *, struct _VSS_SNAPSHOT_PROP *))(*(_QWORD *)v12 + 336LL))(
                v12,
                &v40,
                a2);
      }
      catch ( UnBCL::YAJPEAVString:: )
      {
        JUMPOUT(0x18005242CLL);
      }
      v14 = v13;
      if ( v13 >= 0 )
      {
        v39 = v43;
        throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&v39;
      }
    }
    catch ( UnBCL::Exception * )
    {
      throw;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      if ( v14 != -2147212536 )
      {
        v28 = GetLastError();
        v29 = CurrentIP();
        v30 = ConstructPartialMsgW(0x2000000, "VssGetSnapshotProp: GetSnapshotProperties failed. Error: 0x%08X", v14);
        WdsSetupLogMessageW(
          v30,
          0,
          L"D",
          0,
          309,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssGetSnapshotProp",
          v29,
          v28,
          0,
          0);
      }
    }
    else
    {
      v31 = GetLastError();
      v32 = CurrentIP();
      v33 = ConstructPartialMsgW(0x2000000, "VssGetSnapshotProp: GetSnapshotProperties failed. Error: 0x%08X", v14);
      WdsSetupLogMessageW(
        v33,
        0,
        L"D",
        0,
        314,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
        L"VssGetSnapshotProp",
        v32,
        v31,
        0,
        0);
    }
    v38 = v43;
    throw (`VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException **)&v38;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180039424  mov     r11, rsp
0x180039427  mov     [r11+18h], rbx
0x18003942b  push    rsi
0x18003942c  push    rdi
0x18003942d  push    r14
0x18003942f  sub     rsp, 110h
0x180039436  mov     rax, cs:__security_cookie
0x18003943d  xor     rax, rsp
0x180039440  mov     [rsp+128h+var_20], rax
0x180039448  mov     rdi, rdx
0x18003944b  mov     rbx, rcx
0x18003944e  xor     esi, esi
0x180039450  mov     [r11-70h], rsi
0x180039454  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x18003945b  mov     [r11-78h], rax
0x18003945f  xorps   xmm0, xmm0
0x180039462  movups  xmmword ptr [r11-68h], xmm0
0x180039467  test    rcx, rcx
0x18003946a  jz      loc_18003960C
0x180039470  mov     [rsp+128h+var_C4], esi
0x180039474  test    rdx, rdx
0x180039477  jz      loc_18003960C
0x18003947d  mov     [rsp+128h+var_C8], esi
0x180039481  lea     rcx, [r11-58h]
0x180039485  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x18003948b  lea     rax, ??_7CXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@6B@; const `VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)'::`6'::CXXXXXHandledException::`vftable'
0x180039492  mov     [rsp+128h+var_58], rax
0x18003949a  mov     rcx, rbx
0x18003949d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800394a3  lea     rdx, [rsp+128h+pclsid]; pclsid
0x1800394ab  mov     rcx, rax; lpsz
0x1800394ae  call    cs:__imp_CLSIDFromString
0x1800394b4  mov     r14d, eax
0x1800394b7  mov     [rsp+128h+var_C4], eax
0x1800394bb  test    eax, eax
0x1800394bd  js      loc_180039635
0x1800394c3  mov     rax, [rsp+128h+var_78]
0x1800394cb  lea     rcx, [rsp+128h+var_78]
0x1800394d3  mov     rax, [rax+8]
0x1800394d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394dc  mov     rcx, rax
0x1800394df  call    cs:__imp_CreateVssBackupComponentsInternal
0x1800394e5  mov     r14d, eax
0x1800394e8  mov     [rsp+128h+var_C4], eax
0x1800394ec  test    eax, eax
0x1800394ee  js      loc_1800396C8
0x1800394f4  mov     rax, [rsp+128h+var_78]
0x1800394fc  lea     rcx, [rsp+128h+var_78]
0x180039504  mov     rax, [rax+18h]
0x180039508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003950d  mov     r8, rax
0x180039510  mov     rcx, [rax]
0x180039513  mov     rax, [rcx+28h]
0x180039517  xor     edx, edx
0x180039519  mov     rcx, r8
0x18003951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039521  mov     r14d, eax
0x180039524  mov     [rsp+128h+var_C4], eax
0x180039528  test    eax, eax
0x18003952a  js      loc_18003975A
0x180039530  mov     rax, [rsp+128h+var_78]
0x180039538  lea     rcx, [rsp+128h+var_78]
0x180039540  mov     rax, [rax+18h]
0x180039544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039549  mov     r8, rax
0x18003954c  mov     rcx, [rax]
0x18003954f  mov     rax, [rcx+118h]
0x180039556  or      edx, 0FFFFFFFFh
0x180039559  mov     rcx, r8
0x18003955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039561  mov     r14d, eax
0x180039564  mov     [rsp+128h+var_C4], eax
0x180039568  test    eax, eax
0x18003956a  js      loc_1800397EC
0x180039570  mov     rax, [rsp+128h+var_78]
0x180039578  lea     rcx, [rsp+128h+var_78]
0x180039580  mov     rax, [rax+18h]
0x180039584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039589  mov     r9, rax
0x18003958c  movaps  xmm0, xmmword ptr [rsp+128h+pclsid.Data1]
0x180039594  movdqa  [rsp+128h+var_88], xmm0
0x18003959d  mov     rcx, [rax]
0x1800395a0  mov     rax, [rcx+150h]
0x1800395a7  mov     r8, rdi
0x1800395aa  lea     rdx, [rsp+128h+var_88]
0x1800395b2  mov     rcx, r9
0x1800395b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395ba  mov     r14d, eax
0x1800395bd  mov     [rsp+128h+var_C4], eax
0x1800395c1  test    eax, eax
0x1800395c3  jns     loc_180039993
0x1800395c9  jmp     loc_180039884
0x1800395ce  lea     rcx, [rsp+128h+var_58]
0x1800395d6  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x1800395dc  nop
0x1800395dd  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x1800395e4  mov     [rsp+128h+var_78], rax
0x1800395ec  mov     rcx, [rsp+128h+var_70]
0x1800395f4  test    rcx, rcx
0x1800395f7  jz      short loc_180039606
0x1800395f9  mov     rax, [rcx]
0x1800395fc  mov     rax, [rax+10h]
0x180039600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039605  nop
0x180039606  mov     eax, [rsp+128h+var_C4]
0x18003960a  jmp     short loc_180039611
0x18003960c  mov     eax, 80070057h
0x180039611  mov     rcx, [rsp+128h+var_20]
0x180039619  xor     rcx, rsp; StackCookie
0x18003961c  call    __security_check_cookie
0x180039621  mov     rbx, [rsp+128h+arg_10]
0x180039629  add     rsp, 110h
0x180039630  pop     r14
0x180039632  pop     rdi
0x180039633  pop     rsi
0x180039634  retn
0x180039635  call    cs:__imp_GetLastError
0x18003963b  nop
0x18003963c  mov     edi, eax
0x18003963e  call    cs:__imp_CurrentIP
0x180039644  mov     rbx, rax
0x180039647  mov     r8d, r14d
0x18003964a  lea     rdx, aVssgetsnapshot_4; "VssGetSnapshotProp: Failed to convert I"...
0x180039651  mov     ecx, 2000000h; unsigned int
0x180039656  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003965b  mov     [rsp+128h+var_D8], esi
0x18003965f  mov     [rsp+128h+var_E0], rsi
0x180039664  mov     [rsp+128h+var_E8], edi
0x180039668  mov     [rsp+128h+var_F0], rbx
0x18003966d  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x180039674  mov     [rsp+128h+var_F8], rcx
0x180039679  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039680  mov     [rsp+128h+var_100], rcx
0x180039685  mov     [rsp+128h+var_108], 114h
0x18003968d  xor     r9d, r9d
0x180039690  lea     r8, aD; "D"
0x180039697  xor     edx, edx
0x180039699  mov     rcx, rax
0x18003969c  call    cs:__imp_WdsSetupLogMessageW
0x1800396a2  mov     [rsp+128h+var_C8], 1
0x1800396aa  lea     rax, [rsp+128h+var_58]
0x1800396b2  mov     [rsp+128h+pExceptionObject], rax
0x1800396b7  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x1800396be  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1800396c3  call    _CxxThrowException_0
0x1800396c8  call    cs:__imp_GetLastError
0x1800396ce  mov     edi, eax
0x1800396d0  call    cs:__imp_CurrentIP
0x1800396d6  mov     rbx, rax
0x1800396d9  mov     r8d, r14d
0x1800396dc  lea     rdx, aVssgetsnapshot_0; "VssGetSnapshotProp: Failed to create ba"...
0x1800396e3  mov     ecx, 2000000h; unsigned int
0x1800396e8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800396ed  mov     [rsp+128h+var_D8], esi
0x1800396f1  mov     [rsp+128h+var_E0], rsi
0x1800396f6  mov     [rsp+128h+var_E8], edi
0x1800396fa  mov     [rsp+128h+var_F0], rbx
0x1800396ff  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x180039706  mov     [rsp+128h+var_F8], rcx
0x18003970b  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039712  mov     [rsp+128h+var_100], rcx
0x180039717  mov     [rsp+128h+var_108], 11Ch
0x18003971f  xor     r9d, r9d
0x180039722  lea     r8, aD; "D"
0x180039729  xor     edx, edx
0x18003972b  mov     rcx, rax
0x18003972e  call    cs:__imp_WdsSetupLogMessageW
0x180039734  mov     [rsp+128h+var_C8], 1
0x18003973c  lea     rax, [rsp+128h+var_58]
0x180039744  mov     [rsp+128h+var_B8], rax
0x180039749  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x180039750  lea     rcx, [rsp+128h+var_B8]; pExceptionObject
0x180039755  call    _CxxThrowException_0
0x18003975a  call    cs:__imp_GetLastError
0x180039760  mov     edi, eax
0x180039762  call    cs:__imp_CurrentIP
0x180039768  mov     rbx, rax
0x18003976b  mov     r8d, r14d
0x18003976e  lea     rdx, aVssgetsnapshot_3; "VssGetSnapshotProp: Failed to initializ"...
0x180039775  mov     ecx, 2000000h; unsigned int
0x18003977a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003977f  mov     [rsp+128h+var_D8], esi
0x180039783  mov     [rsp+128h+var_E0], rsi
0x180039788  mov     [rsp+128h+var_E8], edi
0x18003978c  mov     [rsp+128h+var_F0], rbx
0x180039791  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x180039798  mov     [rsp+128h+var_F8], rcx
0x18003979d  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x1800397a4  mov     [rsp+128h+var_100], rcx
0x1800397a9  mov     [rsp+128h+var_108], 123h
0x1800397b1  xor     r9d, r9d
0x1800397b4  lea     r8, aD; "D"
0x1800397bb  xor     edx, edx
0x1800397bd  mov     rcx, rax
0x1800397c0  call    cs:__imp_WdsSetupLogMessageW
0x1800397c6  mov     [rsp+128h+var_C8], 1
0x1800397ce  lea     rax, [rsp+128h+var_58]
0x1800397d6  mov     [rsp+128h+var_B0], rax
0x1800397db  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x1800397e2  lea     rcx, [rsp+128h+var_B0]; pExceptionObject
0x1800397e7  call    _CxxThrowException_0
0x1800397ec  call    cs:__imp_GetLastError
0x1800397f2  mov     edi, eax
0x1800397f4  call    cs:__imp_CurrentIP
0x1800397fa  mov     rbx, rax
0x1800397fd  mov     r8d, r14d
0x180039800  lea     rdx, aVssgetsnapshot; "VssGetSnapshotProp: Failed to set backu"...
0x180039807  mov     ecx, 2000000h; unsigned int
0x18003980c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180039811  mov     [rsp+128h+var_D8], esi
0x180039815  mov     [rsp+128h+var_E0], rsi
0x18003981a  mov     [rsp+128h+var_E8], edi
0x18003981e  mov     [rsp+128h+var_F0], rbx
0x180039823  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x18003982a  mov     [rsp+128h+var_F8], rcx
0x18003982f  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039836  mov     [rsp+128h+var_100], rcx
0x18003983b  mov     [rsp+128h+var_108], 12Ah
0x180039843  xor     r9d, r9d
0x180039846  lea     r8, aD; "D"
0x18003984d  xor     edx, edx
0x18003984f  mov     rcx, rax
0x180039852  call    cs:__imp_WdsSetupLogMessageW
0x180039858  mov     [rsp+128h+var_C8], 1
0x180039860  lea     rax, [rsp+128h+var_58]
0x180039868  mov     [rsp+128h+var_A8], rax
0x180039870  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x180039877  lea     rcx, [rsp+128h+var_A8]; pExceptionObject
0x18003987f  call    _CxxThrowException_0
0x180039884  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18003988b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180039890  test    al, al
0x180039892  jz      short loc_1800398FA
0x180039894  cmp     r14d, 80042308h
0x18003989b  jz      loc_180039966
0x1800398a1  call    cs:__imp_GetLastError
0x1800398a7  mov     edi, eax
0x1800398a9  call    cs:__imp_CurrentIP
0x1800398af  mov     rbx, rax
0x1800398b2  mov     r8d, r14d
0x1800398b5  lea     rdx, aVssgetsnapshot_2; "VssGetSnapshotProp: GetSnapshotProperti"...
0x1800398bc  mov     ecx, 2000000h; unsigned int
0x1800398c1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800398c6  mov     [rsp+128h+var_D8], esi
0x1800398ca  mov     [rsp+128h+var_E0], rsi
0x1800398cf  mov     [rsp+128h+var_E8], edi
0x1800398d3  mov     [rsp+128h+var_F0], rbx
0x1800398d8  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x1800398df  mov     [rsp+128h+var_F8], rcx
0x1800398e4  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x1800398eb  mov     [rsp+128h+var_100], rcx
0x1800398f0  mov     [rsp+128h+var_108], 135h
0x1800398f8  jmp     short loc_180039951
0x1800398fa  call    cs:__imp_GetLastError
0x180039900  mov     edi, eax
0x180039902  call    cs:__imp_CurrentIP
0x180039908  mov     rbx, rax
0x18003990b  mov     r8d, r14d
0x18003990e  lea     rdx, aVssgetsnapshot_2; "VssGetSnapshotProp: GetSnapshotProperti"...
0x180039915  mov     ecx, 2000000h; unsigned int
0x18003991a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003991f  mov     [rsp+128h+var_D8], esi
0x180039923  mov     [rsp+128h+var_E0], rsi
0x180039928  mov     [rsp+128h+var_E8], edi
0x18003992c  mov     [rsp+128h+var_F0], rbx
0x180039931  lea     rcx, aVssgetsnapshot_6; "VssGetSnapshotProp"
0x180039938  mov     [rsp+128h+var_F8], rcx
0x18003993d  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039944  mov     [rsp+128h+var_100], rcx
0x180039949  mov     [rsp+128h+var_108], 13Ah
0x180039951  xor     r9d, r9d
0x180039954  lea     r8, aD; "D"
0x18003995b  xor     edx, edx
0x18003995d  mov     rcx, rax
0x180039960  call    cs:__imp_WdsSetupLogMessageW
0x180039966  mov     [rsp+128h+var_C8], 1
0x18003996e  lea     rax, [rsp+128h+var_58]
0x180039976  mov     [rsp+128h+var_A0], rax
0x18003997e  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x180039985  lea     rcx, [rsp+128h+var_A0]; pExceptionObject
0x18003998d  call    _CxxThrowException_0
0x180039993  mov     [rsp+128h+var_C8], 1
0x18003999b  lea     rax, [rsp+128h+var_58]
0x1800399a3  mov     [rsp+128h+var_98], rax
0x1800399ab  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z@; pThrowInfo
0x1800399b2  lea     rcx, [rsp+128h+var_98]; pExceptionObject
0x1800399ba  call    _CxxThrowException_0
```
