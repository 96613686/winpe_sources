# CKernelHangReport::_CollectKernelDump(void)

- ea: `0x140027624`
- end: `0x140027d10`
- name: `?_CollectKernelDump@CKernelHangReport@@AEAAJXZ`
- size: `1772`
- prototype: `__int64 __fastcall(CKernelHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x140027d30`

## callees

- `0x140002470`
- `0x140002728`
- `0x140004198`
- `0x1400041bc`
- `0x140004230`
- `0x140004300`
- `0x14000b540`
- `0x14000d28c`
- `0x14001444c`
- `0x140014474`
- `0x140014ddc`
- `0x14001af10`
- `0x140020364`
- `0x140027624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140027829`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140027829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027c8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400276d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400276d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140027ca2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140027ca2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140027a22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140027a22`
- `ntdll!RtlNtStatusToDosError` at `0x1400278df`
- `ntdll!RtlNtStatusToDosError` at `0x1400278df`
- `ntdll!NtSystemDebugControl` at `0x1400278d3`
- `ntdll!NtSystemDebugControl` at `0x1400278d3`
- `wer!WerpAddFile` at `0x140027acc`
- `wer!WerpAddFile` at `0x140027acc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CKernelHangReport::_CollectKernelDump(CKernelHangReport *this)
{
  void **v2; // r15
  _DWORD *v3; // rbx
  HANDLE v4; // r14
  int ProcessThreads; // eax
  const struct std::nothrow_t *v6; // rdx
  int v7; // edi
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r12
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  _QWORD *v15; // rax
  CUserModeHangReport *v16; // rax
  unsigned int i; // ebx
  DWORD ThreadId; // eax
  int v19; // eax
  signed int v20; // eax
  int TempFile; // eax
  CUserModeHangReport *v22; // rcx
  __int64 v23; // rdx
  signed int LastError; // eax
  void *v25; // rcx
  int v26; // eax
  __int64 j; // rcx
  CUserModeHangReport *v28; // rcx
  __int64 v29; // rdx
  __int64 OutputBufferLength; // [rsp+20h] [rbp-E0h]
  ULONG nNumberOfBytesToWrite; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  __int128 InputBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+78h] [rbp-88h]
  void **v39; // [rsp+88h] [rbp-78h]
  void **v40; // [rsp+90h] [rbp-70h]
  _DWORD *v41; // [rsp+98h] [rbp-68h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v43[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = 0;
  v40 = 0;
  v33 = 0;
  v3 = 0;
  v41 = 0;
  v4 = 0;
  hFile = 0;
  InputBuffer = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  NumberOfBytesWritten = 0;
  nNumberOfBytesToWrite = 0;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
      **((unsigned int **)this + 2988));
  }
  FileName[0] = 0;
  v43[0] = 0;
  GetTickCount();
  ProcessThreads = GetProcessThreads(**((_DWORD **)this + 2988), 0, 0, 0, &v33);
  v7 = ProcessThreads;
  if ( ProcessThreads < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 11;
LABEL_8:
      v10 = (unsigned int)ProcessThreads;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, v10);
      goto LABEL_91;
    }
    goto LABEL_91;
  }
  v11 = v33;
  v12 = 8LL * v33;
  if ( !is_mul_ok(v33, 8u) )
    v12 = -1;
  v13 = __CFADD__(v12, 8);
  v14 = v12 + 8;
  if ( v13 )
    v14 = -1;
  v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 )
  {
    *v15 = v11;
    v2 = (void **)(v15 + 1);
    `eh vector constructor iterator'(
      v15 + 1,
      8u,
      (unsigned int)v11,
      utl::unique_ptr<IWERPlugIn,utl::default_delete<IWERPlugIn>>::unique_ptr<IWERPlugIn,utl::default_delete<IWERPlugIn>>,
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  }
  else
  {
    v2 = 0;
  }
  v40 = v2;
  if ( !v2 )
  {
    v7 = -2147024882;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_91;
    }
    v29 = 12;
LABEL_90:
    WPP_SF_(*((_QWORD *)v28 + 2), v29, &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids);
    goto LABEL_91;
  }
  v7 = GetProcessThreads(**((_DWORD **)this + 2988), 0x1FFFFFu, v2, v11, 0);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_91;
    }
    v9 = 13;
    goto LABEL_22;
  }
  v16 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    for ( i = 0; i < (unsigned int)v11; ++i )
    {
      if ( v16 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
      {
        ThreadId = GetThreadId(v2[i]);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, ThreadId);
        v16 = WPP_GLOBAL_Control;
      }
    }
  }
  v3 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
  v41 = v3;
  if ( !v3 )
  {
    v7 = -2147024882;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_91;
    }
    v29 = 15;
    goto LABEL_90;
  }
  v37 = 0;
  *(_QWORD *)&v38 = 0;
  *(_QWORD *)&InputBuffer = 0x1F500000001LL;
  *((_QWORD *)&InputBuffer + 1) = 1;
  DWORD2(v38) = 0;
  HIDWORD(v38) = v11;
  v39 = v2;
  v19 = NtSystemDebugControl(SysDbgGetTriageDump, &InputBuffer, 0x38u, v3, 0x100000u, &nNumberOfBytesToWrite);
  if ( v19 < 0 )
  {
    v20 = RtlNtStatusToDosError(v19);
    v7 = v20;
    if ( v20 > 0 )
      v7 = (unsigned __int16)v20 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_91;
    }
    v9 = 16;
    goto LABEL_22;
  }
  if ( nNumberOfBytesToWrite > 0x100000 )
  {
    v7 = -2147024785;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
        nNumberOfBytesToWrite);
    }
    goto LABEL_91;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
      nNumberOfBytesToWrite);
  }
  TempFile = UtilGetTempFile(&hFile, 0, (__int64)L"atk.kdmp", FileName, OutputBufferLength, 0, 0, 0);
  v7 = TempFile;
  if ( TempFile < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v23 = 19;
LABEL_44:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, (unsigned int)TempFile);
LABEL_45:
    v4 = hFile;
    goto LABEL_91;
  }
  TempFile = StringCchPrintfW(v43, 0x104u, L"%s.%s", *((_QWORD *)this + 3054) + 256LL, L"atk.kdmp");
  v7 = TempFile;
  if ( TempFile < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v23 = 20;
    goto LABEL_44;
  }
  v4 = hFile;
  if ( !WriteFile(hFile, v3, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_91;
    }
    v9 = 21;
LABEL_22:
    v10 = (unsigned int)v7;
    goto LABEL_9;
  }
  v25 = v4;
  v4 = 0;
  if ( (unsigned __int64)v25 + 1 > 1 )
    CloseHandle(v25);
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, FileName);
  }
  ProcessThreads = WerpAddFile(*((_QWORD *)this + 3055), FileName, 5);
  v7 = ProcessThreads;
  if ( ProcessThreads >= 0 )
  {
    v26 = CHangReport::_AddFileToList(this, v43, **((unsigned int **)this + 2988), 2);
    if ( v26 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
        (unsigned int)v26);
    }
    if ( nNumberOfBytesToWrite >= 0x1000 && *v3 == 1162297680 && v3[1] == 1347245380 )
    {
      *((_DWORD *)this + 6228) = v3[10];
      for ( j = 0; j != 4; ++j )
        *((_QWORD *)this + j + 3115) = (unsigned int)v3[j + 11];
      *((_BYTE *)this + 24952) = 32;
    }
    else if ( nNumberOfBytesToWrite >= 0x2000 && *v3 == 1162297680 && v3[1] == 875976004 )
    {
      *((_DWORD *)this + 6228) = v3[14];
      *((_QWORD *)this + 3115) = *((_QWORD *)v3 + 8);
      *((_QWORD *)this + 3116) = *((_QWORD *)v3 + 9);
      *((_QWORD *)this + 3117) = *((_QWORD *)v3 + 10);
      *((_QWORD *)this + 3118) = *((_QWORD *)v3 + 11);
      *((_BYTE *)this + 24952) = 64;
    }
    else
    {
      *((_BYTE *)this + 24952) = 0;
    }
    v7 = 0;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 23;
      goto LABEL_8;
    }
  }
LABEL_91:
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  if ( v7 < 0 && FileName[0] )
    DeleteFileW(FileName);
  if ( v3 )
    operator delete(v3, v6);
  if ( v2 )
  {
    `eh vector destructor iterator'(
      v2,
      8u,
      (unsigned __int64)*(v2 - 1),
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
    operator delete[](v2 - 1, 8LL * (_QWORD)*(v2 - 1) + 8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027624  push    rbp
0x140027626  push    rbx
0x140027627  push    rsi
0x140027628  push    rdi
0x140027629  push    r12
0x14002762b  push    r13
0x14002762d  push    r14
0x14002762f  push    r15
0x140027631  lea     rbp, [rsp-3D8h]
0x140027639  sub     rsp, 4D8h
0x140027640  mov     rax, cs:__security_cookie
0x140027647  xor     rax, rsp
0x14002764a  mov     [rbp+410h+var_50], rax
0x140027651  mov     rsi, rcx
0x140027654  xor     r13d, r13d
0x140027657  mov     r15d, r13d
0x14002765a  mov     [rbp+410h+var_480], r13
0x14002765e  mov     [rsp+510h+var_4CC], r13d
0x140027663  mov     ebx, r13d
0x140027666  mov     [rbp+410h+var_478], rbx
0x14002766a  mov     r14d, r13d
0x14002766d  mov     [rsp+510h+hFile], r13
0x140027672  xorps   xmm0, xmm0
0x140027675  xor     eax, eax
0x140027677  movups  [rsp+510h+InputBuffer], xmm0
0x14002767c  movups  [rsp+510h+var_4A8], xmm0
0x140027681  movups  [rsp+510h+var_498], xmm0
0x140027686  mov     [rbp+410h+var_488], rax
0x14002768a  mov     [rsp+510h+NumberOfBytesWritten], r13d
0x14002768f  mov     [rsp+510h+nNumberOfBytesToWrite], r13d
0x140027694  lea     r12, WPP_GLOBAL_Control
0x14002769b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400276a2  cmp     rcx, r12
0x1400276a5  jz      short loc_1400276CA
0x1400276a7  test    byte ptr [rcx+1Ch], 4
0x1400276ab  jz      short loc_1400276CA
0x1400276ad  mov     r9, [rsi+5D60h]
0x1400276b4  lea     edx, [rax+0Ah]
0x1400276b7  mov     r9d, [r9]
0x1400276ba  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x1400276c1  mov     rcx, [rcx+10h]
0x1400276c5  call    WPP_SF_d
0x1400276ca  mov     [rbp+410h+FileName], r13w
0x1400276cf  mov     [rbp+410h+var_260], r13w
0x1400276d7  call    cs:__imp_GetTickCount
0x1400276dd  mov     rcx, [rsi+5D60h]
0x1400276e4  lea     rax, [rsp+510h+var_4CC]
0x1400276e9  mov     qword ptr [rsp+510h+OutputBufferLength], rax; unsigned int *
0x1400276ee  xor     r9d, r9d; unsigned int
0x1400276f1  xor     r8d, r8d; void **
0x1400276f4  xor     edx, edx; unsigned int
0x1400276f6  mov     ecx, [rcx]; unsigned int
0x1400276f8  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x1400276fd  mov     edi, eax
0x1400276ff  test    eax, eax
0x140027701  jns     short loc_14002773A
0x140027703  mov     rcx, cs:WPP_GLOBAL_Control
0x14002770a  cmp     rcx, r12
0x14002770d  jz      loc_140027C80
0x140027713  test    byte ptr [rcx+1Ch], 1
0x140027717  jz      loc_140027C80
0x14002771d  mov     edx, 0Bh
0x140027722  mov     r9d, eax
0x140027725  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x14002772c  mov     rcx, [rcx+10h]
0x140027730  call    WPP_SF_d
0x140027735  jmp     loc_140027C80
0x14002773a  mov     r12d, [rsp+510h+var_4CC]
0x14002773f  mov     eax, 8
0x140027744  mul     r12
0x140027747  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002774e  cmovb   rax, rcx
0x140027752  add     rax, 8
0x140027756  cmovb   rax, rcx
0x14002775a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140027761  mov     rcx, rax; unsigned __int64
0x140027764  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140027769  test    rax, rax
0x14002776c  jz      short loc_14002779A
0x14002776e  mov     [rax], r12
0x140027771  lea     r15, [rax+8]
0x140027775  lea     rax, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x14002777c  mov     qword ptr [rsp+510h+OutputBufferLength], rax; void (*)(void *)
0x140027781  lea     r9, ??0?$unique_ptr@VIWERPlugIn@@U?$default_delete@VIWERPlugIn@@@utl@@@utl@@QEAA@XZ; void (*)(void *)
0x140027788  mov     r8d, r12d; unsigned __int64
0x14002778b  mov     edx, 8; unsigned __int64
0x140027790  mov     rcx, r15; void *
0x140027793  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140027798  jmp     short loc_14002779D
0x14002779a  mov     r15, r13
0x14002779d  mov     [rbp+410h+var_480], r15
0x1400277a1  test    r15, r15
0x1400277a4  jz      loc_140027C4D
0x1400277aa  mov     rcx, [rsi+5D60h]
0x1400277b1  mov     qword ptr [rsp+510h+OutputBufferLength], r13; unsigned int *
0x1400277b6  mov     r9d, r12d; unsigned int
0x1400277b9  mov     r8, r15; void **
0x1400277bc  mov     edx, 1FFFFFh; unsigned int
0x1400277c1  mov     ecx, [rcx]; unsigned int
0x1400277c3  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x1400277c8  mov     edi, eax
0x1400277ca  test    eax, eax
0x1400277cc  jns     short loc_1400277FC
0x1400277ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400277d5  lea     rax, WPP_GLOBAL_Control
0x1400277dc  cmp     rcx, rax
0x1400277df  jz      loc_140027C80
0x1400277e5  test    byte ptr [rcx+1Ch], 1
0x1400277e9  jz      loc_140027C80
0x1400277ef  mov     edx, 0Dh
0x1400277f4  mov     r9d, edi
0x1400277f7  jmp     loc_140027725
0x1400277fc  mov     rax, cs:WPP_GLOBAL_Control
0x140027803  test    byte ptr [rax+1Ch], 4
0x140027807  jz      short loc_14002785C
0x140027809  mov     ebx, r13d
0x14002780c  test    r12d, r12d
0x14002780f  jz      short loc_14002785C
0x140027811  lea     rdi, WPP_GLOBAL_Control
0x140027818  cmp     rax, rdi
0x14002781b  jz      short loc_140027855
0x14002781d  test    byte ptr [rax+1Ch], 4
0x140027821  jz      short loc_140027855
0x140027823  mov     ecx, ebx
0x140027825  mov     rcx, [r15+rcx*8]; Thread
0x140027829  call    cs:__imp_GetThreadId
0x14002782f  mov     edx, 0Eh
0x140027834  mov     r9d, eax
0x140027837  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x14002783e  mov     rcx, cs:WPP_GLOBAL_Control
0x140027845  mov     rcx, [rcx+10h]
0x140027849  call    WPP_SF_d
0x14002784e  mov     rax, cs:WPP_GLOBAL_Control
0x140027855  inc     ebx
0x140027857  cmp     ebx, r12d
0x14002785a  jb      short loc_140027818
0x14002785c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140027863  mov     edi, 100000h
0x140027868  mov     ecx, edi; unsigned __int64
0x14002786a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002786f  mov     rbx, rax
0x140027872  mov     [rbp+410h+var_478], rax
0x140027876  test    rax, rax
0x140027879  jz      loc_140027C28
0x14002787f  xorps   xmm0, xmm0
0x140027882  movups  [rsp+510h+InputBuffer], xmm0
0x140027887  movups  [rsp+510h+var_4A8], xmm0
0x14002788c  movups  [rsp+510h+var_498], xmm0
0x140027891  mov     eax, 1
0x140027896  mov     dword ptr [rsp+510h+InputBuffer], eax
0x14002789a  mov     dword ptr [rsp+510h+InputBuffer+4], 1F5h
0x1400278a2  mov     qword ptr [rsp+510h+InputBuffer+8], rax
0x1400278a7  mov     dword ptr [rbp+410h+var_498+8], r13d
0x1400278ab  mov     dword ptr [rbp+410h+var_498+0Ch], r12d
0x1400278af  mov     [rbp+410h+var_488], r15
0x1400278b3  lea     rax, [rsp+510h+nNumberOfBytesToWrite]
0x1400278b8  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x1400278bd  mov     [rsp+510h+OutputBufferLength], edi; OutputBufferLength
0x1400278c1  mov     r9, rbx; OutputBuffer
0x1400278c4  mov     r8d, 38h ; '8'; InputBufferLength
0x1400278ca  lea     rdx, [rsp+510h+InputBuffer]; InputBuffer
0x1400278cf  lea     ecx, [r8-1Bh]; ControlCode
0x1400278d3  call    cs:__imp_NtSystemDebugControl
0x1400278d9  test    eax, eax
0x1400278db  jns     short loc_14002791F
0x1400278dd  mov     ecx, eax; Status
0x1400278df  call    cs:__imp_RtlNtStatusToDosError
0x1400278e5  mov     edi, eax
0x1400278e7  test    eax, eax
0x1400278e9  jle     short loc_1400278F4
0x1400278eb  movzx   edi, ax
0x1400278ee  or      edi, 80070000h
0x1400278f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400278fb  lea     rax, WPP_GLOBAL_Control
0x140027902  cmp     rcx, rax
0x140027905  jz      loc_140027C80
0x14002790b  test    byte ptr [rcx+1Ch], 1
0x14002790f  jz      loc_140027C80
0x140027915  mov     edx, 10h
0x14002791a  jmp     loc_1400277F4
0x14002791f  mov     r9d, [rsp+510h+nNumberOfBytesToWrite]
0x140027924  cmp     r9d, edi
0x140027927  ja      loc_140027BF3
0x14002792d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027934  lea     r12, WPP_GLOBAL_Control
0x14002793b  cmp     rcx, r12
0x14002793e  jz      short loc_14002795B
0x140027940  test    byte ptr [rcx+1Ch], 4
0x140027944  jz      short loc_14002795B
0x140027946  mov     edx, 12h
0x14002794b  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x140027952  mov     rcx, [rcx+10h]
0x140027956  call    WPP_SF_d
0x14002795b  mov     [rsp+510h+var_4D8], r13d
0x140027960  mov     [rsp+510h+var_4E0], r13d
0x140027965  mov     [rsp+510h+ReturnLength], r13
0x14002796a  lea     r9, [rbp+410h+FileName]
0x14002796e  lea     r14, aAtkKdmp; "atk.kdmp"
0x140027975  mov     r8, r14
0x140027978  xor     edx, edx
0x14002797a  lea     rcx, [rsp+510h+hFile]
0x14002797f  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140027984  mov     edi, eax
0x140027986  test    eax, eax
0x140027988  jns     short loc_1400279BE
0x14002798a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027991  cmp     rcx, r12
0x140027994  jz      short loc_1400279B4
0x140027996  test    byte ptr [rcx+1Ch], 1
0x14002799a  jz      short loc_1400279B4
0x14002799c  mov     edx, 13h
0x1400279a1  mov     r9d, eax
0x1400279a4  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x1400279ab  mov     rcx, [rcx+10h]
0x1400279af  call    WPP_SF_d
0x1400279b4  mov     r14, [rsp+510h+hFile]
0x1400279b9  jmp     loc_140027C80
0x1400279be  mov     r9, [rsi+5F70h]
0x1400279c5  add     r9, 100h
0x1400279cc  mov     qword ptr [rsp+510h+OutputBufferLength], r14
0x1400279d1  lea     r8, aSS; "%s.%s"
0x1400279d8  mov     edx, 104h; unsigned __int64
0x1400279dd  lea     rcx, [rbp+410h+var_260]; wchar_t *
0x1400279e4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400279e9  mov     edi, eax
0x1400279eb  test    eax, eax
0x1400279ed  jns     short loc_140027A08
0x1400279ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400279f6  cmp     rcx, r12
0x1400279f9  jz      short loc_1400279B4
0x1400279fb  test    byte ptr [rcx+1Ch], 1
0x1400279ff  jz      short loc_1400279B4
0x140027a01  mov     edx, 14h
0x140027a06  jmp     short loc_1400279A1
0x140027a08  mov     qword ptr [rsp+510h+OutputBufferLength], r13; lpOverlapped
0x140027a0d  lea     r9, [rsp+510h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140027a12  mov     r8d, [rsp+510h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140027a17  mov     rdx, rbx; lpBuffer
0x140027a1a  mov     r14, [rsp+510h+hFile]
0x140027a1f  mov     rcx, r14; hFile
0x140027a22  call    cs:__imp_WriteFile
0x140027a28  test    eax, eax
0x140027a2a  jnz     short loc_140027A65
0x140027a2c  call    cs:__imp_GetLastError
0x140027a32  mov     edi, eax
0x140027a34  test    eax, eax
0x140027a36  jle     short loc_140027A41
0x140027a38  movzx   edi, ax
0x140027a3b  or      edi, 80070000h
0x140027a41  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a48  cmp     rcx, r12
0x140027a4b  jz      loc_140027C80
0x140027a51  test    byte ptr [rcx+1Ch], 1
0x140027a55  jz      loc_140027C80
0x140027a5b  mov     edx, 15h
0x140027a60  jmp     loc_1400277F4
0x140027a65  mov     rcx, r14; hObject
0x140027a68  mov     r14, r13
0x140027a6b  lea     rax, [rcx+1]
0x140027a6f  cmp     rax, 1
0x140027a73  jbe     short loc_140027A7B
0x140027a75  call    cs:__imp_CloseHandle
0x140027a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a82  cmp     rcx, r12
0x140027a85  jz      short loc_140027AA6
0x140027a87  test    byte ptr [rcx+1Ch], 4
0x140027a8b  jz      short loc_140027AA6
0x140027a8d  mov     edx, 16h
0x140027a92  lea     r9, [rbp+410h+FileName]
0x140027a96  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x140027a9d  mov     rcx, [rcx+10h]
0x140027aa1  call    WPP_SF_S
0x140027aa6  mov     [rsp+510h+ReturnLength], r13
0x140027aab  lea     rax, [rbp+410h+var_260]
0x140027ab2  mov     qword ptr [rsp+510h+OutputBufferLength], rax
0x140027ab7  mov     r9d, 1
0x140027abd  lea     r8d, [r9+4]
0x140027ac1  lea     rdx, [rbp+410h+FileName]
0x140027ac5  mov     rcx, [rsi+5F78h]
0x140027acc  call    cs:__imp_WerpAddFile
0x140027ad2  mov     edi, eax
0x140027ad4  test    eax, eax
0x140027ad6  jns     short loc_140027AFC
0x140027ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x140027adf  cmp     rcx, r12
0x140027ae2  jz      loc_140027C80
0x140027ae8  test    byte ptr [rcx+1Ch], 1
0x140027aec  jz      loc_140027C80
0x140027af2  mov     edx, 17h
0x140027af7  jmp     loc_140027722
0x140027afc  mov     r8, [rsi+5D60h]
0x140027b03  mov     r9d, 2
0x140027b09  mov     r8d, [r8]
0x140027b0c  lea     rdx, [rbp+410h+var_260]
0x140027b13  mov     rcx, rsi
0x140027b16  call    ?_AddFileToList@CHangReport@@IEAAJPEB_WKW4FAULTREP_CROSSPROCESS_FILE_TYPE@@@Z; CHangReport::_AddFileToList(wchar_t const *,ulong,FAULTREP_CROSSPROCESS_FILE_TYPE)
0x140027b1b  test    eax, eax
0x140027b1d  jns     short loc_140027B49
0x140027b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b26  cmp     rcx, r12
  ... truncated ...
```
