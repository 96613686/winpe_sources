# WhesvcUXHandler::WriteDummyFile(void)

- ea: `0x180017834`
- end: `0x180017b0c`
- name: `?WriteDummyFile@WhesvcUXHandler@@AEAAJXZ`
- size: `728`
- prototype: `__int64 __fastcall(WhesvcUXHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001642c`

## callees

- `0x180002c00`
- `0x180003710`
- `0x180007f1c`
- `0x180007f3c`
- `0x18000b524`
- `0x180010058`
- `0x180012c9c`
- `0x1800139b4`
- `0x180013be0`
- `0x180014374`
- `0x180014504`
- `0x180014708`
- `0x180014860`
- `0x180017834`
- `0x180018414`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800179eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800179eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017a49`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017a49`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017887`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017965`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179aa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017887`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017965`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800178a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800178a5`

## string_xrefs

- `0x180017880`: `%TEMP%\whesvc_hotkey_traces`
- `0x180017a08`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180017a93`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180017ad5`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180017935`: `\n	Traces\n		%WINDIR%\Temp\whesvc_hotkey_trace.etl\n		%WINDIR%\Temp\whesvc_hotkey_snap.etl`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::WriteDummyFile(WhesvcUXHandler *this)
{
  __int64 v1; // rax
  __int64 v2; // rax
  const WCHAR *v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // rdx
  LPWSTR v6; // rbx
  unsigned int LastError; // ebx
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  DWORD v10; // eax
  HANDLE FileW; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v18; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR lpDst[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[232]; // [rsp+78h] [rbp-88h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+160h] [rbp+60h] BYREF
  LPCWSTR lpSrc[3]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v24; // [rsp+188h] [rbp+88h]
  _BYTE v25[256]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR Dst[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%TEMP%\\whesvc_hotkey_traces", Dst, 0x104u) - 1 > 0x103 )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)0x80004005LL,
      dwCreationDisposition);
    return LastError;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  memset_0(v25, 0, sizeof(v25));
  dwCreationDispositiona = SystemTime.wMonth;
  _snprintf_s<256>(v25, -1, "%d-%02d-%02d %02d:%02d:%02d (UTC)", SystemTime.wYear);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v20);
  v1 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, L"Traces collected at ");
  v2 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v1, v25);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(
    v2,
    L"\n\tTraces\n\t\t%WINDIR%\\Temp\\whesvc_hotkey_trace.etl\n\t\t%WINDIR%\\Temp\\whesvc_hotkey_snap.etl");
  std::basic_stringbuf<unsigned short>::str(v21, lpSrc);
  v3 = (const WCHAR *)lpSrc;
  if ( v24 > 7 )
    v3 = lpSrc[0];
  v4 = ExpandEnvironmentStringsW(v3, 0, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    lpDst,
    v5,
    v4);
  v6 = lpDst[0];
  if ( lpDst[0] )
  {
    v9 = (const WCHAR *)lpSrc;
    if ( v24 > 7 )
      v9 = lpSrc[0];
    v10 = ExpandEnvironmentStringsW(v9, lpDst[0], v4);
    if ( v10 && v10 <= (unsigned int)v4 )
    {
      FileW = CreateFileW(Dst, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      v18 = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        NumberOfBytesWritten = 0;
        if ( WriteFile(FileW, v6, 2 * v4, &NumberOfBytesWritten, 0) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpDst);
          std::wstring::_Tidy_deallocate(lpSrc);
          std::basic_ostringstream<unsigned short>::`vbase destructor'(v20);
          return 0;
        }
        v13 = 550;
      }
      else
      {
        v13 = 541;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
                    v12);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
      goto LABEL_18;
    }
    LastError = -2147467259;
    v8 = 528;
  }
  else
  {
    LastError = -2147024882;
    v8 = 524;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
    (const char *)LastError,
    dwCreationDispositiona);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpDst);
  std::wstring::_Tidy_deallocate(lpSrc);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v20);
  return LastError;
}

```

## disassembly

```asm
0x180017834  mov     [rsp-8+arg_0], rbx
0x180017839  mov     [rsp-8+arg_8], rdi
0x18001783e  push    rbp
0x18001783f  lea     rbp, [rsp-3B0h]
0x180017847  sub     rsp, 4B0h
0x18001784e  mov     rax, cs:__security_cookie
0x180017855  xor     rax, rsp
0x180017858  mov     [rbp+3B0h+var_10], rax
0x18001785f  xor     edx, edx; Val
0x180017861  mov     r8d, 208h; Size
0x180017867  lea     rcx, [rbp+3B0h+Dst]; void *
0x18001786e  call    memset_0
0x180017873  mov     r8d, 104h; nSize
0x180017879  lea     rdx, [rbp+3B0h+Dst]; lpDst
0x180017880  lea     rcx, Src; "%TEMP%\\whesvc_hotkey_traces"
0x180017887  call    cs:__imp_ExpandEnvironmentStringsW
0x18001788d  dec     eax
0x18001788f  cmp     eax, 103h
0x180017894  ja      loc_180017AC6
0x18001789a  xorps   xmm0, xmm0
0x18001789d  movups  xmmword ptr [rbp+3B0h+SystemTime.wYear], xmm0
0x1800178a1  lea     rcx, [rbp+3B0h+SystemTime]; lpSystemTime
0x1800178a5  call    cs:__imp_GetSystemTime
0x1800178ab  xor     edx, edx; Val
0x1800178ad  mov     r8d, 100h; Size
0x1800178b3  lea     rcx, [rbp+3B0h+var_320]; void *
0x1800178ba  call    memset_0
0x1800178bf  movzx   eax, [rbp+3B0h+SystemTime.wSecond]
0x1800178c3  movzx   ecx, [rbp+3B0h+SystemTime.wMinute]
0x1800178c7  movzx   edx, [rbp+3B0h+SystemTime.wHour]
0x1800178cb  movzx   r8d, [rbp+3B0h+SystemTime.wDay]
0x1800178d0  movzx   r10d, [rbp+3B0h+SystemTime.wMonth]
0x1800178d5  movzx   r9d, [rbp+3B0h+SystemTime.wYear]
0x1800178da  mov     [rsp+4B0h+var_470], eax
0x1800178de  mov     [rsp+4B0h+var_478], ecx
0x1800178e2  mov     dword ptr [rsp+4B0h+hTemplateFile], edx
0x1800178e6  mov     [rsp+4B0h+dwFlagsAndAttributes], r8d
0x1800178eb  mov     [rsp+4B0h+dwCreationDisposition], r10d; int
0x1800178f0  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d (UTC)"
0x1800178f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800178fb  lea     rcx, [rbp+3B0h+var_320]
0x180017902  call    ??$_snprintf_s@$0BAA@@@YAHAEAY0BAA@D_KPEBDZZ; _snprintf_s<256>(char (&)[256],unsigned __int64,char const *,...)
0x180017907  lea     rcx, [rsp+4B0h+var_440]
0x18001790c  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180017911  nop
0x180017912  lea     rdx, aTracesCollecte; "Traces collected at "
0x180017919  lea     rcx, [rsp+4B0h+var_440]
0x18001791e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017923  mov     rcx, rax
0x180017926  lea     rdx, [rbp+3B0h+var_320]
0x18001792d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180017932  mov     rcx, rax
0x180017935  lea     rdx, aTracesWindirTe; "\n\tTraces\n\t\t%WINDIR%\\Temp\\whesvc_"...
0x18001793c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017941  lea     rdx, [rbp+3B0h+lpSrc]
0x180017945  lea     rcx, [rsp+4B0h+var_438]
0x18001794a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18001794f  lea     rcx, [rbp+3B0h+lpSrc]
0x180017953  cmp     [rbp+3B0h+var_328], 7
0x18001795b  cmova   rcx, [rbp+3B0h+lpSrc]; lpSrc
0x180017960  xor     r8d, r8d; nSize
0x180017963  xor     edx, edx; lpDst
0x180017965  call    cs:__imp_ExpandEnvironmentStringsW
0x18001796b  mov     edi, eax
0x18001796d  mov     r8d, eax
0x180017970  lea     rcx, [rsp+4B0h+lpDst]
0x180017975  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001797a  mov     rbx, [rsp+4B0h+lpDst]
0x18001797f  test    rbx, rbx
0x180017982  jnz     short loc_180017993
0x180017984  mov     ebx, 8007000Eh
0x180017989  mov     edx, 20Ch
0x18001798e  jmp     loc_180017A90
0x180017993  lea     rcx, [rbp+3B0h+lpSrc]
0x180017997  cmp     [rbp+3B0h+var_328], 7
0x18001799f  cmova   rcx, [rbp+3B0h+lpSrc]; lpSrc
0x1800179a4  mov     r8d, edi; nSize
0x1800179a7  mov     rdx, rbx; lpDst
0x1800179aa  call    cs:__imp_ExpandEnvironmentStringsW
0x1800179b0  test    eax, eax
0x1800179b2  jz      loc_180017A86
0x1800179b8  cmp     eax, edi
0x1800179ba  ja      loc_180017A86
0x1800179c0  mov     [rsp+4B0h+hTemplateFile], 0; hTemplateFile
0x1800179c9  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800179d1  mov     [rsp+4B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800179d9  xor     r9d, r9d; lpSecurityAttributes
0x1800179dc  xor     r8d, r8d; dwShareMode
0x1800179df  mov     edx, 40000000h; dwDesiredAccess
0x1800179e4  lea     rcx, [rbp+3B0h+Dst]; lpFileName
0x1800179eb  call    cs:__imp_CreateFileW
0x1800179f1  mov     [rsp+4B0h+var_458], rax
0x1800179f6  lea     rcx, [rax+1]
0x1800179fa  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180017a01  jnz     short loc_180017A29
0x180017a03  mov     edx, 21Dh; void *
0x180017a08  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180017a0f  mov     rcx, [rbp+3B8h]; this
0x180017a16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017a1b  mov     ebx, eax
0x180017a1d  lea     rcx, [rsp+4B0h+var_458]
0x180017a22  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017a27  jmp     short loc_180017AA6
0x180017a29  mov     [rsp+4B0h+NumberOfBytesWritten], 0
0x180017a31  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x180017a35  mov     qword ptr [rsp+4B0h+dwCreationDisposition], 0; lpOverlapped
0x180017a3e  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180017a43  mov     rdx, rbx; lpBuffer
0x180017a46  mov     rcx, rax; hFile
0x180017a49  call    cs:__imp_WriteFile
0x180017a4f  test    eax, eax
0x180017a51  jnz     short loc_180017A5A
0x180017a53  mov     edx, 226h
0x180017a58  jmp     short loc_180017A08
0x180017a5a  lea     rcx, [rsp+4B0h+var_458]
0x180017a5f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017a64  lea     rcx, [rsp+4B0h+lpDst]
0x180017a69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180017a6e  lea     rcx, [rbp+3B0h+lpSrc]
0x180017a72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017a77  nop
0x180017a78  lea     rcx, [rsp+4B0h+var_440]
0x180017a7d  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180017a82  xor     eax, eax
0x180017a84  jmp     short loc_180017AE8
0x180017a86  mov     ebx, 80004005h
0x180017a8b  mov     edx, 210h; void *
0x180017a90  mov     r9d, ebx; char *
0x180017a93  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180017a9a  mov     rcx, [rbp+3B8h]; this
0x180017aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017aa6  lea     rcx, [rsp+4B0h+lpDst]
0x180017aab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180017ab0  lea     rcx, [rbp+3B0h+lpSrc]
0x180017ab4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017ab9  nop
0x180017aba  lea     rcx, [rsp+4B0h+var_440]
0x180017abf  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180017ac4  jmp     short loc_180017AE6
0x180017ac6  mov     rcx, [rbp+3B8h]; this
0x180017acd  mov     ebx, 80004005h
0x180017ad2  mov     r9d, ebx; char *
0x180017ad5  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180017adc  mov     edx, 1F8h; void *
0x180017ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ae6  mov     eax, ebx
0x180017ae8  mov     rcx, [rbp+3B0h+var_10]
0x180017aef  xor     rcx, rsp; StackCookie
0x180017af2  call    __security_check_cookie
0x180017af7  lea     r11, [rsp+4B0h+var_s0]
0x180017aff  mov     rbx, [r11+10h]
0x180017b03  mov     rdi, [r11+18h]
0x180017b07  mov     rsp, r11
0x180017b0a  pop     rbp
0x180017b0b  retn
```
