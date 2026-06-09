# Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(void)

- ea: `0x18000275c`
- end: `0x18000291f`
- name: `?InitializeDataChangedSignaler@ApplicationDataServer@Storage@Windows@@AEAAJXZ`
- size: `451`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataServer *this)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035c28`
- `0x180036abc`
- `0x180037c60`

## callees

- `0x1800022b0`
- `0x18000275c`
- `0x180002928`
- `0x1800029b0`
- `0x18000308c`
- `0x180009778`
- `0x180020904`
- `0x180021efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800027a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800027a3`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateChangeNotification` at `0x1800027d6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateChangeNotification` at `0x1800027d6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x18000290c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002914`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x18000290c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002914`

## string_xrefs

- `0x18000284b`: `CreateStateChangeNotification %u`
- `0x1800028dc`: `create %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(
        Windows::Storage::ApplicationDataServer *this)
{
  HRESULT IsAppContainerProcess; // ebx
  void *v3; // rbx
  HANDLE Event; // rsi
  HRESULT LastErrorFailHr; // r14d
  unsigned int v7; // edx
  unsigned int LastErrorMsg; // edi
  void *retaddr; // [rsp+58h] [rbp+28h]
  bool isAppContainer; // [rsp+60h] [rbp+30h] BYREF
  wil::unique_any_t<wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > roamingEvent; // [rsp+68h] [rbp+38h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tag_HSTATE_NOTIFICATION *,int (__cdecl*)(tag_HSTATE_NOTIFICATION *),&CloseStateChangeNotification,wistd::integral_constant<unsigned __int64,0>,tag_HSTATE_NOTIFICATION *,tag_HSTATE_NOTIFICATION *,0,std::nullptr_t> > > hStateNotification; // [rsp+70h] [rbp+40h] BYREF

  if ( !this->m_applicationStateHandle.m_ptr )
  {
    IsAppContainerProcess = -2147483629;
    v7 = 80;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v7,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      IsAppContainerProcess);
    return (unsigned int)IsAppContainerProcess;
  }
  isAppContainer = 0;
  IsAppContainerProcess = Windows::Storage::StateABIHelpers::IsAppContainerProcess(&isAppContainer);
  if ( IsAppContainerProcess < 0 )
  {
    v7 = 83;
    goto LABEL_14;
  }
  v3 = 0;
  roamingEvent.m_ptr = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v3 = Event;
    roamingEvent.m_ptr = Event;
  }
  else
  {
    Event = 0;
    LastErrorFailHr = wil::details::GetLastErrorFailHr();
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x57u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
        LastErrorFailHr,
        "create %u",
        isAppContainer);
      return (unsigned int)LastErrorFailHr;
    }
  }
  hStateNotification.m_ptr = (tag_HSTATE_NOTIFICATION *)CreateStateChangeNotification(this->m_applicationStateHandle.m_ptr);
  if ( hStateNotification.m_ptr )
  {
    IsAppContainerProcess = Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::Initialize(
                              &this->m_dataChangedSignaler,
                              &roamingEvent,
                              &hStateNotification,
                              this);
    if ( IsAppContainerProcess >= 0 )
    {
      if ( hStateNotification.m_ptr )
        CloseStateChangeNotification(hStateNotification.m_ptr);
      if ( roamingEvent.m_ptr )
        wil::details::CloseHandle(roamingEvent.m_ptr);
      return 0;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x5Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      IsAppContainerProcess,
      "Initialize %u",
      isAppContainer);
    if ( hStateNotification.m_ptr )
      CloseStateChangeNotification(hStateNotification.m_ptr);
    if ( roamingEvent.m_ptr )
      wil::details::CloseHandle(roamingEvent.m_ptr);
    return (unsigned int)IsAppContainerProcess;
  }
  LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                   retaddr,
                   0x5Cu,
                   "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
                   "CreateStateChangeNotification %u",
                   isAppContainer);
  if ( Event )
    wil::details::CloseHandle(v3);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18000275c  push    rbp
