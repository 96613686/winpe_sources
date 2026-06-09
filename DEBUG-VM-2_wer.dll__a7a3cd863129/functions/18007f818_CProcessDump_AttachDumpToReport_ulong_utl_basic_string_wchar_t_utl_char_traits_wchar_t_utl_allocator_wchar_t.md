# CProcessDump::AttachDumpToReport(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18007f818`
- end: `0x18007fd52`
- name: `?AttachDumpToReport@CProcessDump@@QEAAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1338`
- prototype: `__int64 __fastcall(CProcessDump *this)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800360d0`
- `0x1800363fc`

## callees

- `0x180007db4`
- `0x180007de0`
- `0x180007e10`
- `0x180009ad4`
- `0x18000b880`
- `0x18000bbc0`
- `0x18000c390`
- `0x18000d590`
- `0x18001bbc4`
- `0x18001da80`
- `0x18001dfac`
- `0x18001f870`
- `0x18001fe24`
- `0x180027884`
- `0x18002ffc4`
- `0x180039f70`
- `0x18003bf14`
- `0x18003d990`
- `0x18003ec1c`
- `0x180044230`
- `0x180050db0`
- `0x180051efc`
- `0x180051fa4`
- `0x18007f510`
- `0x18007f818`
- `0x18007fd58`
- `0x180081b60`
- `0x180081b8c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007faad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007faad`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007f985`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007fd0a`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007f985`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007fd0a`

## string_xrefs

