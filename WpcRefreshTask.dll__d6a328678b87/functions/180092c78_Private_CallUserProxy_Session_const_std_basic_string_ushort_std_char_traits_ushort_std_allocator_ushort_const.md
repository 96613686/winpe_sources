# Private::CallUserProxy(Session const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180092c78`
- end: `0x1800933b6`
- name: `?CallUserProxy@Private@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSession@@AEBV23@@Z`
- size: `1854`
- prototype: `void *__fastcall(void *, __int64)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180028950`
- `0x18002a628`
- `0x1800933bc`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x180006ee0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x18000947c`
- `0x180009a18`
- `0x180009a80`
- `0x18000bba8`
- `0x18000ecc0`
- `0x18000ed00`
- `0x18000fef0`
- `0x1800349ac`
- `0x1800354b8`
- `0x180035e0c`
- `0x180059228`
- `0x18005941c`
- `0x180059908`
- `0x18006105c`
- `0x180061d5c`
- `0x1800928fc`
- `0x180092c78`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180092f94`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180092f94`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180092fd8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180092fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800932fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800932fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093359`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180092dd5`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180092dd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009319e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009319e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093203`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180092fc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180092fc1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800930cd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800930cd`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x180092d16`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x180092d16`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall Private::CallUserProxy(void *a1, __int64 a2)
{
  BOOL v4; // ebx
  _BYTE *v5; // rdx
  _BYTE *v6; // rdx
  Private::Format *v7; // rax
  Private::Format *v8; // rax
  __int64 v9; // rax
  LPWSTR *v10; // r9
  WCHAR *v11; // r8
  const WCHAR *v12; // rdx
  char *hThread; // r15
  char *hProcess; // rbx
  char *v15; // rcx
  char *v16; // r12
  char *i; // r14
  char v18; // r9
  unsigned __int64 v19; // rcx
  __int128 *p_Src; // rax
  __int128 *v21; // r9
  __int128 *v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rdx
  signed int v27; // eax
  unsigned int v28; // ebx
  signed int LastError; // eax
  unsigned int v30; // ebx
  signed int v31; // eax
  unsigned int v32; // ebx
  signed int v33; // eax
  unsigned int v34; // ebx
  DWORD NumberOfBytesRead[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ExitCode; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v37; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  HANDLE v45; // [rsp+E0h] [rbp-20h]
  HANDLE v46; // [rsp+E8h] [rbp-18h]
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  __int128 Src; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v49; // [rsp+170h] [rbp+70h]
  unsigned __int64 v50; // [rsp+178h] [rbp+78h]
  LPWSTR lpCommandLine[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v52; // [rsp+198h] [rbp+98h]
  _BYTE pExceptionObject[40]; // [rsp+1A0h] [rbp+A0h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v55[40]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v56[32]; // [rsp+210h] [rbp+110h] BYREF
  void *hReadPipe; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v58[56]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE *v59; // [rsp+270h] [rbp+170h]
  void *hWritePipe; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v61[56]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE *v62; // [rsp+2C0h] [rbp+1C0h]
  _BYTE Buffer[2048]; // [rsp+2D0h] [rbp+1D0h] BYREF

  hToken[0] = a1;
  hObject = 0;
  v37 = 0;
  *(_OWORD *)&PipeAttributes.nLength = 0;
  *(&PipeAttributes.bInheritHandle + 1) = 0;
  PipeAttributes.bInheritHandle = 1;
  PipeAttributes.nLength = 24;
  stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&hWritePipe, &v37);
  stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&hReadPipe, &hObject);
  v4 = CreatePipe(&hReadPipe, &hWritePipe, &PipeAttributes, 0);
  if ( v59 )
  {
    *(_QWORD *)NumberOfBytesRead = hReadPipe;
    (*(void (__fastcall **)(_BYTE *, DWORD *))(*(_QWORD *)v59 + 16LL))(v59, NumberOfBytesRead);
    if ( v59 )
    {
      v5 = v58;
      LOBYTE(v5) = v59 != v58;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v59 + 32LL))(v59, v5);
      v59 = 0;
    }
  }
  if ( v62 )
  {
    *(_QWORD *)NumberOfBytesRead = hWritePipe;
    (*(void (__fastcall **)(_BYTE *, DWORD *))(*(_QWORD *)v62 + 16LL))(v62, NumberOfBytesRead);
    if ( v62 )
    {
      v6 = v61;
      LOBYTE(v6) = v62 != v61;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v62 + 32LL))(v62, v6);
    }
  }
  if ( !v4 )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v55, v30);
    throw (ErrorCodeException *)v55;
  }
  SetHandleInformation(hObject, 1u, 0);
  std::wstring::wstring(v55, L"WpcTok.exe");
  IO::Path::FromKnownFolder(v56, &FOLDERID_System);
  IO::operator/(lpApplicationName, v56, v55);
  std::wstring::~wstring(v56);
  std::wstring::~wstring(v55);
  v42 = 0;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"{0} {1}", 7);
  v7 = (Private::Format *)StringAlgo::FormatString(pExceptionObject, &v42);
  v8 = (Private::Format *)Private::Format::operator%<std::wstring>(v7);
  v9 = Private::Format::operator%<std::wstring>(v8);
  std::wstring::wstring(lpCommandLine, v9);
  std::wstring::~wstring(pExceptionObject);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v10 = lpCommandLine;
    if ( v52 > 7 )
      v10 = (LPWSTR *)lpCommandLine[0];
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v10);
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.hStdError = v37;
  StartupInfo.hStdOutput = v37;
  StartupInfo.dwFlags = 257;
  StartupInfo.wShowWindow = 0;
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Session::GetToken(a2, hToken);
  v11 = (WCHAR *)lpCommandLine;
  if ( v52 > 7 )
    v11 = lpCommandLine[0];
  v12 = (const WCHAR *)lpApplicationName;
  if ( lpApplicationName[3] > (LPCWSTR)7 )
    v12 = lpApplicationName[0];
  if ( !CreateProcessAsUserW(hToken[0], v12, v11, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v31 = GetLastError();
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v32);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v32);
    throw (ErrorCodeException *)pExceptionObject;
  }
  hThread = (char *)ProcessInformation.hThread;
  v45 = ProcessInformation.hThread;
  hProcess = (char *)ProcessInformation.hProcess;
  v46 = ProcessInformation.hProcess;
  ExitCode = 0;
  if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
  {
    v33 = GetLastError();
    v34 = v33;
    if ( v33 > 0 )
      v34 = (unsigned __int16)v33 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v34);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !GetExitCodeProcess(hProcess, &ExitCode) )
  {
    v27 = GetLastError();
    v28 = v27;
    if ( v27 > 0 )
      v28 = (unsigned __int16)v27 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v28);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v28);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, ExitCode);
  v15 = (char *)v37;
  v37 = 0;
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v15);
  Src = 0;
  v49 = 0;
  v50 = 15;
  LOBYTE(Src) = 0;
  while ( 1 )
  {
    NumberOfBytesRead[0] = 0;
    if ( !ReadFile(hObject, Buffer, 0x800u, NumberOfBytesRead, 0) || !NumberOfBytesRead[0] )
      break;
    v16 = &Buffer[NumberOfBytesRead[0]];
    for ( i = Buffer; i != v16; ++i )
    {
      v18 = *i;
      v19 = v49;
      if ( v49 >= v50 )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&Src);
      }
      else
      {
        ++v49;
        p_Src = &Src;
        if ( v50 > 0xF )
          p_Src = (__int128 *)Src;
        *((_BYTE *)p_Src + v19) = v18;
        *((_BYTE *)p_Src + v19 + 1) = 0;
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    v21 = &Src;
    if ( v50 > 0xF )
      v21 = (__int128 *)Src;
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids, v21);
  }
  v22 = &Src;
  if ( v50 > 0xF )
    v22 = (__int128 *)Src;
  *((_BYTE *)v22 + v49) = 0;
  v23 = std::string::string(v55, &Src);
  v24 = (_QWORD *)StringAlgo::Trim<char>(v56, v23);
  if ( v24[3] > 0xFu )
    v24 = (_QWORD *)*v24;
  StringAlgo::ToUnicode(a1, v25, v24);
  std::string::~string(v56);
  std::string::~string(&Src);
  if ( hProcess && (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hProcess);
  if ( hThread && (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hThread);
  if ( (unsigned __int64)hToken[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hToken[0]);
  std::wstring::~wstring(lpCommandLine);
  std::wstring::~wstring(lpApplicationName);
  if ( v37 && (char *)v37 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v37);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a1;
}

```

