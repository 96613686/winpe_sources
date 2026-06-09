# NetSetupLegacyPlugin::StartAndWaitForGenericHost(_GUID *,ulong *)

- ea: `0x180036010`
- end: `0x1800366a6`
- name: `?StartAndWaitForGenericHost@NetSetupLegacyPlugin@@AEAAXPEAU_GUID@@PEAK@Z`
- size: `1686`
- prototype: `void __fastcall(NetSetupLegacyPlugin *this, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003690c`

## callees

- `0x180005660`
- `0x180011740`
- `0x180036010`
- `0x1800366b0`
- `0x18005097c`
- `0x180052620`
- `0x18005b034`
- `0x18005b188`
- `0x18005c7b8`
- `0x18005c7f4`
- `0x18005c848`
- `0x180064704`
- `0x180065035`
- `0x1800810a2`
- `0x1800810d0`

## import_xrefs

- `msvcrt!malloc` at `0x180036199`
- `msvcrt!malloc` at `0x180036199`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800360e5`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800361fd`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800360e5`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800361fd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036519`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036519`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003607d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003607d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003612e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003624e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003653e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003612e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003624e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003653e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180036128`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180036244`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180036128`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180036244`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800365a5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800365a5`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800362f1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800362f1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180036463`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180036463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800364de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003667a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800364de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003667a`
- `RPCRT4!UuidCreate` at `0x180036396`
- `RPCRT4!UuidCreate` at `0x180036396`

## string_xrefs

- `0x1800360ae`: `readyEvent`

## pseudocode

