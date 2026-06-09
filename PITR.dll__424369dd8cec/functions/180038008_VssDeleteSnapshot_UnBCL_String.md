# VssDeleteSnapshot(UnBCL::String *)

- ea: `0x180038008`
- end: `0x1800386c4`
- name: `?VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(struct UnBCL::String *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a5f0`
- `0x18000b280`

## callees

- `0x18000253c`
- `0x180009e04`
- `0x180038008`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003809b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003809b`
- `WDSCORE!CurrentIP` at `0x1800382bb`
- `WDSCORE!CurrentIP` at `0x18003834d`
- `WDSCORE!CurrentIP` at `0x1800383df`
- `WDSCORE!CurrentIP` at `0x180038471`
- `WDSCORE!CurrentIP` at `0x180038509`
- `WDSCORE!CurrentIP` at `0x18003859e`
- `WDSCORE!CurrentIP` at `0x180038635`
- `WDSCORE!CurrentIP` at `0x1800382bb`
- `WDSCORE!CurrentIP` at `0x18003834d`
- `WDSCORE!CurrentIP` at `0x1800383df`
- `WDSCORE!CurrentIP` at `0x180038471`
- `WDSCORE!CurrentIP` at `0x180038509`
- `WDSCORE!CurrentIP` at `0x18003859e`
- `WDSCORE!CurrentIP` at `0x180038635`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038319`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800383ab`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003843d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800384cf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038567`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800385f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038693`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038319`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800383ab`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003843d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800384cf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038567`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800385f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038693`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180038255`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180038255`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003808a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003808a`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180038072`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180038072`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800380cc`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800380cc`

## string_xrefs

