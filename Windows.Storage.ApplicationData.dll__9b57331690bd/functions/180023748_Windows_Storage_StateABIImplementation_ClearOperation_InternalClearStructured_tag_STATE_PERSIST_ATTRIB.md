# Windows::Storage::StateABIImplementation::ClearOperation::InternalClearStructured(tag_STATE_PERSIST_ATTRIB)

- ea: `0x180023748`
- end: `0x1800238d1`
- name: `?InternalClearStructured@ClearOperation@StateABIImplementation@Storage@Windows@@AEAAJW4tag_STATE_PERSIST_ATTRIB@@@Z`
- size: `393`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::ClearOperation *this, tag_STATE_PERSIST_ATTRIB persistence)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023660`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180018fb8`
- `0x180021fc4`
- `0x180022628`
- `0x180023748`
- `0x1800238d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237a0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x18002378d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x18002378d`

## string_xrefs

- `0x1800237ce`: `CreateStateContainer %u`
- `0x180023888`: `EnumerateAndDeleteContainerItems %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::ClearOperation::InternalClearStructured(
        Windows::Storage::StateABIImplementation::ClearOperation *this,
        tag_STATE_PERSIST_ATTRIB persistence)
{
  void *StateContainer; // rax
  void *v5; // rbx
  signed int LastError; // eax
  HRESULT v7; // ebx
  HRESULT v8; // edi
  HRESULT v9; // eax
  HRESULT v10; // r14d
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  HRESULT v12; // eax
  HRESULT v13; // ebx
  void *retaddr; // [rsp+48h] [rbp+0h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseStateContainer,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > rootContainer; // [rsp+50h] [rbp+8h] BYREF
  signed __int32 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !this->m_applicationStateHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)(persistence - 1) > 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  StateContainer = (void *)CreateStateContainer(this->m_applicationStateHandle, (unsigned int)persistence, 0, 2);
  rootContainer.m_ptr = StateContainer;
  v5 = StateContainer;
  if ( StateContainer )
  {
    v8 = 0;
    v9 = Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(
           this,
           StateContainer,
           ENUMERATE_ITEM_SUBCONTAINER);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        0x1CFu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
        v9);
      v8 = v10;
    }
    currentStatus = this->currentStatus_;
    v17 = -2;
    _InterlockedCompareExchange(&v17, currentStatus, -2);
    if ( v17
      || (v12 = Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(
                  this,
                  v5,
                  ENUMERATE_ITEM_SETTINGS),
          v13 = v12,
          v12 >= 0) )
    {
      if ( v8 >= 0 )
      {
        v7 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        0x1DAu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
        v12);
      if ( v8 >= 0 )
        v8 = v13;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x1E0u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
      v8,
      "EnumerateAndDeleteContainerItems %u",
      persistence);
    v7 = v8;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v7, 4u);
    if ( v7 < 0 )
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1C8u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
        v7,
        "CreateStateContainer %u",
        persistence);
  }
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&rootContainer);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023748  mov     [rsp+arg_10], rbx
0x18002374d  mov     [rsp+arg_18], rbp
0x180023752  push    rsi
0x180023753  push    rdi
0x180023754  push    r14
0x180023756  sub     rsp, 30h
0x18002375a  cmp     qword ptr [this+0A8h], 0
0x180023762  mov     ebp, persistence
0x180023764  mov     rsi, this
0x180023767  jnz     short loc_18002376E
0x180023769  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_applicationStateHandle != INVALID_STATE_HANDLE")
0x18002376e  lea     eax, [rbp-1]
0x180023771  cmp     eax, 3
0x180023774  jbe     short loc_18002377B
0x180023776  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(persistence > STATE_PERSIST_UNDEFINED) && (persistence < STATE_PERSIST_LAST)")
0x18002377b  mov     this, [rsi+0A8h]
0x180023782  mov     r9d, 2
0x180023788  xor     r8d, r8d
0x18002378b  mov     persistence, ebp
0x18002378d  call    cs:__imp_CreateStateContainer
0x180023793  mov     [rsp+48h+rootContainer.m_ptr], rax
0x180023798  mov     rbx, rax
0x18002379b  test    rax, rax
0x18002379e  jnz     short loc_1800237F7
0x1800237a0  call    cs:__imp_GetLastError
0x1800237a6  mov     ebx, eax
0x1800237a8  test    eax, eax
0x1800237aa  jle     short loc_1800237B5
0x1800237ac  movzx   ebx, ax
0x1800237af  or      ebx, 80070000h
0x1800237b5  mov     persistence, 4; idsValue
0x1800237ba  mov     ecx, ebx; hr
0x1800237bc  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x1800237c1  test    ebx, ebx
0x1800237c3  jns     loc_1800238B2
0x1800237c9  mov     this, [rsp+48h]; callerReturnAddress
0x1800237ce  lea     rax, aCreatestatecon_0; "CreateStateContainer %u"
0x1800237d5  mov     [rsp+48h+var_20], ebp
0x1800237d9  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800237e0  mov     r9d, ebx; hr
0x1800237e3  mov     [rsp+48h+formatString], rax; formatString
0x1800237e8  mov     persistence, 1C8h; lineNumber
0x1800237ed  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800237f2  jmp     loc_1800238B2
0x1800237f7  xor     edi, edi
0x1800237f9  mov     rdx, rbx; rootContainer
0x1800237fc  mov     this, rsi; this
0x1800237ff  lea     r8d, [rdi+1]; enumItemType
0x180023803  call    ?EnumerateAndDeleteContainerItems@ClearOperation@StateABIImplementation@Storage@Windows@@AEAAJPEAXW4tag_ENUMERATE_ITEM_TYPE@@@Z; Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(void *,tag_ENUMERATE_ITEM_TYPE)
0x180023808  mov     r14d, eax
0x18002380b  test    eax, eax
0x18002380d  jns     short loc_18002382B
0x18002380f  mov     this, [rsp+48h]; callerReturnAddress
0x180023814  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002381b  mov     r9d, eax; hr
0x18002381e  mov     persistence, 1CFh; lineNumber
0x180023823  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023828  mov     edi, r14d
0x18002382b  mov     ecx, [rsi+48h]
0x18002382e  mov     [rsp+48h+arg_8], 0FFFFFFFEh
0x180023836  mov     eax, [rsp+48h+arg_8]
0x18002383a  lock cmpxchg [rsp+48h+arg_8], ecx
0x180023840  cmp     [rsp+48h+arg_8], 0
0x180023845  jnz     short loc_18002387F
0x180023847  mov     r8d, 2; enumItemType
0x18002384d  mov     rdx, rbx; rootContainer
0x180023850  mov     this, rsi; this
0x180023853  call    ?EnumerateAndDeleteContainerItems@ClearOperation@StateABIImplementation@Storage@Windows@@AEAAJPEAXW4tag_ENUMERATE_ITEM_TYPE@@@Z; Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(void *,tag_ENUMERATE_ITEM_TYPE)
0x180023858  mov     ebx, eax
0x18002385a  test    eax, eax
0x18002385c  jns     short loc_18002387F
0x18002385e  mov     this, [rsp+48h]; callerReturnAddress
0x180023863  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002386a  mov     r9d, eax; hr
0x18002386d  mov     persistence, 1DAh; lineNumber
0x180023872  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023877  test    edi, edi
0x180023879  js      short loc_180023883
0x18002387b  mov     edi, ebx
0x18002387d  jmp     short loc_180023883
0x18002387f  test    edi, edi
0x180023881  jns     short loc_1800238B0
0x180023883  mov     this, [rsp+48h]; callerReturnAddress
0x180023888  lea     rax, aEnumerateandde; "EnumerateAndDeleteContainerItems %u"
0x18002388f  mov     [rsp+48h+var_20], ebp
0x180023893  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002389a  mov     r9d, edi; hr
0x18002389d  mov     [rsp+48h+formatString], rax; formatString
0x1800238a2  mov     persistence, 1E0h; lineNumber
0x1800238a7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800238ac  mov     ebx, edi
0x1800238ae  jmp     short loc_1800238B2
0x1800238b0  xor     ebx, ebx
0x1800238b2  lea     this, [rsp+48h+rootContainer]; this
0x1800238b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800238bc  mov     rbp, [rsp+48h+arg_18]
0x1800238c1  mov     eax, ebx
0x1800238c3  mov     rbx, [rsp+48h+arg_10]
0x1800238c8  add     rsp, 30h
0x1800238cc  pop     r14
0x1800238ce  pop     rdi
0x1800238cf  pop     rsi
0x1800238d0  retn
```