```c
void __fastcall NetSetupLegacyPlugin::StartAndWaitForGenericHost(
        NetSetupLegacyPlugin *this,
        struct _GUID *a2,
        unsigned int *a3)
{
  HANDLE v5; // rax
  void *v6; // rdi
  signed int LastError; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rax
  signed int v9; // ebx
  signed int v10; // ebx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  _QWORD *PathToNotifyObjectHostExe; // rax
  signed int v14; // ebx
  HANDLE hProcess; // rbx
  DWORD v16; // eax
  signed int v17; // esi
  void *v18[3]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v19; // [rsp+70h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-90h]
  void *v21[4]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v22[208]; // [rsp+A0h] [rbp-68h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+170h] [rbp+68h] BYREF
  ULONG_PTR Size; // [rsp+178h] [rbp+70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+180h] [rbp+78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+198h] [rbp+90h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v27; // [rsp+200h] [rbp+F8h]
  const char *v28; // [rsp+208h] [rbp+100h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+210h] [rbp+108h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v31[8]; // [rsp+240h] [rbp+138h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST *p_lpAttributeList; // [rsp+248h] [rbp+140h]
  HANDLE v33; // [rsp+250h] [rbp+148h]
  HANDLE Value; // [rsp+258h] [rbp+150h] BYREF
  HANDLE Handles[3]; // [rsp+260h] [rbp+158h] BYREF
  WCHAR CommandLine[264]; // [rsp+278h] [rbp+170h] BYREF

  v20 = -2;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_OWORD *)&EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v5 = CreateEventW(&EventAttributes, 0, 0, 0);
  v6 = v5;
  v33 = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids, "readyEvent");
    v28 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v28, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  Value = v5;
  Size = 0;
  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
  if ( GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)v22, LastError);
    throw (HResultException *)v22;
  }
  v8 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)malloc(Size);
  lpAttributeList = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids, "attributes");
    v28 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v28, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  LOBYTE(pExceptionObject[0]) = 0;
  pExceptionObject[1] = &lpAttributeList;
  if ( !InitializeProcThreadAttributeList(v8, 1u, 0, &Size) )
  {
    v9 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids,
        (unsigned int)v9);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    HResultException::HResultException((HResultException *)v22, v9);
    throw (HResultException *)v22;
  }
  v31[0] = 0;
  p_lpAttributeList = &lpAttributeList;
  if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, &Value, 8u, 0, 0) )
  {
    v10 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids,
        (unsigned int)v10);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    HResultException::HResultException((HResultException *)v22, v10);
    throw (HResultException *)v22;
  }
  *(_QWORD *)&StartupInfo.cb = 112;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v27 = lpAttributeList;
  UuidCreate(a2);
  v11 = (_QWORD *)StringFromGuid(v21, a2);
  v12 = v11;
  if ( v11[3] >= 8u )
    v12 = (_QWORD *)*v11;
  PathToNotifyObjectHostExe = (_QWORD *)GetPathToNotifyObjectHostExe(v18);
  if ( PathToNotifyObjectHostExe[3] >= 8u )
    PathToNotifyObjectHostExe = (_QWORD *)*PathToNotifyObjectHostExe;
  swprintf_s<260>(CommandLine, L"%s %ws %Iu", PathToNotifyObjectHostExe, v12, v6);
  if ( v19 >= 8 )
    operator delete(v18[0]);
  v19 = 7;
  v18[2] = 0;
  LOWORD(v18[0]) = 0;
  if ( v21[3] >= (void *)8 )
    operator delete(v21[0]);
  if ( !CreateProcessW(0, CommandLine, 0, 0, 1, 0x80000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v14 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids,
        (unsigned int)CommandLine,
        v14);
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    HResultException::HResultException((HResultException *)v22, v14);
    throw (HResultException *)v22;
  }
  CloseHandle(ProcessInformation.hThread);
  hProcess = ProcessInformation.hProcess;
  v28 = (const char *)ProcessInformation.hProcess;
  Handles[0] = v6;
  Handles[1] = ProcessInformation.hProcess;
  v16 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xEA60u, 0);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 != 1 )
    {
      if ( v16 != 258 )
      {
        if ( v16 == -1 )
          v17 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids);
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        HResultException::HResultException((HResultException *)v22, v17);
        throw (HResultException *)v22;
      }
      TerminateProcess(hProcess, 0x41Du);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids);
      HResultException::HResultException((HResultException *)v22, -2147023843);
      throw (HResultException *)v22;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids);
    HResultException::HResultException((HResultException *)v22, -2147023819);
    throw (HResultException *)v22;
  }
  *a3 = ProcessInformation.dwProcessId;
  if ( hProcess )
    CloseHandle(hProcess);
  ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_d56c24711cada7791f9cbe62ad5760be_____(v31);
  ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_319c0e4619e35ca155cc656088fe6dd0_____(pExceptionObject);
  CloseHandle(v6);
}

```

## disassembly

