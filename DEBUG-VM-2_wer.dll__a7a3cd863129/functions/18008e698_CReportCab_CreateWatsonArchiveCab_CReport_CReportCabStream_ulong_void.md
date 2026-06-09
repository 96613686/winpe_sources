# CReportCab::CreateWatsonArchiveCab(CReport *,CReportCabStream *,ulong,void *)

- ea: `0x18008e698`
- end: `0x18008eb0e`
- name: `?CreateWatsonArchiveCab@CReportCab@@QEAAJPEAVCReport@@PEAVCReportCabStream@@KPEAX@Z`
- size: `1142`
- prototype: `__int64 __usercall@<rax>(CReportCab *__hidden this@<rcx>, struct CReport *@<rdx>, struct CReportCabStream *@<r8>, unsigned int@<r9d>, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18007d258`

## callees

- `0x180004bb4`
- `0x180013730`
- `0x18001f9dc`
- `0x18001fe24`
- `0x180026498`
- `0x18002dbac`
- `0x18003bf14`
- `0x180043d28`
- `0x180045bb4`
- `0x180048cd0`
- `0x180048d10`
- `0x18008e698`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e6d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e748`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008eaad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e6d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e748`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008eaad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008e754`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008eab9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008e754`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008eab9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008e6de`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008e6de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e75e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e7c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e7c4`

## pseudocode

```c
__int64 __fastcall CReportCab::CreateWatsonArchiveCab(
        CReportCab *this,
        struct CReport *a2,
        struct CReportCabStream *a3,
        int a4,
        HANDLE hHandle)
{
  HANDLE CurrentThread; // rax
  int v9; // r12d
  signed int LastError; // eax
  unsigned int v11; // ebx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HANDLE v15; // rax
  signed int v16; // eax
  _QWORD *v17; // r15
  __int64 v18; // rax
  int v19; // eax
  struct CReportFile *v20; // rbx
  __int64 v21; // r13
  struct CReportFile *v22; // rbp
  unsigned int v23; // r15d
  int FileByIndex; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  HANDLE v34; // rax
  struct CReportFile *v36; // [rsp+30h] [rbp-48h] BYREF
  struct CReportFile *v37; // [rsp+38h] [rbp-40h] BYREF
  int ThreadPriority; // [rsp+88h] [rbp+10h]

  v37 = 0;
  if ( !a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids);
    return 2147942487LL;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v9 = ThreadPriority;
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 28;
      v14 = v11;
      goto LABEL_9;
    }
    goto LABEL_75;
  }
  v15 = GetCurrentThread();
  if ( !SetThreadPriority(v15, -1) )
  {
    v16 = GetLastError();
    v11 = v16;
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v11);
    v9 = 0x7FFFFFFF;
    goto LABEL_75;
  }
  if ( hHandle )
  {
    *(_QWORD *)this = hHandle;
    if ( !WaitForSingleObject(hHandle, 0) )
    {
      v11 = -2145681407;
      goto LABEL_75;
    }
  }
  v17 = (_QWORD *)((char *)this + 40);
  if ( *((_DWORD *)a3 + 4) )
    v18 = utl::make_unique<CZipArchiveFile,,0>(&v36);
  else
    v18 = utl::make_unique<CCabArchiveFile,,0>(&v36);
  utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(
    (char *)this + 40,
    v18);
  utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(&v36);
  if ( !*v17 )
  {
    v11 = -2147024882;
    goto LABEL_75;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, struct CReportCabStream *, _QWORD, _QWORD, HANDLE))(*(_QWORD *)*v17 + 8LL))(
          *v17,
          a3,
          0,
          0,
          hHandle);
  v11 = v19;
  if ( v19 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 30;
      goto LABEL_28;
    }
    goto LABEL_75;
  }
  v20 = 0;
  v21 = (__int64)(*((_QWORD *)a2 + 728) - *((_QWORD *)a2 + 727)) >> 3;
  v22 = 0;
  v23 = 0;
  v36 = 0;
  if ( !(_DWORD)v21 )
    goto LABEL_58;
  do
  {
    FileByIndex = CReport::GetFileByIndex(a2, v23, &v37);
    if ( FileByIndex < 0 || (v20 = v37) == 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v30 = 31;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, (unsigned int)FileByIndex);
      }
LABEL_55:
      v20 = v36;
      goto LABEL_56;
    }
    if ( (a4 & *((_DWORD *)v37 + 1)) != a4 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v28 = *((_QWORD *)v37 + 10);
        if ( v28 == *((_QWORD *)v37 + 11) )
          v28 = *((_QWORD *)v37 + 14);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v28);
      }
      goto LABEL_55;
    }
    if ( *((_DWORD *)a2 + 1468) != 4 )
      goto LABEL_47;
    if ( *(_DWORD *)v37 != 2 )
    {
      if ( *(_DWORD *)v37 == 3 )
      {
        if ( v22 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25, v27);
        v22 = v20;
        goto LABEL_55;
      }
LABEL_47:
      FileByIndex = CReportCab::AddReportFileToCab(this, a2, v37);
      if ( FileByIndex < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v30 = 33;
          goto LABEL_54;
        }
      }
      goto LABEL_55;
    }
    if ( v36 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25, v27);
    v36 = v20;
LABEL_56:
    ++v23;
  }
  while ( v23 < (unsigned int)v21 );
  v9 = ThreadPriority;
LABEL_58:
  if ( *((_DWORD *)a2 + 1468) == 4 )
  {
    if ( !v22 )
      goto LABEL_64;
    v31 = CReportCab::AddReportFileToCab(this, a2, v22);
    if ( v31 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
          (unsigned int)v31);
LABEL_64:
      if ( v20 )
      {
        v32 = CReportCab::AddReportFileToCab(this, a2, v20);
        if ( v32 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
            (unsigned int)v32);
      }
    }
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5));
  v11 = v19;
  if ( v19 >= 0 )
  {
    v11 = 0;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 36;
LABEL_28:
      v14 = (unsigned int)v19;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v14);
    }
  }
LABEL_75:
  v33 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v33 )
    utl::default_delete<ITpCommand>::operator()();
  if ( v9 != 0x7FFFFFFF )
  {
    v34 = GetCurrentThread();
    SetThreadPriority(v34, v9);
  }
  return v11;
}

```