- `0x18007fc1c`: `Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.`
- `0x18007fc44`: `Dump file could not be created: Failed to produce security attributes %08X.`
- `0x18007fc32`: `Couldn't write out the GameCore specific heap dump file path %08X.`
- `0x18007fc3b`: `Dump file could not be created: UtilGetTempFile %08X.`
- `0x18007fca9`: `onecore\windows\feedback\core\werdll\lib\processdump.cpp`
- `0x18007fce8`: `Dump path could not be copied: %08X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProcessDump::AttachDumpToReport(enum _WER_DUMP_TYPE *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // r15d
  int v5; // r14d
  int v6; // ebx
  int Dump; // ebx
  int i; // r12d
  unsigned int v9; // esi
  int v10; // r13d
  int PathOfWERTempDirectory; // eax
  BOOL v12; // eax
  int NewRestrictedFileOrDirectorySecurityAttributes; // eax
  bool v14; // zf
  char v15; // al
  enum _WER_DUMP_TYPE v16; // ecx
  int v17; // eax
  const size_t *v18; // rax
  int TempFile; // eax
  wil::details::in1diag3 *v20; // rcx
  int v21; // eax
  char v22; // al
  struct _SECURITY_ATTRIBUTES *v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  void **v26; // [rsp+68h] [rbp-98h] BYREF
  void *v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES v29; // [rsp+80h] [rbp-80h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h]
  __int128 v31; // [rsp+A8h] [rbp-58h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v35[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR v36[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v28 = a3;
  v3 = a2;
  v26 = &CFileByteStream::`vftable';
  v5 = 0;
  v27 = 0;
  v25 = 0;
  SystemTime = 0;
  if ( *this == WerDumpTypeNone )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( !*((_QWORD *)this + 14) && !*((_QWORD *)this + 96) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( !*((_DWORD *)this + 30) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_DWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids, v3);
  if ( *((_DWORD *)this + 42) != 3 )
    goto LABEL_77;
  if ( (this[31] & 1) != 0 )
    goto LABEL_20;
  CRegSetting::CRegSetting((CRegSetting *)&v29);
  v24 = 0;
  if ( (int)CRegSetting::Initialize(&v29, 0, L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug") < 0
    || CRegSetting::Load((CRegSetting *)&v29, HKEY_LOCAL_MACHINE, 0x100u) < 0
    || (v6 = 1, !CRegSetting::GetDwordData((CRegSetting *)&v29)) )
  {
    v6 = 0;
  }
  CRegSetting::~CRegSetting((CRegSetting *)&v29);
  if ( v6 )
  {
LABEL_20:
    CProcessDump::LogTrace((CProcessDump *)this, 1u, L"Heapdump generation disabled by NoHeap flag.");
    Dump = -2147019873;
  }
  else
  {
LABEL_77:
    if ( (unsigned __int8)((__int64 (*)(void))IsXerProgressCallbackPresent)() )
      XerProgressCallback(1);
    for ( i = 0; i < 2; ++i )
    {
      if ( (v3 & 0x10) != 0 || *((int *)this + 44) < 0 )
        v5 = 1;
      if ( i == 1 )
      {
        v5 = 0;
        if ( (v3 & 0x60) != 0x40 || !*((_QWORD *)this + 96) )
          break;
        v9 = v3 & 0xFFFFFF8F | 0x20;
        v10 = 1;
      }
      else
      {
        v10 = 0;
        v9 = v3;
      }
      if ( *((_QWORD *)this + 2) )
      {
        PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v36, 260);
        Dump = PathOfWERTempDirectory;
        if ( PathOfWERTempDirectory < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.",
            (unsigned int)PathOfWERTempDirectory);
          goto LABEL_65;
        }
      }
      v12 = *((_DWORD *)this + 21) || (v3 & 0x80u) != 0;
      *((_DWORD *)this + 21) = v12;
      if ( v5 )
      {
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, 0, v10, v9);
        v5 = 0;
      }
      else
      {
        memset(&v29, 0, sizeof(v29));
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        v29.nLength = 24;
        NewRestrictedFileOrDirectorySecurityAttributes = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                                                           (struct CSecurityAttributes *)&v29,
                                                           0);
        Dump = NewRestrictedFileOrDirectorySecurityAttributes;
        v5 = 0;
        if ( NewRestrictedFileOrDirectorySecurityAttributes < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: Failed to produce security attributes %08X.",
            (unsigned int)NewRestrictedFileOrDirectorySecurityAttributes,
            v24);
          goto LABEL_62;
        }
        if ( !(unsigned __int8)IsXerTransportEventUploadCompletePresent()
          || (v14 = CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 2) + 51680LL)) == 0, v15 = 1, v14) )
        {
          v15 = 0;
        }
        v16 = *((_DWORD *)this + 42);
        if ( v16 == WerDumpTypeHeapDump && v15 && *((_DWORD *)this + 21) )
        {
          GetSystemTime(&SystemTime);
          LODWORD(v24) = SystemTime.wMonth;
          v17 = StringCchPrintfW(
                  v35,
                  0x104u,
                  L"\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u%u%u%u.memory.protected.hdmp",
                  SystemTime.wYear);
          Dump = v17;
          if ( v17 < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Couldn't write out the GameCore specific heap dump file path %08X.",
              (unsigned int)v17,
              v24);
LABEL_62:
            CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v29);
            goto LABEL_65;
          }
          CFileByteStream::OpenFile((CFileByteStream *)&v26, v35, 0xC0000000, 1u, &v29, 1u, 0x20000080u, 0);
        }
        else
        {
          v18 = (const size_t *)CProcessDump::MapDumpFileExtension(v16, v10);
          TempFile = UtilGetTempFile((__int64)&v25, v36, v18, v35, (__int64)v24, &v29, 1u, 0);
          Dump = TempFile;
          if ( TempFile < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Dump file could not be created: UtilGetTempFile %08X.",
              (unsigned int)TempFile,
              v24);
            goto LABEL_62;
          }
          tlx::unique_any<tlx::file_handle_traits>::operator=(&v27, &v25);
        }
        Dump = CProcessDump::GenerateDump((CProcessDump *)this, (struct IWerByteStream *)&v26, v9, v27);
        if ( Dump < 0 )
          goto LABEL_62;
        if ( *((_DWORD *)this + 42) == 3 )
          *(_DWORD *)(*((_QWORD *)this + 2) + 6024LL) = 1;
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, v35, v10, v9);
        CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v29);
      }
      if ( Dump < 0 )
      {
        CProcessDump::LogTrace((CProcessDump *)this, 0, L"Dump could not be added to report: %08X.", (unsigned int)Dump);
        goto LABEL_65;
      }
      *((_DWORD *)this + 1) = 1;
    }
    Dump = 0;
LABEL_65:
    CFileByteStream::Close((CFileByteStream *)&v26);
    if ( Dump >= 0 )
    {
      if ( v35[0] && v28 )
      {
        v22 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v28, v35);
        CProcessDump::LogTrace(
          (CProcessDump *)this,
          0,
          L"Dump path could not be copied: %08X.",
          v22 == 0 ? 0x8007000E : 0);
      }
    }
    else if ( v35[0] )
    {
      v21 = UtilDeleteFilePath(v35);
      v20 = retaddr;
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\processdump.cpp",
          (const char *)(unsigned int)v21,
          (int)v24);
    }
    if ( (unsigned __int8)IsXerProgressCallbackPresent(v20) )
      XerProgressCallback(2);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v26);
  return (unsigned int)Dump;
}