- `0x1800382f6`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038388`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x18003841a`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x1800384ac`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038544`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x1800385d6`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180038670`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x1800382ea`: `VssDeleteSnapshot`
- `0x18003837c`: `VssDeleteSnapshot`
- `0x18003840e`: `VssDeleteSnapshot`
- `0x1800384a0`: `VssDeleteSnapshot`
- `0x180038538`: `VssDeleteSnapshot`
- `0x1800385ca`: `VssDeleteSnapshot`
- `0x180038664`: `VssDeleteSnapshot`
- `0x1800382c7`: `VssDeleteSnapshot: Failed to convert ID to VSS_ID. Error: 0x%08X`
- `0x180038359`: `VssDeleteSnapshot: Failed to create backup components. Error: 0x%08X`
- `0x1800383eb`: `VssDeleteSnapshot: Failed to initialize VSS for backup. Error: 0x%08X`
- `0x18003847d`: `VssDeleteSnapshot: Failed to set backup context. Error: 0x%08X`
- `0x180038515`: `VssDeleteSnapshot: Failed to set backup state. Error: 0x%08X`
- `0x1800385a7`: `VssDeleteSnapshot: Target snapshot doesn't exist, assume it's already removed`
- `0x180038641`: `VssDeleteSnapshot: Failed to delete snapshot. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=2
__int64 __fastcall VssDeleteSnapshot(struct UnBCL::String *a1)
{
  const OLECHAR *CString; // rax
  HRESULT v4; // r14d
  __int64 v5; // rax
  int VssBackupComponentsInternal; // r14d
  __int64 v7; // rax
  int v8; // r14d
  __int64 v9; // rax
  int v10; // r14d
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // r15d
  __int64 v15; // rax
  int v16; // r15d
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  DWORD LastError; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  _QWORD *pExceptionObject; // [rsp+68h] [rbp-E0h] BYREF
  _QWORD *v39; // [rsp+70h] [rbp-D8h] BYREF
  _QWORD *v40; // [rsp+78h] [rbp-D0h] BYREF
  _QWORD *v41; // [rsp+80h] [rbp-C8h] BYREF
  _QWORD *v42; // [rsp+88h] [rbp-C0h] BYREF
  _QWORD *v43; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD *v44; // [rsp+98h] [rbp-B0h] BYREF
  GUID v45; // [rsp+A0h] [rbp-A8h] BYREF
  _QWORD v46[2]; // [rsp+B0h] [rbp-98h] BYREF
  _DWORD v47[4]; // [rsp+C0h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+D0h] [rbp-78h] BYREF
  _QWORD v49[7]; // [rsp+E0h] [rbp-68h] BYREF
  GUID v50; // [rsp+118h] [rbp-30h] BYREF

  v46[1] = 0;
  v46[0] = &RAII::CAutoRelease<IVssBackupComponents *>::`vftable';
  pclsid = 0;
  if ( a1 )
  {
    UnBCL::Exception::Exception((UnBCL::Exception *)v49);
    v49[0] = &`VssDeleteSnapshot'::`6'::CXXXXXHandledException::`vftable';
    CString = UnBCL::String::get_CString(a1);
    v4 = CLSIDFromString(CString, &pclsid);
    if ( v4 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 8LL))(v46);
      VssBackupComponentsInternal = CreateVssBackupComponentsInternal(v5);
      if ( VssBackupComponentsInternal >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 24LL))(v46);
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, 0);
        if ( v8 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 24LL))(v46);
          v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 280LL))(v9, 0xFFFFFFFFLL);
          if ( v10 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 24LL))(v46);
            LOBYTE(v12) = 1;
            LOBYTE(v13) = 1;
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _BYTE))(*(_QWORD *)v11 + 48LL))(
                    v11,
                    v13,
                    v12,
                    1,
                    0);
            if ( v14 >= 0 )
            {
              v47[0] = 0;
              v50 = GUID_NULL;
              v15 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 24LL))(v46);
              v45 = pclsid;
              v16 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64, _DWORD *, GUID *))(*(_QWORD *)v15 + 312LL))(
                      v15,
                      &v45,
                      3,
                      1,
                      v47,
                      &v50);
              if ( v16 == -2147212536 )
              {
                LastError = GetLastError();
                v33 = CurrentIP();
                v34 = ConstructPartialMsgW(
                        50331648,
                        "VssDeleteSnapshot: Target snapshot doesn't exist, assume it's already removed");
                WdsSetupLogMessageW(
                  v34,
                  0,
                  L"D",
                  0,
                  589,
                  L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
                  L"VssDeleteSnapshot",
                  v33,
                  LastError,
                  0,
                  0);
              }
              else if ( v16 < 0 )
              {
                v35 = GetLastError();
                v36 = CurrentIP();
                v37 = ConstructPartialMsgW(
                        0x2000000,
                        "VssDeleteSnapshot: Failed to delete snapshot. Error: 0x%08X",
                        v16);
                WdsSetupLogMessageW(
                  v37,
                  0,
                  L"D",
                  0,
                  594,
                  L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
                  L"VssDeleteSnapshot",
                  v36,
                  v35,
                  0,
                  0);
                v43 = v49;
                throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v43;
              }
              v44 = v49;
              throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v44;
            }
            v29 = GetLastError();
            v30 = CurrentIP();
            v31 = ConstructPartialMsgW(0x2000000, "VssDeleteSnapshot: Failed to set backup state. Error: 0x%08X", v14);
            WdsSetupLogMessageW(
              v31,
              0,
              L"D",
              0,
              573,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
              L"VssDeleteSnapshot",
              v30,
              v29,
              0,
              0);
            v42 = v49;
            throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v42;
          }
          v26 = GetLastError();
          v27 = CurrentIP();
          v28 = ConstructPartialMsgW(0x2000000, "VssDeleteSnapshot: Failed to set backup context. Error: 0x%08X", v10);
          WdsSetupLogMessageW(
            v28,
            0,
            L"D",
            0,
            566,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssDeleteSnapshot",
            v27,
            v26,
            0,
            0);
          v41 = v49;
          throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v41;
        }
        v23 = GetLastError();
        v24 = CurrentIP();
        v25 = ConstructPartialMsgW(
                0x2000000,
                "VssDeleteSnapshot: Failed to initialize VSS for backup. Error: 0x%08X",
                v8);
        WdsSetupLogMessageW(
          v25,
          0,
          L"D",
          0,
          559,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssDeleteSnapshot",
          v24,
          v23,
          0,
          0);
        v40 = v49;
        throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v40;
      }
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = ConstructPartialMsgW(
              0x2000000,
              "VssDeleteSnapshot: Failed to create backup components. Error: 0x%08X",
              VssBackupComponentsInternal);
      WdsSetupLogMessageW(
        v22,
        0,
        L"D",
        0,
        552,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
        L"VssDeleteSnapshot",
        v21,
        v20,
        0,
        0);
      v39 = v49;
      throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&v39;
    }
    v17 = GetLastError();
    v18 = CurrentIP();
    v19 = ConstructPartialMsgW(0x2000000, "VssDeleteSnapshot: Failed to convert ID to VSS_ID. Error: 0x%08X", v4);
    WdsSetupLogMessageW(
      v19,
      0,
      L"D",
      0,
      544,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
      L"VssDeleteSnapshot",
      v18,
      v17,
      0,
      0);
    pExceptionObject = v49;
    throw (`VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException **)&pExceptionObject;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180038008  mov     r11, rsp
