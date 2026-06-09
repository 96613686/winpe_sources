# wpc::LogRecorder::LogRecorderChannel::AddLogEntry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18006826c`
- end: `0x180068483`
- name: `?AddLogEntry@LogRecorderChannel@LogRecorder@wpc@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(wpc::LogRecorder::LogRecorderChannel *this)`
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800670c8`
- `0x180067a3c`
- `0x180068154`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x18000bba8`
- `0x18000e8b0`
- `0x18000ecc0`
- `0x18001484c`
- `0x180035240`
- `0x180035e0c`
- `0x180040888`
- `0x180040eb4`
- `0x18006826c`
- `0x180068730`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800682a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800682a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068420`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180068303`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180068303`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wpc::LogRecorder::LogRecorderChannel::AddLogEntry(
        wpc::LogRecorder::LogRecorderChannel *this,
        __int64 a2)
{
  Private::Format *v4; // rsi
  const struct _FILETIME *v5; // rdx
  Private::Format *v6; // rax
  Private::Format *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 v11; // rax
  signed int LastError; // eax
  unsigned int v14; // ebx
  int wHour; // [rsp+20h] [rbp-99h]
  int wMinute; // [rsp+28h] [rbp-91h]
  int wSecond; // [rsp+30h] [rbp-89h]
  FILETIME FileTime; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-69h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-59h] BYREF
  __int64 v21; // [rsp+70h] [rbp-49h]
  __int64 v22; // [rsp+78h] [rbp-41h]
  __int64 v23; // [rsp+80h] [rbp-39h]
  _BYTE pExceptionObject[40]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp-9h] BYREF
  _BYTE v26[40]; // [rsp+D0h] [rbp+17h] BYREF

  v23 = a2;
  DateTime::GetCurrent(v19);
  GetCurrentThreadId();
  SystemTime = 0;
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&SystemTime, L"{0}[{1}] {2}\n", 13);
  v4 = (Private::Format *)StringAlgo::FormatString(v26, &SystemTime);
  SystemTime = 0;
  FileTime = Private::UTCToLocal((Private *)v19, v5);
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f3a944bc79723267707e4fbb78514ff7_Traceguids, v14);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
    throw (ErrorCodeException *)pExceptionObject;
  }
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  StringAlgo::Format(v25, L"%02d/%02d %02d:%02d:%02d", SystemTime.wMonth, SystemTime.wDay, wHour, wMinute, wSecond);
  v6 = (Private::Format *)Private::Format::operator%<std::wstring>(v4);
  v7 = (Private::Format *)Private::Format::operator%<unsigned long>(v6);
  v8 = Private::Format::operator%<std::wstring>(v7);
  std::wstring::wstring(pExceptionObject, v8);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v26);
  v9 = (*(__int64 (__fastcall **)(char *, struct _SYSTEMTIME *))(*((_QWORD *)this + 11) + 48LL))(
         (char *)this + 88,
         &SystemTime);
  std::wstring::append(*(void **)(v9 + 8));
  if ( *(_QWORD *)&SystemTime.wYear )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SystemTime.wYear + 24LL))(*(_QWORD *)&SystemTime.wYear);
  v10 = (__int64 *)*((_QWORD *)this + 17);
  if ( v10 )
  {
    v11 = *v10;
    FileTime = (FILETIME)50000000LL;
    (*(void (__fastcall **)(__int64 *, FILETIME *))(v11 + 24))(v10, &FileTime);
  }
  else
  {
    wpc::LogRecorder::LogRecorderChannel::FlushAndCommit(this);
  }
  std::wstring::~wstring(pExceptionObject);
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x18006826c  mov     [rsp-8+arg_10], rbx
0x180068271  push    rbp
0x180068272  push    rsi
0x180068273  push    rdi
0x180068274  lea     rbp, [rsp-47h]
0x180068279  sub     rsp, 100h
0x180068280  mov     rax, cs:__security_cookie
0x180068287  xor     rax, rsp
0x18006828a  mov     [rbp+57h+var_18], rax
0x18006828e  mov     rdi, rdx
0x180068291  mov     rbx, rcx
0x180068294  mov     [rbp+57h+var_90], rdx
0x180068298  lea     rcx, [rbp+57h+var_C0]
0x18006829c  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x1800682a1  call    cs:__imp_GetCurrentThreadId
0x1800682a7  mov     [rbp+57h+var_D0], eax
0x1800682aa  xorps   xmm0, xmm0
0x1800682ad  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800682b1  mov     [rbp+57h+var_A0], 0
0x1800682b9  mov     [rbp+57h+var_98], 0
0x1800682c1  mov     r8d, 0Dh
0x1800682c7  lea     rdx, a012; "{0}[{1}] {2}\n"
0x1800682ce  lea     rcx, [rbp+57h+SystemTime]
0x1800682d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800682d7  lea     rdx, [rbp+57h+SystemTime]
0x1800682db  lea     rcx, [rbp+57h+var_40]
0x1800682df  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x1800682e4  mov     rsi, rax
0x1800682e7  xorps   xmm0, xmm0
0x1800682ea  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800682ee  lea     rcx, [rbp+57h+var_C0]; this
0x1800682f2  call    ?UTCToLocal@Private@@YA?AU_FILETIME@@AEBU2@@Z; Private::UTCToLocal(_FILETIME const &)
0x1800682f7  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x1800682fb  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800682ff  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180068303  call    cs:__imp_FileTimeToSystemTime
0x180068309  test    eax, eax
0x18006830b  jz      loc_180068420
0x180068311  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x180068315  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x180068319  movzx   edx, [rbp+57h+SystemTime.wHour]
0x18006831d  movzx   r9d, [rbp+57h+SystemTime.wDay]
0x180068322  movzx   r8d, [rbp+57h+SystemTime.wMonth]
0x180068327  mov     [rsp+110h+var_E0], eax
0x18006832b  mov     [rsp+110h+var_E8], ecx
0x18006832f  mov     [rsp+110h+var_F0], edx
0x180068333  lea     rdx, a02d02d02d02d02; "%02d/%02d %02d:%02d:%02d"
0x18006833a  lea     rcx, [rbp+57h+var_60]
0x18006833e  call    ?Format@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; StringAlgo::Format(ushort const *,...)
0x180068343  nop
0x180068344  lea     rdx, [rbp+57h+var_60]
0x180068348  mov     rcx, rsi; this
0x18006834b  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180068350  lea     rdx, [rbp+57h+var_D0]
0x180068354  mov     rcx, rax; this
0x180068357  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x18006835c  mov     rdx, rdi
0x18006835f  mov     rcx, rax; this
0x180068362  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180068367  mov     rdx, rax
0x18006836a  lea     rcx, [rbp+57h+pExceptionObject]
0x18006836e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180068373  nop
0x180068374  lea     rcx, [rbp+57h+var_60]
0x180068378  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006837d  nop
0x18006837e  lea     rcx, [rbp+57h+var_40]
0x180068382  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068387  lea     rcx, [rbx+58h]
0x18006838b  mov     rax, [rcx]
0x18006838e  lea     rdx, [rbp+57h+SystemTime]
0x180068392  mov     rax, [rax+30h]
0x180068396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006839b  nop
0x18006839c  lea     rdx, [rbp+57h+pExceptionObject]
0x1800683a0  mov     rcx, [rax+8]; Src
0x1800683a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800683a9  nop
0x1800683aa  mov     rcx, qword ptr [rbp+57h+SystemTime.wYear]
0x1800683ae  test    rcx, rcx
0x1800683b1  jz      short loc_1800683C0
0x1800683b3  mov     rax, [rcx]
0x1800683b6  mov     rax, [rax+18h]
0x1800683ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683bf  nop
0x1800683c0  mov     rcx, [rbx+88h]
0x1800683c7  test    rcx, rcx
0x1800683ca  jz      short loc_1800683E6
0x1800683cc  mov     rax, [rcx]
0x1800683cf  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 2FAF080h
0x1800683d7  lea     rdx, [rbp+57h+FileTime]
0x1800683db  mov     rax, [rax+18h]
0x1800683df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683e4  jmp     short loc_1800683EF
0x1800683e6  mov     rcx, rbx; this
0x1800683e9  call    ?FlushAndCommit@LogRecorderChannel@LogRecorder@wpc@@AEAAXXZ; wpc::LogRecorder::LogRecorderChannel::FlushAndCommit(void)
0x1800683ee  nop
0x1800683ef  lea     rcx, [rbp+57h+pExceptionObject]
0x1800683f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800683f8  nop
0x1800683f9  mov     rcx, rdi
0x1800683fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068401  mov     rcx, [rbp+57h+var_18]
0x180068405  xor     rcx, rsp; StackCookie
0x180068408  call    __security_check_cookie
0x18006840d  mov     rbx, [rsp+110h+arg_10]
0x180068415  add     rsp, 100h
0x18006841c  pop     rdi
0x18006841d  pop     rsi
0x18006841e  pop     rbp
0x18006841f  retn
0x180068420  call    cs:__imp_GetLastError
0x180068426  nop
0x180068427  mov     ebx, eax
0x180068429  test    eax, eax
0x18006842b  jle     short loc_180068436
0x18006842d  movzx   ebx, ax
0x180068430  or      ebx, 80070000h
0x180068436  lea     rax, WPP_GLOBAL_Control
0x18006843d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068444  cmp     rcx, rax
0x180068447  jz      short loc_180068467
0x180068449  test    byte ptr [rcx+1Ch], 1
0x18006844d  jz      short loc_180068467
0x18006844f  mov     edx, 23h ; '#'
0x180068454  mov     r9d, ebx
0x180068457  lea     r8, WPP_f3a944bc79723267707e4fbb78514ff7_Traceguids
0x18006845e  mov     rcx, [rcx+10h]
0x180068462  call    WPP_SF_d
0x180068467  mov     edx, ebx; int
0x180068469  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18006846d  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180068472  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180068479  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006847d  call    _CxxThrowException_0
```
