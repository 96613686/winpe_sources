# CWorkflowSourceSession::LaunchWorkflowAppForPrinter(void)

- ea: `0x18001b100`
- end: `0x18001b5a2`
- name: `?LaunchWorkflowAppForPrinter@CWorkflowSourceSession@@UEAAJXZ`
- size: `1186`
- prototype: `__int64 __fastcall(CWorkflowSourceSession *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001614`
- `0x180001aa4`
- `0x180003ca0`
- `0x180008698`
- `0x180010b0c`
- `0x180012784`
- `0x180012820`
- `0x18001a85c`
- `0x18001a910`
- `0x18001abb8`
- `0x18001b100`
- `0x18001c114`
- `0x18001c3e8`
- `0x18001c9c4`
- `0x180022f14`
- `0x1800243c4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b4c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b4c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b2b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b2b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b55e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b55e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b4a9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b4a9`

## string_xrefs

- `0x18001b1b7`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsourcesession.cpp`
- `0x18001b252`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsourcesession.cpp`
- `0x18001b2df`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsourcesession.cpp`

## pseudocode

```c
__int64 __fastcall CWorkflowSourceSession::LaunchWorkflowAppForPrinter(CWorkflowSourceSession *this)
{
  _QWORD *v1; // r14
  int *v2; // rsi
  int v3; // r8d
  int v4; // r9d
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  int DebuggedOnLaunch; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  int WorkflowAppBackgroundTaskInfo; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rcx
  const WCHAR *v21; // rax
  const WCHAR *v22; // rdx
  __int64 v23; // r8
  int v24; // r8d
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  DWORD v28; // edx
  int v29; // r8d
  int v30; // r9d
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+28h] [rbp-D8h]
  _BYTE v34[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  int v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v40[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v41; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  _OWORD v43[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v44[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v45[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v46[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v1 = (_QWORD *)((char *)this + 24);
  v2 = (int *)((char *)this + 40);
  wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "LaunchWorkFlowAppActivity");
  v46[0] = &PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::`vftable';
  PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::StartActivity(v46, (unsigned int)*v2, v1);
  if ( (unsigned int)dword_180083038 > 5 )
  {
    v36[0] = *v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180083038,
      (unsigned int)&word_180070DC6,
      v3,
      v4,
      (__int64)v36);
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 120LL))(*v1);
  DebuggedOnLaunch = v5;
  if ( v5 >= 0 )
  {
    v40[0] = 1387304939;
    v40[1] = 1095466783;
    v40[2] = 882944905;
    v40[3] = -1908742531;
    if ( (unsigned int)dword_180083038 > 5 )
    {
      v36[0] = *v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180083038,
        (unsigned int)byte_180070D4D,
        v6,
        v7,
        (__int64)v36);
    }
    string = 0;
    v9 = *v1;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v1 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    DebuggedOnLaunch = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsourcesession.cpp",
        (const char *)(unsigned int)v11,
        v32);
LABEL_9:
      WindowsDeleteString(string);
LABEL_36:
      string = 0;
      goto LABEL_37;
    }
    v41 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v41) = 0;
    v43[0] = 0;
    v43[1] = si128;
    LOWORD(v43[0]) = 0;
    v44[0] = 0;
    v44[1] = si128;
    LOWORD(v44[0]) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    WorkflowAppBackgroundTaskInfo = GetWorkflowAppBackgroundTaskInfo(StringRawBuffer, &v41, v43, v44);
    DebuggedOnLaunch = WorkflowAppBackgroundTaskInfo;
    if ( WorkflowAppBackgroundTaskInfo >= 0 )
    {
      *(_QWORD *)v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v41);
      PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::AppId<unsigned short const *>(v46, v36);
      if ( (unsigned int)dword_180083038 > 5 )
      {
        v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
        v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v41);
        *(_QWORD *)&v45[0] = WindowsGetStringRawBuffer(string, 0);
        v36[0] = *v2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v16,
          (unsigned int)&unk_180070CA0,
          v17,
          v18,
          (__int64)v36,
          (__int64)v45,
          (__int64)&v39,
          (__int64)&v38);
      }
      v34[0] = 0;
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
      std::wstring::wstring(v45, v19);
      DebuggedOnLaunch = CWorkflowSourceSession::WillExecutableGetDebuggedOnLaunch(v20, v45, v34);
      std::wstring::_Tidy_deallocate(v45);
      if ( DebuggedOnLaunch < 0 )
      {
        v15 = (unsigned int)DebuggedOnLaunch;
        v14 = 109;
        goto LABEL_13;
      }
      v45[0] = 0;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
      v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v41);
      WorkflowAppBackgroundTaskInfo = ActivateBackgroundTaskAndGetId((__int64)v40, (__int64)v2, v23, v21, v22, v33, v45);
      DebuggedOnLaunch = WorkflowAppBackgroundTaskInfo;
      if ( WorkflowAppBackgroundTaskInfo >= 0 )
      {
        hHandle = 0;
        if ( (unsigned int)dword_180083038 > 5 )
        {
          v36[0] = *v2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180083038,
            (unsigned int)&dword_180070C2C,
            v24,
            v25,
            (__int64)v36);
        }
        WorkflowAppBackgroundTaskInfo = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(*(_QWORD *)*v1 + 224LL))(
                                          *v1,
                                          &hHandle);
        DebuggedOnLaunch = WorkflowAppBackgroundTaskInfo;
        if ( WorkflowAppBackgroundTaskInfo >= 0 )
        {
          if ( (unsigned int)dword_180083038 > 5 )
          {
            v36[0] = *v2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180083038,
              (unsigned int)word_180070BBA,
              v26,
              v27,
              (__int64)v36);
          }
          if ( IsDebuggerPresent() || (v28 = 60000, v34[0]) )
            v28 = -1;
          if ( !WaitForSingleObject(hHandle, v28) )
          {
            if ( (unsigned int)dword_180083038 > 5 )
            {
              v36[0] = *v2;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180083038,
                (unsigned int)&word_180070AE6,
                v29,
                v30,
                (__int64)v36);
            }
            wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v46);
            std::wstring::_Tidy_deallocate(v44);
            std::wstring::_Tidy_deallocate(v43);
            std::wstring::_Tidy_deallocate(&v41);
            WindowsDeleteString(string);
            DebuggedOnLaunch = 0;
            goto LABEL_36;
          }
          if ( (unsigned int)dword_180083038 > 5 )
          {
            v36[0] = *v2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180083038,
              (unsigned int)&unk_180070B40,
              v29,
              v30,
              (__int64)v36);
          }
          DebuggedOnLaunch = -2147467259;
          v15 = 2147500037LL;
          v14 = 144;
          goto LABEL_13;
        }
        v14 = 125;
      }
      else
      {
        v14 = 118;
      }
    }
    else
    {
      v14 = 96;
    }
    v15 = (unsigned int)WorkflowAppBackgroundTaskInfo;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsourcesession.cpp",
      (const char *)v15,
      v32);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::_Tidy_deallocate(&v41);
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4F,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsourcesession.cpp",
    (const char *)(unsigned int)v5,
    v32);
LABEL_37:
  PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::~LaunchWorkFlowAppActivity((PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity *)v46);
  return (unsigned int)DebuggedOnLaunch;
}

```

## disassembly

```asm
0x18001b100  mov     [rsp-8+arg_8], rbx
0x18001b105  mov     [rsp-8+arg_10], rsi
0x18001b10a  push    rbp
0x18001b10b  push    rdi
0x18001b10c  push    r13
0x18001b10e  push    r14
0x18001b110  push    r15
0x18001b112  lea     rbp, [rsp-160h]
0x18001b11a  sub     rsp, 260h
0x18001b121  mov     rax, cs:__security_cookie
0x18001b128  xor     rax, rsp
0x18001b12b  mov     [rbp+180h+var_30], rax
0x18001b132  lea     r14, [rcx+18h]
0x18001b136  lea     rsi, [rcx+28h]
0x18001b13a  lea     rdx, aLaunchworkflow; "LaunchWorkFlowAppActivity"
0x18001b141  lea     rcx, [rbp+180h+var_180]
0x18001b145  call    ??0?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001b14a  lea     rax, ??_7LaunchWorkFlowAppActivity@PrintWorkFlowTelemetry@@6B@; const PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::`vftable'
0x18001b151  mov     [rbp+180h+var_180], rax
0x18001b155  mov     r8, r14
0x18001b158  mov     edx, [rsi]
0x18001b15a  lea     rcx, [rbp+180h+var_180]
0x18001b15e  call    ?StartActivity@LaunchWorkFlowAppActivity@PrintWorkFlowTelemetry@@QEAAXKAEBV?$ComPtr@UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@WRL@Microsoft@@@Z; PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::StartActivity(ulong,Microsoft::WRL::ComPtr<Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession> const &)
0x18001b163  nop
0x18001b164  mov     eax, cs:dword_180083038
0x18001b16a  lea     r13, dword_180083038
0x18001b171  cmp     eax, 5
0x18001b174  jbe     short loc_18001B195
0x18001b176  mov     eax, [rsi]
0x18001b178  mov     [rsp+280h+var_230], eax
0x18001b17c  lea     rax, [rsp+280h+var_230]
0x18001b181  mov     qword ptr [rsp+280h+var_260], rax; int
0x18001b186  lea     rdx, word_180070DC6
0x18001b18d  mov     rcx, r13
0x18001b190  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b195  mov     rcx, [r14]
0x18001b198  mov     rax, [rcx]
0x18001b19b  mov     rax, [rax+78h]
0x18001b19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1a4  mov     ebx, eax
0x18001b1a6  xor     r15d, r15d
0x18001b1a9  test    eax, eax
0x18001b1ab  jns     short loc_18001B1CC
0x18001b1ad  mov     rcx, [rbp+188h]; this
0x18001b1b4  mov     r9d, eax; char *
0x18001b1b7  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\workflow"...
0x18001b1be  lea     edx, [r15+4Fh]; void *
0x18001b1c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1c7  jmp     loc_18001B56C
0x18001b1cc  mov     [rsp+280h+var_210], 52B097EBh
0x18001b1d4  mov     [rsp+280h+var_20C], 414B7F1Fh
0x18001b1dc  mov     [rsp+280h+var_208], 34A0AB89h
0x18001b1e4  mov     [rsp+280h+var_204], 8E3AE67Dh
0x18001b1ec  mov     eax, cs:dword_180083038
0x18001b1f2  cmp     eax, 5
0x18001b1f5  jbe     short loc_18001B216
0x18001b1f7  mov     eax, [rsi]
0x18001b1f9  mov     [rsp+280h+var_230], eax
0x18001b1fd  lea     rax, [rsp+280h+var_230]
0x18001b202  mov     qword ptr [rsp+280h+var_260], rax; int
0x18001b207  lea     rdx, byte_180070D4D
0x18001b20e  mov     rcx, r13
0x18001b211  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b216  mov     [rsp+280h+string], r15
0x18001b21b  mov     rdi, [r14]
0x18001b21e  mov     rax, [rdi]
0x18001b221  mov     rbx, [rax+30h]
0x18001b225  xor     ecx, ecx; string
0x18001b227  call    cs:__imp_WindowsDeleteString
0x18001b22d  mov     [rsp+280h+string], r15
0x18001b232  lea     rdx, [rsp+280h+string]
0x18001b237  mov     rcx, rdi
0x18001b23a  mov     rax, rbx
0x18001b23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b242  mov     ebx, eax
0x18001b244  test    eax, eax
0x18001b246  jns     short loc_18001B274
0x18001b248  mov     rcx, [rbp+188h]; this
0x18001b24f  mov     r9d, eax; char *
0x18001b252  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\workflow"...
0x18001b259  mov     edx, 5Bh ; '['; void *
0x18001b25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b263  nop
0x18001b264  mov     rcx, [rsp+280h+string]; string
0x18001b269  call    cs:__imp_WindowsDeleteString
0x18001b26f  jmp     loc_18001B567
0x18001b274  xorps   xmm0, xmm0
0x18001b277  movups  [rbp+180h+var_200], xmm0
0x18001b27b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b283  movdqu  [rbp+180h+var_1F0], xmm1
0x18001b288  mov     word ptr [rbp+180h+var_200], r15w
0x18001b28d  movups  [rbp+180h+var_1E0], xmm0
0x18001b291  movdqu  [rbp+180h+var_1D0], xmm1
0x18001b296  mov     word ptr [rbp+180h+var_1E0], r15w
0x18001b29b  movups  [rbp+180h+var_1C0], xmm0
0x18001b29f  movdqu  [rbp+180h+var_1B0], xmm1
0x18001b2a4  mov     word ptr [rbp+180h+var_1C0], r15w
0x18001b2a9  xor     edx, edx; length
0x18001b2ab  mov     rcx, [rsp+280h+string]; string
0x18001b2b0  call    cs:__imp_WindowsGetStringRawBuffer
0x18001b2b6  lea     r9, [rbp+180h+var_1C0]
0x18001b2ba  lea     r8, [rbp+180h+var_1E0]
0x18001b2be  lea     rdx, [rbp+180h+var_200]
0x18001b2c2  mov     rcx, rax
0x18001b2c5  call    ?GetWorkflowAppBackgroundTaskInfo@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; GetWorkflowAppBackgroundTaskInfo(ushort const *,std::wstring &,std::wstring &,std::wstring &)
0x18001b2ca  mov     ebx, eax
0x18001b2cc  test    eax, eax
0x18001b2ce  jns     short loc_18001B30E
0x18001b2d0  mov     edx, 60h ; '`'; void *
0x18001b2d5  mov     r9d, eax; char *
0x18001b2d8  mov     rcx, [rbp+188h]; this
0x18001b2df  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\workflow"...
0x18001b2e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b2eb  nop
0x18001b2ec  lea     rcx, [rbp+180h+var_1C0]
0x18001b2f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b2f5  nop
0x18001b2f6  lea     rcx, [rbp+180h+var_1E0]
0x18001b2fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b2ff  nop
0x18001b300  lea     rcx, [rbp+180h+var_200]
0x18001b304  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b309  jmp     loc_18001B264
0x18001b30e  lea     rcx, [rbp+180h+var_200]
0x18001b312  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b317  mov     qword ptr [rsp+280h+var_230], rax
0x18001b31c  lea     rdx, [rsp+280h+var_230]
0x18001b321  lea     rcx, [rbp+180h+var_180]
0x18001b325  call    ??$AppId@PEBG@LaunchWorkFlowAppActivity@PrintWorkFlowTelemetry@@QEAAX$$QEAPEBG@Z; PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::AppId<ushort const *>(ushort const * &&)
0x18001b32a  mov     eax, cs:dword_180083038
0x18001b330  cmp     eax, 5
0x18001b333  jbe     short loc_18001B39B
0x18001b335  lea     rcx, [rbp+180h+var_1E0]
0x18001b339  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b33e  mov     [rsp+280h+var_220], rax
0x18001b343  lea     rcx, [rbp+180h+var_200]
0x18001b347  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b34c  mov     [rsp+280h+var_218], rax
0x18001b351  xor     edx, edx; length
0x18001b353  mov     rcx, [rsp+280h+string]; string
0x18001b358  call    cs:__imp_WindowsGetStringRawBuffer
0x18001b35e  mov     qword ptr [rbp+180h+var_1A0], rax
0x18001b362  mov     eax, [rsi]
0x18001b364  mov     [rsp+280h+var_230], eax
0x18001b368  lea     rax, [rsp+280h+var_220]
0x18001b36d  mov     [rsp+280h+var_248], rax
0x18001b372  lea     rax, [rsp+280h+var_218]
0x18001b377  mov     [rsp+280h+var_250], rax
0x18001b37c  lea     rax, [rbp+180h+var_1A0]
0x18001b380  mov     [rsp+280h+var_258], rax
0x18001b385  lea     rax, [rsp+280h+var_230]
0x18001b38a  mov     qword ptr [rsp+280h+var_260], rax
0x18001b38f  lea     rdx, unk_180070CA0
0x18001b396  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001b39b  mov     [rsp+280h+var_240], r15b
0x18001b3a0  lea     rcx, [rbp+180h+var_1C0]
0x18001b3a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b3a9  mov     rdx, rax
0x18001b3ac  lea     rcx, [rbp+180h+var_1A0]
0x18001b3b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b3b5  lea     r8, [rsp+280h+var_240]
0x18001b3ba  lea     rdx, [rbp+180h+var_1A0]
0x18001b3be  call    ?WillExecutableGetDebuggedOnLaunch@CWorkflowSourceSession@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAE@Z; CWorkflowSourceSession::WillExecutableGetDebuggedOnLaunch(std::wstring const &,uchar &)
0x18001b3c3  mov     ebx, eax
0x18001b3c5  lea     rcx, [rbp+180h+var_1A0]
0x18001b3c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b3ce  test    ebx, ebx
0x18001b3d0  jns     short loc_18001B3DF
0x18001b3d2  mov     r9d, ebx
0x18001b3d5  mov     edx, 6Dh ; 'm'
0x18001b3da  jmp     loc_18001B2D8
0x18001b3df  xorps   xmm0, xmm0
0x18001b3e2  movups  [rbp+180h+var_1A0], xmm0
0x18001b3e6  lea     rcx, [rbp+180h+var_1E0]
0x18001b3ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b3ef  mov     rdx, rax
0x18001b3f2  lea     rcx, [rbp+180h+var_200]
0x18001b3f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b3fb  mov     r9, rax
0x18001b3fe  lea     rax, [rbp+180h+var_1A0]
0x18001b402  mov     [rsp+280h+var_250], rax
0x18001b407  mov     qword ptr [rsp+280h+var_260], rdx
0x18001b40c  mov     rdx, rsi
0x18001b40f  lea     rcx, [rsp+280h+var_210]
0x18001b414  call    ActivateBackgroundTaskAndGetId
0x18001b419  mov     ebx, eax
0x18001b41b  test    eax, eax
0x18001b41d  jns     short loc_18001B429
0x18001b41f  mov     edx, 76h ; 'v'
0x18001b424  jmp     loc_18001B2D5
0x18001b429  mov     [rsp+280h+hHandle], r15
0x18001b42e  mov     eax, cs:dword_180083038
0x18001b434  cmp     eax, 5
0x18001b437  jbe     short loc_18001B458
0x18001b439  mov     eax, [rsi]
0x18001b43b  mov     [rsp+280h+var_230], eax
0x18001b43f  lea     rax, [rsp+280h+var_230]
0x18001b444  mov     qword ptr [rsp+280h+var_260], rax
0x18001b449  lea     rdx, dword_180070C2C
0x18001b450  mov     rcx, r13
0x18001b453  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b458  mov     rcx, [r14]
0x18001b45b  mov     rax, [rcx]
0x18001b45e  lea     rdx, [rsp+280h+hHandle]
0x18001b463  mov     rax, [rax+0E0h]
0x18001b46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b46f  mov     ebx, eax
0x18001b471  test    eax, eax
0x18001b473  jns     short loc_18001B47F
0x18001b475  mov     edx, 7Dh ; '}'
0x18001b47a  jmp     loc_18001B2D5
0x18001b47f  mov     eax, cs:dword_180083038
0x18001b485  cmp     eax, 5
0x18001b488  jbe     short loc_18001B4A9
0x18001b48a  mov     eax, [rsi]
0x18001b48c  mov     [rsp+280h+var_230], eax
0x18001b490  lea     rax, [rsp+280h+var_230]
0x18001b495  mov     qword ptr [rsp+280h+var_260], rax
0x18001b49a  lea     rdx, word_180070BBA
0x18001b4a1  mov     rcx, r13
0x18001b4a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b4a9  call    cs:__imp_IsDebuggerPresent
0x18001b4af  test    eax, eax
0x18001b4b1  jnz     short loc_18001B4BF
0x18001b4b3  mov     edx, 0EA60h
0x18001b4b8  cmp     [rsp+280h+var_240], r15b
0x18001b4bd  jz      short loc_18001B4C2
0x18001b4bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b4c2  mov     rcx, [rsp+280h+hHandle]; hHandle
0x18001b4c7  call    cs:__imp_WaitForSingleObject
0x18001b4cd  test    eax, eax
0x18001b4cf  mov     eax, cs:dword_180083038
0x18001b4d5  jz      short loc_18001B50D
0x18001b4d7  cmp     eax, 5
0x18001b4da  jbe     short loc_18001B4FB
0x18001b4dc  mov     eax, [rsi]
0x18001b4de  mov     [rsp+280h+var_230], eax
0x18001b4e2  lea     rax, [rsp+280h+var_230]
0x18001b4e7  mov     qword ptr [rsp+280h+var_260], rax
0x18001b4ec  lea     rdx, unk_180070B40
0x18001b4f3  mov     rcx, r13
0x18001b4f6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b4fb  mov     ebx, 80004005h
0x18001b500  mov     r9d, ebx
0x18001b503  mov     edx, 90h
0x18001b508  jmp     loc_18001B2D8
0x18001b50d  cmp     eax, 5
0x18001b510  jbe     short loc_18001B531
0x18001b512  mov     eax, [rsi]
0x18001b514  mov     [rsp+280h+var_230], eax
0x18001b518  lea     rax, [rsp+280h+var_230]
0x18001b51d  mov     qword ptr [rsp+280h+var_260], rax
0x18001b522  lea     rdx, word_180070AE6
0x18001b529  mov     rcx, r13
0x18001b52c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001b531  lea     rcx, [rbp+180h+var_180]
0x18001b535  call    ?Stop@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b53a  nop
0x18001b53b  lea     rcx, [rbp+180h+var_1C0]
0x18001b53f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b544  nop
0x18001b545  lea     rcx, [rbp+180h+var_1E0]
0x18001b549  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b54e  nop
0x18001b54f  lea     rcx, [rbp+180h+var_200]
0x18001b553  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b558  nop
0x18001b559  mov     rcx, [rsp+280h+string]; string
0x18001b55e  call    cs:__imp_WindowsDeleteString
0x18001b564  mov     ebx, r15d
0x18001b567  mov     [rsp+280h+string], r15
0x18001b56c  lea     rcx, [rbp+180h+var_180]; this
0x18001b570  call    ??1LaunchWorkFlowAppActivity@PrintWorkFlowTelemetry@@QEAA@XZ; PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::~LaunchWorkFlowAppActivity(void)
0x18001b575  mov     eax, ebx
0x18001b577  mov     rcx, [rbp+180h+var_30]
0x18001b57e  xor     rcx, rsp; StackCookie
0x18001b581  call    __security_check_cookie
0x18001b586  lea     r11, [rsp+280h+var_20]
0x18001b58e  mov     rbx, [r11+38h]
0x18001b592  mov     rsi, [r11+40h]
0x18001b596  mov     rsp, r11
0x18001b599  pop     r15
0x18001b59b  pop     r14
0x18001b59d  pop     r13
0x18001b59f  pop     rdi
0x18001b5a0  pop     rbp
0x18001b5a1  retn
```
