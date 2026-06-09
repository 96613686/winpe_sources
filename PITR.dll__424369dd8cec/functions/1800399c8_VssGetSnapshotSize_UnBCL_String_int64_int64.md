# VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)

- ea: `0x1800399c8`
- end: `0x18003a007`
- name: `?VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z`
- size: `1599`
- prototype: `__int64 __fastcall(struct UnBCL::String *, __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000a5f0`
- `0x18000fab0`
- `0x1800131c4`

## callees

- `0x18000253c`
- `0x180009e04`
- `0x180039424`
- `0x1800399c8`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039c10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f18`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039c5a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039c5a`
- `WDSCORE!CurrentIP` at `0x180039cc0`
- `WDSCORE!CurrentIP` at `0x180039d65`
- `WDSCORE!CurrentIP` at `0x180039e39`
- `WDSCORE!CurrentIP` at `0x180039f20`
- `WDSCORE!CurrentIP` at `0x180039cc0`
- `WDSCORE!CurrentIP` at `0x180039d65`
- `WDSCORE!CurrentIP` at `0x180039e39`
- `WDSCORE!CurrentIP` at `0x180039f20`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039d2b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039dc1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039f97`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039d2b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039dc1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180039f97`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180039c75`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180039c75`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180039ab4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180039b22`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180039ab4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180039b22`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180039ad5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180039b43`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180039ad5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180039b43`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039be3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039ccc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039e53`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039f3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039be3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039ccc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039e53`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180039f3a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039af2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039b60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039bac`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039af2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039b60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180039bac`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180039a1b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180039a1b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039a55`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039b80`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039bcc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039c84`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039a55`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039b80`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039bcc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180039c84`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039b06`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039b74`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039bc0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039b06`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039b74`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180039bc0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039b8e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039bda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039e4a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039f31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039b8e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039bda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039e4a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180039f31`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x180039b9e`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x180039b9e`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180039a72`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180039a72`

## string_xrefs

- `0x180039d6e`: `Non-client accessible snapshots need to be exposed`
- `0x180039d08`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180039d9e`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180039e8d`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180039f74`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`
- `0x180039e5f`: `Error opening volume handle for %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall VssGetSnapshotSize(struct UnBCL::String *a1, __int64 *a2, __int64 *a3)
{
  int SnapshotProp; // ebx
  UnBCL::String *v7; // rax
  UnBCL::String *v8; // rbx
  UnBCL::String *v9; // rax
  UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *v13; // rax
  HANDLE FileW; // rax
  BOOL v15; // eax
  DWORD LastError; // esi
  __int64 v17; // r14
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  signed int v23; // eax
  bool v24; // sf
  signed int v25; // eax
  unsigned int v26; // ebx
  DWORD v27; // edi
  __int64 v28; // rsi
  UnBCL::String *v29; // rax
  const char *v30; // rax
  struct tagLOG_PARTIAL_MSG *v31; // rax
  signed int v32; // eax
  bool v33; // sf
  signed int v34; // eax
  unsigned int v35; // ebx
  DWORD v36; // edi
  __int64 v37; // rsi
  UnBCL::String *v38; // rax
  const char *v39; // rax
  struct tagLOG_PARTIAL_MSG *v40; // rax
  _BYTE v41[16]; // [rsp+68h] [rbp-150h] BYREF
  __int64 v42; // [rsp+78h] [rbp-140h]
  _QWORD *pExceptionObject; // [rsp+80h] [rbp-138h] BYREF
  _QWORD *v44; // [rsp+88h] [rbp-130h] BYREF
  _QWORD *v45; // [rsp+90h] [rbp-128h] BYREF
  _QWORD *v46; // [rsp+98h] [rbp-120h] BYREF
  _QWORD *v47; // [rsp+A0h] [rbp-118h] BYREF
  UnBCL::String *v48; // [rsp+A8h] [rbp-110h]
  struct _VSS_SNAPSHOT_PROP v49; // [rsp+B0h] [rbp-108h] BYREF
  _BYTE v50[16]; // [rsp+130h] [rbp-88h] BYREF
  DWORD BytesReturned; // [rsp+140h] [rbp-78h] BYREF
  __int128 OutBuffer; // [rsp+148h] [rbp-70h] BYREF
  __int64 v53; // [rsp+158h] [rbp-60h]
  _QWORD v54[7]; // [rsp+160h] [rbp-58h] BYREF

  memset_0(&v49, 0, sizeof(v49));
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v50);
  v42 = -1;
  OutBuffer = 0;
  v53 = 0;
  BytesReturned = 0;
  if ( a1 )
  {
    UnBCL::Exception::Exception((UnBCL::Exception *)v54);
    try
    {
      v54[0] = &`VssGetSnapshotSize'::`6'::CXXXXXHandledException::`vftable';
      SnapshotProp = VssGetSnapshotProp(a1, &v49);
      if ( SnapshotProp < 0 )
      {
        LastError = GetLastError();
        v17 = CurrentIP();
        CString = (const char *)UnBCL::String::get_CString(a1);
        v19 = ConstructPartialMsgW(
                0x4000000,
                "Error retrieving snapshot properties for %s. Error: 0x%08X",
                CString,
                SnapshotProp);
        WdsSetupLogMessageW(
          v19,
          0,
          L"D",
          0,
          353,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssGetSnapshotSize",
          v17,
          LastError,
          0,
          0);
        pExceptionObject = v54;
        throw (`VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException **)&pExceptionObject;
      }
      if ( (v49.m_lSnapshotAttributes & 4) != 0 )
      {
        v7 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v8 = v7;
        v48 = v7;
        if ( v7 )
        {
          UnBCL::String::String(v7, v49.m_pwszSnapshotDeviceObject);
          *(_QWORD *)v8 = &UnBCL::String::`local vftable';
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        if ( !v49.m_pwszExposedPath )
        {
          v20 = GetLastError();
          v21 = CurrentIP();
          v22 = ConstructPartialMsgW(0x2000000, "Non-client accessible snapshots need to be exposed");
          WdsSetupLogMessageW(
            v22,
            0,
            L"D",
            0,
            368,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
            L"VssGetSnapshotSize",
            v21,
            v20,
            0,
            0);
          v44 = v54;
          throw (`VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException **)&v44;
        }
        v9 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v8 = v9;
        v48 = v9;
        if ( v9 )
        {
          UnBCL::String::String(v9, v49.m_pwszExposedPath);
          *(_QWORD *)v8 = &UnBCL::String::`local vftable';
        }
        else
        {
          v8 = 0;
        }
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v41, v8);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v41);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v41);
      v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
      v11 = UnBCL::String::TrimEnd(v10, L"\\");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v41, v11);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v41);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v41);
      v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
      v13 = UnBCL::String::get_CString(v12);
      FileW = CreateFileW(v13, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
      v42 = (__int64)FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v23 = GetLastError();
        v24 = v23 < 0;
        if ( v23 > 0 )
          v24 = 1;
        if ( v24 )
        {
          v25 = GetLastError();
          v26 = v25;
          if ( v25 > 0 )
            v26 = (unsigned __int16)v25 | 0x80070000;
        }
        else
        {
          v26 = -2147467259;
        }
        v27 = GetLastError();
        v28 = CurrentIP();
        v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
        v30 = (const char *)UnBCL::String::get_CString(v29);
        v31 = ConstructPartialMsgW(0x2000000, "Error opening volume handle for %s. Error: 0x%08X", v30, v26);
        WdsSetupLogMessageW(
          v31,
          0,
          L"D",
          0,
          388,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
          L"VssGetSnapshotSize",
          v28,
          v27,
          0,
          0);
        v45 = v54;
        throw (`VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException **)&v45;
      }
      v15 = DeviceIoControl(FileW, 0x5301D0u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0);
    }
    catch ( UnBCL::YAJPEAVString:: )
    {
      JUMPOUT(0x18005242CLL);
    }
    if ( !v15 )
    {
      v32 = GetLastError();
      v33 = v32 < 0;
      if ( v32 > 0 )
        v33 = 1;
      if ( v33 )
      {
        v34 = GetLastError();
        v35 = v34;
        if ( v34 > 0 )
          v35 = (unsigned __int16)v34 | 0x80070000;
      }
      else
      {
        v35 = -2147467259;
      }
      v36 = GetLastError();
      v37 = CurrentIP();
      v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
      v39 = (const char *)UnBCL::String::get_CString(v38);
      v40 = ConstructPartialMsgW(0x2000000, "Error querying diff area for %s. Error: 0x%08X", v39, v35);
      WdsSetupLogMessageW(
        v40,
        0,
        L"D",
        0,
        405,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
        L"VssGetSnapshotSize",
        v37,
        v36,
        0,
        0);
      v46 = v54;
      throw (`VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException **)&v46;
    }
    if ( a2 )
      *a2 = OutBuffer;
    v47 = v54;
    throw (`VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException **)&v47;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v50);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800399c8  mov     [rsp+arg_10], rbx
0x1800399cd  mov     [rsp+arg_18], rsi
0x1800399d2  push    rdi
0x1800399d3  push    r14
0x1800399d5  push    r15
0x1800399d7  sub     rsp, 1A0h
0x1800399de  mov     rax, cs:__security_cookie
0x1800399e5  xor     rax, rsp
0x1800399e8  mov     [rsp+1B8h+var_20], rax
0x1800399f0  mov     rsi, rdx
0x1800399f3  mov     rdi, rcx
0x1800399f6  xor     r15d, r15d
0x1800399f9  mov     [rsp+1B8h+var_158], r15d
0x1800399fe  xor     edx, edx; Val
0x180039a00  mov     r8d, 80h; Size
0x180039a06  lea     rcx, [rsp+1B8h+var_108]; void *
0x180039a0e  call    memset_0
0x180039a13  lea     rcx, [rsp+1B8h+var_88]
0x180039a1b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180039a21  nop
0x180039a22  mov     [rsp+1B8h+var_140], 0FFFFFFFFFFFFFFFFh
0x180039a2b  xorps   xmm0, xmm0
0x180039a2e  xor     eax, eax
0x180039a30  movups  [rsp+1B8h+OutBuffer], xmm0
0x180039a38  mov     [rsp+1B8h+var_60], rax
0x180039a40  mov     [rsp+1B8h+BytesReturned], r15d
0x180039a48  test    rdi, rdi
0x180039a4b  jnz     short loc_180039A65
0x180039a4d  lea     rcx, [rsp+1B8h+var_88]
0x180039a55  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180039a5b  mov     eax, 80070057h
0x180039a60  jmp     loc_180039C8E
0x180039a65  mov     [rsp+1B8h+var_154], r15d
0x180039a6a  lea     rcx, [rsp+1B8h+var_58]
0x180039a72  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180039a78  lea     rax, ??_7CXXXXXHandledException@?5??VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z@6B@; const `VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)'::`6'::CXXXXXHandledException::`vftable'
0x180039a7f  mov     [rsp+1B8h+var_58], rax
0x180039a87  lea     rdx, [rsp+1B8h+var_108]; struct _VSS_SNAPSHOT_PROP *
0x180039a8f  mov     rcx, rdi; struct UnBCL::String *
0x180039a92  call    ?VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z; VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)
0x180039a97  mov     ebx, eax
0x180039a99  mov     [rsp+1B8h+var_158], eax
0x180039a9d  test    eax, eax
0x180039a9f  js      loc_180039CB7
0x180039aa5  test    byte ptr [rsp+1B8h+var_108.m_lSnapshotAttributes], 4
0x180039aad  jz      short loc_180039B0F
0x180039aaf  mov     ecx, 18h
0x180039ab4  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180039aba  mov     rbx, rax
0x180039abd  mov     [rsp+1B8h+var_110], rax
0x180039ac5  test    rax, rax
0x180039ac8  jz      short loc_180039AE7
0x180039aca  mov     rdx, [rsp+1B8h+var_108.m_pwszSnapshotDeviceObject]
0x180039ad2  mov     rcx, rax
0x180039ad5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180039adb  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180039ae2  mov     [rbx], rax
0x180039ae5  jmp     short loc_180039AEA
0x180039ae7  mov     rbx, r15
0x180039aea  mov     rdx, rbx
0x180039aed  lea     rcx, [rsp+1B8h+var_150]
0x180039af2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180039af8  nop
0x180039af9  lea     rdx, [rsp+1B8h+var_150]
0x180039afe  lea     rcx, [rsp+1B8h+var_88]
0x180039b06  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180039b0c  nop
0x180039b0d  jmp     short loc_180039B7B
0x180039b0f  cmp     [rsp+1B8h+var_108.m_pwszExposedPath], r15
0x180039b17  jz      loc_180039D5D
0x180039b1d  mov     ecx, 18h
0x180039b22  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180039b28  mov     rbx, rax
0x180039b2b  mov     [rsp+1B8h+var_110], rax
0x180039b33  test    rax, rax
0x180039b36  jz      short loc_180039B55
0x180039b38  mov     rdx, [rsp+1B8h+var_108.m_pwszExposedPath]
0x180039b40  mov     rcx, rax
0x180039b43  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180039b49  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180039b50  mov     [rbx], rax
0x180039b53  jmp     short loc_180039B58
0x180039b55  mov     rbx, r15
0x180039b58  mov     rdx, rbx
0x180039b5b  lea     rcx, [rsp+1B8h+var_150]
0x180039b60  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180039b66  nop
0x180039b67  lea     rdx, [rsp+1B8h+var_150]
0x180039b6c  lea     rcx, [rsp+1B8h+var_88]
0x180039b74  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180039b7a  nop
0x180039b7b  lea     rcx, [rsp+1B8h+var_150]
0x180039b80  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180039b86  lea     rcx, [rsp+1B8h+var_88]
0x180039b8e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180039b94  lea     rdx, pszSrc; "\\"
0x180039b9b  mov     rcx, rax
0x180039b9e  call    cs:__imp_?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z; UnBCL::String::TrimEnd(ushort const *)
0x180039ba4  mov     rdx, rax
0x180039ba7  lea     rcx, [rsp+1B8h+var_150]
0x180039bac  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180039bb2  nop
0x180039bb3  lea     rdx, [rsp+1B8h+var_150]
0x180039bb8  lea     rcx, [rsp+1B8h+var_88]
0x180039bc0  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180039bc6  nop
0x180039bc7  lea     rcx, [rsp+1B8h+var_150]
0x180039bcc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180039bd2  lea     rcx, [rsp+1B8h+var_88]
0x180039bda  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180039be0  mov     rcx, rax
0x180039be3  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180039be9  mov     [rsp+1B8h+hTemplateFile], r15; hTemplateFile
0x180039bee  mov     r14d, 2000000h
0x180039bf4  mov     [rsp+1B8h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180039bf9  mov     [rsp+1B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180039c01  xor     r9d, r9d; lpSecurityAttributes
0x180039c04  mov     edx, 80000000h; dwDesiredAccess
0x180039c09  lea     r8d, [r9+7]; dwShareMode
0x180039c0d  mov     rcx, rax; lpFileName
0x180039c10  call    cs:__imp_CreateFileW
0x180039c16  mov     [rsp+1B8h+var_140], rax
0x180039c1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039c1f  jz      loc_180039DFB
0x180039c25  mov     [rsp+1B8h+lpOverlapped], r15; lpOverlapped
0x180039c2a  lea     rcx, [rsp+1B8h+BytesReturned]
0x180039c32  mov     [rsp+1B8h+hTemplateFile], rcx; lpBytesReturned
0x180039c37  mov     [rsp+1B8h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x180039c3f  lea     rcx, [rsp+1B8h+OutBuffer]
0x180039c47  mov     qword ptr [rsp+1B8h+dwCreationDisposition], rcx; lpOutBuffer
0x180039c4c  xor     r9d, r9d; nInBufferSize
0x180039c4f  xor     r8d, r8d; lpInBuffer
0x180039c52  mov     edx, 5301D0h; dwIoControlCode
0x180039c57  mov     rcx, rax; hDevice
0x180039c5a  call    cs:__imp_DeviceIoControl
0x180039c60  test    eax, eax
0x180039c62  jnz     loc_180039FC9
0x180039c68  jmp     loc_180039EE2
0x180039c6d  lea     rcx, [rsp+1B8h+var_58]
0x180039c75  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x180039c7b  nop
0x180039c7c  lea     rcx, [rsp+1B8h+var_88]
0x180039c84  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180039c8a  mov     eax, [rsp+1B8h+var_158]
0x180039c8e  mov     rcx, [rsp+1B8h+var_20]
0x180039c96  xor     rcx, rsp; StackCookie
0x180039c99  call    __security_check_cookie
0x180039c9e  lea     r11, [rsp+1B8h+var_18]
0x180039ca6  mov     rbx, [r11+30h]
0x180039caa  mov     rsi, [r11+38h]
0x180039cae  mov     rsp, r11
0x180039cb1  pop     r15
0x180039cb3  pop     r14
0x180039cb5  pop     rdi
0x180039cb6  retn
0x180039cb7  call    cs:__imp_GetLastError
0x180039cbd  nop
0x180039cbe  mov     esi, eax
0x180039cc0  call    cs:__imp_CurrentIP
0x180039cc6  mov     r14, rax
0x180039cc9  mov     rcx, rdi
0x180039ccc  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180039cd2  mov     r9d, ebx
0x180039cd5  mov     r8, rax
0x180039cd8  lea     rdx, aErrorRetrievin_0; "Error retrieving snapshot properties fo"...
0x180039cdf  mov     ecx, 4000000h; unsigned int
0x180039ce4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180039ce9  mov     [rsp+1B8h+var_168], r15d
0x180039cee  mov     [rsp+1B8h+var_170], r15
0x180039cf3  mov     [rsp+1B8h+var_178], esi
0x180039cf7  mov     [rsp+1B8h+lpOverlapped], r14
0x180039cfc  lea     rcx, aVssgetsnapshot_5; "VssGetSnapshotSize"
0x180039d03  mov     [rsp+1B8h+hTemplateFile], rcx
0x180039d08  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039d0f  mov     qword ptr [rsp+1B8h+dwFlagsAndAttributes], rcx
0x180039d14  mov     [rsp+1B8h+dwCreationDisposition], 161h
0x180039d1c  xor     r9d, r9d
0x180039d1f  lea     r8, aD; "D"
0x180039d26  xor     edx, edx
0x180039d28  mov     rcx, rax
0x180039d2b  call    cs:__imp_WdsSetupLogMessageW
0x180039d31  mov     [rsp+1B8h+var_154], 1
0x180039d39  lea     rax, [rsp+1B8h+var_58]
0x180039d41  mov     [rsp+1B8h+pExceptionObject], rax
0x180039d49  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z@; pThrowInfo
0x180039d50  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180039d58  call    _CxxThrowException_0
0x180039d5d  call    cs:__imp_GetLastError
0x180039d63  mov     edi, eax
0x180039d65  call    cs:__imp_CurrentIP
0x180039d6b  mov     rbx, rax
0x180039d6e  lea     rdx, aNonClientAcces; "Non-client accessible snapshots need to"...
0x180039d75  mov     ecx, 2000000h; unsigned int
0x180039d7a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180039d7f  mov     [rsp+1B8h+var_168], r15d
0x180039d84  mov     [rsp+1B8h+var_170], r15
0x180039d89  mov     [rsp+1B8h+var_178], edi
0x180039d8d  mov     [rsp+1B8h+lpOverlapped], rbx
0x180039d92  lea     rcx, aVssgetsnapshot_5; "VssGetSnapshotSize"
0x180039d99  mov     [rsp+1B8h+hTemplateFile], rcx
0x180039d9e  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039da5  mov     qword ptr [rsp+1B8h+dwFlagsAndAttributes], rcx
0x180039daa  mov     [rsp+1B8h+dwCreationDisposition], 170h
0x180039db2  xor     r9d, r9d
0x180039db5  lea     r8, aD; "D"
0x180039dbc  xor     edx, edx
0x180039dbe  mov     rcx, rax
0x180039dc1  call    cs:__imp_WdsSetupLogMessageW
0x180039dc7  mov     [rsp+1B8h+var_158], 80042301h
0x180039dcf  mov     [rsp+1B8h+var_154], 1
0x180039dd7  lea     rax, [rsp+1B8h+var_58]
0x180039ddf  mov     [rsp+1B8h+var_130], rax
0x180039de7  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z@; pThrowInfo
0x180039dee  lea     rcx, [rsp+1B8h+var_130]; pExceptionObject
0x180039df6  call    _CxxThrowException_0
0x180039dfb  call    cs:__imp_GetLastError
0x180039e01  test    eax, eax
0x180039e03  jle     short loc_180039E0F
0x180039e05  movzx   eax, ax
0x180039e08  or      eax, 80070000h
0x180039e0d  test    eax, eax
0x180039e0f  jns     short loc_180039E28
0x180039e11  call    cs:__imp_GetLastError
0x180039e17  mov     ebx, eax
0x180039e19  test    eax, eax
0x180039e1b  jle     short loc_180039E2D
0x180039e1d  movzx   ebx, ax
0x180039e20  or      ebx, 80070000h
0x180039e26  jmp     short loc_180039E2D
0x180039e28  mov     ebx, 80004005h
0x180039e2d  mov     [rsp+1B8h+var_158], ebx
0x180039e31  call    cs:__imp_GetLastError
0x180039e37  mov     edi, eax
0x180039e39  call    cs:__imp_CurrentIP
0x180039e3f  mov     rsi, rax
0x180039e42  lea     rcx, [rsp+1B8h+var_88]
0x180039e4a  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180039e50  mov     rcx, rax
0x180039e53  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180039e59  mov     r9d, ebx
0x180039e5c  mov     r8, rax
0x180039e5f  lea     rdx, aErrorOpeningVo; "Error opening volume handle for %s. Err"...
0x180039e66  mov     ecx, r14d; unsigned int
0x180039e69  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180039e6e  mov     [rsp+1B8h+var_168], r15d
0x180039e73  mov     [rsp+1B8h+var_170], r15
0x180039e78  mov     [rsp+1B8h+var_178], edi
0x180039e7c  mov     [rsp+1B8h+lpOverlapped], rsi
0x180039e81  lea     rcx, aVssgetsnapshot_5; "VssGetSnapshotSize"
0x180039e88  mov     [rsp+1B8h+hTemplateFile], rcx
0x180039e8d  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180039e94  mov     qword ptr [rsp+1B8h+dwFlagsAndAttributes], rcx
0x180039e99  mov     [rsp+1B8h+dwCreationDisposition], 184h
0x180039ea1  xor     r9d, r9d
0x180039ea4  lea     r8, aD; "D"
0x180039eab  xor     edx, edx
0x180039ead  mov     rcx, rax
0x180039eb0  call    cs:__imp_WdsSetupLogMessageW
0x180039eb6  mov     [rsp+1B8h+var_154], 1
0x180039ebe  lea     rax, [rsp+1B8h+var_58]
0x180039ec6  mov     [rsp+1B8h+var_128], rax
0x180039ece  lea     rdx, __TI4PEAVCXXXXXHandledException@?5??VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z@; pThrowInfo
0x180039ed5  lea     rcx, [rsp+1B8h+var_128]; pExceptionObject
0x180039edd  call    _CxxThrowException_0
0x180039ee2  call    cs:__imp_GetLastError
0x180039ee8  test    eax, eax
0x180039eea  jle     short loc_180039EF6
0x180039eec  movzx   eax, ax
0x180039eef  or      eax, 80070000h
0x180039ef4  test    eax, eax
0x180039ef6  jns     short loc_180039F0F
0x180039ef8  call    cs:__imp_GetLastError
0x180039efe  mov     ebx, eax
0x180039f00  test    eax, eax
0x180039f02  jle     short loc_180039F14
0x180039f04  movzx   ebx, ax
0x180039f07  or      ebx, 80070000h
0x180039f0d  jmp     short loc_180039F14
0x180039f0f  mov     ebx, 80004005h
0x180039f14  mov     [rsp+1B8h+var_158], ebx
0x180039f18  call    cs:__imp_GetLastError
0x180039f1e  mov     edi, eax
0x180039f20  call    cs:__imp_CurrentIP
0x180039f26  mov     rsi, rax
0x180039f29  lea     rcx, [rsp+1B8h+var_88]
0x180039f31  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180039f37  mov     rcx, rax
0x180039f3a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180039f40  mov     r9d, ebx
0x180039f43  mov     r8, rax
0x180039f46  lea     rdx, aErrorQueryingD; "Error querying diff area for %s. Error:"...
0x180039f4d  mov     ecx, r14d; unsigned int
0x180039f50  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180039f55  mov     [rsp+1B8h+var_168], r15d
0x180039f5a  mov     [rsp+1B8h+var_170], r15
0x180039f5f  mov     [rsp+1B8h+var_178], edi
0x180039f63  mov     [rsp+1B8h+lpOverlapped], rsi
0x180039f68  lea     rcx, aVssgetsnapshot_5; "VssGetSnapshotSize"
0x180039f6f  mov     [rsp+1B8h+hTemplateFile], rcx
0x180039f74  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
  ... truncated ...
```
