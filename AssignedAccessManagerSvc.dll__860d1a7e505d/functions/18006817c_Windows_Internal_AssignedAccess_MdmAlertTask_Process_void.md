# Windows::Internal::AssignedAccess::MdmAlertTask::Process(void)

- ea: `0x18006817c`
- end: `0x1800686ef`
- name: `?Process@MdmAlertTask@AssignedAccess@Internal@Windows@@QEAAJXZ`
- size: `1395`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800671a0`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000f54c`
- `0x180010c98`
- `0x180014a5c`
- `0x180014b00`
- `0x180022dd8`
- `0x18002da20`
- `0x180067510`
- `0x1800675e0`
- `0x180067718`
- `0x1800677bc`
- `0x1800678c0`
- `0x180067a90`
- `0x180067b70`
- `0x180067bbc`
- `0x180067c40`
- `0x180067c70`
- `0x18006817c`
- `0x1800686f8`
- `0x180068c00`
- `0x180069ca8`
- `0x180069e1c`
- `0x18006b0e4`
- `0x18006b1bc`
- `0x18006e7a0`
- `0x18006e93c`

## string_xrefs

- `0x1800681f2`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x18006820e`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x18006830c`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x180068376`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x1800683ef`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x180068566`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\mdmalerttask.cpp`
- `0x180068266`: `Microsoft-Windows-AssignedAccess-Trace`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::MdmAlertTask::Process(HANDLE *this)
{
  Windows::Internal::AssignedAccess::StatusRepository *v2; // rax
  unsigned int StatusEnabled; // ebx
  unsigned int v5; // edi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  int AlertDataList; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-348h]
  int v15; // [rsp+20h] [rbp-348h]
  Windows::Internal::AssignedAccess::EtwTraceSessionProcessor *v16; // [rsp+30h] [rbp-338h] BYREF
  __int64 v17; // [rsp+38h] [rbp-330h] BYREF
  __int128 v18; // [rsp+40h] [rbp-328h]
  _DWORD v19[4]; // [rsp+50h] [rbp-318h] BYREF
  _BYTE v20[144]; // [rsp+60h] [rbp-308h] BYREF
  _QWORD v21[10]; // [rsp+F0h] [rbp-278h] BYREF
  _BYTE Context[80]; // [rsp+140h] [rbp-228h] BYREF
  _BYTE v23[32]; // [rsp+190h] [rbp-1D8h] BYREF
  _BYTE v24[80]; // [rsp+1B0h] [rbp-1B8h] BYREF
  _BYTE v25[336]; // [rsp+200h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  AssignedAccessTelemetry::MdmTask_Process::MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
  v19[0] = 0;
  v2 = (Windows::Internal::AssignedAccess::StatusRepository *)Windows::Internal::AssignedAccess::StatusRepository::StatusRepository((Windows::Internal::AssignedAccess::StatusRepository *)v21);
  StatusEnabled = Windows::Internal::AssignedAccess::StatusRepository::GetStatusEnabled(
                    v2,
                    (enum Windows::Internal::AssignedAccess::StatusEnabled *)v19);
  Windows::Internal::AssignedAccess::StatusRepository::~StatusRepository((Windows::Internal::AssignedAccess::StatusRepository *)v21);
  if ( (StatusEnabled & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
      (const char *)StatusEnabled,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
      (const char *)StatusEnabled,
      v15);
    AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
    return StatusEnabled;
  }
  AssignedAccessTelemetry::MdmTask_Process::StatusConfiguration<enum Windows::Internal::AssignedAccess::StatusEnabled &>(
    v25,
    v19);
  v5 = v19[0];
  if ( (unsigned int)(v19[0] - 1) > 1 )
  {
    AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
    return 0;
  }
  std::wstring::wstring(v23, L"Microsoft-Windows-AssignedAccess-Trace");
  Windows::Internal::AssignedAccess::EtwTraceSessionProcessor::OpenRealtimeLogger(&v16, v23);
  std::wstring::_Tidy_deallocate(v23);
  v21[0] = off_18009CEC8;
  v21[1] = &v16;
  v21[7] = v21;
  Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::AutoRegisterWaitForSingleObject(Context, *this);
  Windows::Internal::AssignedAccess::XmlSerializer::XmlSerializer((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
  v6 = Windows::Internal::AssignedAccess::XmlSerializer::Initialize((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
      (const char *)(unsigned int)v6,
      v14);
    Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
    Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject((Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject *)Context);
    std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(&v16);
    AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
    return v7;
  }
  v8 = Windows::Internal::AssignedAccess::EtwTraceSessionProcessor::Process(
         v16,
         (struct Windows::Internal::AssignedAccess::IEtwTraceSessionCallback *)v20);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
      (const char *)(unsigned int)v8,
      v14);
    Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
    Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject((Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject *)Context);
    std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(&v16);
    AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
    return v9;
  }
  std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(&v17);
  AlertDataList = Windows::Internal::AssignedAccess::XmlSerializer::GetAlertDataList(v20, &v17);
  v11 = AlertDataList;
  if ( AlertDataList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
      (const char *)(unsigned int)AlertDataList,
      v14);
    if ( v17 )
    {
      std::_Destroy_range<std::allocator<std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(
        v17,
        v18);
      std::_Deallocate<16>(v17, 72 * ((*((_QWORD *)&v18 + 1) - v17) / 72));
      v17 = 0;
      v18 = 0;
    }
LABEL_12:
    Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
    Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject((Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject *)Context);
    std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(&v16);
    AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
    return v11;
  }
  if ( v17 == (_QWORD)v18 )
  {
    if ( v17 )
    {
      std::_Destroy_range<std::allocator<std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(
        v17,
        v18);
      std::_Deallocate<16>(v17, 72 * ((*((_QWORD *)&v18 + 1) - v17) / 72));
      v17 = 0;
      v18 = 0;
    }
  }
  else
  {
    std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>::tuple<std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>(
      v24,
      v18 - 72);
    v13 = Windows::Internal::AssignedAccess::MdmAlertTask::ProcessStatusPayload(v12, v5, v24);
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\mdmalerttask.cpp",
        (const char *)(unsigned int)v13,
        v14);
      std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(v24);
      if ( v17 )
      {
        std::_Destroy_range<std::allocator<std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(
          v17,
          v18);
        std::_Deallocate<16>(v17, 72 * ((*((_QWORD *)&v18 + 1) - v17) / 72));
        v17 = 0;
        v18 = 0;
      }
      goto LABEL_12;
    }
    wil::ActivityBase<AssignedAccessTelemetry,1,70368744177664,5,2048,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
    std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(v24);
    if ( v17 )
    {
      std::_Destroy_range<std::allocator<std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(
        v17,
        v18);
      std::_Deallocate<16>(v17, 72 * ((*((_QWORD *)&v18 + 1) - v17) / 72));
      v17 = 0;
      v18 = 0;
    }
  }
  Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer((Windows::Internal::AssignedAccess::XmlSerializer *)v20);
  Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject((Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject *)Context);
  std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(&v16);
  AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process((AssignedAccessTelemetry::MdmTask_Process *)v25);
  return 0;
}

