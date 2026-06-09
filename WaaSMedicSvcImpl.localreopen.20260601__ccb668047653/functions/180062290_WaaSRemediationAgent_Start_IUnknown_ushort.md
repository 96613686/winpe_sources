# WaaSRemediationAgent::Start(IUnknown *,ushort *)

- ea: `0x180062290`
- end: `0x1800627f1`
- name: `?Start@WaaSRemediationAgent@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `1377`
- prototype: `__int64 __fastcall(WaaSRemediationAgent *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18002a32c`
- `0x18002e81c`
- `0x18005200c`
- `0x180054bc4`
- `0x180061440`
- `0x180062290`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800627da`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800627ea`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800627da`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800627ea`
- `msvcp_win!_Thrd_detach` at `0x180062721`
- `msvcp_win!_Thrd_detach` at `0x180062721`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800624f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062535`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062573`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800624f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062535`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062573`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800626f7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800626f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800622d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800622d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006269e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006269e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062756`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006276c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006276c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006236f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006265c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006268b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006236f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006265c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006268b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062745`
- `OLEAUT32!__imp_SysStringLen` at `0x180062499`
- `OLEAUT32!__imp_SysStringLen` at `0x180062499`

## string_xrefs

- `0x18006263c`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x1800625cf`: `Failed to execute Waas medic launch remediation on a thread. hr = 0x%08x`
- `0x180062474`: `TaskHandler`
- `0x1800622fb`: `WaaS remediation agent received request to start remediation task.`
- `0x1800623d3`: `Remediation agent is handling service shutdown and cannot process the start request.`
- `0x1800623ea`: `Remediation agent is currently in progress.`
- `0x18006231a`: `Remediation agent start received an invalid task handler pointer.`
- `0x1800623bc`: `Remediation agent is unexpectedly not initialized`
- `0x1800624cb`: `Caller info passed by Task Scheduler: %s`
- `0x18006245f`: `Failed to set task handler status. hr = 0x%08x`
- `0x1800627a0`: `Task handler start thread was signaled!`
- `0x180062797`: `Task handler start thread abandoned the thread inited handle!`
- `0x180062784`: `Failed to wait for the task handler start thread! hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaaSRemediationAgent::Start(WaaSRemediationAgent *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  char *v6; // r14
  signed int inited; // ebx
  __int64 v8; // rcx
  char *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  unsigned int *v14; // r8
  unsigned int v15; // r9d
  UINT v16; // eax
  _Thrd_t *Hnd; // r8
  _Thrd_t *v18; // rdx
  _Thrd_t *v19; // rdx
  _Thrd_t *v20; // rdx
  int v21; // eax
  unsigned __int16 **v22; // r8
  int v23; // eax
  unsigned int v24; // r15d
  _QWORD *v25; // rax
  DWORD v26; // eax
  signed int LastError; // eax
  int v28; // [rsp+20h] [rbp-99h]
  __int128 Parameter; // [rsp+30h] [rbp-89h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-79h]
  WaasMedic *v31[2]; // [rsp+48h] [rbp-71h]
  char *v32; // [rsp+58h] [rbp-61h]
  _BYTE v33[16]; // [rsp+60h] [rbp-59h] BYREF
  HANDLE v34; // [rsp+70h] [rbp-49h]
  unsigned __int16 v35; // [rsp+78h] [rbp-41h] BYREF
  int v36; // [rsp+80h] [rbp-39h]
  _Thrd_t v37; // [rsp+90h] [rbp-29h] BYREF
  __int128 *p_Parameter; // [rsp+A0h] [rbp-19h]
  char v39; // [rsp+A8h] [rbp-11h]
  int v40; // [rsp+ACh] [rbp-Dh]
  _Thrd_t v41; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v42; // [rsp+C0h] [rbp+7h]
  unsigned __int64 v43; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v6 = (char *)this + 56;
  v32 = (char *)this + 56;
  if ( this != (WaaSRemediationAgent *)-56LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  Parameter = 0;
  hObject = 0;
  *(_OWORD *)v31 = 0;
  p_Parameter = &Parameter;
  v39 = 1;
  LogLevelW(4u, L"WaaS remediation agent received request to start remediation task.");
  if ( !a2 )
  {
    inited = -2147467261;
    LogLevelW(2u, L"Remediation agent start received an invalid task handler pointer.");
    goto LABEL_5;
  }
  if ( !*((_BYTE *)this + 112) )
  {
    inited = -2147418113;
    LogLevelW(2u, L"Remediation agent is unexpectedly not initialized");
    goto LABEL_5;
  }
  if ( *((_BYTE *)this + 114) )
  {
    inited = -2147024846;
    LogLevelW(2u, L"Remediation agent is handling service shutdown and cannot process the start request.");
    goto LABEL_5;
  }
  if ( *((_BYTE *)this + 113) )
  {
    inited = -2147024567;
    LogLevelW(2u, L"Remediation agent is currently in progress.");
    goto LABEL_5;
  }
  v10 = (char *)this - 16;
  v11 = WaaSRemediationAgent::SetAndExtendCV((WaaSRemediationAgent *)((char *)this - 16), 0);
  inited = v11;
  if ( v11 < 0 )
  {
    LogLevelW(2u, L"Failed to set and extend CV for LaunchRemediation. hr = 0x%08x", (unsigned int)v11);
    goto LABEL_5;
  }
  v12 = *((_QWORD *)v10 + 18);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)v10 + 18) = 0;
  }
  v13 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
          v10 + 144);
  inited = v13;
  if ( v13 < 0 )
  {
    LogLevelW(2u, L"Failed to set task handler status. hr = 0x%08x", (unsigned int)v13);
    goto LABEL_5;
  }
  inited = InitAsyncParams(
             (WaaSRemediationAgent *)((char *)this - 16),
             L"TaskHandler",
             *((struct TraceLoggingCorrelationVector **)this + 18),
             (struct WaasMedic::tagLaunchRemediationAsyncParams *)&Parameter);
  if ( inited < 0 )
  {
LABEL_5:
    v8 = *((_QWORD *)this + 16);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 16) = 0;
    }
    goto LABEL_7;
  }
  if ( a3 )
  {
    v16 = SysStringLen(a3);
    v41 = 0;
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v41, a3, v16);
    Hnd = &v41;
    if ( v43 > 7 )
      Hnd = (_Thrd_t *)v41._Hnd;
    LogLevelW(4u, L"Caller info passed by Task Scheduler: %s", Hnd);
    v18 = &v41;
    if ( v43 > 7 )
      v18 = (_Thrd_t *)v41._Hnd;
    if ( (unsigned int)_o__wcsicmp(L"MaintenanceWork", v18) )
    {
      v19 = &v41;
      if ( v43 > 7 )
        v19 = (_Thrd_t *)v41._Hnd;
      if ( (unsigned int)_o__wcsicmp(L"DeferralWork", v19) )
      {
        v20 = &v41;
        if ( v43 > 7 )
          v20 = (_Thrd_t *)v41._Hnd;
        if ( !(unsigned int)_o__wcsicmp(L"None", v20) )
          LogLevelW(4u, L"Found %s parameter. Leaving run mode to default (unset).", L"None");
      }
      else
      {
        LogLevelW(4u, L"Found %s parameter. Setting the run mode to deferral (mode %d).", L"DeferralWork", 4);
        LODWORD(v31[1]) = 4;
      }
    }
    else
    {
      LogLevelW(4u, L"Found %s parameter. Setting the run mode to maintenance (mode %d).", L"MaintenanceWork", 3);
      LODWORD(v31[1]) = 3;
    }
    std::wstring::~wstring(&v41);
  }
  if ( (unsigned int)(LODWORD(v31[1]) - 3) > 1 )
  {
    v21 = WaaSRemediationAgent::ExecuteProcOnThread(
            (LPTHREAD_START_ROUTINE)TaskHandlerStartThreadHelper,
            &Parameter,
            v14,
            v15,
            0);
    inited = v21;
    if ( v21 < 0 )
    {
      LogLevelW(2u, L"Failed to execute Waas medic launch remediation on a thread. hr = 0x%08x", (unsigned int)v21);
      goto LABEL_5;
    }
LABEL_64:
    v26 = WaitForSingleObject(hObject, 0xFFFFFFFF);
    if ( v26 )
    {
      if ( v26 == 128 )
      {
        LogLevelW(4u, L"Task handler start thread abandoned the thread inited handle!");
      }
      else if ( v26 == -1 )
      {
        LastError = GetLastError();
        inited = LastError;
        if ( LastError > 0 )
          inited = (unsigned __int16)LastError | 0x80070000;
        LogLevelW(2u, L"Failed to wait for the task handler start thread! hr=0x%08X", (unsigned int)inited);
        goto LABEL_75;
      }
    }
    else
    {
      LogLevelW(4u, L"Task handler start thread was signaled!");
    }
    if ( v10[128] && !v10[129] )
      v10[129] = 1;
LABEL_75:
    if ( inited >= 0 )
    {
LABEL_7:
      if ( (_QWORD)Parameter )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter + 16LL))(Parameter);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      hObject = 0;
      if ( v6 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
      return (unsigned int)inited;
    }
    goto LABEL_5;
  }
  v34 = 0;
  inited = (**(__int64 (__fastcall ***)(char *, GUID *, _BYTE *))v10)((char *)this - 16, &IID_IUnknown, v33);
  if ( inited < 0 )
  {
    if ( (char *)v34 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v34);
    goto LABEL_5;
  }
  v36 = (int)v31[1];
  v23 = WaasMedic::SafeAllocString(v31[0], &v35, v22);
  v24 = v23;
  if ( v23 >= 0 )
  {
    v25 = operator new(0x20u);
    *v25 = &Parameter;
    v25[1] = v10;
    v25[2] = WaaSRemediationAgent::LaunchMaintenanceRun;
    *((_DWORD *)v25 + 6) = 0;
    *((_DWORD *)v25 + 7) = v40;
    v37._Hnd = v25;
    v41._Hnd = (void *)_o__beginthreadex(
                         0,
                         0,
                         std::thread::_Invoke<std::tuple<long (WaaSRemediationAgent::*)(WaasMedic::tagLaunchRemediationAsyncParams *),WaaSRemediationAgent *,WaasMedic::tagLaunchRemediationAsyncParams *>,0,1,2>,
                         v25,
                         0,
                         &v41._Id);
    if ( v41._Hnd )
    {
      if ( v41._Id )
      {
        v37 = v41;
        if ( !_Thrd_detach(&v37) )
        {
          v41 = 0;
          if ( (char *)v34 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v34);
          goto LABEL_64;
        }
      }
      std::_Throw_Cpp_error(1);
    }
    v41._Id = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x1800627F0LL);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BA,
    (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
    (const char *)(unsigned int)v23,
    v28);
  if ( (char *)v34 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v34);
  v34 = 0;
  if ( (_QWORD)Parameter )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = 0;
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
  return v24;
}

```

## disassembly

```asm
0x180062290  mov     [rsp-8+arg_18], rbx
0x180062295  push    rbp
0x180062296  push    rsi
0x180062297  push    rdi
0x180062298  push    r12
0x18006229a  push    r13
0x18006229c  push    r14
0x18006229e  push    r15
0x1800622a0  lea     rbp, [rsp-27h]
0x1800622a5  sub     rsp, 0E0h
0x1800622ac  mov     rax, cs:__security_cookie
0x1800622b3  xor     rax, rsp
0x1800622b6  mov     [rbp+57h+var_40], rax
0x1800622ba  mov     r12, r8
0x1800622bd  mov     r15, rdx
0x1800622c0  mov     rsi, rcx
0x1800622c3  xor     r13d, r13d
0x1800622c6  lea     r14, [rcx+38h]
0x1800622ca  mov     [rbp+57h+var_B8], r14
0x1800622ce  test    r14, r14
0x1800622d1  jz      short loc_1800622DE
0x1800622d3  lea     rcx, [r14+10h]; lpCriticalSection
0x1800622d7  call    cs:__imp_EnterCriticalSection
0x1800622dd  nop
0x1800622de  xorps   xmm0, xmm0
0x1800622e1  movups  [rsp+110h+Parameter], xmm0
0x1800622e6  mov     [rbp+57h+hObject], r13
0x1800622ea  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x1800622ee  lea     rax, [rsp+110h+Parameter]
0x1800622f3  mov     [rbp+57h+var_70], rax
0x1800622f7  mov     [rbp+57h+var_68], 1
0x1800622fb  lea     rdx, aWaasRemediatio_4; "WaaS remediation agent received request"...
0x180062302  mov     ecx, 4; unsigned __int8
0x180062307  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006230c  test    r15, r15
0x18006230f  jnz     loc_1800623B1
0x180062315  mov     ebx, 80004003h
0x18006231a  lea     rdx, aRemediationAge_4; "Remediation agent start received an inv"...
0x180062321  mov     ecx, 2; unsigned __int8
0x180062326  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006232b  mov     rcx, [rsi+80h]
0x180062332  test    rcx, rcx
0x180062335  jz      short loc_18006234A
0x180062337  mov     rax, [rcx]
0x18006233a  mov     rax, [rax+10h]
0x18006233e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062343  mov     [rsi+80h], r13
0x18006234a  mov     rcx, qword ptr [rsp+110h+Parameter]
0x18006234f  test    rcx, rcx
0x180062352  jz      short loc_180062361
0x180062354  mov     rax, [rcx]
0x180062357  mov     rax, [rax+10h]
0x18006235b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062360  nop
0x180062361  mov     rcx, [rbp+57h+hObject]; hObject
0x180062365  lea     rax, [rcx-1]
0x180062369  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006236d  ja      short loc_180062375
0x18006236f  call    cs:__imp_CloseHandle
0x180062375  mov     [rbp+57h+hObject], r13
0x180062379  test    r14, r14
0x18006237c  jz      short loc_180062388
0x18006237e  lea     rcx, [r14+10h]; lpCriticalSection
0x180062382  call    cs:__imp_LeaveCriticalSection
0x180062388  mov     eax, ebx
0x18006238a  mov     rcx, [rbp+57h+var_40]
0x18006238e  xor     rcx, rsp; StackCookie
0x180062391  call    __security_check_cookie
0x180062396  mov     rbx, [rsp+110h+arg_18]
0x18006239e  add     rsp, 0E0h
0x1800623a5  pop     r15
0x1800623a7  pop     r14
0x1800623a9  pop     r13
0x1800623ab  pop     r12
0x1800623ad  pop     rdi
0x1800623ae  pop     rsi
0x1800623af  pop     rbp
0x1800623b0  retn
0x1800623b1  cmp     [rsi+70h], r13b
0x1800623b5  jnz     short loc_1800623C8
0x1800623b7  mov     ebx, 8000FFFFh
0x1800623bc  lea     rdx, aRemediationAge_8; "Remediation agent is unexpectedly not i"...
0x1800623c3  jmp     loc_180062321
0x1800623c8  cmp     [rsi+72h], r13b
0x1800623cc  jz      short loc_1800623DF
0x1800623ce  mov     ebx, 80070032h
0x1800623d3  lea     rdx, aRemediationAge; "Remediation agent is handling service s"...
0x1800623da  jmp     loc_180062321
0x1800623df  cmp     [rsi+71h], r13b
0x1800623e3  jz      short loc_1800623F6
0x1800623e5  mov     ebx, 80070149h
0x1800623ea  lea     rdx, aRemediationAge_5; "Remediation agent is currently in progr"...
0x1800623f1  jmp     loc_180062321
0x1800623f6  lea     rdi, [rsi-10h]
0x1800623fa  xor     edx, edx; char *
0x1800623fc  mov     rcx, rdi; this
0x1800623ff  call    ?SetAndExtendCV@WaaSRemediationAgent@@AEAAJPEBD@Z; WaaSRemediationAgent::SetAndExtendCV(char const *)
0x180062404  mov     ebx, eax
0x180062406  test    eax, eax
0x180062408  jns     short loc_180062423
0x18006240a  lea     rdx, aFailedToSetAnd_8; "Failed to set and extend CV for LaunchR"...
0x180062411  mov     r8d, eax
0x180062414  mov     ecx, 2; unsigned __int8
0x180062419  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006241e  jmp     loc_18006232B
0x180062423  lea     rbx, [rdi+90h]
0x18006242a  mov     rcx, [rbx]
0x18006242d  test    rcx, rcx
0x180062430  jz      short loc_180062441
0x180062432  mov     rax, [rcx]
0x180062435  mov     rax, [rax+10h]
0x180062439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006243e  mov     [rbx], r13
0x180062441  mov     rax, [r15]
0x180062444  mov     r8, rbx
0x180062447  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18006244e  mov     rcx, r15
0x180062451  mov     rax, [rax]
0x180062454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062459  mov     ebx, eax
0x18006245b  test    eax, eax
0x18006245d  jns     short loc_180062468
0x18006245f  lea     rdx, aFailedToSetTas_0; "Failed to set task handler status. hr ="...
0x180062466  jmp     short loc_180062411
0x180062468  lea     r9, [rsp+110h+Parameter]; struct WaasMedic::tagLaunchRemediationAsyncParams *
0x18006246d  mov     r8, [rsi+90h]; struct TraceLoggingCorrelationVector *
0x180062474  lea     rdx, aTaskhandler; "TaskHandler"
0x18006247b  mov     rcx, rdi; struct WaaSRemediationAgent *
0x18006247e  call    ?InitAsyncParams@@YAJPEAVWaaSRemediationAgent@@PEBGPEAVTraceLoggingCorrelationVector@@AEAUtagLaunchRemediationAsyncParams@WaasMedic@@@Z; InitAsyncParams(WaaSRemediationAgent *,ushort const *,TraceLoggingCorrelationVector *,WaasMedic::tagLaunchRemediationAsyncParams &)
0x180062483  mov     ebx, eax
0x180062485  test    eax, eax
0x180062487  js      loc_18006232B
0x18006248d  test    r12, r12
0x180062490  jz      loc_18006259E
0x180062496  mov     rcx, r12; pbstr
0x180062499  call    cs:__imp_SysStringLen
0x18006249f  mov     r8d, eax
0x1800624a2  xorps   xmm0, xmm0
0x1800624a5  movups  [rbp+57h+var_60], xmm0
0x1800624a9  mov     [rbp+57h+var_50], r13
0x1800624ad  mov     [rbp+57h+var_48], r13
0x1800624b1  mov     rdx, r12
0x1800624b4  lea     rcx, [rbp+57h+var_60]
0x1800624b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800624bd  lea     r8, [rbp+57h+var_60]
0x1800624c1  cmp     [rbp+57h+var_48], 7
0x1800624c6  cmova   r8, qword ptr [rbp+57h+var_60]
0x1800624cb  lea     rdx, aCallerInfoPass; "Caller info passed by Task Scheduler: %"...
0x1800624d2  mov     r12d, 4
0x1800624d8  mov     ecx, r12d; unsigned __int8
0x1800624db  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800624e0  lea     rdx, [rbp+57h+var_60]
0x1800624e4  cmp     [rbp+57h+var_48], 7
0x1800624e9  cmova   rdx, qword ptr [rbp+57h+var_60]
0x1800624ee  lea     rcx, aMaintenancewor; "MaintenanceWork"
0x1800624f5  call    cs:__imp__o__wcsicmp
0x1800624fb  test    eax, eax
0x1800624fd  jnz     short loc_180062520
0x1800624ff  lea     ebx, [rax+3]
0x180062502  mov     r9d, ebx
0x180062505  lea     r8, aMaintenancewor; "MaintenanceWork"
0x18006250c  lea     rdx, aFoundSParamete_1; "Found %s parameter. Setting the run mod"...
0x180062513  mov     ecx, r12d; unsigned __int8
0x180062516  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006251b  mov     dword ptr [rbp+57h+var_C8+8], ebx
0x18006251e  jmp     short loc_180062593
0x180062520  lea     rdx, [rbp+57h+var_60]
0x180062524  cmp     [rbp+57h+var_48], 7
0x180062529  cmova   rdx, qword ptr [rbp+57h+var_60]
0x18006252e  lea     rcx, aDeferralwork; "DeferralWork"
0x180062535  call    cs:__imp__o__wcsicmp
0x18006253b  test    eax, eax
0x18006253d  jnz     short loc_18006255E
0x18006253f  mov     r9d, r12d
0x180062542  lea     r8, aDeferralwork; "DeferralWork"
0x180062549  lea     rdx, aFoundSParamete_0; "Found %s parameter. Setting the run mod"...
0x180062550  mov     ecx, r12d; unsigned __int8
0x180062553  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062558  mov     dword ptr [rbp+57h+var_C8+8], r12d
0x18006255c  jmp     short loc_180062593
0x18006255e  lea     rdx, [rbp+57h+var_60]
0x180062562  cmp     [rbp+57h+var_48], 7
0x180062567  cmova   rdx, qword ptr [rbp+57h+var_60]
0x18006256c  lea     rcx, aNone; "None"
0x180062573  call    cs:__imp__o__wcsicmp
0x180062579  test    eax, eax
0x18006257b  jnz     short loc_180062593
0x18006257d  lea     r8, aNone; "None"
0x180062584  lea     rdx, aFoundSParamete; "Found %s parameter. Leaving run mode to"...
0x18006258b  mov     ecx, r12d; unsigned __int8
0x18006258e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062593  lea     rcx, [rbp+57h+var_60]; void *
0x180062597  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006259c  jmp     short loc_1800625A4
0x18006259e  mov     r12d, 4
0x1800625a4  mov     eax, dword ptr [rbp+57h+var_C8+8]
0x1800625a7  add     eax, 0FFFFFFFDh
0x1800625aa  cmp     eax, 1
0x1800625ad  jbe     short loc_1800625DB
0x1800625af  mov     [rsp+110h+var_F0], r13b; bool
0x1800625b4  lea     rdx, [rsp+110h+Parameter]; lpParameter
0x1800625b9  lea     rcx, ?TaskHandlerStartThreadHelper@@YAKPEAX@Z; lpStartAddress
0x1800625c0  call    ?ExecuteProcOnThread@WaaSRemediationAgent@@CAKP6AKPEAX@Z0PEAKK_N@Z; WaaSRemediationAgent::ExecuteProcOnThread(ulong (*)(void *),void *,ulong *,ulong,bool)
0x1800625c5  mov     ebx, eax
0x1800625c7  test    eax, eax
0x1800625c9  jns     loc_18006274B
0x1800625cf  lea     rdx, aFailedToExecut; "Failed to execute Waas medic launch rem"...
0x1800625d6  jmp     loc_180062411
0x1800625db  mov     [rbp+57h+var_A0], r13
0x1800625df  mov     rax, [rdi]
0x1800625e2  lea     r8, [rbp+57h+var_B0]
0x1800625e6  lea     rdx, IID_IUnknown
0x1800625ed  mov     rcx, rdi
0x1800625f0  mov     rax, [rax]
0x1800625f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625f8  mov     ebx, eax
0x1800625fa  test    eax, eax
0x1800625fc  jns     short loc_18006261B
0x1800625fe  mov     rcx, [rbp+57h+var_A0]; hObject
0x180062602  lea     rax, [rcx-1]
0x180062606  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006260a  ja      loc_18006232B
0x180062610  call    cs:__imp_CloseHandle
0x180062616  jmp     loc_18006232B
0x18006261b  mov     eax, dword ptr [rbp+57h+var_C8+8]
0x18006261e  mov     [rbp+57h+var_90], eax
0x180062621  lea     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x180062625  mov     rcx, [rbp+57h+var_C8]; this
0x180062629  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x18006262e  mov     r15d, eax
0x180062631  test    eax, eax
0x180062633  jns     short loc_1800626AC
0x180062635  mov     rcx, [rbp+5Fh]; this
0x180062639  mov     r9d, eax; char *
0x18006263c  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x180062643  mov     edx, 2BAh; void *
0x180062648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006264d  nop
0x18006264e  mov     rcx, [rbp+57h+var_A0]; hObject
0x180062652  lea     rdx, [rcx-1]
0x180062656  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18006265a  ja      short loc_180062662
0x18006265c  call    cs:__imp_CloseHandle
0x180062662  mov     [rbp+57h+var_A0], r13
0x180062666  mov     rcx, qword ptr [rsp+110h+Parameter]
0x18006266b  test    rcx, rcx
0x18006266e  jz      short loc_18006267D
0x180062670  mov     rax, [rcx]
0x180062673  mov     rax, [rax+10h]
0x180062677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006267c  nop
0x18006267d  mov     rcx, [rbp+57h+hObject]; hObject
0x180062681  lea     rax, [rcx-1]
0x180062685  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062689  ja      short loc_180062691
0x18006268b  call    cs:__imp_CloseHandle
0x180062691  mov     [rbp+57h+hObject], r13
0x180062695  test    r14, r14
0x180062698  jz      short loc_1800626A4
0x18006269a  lea     rcx, [r14+10h]; lpCriticalSection
0x18006269e  call    cs:__imp_LeaveCriticalSection
0x1800626a4  mov     eax, r15d
0x1800626a7  jmp     loc_18006238A
0x1800626ac  mov     ecx, 20h ; ' '; Size
0x1800626b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800626b6  lea     rcx, [rsp+110h+Parameter]
0x1800626bb  mov     [rax], rcx
0x1800626be  mov     [rax+8], rdi
0x1800626c2  lea     rcx, ?LaunchMaintenanceRun@WaaSRemediationAgent@@AEAAJPEAUtagLaunchRemediationAsyncParams@WaasMedic@@@Z; WaaSRemediationAgent::LaunchMaintenanceRun(WaasMedic::tagLaunchRemediationAsyncParams *)
0x1800626c9  mov     [rax+10h], rcx
0x1800626cd  mov     [rax+18h], r13d
0x1800626d1  mov     ecx, [rbp+57h+var_64]
0x1800626d4  mov     [rax+1Ch], ecx
0x1800626d7  mov     [rbp+57h+var_80._Hnd], rax
0x1800626db  lea     rcx, [rbp+57h+var_60+8]
0x1800626df  mov     [rsp+110h+var_E8], rcx
0x1800626e4  mov     dword ptr [rsp+110h+var_F0], r13d
0x1800626e9  mov     r9, rax
0x1800626ec  lea     r8, ??$_Invoke@V?$tuple@P8WaaSRemediationAgent@@EAAJPEAUtagLaunchRemediationAsyncParams@WaasMedic@@@ZPEAV1@PEAU23@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<long (WaaSRemediationAgent::*)(WaasMedic::tagLaunchRemediationAsyncParams *),WaaSRemediationAgent *,WaasMedic::tagLaunchRemediationAsyncParams *>,0,1,2>(void *)
0x1800626f3  xor     edx, edx
0x1800626f5  xor     ecx, ecx
0x1800626f7  call    cs:__imp__o__beginthreadex
0x1800626fd  mov     qword ptr [rbp+57h+var_60], rax
0x180062701  test    rax, rax
0x180062704  jz      loc_1800627E1
0x18006270a  cmp     dword ptr [rbp+57h+var_60+8], r13d
0x18006270e  jz      loc_1800627D5
0x180062714  movaps  xmm0, [rbp+57h+var_60]
0x180062718  movdqa  xmmword ptr [rbp+57h+var_80._Hnd], xmm0
0x18006271d  lea     rcx, [rbp+57h+var_80]; _Thrd_t
0x180062721  call    cs:__imp__Thrd_detach
0x180062727  test    eax, eax
0x180062729  jnz     loc_1800627D5
0x18006272f  xorps   xmm0, xmm0
0x180062732  movdqa  [rbp+57h+var_60], xmm0
0x180062737  mov     rcx, [rbp+57h+var_A0]; hObject
0x18006273b  lea     rax, [rcx-1]
0x18006273f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062743  ja      short loc_18006274B
0x180062745  call    cs:__imp_CloseHandle
  ... truncated ...
```