## disassembly

```asm
0x18008e698  mov     [rsp+arg_0], rbx
0x18008e69d  mov     [rsp+arg_18], r9d
0x18008e6a2  push    rbp
0x18008e6a3  push    rsi
0x18008e6a4  push    rdi
0x18008e6a5  push    r12
0x18008e6a7  push    r13
0x18008e6a9  push    r14
0x18008e6ab  push    r15
0x18008e6ad  sub     rsp, 40h
0x18008e6b1  mov     [rsp+78h+var_40], 0
0x18008e6ba  mov     rdi, r8
0x18008e6bd  mov     rsi, rdx
0x18008e6c0  mov     r14, rcx
0x18008e6c3  test    rdx, rdx
0x18008e6c6  jz      loc_18008EAC3
0x18008e6cc  test    r8, r8
0x18008e6cf  jz      loc_18008EAC3
0x18008e6d5  call    cs:__imp_GetCurrentThread
0x18008e6db  mov     rcx, rax; hThread
0x18008e6de  call    cs:__imp_GetThreadPriority
0x18008e6e4  mov     [rsp+78h+arg_8], eax
0x18008e6eb  mov     r12d, eax
0x18008e6ee  cmp     eax, 7FFFFFFFh
0x18008e6f3  jnz     short loc_18008E748
0x18008e6f5  call    cs:__imp_GetLastError
0x18008e6fb  mov     ebx, eax
0x18008e6fd  test    eax, eax
0x18008e6ff  jle     short loc_18008E70A
0x18008e701  movzx   ebx, ax
0x18008e704  or      ebx, 80070000h
0x18008e70a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e711  lea     rdi, WPP_GLOBAL_Control
0x18008e718  cmp     rcx, rdi
0x18008e71b  jz      loc_18008EA8E
0x18008e721  test    byte ptr [rcx+1Ch], 1
0x18008e725  jz      loc_18008EA8E
0x18008e72b  mov     edx, 1Ch
0x18008e730  mov     r9d, ebx
0x18008e733  mov     rcx, [rcx+10h]
0x18008e737  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e73e  call    WPP_SF_d
0x18008e743  jmp     loc_18008EA8E
0x18008e748  call    cs:__imp_GetCurrentThread
0x18008e74e  mov     rcx, rax; hThread
0x18008e751  or      edx, 0FFFFFFFFh; nPriority
0x18008e754  call    cs:__imp_SetThreadPriority
0x18008e75a  test    eax, eax
0x18008e75c  jnz     short loc_18008E7AF
0x18008e75e  call    cs:__imp_GetLastError
0x18008e764  mov     ebx, eax
0x18008e766  test    eax, eax
0x18008e768  jle     short loc_18008E773
0x18008e76a  movzx   ebx, ax
0x18008e76d  or      ebx, 80070000h
0x18008e773  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e77a  lea     rdi, WPP_GLOBAL_Control
0x18008e781  cmp     rcx, rdi
0x18008e784  jz      short loc_18008E7A4
0x18008e786  test    byte ptr [rcx+1Ch], 1
0x18008e78a  jz      short loc_18008E7A4
0x18008e78c  mov     rcx, [rcx+10h]
0x18008e790  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e797  mov     edx, 1Dh
0x18008e79c  mov     r9d, ebx
0x18008e79f  call    WPP_SF_d
0x18008e7a4  mov     r12d, 7FFFFFFFh
0x18008e7aa  jmp     loc_18008EA8E
0x18008e7af  mov     rbx, [rsp+78h+hHandle]
0x18008e7b7  test    rbx, rbx
0x18008e7ba  jz      short loc_18008E7D8
0x18008e7bc  xor     edx, edx; dwMilliseconds
0x18008e7be  mov     [r14], rbx
0x18008e7c1  mov     rcx, rbx; hHandle
0x18008e7c4  call    cs:__imp_WaitForSingleObject
0x18008e7ca  test    eax, eax
0x18008e7cc  jnz     short loc_18008E7D8
0x18008e7ce  mov     ebx, 801B8001h
0x18008e7d3  jmp     loc_18008EA8E
0x18008e7d8  cmp     dword ptr [rdi+10h], 0
0x18008e7dc  lea     r15, [r14+28h]
0x18008e7e0  lea     rcx, [rsp+78h+var_48]
0x18008e7e5  jz      short loc_18008E803
0x18008e7e7  call    ??$make_unique@VCZipArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@0@XZ; utl::make_unique<CZipArchiveFile,,0>(void)
0x18008e7ec  mov     rdx, rax
0x18008e7ef  mov     rcx, r15
0x18008e7f2  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x18008e7f7  lea     rcx, [rsp+78h+var_48]
0x18008e7fc  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x18008e801  jmp     short loc_18008E81D
0x18008e803  call    ??$make_unique@VCCabArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCCabArchiveFile@@U?$default_delete@VCCabArchiveFile@@@utl@@@0@XZ; utl::make_unique<CCabArchiveFile,,0>(void)
0x18008e808  mov     rdx, rax
0x18008e80b  mov     rcx, r15
0x18008e80e  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x18008e813  lea     rcx, [rsp+78h+var_48]
0x18008e818  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x18008e81d  mov     rcx, [r15]
0x18008e820  test    rcx, rcx
0x18008e823  jz      loc_18008EA89
0x18008e829  mov     rax, [rcx]
0x18008e82c  xor     r9d, r9d
0x18008e82f  xor     r8d, r8d
0x18008e832  mov     [rsp+78h+var_58], rbx
0x18008e837  mov     rdx, rdi
0x18008e83a  mov     rax, [rax+8]
0x18008e83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e843  mov     ebx, eax
0x18008e845  test    eax, eax
0x18008e847  jns     short loc_18008E877
0x18008e849  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e850  lea     rdi, WPP_GLOBAL_Control
0x18008e857  cmp     rcx, rdi
0x18008e85a  jz      loc_18008EA8E
0x18008e860  test    byte ptr [rcx+1Ch], 1
0x18008e864  jz      loc_18008EA8E
0x18008e86a  mov     edx, 1Eh
0x18008e86f  mov     r9d, eax
0x18008e872  jmp     loc_18008E733
0x18008e877  mov     r13, [rsi+16C0h]
0x18008e87e  lea     rdi, WPP_GLOBAL_Control
0x18008e885  sub     r13, [rsi+16B8h]
0x18008e88c  xor     ebx, ebx
0x18008e88e  sar     r13, 3
0x18008e892  xor     ebp, ebp
0x18008e894  xor     r15d, r15d
0x18008e897  mov     [rsp+78h+var_48], rbx
0x18008e89c  test    r13d, r13d
0x18008e89f  jz      loc_18008E9C4
0x18008e8a5  mov     r12d, [rsp+78h+arg_18]
0x18008e8ad  lea     r8, [rsp+78h+var_40]; struct CReportFile **
0x18008e8b2  mov     edx, r15d; unsigned int
0x18008e8b5  mov     rcx, rsi; this
0x18008e8b8  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x18008e8bd  test    eax, eax
0x18008e8bf  js      loc_18008E981
0x18008e8c5  mov     rbx, [rsp+78h+var_40]
0x18008e8ca  test    rbx, rbx
0x18008e8cd  jz      loc_18008E981
0x18008e8d3  mov     eax, [rbx+4]
0x18008e8d6  and     eax, r12d
0x18008e8d9  cmp     eax, r12d
0x18008e8dc  jz      short loc_18008E920
0x18008e8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e8e5  cmp     rcx, rdi
0x18008e8e8  jz      loc_18008E9AB
0x18008e8ee  test    byte ptr [rcx+1Ch], 4
0x18008e8f2  jz      loc_18008E9AB
0x18008e8f8  mov     r9, [rbx+50h]
0x18008e8fc  cmp     r9, [rbx+58h]
0x18008e900  jnz     short loc_18008E906
0x18008e902  mov     r9, [rbx+70h]
0x18008e906  mov     rcx, [rcx+10h]
0x18008e90a  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e911  mov     edx, 20h ; ' '
0x18008e916  call    WPP_SF_S
0x18008e91b  jmp     loc_18008E9AB
0x18008e920  cmp     dword ptr [rsi+16F0h], 4
0x18008e927  jnz     short loc_18008E956
0x18008e929  cmp     dword ptr [rbx], 2
0x18008e92c  jnz     short loc_18008E942
0x18008e92e  cmp     [rsp+78h+var_48], 0
0x18008e934  jz      short loc_18008E93B
0x18008e936  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e93b  mov     [rsp+78h+var_48], rbx
0x18008e940  jmp     short loc_18008E9B0
0x18008e942  cmp     dword ptr [rbx], 3
0x18008e945  jnz     short loc_18008E956
0x18008e947  test    rbp, rbp
0x18008e94a  jz      short loc_18008E951
0x18008e94c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e951  mov     rbp, rbx
0x18008e954  jmp     short loc_18008E9AB
0x18008e956  mov     r8, rbx; struct CReportFile *
0x18008e959  mov     rdx, rsi; struct CReport *
0x18008e95c  mov     rcx, r14; this
0x18008e95f  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008e964  test    eax, eax
0x18008e966  jns     short loc_18008E9AB
0x18008e968  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e96f  cmp     rcx, rdi
0x18008e972  jz      short loc_18008E9AB
0x18008e974  test    byte ptr [rcx+1Ch], 2
0x18008e978  jz      short loc_18008E9AB
0x18008e97a  mov     edx, 21h ; '!'
0x18008e97f  jmp     short loc_18008E998
0x18008e981  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e988  cmp     rcx, rdi
0x18008e98b  jz      short loc_18008E9AB
0x18008e98d  test    byte ptr [rcx+1Ch], 2
0x18008e991  jz      short loc_18008E9AB
0x18008e993  mov     edx, 1Fh
0x18008e998  mov     rcx, [rcx+10h]
0x18008e99c  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e9a3  mov     r9d, eax
0x18008e9a6  call    WPP_SF_d
0x18008e9ab  mov     rbx, [rsp+78h+var_48]
0x18008e9b0  inc     r15d
0x18008e9b3  cmp     r15d, r13d
0x18008e9b6  jb      loc_18008E8AD
0x18008e9bc  mov     r12d, [rsp+78h+arg_8]
0x18008e9c4  cmp     dword ptr [rsi+16F0h], 4
0x18008e9cb  jnz     loc_18008EA53
0x18008e9d1  test    rbp, rbp
0x18008e9d4  jz      short loc_18008EA12
0x18008e9d6  mov     r8, rbp; struct CReportFile *
0x18008e9d9  mov     rdx, rsi; struct CReport *
0x18008e9dc  mov     rcx, r14; this
0x18008e9df  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008e9e4  test    eax, eax
0x18008e9e6  jns     short loc_18008EA53
0x18008e9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9ef  cmp     rcx, rdi
0x18008e9f2  jz      short loc_18008EA12
0x18008e9f4  test    byte ptr [rcx+1Ch], 2
0x18008e9f8  jz      short loc_18008EA12
0x18008e9fa  mov     rcx, [rcx+10h]
0x18008e9fe  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008ea05  mov     edx, 22h ; '"'
0x18008ea0a  mov     r9d, eax
0x18008ea0d  call    WPP_SF_d
0x18008ea12  test    rbx, rbx
0x18008ea15  jz      short loc_18008EA53
0x18008ea17  mov     r8, rbx; struct CReportFile *
0x18008ea1a  mov     rdx, rsi; struct CReport *
0x18008ea1d  mov     rcx, r14; this
0x18008ea20  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008ea25  test    eax, eax
0x18008ea27  jns     short loc_18008EA53
0x18008ea29  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea30  cmp     rcx, rdi
0x18008ea33  jz      short loc_18008EA53
0x18008ea35  test    byte ptr [rcx+1Ch], 2
0x18008ea39  jz      short loc_18008EA53
0x18008ea3b  mov     rcx, [rcx+10h]
0x18008ea3f  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008ea46  mov     edx, 23h ; '#'
0x18008ea4b  mov     r9d, eax
0x18008ea4e  call    WPP_SF_d
0x18008ea53  mov     rcx, [r14+28h]
0x18008ea57  mov     rax, [rcx]
0x18008ea5a  mov     rax, [rax+28h]
0x18008ea5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea63  mov     ebx, eax
0x18008ea65  test    eax, eax
0x18008ea67  jns     short loc_18008EA85
0x18008ea69  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea70  cmp     rcx, rdi
0x18008ea73  jz      short loc_18008EA8E
0x18008ea75  test    byte ptr [rcx+1Ch], 1
0x18008ea79  jz      short loc_18008EA8E
0x18008ea7b  mov     edx, 24h ; '$'
0x18008ea80  jmp     loc_18008E86F
0x18008ea85  xor     ebx, ebx
0x18008ea87  jmp     short loc_18008EA8E
0x18008ea89  mov     ebx, 8007000Eh
0x18008ea8e  mov     rdx, [r14+28h]
0x18008ea92  mov     qword ptr [r14+28h], 0
0x18008ea9a  test    rdx, rdx
0x18008ea9d  jz      short loc_18008EAA4
0x18008ea9f  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18008eaa4  cmp     r12d, 7FFFFFFFh
0x18008eaab  jz      short loc_18008EABF
0x18008eaad  call    cs:__imp_GetCurrentThread
0x18008eab3  mov     rcx, rax; hThread
0x18008eab6  mov     edx, r12d; nPriority
0x18008eab9  call    cs:__imp_SetThreadPriority
0x18008eabf  mov     eax, ebx
0x18008eac1  jmp     short loc_18008EAF6
0x18008eac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eaca  lea     rdi, WPP_GLOBAL_Control
0x18008ead1  cmp     rcx, rdi
0x18008ead4  jz      short loc_18008EAF1
0x18008ead6  test    byte ptr [rcx+1Ch], 1
0x18008eada  jz      short loc_18008EAF1
0x18008eadc  mov     rcx, [rcx+10h]
0x18008eae0  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008eae7  mov     edx, 1Bh
0x18008eaec  call    WPP_SF_
0x18008eaf1  mov     eax, 80070057h
0x18008eaf6  mov     rbx, [rsp+78h+arg_0]
0x18008eafe  add     rsp, 40h
0x18008eb02  pop     r15
0x18008eb04  pop     r14
0x18008eb06  pop     r13
0x18008eb08  pop     r12
0x18008eb0a  pop     rdi
0x18008eb0b  pop     rsi
0x18008eb0c  pop     rbp
0x18008eb0d  retn
```