```

## disassembly

```asm
0x18006817c  mov     [rsp+arg_8], rbx
0x180068181  mov     [rsp+arg_10], rsi
0x180068186  push    rdi
0x180068187  sub     rsp, 360h
0x18006818e  mov     rax, cs:__security_cookie
0x180068195  xor     rax, rsp
0x180068198  mov     [rsp+368h+var_18], rax
0x1800681a0  mov     rsi, rcx
0x1800681a3  lea     rcx, [rsp+368h+var_168]; this
0x1800681ab  call    ??$?0$$V@MdmTask_Process@AssignedAccessTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; AssignedAccessTelemetry::MdmTask_Process::MdmTask_Process(wistd::integral_constant<char,0>)
0x1800681b0  nop
0x1800681b1  mov     [rsp+368h+var_318], 0
0x1800681b9  lea     rcx, [rsp+368h+var_278]; this
0x1800681c1  call    ??0StatusRepository@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::StatusRepository::StatusRepository(void)
0x1800681c6  nop
0x1800681c7  lea     rdx, [rsp+368h+var_318]; enum Windows::Internal::AssignedAccess::StatusEnabled *
0x1800681cc  mov     rcx, rax; this
0x1800681cf  call    ?GetStatusEnabled@StatusRepository@AssignedAccess@Internal@Windows@@QEAAJAEAW4StatusEnabled@234@@Z; Windows::Internal::AssignedAccess::StatusRepository::GetStatusEnabled(Windows::Internal::AssignedAccess::StatusEnabled &)
0x1800681d4  mov     ebx, eax
0x1800681d6  lea     rcx, [rsp+368h+var_278]; this
0x1800681de  call    ??1StatusRepository@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::StatusRepository::~StatusRepository(void)
0x1800681e3  test    ebx, ebx
0x1800681e5  jns     short loc_180068234
0x1800681e7  mov     rcx, [rsp+368h]; this
0x1800681ef  mov     r9d, ebx; char *
0x1800681f2  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800681f9  mov     edx, 0B3h; void *
0x1800681fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068203  mov     rcx, [rsp+368h]; this
0x18006820b  mov     r9d, ebx; char *
0x18006820e  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180068215  mov     edx, 49h ; 'I'; void *
0x18006821a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006821f  nop
0x180068220  lea     rcx, [rsp+368h+var_168]; this
0x180068228  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x18006822d  mov     eax, ebx
0x18006822f  jmp     loc_1800686C9
0x180068234  lea     rdx, [rsp+368h+var_318]
0x180068239  lea     rcx, [rsp+368h+var_168]
0x180068241  call    ??$StatusConfiguration@AEAW4StatusEnabled@AssignedAccess@Internal@Windows@@@MdmTask_Process@AssignedAccessTelemetry@@QEAAXAEAW4StatusEnabled@AssignedAccess@Internal@Windows@@@Z; AssignedAccessTelemetry::MdmTask_Process::StatusConfiguration<Windows::Internal::AssignedAccess::StatusEnabled &>(Windows::Internal::AssignedAccess::StatusEnabled &)
0x180068246  mov     edi, [rsp+368h+var_318]
0x18006824a  lea     eax, [rdi-1]
0x18006824d  cmp     eax, 1
0x180068250  jbe     short loc_180068266
0x180068252  lea     rcx, [rsp+368h+var_168]; this
0x18006825a  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x18006825f  xor     eax, eax
0x180068261  jmp     loc_1800686C9
0x180068266  lea     rdx, aMicrosoftWindo_4; "Microsoft-Windows-AssignedAccess-Trace"
0x18006826d  lea     rcx, [rsp+368h+var_1D8]
0x180068275  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006827a  nop
0x18006827b  lea     rdx, [rsp+368h+var_1D8]
0x180068283  lea     rcx, [rsp+368h+var_338]
0x180068288  call    ?OpenRealtimeLogger@EtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; Windows::Internal::AssignedAccess::EtwTraceSessionProcessor::OpenRealtimeLogger(std::wstring const &)
0x18006828d  nop
0x18006828e  lea     rcx, [rsp+368h+var_1D8]
0x180068296  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006829b  lea     rax, off_18009CEC8
0x1800682a2  mov     [rsp+368h+var_278], rax
0x1800682aa  lea     rax, [rsp+368h+var_338]
0x1800682af  mov     [rsp+368h+var_270], rax
0x1800682b7  lea     rax, [rsp+368h+var_278]
0x1800682bf  mov     [rsp+368h+var_240], rax
0x1800682c7  mov     r9d, 7530h
0x1800682cd  lea     r8, [rsp+368h+var_278]
0x1800682d5  mov     rdx, [rsi]; hObject
0x1800682d8  lea     rcx, [rsp+368h+Context]; Context
0x1800682e0  call    ??0AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@PEAXV?$function@$$A6AX_N@Z@std@@KK@Z; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::AutoRegisterWaitForSingleObject(void *,std::function<void (bool)>,ulong,ulong)
0x1800682e5  nop
0x1800682e6  lea     rcx, [rsp+368h+var_308]; this
0x1800682eb  call    ??0XmlSerializer@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::XmlSerializer(void)
0x1800682f0  nop
0x1800682f1  lea     rcx, [rsp+368h+var_308]; this
0x1800682f6  call    ?Initialize@XmlSerializer@AssignedAccess@Internal@Windows@@QEAAJXZ; Windows::Internal::AssignedAccess::XmlSerializer::Initialize(void)
0x1800682fb  mov     ebx, eax
0x1800682fd  test    eax, eax
0x1800682ff  jns     short loc_180068356
0x180068301  mov     rcx, [rsp+368h]; this
0x180068309  mov     r9d, eax; char *
0x18006830c  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180068313  mov     edx, 55h ; 'U'; void *
0x180068318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006831d  nop
0x18006831e  lea     rcx, [rsp+368h+var_308]; this
0x180068323  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x180068328  nop
0x180068329  lea     rcx, [rsp+368h+Context]; this
0x180068331  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x180068336  nop
0x180068337  lea     rcx, [rsp+368h+var_338]
0x18006833c  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x180068341  nop
0x180068342  lea     rcx, [rsp+368h+var_168]; this
0x18006834a  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x18006834f  mov     eax, ebx
0x180068351  jmp     loc_1800686C9
0x180068356  lea     rdx, [rsp+368h+var_308]; struct Windows::Internal::AssignedAccess::IEtwTraceSessionCallback *
0x18006835b  mov     rcx, [rsp+368h+var_338]; this
0x180068360  call    ?Process@EtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@QEAAJPEAVIEtwTraceSessionCallback@234@@Z; Windows::Internal::AssignedAccess::EtwTraceSessionProcessor::Process(Windows::Internal::AssignedAccess::IEtwTraceSessionCallback *)
0x180068365  mov     ebx, eax
0x180068367  test    eax, eax
0x180068369  jns     short loc_1800683C0
0x18006836b  mov     rcx, [rsp+368h]; this
0x180068373  mov     r9d, eax; char *
0x180068376  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006837d  mov     edx, 56h ; 'V'; void *
0x180068382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068387  nop
0x180068388  lea     rcx, [rsp+368h+var_308]; this
0x18006838d  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x180068392  nop
0x180068393  lea     rcx, [rsp+368h+Context]; this
0x18006839b  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x1800683a0  nop
0x1800683a1  lea     rcx, [rsp+368h+var_338]
0x1800683a6  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x1800683ab  nop
0x1800683ac  lea     rcx, [rsp+368h+var_168]; this
0x1800683b4  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x1800683b9  mov     eax, ebx
0x1800683bb  jmp     loc_1800686C9
0x1800683c0  lea     rcx, [rsp+368h+var_330]
0x1800683c5  call    ??0?$vector@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@V?$allocator@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@@2@@std@@QEAA@XZ; std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(void)
0x1800683ca  nop
0x1800683cb  lea     rdx, [rsp+368h+var_330]
0x1800683d0  lea     rcx, [rsp+368h+var_308]
0x1800683d5  call    ?GetAlertDataList@XmlSerializer@AssignedAccess@Internal@Windows@@QEAAJAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@2@@std@@@Z; Windows::Internal::AssignedAccess::XmlSerializer::GetAlertDataList(std::vector<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>> &)
0x1800683da  mov     ebx, eax
0x1800683dc  test    eax, eax
0x1800683de  jns     loc_180068494
0x1800683e4  mov     rcx, [rsp+368h]; this
0x1800683ec  mov     r9d, eax; char *
0x1800683ef  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800683f6  mov     edx, 58h ; 'X'; void *
0x1800683fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068400  nop
0x180068401  mov     rcx, [rsp+368h+var_330]
0x180068406  test    rcx, rcx
0x180068409  jz      short loc_18006845C
0x18006840b  mov     rdx, qword ptr [rsp+368h+var_328]
0x180068410  call    ??$_Destroy_range@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@YAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@0@QEAV10@AEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> *,std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> * const,std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>> &)
0x180068415  mov     rcx, [rsp+368h+var_330]
0x18006841a  mov     rdx, qword ptr [rsp+368h+var_328+8]
0x18006841f  sub     rdx, rcx
0x180068422  mov     rax, 0E38E38E38E38E39h
0x18006842c  imul    rdx
0x18006842f  sar     rdx, 2
0x180068433  mov     rax, rdx
0x180068436  shr     rax, 3Fh
0x18006843a  add     rdx, rax
0x18006843d  lea     rdx, [rdx+rdx*8]
0x180068441  shl     rdx, 3
0x180068445  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006844a  mov     [rsp+368h+var_330], 0
0x180068453  xorps   xmm0, xmm0
0x180068456  movdqu  [rsp+368h+var_328], xmm0
0x18006845c  lea     rcx, [rsp+368h+var_308]; this
0x180068461  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x180068466  nop
0x180068467  lea     rcx, [rsp+368h+Context]; this
0x18006846f  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x180068474  nop
0x180068475  lea     rcx, [rsp+368h+var_338]
0x18006847a  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x18006847f  nop
0x180068480  lea     rcx, [rsp+368h+var_168]; this
0x180068488  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x18006848d  mov     eax, ebx
0x18006848f  jmp     loc_1800686C9
0x180068494  mov     rdx, qword ptr [rsp+368h+var_328]
0x180068499  mov     rcx, [rsp+368h+var_330]
0x18006849e  cmp     rcx, rdx
0x1800684a1  jnz     loc_180068530
0x1800684a7  test    rcx, rcx
0x1800684aa  jz      short loc_1800684F8
0x1800684ac  call    ??$_Destroy_range@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@YAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@0@QEAV10@AEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> *,std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> * const,std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>> &)
0x1800684b1  mov     rcx, [rsp+368h+var_330]
0x1800684b6  mov     rdx, qword ptr [rsp+368h+var_328+8]
0x1800684bb  sub     rdx, rcx
0x1800684be  mov     rax, 0E38E38E38E38E39h
0x1800684c8  imul    rdx
0x1800684cb  sar     rdx, 2
0x1800684cf  mov     rax, rdx
0x1800684d2  shr     rax, 3Fh
0x1800684d6  add     rdx, rax
0x1800684d9  lea     rdx, [rdx+rdx*8]
0x1800684dd  shl     rdx, 3
0x1800684e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800684e6  mov     [rsp+368h+var_330], 0
0x1800684ef  xorps   xmm0, xmm0
0x1800684f2  movdqu  [rsp+368h+var_328], xmm0
0x1800684f8  lea     rcx, [rsp+368h+var_308]; this
0x1800684fd  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x180068502  nop
0x180068503  lea     rcx, [rsp+368h+Context]; this
0x18006850b  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x180068510  nop
0x180068511  lea     rcx, [rsp+368h+var_338]
0x180068516  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x18006851b  nop
0x18006851c  lea     rcx, [rsp+368h+var_168]; this
0x180068524  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x180068529  xor     eax, eax
0x18006852b  jmp     loc_1800686C9
0x180068530  add     rdx, 0FFFFFFFFFFFFFFB8h
0x180068534  lea     rcx, [rsp+368h+var_1B8]
0x18006853c  call    ??0?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@QEAA@AEBV01@@Z; std::tuple<std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>::tuple<std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>(std::tuple<std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &)
0x180068541  nop
0x180068542  lea     r8, [rsp+368h+var_1B8]
0x18006854a  mov     edx, edi
0x18006854c  call    ?ProcessStatusPayload@MdmAlertTask@AssignedAccess@Internal@Windows@@AEAAJW4StatusEnabled@234@AEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@Z; Windows::Internal::AssignedAccess::MdmAlertTask::ProcessStatusPayload(Windows::Internal::AssignedAccess::StatusEnabled,std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> &)
0x180068551  mov     ebx, eax
0x180068553  test    eax, eax
0x180068555  jns     loc_180068619
0x18006855b  mov     rcx, [rsp+368h]; this
0x180068563  mov     r9d, eax; char *
0x180068566  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006856d  mov     edx, 5Ch ; '\'; void *
0x180068572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068577  nop
0x180068578  lea     rcx, [rsp+368h+var_1B8]
0x180068580  call    ??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@QEAA@XZ; std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(void)
0x180068585  nop
0x180068586  mov     rcx, [rsp+368h+var_330]
0x18006858b  test    rcx, rcx
0x18006858e  jz      short loc_1800685E1
0x180068590  mov     rdx, qword ptr [rsp+368h+var_328]
0x180068595  call    ??$_Destroy_range@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@YAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@0@QEAV10@AEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> *,std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> * const,std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>> &)
0x18006859a  mov     rcx, [rsp+368h+var_330]
0x18006859f  mov     rdx, qword ptr [rsp+368h+var_328+8]
0x1800685a4  sub     rdx, rcx
0x1800685a7  mov     rax, 0E38E38E38E38E39h
0x1800685b1  imul    rdx
0x1800685b4  sar     rdx, 2
0x1800685b8  mov     rax, rdx
0x1800685bb  shr     rax, 3Fh
0x1800685bf  add     rdx, rax
0x1800685c2  lea     rdx, [rdx+rdx*8]
0x1800685c6  shl     rdx, 3
0x1800685ca  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800685cf  mov     [rsp+368h+var_330], 0
0x1800685d8  xorps   xmm0, xmm0
0x1800685db  movdqu  [rsp+368h+var_328], xmm0
0x1800685e1  lea     rcx, [rsp+368h+var_308]; this
0x1800685e6  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x1800685eb  nop
0x1800685ec  lea     rcx, [rsp+368h+Context]; this
0x1800685f4  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x1800685f9  nop
0x1800685fa  lea     rcx, [rsp+368h+var_338]
0x1800685ff  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x180068604  nop
0x180068605  lea     rcx, [rsp+368h+var_168]; this
0x18006860d  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x180068612  mov     eax, ebx
0x180068614  jmp     loc_1800686C9
0x180068619  lea     rcx, [rsp+368h+var_168]
0x180068621  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$00$0EAAAAAAAAAAA@$04$0IAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,1,70368744177664,5,2048,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180068626  nop
0x180068627  lea     rcx, [rsp+368h+var_1B8]
0x18006862f  call    ??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@QEAA@XZ; std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(void)
0x180068634  nop
0x180068635  mov     rcx, [rsp+368h+var_330]
0x18006863a  test    rcx, rcx
0x18006863d  jz      short loc_180068690
0x18006863f  mov     rdx, qword ptr [rsp+368h+var_328]
0x180068644  call    ??$_Destroy_range@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@YAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@0@QEAV10@AEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>>>(std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> *,std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring> * const,std::allocator<std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>> &)
0x180068649  mov     rcx, [rsp+368h+var_330]
0x18006864e  mov     rdx, qword ptr [rsp+368h+var_328+8]
0x180068653  sub     rdx, rcx
0x180068656  mov     rax, 0E38E38E38E38E39h
0x180068660  imul    rdx
0x180068663  sar     rdx, 2
0x180068667  mov     rax, rdx
0x18006866a  shr     rax, 3Fh
0x18006866e  add     rdx, rax
0x180068671  lea     rdx, [rdx+rdx*8]
0x180068675  shl     rdx, 3
0x180068679  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006867e  mov     [rsp+368h+var_330], 0
0x180068687  xorps   xmm0, xmm0
0x18006868a  movdqu  [rsp+368h+var_328], xmm0
0x180068690  lea     rcx, [rsp+368h+var_308]; this
0x180068695  call    ??1XmlSerializer@AssignedAccess@Internal@Windows@@UEAA@XZ; Windows::Internal::AssignedAccess::XmlSerializer::~XmlSerializer(void)
0x18006869a  nop
0x18006869b  lea     rcx, [rsp+368h+Context]; this
0x1800686a3  call    ??1AutoRegisterWaitForSingleObject@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AutoRegisterWaitForSingleObject::~AutoRegisterWaitForSingleObject(void)
0x1800686a8  nop
0x1800686a9  lea     rcx, [rsp+368h+var_338]
0x1800686ae  call    ??1?$unique_ptr@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@U?$default_delete@VEtwTraceSessionProcessor@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>::~unique_ptr<Windows::Internal::AssignedAccess::EtwTraceSessionProcessor>(void)
0x1800686b3  nop
0x1800686b4  lea     rcx, [rsp+368h+var_168]; this
0x1800686bc  call    ??1MdmTask_Process@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTask_Process::~MdmTask_Process(void)
0x1800686c1  xor     eax, eax
0x1800686c3  jmp     short loc_1800686C9
0x1800686c5  mov     eax, [rsp+368h+var_318]
0x1800686c9  mov     rcx, [rsp+368h+var_18]
0x1800686d1  xor     rcx, rsp; StackCookie
  ... truncated ...
```
