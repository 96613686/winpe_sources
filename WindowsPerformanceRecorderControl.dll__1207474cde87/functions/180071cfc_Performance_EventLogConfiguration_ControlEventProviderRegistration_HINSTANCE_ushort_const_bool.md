# Performance::EventLogConfiguration::ControlEventProviderRegistration(HINSTANCE__ *,ushort const *,bool)

- ea: `0x180071cfc`
- end: `0x180071ea3`
- name: `?ControlEventProviderRegistration@EventLogConfiguration@Performance@@YAJPEAUHINSTANCE__@@PEBG_N@Z`
- size: `423`
- prototype: `__int64 __fastcall(HMODULE hModule, HINSTANCE, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180072450`
- `0x180072880`

## callees

- `0x180008330`
- `0x1800102a0`
- `0x1800131a0`
- `0x18001c820`
- `0x18002a6b4`
- `0x18004b39c`
- `0x180071cfc`
- `0x180071eac`
- `0x180072028`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180071ddd`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180071ddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071dbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071dbd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071e7e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071e7e`

## string_xrefs

- `0x180071d58`: `wevtutil.exe uninstall-manifest %ws`
- `0x180071e10`: `wevtutil.exe install-manifest "%ws" /mf:"%ws" /rf:"%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Performance::EventLogConfiguration::ControlEventProviderRegistration(
        HMODULE hModule,
        HINSTANCE a2,
        const unsigned __int16 *a3)
{
  char v3; // r14
  __int64 v5; // rdx
  int v6; // eax
  int Error; // edi
  const WCHAR *v8; // rbx
  int v9; // eax
  WCHAR *v10; // rax
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-30h] BYREF
  ATL::CAtlException *v14; // [rsp+48h] [rbp-20h] BYREF
  HINSTANCE v15; // [rsp+78h] [rbp+10h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp+20h] BYREF

  v15 = a2;
  v13[1] = -2;
  v3 = (char)a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  v6 = Performance::EventLogConfiguration::_anonymous_namespace_::ExtractResourceToFile(hModule, v5, &lpFileName);
  try
  {
    Error = v6;
    if ( v6 < 0 )
    {
      v8 = lpFileName;
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
      v8 = lpFileName;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v12,
        L"wevtutil.exe uninstall-manifest %ws",
        lpFileName);
      LODWORD(v15) = 0;
      v9 = Performance::EventLogConfiguration::_anonymous_namespace_::ExecuteCommand(v12, &v15);
      if ( !v3 )
      {
        Error = v9;
        if ( v9 >= 0 )
        {
          if ( (_DWORD)v15 )
            Error = (int)v15;
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v12);
      if ( Error >= 0 && v3 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
        SetLastError(0);
        v10 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v12, 260);
        GetModuleFileNameW(hModule, v10, 0x104u);
        ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v12);
        Error = ATL::AtlHresultFromLastError();
        if ( Error >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v13);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            v13,
            L"wevtutil.exe install-manifest \"%ws\" /mf:\"%ws\" /rf:\"%ws\"",
            v8);
          LODWORD(v15) = 0;
          Error = Performance::EventLogConfiguration::_anonymous_namespace_::ExecuteCommand(v13[0], &v15);
          if ( Error >= 0 && (_DWORD)v15 )
            Error = (int)v15;
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v13);
        }
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v12);
      }
    }
  }
  catch ( ATL::CAtlException *v14 )
  {
    LODWORD(v15) = *(_DWORD *)v14;
    Error = (int)v15;
    v8 = lpFileName;
  }
  if ( *((_DWORD *)v8 - 4) )
    DeleteFileW(v8);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180071cfc  mov     rax, rsp
0x180071cff  mov     [rax+10h], rdx
0x180071d03  push    rdi
0x180071d04  push    r14
0x180071d06  push    r15
0x180071d08  sub     rsp, 50h
0x180071d0c  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180071d14  mov     [rax+8], rbx
0x180071d18  mov     r14b, r8b
0x180071d1b  mov     r15, rcx
0x180071d1e  lea     rcx, [rax+20h]; void *
0x180071d22  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180071d27  nop
0x180071d28  lea     r8, [rsp+68h+lpFileName]
0x180071d30  mov     rcx, r15; hModule
0x180071d33  call    Performance__EventLogConfiguration___anonymous_namespace___ExtractResourceToFile
0x180071d38  mov     edi, eax
0x180071d3a  test    eax, eax
0x180071d3c  js      loc_180071E5F
0x180071d42  lea     rcx, [rsp+68h+var_38]; void *
0x180071d47  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180071d4c  nop
0x180071d4d  mov     rbx, [rsp+68h+lpFileName]
0x180071d55  mov     r8, rbx
0x180071d58  lea     rdx, aWevtutilExeUni; "wevtutil.exe uninstall-manifest %ws"
0x180071d5f  lea     rcx, [rsp+68h+var_38]
0x180071d64  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180071d69  mov     dword ptr [rsp+68h+arg_8], 0
0x180071d71  lea     rdx, [rsp+68h+arg_8]
0x180071d76  mov     rcx, [rsp+68h+var_38]
0x180071d7b  call    Performance__EventLogConfiguration___anonymous_namespace___ExecuteCommand
0x180071d80  test    r14b, r14b
0x180071d83  jnz     short loc_180071D95
0x180071d85  mov     edi, eax
0x180071d87  test    eax, eax
0x180071d89  js      short loc_180071D95
0x180071d8b  cmp     dword ptr [rsp+68h+arg_8], 0
0x180071d90  cmovnz  edi, dword ptr [rsp+68h+arg_8]
0x180071d95  lea     rcx, [rsp+68h+var_38]; this
0x180071d9a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071d9f  test    edi, edi
0x180071da1  js      loc_180071E67
0x180071da7  test    r14b, r14b
0x180071daa  jz      loc_180071E67
0x180071db0  lea     rcx, [rsp+68h+var_38]; void *
0x180071db5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180071dba  nop
0x180071dbb  xor     ecx, ecx; dwErrCode
0x180071dbd  call    cs:__imp_SetLastError
0x180071dc3  mov     edi, 104h
0x180071dc8  mov     edx, edi
0x180071dca  lea     rcx, [rsp+68h+var_38]
0x180071dcf  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x180071dd4  mov     r8d, edi; nSize
0x180071dd7  mov     rdx, rax; lpFilename
0x180071dda  mov     rcx, r15; hModule
0x180071ddd  call    cs:__imp_GetModuleFileNameW
0x180071de3  lea     rcx, [rsp+68h+var_38]
0x180071de8  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180071ded  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180071df2  mov     edi, eax
0x180071df4  test    eax, eax
0x180071df6  js      short loc_180071E53
0x180071df8  lea     rcx, [rsp+68h+var_30]; void *
0x180071dfd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180071e02  nop
0x180071e03  mov     r9, [rsp+68h+var_38]
0x180071e08  mov     [rsp+68h+var_48], r9
0x180071e0d  mov     r8, rbx
0x180071e10  lea     rdx, aWevtutilExeIns; "wevtutil.exe install-manifest \"%ws\" /"...
0x180071e17  lea     rcx, [rsp+68h+var_30]
0x180071e1c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180071e21  mov     dword ptr [rsp+68h+arg_8], 0
0x180071e29  lea     rdx, [rsp+68h+arg_8]
0x180071e2e  mov     rcx, [rsp+68h+var_30]
0x180071e33  call    Performance__EventLogConfiguration___anonymous_namespace___ExecuteCommand
0x180071e38  mov     edi, eax
0x180071e3a  test    eax, eax
0x180071e3c  js      short loc_180071E48
0x180071e3e  cmp     dword ptr [rsp+68h+arg_8], 0
0x180071e43  cmovnz  edi, dword ptr [rsp+68h+arg_8]
0x180071e48  lea     rcx, [rsp+68h+var_30]; this
0x180071e4d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071e52  nop
0x180071e53  lea     rcx, [rsp+68h+var_38]; this
0x180071e58  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071e5d  jmp     short loc_180071E67
0x180071e5f  mov     rbx, [rsp+68h+lpFileName]
0x180071e67  jmp     short loc_180071E75
0x180071e69  mov     edi, dword ptr [rsp+68h+arg_8]
0x180071e6d  mov     rbx, [rsp+68h+lpFileName]
0x180071e75  cmp     dword ptr [rbx-10h], 0
0x180071e79  jz      short loc_180071E85
0x180071e7b  mov     rcx, rbx; lpFileName
0x180071e7e  call    cs:__imp_DeleteFileW
0x180071e84  nop
0x180071e85  lea     rcx, [rsp+68h+lpFileName]; this
0x180071e8d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071e92  mov     eax, edi
0x180071e94  mov     rbx, [rsp+68h+arg_0]
0x180071e99  add     rsp, 50h
0x180071e9d  pop     r15
0x180071e9f  pop     r14
0x180071ea1  pop     rdi
0x180071ea2  retn
```
