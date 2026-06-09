# CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)

- ea: `0x1400221f4`
- end: `0x1400225c3`
- name: `?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z`
- size: `975`
- prototype: `static int(void *, void *, unsigned int, unsigned int, enum _WER_DUMP_TYPE, unsigned int, struct _EXCEPTION_POINTERS *, struct HPSS__ *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400225cc`
- `0x140024924`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140005550`
- `0x140014f14`
- `0x140014f58`
- `0x1400166ec`
- `0x14001bf5c`
- `0x140020a1c`
- `0x1400221f4`
- `0x14002380c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002235d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002235d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002231f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002231f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002226a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002226a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022591`
- `wer!WerpAddMemoryBlock` at `0x140022546`
- `wer!WerpAddMemoryBlock` at `0x140022546`
- `wer!WerpGetExtendedDiagData` at `0x140022514`
- `wer!WerpGetExtendedDiagData` at `0x140022514`
- `wer!WerpAddRegisteredDataToReport` at `0x1400224cd`
- `wer!WerpAddRegisteredDataToReport` at `0x1400224cd`
- `wer!WerReportAddDump` at `0x140022452`
- `wer!WerReportAddDump` at `0x140022452`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHangReport::_AddWerDumpForProcess(
        void *a1,
        void *a2,
        unsigned int a3,
        DWORD a4,
        WER_DUMP_TYPE dumpType,
        DWORD dwFlags,
        struct _EXCEPTION_POINTERS *a7,
        struct HPSS__ *a8)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  void **v15; // rax
  int ProcessThreads; // eax
  unsigned int v17; // ebx
  CUserModeHangReport *v18; // rcx
  __int64 v19; // rdx
  DWORD v20; // esi
  HANDLE v21; // rax
  HANDLE v22; // rdx
  signed int LastError; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  HREPORT v26; // rbx
  int v27; // eax
  int v28; // eax
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  HREPORT hReportHandle; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  struct _WER_EXCEPTION_INFORMATION pExceptionParam; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[72]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v36; // [rsp+2B0h] [rbp+1B0h]

  hReportHandle = a1;
  pExceptionParam = 0;
  memset_0(v35, 0, 0x248u);
  hObject = 0;
  v33 = 0;
  v31 = 0;
  if ( a3 != GetProcessId(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a7->ExceptionRecord )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a7->ContextRecord )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  pExceptionParam.bClientPointers = 0;
  pExceptionParam.pExceptionPointers = a7;
  if ( a4 )
  {
    v21 = OpenThread(0x48u, 0, a4);
    v22 = hObject;
    hObject = v21;
    if ( (unsigned __int64)v22 + 1 > 1 )
    {
      CloseHandle(v22);
      v21 = hObject;
    }
    if ( (unsigned __int64)v21 + 1 <= 1 )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
      }
      goto LABEL_46;
    }
    v20 = -805306369;
  }
  else
  {
    v15 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    ProcessThreads = GetProcessThreads(a3, 0x48u, v15, 1u, 0);
    v17 = ProcessThreads;
    if ( ProcessThreads < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 101;
LABEL_12:
        WPP_SF_d(
          *((_QWORD *)v18 + 2),
          v19,
          WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
          (unsigned int)ProcessThreads);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
    v20 = -536870913;
    v21 = hObject;
  }
  ProcessThreads = CHangReport::SetHangExceptionInformation(v21, v20, a7);
  v17 = ProcessThreads;
  if ( ProcessThreads >= 0 )
  {
    v35[0] = 584;
    v35[71] = a8;
    v36 = a4;
    ProcessThreads = WerReportAddDump(
                       hReportHandle,
                       a2,
                       hObject,
                       dumpType,
                       &pExceptionParam,
                       (PWER_DUMP_CUSTOM_OPTIONS)((unsigned __int64)v35 & -(__int64)(a8 != 0)),
                       dwFlags);
    v17 = ProcessThreads;
    if ( ProcessThreads >= 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, a3, a4, a8, v20);
      }
      v26 = hReportHandle;
      v27 = WerpAddRegisteredDataToReport(hReportHandle, a2);
      if ( v27 < 0
        && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
          (unsigned int)v27);
      }
      if ( (int)WerpGetExtendedDiagData(a2, &v33, &v31) >= 0 )
      {
        if ( v33 )
        {
          if ( v31 )
          {
            v28 = WerpAddMemoryBlock(v26, a3);
            if ( v28 < 0
              && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                107,
                WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v28);
            }
          }
        }
      }
      v17 = 0;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 104;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 103;
      goto LABEL_12;
    }
  }
LABEL_46:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v17;
}

```