0x18003800b  mov     [r11+10h], rbx
0x18003800f  mov     [r11+18h], rsi
0x180038013  push    rdi
0x180038014  push    r14
0x180038016  push    r15
0x180038018  sub     rsp, 130h
0x18003801f  mov     rax, cs:__security_cookie
0x180038026  xor     rax, rsp
0x180038029  mov     [rsp+148h+var_20], rax
0x180038031  mov     rbx, rcx
0x180038034  xor     esi, esi
0x180038036  mov     [rsp+148h+var_E4], esi
0x18003803a  mov     [r11-90h], rsi
0x180038041  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x180038048  mov     [r11-98h], rax
0x18003804f  xorps   xmm0, xmm0
0x180038052  movups  xmmword ptr [r11-78h], xmm0
0x180038057  test    rcx, rcx
0x18003805a  jnz     short loc_180038066
0x18003805c  mov     eax, 80070057h
0x180038061  jmp     loc_180038289
0x180038066  mov     [rsp+148h+var_E8], esi
0x18003806a  lea     rcx, [rsp+148h+var_68]
0x180038072  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180038078  lea     rax, ??_7CXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@6B@; const `VssDeleteSnapshot(UnBCL::String *)'::`6'::CXXXXXHandledException::`vftable'
0x18003807f  mov     [rsp+148h+var_68], rax
0x180038087  mov     rcx, rbx
0x18003808a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180038090  lea     rdx, [rsp+148h+pclsid]; pclsid
0x180038098  mov     rcx, rax; lpsz
0x18003809b  call    cs:__imp_CLSIDFromString
0x1800380a1  mov     r14d, eax
0x1800380a4  mov     [rsp+148h+var_E4], eax
0x1800380a8  test    eax, eax
0x1800380aa  js      loc_1800382B2
0x1800380b0  mov     rax, [rsp+148h+var_98]
0x1800380b8  lea     rcx, [rsp+148h+var_98]
0x1800380c0  mov     rax, [rax+8]
0x1800380c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380c9  mov     rcx, rax
0x1800380cc  call    cs:__imp_CreateVssBackupComponentsInternal
0x1800380d2  mov     r14d, eax
0x1800380d5  mov     [rsp+148h+var_E4], eax
0x1800380d9  test    eax, eax
0x1800380db  js      loc_180038345
0x1800380e1  mov     rax, [rsp+148h+var_98]
0x1800380e9  lea     rcx, [rsp+148h+var_98]
0x1800380f1  mov     rax, [rax+18h]
0x1800380f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380fa  mov     r8, rax
0x1800380fd  mov     rcx, [rax]
0x180038100  mov     rax, [rcx+28h]
0x180038104  xor     edx, edx
0x180038106  mov     rcx, r8
0x180038109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003810e  mov     r14d, eax
0x180038111  mov     [rsp+148h+var_E4], eax
0x180038115  test    eax, eax
0x180038117  js      loc_1800383D7
0x18003811d  mov     rax, [rsp+148h+var_98]
0x180038125  lea     rcx, [rsp+148h+var_98]
0x18003812d  mov     rax, [rax+18h]
0x180038131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038136  mov     r8, rax
0x180038139  mov     rcx, [rax]
0x18003813c  mov     rax, [rcx+118h]
0x180038143  or      edx, 0FFFFFFFFh
0x180038146  mov     rcx, r8
0x180038149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003814e  mov     r14d, eax
0x180038151  mov     [rsp+148h+var_E4], eax
0x180038155  test    eax, eax
0x180038157  js      loc_180038469
0x18003815d  mov     rax, [rsp+148h+var_98]
0x180038165  lea     rcx, [rsp+148h+var_98]
0x18003816d  mov     rax, [rax+18h]
0x180038171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038176  mov     r10, rax
0x180038179  mov     rcx, [rax]
0x18003817c  mov     rax, [rcx+30h]
0x180038180  mov     byte ptr [rsp+148h+var_128], sil
0x180038185  mov     r14d, 1
0x18003818b  mov     r9d, r14d
0x18003818e  mov     r8b, r14b
0x180038191  mov     dl, r14b
0x180038194  mov     rcx, r10
0x180038197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003819c  mov     r15d, eax
0x18003819f  mov     [rsp+148h+var_E4], eax
0x1800381a3  test    eax, eax
0x1800381a5  js      loc_180038501
0x1800381ab  mov     [rsp+148h+var_88], esi
0x1800381b2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800381b9  movdqu  [rsp+148h+var_30], xmm0
0x1800381c2  mov     rax, [rsp+148h+var_98]
0x1800381ca  lea     rcx, [rsp+148h+var_98]
0x1800381d2  mov     rax, [rax+18h]
0x1800381d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381db  mov     r10, rax
0x1800381de  movaps  xmm0, xmmword ptr [rsp+148h+pclsid.Data1]
0x1800381e6  movdqa  [rsp+148h+var_A8], xmm0
0x1800381ef  mov     rcx, [rax]
0x1800381f2  mov     rax, [rcx+138h]
0x1800381f9  lea     rcx, [rsp+148h+var_30]
0x180038201  mov     [rsp+148h+var_120], rcx
0x180038206  lea     rcx, [rsp+148h+var_88]
0x18003820e  mov     [rsp+148h+var_128], rcx
0x180038213  mov     r9d, r14d
0x180038216  mov     r8d, 3
0x18003821c  lea     rdx, [rsp+148h+var_A8]
0x180038224  mov     rcx, r10
0x180038227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003822c  mov     r15d, eax
0x18003822f  cmp     eax, 80042308h
0x180038234  jz      loc_180038596
0x18003823a  mov     [rsp+148h+var_E4], r15d
0x18003823f  test    r15d, r15d
0x180038242  js      loc_18003862D
0x180038248  jmp     loc_180038603
0x18003824d  lea     rcx, [rsp+148h+var_68]
0x180038255  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x18003825b  nop
0x18003825c  lea     rax, ??_7?$CAutoRelease@PEAVIVssBackupComponents@@@RAII@@6B@; const RAII::CAutoRelease<IVssBackupComponents *>::`vftable'
0x180038263  mov     [rsp+148h+var_98], rax
0x18003826b  mov     rcx, [rsp+148h+var_90]
0x180038273  test    rcx, rcx
0x180038276  jz      short loc_180038285
0x180038278  mov     rax, [rcx]
0x18003827b  mov     rax, [rax+10h]
0x18003827f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038284  nop
0x180038285  mov     eax, [rsp+148h+var_E4]
0x180038289  mov     rcx, [rsp+148h+var_20]
0x180038291  xor     rcx, rsp; StackCookie
0x180038294  call    __security_check_cookie
0x180038299  lea     r11, [rsp+148h+var_18]
0x1800382a1  mov     rbx, [r11+28h]
0x1800382a5  mov     rsi, [r11+30h]
0x1800382a9  mov     rsp, r11
0x1800382ac  pop     r15
0x1800382ae  pop     r14
0x1800382b0  pop     rdi
0x1800382b1  retn
0x1800382b2  call    cs:__imp_GetLastError
0x1800382b8  nop
0x1800382b9  mov     edi, eax
0x1800382bb  call    cs:__imp_CurrentIP
0x1800382c1  mov     rbx, rax
0x1800382c4  mov     r8d, r14d
0x1800382c7  lea     rdx, aVssdeletesnaps_0; "VssDeleteSnapshot: Failed to convert ID"...
0x1800382ce  mov     ecx, 2000000h; unsigned int
0x1800382d3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800382d8  mov     [rsp+148h+var_F8], esi
0x1800382dc  mov     [rsp+148h+var_100], rsi
0x1800382e1  mov     [rsp+148h+var_108], edi
0x1800382e5  mov     [rsp+148h+var_110], rbx
0x1800382ea  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x1800382f1  mov     [rsp+148h+var_118], rcx
0x1800382f6  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x1800382fd  mov     [rsp+148h+var_120], rcx
0x180038302  mov     dword ptr [rsp+148h+var_128], 220h
0x18003830a  xor     r9d, r9d
0x18003830d  lea     r8, aD; "D"
0x180038314  xor     edx, edx
0x180038316  mov     rcx, rax
0x180038319  call    cs:__imp_WdsSetupLogMessageW
0x18003831f  mov     [rsp+148h+var_E8], 1
0x180038327  lea     rax, [rsp+148h+var_68]
0x18003832f  mov     [rsp+148h+pExceptionObject], rax
0x180038334  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@; pThrowInfo
0x18003833b  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180038340  call    _CxxThrowException_0
0x180038345  call    cs:__imp_GetLastError
0x18003834b  mov     edi, eax
0x18003834d  call    cs:__imp_CurrentIP
0x180038353  mov     rbx, rax
0x180038356  mov     r8d, r14d
0x180038359  lea     rdx, aVssdeletesnaps_6; "VssDeleteSnapshot: Failed to create bac"...
0x180038360  mov     ecx, 2000000h; unsigned int
0x180038365  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003836a  mov     [rsp+148h+var_F8], esi
0x18003836e  mov     [rsp+148h+var_100], rsi
0x180038373  mov     [rsp+148h+var_108], edi
0x180038377  mov     [rsp+148h+var_110], rbx
0x18003837c  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x180038383  mov     [rsp+148h+var_118], rcx
0x180038388  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x18003838f  mov     [rsp+148h+var_120], rcx
0x180038394  mov     dword ptr [rsp+148h+var_128], 228h
0x18003839c  xor     r9d, r9d
0x18003839f  lea     r8, aD; "D"
0x1800383a6  xor     edx, edx
0x1800383a8  mov     rcx, rax
0x1800383ab  call    cs:__imp_WdsSetupLogMessageW
0x1800383b1  mov     [rsp+148h+var_E8], 1
0x1800383b9  lea     rax, [rsp+148h+var_68]
0x1800383c1  mov     [rsp+148h+var_D8], rax
0x1800383c6  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@; pThrowInfo
0x1800383cd  lea     rcx, [rsp+148h+var_D8]; pExceptionObject
0x1800383d2  call    _CxxThrowException_0
0x1800383d7  call    cs:__imp_GetLastError
0x1800383dd  mov     edi, eax
0x1800383df  call    cs:__imp_CurrentIP
0x1800383e5  mov     rbx, rax
0x1800383e8  mov     r8d, r14d
0x1800383eb  lea     rdx, aVssdeletesnaps_4; "VssDeleteSnapshot: Failed to initialize"...
0x1800383f2  mov     ecx, 2000000h; unsigned int
0x1800383f7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800383fc  mov     [rsp+148h+var_F8], esi
0x180038400  mov     [rsp+148h+var_100], rsi
0x180038405  mov     [rsp+148h+var_108], edi
0x180038409  mov     [rsp+148h+var_110], rbx
0x18003840e  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x180038415  mov     [rsp+148h+var_118], rcx
0x18003841a  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180038421  mov     [rsp+148h+var_120], rcx
0x180038426  mov     dword ptr [rsp+148h+var_128], 22Fh
0x18003842e  xor     r9d, r9d
0x180038431  lea     r8, aD; "D"
0x180038438  xor     edx, edx
0x18003843a  mov     rcx, rax
0x18003843d  call    cs:__imp_WdsSetupLogMessageW
0x180038443  mov     [rsp+148h+var_E8], 1
0x18003844b  lea     rax, [rsp+148h+var_68]
0x180038453  mov     [rsp+148h+var_D0], rax
0x180038458  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@; pThrowInfo
0x18003845f  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x180038464  call    _CxxThrowException_0
0x180038469  call    cs:__imp_GetLastError
0x18003846f  mov     edi, eax
0x180038471  call    cs:__imp_CurrentIP
0x180038477  mov     rbx, rax
0x18003847a  mov     r8d, r14d
0x18003847d  lea     rdx, aVssdeletesnaps_3; "VssDeleteSnapshot: Failed to set backup"...
0x180038484  mov     ecx, 2000000h; unsigned int
0x180038489  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003848e  mov     [rsp+148h+var_F8], esi
0x180038492  mov     [rsp+148h+var_100], rsi
0x180038497  mov     [rsp+148h+var_108], edi
0x18003849b  mov     [rsp+148h+var_110], rbx
0x1800384a0  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x1800384a7  mov     [rsp+148h+var_118], rcx
0x1800384ac  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x1800384b3  mov     [rsp+148h+var_120], rcx
0x1800384b8  mov     dword ptr [rsp+148h+var_128], 236h
0x1800384c0  xor     r9d, r9d
0x1800384c3  lea     r8, aD; "D"
0x1800384ca  xor     edx, edx
0x1800384cc  mov     rcx, rax
0x1800384cf  call    cs:__imp_WdsSetupLogMessageW
0x1800384d5  mov     [rsp+148h+var_E8], 1
0x1800384dd  lea     rax, [rsp+148h+var_68]
0x1800384e5  mov     [rsp+148h+var_C8], rax
0x1800384ed  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@; pThrowInfo
0x1800384f4  lea     rcx, [rsp+148h+var_C8]; pExceptionObject
0x1800384fc  call    _CxxThrowException_0
0x180038501  call    cs:__imp_GetLastError
0x180038507  mov     edi, eax
0x180038509  call    cs:__imp_CurrentIP
0x18003850f  mov     rbx, rax
0x180038512  mov     r8d, r15d
0x180038515  lea     rdx, aVssdeletesnaps_5; "VssDeleteSnapshot: Failed to set backup"...
0x18003851c  mov     ecx, 2000000h; unsigned int
0x180038521  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038526  mov     [rsp+148h+var_F8], esi
0x18003852a  mov     [rsp+148h+var_100], rsi
0x18003852f  mov     [rsp+148h+var_108], edi
0x180038533  mov     [rsp+148h+var_110], rbx
0x180038538  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x18003853f  mov     [rsp+148h+var_118], rcx
0x180038544  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x18003854b  mov     [rsp+148h+var_120], rcx
0x180038550  mov     dword ptr [rsp+148h+var_128], 23Dh
0x180038558  xor     r9d, r9d
0x18003855b  lea     r8, aD; "D"
0x180038562  xor     edx, edx
0x180038564  mov     rcx, rax
0x180038567  call    cs:__imp_WdsSetupLogMessageW
0x18003856d  mov     [rsp+148h+var_E8], r14d
0x180038572  lea     rax, [rsp+148h+var_68]
0x18003857a  mov     [rsp+148h+var_C0], rax
0x180038582  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssDeleteSnapshot@@YAJPEAVString@UnBCL@@@Z@; pThrowInfo
0x180038589  lea     rcx, [rsp+148h+var_C0]; pExceptionObject
0x180038591  call    _CxxThrowException_0
0x180038596  call    cs:__imp_GetLastError
0x18003859c  mov     edi, eax
0x18003859e  call    cs:__imp_CurrentIP
0x1800385a4  mov     rbx, rax
0x1800385a7  lea     rdx, aVssdeletesnaps_2; "VssDeleteSnapshot: Target snapshot does"...
0x1800385ae  mov     ecx, 3000000h; unsigned int
0x1800385b3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800385b8  mov     [rsp+148h+var_F8], esi
0x1800385bc  mov     [rsp+148h+var_100], rsi
0x1800385c1  mov     [rsp+148h+var_108], edi
0x1800385c5  mov     [rsp+148h+var_110], rbx
0x1800385ca  lea     rcx, aVssdeletesnaps_1; "VssDeleteSnapshot"
0x1800385d1  mov     [rsp+148h+var_118], rcx
0x1800385d6  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x1800385dd  mov     [rsp+148h+var_120], rcx
  ... truncated ...
```
