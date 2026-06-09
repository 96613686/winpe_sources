# ServiceMain

- ea: `0x180015530`
- end: `0x18001585d`
- name: `ServiceMain`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180001008`
- `0x1800010f4`
- `0x1800049a0`
- `0x180014ac0`
- `0x180014f60`
- `0x180014ff8`
- `0x180015530`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800155dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800155dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001570b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157ff`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180015652`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180015652`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800157e8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800157e8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800156bf`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800156bf`

## string_xrefs

- `0x1800155f8`: `Service starting.`
- `0x1800155c1`: `ServiceMain`

## pseudocode

```c
signed int __fastcall ServiceMain(int a1, _QWORD *a2, int a3, int a4)
{
  int v5; // ebx
  BOOL v6; // eax
  signed int LastError; // eax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ecx
  signed int result; // eax
  signed int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  void *v17; // rcx
  int v18; // [rsp+40h] [rbp-19h] BYREF
  const char *v19; // [rsp+48h] [rbp-11h] BYREF
  const char *v20; // [rsp+50h] [rbp-9h] BYREF
  const char *v21; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp+7h] BYREF
  const char **v23; // [rsp+80h] [rbp+27h]
  __int64 v24; // [rsp+88h] [rbp+2Fh]

  v5 = a1;
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    a1 = 0;
    if ( (qword_18012F058 & 0x200000000000LL) != 0 && (qword_18012F060 & 0x200000000000LL) == qword_18012F060 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18012F048, qword_180119AD0, 0, 0, 2, v22);
  }
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v6 = v5 == 2 && !(unsigned int)_o__wcsicmp(a2[1], L"TriggerStarted");
    v18 = v6;
    v20 = "ServiceMain";
    v19 = "Service starting.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18011998B,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57457500>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_57457500>::GetImpl'::`2'::impl) )
  {
    v18 = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, &v18) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_18012F048 > 3 )
      {
        LODWORD(v19) = v10;
        v20 = "SetProcessMitigationPolicy failed to enable RedirectionGuard!";
        v21 = "ServiceMain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)byte_1801199E3,
          v8,
          v9,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v19);
      }
    }
  }
  hServiceStatus = RegisterServiceCtrlHandlerExW((LPCWSTR)*a2, ServiceHandler, 0);
  if ( hServiceStatus )
  {
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    ServiceStatus.dwServiceType = 32;
    *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
    UpdateServiceStatus(2u, 0, 0xBB8u);
    hObject = CreateEventW(0, 0, 0, 0);
    if ( hObject )
    {
      v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(qword_180133068 + 192))(
              &qword_180133000,
              *a2,
              hObject,
              StopService,
              0,
              24);
      v12 = v13;
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      if ( v12 >= 0 )
      {
        v12 = SvcInitialize(v15, v14, v16);
        if ( v12 >= 0 )
          return UpdateServiceStatus(4u, 0, 0);
      }
      goto LABEL_27;
    }
  }
  result = GetLastError();
  v12 = result;
  if ( result > 0 )
    v12 = (unsigned __int16)result | 0x80070000;
  if ( v12 < 0 )
  {
LABEL_27:
    if ( (unsigned int)dword_18012F048 > 5 )
    {
      LODWORD(v19) = v12;
      v23 = &v19;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18012F048, byte_180119943, 0, 0, 3, v22);
    }
    v17 = (void *)_InterlockedExchange64(&qword_180133000, 0);
    if ( v17 )
      UnregisterWaitEx(v17, 0);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    result = UpdateServiceStatus(1u, v12, 0);
    qword_180133068 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015530  mov     [rsp-8+arg_0], rbx