## disassembly

```asm
0x1400221f4  push    rbp
0x1400221f6  push    rbx
0x1400221f7  push    rsi
0x1400221f8  push    rdi
0x1400221f9  push    r12
0x1400221fb  push    r13
0x1400221fd  push    r14
0x1400221ff  push    r15
0x140022201  lea     rbp, [rsp-1D8h]
0x140022209  sub     rsp, 2D8h
0x140022210  mov     rax, cs:__security_cookie
0x140022217  xor     rax, rsp
0x14002221a  mov     [rbp+210h+var_50], rax
0x140022221  mov     r14d, r9d
0x140022224  mov     r13d, r8d
0x140022227  mov     r15, rdx
0x14002222a  mov     [rsp+310h+hReportHandle], rcx
0x14002222f  mov     rdi, [rbp+210h+arg_30]
0x140022236  mov     r12, [rbp+210h+arg_38]
0x14002223d  xorps   xmm0, xmm0
0x140022240  movups  xmmword ptr [rsp+310h+var_2B0.pExceptionPointers], xmm0
0x140022245  xor     edx, edx; Val
0x140022247  mov     r8d, 248h; Size
0x14002224d  lea     rcx, [rsp+310h+var_2A0]; void *
0x140022252  call    memset_0
0x140022257  xor     esi, esi
0x140022259  mov     [rsp+310h+hObject], rsi
0x14002225e  mov     [rsp+310h+var_2B8], rsi
0x140022263  mov     [rsp+310h+var_2C8], esi
0x140022267  mov     rcx, r15; Process
0x14002226a  call    cs:__imp_GetProcessId
0x140022271  nop     dword ptr [rax+rax+00h]
0x140022276  cmp     r13d, eax
0x140022279  jz      short loc_140022280
0x14002227b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140022280  cmp     [rdi], rsi
0x140022283  jnz     short loc_14002228A
0x140022285  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002228a  cmp     [rdi+8], rsi
0x14002228e  jnz     short loc_140022295
0x140022290  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140022295  mov     [rsp+310h+var_2B0.bClientPointers], esi
0x140022299  mov     [rsp+310h+var_2B0.pExceptionPointers], rdi
0x14002229e  test    r14d, r14d
0x1400222a1  jnz     short loc_140022317
0x1400222a3  lea     rcx, [rsp+310h+hObject]
0x1400222a8  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400222ad  mov     r8, rax; void **
0x1400222b0  mov     [rsp+310h+pExceptionParam], rsi; unsigned int *
0x1400222b5  lea     edx, [r14+48h]; unsigned int
0x1400222b9  lea     r9d, [r14+1]; unsigned int
0x1400222bd  mov     ecx, r13d; unsigned int
0x1400222c0  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x1400222c5  mov     ebx, eax
0x1400222c7  test    eax, eax
0x1400222c9  jns     short loc_140022308
0x1400222cb  lea     rdi, WPP_GLOBAL_Control
0x1400222d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400222d9  cmp     rcx, rdi
0x1400222dc  jz      loc_140022582
0x1400222e2  test    byte ptr [rcx+1Ch], 1
0x1400222e6  jz      loc_140022582
0x1400222ec  lea     edx, [r14+65h]
0x1400222f0  mov     r9d, eax
0x1400222f3  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400222fa  mov     rcx, [rcx+10h]
0x1400222fe  call    WPP_SF_d
0x140022303  jmp     loc_140022582
0x140022308  mov     esi, 0DFFFFFFFh
0x14002230d  mov     rax, [rsp+310h+hObject]
0x140022312  jmp     loc_1400223BF
0x140022317  mov     r8d, r14d; dwThreadId
0x14002231a  xor     edx, edx; bInheritHandle
0x14002231c  lea     ecx, [rdx+48h]; dwDesiredAccess
0x14002231f  call    cs:__imp_OpenThread
0x140022326  nop     dword ptr [rax+rax+00h]
0x14002232b  mov     rdx, [rsp+310h+hObject]
0x140022330  mov     [rsp+310h+hObject], rax
0x140022335  lea     rcx, [rdx+1]
0x140022339  cmp     rcx, 1
0x14002233d  jbe     short loc_140022353
0x14002233f  mov     rcx, rdx; hObject
0x140022342  call    cs:__imp_CloseHandle
0x140022349  nop     dword ptr [rax+rax+00h]
0x14002234e  mov     rax, [rsp+310h+hObject]
0x140022353  lea     rcx, [rax+1]
0x140022357  cmp     rcx, 1
0x14002235b  ja      short loc_1400223BA
0x14002235d  call    cs:__imp_GetLastError
0x140022364  nop     dword ptr [rax+rax+00h]
0x140022369  mov     ebx, eax
0x14002236b  test    eax, eax
0x14002236d  jle     short loc_140022378
0x14002236f  movzx   ebx, ax
0x140022372  or      ebx, 80070000h
0x140022378  lea     rdi, WPP_GLOBAL_Control
0x14002237f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022386  cmp     rcx, rdi
0x140022389  jz      loc_140022582
0x14002238f  test    byte ptr [rcx+1Ch], 1
0x140022393  jz      loc_140022582
0x140022399  mov     edx, 66h ; 'f'
0x14002239e  mov     dword ptr [rsp+310h+pExceptionParam], ebx
0x1400223a2  mov     r9d, r14d
0x1400223a5  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400223ac  mov     rcx, [rcx+10h]
0x1400223b0  call    WPP_SF_Dd
0x1400223b5  jmp     loc_140022582
0x1400223ba  mov     esi, 0CFFFFFFFh
0x1400223bf  mov     r8, rdi; struct _EXCEPTION_POINTERS *
0x1400223c2  mov     edx, esi; unsigned int
0x1400223c4  mov     rcx, rax; hThread
0x1400223c7  call    ?SetHangExceptionInformation@CHangReport@@CAJPEAXKPEAU_EXCEPTION_POINTERS@@@Z; CHangReport::SetHangExceptionInformation(void *,ulong,_EXCEPTION_POINTERS *)
0x1400223cc  mov     ebx, eax
0x1400223ce  test    eax, eax
0x1400223d0  jns     short loc_1400223FD
0x1400223d2  lea     rdi, WPP_GLOBAL_Control
0x1400223d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400223e0  cmp     rcx, rdi
0x1400223e3  jz      loc_140022582
0x1400223e9  test    byte ptr [rcx+1Ch], 1
0x1400223ed  jz      loc_140022582
0x1400223f3  mov     edx, 67h ; 'g'
0x1400223f8  jmp     loc_1400222F0
0x1400223fd  mov     [rsp+310h+var_2A0], 248h
0x140022406  mov     [rbp+210h+var_68], r12
0x14002240d  mov     [rbp+210h+var_60], r14d
0x140022414  mov     rax, r12
0x140022417  neg     rax
0x14002241a  sbb     rcx, rcx
0x14002241d  lea     rax, [rsp+310h+var_2A0]
0x140022422  and     rcx, rax
0x140022425  mov     eax, [rbp+210h+arg_28]
0x14002242b  mov     [rsp+310h+dwFlags], eax; dwFlags
0x14002242f  mov     [rsp+310h+pDumpCustomOptions], rcx; pDumpCustomOptions
0x140022434  lea     rax, [rsp+310h+var_2B0]
0x140022439  mov     [rsp+310h+pExceptionParam], rax; pExceptionParam
0x14002243e  mov     r9d, [rbp+210h+dumpType]; dumpType
0x140022445  mov     r8, [rsp+310h+hObject]; hThread
0x14002244a  mov     rdx, r15; hProcess
0x14002244d  mov     rcx, [rsp+310h+hReportHandle]; hReportHandle
0x140022452  call    cs:__imp_WerReportAddDump
0x140022459  nop     dword ptr [rax+rax+00h]
0x14002245e  mov     ebx, eax
0x140022460  test    eax, eax
0x140022462  jns     short loc_14002248F
0x140022464  lea     rdi, WPP_GLOBAL_Control
0x14002246b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022472  cmp     rcx, rdi
0x140022475  jz      loc_140022582
0x14002247b  test    byte ptr [rcx+1Ch], 1
0x14002247f  jz      loc_140022582
0x140022485  mov     edx, 68h ; 'h'
0x14002248a  jmp     loc_1400222F0
0x14002248f  lea     rdi, WPP_GLOBAL_Control
0x140022496  mov     rcx, cs:WPP_GLOBAL_Control
0x14002249d  cmp     rcx, rdi
0x1400224a0  jz      short loc_1400224C2
0x1400224a2  test    byte ptr [rcx+1Ch], 4
0x1400224a6  jz      short loc_1400224C2
0x1400224a8  mov     [rsp+310h+dwFlags], esi
0x1400224ac  mov     [rsp+310h+pDumpCustomOptions], r12
0x1400224b1  mov     dword ptr [rsp+310h+pExceptionParam], r14d
0x1400224b6  mov     r9d, r13d
0x1400224b9  mov     rcx, [rcx+10h]
0x1400224bd  call    WPP_SF_DDqD
0x1400224c2  mov     rdx, r15
0x1400224c5  mov     rbx, [rsp+310h+hReportHandle]
0x1400224ca  mov     rcx, rbx
0x1400224cd  call    cs:__imp_WerpAddRegisteredDataToReport
0x1400224d4  nop     dword ptr [rax+rax+00h]
0x1400224d9  test    eax, eax
0x1400224db  jns     short loc_140022507
0x1400224dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400224e4  cmp     rcx, rdi
0x1400224e7  jz      short loc_140022507
0x1400224e9  test    byte ptr [rcx+1Ch], 2
0x1400224ed  jz      short loc_140022507
0x1400224ef  mov     edx, 6Ah ; 'j'
0x1400224f4  mov     r9d, eax
0x1400224f7  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x1400224fe  mov     rcx, [rcx+10h]
0x140022502  call    WPP_SF_d
0x140022507  lea     r8, [rsp+310h+var_2C8]
0x14002250c  lea     rdx, [rsp+310h+var_2B8]
0x140022511  mov     rcx, r15
0x140022514  call    cs:__imp_WerpGetExtendedDiagData
0x14002251b  nop     dword ptr [rax+rax+00h]
0x140022520  test    eax, eax
0x140022522  js      short loc_140022580
0x140022524  mov     r8, [rsp+310h+var_2B8]
0x140022529  test    r8, r8
0x14002252c  jz      short loc_140022580
0x14002252e  mov     r9d, [rsp+310h+var_2C8]
0x140022533  test    r9d, r9d
0x140022536  jz      short loc_140022580
0x140022538  mov     dword ptr [rsp+310h+pExceptionParam], 0
0x140022540  mov     edx, r13d
0x140022543  mov     rcx, rbx
0x140022546  call    cs:__imp_WerpAddMemoryBlock
0x14002254d  nop     dword ptr [rax+rax+00h]
0x140022552  test    eax, eax
0x140022554  jns     short loc_140022580
0x140022556  mov     rcx, cs:WPP_GLOBAL_Control
0x14002255d  cmp     rcx, rdi
0x140022560  jz      short loc_140022580
0x140022562  test    byte ptr [rcx+1Ch], 2
0x140022566  jz      short loc_140022580
0x140022568  mov     edx, 6Bh ; 'k'
0x14002256d  mov     r9d, eax
0x140022570  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022577  mov     rcx, [rcx+10h]
0x14002257b  call    WPP_SF_d
0x140022580  xor     ebx, ebx
0x140022582  mov     rcx, [rsp+310h+hObject]; hObject
0x140022587  lea     rax, [rcx+1]
0x14002258b  cmp     rax, 1
0x14002258f  jbe     short loc_14002259D
0x140022591  call    cs:__imp_CloseHandle
0x140022598  nop     dword ptr [rax+rax+00h]
0x14002259d  mov     eax, ebx
0x14002259f  mov     rcx, [rbp+210h+var_50]
0x1400225a6  xor     rcx, rsp; StackCookie
0x1400225a9  call    __security_check_cookie
0x1400225ae  add     rsp, 2D8h
0x1400225b5  pop     r15
0x1400225b7  pop     r14
0x1400225b9  pop     r13
0x1400225bb  pop     r12
0x1400225bd  pop     rdi
0x1400225be  pop     rsi
0x1400225bf  pop     rbx
0x1400225c0  pop     rbp
0x1400225c1  retn
```