```asm
0x180036010  mov     rax, rsp
0x180036013  push    rbp
0x180036014  push    rsi
0x180036015  push    rdi
0x180036016  push    r12
0x180036018  push    r14
0x18003601a  lea     rbp, [rax-3B8h]
0x180036021  sub     rsp, 490h
0x180036028  mov     [rsp+4B0h+var_440], 0FFFFFFFFFFFFFFFEh
0x180036031  mov     [rax+8], rbx
0x180036035  mov     rax, cs:__security_cookie
0x18003603c  xor     rax, rsp
0x18003603f  mov     [rbp+3B0h+var_30], rax
0x180036046  mov     r14, r8
0x180036049  mov     rbx, rdx
0x18003604c  mov     qword ptr [rbp+3B0h+EventAttributes.nLength], 18h
0x180036057  xorps   xmm0, xmm0
0x18003605a  movups  xmmword ptr [rbp+3B0h+EventAttributes.lpSecurityDescriptor], xmm0
0x180036061  mov     r12d, 1
0x180036067  mov     [rbp+3B0h+EventAttributes.bInheritHandle], r12d
0x18003606e  xor     r9d, r9d; lpName
0x180036071  xor     r8d, r8d; bInitialState
0x180036074  xor     edx, edx; bManualReset
0x180036076  lea     rcx, [rbp+3B0h+EventAttributes]; lpEventAttributes
0x18003607d  call    cs:__imp_CreateEventW
0x180036083  mov     rdi, rax
0x180036086  mov     [rbp+3B0h+var_268], rax
0x18003608d  test    rax, rax
0x180036090  jnz     short loc_18003610D
0x180036092  lea     rax, WPP_GLOBAL_Control
0x180036099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360a0  cmp     rcx, rax
0x1800360a3  jz      short loc_1800360C6
0x1800360a5  cmp     byte ptr [rcx+19h], 2
0x1800360a9  jb      short loc_1800360C6
0x1800360ab  lea     edx, [rdi+0Fh]
0x1800360ae  lea     r9, aReadyevent; "readyEvent"
0x1800360b5  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x1800360bc  mov     rcx, [rcx+10h]
0x1800360c0  call    WPP_SF_s
0x1800360c5  nop
0x1800360c6  lea     rax, aBadAllocation; "bad allocation"
0x1800360cd  mov     [rbp+3B0h+var_2B0], rax
0x1800360d4  mov     r8d, r12d
0x1800360d7  lea     rdx, [rbp+3B0h+var_2B0]
0x1800360de  lea     rcx, [rbp+3B0h+pExceptionObject]
0x1800360e5  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x1800360eb  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800360f2  mov     [rbp+3B0h+pExceptionObject], rax
0x1800360f9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180036100  lea     rcx, [rbp+3B0h+pExceptionObject]; pExceptionObject
0x180036107  call    _CxxThrowException_0
0x18003610d  mov     [rbp+3B0h+Value], rdi
0x180036114  mov     [rbp+3B0h+Size], 0
0x18003611c  lea     r9, [rbp+3B0h+Size]; lpSize
0x180036120  xor     r8d, r8d; dwFlags
0x180036123  mov     edx, r12d; dwAttributeCount
0x180036126  xor     ecx, ecx; lpAttributeList
0x180036128  call    cs:__imp_InitializeProcThreadAttributeList
0x18003612e  call    cs:__imp_GetLastError
0x180036134  cmp     eax, 7Ah ; 'z'
0x180036137  jz      short loc_180036195
0x180036139  lea     rax, WPP_GLOBAL_Control
0x180036140  mov     rcx, cs:WPP_GLOBAL_Control
0x180036147  cmp     rcx, rax
0x18003614a  jz      short loc_180036167
0x18003614c  cmp     byte ptr [rcx+19h], 2
0x180036150  jb      short loc_180036167
0x180036152  mov     edx, 10h
0x180036157  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x18003615e  mov     rcx, [rcx+10h]
0x180036162  call    WPP_SF_
0x180036167  call    cs:__imp_GetLastError
0x18003616d  test    eax, eax
0x18003616f  jle     short loc_180036179
0x180036171  movzx   eax, ax
0x180036174  or      eax, 80070000h
0x180036179  mov     edx, eax; int
0x18003617b  lea     rcx, [rbp+3B0h+var_418]; this
0x18003617f  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180036184  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18003618b  lea     rcx, [rbp+3B0h+var_418]; pExceptionObject
0x18003618f  call    _CxxThrowException_0
0x180036195  mov     rcx, [rbp+3B0h+Size]; Size
0x180036199  call    cs:__imp_malloc
0x18003619f  mov     [rbp+3B0h+lpAttributeList], rax
0x1800361a3  test    rax, rax
0x1800361a6  jnz     short loc_180036225
0x1800361a8  lea     rax, WPP_GLOBAL_Control
0x1800361af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361b6  cmp     rcx, rax
0x1800361b9  jz      short loc_1800361DE
0x1800361bb  cmp     byte ptr [rcx+19h], 2
0x1800361bf  jb      short loc_1800361DE
0x1800361c1  mov     edx, 11h
0x1800361c6  lea     r9, aAttributes; "attributes"
0x1800361cd  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x1800361d4  mov     rcx, [rcx+10h]
0x1800361d8  call    WPP_SF_s
0x1800361dd  nop
0x1800361de  lea     rax, aBadAllocation; "bad allocation"
0x1800361e5  mov     [rbp+3B0h+var_2B0], rax
0x1800361ec  mov     r8d, r12d
0x1800361ef  lea     rdx, [rbp+3B0h+var_2B0]
0x1800361f6  lea     rcx, [rbp+3B0h+pExceptionObject]
0x1800361fd  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180036203  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18003620a  mov     [rbp+3B0h+pExceptionObject], rax
0x180036211  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180036218  lea     rcx, [rbp+3B0h+pExceptionObject]; pExceptionObject
0x18003621f  call    _CxxThrowException_0
0x180036225  mov     byte ptr [rbp+3B0h+pExceptionObject], 0
0x18003622c  lea     rcx, [rbp+3B0h+lpAttributeList]
0x180036230  mov     [rbp+3B0h+var_2A0], rcx
0x180036237  lea     r9, [rbp+3B0h+Size]; lpSize
0x18003623b  xor     r8d, r8d; dwFlags
0x18003623e  mov     edx, r12d; dwAttributeCount
0x180036241  mov     rcx, rax; lpAttributeList
0x180036244  call    cs:__imp_InitializeProcThreadAttributeList
0x18003624a  test    eax, eax
0x18003624c  jnz     short loc_1800362B0
0x18003624e  call    cs:__imp_GetLastError
0x180036254  mov     ebx, eax
0x180036256  lea     rax, WPP_GLOBAL_Control
0x18003625d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036264  cmp     rcx, rax
0x180036267  jz      short loc_180036287
0x180036269  cmp     byte ptr [rcx+19h], 2
0x18003626d  jb      short loc_180036287
0x18003626f  mov     edx, 12h
0x180036274  mov     r9d, ebx
0x180036277  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x18003627e  mov     rcx, [rcx+10h]
0x180036282  call    WPP_SF_d
0x180036287  test    ebx, ebx
0x180036289  jle     short loc_180036294
0x18003628b  movzx   ebx, bx
0x18003628e  or      ebx, 80070000h
0x180036294  mov     edx, ebx; int
0x180036296  lea     rcx, [rbp+3B0h+var_418]; this
0x18003629a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18003629f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800362a6  lea     rcx, [rbp+3B0h+var_418]; pExceptionObject
0x1800362aa  call    _CxxThrowException_0
0x1800362b0  mov     [rbp+3B0h+var_278], 0
0x1800362b7  lea     rax, [rbp+3B0h+lpAttributeList]
0x1800362bb  mov     [rbp+3B0h+var_270], rax
0x1800362c2  mov     [rsp+4B0h+lpReturnSize], 0; lpReturnSize
0x1800362cb  mov     [rsp+4B0h+lpPreviousValue], 0; lpPreviousValue
0x1800362d4  mov     esi, 8
0x1800362d9  mov     [rsp+4B0h+cbSize], rsi; cbSize
0x1800362de  lea     r9, [rbp+3B0h+Value]; lpValue
0x1800362e5  xor     edx, edx; dwFlags
0x1800362e7  mov     r8d, 20002h; Attribute
0x1800362ed  mov     rcx, [rbp+3B0h+lpAttributeList]; lpAttributeList
0x1800362f1  call    cs:__imp_UpdateProcThreadAttribute
0x1800362f7  test    eax, eax
0x1800362f9  jnz     short loc_18003635B
0x1800362fb  call    cs:__imp_GetLastError
0x180036301  mov     ebx, eax
0x180036303  lea     rax, WPP_GLOBAL_Control
0x18003630a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036311  cmp     rcx, rax
0x180036314  jz      short loc_180036332
0x180036316  cmp     byte ptr [rcx+19h], 2
0x18003631a  jb      short loc_180036332
0x18003631c  lea     edx, [rsi+0Bh]
0x18003631f  mov     r9d, ebx
0x180036322  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x180036329  mov     rcx, [rcx+10h]
0x18003632d  call    WPP_SF_d
0x180036332  test    ebx, ebx
0x180036334  jle     short loc_18003633F
0x180036336  movzx   ebx, bx
0x180036339  or      ebx, 80070000h
0x18003633f  mov     edx, ebx; int
0x180036341  lea     rcx, [rbp+3B0h+var_418]; this
0x180036345  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18003634a  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180036351  lea     rcx, [rbp+3B0h+var_418]; pExceptionObject
0x180036355  call    _CxxThrowException_0
0x18003635b  mov     qword ptr [rbp+3B0h+StartupInfo.cb], 70h ; 'p'
0x180036366  xor     edx, edx; Val
0x180036368  lea     r8d, [rdx+68h]; Size
0x18003636c  lea     rcx, [rbp+3B0h+StartupInfo.lpReserved]; void *
0x180036373  call    memset_0
0x180036378  xorps   xmm0, xmm0
0x18003637b  xor     eax, eax
0x18003637d  movups  xmmword ptr [rbp+3B0h+ProcessInformation.hProcess], xmm0
0x180036381  mov     qword ptr [rbp+3B0h+ProcessInformation.dwProcessId], rax
0x180036388  mov     rax, [rbp+3B0h+lpAttributeList]
0x18003638c  mov     [rbp+3B0h+var_2B8], rax
0x180036393  mov     rcx, rbx; Uuid
0x180036396  call    cs:__imp_UuidCreate
0x18003639c  mov     rdx, rbx
0x18003639f  lea     rcx, [rsp+78h]
0x1800363a4  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x1800363a9  mov     rbx, rax
0x1800363ac  cmp     [rax+18h], rsi
0x1800363b0  jb      short loc_1800363B5
0x1800363b2  mov     rbx, [rax]
0x1800363b5  lea     rcx, [rsp+50h]
0x1800363ba  call    GetPathToNotifyObjectHostExe
0x1800363bf  cmp     [rax+18h], rsi
0x1800363c3  jb      short loc_1800363C8
0x1800363c5  mov     rax, [rax]
0x1800363c8  mov     [rsp+4B0h+cbSize], rdi
0x1800363cd  mov     r9, rbx
0x1800363d0  mov     r8, rax
0x1800363d3  lea     rdx, aSWsIu; "%s %ws %Iu"
0x1800363da  lea     rcx, [rbp+3B0h+CommandLine]
0x1800363e1  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@_WPEB_WZZ; swprintf_s<260>(wchar_t (&)[260],wchar_t const *,...)
0x1800363e6  cmp     [rsp+4B0h+var_448], rsi
0x1800363eb  jb      short loc_1800363F7
0x1800363ed  mov     rcx, [rsp+50h]; Block
0x1800363f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800363f7  mov     [rsp+4B0h+var_448], 7
0x180036400  mov     [rsp+4B0h+var_450], 0
0x180036409  xor     eax, eax
0x18003640b  mov     [rsp+50h], ax
0x180036410  cmp     [rbp+3B0h+var_420], rsi
0x180036414  jb      short loc_180036420
0x180036416  mov     rcx, [rsp+78h]; Block
0x18003641b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036420  lea     rax, [rbp+3B0h+ProcessInformation]
0x180036424  mov     [rsp+4B0h+lpProcessInformation], rax; lpProcessInformation
0x180036429  lea     rax, [rbp+3B0h+StartupInfo]
0x180036430  mov     [rsp+4B0h+lpStartupInfo], rax; lpStartupInfo
0x180036435  mov     [rsp+4B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003643e  mov     [rsp+4B0h+lpReturnSize], 0; lpEnvironment
0x180036447  mov     dword ptr [rsp+4B0h+lpPreviousValue], 80000h; dwCreationFlags
0x18003644f  mov     dword ptr [rsp+4B0h+cbSize], r12d; bInheritHandles
0x180036454  xor     r9d, r9d; lpThreadAttributes
0x180036457  xor     r8d, r8d; lpProcessAttributes
0x18003645a  lea     rdx, [rbp+3B0h+CommandLine]; lpCommandLine
0x180036461  xor     ecx, ecx; lpApplicationName
0x180036463  call    cs:__imp_CreateProcessW
0x180036469  test    eax, eax
0x18003646b  jnz     short loc_1800364D7
0x18003646d  call    cs:__imp_GetLastError
0x180036473  mov     ebx, eax
0x180036475  lea     rax, WPP_GLOBAL_Control
0x18003647c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036483  cmp     rcx, rax
0x180036486  jz      short loc_1800364AE
0x180036488  cmp     byte ptr [rcx+19h], 2
0x18003648c  jb      short loc_1800364AE
0x18003648e  mov     edx, 14h
0x180036493  mov     dword ptr [rsp+4B0h+cbSize], ebx
0x180036497  lea     r9, [rbp+3B0h+CommandLine]
0x18003649e  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x1800364a5  mov     rcx, [rcx+10h]
0x1800364a9  call    WPP_SF_Sd
0x1800364ae  test    ebx, ebx
0x1800364b0  jle     short loc_1800364BB
0x1800364b2  movzx   ebx, bx
0x1800364b5  or      ebx, 80070000h
0x1800364bb  mov     edx, ebx; int
0x1800364bd  lea     rcx, [rbp+3B0h+var_418]; this
0x1800364c1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800364c6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800364cd  lea     rcx, [rbp+3B0h+var_418]; pExceptionObject
0x1800364d1  call    _CxxThrowException_0
0x1800364d7  mov     rcx, [rbp+3B0h+ProcessInformation.hThread]; hObject
0x1800364de  call    cs:__imp_CloseHandle
0x1800364e4  mov     rbx, [rbp+3B0h+ProcessInformation.hProcess]
0x1800364e8  mov     [rbp+3B0h+var_2B0], rbx
0x1800364ef  mov     [rbp+3B0h+Handles], rdi
0x1800364f6  mov     [rbp+3B0h+var_250], rbx
0x1800364fd  mov     dword ptr [rsp+4B0h+cbSize], 0; bAlertable
0x180036505  mov     r9d, 0EA60h; dwMilliseconds
0x18003650b  xor     r8d, r8d; bWaitAll
0x18003650e  lea     rdx, [rbp+3B0h+Handles]; lpHandles
0x180036515  lea     ecx, [r8+2]; nCount
0x180036519  call    cs:__imp_WaitForMultipleObjectsEx
0x18003651f  mov     esi, eax
0x180036521  test    eax, eax
0x180036523  jz      loc_180036645
0x180036529  cmp     eax, r12d
0x18003652c  jz      loc_1800365F8
0x180036532  cmp     eax, 102h
0x180036537  jz      short loc_18003659D
0x180036539  cmp     eax, 0FFFFFFFFh
0x18003653c  jnz     short loc_180036546
0x18003653e  call    cs:__imp_GetLastError
0x180036544  mov     esi, eax
0x180036546  lea     rax, WPP_GLOBAL_Control
0x18003654d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036554  cmp     rcx, rax
0x180036557  jz      short loc_180036574
0x180036559  cmp     byte ptr [rcx+19h], 2
0x18003655d  jb      short loc_180036574
0x18003655f  mov     edx, 17h
0x180036564  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x18003656b  mov     rcx, [rcx+10h]
0x18003656f  call    WPP_SF_
0x180036574  test    esi, esi
0x180036576  jle     short loc_180036581
0x180036578  movzx   esi, si
0x18003657b  or      esi, 80070000h
  ... truncated ...
```
