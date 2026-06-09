# InstallDtc

- ea: `0x180051df0`
- end: `0x1800526ed`
- name: `InstallDtc`
- size: `2301`
- prototype: `__int64 __fastcall(struct ITmInstance *, wchar_t *Source, _WORD *, unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180049480`

## callees

- `0x180006054`
- `0x18000c6bc`
- `0x18001156c`
- `0x180011ac0`
- `0x18004b6fc`
- `0x180050450`
- `0x180050564`
- `0x1800508b4`
- `0x180050a7c`
- `0x18005122c`
- `0x1800513e8`
- `0x180051b40`
- `0x180051df0`
- `0x180071670`
- `0x18007171c`
- `0x180074200`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521b6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800521a9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800521a9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800520b1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800520b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005218d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005218d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800521e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800521e1`
- `msvcrt!_waccess` at `0x180052098`
- `msvcrt!_waccess` at `0x18005214d`
- `msvcrt!_waccess` at `0x180052098`
- `msvcrt!_waccess` at `0x18005214d`

## string_xrefs

- `0x180051f39`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x1800526bc`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180052636`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x1800523cf`: `Service`
- `0x1800526ae`: `InstallDTC: failed INVALIDARG`
- `0x18005269f`: `InstallDTC: failed INVALIDARG, path for DTC binaries not specified`
- `0x180051e8c`: `InstallDTC: failed INVALIDARG, invalid log file path`
- `0x180051eac`: `InstallDTC: InitializeMutableRegistryKeys failed`
- `0x180051edb`: `InstallDTC: failed InstallDtcOnNT`
- `0x180051f0e`: `InstallDTC: failed GetContactPool`
- `0x180051f70`: `InstallDtc: failed to get the host name for tm contact`
- `0x180051fc5`: `InstallDTC: Create ContactPool`
- `0x180052229`: `InstallDTC: failed QI for ICustomProps 1`
- `0x180052283`: `InstallDTC: Setserviceid of TM`
- `0x18005201d`: `InstallDTC: failed QI for ICustomProps 2`
- `0x1800520ff`: `InstallDTC: Setdescription of TM`
- `0x1800522b0`: `InstallDTC: SetClassId of TM`
- `0x1800522e3`: `InstallDTC: Write of TM`
- `0x18005234e`: `InstallDTC: Write String of TM/log info`
- `0x1800523b7`: `InstallDTC: Write Number of TM/Log size info`
- `0x1800523ec`: `InstallDTC: Write String of TM/Svc info`
- `0x18005245d`: `InstallDtc: failed to get the host name for ui contact`
- `0x1800524e7`: `InstallDTC: CreateContactpool for UIS`
- `0x180052522`: `InstallDTC: Setserviceid for UIS`
- `0x180052574`: `InstallDTC: SetDescription for UIS`
- `0x1800525a4`: `InstallDTC: SetClassId for UIS`
- `0x1800525d5`: `InstallDTC: Write for UIS`
- `0x18005263d`: `InstallDTC: InstallContacts failed`
- `0x18005265e`: `InstallDTC: InstallDtcAsAnOleTxTm failed`
- `0x180052689`: `InstallDTC: SetSddlOnResources failed`

## pseudocode