0x180015535  mov     [rsp-8+arg_10], rdi
0x18001553a  push    rbp
0x18001553b  push    r12
0x18001553d  push    r14
0x18001553f  lea     rbp, [rsp-47h]
0x180015544  sub     rsp, 0A0h
0x18001554b  mov     rax, cs:__security_cookie
0x180015552  xor     rax, rsp
0x180015555  mov     [rbp+57h+var_20], rax
0x180015559  mov     eax, cs:dword_18012F048
0x18001555f  mov     rdi, rdx
0x180015562  mov     ebx, ecx
0x180015564  cmp     eax, 5
0x180015567  jbe     short loc_1800155BB
0x180015569  mov     rdx, cs:qword_18012F060
0x180015570  mov     rcx, 200000000000h
0x18001557a  mov     rax, cs:qword_18012F058
0x180015581  test    rcx, rax
0x180015584  jz      short loc_1800155BB
0x180015586  mov     rax, rdx
0x180015589  and     rax, rcx
0x18001558c  cmp     rax, rdx
0x18001558f  jnz     short loc_1800155BB
0x180015591  lea     rax, [rbp+57h+var_50]
0x180015595  xor     r9d, r9d
0x180015598  mov     [rsp+0B0h+var_88], rax
0x18001559d  lea     rdx, qword_180119AD0
0x1800155a4  xor     r8d, r8d
0x1800155a7  mov     dword ptr [rsp+0B0h+var_90], 2
0x1800155af  lea     rcx, dword_18012F048
0x1800155b6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800155bb  mov     eax, cs:dword_18012F048
0x1800155c1  lea     r12, aServicemain_0; "ServiceMain"
0x1800155c8  cmp     eax, 5
0x1800155cb  jbe     short loc_180015627
0x1800155cd  cmp     ebx, 2
0x1800155d0  jnz     short loc_1800155EC
0x1800155d2  mov     rcx, [rdi+8]
0x1800155d6  lea     rdx, aTriggerstarted; "TriggerStarted"
0x1800155dd  call    cs:__imp__o__wcsicmp
0x1800155e3  test    eax, eax
0x1800155e5  jnz     short loc_1800155EC
0x1800155e7  lea     eax, [rbx-1]
0x1800155ea  jmp     short loc_1800155EE
0x1800155ec  xor     eax, eax
0x1800155ee  mov     [rbp+57h+var_70], eax
0x1800155f1  lea     rdx, byte_18011998B
0x1800155f8  lea     rax, aServiceStartin; "Service starting."
0x1800155ff  mov     [rbp+57h+var_60], r12
0x180015603  mov     [rbp+57h+var_68], rax
0x180015607  lea     rax, [rbp+57h+var_70]
0x18001560b  mov     [rsp+0B0h+var_80], rax
0x180015610  lea     rax, [rbp+57h+var_68]
0x180015614  mov     [rsp+0B0h+var_88], rax
0x180015619  lea     rax, [rbp+57h+var_60]
0x18001561d  mov     [rsp+0B0h+var_90], rax
0x180015622  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015627  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_57457500@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_57457500@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57457500> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_57457500>::GetImpl(void)'::`2'::impl
0x18001562e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_57457500@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57457500>::__private_IsEnabled(void)
0x180015633  mov     r14d, 80070000h
0x180015639  test    al, al
0x18001563b  jz      short loc_1800156B2
0x18001563d  mov     r8d, 4
0x180015643  mov     [rbp+57h+var_70], 1
0x18001564a  lea     rdx, [rbp+57h+var_70]
0x18001564e  lea     ecx, [r8+0Ch]
0x180015652  call    cs:__imp_SetProcessMitigationPolicy
0x180015658  test    eax, eax
0x18001565a  jnz     short loc_1800156B2
0x18001565c  call    cs:__imp_GetLastError
0x180015662  mov     ecx, eax
0x180015664  test    eax, eax
0x180015666  jle     short loc_18001566E
0x180015668  movzx   ecx, ax
0x18001566b  or      ecx, r14d
0x18001566e  mov     eax, cs:dword_18012F048
0x180015674  cmp     eax, 3
0x180015677  jbe     short loc_1800156B2
0x180015679  lea     rax, aSetprocessmiti; "SetProcessMitigationPolicy failed to en"...
0x180015680  mov     dword ptr [rbp+57h+var_68], ecx
0x180015683  mov     [rbp+57h+var_60], rax
0x180015687  lea     rdx, byte_1801199E3
0x18001568e  lea     rax, [rbp+57h+var_68]
0x180015692  mov     [rbp+57h+var_58], r12
0x180015696  mov     [rsp+0B0h+var_80], rax
0x18001569b  lea     rax, [rbp+57h+var_60]
0x18001569f  mov     [rsp+0B0h+var_88], rax
0x1800156a4  lea     rax, [rbp+57h+var_58]
0x1800156a8  mov     [rsp+0B0h+var_90], rax
0x1800156ad  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800156b2  mov     rcx, [rdi]; lpServiceName
0x1800156b5  lea     rdx, ServiceHandler; lpHandlerProc
0x1800156bc  xor     r8d, r8d; lpContext
0x1800156bf  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800156c5  mov     cs:hServiceStatus, rax
0x1800156cc  test    rax, rax
0x1800156cf  jz      short loc_180015720
0x1800156d1  xor     edx, edx; unsigned int
0x1800156d3  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x1800156de  xorps   xmm0, xmm0
0x1800156e1  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800156eb  mov     r8d, 0BB8h; unsigned int
0x1800156f1  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x1800156f9  lea     ecx, [rdx+2]; unsigned int
0x1800156fc  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180015701  xor     r9d, r9d; lpName
0x180015704  xor     r8d, r8d; bInitialState
0x180015707  xor     edx, edx; bManualReset
0x180015709  xor     ecx, ecx; lpEventAttributes
0x18001570b  call    cs:__imp_CreateEventW
0x180015711  mov     cs:hObject, rax
0x180015718  mov     r8, rax
0x18001571b  test    rax, rax
0x18001571e  jnz     short loc_18001573C
0x180015720  call    cs:__imp_GetLastError
0x180015726  mov     ebx, eax
0x180015728  test    eax, eax
0x18001572a  jle     short loc_180015732
0x18001572c  movzx   ebx, ax
0x18001572f  or      ebx, r14d
0x180015732  test    ebx, ebx
0x180015734  jns     loc_180015838
0x18001573a  jmp     short loc_180015790
0x18001573c  mov     rax, cs:qword_180133068
0x180015743  lea     r9, ?StopService@@YAXPEAXE@Z; StopService(void *,uchar)
0x18001574a  mov     rdx, [rdi]
0x18001574d  lea     rcx, qword_180133000
0x180015754  mov     dword ptr [rsp+0B0h+var_88], 18h
0x18001575c  mov     [rsp+0B0h+var_90], 0
0x180015765  mov     rax, [rax+0C0h]
0x18001576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015771  mov     ebx, eax
0x180015773  test    eax, eax
0x180015775  jle     short loc_18001577D
0x180015777  movzx   ebx, ax
0x18001577a  or      ebx, r14d
0x18001577d  test    ebx, ebx
0x18001577f  js      short loc_180015790
0x180015781  call    ?SvcInitialize@@YAJXZ; SvcInitialize(void)
0x180015786  mov     ebx, eax
0x180015788  test    eax, eax
0x18001578a  jns     loc_18001582B
0x180015790  mov     eax, cs:dword_18012F048
0x180015796  cmp     eax, 5
0x180015799  jbe     short loc_1800157D8
0x18001579b  lea     rax, [rbp+57h+var_68]
0x18001579f  mov     dword ptr [rbp+57h+var_68], ebx
0x1800157a2  mov     [rbp+57h+var_30], rax
0x1800157a6  lea     rdx, byte_180119943
0x1800157ad  lea     rax, [rbp+57h+var_50]
0x1800157b1  mov     [rbp+57h+var_28], 4
0x1800157b9  mov     [rsp+0B0h+var_88], rax
0x1800157be  lea     rcx, dword_18012F048
0x1800157c5  xor     r9d, r9d
0x1800157c8  mov     dword ptr [rsp+0B0h+var_90], 3
0x1800157d0  xor     r8d, r8d
0x1800157d3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800157d8  xor     ecx, ecx
0x1800157da  xchg    rcx, cs:qword_180133000; WaitHandle
0x1800157e1  test    rcx, rcx
0x1800157e4  jz      short loc_1800157EE
0x1800157e6  xor     edx, edx; CompletionEvent
0x1800157e8  call    cs:__imp_UnregisterWaitEx
0x1800157ee  mov     rcx, cs:hObject; hObject
0x1800157f5  lea     rax, [rcx-1]
0x1800157f9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800157fd  ja      short loc_180015810
0x1800157ff  call    cs:__imp_CloseHandle
0x180015805  mov     cs:hObject, 0
0x180015810  xor     r8d, r8d; unsigned int
0x180015813  mov     edx, ebx; unsigned int
0x180015815  lea     ecx, [r8+1]; unsigned int
0x180015819  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18001581e  mov     cs:qword_180133068, 0
0x180015829  jmp     short loc_180015838
0x18001582b  xor     edx, edx; unsigned int
0x18001582d  xor     r8d, r8d; unsigned int
0x180015830  lea     ecx, [rdx+4]; unsigned int
0x180015833  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180015838  mov     rcx, [rbp+57h+var_20]
0x18001583c  xor     rcx, rsp; StackCookie
0x18001583f  call    __security_check_cookie
0x180015844  lea     r11, [rsp+0B0h+var_10]
0x18001584c  mov     rbx, [r11+20h]
0x180015850  mov     rdi, [r11+30h]
0x180015854  mov     rsp, r11
0x180015857  pop     r14
0x180015859  pop     r12
0x18001585b  pop     rbp
0x18001585c  retn
```