0x18000275e  push    rbx
0x18000275f  push    rsi
0x180002760  push    rdi
0x180002761  push    r14
0x180002763  mov     rbp, rsp
0x180002766  sub     rsp, 30h
0x18000276a  cmp     qword ptr [this+58h], 0
0x18000276f  mov     rdi, this
0x180002772  jz      loc_180002826
0x180002778  lea     this, [rbp+isAppContainer]; isAppContainerProcess
0x18000277c  mov     [rbp+isAppContainer], 0
0x180002780  call    ?IsAppContainerProcess@StateABIHelpers@Storage@Windows@@YAJPEA_N@Z; Windows::Storage::StateABIHelpers::IsAppContainerProcess(bool *)
0x180002785  mov     ebx, eax
0x180002787  test    eax, eax
0x180002789  js      loc_180002885
0x18000278f  xor     ebx, ebx
0x180002791  xor     edx, edx; lpName
0x180002793  xor     ecx, ecx; lpEventAttributes
0x180002795  mov     [rbp+roamingEvent.m_ptr], rbx
0x180002799  mov     r9d, 1F0003h; dwDesiredAccess
0x18000279f  lea     r8d, [rbx+1]; dwFlags
0x1800027a3  call    cs:__imp_CreateEventExW
0x1800027a9  mov     rsi, rax
0x1800027ac  test    rax, rax
0x1800027af  jz      short loc_1800027C0
0x1800027b1  call    cs:__imp_GetLastError
0x1800027b7  mov     rbx, rsi
0x1800027ba  mov     [rbp+roamingEvent.m_ptr], rbx
0x1800027be  jmp     short loc_1800027D2
0x1800027c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800027c5  xor     esi, esi
0x1800027c7  mov     r14d, eax
0x1800027ca  test    eax, eax
0x1800027cc  js      loc_1800028D8
0x1800027d2  mov     this, [rdi+58h]
0x1800027d6  call    cs:__imp_CreateStateChangeNotification
0x1800027dc  mov     [rbp+hStateNotification.m_ptr], rax
0x1800027e0  test    rax, rax
0x1800027e3  jz      short loc_180002847
0x1800027e5  lea     this, [rdi+68h]; this
0x1800027e9  mov     r9, rdi; eventSource
0x1800027ec  lea     r8, [rbp+hStateNotification]; notification
0x1800027f0  lea     rdx, [rbp+roamingEvent]; signalEvent
0x1800027f4  call    ?Initialize@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@QEAAJ$$QEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtag_HSTATE_NOTIFICATION@@P6AHPEAU1@@Z$1?CloseStateChangeNotification@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@6@PEAUIApplicationData@34@@Z
0x1800027f9  mov     ebx, eax
0x1800027fb  test    eax, eax
0x1800027fd  js      loc_18000288C
0x180002803  mov     this, [rbp+hStateNotification.m_ptr]
0x180002807  test    this, this
0x18000280a  jnz     loc_180002914
0x180002810  mov     this, [rbp+roamingEvent.m_ptr]; handle
0x180002814  test    this, this
0x180002817  jnz     short loc_18000287E
0x180002819  xor     eax, eax
0x18000281b  add     rsp, 30h
0x18000281f  pop     r14
0x180002821  pop     rdi
0x180002822  pop     rsi
0x180002823  pop     rbx
0x180002824  pop     rbp
0x180002825  retn
0x180002826  mov     ebx, 80000013h
0x18000282b  mov     edx, 50h ; 'P'; lineNumber
0x180002830  mov     this, [rbp+28h]; callerReturnAddress
0x180002834  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000283b  mov     r9d, ebx; hr
0x18000283e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002843  mov     eax, ebx
0x180002845  jmp     short loc_18000281B
0x180002847  movzx   eax, [rbp+isAppContainer]
0x18000284b  lea     r9, formatString; "CreateStateChangeNotification %u"
0x180002852  mov     this, [rbp+28h]; callerReturnAddress
0x180002856  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000285d  mov     edx, 5Ch ; '\'; lineNumber
0x180002862  mov     dword ptr [rsp+30h+formatString], eax
0x180002866  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000286b  mov     edi, eax
0x18000286d  test    rsi, rsi
0x180002870  jz      short loc_18000287A
0x180002872  mov     this, rbx; handle
0x180002875  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000287a  mov     eax, edi
0x18000287c  jmp     short loc_18000281B
0x18000287e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002883  jmp     short loc_180002819
0x180002885  mov     edx, 53h ; 'S'
0x18000288a  jmp     short loc_180002830
0x18000288c  movzx   edx, [rbp+isAppContainer]
0x180002890  lea     rax, aInitializeU; "Initialize %u"
0x180002897  mov     this, [rbp+28h]; callerReturnAddress
0x18000289b  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800028a2  mov     [rsp+30h+var_8], edx
0x1800028a6  mov     r9d, ebx; hr
0x1800028a9  mov     edx, 5Fh ; '_'; lineNumber
0x1800028ae  mov     [rsp+30h+formatString], rax; formatString
0x1800028b3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800028b8  mov     this, [rbp+hStateNotification.m_ptr]
0x1800028bc  test    this, this
0x1800028bf  jnz     short loc_18000290C
0x1800028c1  mov     this, [rbp+roamingEvent.m_ptr]; handle
0x1800028c5  test    this, this
0x1800028c8  jz      loc_180002843
0x1800028ce  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800028d3  jmp     loc_180002843
0x1800028d8  movzx   edx, [rbp+isAppContainer]
0x1800028dc  lea     rax, aCreateU; "create %u"
0x1800028e3  mov     this, [rbp+28h]; callerReturnAddress
0x1800028e7  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800028ee  mov     [rsp+30h+var_8], edx
0x1800028f2  mov     r9d, r14d; hr
0x1800028f5  mov     edx, 57h ; 'W'; lineNumber
0x1800028fa  mov     [rsp+30h+formatString], rax; formatString
0x1800028ff  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180002904  mov     eax, r14d
0x180002907  jmp     loc_18000281B
0x18000290c  call    cs:__imp_CloseStateChangeNotification
0x180002912  jmp     short loc_1800028C1
0x180002914  call    cs:__imp_CloseStateChangeNotification
0x18000291a  jmp     loc_180002810
```