```

## disassembly

```asm
0x18007f818  mov     [rsp-8+arg_18], rbx
0x18007f81d  push    rbp
0x18007f81e  push    rsi
0x18007f81f  push    rdi
0x18007f820  push    r12
0x18007f822  push    r13
0x18007f824  push    r14
0x18007f826  push    r15
0x18007f828  lea     rbp, [rsp-430h]
0x18007f830  sub     rsp, 530h
0x18007f837  mov     rax, cs:__security_cookie
0x18007f83e  xor     rax, rsp
0x18007f841  mov     [rbp+460h+var_40], rax
0x18007f848  mov     [rsp+560h+var_4E8], r8
0x18007f84d  mov     r15d, edx
0x18007f850  mov     rdi, rcx
0x18007f853  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18007f85a  mov     [rsp+560h+var_4F8], rax
0x18007f85f  xor     r14d, r14d
0x18007f862  mov     [rsp+560h+var_4F0], r14
0x18007f867  mov     [rsp+560h+var_500], r14
0x18007f86c  xorps   xmm0, xmm0
0x18007f86f  movups  xmmword ptr [rbp+460h+SystemTime.wYear], xmm0
0x18007f873  cmp     [rcx], r14d
0x18007f876  jnz     short loc_18007F87D
0x18007f878  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f87d  cmp     [rdi+70h], r14
0x18007f881  jnz     short loc_18007F891
0x18007f883  cmp     [rdi+300h], r14
0x18007f88a  jnz     short loc_18007F891
0x18007f88c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f891  cmp     [rdi+78h], r14d
0x18007f895  jnz     short loc_18007F89C
0x18007f897  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f89c  cmp     [rdi+4], r14d
0x18007f8a0  jz      short loc_18007F8A7
0x18007f8a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f8a7  lea     rax, WPP_GLOBAL_Control
0x18007f8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f8b5  cmp     rcx, rax
0x18007f8b8  jz      short loc_18007F8D8
0x18007f8ba  test    byte ptr [rcx+1Ch], 4
0x18007f8be  jz      short loc_18007F8D8
0x18007f8c0  mov     edx, 0Ch
0x18007f8c5  mov     r9d, r15d
0x18007f8c8  lea     r8, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids
0x18007f8cf  mov     rcx, [rcx+10h]
0x18007f8d3  call    WPP_SF_d
0x18007f8d8  cmp     dword ptr [rdi+0A8h], 3
0x18007f8df  jnz     loc_18007F970
0x18007f8e5  test    byte ptr [rdi+7Ch], 1
0x18007f8e9  jnz     short loc_18007F952
0x18007f8eb  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f8ef  call    ??0CRegSetting@@QEAA@XZ; CRegSetting::CRegSetting(void)
0x18007f8f4  mov     [rsp+560h+var_540], r14
0x18007f8f9  lea     r9, aNoheap; "NoHeap"
0x18007f900  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18007f907  xor     edx, edx
0x18007f909  lea     rcx, [rbp+460h+var_4E0]
0x18007f90d  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18007f912  test    eax, eax
0x18007f914  js      short loc_18007F942
0x18007f916  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18007f91d  mov     r8d, 100h; unsigned int
0x18007f923  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f927  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18007f92c  test    eax, eax
0x18007f92e  js      short loc_18007F942
0x18007f930  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f934  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18007f939  test    eax, eax
0x18007f93b  mov     ebx, 1
0x18007f940  jnz     short loc_18007F945
0x18007f942  mov     ebx, r14d
0x18007f945  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f949  call    ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x18007f94e  test    ebx, ebx
0x18007f950  jz      short loc_18007F970
0x18007f952  lea     r8, aHeapdumpGenera; "Heapdump generation disabled by NoHeap "...
0x18007f959  mov     edx, 1; unsigned int
0x18007f95e  mov     rcx, rdi; this
0x18007f961  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007f966  mov     ebx, 8007139Fh
0x18007f96b  jmp     loc_18007FD11
0x18007f970  call    IsXerProgressCallbackPresent
0x18007f975  test    al, al
0x18007f977  jz      short loc_18007F98B
0x18007f979  movsxd  rdx, dword ptr [rdi+0A8h]
0x18007f980  mov     ecx, 1
0x18007f985  call    cs:__imp_XerProgressCallback
0x18007f98b  mov     r12d, r14d
0x18007f98e  cmp     r12d, 2
0x18007f992  jge     loc_18007FC7A
0x18007f998  test    r15b, 10h
0x18007f99c  jnz     short loc_18007F9A7
0x18007f99e  cmp     [rdi+0B0h], r14d
0x18007f9a5  jge     short loc_18007F9AD
0x18007f9a7  mov     r14d, 1
0x18007f9ad  cmp     r12d, 1
0x18007f9b1  jnz     short loc_18007F9DE
0x18007f9b3  mov     eax, r15d
0x18007f9b6  and     al, 60h
0x18007f9b8  xor     r14d, r14d
0x18007f9bb  cmp     al, 40h ; '@'
0x18007f9bd  jnz     loc_18007FC7A
0x18007f9c3  cmp     [rdi+300h], r14
0x18007f9ca  jz      loc_18007FC7A
0x18007f9d0  mov     esi, r15d
0x18007f9d3  and     esi, 0FFFFFFAFh
0x18007f9d6  or      esi, 20h
0x18007f9d9  mov     r13d, r12d
0x18007f9dc  jmp     short loc_18007F9E4
0x18007f9de  xor     r13d, r13d
0x18007f9e1  mov     esi, r15d
0x18007f9e4  cmp     qword ptr [rdi+10h], 0
0x18007f9e9  jz      short loc_18007FA06
0x18007f9eb  mov     edx, 104h
0x18007f9f0  lea     rcx, [rbp+460h+var_250]
0x18007f9f7  call    WerpGetPathOfWERTempDirectory
0x18007f9fc  mov     ebx, eax
0x18007f9fe  test    eax, eax
0x18007fa00  js      loc_18007FC19
0x18007fa06  cmp     dword ptr [rdi+54h], 0
0x18007fa0a  jnz     short loc_18007FA15
0x18007fa0c  test    r15b, r15b
0x18007fa0f  js      short loc_18007FA15
0x18007fa11  xor     eax, eax
0x18007fa13  jmp     short loc_18007FA1A
0x18007fa15  mov     eax, 1
0x18007fa1a  mov     [rdi+54h], eax
0x18007fa1d  test    r14d, r14d
0x18007fa20  jnz     loc_18007FBF1
0x18007fa26  xorps   xmm0, xmm0
0x18007fa29  xor     eax, eax
0x18007fa2b  movups  xmmword ptr [rbp+460h+var_4E0.nLength], xmm0
0x18007fa2f  mov     qword ptr [rbp+460h+var_4E0.bInheritHandle], rax
0x18007fa33  xorps   xmm1, xmm1
0x18007fa36  movups  [rbp+460h+var_4C8], xmm1
0x18007fa3a  movups  [rbp+460h+var_4B8], xmm1
0x18007fa3e  mov     [rbp+460h+var_4A8], rax
0x18007fa42  movdqa  [rbp+460h+var_4A0], xmm0
0x18007fa47  mov     [rbp+460h+var_4E0.nLength], 18h
0x18007fa4e  xor     edx, edx; bool
0x18007fa50  lea     rcx, [rbp+460h+var_4E0]; this
0x18007fa54  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x18007fa59  mov     ebx, eax
0x18007fa5b  xor     r14d, r14d
0x18007fa5e  test    eax, eax
0x18007fa60  js      loc_18007FC44
0x18007fa66  call    IsXerTransportEventUploadCompletePresent
0x18007fa6b  test    al, al
0x18007fa6d  jz      short loc_18007FA85
0x18007fa6f  mov     rcx, [rdi+10h]
0x18007fa73  add     rcx, 0C9E0h; this
0x18007fa7a  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18007fa7f  test    eax, eax
0x18007fa81  mov     al, 1
0x18007fa83  jnz     short loc_18007FA88
0x18007fa85  mov     al, r14b
0x18007fa88  mov     ecx, [rdi+0A8h]; enum _WER_DUMP_TYPE
0x18007fa8e  cmp     ecx, 3
0x18007fa91  jnz     loc_18007FB4D
0x18007fa97  test    al, al
0x18007fa99  jz      loc_18007FB4D
0x18007fa9f  cmp     [rdi+54h], r14d
0x18007faa3  jz      loc_18007FB4D
0x18007faa9  lea     rcx, [rbp+460h+SystemTime]; lpSystemTime
0x18007faad  call    cs:__imp_GetSystemTime
0x18007fab3  movzx   eax, [rbp+460h+SystemTime.wMilliseconds]
0x18007fab7  movzx   ecx, [rbp+460h+SystemTime.wSecond]
0x18007fabb  movzx   edx, [rbp+460h+SystemTime.wMinute]
0x18007fabf  movzx   r8d, [rbp+460h+SystemTime.wHour]
0x18007fac4  movzx   r10d, [rbp+460h+SystemTime.wDay]
0x18007fac9  movzx   r11d, [rbp+460h+SystemTime.wDayOfWeek]
0x18007face  movzx   ebx, [rbp+460h+SystemTime.wMonth]
0x18007fad2  movzx   r9d, [rbp+460h+SystemTime.wYear]
0x18007fad7  mov     [rsp+560h+var_510], eax
0x18007fadb  mov     [rsp+560h+var_518], ecx
0x18007fadf  mov     [rsp+560h+var_520], edx
0x18007fae3  mov     dword ptr [rsp+560h+var_528], r8d
0x18007fae8  mov     [rsp+560h+var_530], r10d
0x18007faed  mov     [rsp+560h+var_538], r11d
0x18007faf2  mov     dword ptr [rsp+560h+var_540], ebx
0x18007faf6  lea     r8, aWerCrashdumpsW; "\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u"...
0x18007fafd  mov     edx, 104h; unsigned __int64
0x18007fb02  lea     rcx, [rbp+460h+var_460]; wchar_t *
0x18007fb06  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007fb0b  mov     ebx, eax
0x18007fb0d  test    eax, eax
0x18007fb0f  js      loc_18007FC32
0x18007fb15  mov     [rsp+560h+var_528], r14; void *
0x18007fb1a  mov     [rsp+560h+var_530], 20000080h; unsigned int
0x18007fb22  mov     ecx, 1
0x18007fb27  mov     [rsp+560h+var_538], ecx; unsigned int
0x18007fb2b  lea     rax, [rbp+460h+var_4E0]
0x18007fb2f  mov     [rsp+560h+var_540], rax; struct _SECURITY_ATTRIBUTES *
0x18007fb34  mov     r9d, ecx; unsigned int
0x18007fb37  mov     r8d, 0C0000000h; unsigned int
0x18007fb3d  lea     rdx, [rbp+460h+var_460]; wchar_t *
0x18007fb41  lea     rcx, [rsp+560h+var_4F8]; this
0x18007fb46  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18007fb4b  jmp     short loc_18007FB9C
0x18007fb4d  mov     edx, r13d; int
0x18007fb50  call    ?MapDumpFileExtension@CProcessDump@@SAPEB_WW4_WER_DUMP_TYPE@@H@Z; CProcessDump::MapDumpFileExtension(_WER_DUMP_TYPE,int)
0x18007fb55  mov     dword ptr [rsp+560h+var_528], r14d
0x18007fb5a  mov     [rsp+560h+var_530], 1
0x18007fb62  lea     rcx, [rbp+460h+var_4E0]
0x18007fb66  mov     qword ptr [rsp+560h+var_538], rcx
0x18007fb6b  lea     r9, [rbp+460h+var_460]
0x18007fb6f  mov     r8, rax
0x18007fb72  lea     rdx, [rbp+460h+var_250]
0x18007fb79  lea     rcx, [rsp+560h+var_500]
0x18007fb7e  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007fb83  mov     ebx, eax
0x18007fb85  test    eax, eax
0x18007fb87  js      loc_18007FC3B
0x18007fb8d  lea     rdx, [rsp+560h+var_500]
0x18007fb92  lea     rcx, [rsp+560h+var_4F0]
0x18007fb97  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18007fb9c  mov     r9, [rsp+560h+var_4F0]; void *
0x18007fba1  mov     r8d, esi; unsigned int
0x18007fba4  lea     rdx, [rsp+560h+var_4F8]; struct IWerByteStream *
0x18007fba9  mov     rcx, rdi; this
0x18007fbac  call    ?GenerateDump@CProcessDump@@AEAAJPEAUIWerByteStream@@KPEAX@Z; CProcessDump::GenerateDump(IWerByteStream *,ulong,void *)
0x18007fbb1  mov     ebx, eax
0x18007fbb3  test    eax, eax
0x18007fbb5  js      loc_18007FC59
0x18007fbbb  cmp     dword ptr [rdi+0A8h], 3
0x18007fbc2  jnz     short loc_18007FBD2
0x18007fbc4  mov     rax, [rdi+10h]
0x18007fbc8  mov     dword ptr [rax+1788h], 1
0x18007fbd2  mov     r9d, esi; unsigned int
0x18007fbd5  mov     r8d, r13d; int
0x18007fbd8  lea     rdx, [rbp+460h+var_460]; wchar_t *
0x18007fbdc  mov     rcx, rdi; this
0x18007fbdf  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x18007fbe4  mov     ebx, eax
0x18007fbe6  lea     rcx, [rbp+460h+var_4E0]; this
0x18007fbea  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18007fbef  jmp     short loc_18007FC06
0x18007fbf1  mov     r9d, esi; unsigned int
0x18007fbf4  mov     r8d, r13d; int
0x18007fbf7  xor     edx, edx; wchar_t *
0x18007fbf9  mov     rcx, rdi; this
0x18007fbfc  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x18007fc01  mov     ebx, eax
0x18007fc03  xor     r14d, r14d
0x18007fc06  test    ebx, ebx
0x18007fc08  js      short loc_18007FC64
0x18007fc0a  mov     dword ptr [rdi+4], 1
0x18007fc11  inc     r12d
0x18007fc14  jmp     loc_18007F98E
0x18007fc19  mov     r9d, eax
0x18007fc1c  lea     r8, aDumpFileCouldN; "Dump file could not be created: WerpGet"...
0x18007fc23  xor     edx, edx; unsigned int
0x18007fc25  mov     rcx, rdi; this
0x18007fc28  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fc2d  xor     r14d, r14d
0x18007fc30  jmp     short loc_18007FC7D
0x18007fc32  lea     r8, aCouldnTWriteOu; "Couldn't write out the GameCore specifi"...
0x18007fc39  jmp     short loc_18007FC4B
0x18007fc3b  lea     r8, aDumpFileCouldN_2; "Dump file could not be created: UtilGet"...
0x18007fc42  jmp     short loc_18007FC4B
0x18007fc44  lea     r8, aDumpFileCouldN_1; "Dump file could not be created: Failed "...
0x18007fc4b  mov     r9d, eax
0x18007fc4e  xor     edx, edx; unsigned int
0x18007fc50  mov     rcx, rdi; this
0x18007fc53  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fc58  nop
0x18007fc59  lea     rcx, [rbp+460h+var_4E0]; this
0x18007fc5d  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18007fc62  jmp     short loc_18007FC7D
0x18007fc64  mov     r9d, ebx
0x18007fc67  lea     r8, aDumpCouldNotBe_0; "Dump could not be added to report: %08X"...
0x18007fc6e  xor     edx, edx; unsigned int
0x18007fc70  mov     rcx, rdi; this
0x18007fc73  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fc78  jmp     short loc_18007FC7D
0x18007fc7a  mov     ebx, r14d
0x18007fc7d  lea     rcx, [rsp+560h+var_4F8]; this
0x18007fc82  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x18007fc87  test    ebx, ebx
0x18007fc89  jns     short loc_18007FCBC
0x18007fc8b  cmp     [rbp+460h+var_460], r14w
0x18007fc90  jz      short loc_18007FCF9
0x18007fc92  lea     rcx, [rbp+460h+var_460]; wchar_t *
0x18007fc96  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18007fc9b  mov     rcx, [rbp+468h]; this
0x18007fca2  test    eax, eax
0x18007fca4  jns     short loc_18007FCF9
0x18007fca6  mov     r9d, eax; char *
0x18007fca9  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werdl"...
0x18007fcb0  mov     edx, 0B10h; void *
0x18007fcb5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007fcba  jmp     short loc_18007FCF9
0x18007fcbc  cmp     [rbp+460h+var_460], r14w
0x18007fcc1  jz      short loc_18007FCF9
0x18007fcc3  mov     rsi, [rsp+560h+var_4E8]
0x18007fcc8  test    rsi, rsi
0x18007fccb  jz      short loc_18007FCF9
  ... truncated ...
```