## disassembly

```asm
0x180092c78  mov     [rsp-8+arg_18], rbx
0x180092c7d  push    rbp
0x180092c7e  push    rsi
0x180092c7f  push    rdi
0x180092c80  push    r12
0x180092c82  push    r13
0x180092c84  push    r14
0x180092c86  push    r15
0x180092c88  lea     rbp, [rsp-9E0h]
0x180092c90  sub     rsp, 0AE0h
0x180092c97  mov     rax, cs:__security_cookie
0x180092c9e  xor     rax, rsp
0x180092ca1  mov     [rbp+0A10h+var_40], rax
0x180092ca8  mov     rdi, r8
0x180092cab  mov     r14, rdx
0x180092cae  mov     r13, rcx
0x180092cb1  mov     [rbp+0A10h+hToken], rcx
0x180092cb5  xor     r12d, r12d
0x180092cb8  mov     [rsp+0B10h+hObject], r12
0x180092cbd  mov     [rsp+0B10h+var_AA0], r12
0x180092cc2  xorps   xmm0, xmm0
0x180092cc5  xor     eax, eax
0x180092cc7  movups  xmmword ptr [rbp+0A10h+PipeAttributes.nLength], xmm0
0x180092ccb  mov     qword ptr [rbp+0A10h+PipeAttributes.bInheritHandle], rax
0x180092ccf  lea     r15d, [r12+1]
0x180092cd4  mov     [rbp+0A10h+PipeAttributes.bInheritHandle], r15d
0x180092cd8  mov     [rbp+0A10h+PipeAttributes.nLength], 18h
0x180092cdf  lea     rdx, [rsp+0B10h+var_AA0]
0x180092ce4  lea     rcx, [rbp+0A10h+hWritePipe]
0x180092ceb  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180092cf0  lea     rdx, [rsp+0B10h+hObject]
0x180092cf5  lea     rcx, [rbp+0A10h+hReadPipe]
0x180092cfc  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x180092d01  xor     r9d, r9d; nSize
0x180092d04  lea     r8, [rbp+0A10h+PipeAttributes]; lpPipeAttributes
0x180092d08  lea     rdx, [rbp+0A10h+hWritePipe]; hWritePipe
0x180092d0f  lea     rcx, [rbp+0A10h+hReadPipe]; hReadPipe
0x180092d16  call    cs:__imp_CreatePipe
0x180092d1c  mov     ebx, eax
0x180092d1e  mov     rcx, [rbp+0A10h+var_8A0]
0x180092d25  test    rcx, rcx
0x180092d28  jz      short loc_180092D73
0x180092d2a  mov     rax, [rbp+0A10h+hReadPipe]
0x180092d31  mov     qword ptr [rsp+0B10h+NumberOfBytesRead], rax
0x180092d36  mov     rax, [rcx]
0x180092d39  lea     rdx, [rsp+0B10h+NumberOfBytesRead]
0x180092d3e  mov     rax, [rax+10h]
0x180092d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d47  mov     rcx, [rbp+0A10h+var_8A0]
0x180092d4e  test    rcx, rcx
0x180092d51  jz      short loc_180092D73
0x180092d53  mov     rax, [rcx]
0x180092d56  lea     rdx, [rbp+0A10h+var_8D8]
0x180092d5d  cmp     rcx, rdx
0x180092d60  setnz   dl
0x180092d63  mov     rax, [rax+20h]
0x180092d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d6c  mov     [rbp+0A10h+var_8A0], r12
0x180092d73  mov     rcx, [rbp+0A10h+var_850]
0x180092d7a  test    rcx, rcx
0x180092d7d  jz      short loc_180092DC2
0x180092d7f  mov     rax, [rbp+0A10h+hWritePipe]
0x180092d86  mov     qword ptr [rsp+0B10h+NumberOfBytesRead], rax
0x180092d8b  mov     rax, [rcx]
0x180092d8e  lea     rdx, [rsp+0B10h+NumberOfBytesRead]
0x180092d93  mov     rax, [rax+10h]
0x180092d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d9c  mov     rcx, [rbp+0A10h+var_850]
0x180092da3  test    rcx, rcx
0x180092da6  jz      short loc_180092DC2
0x180092da8  mov     rax, [rcx]
0x180092dab  lea     rdx, [rbp+0A10h+var_888]
0x180092db2  cmp     rcx, rdx
0x180092db5  setnz   dl
0x180092db8  mov     rax, [rax+20h]
0x180092dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092dc1  nop
0x180092dc2  test    ebx, ebx
0x180092dc4  jz      loc_180093294
0x180092dca  xor     r8d, r8d; dwFlags
0x180092dcd  mov     edx, r15d; dwMask
0x180092dd0  mov     rcx, [rsp+0B10h+hObject]; hObject
0x180092dd5  call    cs:__imp_SetHandleInformation
0x180092ddb  lea     rdx, aWpctokExe; "WpcTok.exe"
0x180092de2  lea     rcx, [rbp+0A10h+var_928]
0x180092de9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180092dee  nop
0x180092def  lea     rdx, FOLDERID_System
0x180092df6  lea     rcx, [rbp+0A10h+var_900]
0x180092dfd  call    ?FromKnownFolder@Path@IO@@SA?AV12@AEBU_GUID@@@Z; IO::Path::FromKnownFolder(_GUID const &)
0x180092e02  nop
0x180092e03  lea     r8, [rbp+0A10h+var_928]
0x180092e0a  lea     rdx, [rbp+0A10h+var_900]
0x180092e11  lea     rcx, [rbp+0A10h+lpApplicationName]
0x180092e18  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x180092e1d  nop
0x180092e1e  lea     rcx, [rbp+0A10h+var_900]
0x180092e25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180092e2a  nop
0x180092e2b  lea     rcx, [rbp+0A10h+var_928]
0x180092e32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180092e37  xorps   xmm0, xmm0
0x180092e3a  movups  [rbp+0A10h+var_A50], xmm0
0x180092e3e  mov     [rbp+0A10h+var_A40], r12
0x180092e42  mov     [rbp+0A10h+var_A38], r12
0x180092e46  mov     r8d, 7
0x180092e4c  lea     rdx, a01_0; "{0} {1}"
0x180092e53  lea     rcx, [rbp+0A10h+var_A50]
0x180092e57  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180092e5c  lea     rdx, [rbp+0A10h+var_A50]
0x180092e60  lea     rcx, [rbp+0A10h+pExceptionObject]
0x180092e67  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x180092e6c  nop
0x180092e6d  lea     rdx, [rbp+0A10h+lpApplicationName]
0x180092e74  mov     rcx, rax; this
0x180092e77  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180092e7c  mov     rdx, rdi
0x180092e7f  mov     rcx, rax; this
0x180092e82  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180092e87  mov     rdx, rax
0x180092e8a  lea     rcx, [rbp+0A10h+lpCommandLine]
0x180092e91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180092e96  nop
0x180092e97  lea     rcx, [rbp+0A10h+pExceptionObject]
0x180092e9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180092ea3  lea     rsi, WPP_GLOBAL_Control
0x180092eaa  lea     rdi, WPP_216598ec635f36e1484cde74c8ed1f5f_Traceguids
0x180092eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180092eb8  cmp     rcx, rsi
0x180092ebb  jz      short loc_180092EEB
0x180092ebd  test    byte ptr [rcx+1Ch], 4
0x180092ec1  jz      short loc_180092EEB
0x180092ec3  lea     r9, [rbp+0A10h+lpCommandLine]
0x180092eca  cmp     [rbp+0A10h+var_978], 7
0x180092ed2  cmova   r9, [rbp+0A10h+lpCommandLine]
0x180092eda  mov     edx, 0Bh
0x180092edf  mov     r8, rdi
0x180092ee2  mov     rcx, [rcx+10h]
0x180092ee6  call    WPP_SF_S
0x180092eeb  mov     ebx, 68h ; 'h'
0x180092ef0  mov     r8d, ebx; Size
0x180092ef3  xor     edx, edx; Val
0x180092ef5  lea     rcx, [rbp+0A10h+StartupInfo]; void *
0x180092ef9  call    memset_0
0x180092efe  mov     rax, [rsp+0B10h+var_AA0]
0x180092f03  mov     [rbp+0A10h+StartupInfo.hStdError], rax
0x180092f07  mov     [rbp+0A10h+StartupInfo.hStdOutput], rax
0x180092f0b  mov     [rbp+0A10h+StartupInfo.dwFlags], 101h
0x180092f12  mov     [rbp+0A10h+StartupInfo.wShowWindow], r12w
0x180092f17  mov     [rbp+0A10h+StartupInfo.cb], ebx
0x180092f1a  xorps   xmm0, xmm0
0x180092f1d  xor     eax, eax
0x180092f1f  movups  xmmword ptr [rbp+0A10h+ProcessInformation.hProcess], xmm0
0x180092f23  mov     qword ptr [rbp+0A10h+ProcessInformation.dwProcessId], rax
0x180092f27  lea     rdx, [rbp+0A10h+hToken]
0x180092f2b  mov     rcx, r14
0x180092f2e  call    ?GetToken@Session@@QEBA?AVToken@@XZ; Session::GetToken(void)
0x180092f33  nop
0x180092f34  lea     r8, [rbp+0A10h+lpCommandLine]
0x180092f3b  cmp     [rbp+0A10h+var_978], 7
0x180092f43  cmova   r8, [rbp+0A10h+lpCommandLine]; lpCommandLine
0x180092f4b  lea     rdx, [rbp+0A10h+lpApplicationName]
0x180092f52  cmp     [rbp+0A10h+var_930], 7
0x180092f5a  cmova   rdx, [rbp+0A10h+lpApplicationName]; lpApplicationName
0x180092f62  lea     rax, [rbp+0A10h+ProcessInformation]
0x180092f66  mov     [rsp+0B10h+lpProcessInformation], rax; lpProcessInformation
0x180092f6b  lea     rax, [rbp+0A10h+StartupInfo]
0x180092f6f  mov     [rsp+0B10h+lpStartupInfo], rax; lpStartupInfo
0x180092f74  mov     [rsp+0B10h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180092f79  mov     [rsp+0B10h+lpEnvironment], r12; lpEnvironment
0x180092f7e  mov     [rsp+0B10h+dwCreationFlags], r12d; dwCreationFlags
0x180092f83  mov     [rsp+0B10h+bInheritHandles], r15d; bInheritHandles
0x180092f88  mov     [rsp+0B10h+lpThreadAttributes], r12; lpThreadAttributes
0x180092f8d  xor     r9d, r9d; lpProcessAttributes
0x180092f90  mov     rcx, [rbp+0A10h+hToken]; hToken
0x180092f94  call    cs:__imp_CreateProcessAsUserW
0x180092f9a  test    eax, eax
0x180092f9c  jz      loc_1800932FC
0x180092fa2  mov     r15, [rbp+0A10h+ProcessInformation.hThread]
0x180092fa6  mov     [rbp+0A10h+var_A30], r15
0x180092faa  mov     rbx, [rbp+0A10h+ProcessInformation.hProcess]
0x180092fae  mov     [rbp+0A10h+var_A28], rbx
0x180092fb2  mov     [rsp+0B10h+ExitCode], r12d
0x180092fb7  or      r14d, 0FFFFFFFFh
0x180092fbb  mov     edx, r14d; dwMilliseconds
0x180092fbe  mov     rcx, rbx; hHandle
0x180092fc1  call    cs:__imp_WaitForSingleObject
0x180092fc7  cmp     eax, r14d
0x180092fca  jz      loc_180093359
0x180092fd0  lea     rdx, [rsp+0B10h+ExitCode]; lpExitCode
0x180092fd5  mov     rcx, rbx; hProcess
0x180092fd8  call    cs:__imp_GetExitCodeProcess
0x180092fde  test    eax, eax
0x180092fe0  jz      loc_180093236
0x180092fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180092fed  cmp     rcx, rsi
0x180092ff0  jz      short loc_18009300E
0x180092ff2  test    byte ptr [rcx+1Ch], 4
0x180092ff6  jz      short loc_18009300E
0x180092ff8  mov     edx, 0Fh
0x180092ffd  mov     r9d, [rsp+0B10h+ExitCode]
0x180093002  mov     r8, rdi
0x180093005  mov     rcx, [rcx+10h]
0x180093009  call    WPP_SF_d
0x18009300e  mov     rcx, [rsp+0B10h+var_AA0]; hObject
0x180093013  mov     [rsp+0B10h+var_AA0], r12
0x180093018  lea     rax, [rcx-1]
0x18009301c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180093020  ja      short loc_180093028
0x180093022  call    cs:__imp_CloseHandle
0x180093028  xorps   xmm0, xmm0
0x18009302b  movups  [rbp+0A10h+Src], xmm0
0x18009302f  mov     [rbp+0A10h+var_9A0], r12
0x180093033  mov     [rbp+0A10h+var_998], 0Fh
0x18009303b  mov     byte ptr [rbp+0A10h+Src], r12b
0x18009303f  jmp     short loc_1800930AC
0x180093041  mov     eax, [rsp+0B10h+NumberOfBytesRead]
0x180093045  test    eax, eax
0x180093047  jz      loc_1800930DB
0x18009304d  lea     r12, [rbp+0A10h+Buffer]
0x180093054  add     r12, rax
0x180093057  lea     r14, [rbp+0A10h+Buffer]
0x18009305e  lea     rax, [rbp+0A10h+Buffer]
0x180093065  cmp     rax, r12
0x180093068  jz      short loc_1800930A9
0x18009306a  mov     r9b, [r14]
0x18009306d  mov     rcx, [rbp+0A10h+var_9A0]
0x180093071  cmp     rcx, [rbp+0A10h+var_998]
0x180093075  jnb     short loc_180093098
0x180093077  lea     rax, [rcx+1]
0x18009307b  mov     [rbp+0A10h+var_9A0], rax
0x18009307f  lea     rax, [rbp+0A10h+Src]
0x180093083  cmp     [rbp+0A10h+var_998], 0Fh
0x180093088  cmova   rax, qword ptr [rbp+0A10h+Src]
0x18009308d  mov     [rax+rcx], r9b
0x180093091  mov     byte ptr [rax+rcx+1], 0
0x180093096  jmp     short loc_1800930A1
0x180093098  lea     rcx, [rbp+0A10h+Src]; Src
0x18009309c  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x1800930a1  inc     r14
0x1800930a4  cmp     r14, r12
0x1800930a7  jnz     short loc_18009306A
0x1800930a9  xor     r12d, r12d
0x1800930ac  mov     [rsp+0B10h+lpThreadAttributes], r12; lpOverlapped
0x1800930b1  mov     [rsp+0B10h+NumberOfBytesRead], r12d
0x1800930b6  lea     r9, [rsp+0B10h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800930bb  mov     r8d, 800h; nNumberOfBytesToRead
0x1800930c1  lea     rdx, [rbp+0A10h+Buffer]; lpBuffer
0x1800930c8  mov     rcx, [rsp+0B10h+hObject]; hFile
0x1800930cd  call    cs:__imp_ReadFile
0x1800930d3  test    eax, eax
0x1800930d5  jnz     loc_180093041
0x1800930db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800930e2  cmp     rcx, rsi
0x1800930e5  jz      short loc_18009310C
0x1800930e7  test    byte ptr [rcx+1Ch], 8
0x1800930eb  jz      short loc_18009310C
0x1800930ed  lea     r9, [rbp+0A10h+Src]
0x1800930f1  cmp     [rbp+0A10h+var_998], 0Fh
0x1800930f6  cmova   r9, qword ptr [rbp+0A10h+Src]
0x1800930fb  mov     edx, 10h
0x180093100  mov     r8, rdi
0x180093103  mov     rcx, [rcx+10h]
0x180093107  call    WPP_SF_s
0x18009310c  mov     rcx, [rbp+0A10h+var_9A0]
0x180093110  mov     [rbp+0A10h+var_9A0], rcx
0x180093114  lea     rax, [rbp+0A10h+Src]
0x180093118  cmp     [rbp+0A10h+var_998], 0Fh
0x18009311d  cmova   rax, qword ptr [rbp+0A10h+Src]
0x180093122  mov     [rax+rcx], r12b
0x180093126  lea     rdx, [rbp+0A10h+Src]
0x18009312a  lea     rcx, [rbp+0A10h+var_928]
0x180093131  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180093136  mov     rdx, rax
0x180093139  lea     rcx, [rbp+0A10h+var_900]
0x180093140  call    ??$Trim@D@StringAlgo@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@Z; StringAlgo::Trim<char>(std::string)
0x180093145  nop
0x180093146  cmp     qword ptr [rax+18h], 0Fh
0x18009314b  jbe     short loc_180093150
0x18009314d  mov     rax, [rax]
0x180093150  mov     r8, rax
0x180093153  mov     rcx, r13
0x180093156  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEBDH@Z; StringAlgo::ToUnicode(int,char const *,int)
0x18009315b  nop
0x18009315c  lea     rcx, [rbp+0A10h+var_900]
0x180093163  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180093168  nop
0x180093169  lea     rcx, [rbp+0A10h+Src]
0x18009316d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180093172  nop
0x180093173  test    rbx, rbx
0x180093176  jz      short loc_18009318C
0x180093178  lea     rax, [rbx-1]
0x18009317c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180093180  ja      short loc_18009318C
0x180093182  mov     rcx, rbx; hObject
0x180093185  call    cs:__imp_CloseHandle
0x18009318b  nop
0x18009318c  test    r15, r15
0x18009318f  jz      short loc_1800931A5
  ... truncated ...
```
