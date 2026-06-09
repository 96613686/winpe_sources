# CKernelHangReport::_CollectKernelDump(void)

- ea: `0x140029018`
- end: `0x140029741`
- name: `?_CollectKernelDump@CKernelHangReport@@AEAAJXZ`
- size: `1833`
- prototype: `__int64 __fastcall(CKernelHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x140029760`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400041e8`
- `0x14000420c`
- `0x140004280`
- `0x140004350`
- `0x14000b580`
- `0x14000d544`
- `0x140014ee4`
- `0x140014f14`
- `0x1400158e8`
- `0x14001bf5c`
- `0x140021930`
- `0x140029018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002943e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002943e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140029223`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140029223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002948d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400296b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002948d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400296b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400290cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400290cb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400296cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400296cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002942e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002942e`
- `ntdll!RtlNtStatusToDosError` at `0x1400292e5`
- `ntdll!RtlNtStatusToDosError` at `0x1400292e5`
- `ntdll!NtSystemDebugControl` at `0x1400292d3`
- `ntdll!NtSystemDebugControl` at `0x1400292d3`
- `wer!WerpAddFile` at `0x1400294ea`
- `wer!WerpAddFile` at `0x1400294ea`

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
      WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
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
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, v10);
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
    WPP_SF_(*((_QWORD *)v28 + 2), v29, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, ThreadId);
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
        WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
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
      WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
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
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, (unsigned int)TempFile);
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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids, FileName);
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
        WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids,
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
0x140029018  push    rbp
0x14002901a  push    rbx
0x14002901b  push    rsi
0x14002901c  push    rdi
0x14002901d  push    r12
0x14002901f  push    r13
0x140029021  push    r14
0x140029023  push    r15
0x140029025  lea     rbp, [rsp-3D8h]
0x14002902d  sub     rsp, 4D8h
0x140029034  mov     rax, cs:__security_cookie
0x14002903b  xor     rax, rsp
0x14002903e  mov     [rbp+410h+var_50], rax
0x140029045  mov     rsi, rcx
0x140029048  xor     r13d, r13d
0x14002904b  mov     r15d, r13d
0x14002904e  mov     [rbp+410h+var_480], r13
0x140029052  mov     [rsp+510h+var_4CC], r13d
0x140029057  mov     ebx, r13d
0x14002905a  mov     [rbp+410h+var_478], rbx
0x14002905e  mov     r14d, r13d
0x140029061  mov     [rsp+510h+hFile], r13
0x140029066  xorps   xmm0, xmm0
0x140029069  xor     eax, eax
0x14002906b  movups  [rsp+510h+InputBuffer], xmm0
0x140029070  movups  [rsp+510h+var_4A8], xmm0
0x140029075  movups  [rsp+510h+var_498], xmm0
0x14002907a  mov     [rbp+410h+var_488], rax
0x14002907e  mov     [rsp+510h+NumberOfBytesWritten], r13d
0x140029083  mov     [rsp+510h+nNumberOfBytesToWrite], r13d
0x140029088  lea     r12, WPP_GLOBAL_Control
0x14002908f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029096  cmp     rcx, r12
0x140029099  jz      short loc_1400290BE
0x14002909b  test    byte ptr [rcx+1Ch], 4
0x14002909f  jz      short loc_1400290BE
0x1400290a1  mov     r9, [rsi+5D60h]
0x1400290a8  lea     edx, [rax+0Ah]
0x1400290ab  mov     r9d, [r9]
0x1400290ae  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x1400290b5  mov     rcx, [rcx+10h]
0x1400290b9  call    WPP_SF_d
0x1400290be  mov     [rbp+410h+FileName], r13w
0x1400290c3  mov     [rbp+410h+var_260], r13w
0x1400290cb  call    cs:__imp_GetTickCount
0x1400290d2  nop     dword ptr [rax+rax+00h]
0x1400290d7  mov     rcx, [rsi+5D60h]
0x1400290de  lea     rax, [rsp+510h+var_4CC]
0x1400290e3  mov     qword ptr [rsp+510h+OutputBufferLength], rax; unsigned int *
0x1400290e8  xor     r9d, r9d; unsigned int
0x1400290eb  xor     r8d, r8d; void **
0x1400290ee  xor     edx, edx; unsigned int
0x1400290f0  mov     ecx, [rcx]; unsigned int
0x1400290f2  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x1400290f7  mov     edi, eax
0x1400290f9  test    eax, eax
0x1400290fb  jns     short loc_140029134
0x1400290fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140029104  cmp     rcx, r12
0x140029107  jz      loc_1400296A4
0x14002910d  test    byte ptr [rcx+1Ch], 1
0x140029111  jz      loc_1400296A4
0x140029117  mov     edx, 0Bh
0x14002911c  mov     r9d, eax
0x14002911f  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x140029126  mov     rcx, [rcx+10h]
0x14002912a  call    WPP_SF_d
0x14002912f  jmp     loc_1400296A4
0x140029134  mov     r12d, [rsp+510h+var_4CC]
0x140029139  mov     eax, 8
0x14002913e  mul     r12
0x140029141  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140029148  cmovb   rax, rcx
0x14002914c  add     rax, 8
0x140029150  cmovb   rax, rcx
0x140029154  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002915b  mov     rcx, rax; unsigned __int64
0x14002915e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140029163  test    rax, rax
0x140029166  jz      short loc_140029194
0x140029168  mov     [rax], r12
0x14002916b  lea     r15, [rax+8]
0x14002916f  lea     rax, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x140029176  mov     qword ptr [rsp+510h+OutputBufferLength], rax; void (*)(void *)
0x14002917b  lea     r9, ??0?$unique_ptr@VIWERPlugIn@@U?$default_delete@VIWERPlugIn@@@utl@@@utl@@QEAA@XZ; void (*)(void *)
0x140029182  mov     r8d, r12d; unsigned __int64
0x140029185  mov     edx, 8; unsigned __int64
0x14002918a  mov     rcx, r15; void *
0x14002918d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140029192  jmp     short loc_140029197
0x140029194  mov     r15, r13
0x140029197  mov     [rbp+410h+var_480], r15
0x14002919b  test    r15, r15
0x14002919e  jz      loc_140029671
0x1400291a4  mov     rcx, [rsi+5D60h]
0x1400291ab  mov     qword ptr [rsp+510h+OutputBufferLength], r13; unsigned int *
0x1400291b0  mov     r9d, r12d; unsigned int
0x1400291b3  mov     r8, r15; void **
0x1400291b6  mov     edx, 1FFFFFh; unsigned int
0x1400291bb  mov     ecx, [rcx]; unsigned int
0x1400291bd  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x1400291c2  mov     edi, eax
0x1400291c4  test    eax, eax
0x1400291c6  jns     short loc_1400291F6
0x1400291c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291cf  lea     rax, WPP_GLOBAL_Control
0x1400291d6  cmp     rcx, rax
0x1400291d9  jz      loc_1400296A4
0x1400291df  test    byte ptr [rcx+1Ch], 1
0x1400291e3  jz      loc_1400296A4
0x1400291e9  mov     edx, 0Dh
0x1400291ee  mov     r9d, edi
0x1400291f1  jmp     loc_14002911F
0x1400291f6  mov     rax, cs:WPP_GLOBAL_Control
0x1400291fd  test    byte ptr [rax+1Ch], 4
0x140029201  jz      short loc_14002925C
0x140029203  mov     ebx, r13d
0x140029206  test    r12d, r12d
0x140029209  jz      short loc_14002925C
0x14002920b  lea     rdi, WPP_GLOBAL_Control
0x140029212  cmp     rax, rdi
0x140029215  jz      short loc_140029255
0x140029217  test    byte ptr [rax+1Ch], 4
0x14002921b  jz      short loc_140029255
0x14002921d  mov     ecx, ebx
0x14002921f  mov     rcx, [r15+rcx*8]; Thread
0x140029223  call    cs:__imp_GetThreadId
0x14002922a  nop     dword ptr [rax+rax+00h]
0x14002922f  mov     edx, 0Eh
0x140029234  mov     r9d, eax
0x140029237  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x14002923e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029245  mov     rcx, [rcx+10h]
0x140029249  call    WPP_SF_d
0x14002924e  mov     rax, cs:WPP_GLOBAL_Control
0x140029255  inc     ebx
0x140029257  cmp     ebx, r12d
0x14002925a  jb      short loc_140029212
0x14002925c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140029263  mov     edi, 100000h
0x140029268  mov     ecx, edi; unsigned __int64
0x14002926a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002926f  mov     rbx, rax
0x140029272  mov     [rbp+410h+var_478], rax
0x140029276  test    rax, rax
0x140029279  jz      loc_14002964C
0x14002927f  xorps   xmm0, xmm0
0x140029282  movups  [rsp+510h+InputBuffer], xmm0
0x140029287  movups  [rsp+510h+var_4A8], xmm0
0x14002928c  movups  [rsp+510h+var_498], xmm0
0x140029291  mov     eax, 1
0x140029296  mov     dword ptr [rsp+510h+InputBuffer], eax
0x14002929a  mov     dword ptr [rsp+510h+InputBuffer+4], 1F5h
0x1400292a2  mov     qword ptr [rsp+510h+InputBuffer+8], rax
0x1400292a7  mov     dword ptr [rbp+410h+var_498+8], r13d
0x1400292ab  mov     dword ptr [rbp+410h+var_498+0Ch], r12d
0x1400292af  mov     [rbp+410h+var_488], r15
0x1400292b3  lea     rax, [rsp+510h+nNumberOfBytesToWrite]
0x1400292b8  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x1400292bd  mov     [rsp+510h+OutputBufferLength], edi; OutputBufferLength
0x1400292c1  mov     r9, rbx; OutputBuffer
0x1400292c4  mov     r8d, 38h ; '8'; InputBufferLength
0x1400292ca  lea     rdx, [rsp+510h+InputBuffer]; InputBuffer
0x1400292cf  lea     ecx, [r8-1Bh]; ControlCode
0x1400292d3  call    cs:__imp_NtSystemDebugControl
0x1400292da  nop     dword ptr [rax+rax+00h]
0x1400292df  test    eax, eax
0x1400292e1  jns     short loc_14002932B
0x1400292e3  mov     ecx, eax; Status
0x1400292e5  call    cs:__imp_RtlNtStatusToDosError
0x1400292ec  nop     dword ptr [rax+rax+00h]
0x1400292f1  mov     edi, eax
0x1400292f3  test    eax, eax
0x1400292f5  jle     short loc_140029300
0x1400292f7  movzx   edi, ax
0x1400292fa  or      edi, 80070000h
0x140029300  mov     rcx, cs:WPP_GLOBAL_Control
0x140029307  lea     rax, WPP_GLOBAL_Control
0x14002930e  cmp     rcx, rax
0x140029311  jz      loc_1400296A4
0x140029317  test    byte ptr [rcx+1Ch], 1
0x14002931b  jz      loc_1400296A4
0x140029321  mov     edx, 10h
0x140029326  jmp     loc_1400291EE
0x14002932b  mov     r9d, [rsp+510h+nNumberOfBytesToWrite]
0x140029330  cmp     r9d, edi
0x140029333  ja      loc_140029617
0x140029339  mov     rcx, cs:WPP_GLOBAL_Control
0x140029340  lea     r12, WPP_GLOBAL_Control
0x140029347  cmp     rcx, r12
0x14002934a  jz      short loc_140029367
0x14002934c  test    byte ptr [rcx+1Ch], 4
0x140029350  jz      short loc_140029367
0x140029352  mov     edx, 12h
0x140029357  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x14002935e  mov     rcx, [rcx+10h]
0x140029362  call    WPP_SF_d
0x140029367  mov     [rsp+510h+var_4D8], r13d
0x14002936c  mov     [rsp+510h+var_4E0], r13d
0x140029371  mov     [rsp+510h+ReturnLength], r13
0x140029376  lea     r9, [rbp+410h+FileName]
0x14002937a  lea     r14, aAtkKdmp; "atk.kdmp"
0x140029381  mov     r8, r14
0x140029384  xor     edx, edx
0x140029386  lea     rcx, [rsp+510h+hFile]
0x14002938b  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140029390  mov     edi, eax
0x140029392  test    eax, eax
0x140029394  jns     short loc_1400293CA
0x140029396  mov     rcx, cs:WPP_GLOBAL_Control
0x14002939d  cmp     rcx, r12
0x1400293a0  jz      short loc_1400293C0
0x1400293a2  test    byte ptr [rcx+1Ch], 1
0x1400293a6  jz      short loc_1400293C0
0x1400293a8  mov     edx, 13h
0x1400293ad  mov     r9d, eax
0x1400293b0  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x1400293b7  mov     rcx, [rcx+10h]
0x1400293bb  call    WPP_SF_d
0x1400293c0  mov     r14, [rsp+510h+hFile]
0x1400293c5  jmp     loc_1400296A4
0x1400293ca  mov     r9, [rsi+5F70h]
0x1400293d1  add     r9, 100h
0x1400293d8  mov     qword ptr [rsp+510h+OutputBufferLength], r14
0x1400293dd  lea     r8, aSS; "%s.%s"
0x1400293e4  mov     edx, 104h; unsigned __int64
0x1400293e9  lea     rcx, [rbp+410h+var_260]; wchar_t *
0x1400293f0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400293f5  mov     edi, eax
0x1400293f7  test    eax, eax
0x1400293f9  jns     short loc_140029414
0x1400293fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140029402  cmp     rcx, r12
0x140029405  jz      short loc_1400293C0
0x140029407  test    byte ptr [rcx+1Ch], 1
0x14002940b  jz      short loc_1400293C0
0x14002940d  mov     edx, 14h
0x140029412  jmp     short loc_1400293AD
0x140029414  mov     qword ptr [rsp+510h+OutputBufferLength], r13; lpOverlapped
0x140029419  lea     r9, [rsp+510h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002941e  mov     r8d, [rsp+510h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140029423  mov     rdx, rbx; lpBuffer
0x140029426  mov     r14, [rsp+510h+hFile]
0x14002942b  mov     rcx, r14; hFile
0x14002942e  call    cs:__imp_WriteFile
0x140029435  nop     dword ptr [rax+rax+00h]
0x14002943a  test    eax, eax
0x14002943c  jnz     short loc_14002947D
0x14002943e  call    cs:__imp_GetLastError
0x140029445  nop     dword ptr [rax+rax+00h]
0x14002944a  mov     edi, eax
0x14002944c  test    eax, eax
0x14002944e  jle     short loc_140029459
0x140029450  movzx   edi, ax
0x140029453  or      edi, 80070000h
0x140029459  mov     rcx, cs:WPP_GLOBAL_Control
0x140029460  cmp     rcx, r12
0x140029463  jz      loc_1400296A4
0x140029469  test    byte ptr [rcx+1Ch], 1
0x14002946d  jz      loc_1400296A4
0x140029473  mov     edx, 15h
0x140029478  jmp     loc_1400291EE
0x14002947d  mov     rcx, r14; hObject
0x140029480  mov     r14, r13
0x140029483  lea     rax, [rcx+1]
0x140029487  cmp     rax, 1
0x14002948b  jbe     short loc_140029499
0x14002948d  call    cs:__imp_CloseHandle
0x140029494  nop     dword ptr [rax+rax+00h]
0x140029499  mov     rcx, cs:WPP_GLOBAL_Control
0x1400294a0  cmp     rcx, r12
0x1400294a3  jz      short loc_1400294C4
0x1400294a5  test    byte ptr [rcx+1Ch], 4
0x1400294a9  jz      short loc_1400294C4
0x1400294ab  mov     edx, 16h
0x1400294b0  lea     r9, [rbp+410h+FileName]
0x1400294b4  lea     r8, WPP_0bdee4361a9639f0515af5bbfce93a4d_Traceguids
0x1400294bb  mov     rcx, [rcx+10h]
0x1400294bf  call    WPP_SF_S
0x1400294c4  mov     [rsp+510h+ReturnLength], r13
0x1400294c9  lea     rax, [rbp+410h+var_260]
0x1400294d0  mov     qword ptr [rsp+510h+OutputBufferLength], rax
0x1400294d5  mov     r9d, 1
0x1400294db  lea     r8d, [r9+4]
0x1400294df  lea     rdx, [rbp+410h+FileName]
0x1400294e3  mov     rcx, [rsi+5F78h]
0x1400294ea  call    cs:__imp_WerpAddFile
0x1400294f1  nop     dword ptr [rax+rax+00h]
0x1400294f6  mov     edi, eax
0x1400294f8  test    eax, eax
0x1400294fa  jns     short loc_140029520
0x1400294fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140029503  cmp     rcx, r12
0x140029506  jz      loc_1400296A4
0x14002950c  test    byte ptr [rcx+1Ch], 1
0x140029510  jz      loc_1400296A4
0x140029516  mov     edx, 17h
0x14002951b  jmp     loc_14002911C
0x140029520  mov     r8, [rsi+5D60h]
0x140029527  mov     r9d, 2
  ... truncated ...
```