```c
__int64 __fastcall InstallDtc(
        struct ITmInstance *a1,
        wchar_t *Source,
        _WORD *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        unsigned int a7)
{
  unsigned int v11; // r9d
  char *v12; // rdx
  int v13; // eax
  int v14; // ebx
  int v15; // ecx
  unsigned int v16; // r14d
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // r9d
  char *v22; // rdx
  unsigned __int16 *BSW; // rax
  unsigned int v24; // r9d
  char *v25; // rdx
  int v26; // ecx
  unsigned __int16 *v27; // rax
  char *FileW; // rax
  void *v29; // rbx
  DWORD FileSize; // ecx
  int v31; // eax
  const unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // r15
  int v34; // eax
  unsigned int v35; // r9d
  char *v36; // rdx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  char *v44; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v45; // [rsp+60h] [rbp-A0h]
  wchar_t Sourcea[272]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t FileName[272]; // [rsp+290h] [rbp+190h] BYREF
  _WORD v48[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t v49[272]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v50[264]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v45 = a5;
  v42 = 0;
  v41 = 0;
  v43 = 0;
  memset_0(v50, 0, 0x20Au);
  if ( !Source || !*Source )
  {
    v11 = 947;
    v12 = "InstallDTC: failed INVALIDARG";
    goto LABEL_82;
  }
  if ( !a3 || !*a3 )
  {
    v11 = 954;
    v12 = "InstallDTC: failed INVALIDARG, path for DTC binaries not specified";
    goto LABEL_82;
  }
  if ( !a4 )
  {
    v11 = 961;
    v12 = "InstallDTC: failed INVALIDARG, invalid log file path";
LABEL_82:
    v14 = -2147024809;
    v15 = -2147024809;
    goto LABEL_83;
  }
  v13 = InitializeMutableRegistryKeys(a1);
  v14 = v13;
  if ( v13 < 0 )
  {
    v11 = 971;
    v12 = "InstallDTC: InitializeMutableRegistryKeys failed";
LABEL_9:
    v15 = v13;
LABEL_83:
    TraceFile(v15, v12, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v11);
    return (unsigned int)v14;
  }
  v13 = InstallDtcOnNT(a1, Source, a3, a7);
  v14 = v13;
  if ( v13 )
  {
    v11 = 990;
    v12 = "InstallDTC: failed InstallDtcOnNT";
    goto LABEL_9;
  }
  v13 = (*(__int64 (__fastcall **)(struct ITmInstance *, GUID *, __int64 *))(*(_QWORD *)a1 + 136LL))(
          a1,
          &IID_IContactPool,
          &v42);
  v14 = v13;
  if ( v13 < 0 )
  {
    v11 = 1000;
    v12 = "InstallDTC: failed GetContactPool";
    goto LABEL_9;
  }
  v16 = 4;
  if ( (*(int (__fastcall **)(struct ITmInstance *, wchar_t *, __int64 *))(*(_QWORD *)a1 + 144LL))(a1, Source, &v41) < 0 )
    goto LABEL_17;
  v17 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v41 + 72LL))(v41, v48, 257);
  if ( v17 < 0 )
  {
    TraceFile(
      v17,
      "InstallDtc: failed to get the host name for tm contact",
      "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x3F7u);
LABEL_17:
    (*(void (__fastcall **)(struct ITmInstance *, wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, Source);
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v42 + 56LL))(
            v42,
            0,
            &IID_IProperties,
            &v41);
    v14 = v18;
    if ( v18 < 0 )
    {
      TraceFile(v18, "InstallDTC: Create ContactPool", "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x40Du);
LABEL_19:
      v19 = v42;
LABEL_20:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return (unsigned int)v14;
    }
    StringCchCopyW(Sourcea, 0x110u, a4);
    v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(v41, &IID_ICustomProperties, &v43);
    v14 = v20;
    if ( v20 < 0 )
    {
      v21 = 1049;
      v22 = "InstallDTC: failed QI for ICustomProps 1";
      goto LABEL_41;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v41 + 120LL))(v41, &SVCID_MSDTC_TM, 1);
    v14 = v20;
    if ( v20 < 0 )
    {
      v21 = 1062;
      v22 = "InstallDTC: Setserviceid of TM";
      goto LABEL_41;
    }
    goto LABEL_27;
  }
  if ( v48[0] )
    goto LABEL_17;
  v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(v41, &IID_ICustomProperties, &v43);
  v14 = v20;
  if ( v20 < 0 )
  {
    v21 = 1087;
    v22 = "InstallDTC: failed QI for ICustomProps 2";
LABEL_41:
    TraceFile(v20, v22, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v21);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v19 = v41;
    goto LABEL_20;
  }
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, const wchar_t *, wchar_t *, int))(*(_QWORD *)v43 + 32LL))(
         v43,
         L"LOG",
         L"Path",
         Sourcea,
         272) < 0
    || (v27 = SZStripLastBSW(Sourcea), StringCchPrintfW(v49, 0x110u, L"%s\\msdtc.log", v27), _waccess(v49, 0)) )
  {
    StringCchCopyW(Sourcea, 0x110u, a4);
    BSW = SZStripLastBSW(a4);
    StringCchPrintfW(FileName, 0x110u, L"%s\\msdtc.log", BSW);
    if ( !_waccess(FileName, 0) )
      SetFileAttributesW(FileName, 0x80u);
  }
  else
  {
    FileW = (char *)CreateFileW(v49, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v29 = FileW;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      FileSize = GetFileSize(FileW, 0);
      if ( FileSize == -1 )
        GetLastError();
      else
        v16 = 1000000 * (FileSize / 0xF4240) / 0xF4240;
      CloseHandle(v29);
    }
  }
LABEL_27:
  v44 = 0;
  v14 = WideToMultiByteString(Source, &v44);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v41 + 48LL))(v41, v44);
  FreeMultiByteString(v44);
  if ( v14 < 0 )
  {
    v24 = 1233;
    v25 = "InstallDTC: Setdescription of TM";
LABEL_31:
    v26 = v14;
LABEL_32:
    TraceFile(v26, v25, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    goto LABEL_19;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v41 + 104LL))(v41, &CLSID_DTCTM);
  v14 = v31;
  if ( v31 < 0 )
  {
    v24 = 1244;
    v25 = "InstallDTC: SetClassId of TM";
LABEL_46:
    v26 = v31;
    goto LABEL_32;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v42 + 64LL))(v42, v41, 0);
  v14 = v31;
  if ( v31 < 0 )
  {
    v24 = 1257;
    v25 = "InstallDTC: Write of TM";
    goto LABEL_46;
  }
  v32 = SZStripLastBSW(Sourcea);
  v33 = v45;
  StringCchCopyW(v45, (unsigned int)a6, v32);
  RecCreateDirW(v33);
  CreateTraceDirectory(v50);
  v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, wchar_t *))(*(_QWORD *)v43 + 48LL))(
          v43,
          L"LOG",
          L"Path",
          Sourcea);
  if ( v34 < 0 )
  {
    v35 = 1276;
    v36 = "InstallDTC: Write String of TM/log info";
LABEL_51:
    TraceFile(v34, v36, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    return (unsigned int)-1073737711;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v43 + 80LL))(
          v43,
          L"LOG",
          L"Size",
          v16);
  if ( v34 < 0 )
  {
    v35 = 1288;
    v36 = "InstallDTC: Write Number of TM/Log size info";
    goto LABEL_51;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _WORD *))(*(_QWORD *)v43 + 48LL))(
          v43,
          L"Service",
          L"Path",
          a3);
  if ( v34 < 0 )
  {
    v35 = 1303;
    v36 = "InstallDTC: Write String of TM/Svc info";
    goto LABEL_51;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( (*(int (__fastcall **)(struct ITmInstance *, __int64 *))(*(_QWORD *)a1 + 152LL))(a1, &v41) >= 0 )
  {
    v37 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v41 + 72LL))(v41, v48, 257);
    if ( v37 >= 0 )
    {
      if ( !v48[0] )
        goto LABEL_72;
    }
    else
    {
      TraceFile(
        v37,
        "InstallDtc: failed to get the host name for ui contact",
        "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
        0x52Eu);
    }
  }
  StringCchCopyW(Sourcea, 0x110u, L"MSDTCUIS");
  (*(void (__fastcall **)(struct ITmInstance *, wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, Sourcea);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v42 + 56LL))(
          v42,
          0,
          &IID_IProperties,
          &v41);
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v11 = 1348;
    v12 = "InstallDTC: CreateContactpool for UIS";
    v15 = v14;
    goto LABEL_83;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v41 + 120LL))(v41, &SVCID_MSDTC_UIS, 1);
  v14 = v31;
  if ( v31 < 0 )
  {
    v24 = 1357;
    v25 = "InstallDTC: Setserviceid for UIS";
    goto LABEL_46;
  }
  v44 = 0;
  v14 = WideToMultiByteString(Sourcea, &v44);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v41 + 48LL))(v41, v44);
  FreeMultiByteString(v44);
  if ( v14 < 0 )
  {
    v24 = 1376;
    v25 = "InstallDTC: SetDescription for UIS";
    goto LABEL_31;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v41 + 104LL))(v41, &CLSID_DTCUIS);
  v14 = v31;
  if ( v31 < 0 )
  {
    v24 = 1387;
    v25 = "InstallDTC: SetClassId for UIS";
    goto LABEL_46;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v42 + 64LL))(v42, v41, 0);
  v14 = v31;
  if ( v31 < 0 )
  {
    v24 = 1399;
    v25 = "InstallDTC: Write for UIS";
    goto LABEL_46;
  }
LABEL_72:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  (*(void (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)a1 + 368LL))(
    a1,
    L"MaxLogSize",
    512);
  v38 = InstallContacts(a1);
  v14 = v38;
  if ( v38 >= 0 )
  {
    v39 = InstallDtcAsAnOleTxTm();
    v14 = v39;
    if ( v39 )
    {
      v11 = 1424;
      v12 = "InstallDTC: InstallDtcAsAnOleTxTm failed";
    }
    else
    {
      v39 = SetSddlOnResources(a1, v33, 1);
      v14 = v39;
      if ( v39 >= 0 )
      {
        SyncCIDKeys();
        return (unsigned int)v14;
      }
      v11 = 1430;
      v12 = "InstallDTC: SetSddlOnResources failed";
    }
    v15 = v39;
    goto LABEL_83;
  }
  TraceFileW(v38, L"InstallDTC: InstallContacts failed", L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x58Au);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180051df0  push    rbp
0x180051df2  push    rbx
0x180051df3  push    rsi
0x180051df4  push    rdi
0x180051df5  push    r12
0x180051df7  push    r13
0x180051df9  push    r14
0x180051dfb  push    r15
0x180051dfd  lea     rbp, [rsp-0A08h]
0x180051e05  sub     rsp, 0B08h
0x180051e0c  mov     rax, cs:__security_cookie
0x180051e13  xor     rax, rsp
0x180051e16  mov     [rbp+0A40h+var_50], rax
0x180051e1d  mov     rax, [rbp+0A40h+arg_20]
0x180051e24  xor     edi, edi
0x180051e26  mov     r13, r8
0x180051e29  mov     [rsp+0B40h+var_AE0], rax
0x180051e2e  mov     r15, rdx
0x180051e31  mov     [rsp+0B40h+var_AF8], rdi
0x180051e36  mov     rsi, rcx
0x180051e39  mov     [rsp+0B40h+var_B00], rdi
0x180051e3e  xor     edx, edx; Val
0x180051e40  mov     [rsp+0B40h+var_AF0], rdi
0x180051e45  mov     r8d, 20Ah; Size
0x180051e4b  lea     rcx, [rbp+0A40h+var_260]; void *
0x180051e52  mov     r12, r9
0x180051e55  call    memset_0
0x180051e5a  test    r15, r15
0x180051e5d  jz      loc_1800526A8
0x180051e63  cmp     [r15], di
0x180051e67  jz      loc_1800526A8
0x180051e6d  test    r13, r13
0x180051e70  jz      loc_180052699
0x180051e76  cmp     [r13+0], di
0x180051e7b  jz      loc_180052699
0x180051e81  test    r12, r12
0x180051e84  jnz     short loc_180051E98
0x180051e86  mov     r9d, 3C1h
0x180051e8c  lea     rdx, aInstalldtcFail_3; "InstallDTC: failed INVALIDARG, invalid "...
0x180051e93  jmp     loc_1800526B5
0x180051e98  mov     rcx, rsi; struct ITmInstance *
0x180051e9b  call    ?InitializeMutableRegistryKeys@@YAJPEAUITmInstance@@@Z; InitializeMutableRegistryKeys(ITmInstance *)
0x180051ea0  mov     ebx, eax
0x180051ea2  test    eax, eax
0x180051ea4  jns     short loc_180051EBA
0x180051ea6  mov     r9d, 3CBh
0x180051eac  lea     rdx, aInstalldtcInit; "InstallDTC: InitializeMutableRegistryKe"...
0x180051eb3  mov     ecx, eax
0x180051eb5  jmp     loc_1800526BC
0x180051eba  mov     r9d, [rbp+0A40h+arg_30]
0x180051ec1  mov     r8, r13
0x180051ec4  mov     rdx, r15
0x180051ec7  mov     rcx, rsi
0x180051eca  call    InstallDtcOnNT
0x180051ecf  mov     ebx, eax
0x180051ed1  test    eax, eax
0x180051ed3  jz      short loc_180051EE4
0x180051ed5  mov     r9d, 3DEh
0x180051edb  lea     rdx, aInstalldtcFail_8; "InstallDTC: failed InstallDtcOnNT"
0x180051ee2  jmp     short loc_180051EB3
0x180051ee4  mov     rax, [rsi]
0x180051ee7  lea     r8, [rsp+0B40h+var_AF8]
0x180051eec  lea     rdx, IID_IContactPool
0x180051ef3  mov     rcx, rsi
0x180051ef6  mov     rax, [rax+88h]
0x180051efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f02  mov     ebx, eax
0x180051f04  test    eax, eax
0x180051f06  jns     short loc_180051F17
0x180051f08  mov     r9d, 3E8h
0x180051f0e  lea     rdx, aInstalldtcFail_5; "InstallDTC: failed GetContactPool"
0x180051f15  jmp     short loc_180051EB3
0x180051f17  mov     rax, [rsi]
0x180051f1a  lea     r8, [rsp+0B40h+var_B00]
0x180051f1f  mov     rdx, r15
0x180051f22  mov     rcx, rsi
0x180051f25  mov     r14d, 4
0x180051f2b  mov     rax, [rax+90h]
0x180051f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f37  xor     ebx, ebx
0x180051f39  lea     rdi, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180051f40  test    eax, eax
0x180051f42  js      short loc_180051F81
0x180051f44  mov     rcx, [rsp+0B40h+var_B00]
0x180051f49  lea     rdx, [rbp+0A40h+var_690]
0x180051f50  mov     r8d, 101h
0x180051f56  mov     rax, [rcx]
0x180051f59  mov     rax, [rax+48h]
0x180051f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f62  test    eax, eax
0x180051f64  jns     loc_180051FEC
0x180051f6a  mov     r9d, 3F7h; unsigned int
0x180051f70  lea     rdx, aInstalldtcFail_1; "InstallDtc: failed to get the host name"...
0x180051f77  mov     r8, rdi; char *
0x180051f7a  mov     ecx, eax; int
0x180051f7c  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180051f81  mov     rax, [rsi]
0x180051f84  mov     rdx, r15
0x180051f87  mov     rcx, rsi
0x180051f8a  mov     rax, [rax+0B8h]
0x180051f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f96  mov     rcx, [rsp+0B40h+var_AF8]
0x180051f9b  lea     r9, [rsp+0B40h+var_B00]
0x180051fa0  lea     r8, IID_IProperties
0x180051fa7  xor     edx, edx
0x180051fa9  mov     rax, [rcx]
0x180051fac  mov     rax, [rax+38h]
0x180051fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fb5  mov     ebx, eax
0x180051fb7  test    eax, eax
0x180051fb9  jns     loc_1800521EC
0x180051fbf  mov     r9d, 40Dh; unsigned int
0x180051fc5  lea     rdx, aInstalldtcCrea_0; "InstallDTC: Create ContactPool"
0x180051fcc  mov     r8, rdi; char *
0x180051fcf  mov     ecx, eax; int
0x180051fd1  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180051fd6  mov     rcx, [rsp+0B40h+var_AF8]
0x180051fdb  mov     rax, [rcx]
0x180051fde  mov     rax, [rax+10h]
0x180051fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fe7  jmp     loc_1800526C8
0x180051fec  cmp     [rbp+0A40h+var_690], bx
0x180051ff3  jnz     short loc_180051F81
0x180051ff5  mov     rcx, [rsp+0B40h+var_B00]
0x180051ffa  lea     r8, [rsp+0B40h+var_AF0]
0x180051fff  lea     rdx, IID_ICustomProperties
0x180052006  mov     rax, [rcx]
0x180052009  mov     rax, [rax]
0x18005200c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052011  mov     ebx, eax
0x180052013  test    eax, eax
0x180052015  jns     short loc_180052029
0x180052017  mov     r9d, 43Fh
0x18005201d  lea     rdx, aInstalldtcFail_7; "InstallDTC: failed QI for ICustomProps "...
0x180052024  jmp     loc_180052230
0x180052029  mov     rcx, [rsp+0B40h+var_AF0]
0x18005202e  lea     r9, [rsp+0B40h+Source]
0x180052033  mov     ebx, 110h
0x180052038  lea     r8, aPath; "Path"
0x18005203f  lea     rdx, aLog; "LOG"
0x180052046  mov     [rsp+0B40h+dwCreationDisposition], ebx
0x18005204a  mov     rax, [rcx]
0x18005204d  mov     rax, [rax+20h]
0x180052051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052056  lea     rcx, [rsp+0B40h+Source]; unsigned __int16 *
0x18005205b  test    eax, eax
0x18005205d  jns     loc_180052126
0x180052063  mov     rdx, rbx; unsigned __int64
0x180052066  mov     r8, r12; unsigned __int16 *
0x180052069  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005206e  mov     rcx, r12; unsigned __int16 *
0x180052071  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x180052076  mov     r9, rax
0x180052079  lea     r8, aSMsdtcLog; "%s\\msdtc.log"
0x180052080  mov     rdx, rbx; unsigned __int64
0x180052083  lea     rcx, [rbp+0A40h+FileName]; unsigned __int16 *
0x18005208a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005208f  xor     edx, edx; AccessMode
0x180052091  lea     rcx, [rbp+0A40h+FileName]; FileName
0x180052098  call    cs:__imp__waccess
0x18005209e  xor     r12d, r12d
0x1800520a1  test    eax, eax
0x1800520a3  jnz     short loc_1800520B7
0x1800520a5  mov     edx, 80h; dwFileAttributes
0x1800520aa  lea     rcx, [rbp+0A40h+FileName]; lpFileName
0x1800520b1  call    cs:__imp_SetFileAttributesW
0x1800520b7  lea     rdx, [rsp+0B40h+var_AE8]; char **
0x1800520bc  mov     [rsp+0B40h+var_AE8], r12
0x1800520c1  mov     rcx, r15; Source
0x1800520c4  call    ?WideToMultiByteString@@YAJPEAGAEAPEAD@Z; WideToMultiByteString(ushort *,char * &)
0x1800520c9  mov     ebx, eax
0x1800520cb  test    eax, eax
0x1800520cd  js      short loc_1800520E7
0x1800520cf  mov     rcx, [rsp+0B40h+var_B00]
0x1800520d4  mov     rdx, [rsp+0B40h+var_AE8]
0x1800520d9  mov     rax, [rcx]
0x1800520dc  mov     rax, [rax+30h]
0x1800520e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520e5  mov     ebx, eax
0x1800520e7  mov     rcx, [rsp+0B40h+var_AE8]; char *
0x1800520ec  call    ?FreeMultiByteString@@YAXPEAD@Z; FreeMultiByteString(char *)
0x1800520f1  test    ebx, ebx
0x1800520f3  jns     loc_18005228C
0x1800520f9  mov     r9d, 4D1h; unsigned int
0x1800520ff  lea     rdx, aInstalldtcSetd_0; "InstallDTC: Setdescription of TM"
0x180052106  mov     ecx, ebx; int
0x180052108  mov     r8, rdi; char *
0x18005210b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180052110  mov     rcx, [rsp+0B40h+var_B00]
0x180052115  mov     rax, [rcx]
0x180052118  mov     rax, [rax+10h]
0x18005211c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052121  jmp     loc_180051FD6
0x180052126  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x18005212b  mov     r9, rax
0x18005212e  lea     r8, aSMsdtcLog; "%s\\msdtc.log"
0x180052135  mov     rdx, rbx; unsigned __int64
0x180052138  lea     rcx, [rbp+0A40h+var_480]; unsigned __int16 *
0x18005213f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052144  xor     edx, edx; AccessMode
0x180052146  lea     rcx, [rbp+0A40h+var_480]; FileName
0x18005214d  call    cs:__imp__waccess
0x180052153  test    eax, eax
0x180052155  jz      short loc_180052161
0x180052157  lea     rcx, [rsp+0B40h+Source]
0x18005215c  jmp     loc_180052063
0x180052161  xor     r12d, r12d
0x180052164  lea     rcx, [rbp+0A40h+var_480]; lpFileName
0x18005216b  mov     [rsp+0B40h+hTemplateFile], r12; hTemplateFile
0x180052170  xor     r9d, r9d; lpSecurityAttributes
0x180052173  mov     [rsp+0B40h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005217b  mov     edx, 80000000h; dwDesiredAccess
0x180052180  mov     [rsp+0B40h+dwCreationDisposition], 3; dwCreationDisposition
0x180052188  lea     r8d, [r12+1]; dwShareMode
0x18005218d  call    cs:__imp_CreateFileW
0x180052193  mov     rbx, rax
0x180052196  lea     rcx, [rax-1]
0x18005219a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005219e  ja      loc_1800520B7
0x1800521a4  xor     edx, edx; lpFileSizeHigh
0x1800521a6  mov     rcx, rax; hFile
0x1800521a9  call    cs:__imp_GetFileSize
0x1800521af  mov     ecx, eax
0x1800521b1  cmp     eax, 0FFFFFFFFh
0x1800521b4  jnz     short loc_1800521BE
0x1800521b6  call    cs:__imp_GetLastError
0x1800521bc  jmp     short loc_1800521DE
0x1800521be  mov     r8d, 431BDE83h
0x1800521c4  mov     eax, r8d
0x1800521c7  mul     ecx
0x1800521c9  mov     eax, r8d
0x1800521cc  shr     edx, 12h
0x1800521cf  imul    ecx, edx, 0F4240h
0x1800521d5  mul     ecx
0x1800521d7  mov     r14d, edx
0x1800521da  shr     r14d, 12h
0x1800521de  mov     rcx, rbx; hObject
0x1800521e1  call    cs:__imp_CloseHandle
0x1800521e7  jmp     loc_1800520B7
0x1800521ec  mov     r8, r12; unsigned __int16 *
0x1800521ef  lea     rcx, [rsp+0B40h+Source]; unsigned __int16 *
0x1800521f4  mov     edx, 110h; unsigned __int64
0x1800521f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800521fe  mov     rcx, [rsp+0B40h+var_B00]
0x180052203  lea     r8, [rsp+0B40h+var_AF0]
0x180052208  lea     rdx, IID_ICustomProperties
0x18005220f  mov     rax, [rcx]
0x180052212  mov     rax, [rax]
0x180052215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005221a  xor     r12d, r12d
0x18005221d  mov     ebx, eax
0x18005221f  test    eax, eax
0x180052221  jns     short loc_180052255
0x180052223  mov     r9d, 419h; unsigned int
0x180052229  lea     rdx, aInstalldtcFail_4; "InstallDTC: failed QI for ICustomProps "...
0x180052230  mov     r8, rdi; char *
0x180052233  mov     ecx, eax; int
0x180052235  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18005223a  mov     rcx, [rsp+0B40h+var_AF8]
0x18005223f  mov     rax, [rcx]
0x180052242  mov     rax, [rax+10h]
0x180052246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005224b  mov     rcx, [rsp+0B40h+var_B00]
0x180052250  jmp     loc_180051FDB
0x180052255  mov     rcx, [rsp+0B40h+var_B00]
0x18005225a  lea     rdx, SVCID_MSDTC_TM
0x180052261  mov     r8d, 1
0x180052267  mov     rax, [rcx]
0x18005226a  mov     rax, [rax+78h]
0x18005226e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052273  mov     ebx, eax
0x180052275  test    eax, eax
0x180052277  jns     loc_1800520B7
0x18005227d  mov     r9d, 426h
0x180052283  lea     rdx, aInstalldtcSets_1; "InstallDTC: Setserviceid of TM"
0x18005228a  jmp     short loc_180052230
0x18005228c  mov     rcx, [rsp+0B40h+var_B00]
0x180052291  lea     rdx, CLSID_DTCTM
0x180052298  mov     rax, [rcx]
0x18005229b  mov     rax, [rax+68h]
0x18005229f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522a4  mov     ebx, eax
0x1800522a6  test    eax, eax
0x1800522a8  jns     short loc_1800522BE
0x1800522aa  mov     r9d, 4DCh
0x1800522b0  lea     rdx, aInstalldtcSetc_0; "InstallDTC: SetClassId of TM"
0x1800522b7  mov     ecx, eax
0x1800522b9  jmp     loc_180052108
0x1800522be  mov     rcx, [rsp+0B40h+var_AF8]
0x1800522c3  xor     r8d, r8d
0x1800522c6  mov     rdx, [rsp+0B40h+var_B00]
0x1800522cb  mov     rax, [rcx]
0x1800522ce  mov     rax, [rax+40h]
0x1800522d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522d7  mov     ebx, eax
0x1800522d9  test    eax, eax
0x1800522db  jns     short loc_1800522EC
0x1800522dd  mov     r9d, 4E9h
0x1800522e3  lea     rdx, aInstalldtcWrit_0; "InstallDTC: Write of TM"
0x1800522ea  jmp     short loc_1800522B7
  ... truncated ...
```
