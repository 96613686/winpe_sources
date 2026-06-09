# DragDropTelemetry::DragDropSession::DragStarted(ushort const *)

- ea: `0x18003c554`
- end: `0x18003c768`
- name: `?DragStarted@DragDropSession@DragDropTelemetry@@QEAAXPEBG@Z`
- size: `532`
- prototype: `void __fastcall(DragDropTelemetry::DragDropSession *this, const wchar_t *pszDataFormats)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003ca70`

## callees

- `0x180022f40`
- `0x18002c588`
- `0x18002cb84`
- `0x1800316c8`
- `0x180035a20`
- `0x1800396e0`
- `0x18003b2ec`
- `0x18003c554`
- `0x18003f418`
- `0x180041564`
- `0x1800428a8`
- `0x180052390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c69f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c69f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c590`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003c631`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003c631`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003c5e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003c5e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18003c5d5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18003c5d5`

## pseudocode

```c
void __fastcall DragDropTelemetry::DragDropSession::DragStarted(
        DragDropTelemetry::DragDropSession *this,
        const wchar_t *pszDataFormats)
{
  DWORD CurrentProcessId; // edi
  const wchar_t *StringFromUIContext; // r15
  unsigned int v6; // r8d
  wchar_t *FileNameW; // rsi
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rdi
  const _tlgProvider_t *v9; // rax
  const _tlgProvider_t *v10; // rax
  const _tlgProvider_t *v11; // rdi
  PROCESS_UICONTEXT CurrentThreadId; // eax
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v13; // r8
  const _GUID *p_m_CapturedRelatedId; // r9
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > uiContext; // [rsp+60h] [rbp-A0h] BYREF
  _tlgWrapperByVal<8> v16; // [rsp+68h] [rbp-98h] BYREF
  _tlgWrapSz<unsigned short> v17; // [rsp+70h] [rbp-90h] BYREF
  _tlgWrapSz<unsigned short> v18; // [rsp+78h] [rbp-88h] BYREF
  _tlgWrapSz<unsigned short> v19; // [rsp+80h] [rbp-80h] BYREF
  _tlgWrapSz<unsigned short> v20; // [rsp+88h] [rbp-78h] BYREF
  _tlgWrapperByVal<8> v21; // [rsp+90h] [rbp-70h] BYREF
  wchar_t dragSourceName[264]; // [rsp+A0h] [rbp-60h] BYREF

  if ( DragDropTelemetry::IsEnabled((unsigned __int8)this, (unsigned __int64)pszDataFormats) )
  {
    LODWORD(uiContext.m_ptr) = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( CallerIdentity::GetCallingProcessType((PROCESS_UICONTEXT *)&uiContext) >= 0 )
    {
      StringFromUIContext = DragDropTelemetryHelper::GetStringFromUIContext((PROCESS_UICONTEXT)uiContext.m_ptr);
      if ( DragDropTelemetryHelper::GetProcessNameFromId(CurrentProcessId, dragSourceName, v6) )
      {
        if ( PathIsFileSpecW(dragSourceName) )
          FileNameW = dragSourceName;
        else
          FileNameW = PathFindFileNameW(dragSourceName);
        wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          (wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType> *)this,
          &uiContext);
        m_pActivityData = this->m_pActivityData;
        v9 = DragDropLogging::Provider();
        if ( v9->LevelPlus1 > 5 && tlgKeywordOn(v9, 0x400000000000uLL) )
          EventActivityIdControl(3u, &m_pActivityData->m_Id);
        else
          m_pActivityData->m_Id = 0;
        m_pActivityData->m_State = TlgStateStarted;
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&uiContext);
        v10 = DragDropLogging::Provider();
        v11 = v10;
        if ( v10->LevelPlus1 > 5 && tlgKeywordOn(v10, 0x400000000000uLL) )
        {
          v16.Value = 0x2000000;
          v17.Psz = L"OleDragDrop";
          v18.Psz = pszDataFormats;
          v19.Psz = StringFromUIContext;
          v20.Psz = FileNameW;
          CurrentThreadId = GetCurrentThreadId();
          v13 = this->m_pActivityData;
          LODWORD(uiContext.m_ptr) = CurrentThreadId;
          v21.Value = 0x2000000;
          if ( !v13->m_HasRelatedId
            || (p_m_CapturedRelatedId = &v13->m_CapturedRelatedId, !v13->m_CapturedRelatedId.Data1)
            && !*(_DWORD *)&v13->m_CapturedRelatedId.Data2
            && !*(_DWORD *)v13->m_CapturedRelatedId.Data4
            && !*(_DWORD *)&v13->m_CapturedRelatedId.Data4[4] )
          {
            p_m_CapturedRelatedId = 0;
          }
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v11,
            &`DragDropTelemetry::DragDropSession::DragStarted'::`15'::_tlgEvent._tlgChannel,
            &v13->m_Id,
            p_m_CapturedRelatedId,
            &v21,
            (const _tlgWrapperByVal<4> *)&uiContext,
            &v20,
            &v19,
            &v18,
            &v17,
            &v16);
        }
        if ( !this->m_callbackHolder.m_threadId )
          wil::details::ThreadFailureCallbackHolder::StartWatching(&this->m_callbackHolder);
      }
    }
  }
}

```

## disassembly

```asm
0x18003c554  push    rbp
0x18003c556  push    rbx
0x18003c557  push    rsi
0x18003c558  push    rdi
0x18003c559  push    r14
0x18003c55b  push    r15
0x18003c55d  lea     rbp, [rsp-1C8h]
0x18003c565  sub     rsp, 2C8h
0x18003c56c  mov     rax, cs:__security_cookie
0x18003c573  xor     rax, rsp
0x18003c576  mov     [rbp+1F0h+var_40], rax
0x18003c57d  mov     r14, pszDataFormats
0x18003c580  mov     rbx, this
0x18003c583  call    ?IsEnabled@DragDropTelemetry@@SA_NE_K@Z; DragDropTelemetry::IsEnabled(uchar,unsigned __int64)
0x18003c588  test    al, al
0x18003c58a  jz      loc_18003C749
0x18003c590  call    cs:__imp_GetCurrentProcessId
0x18003c596  lea     this, [rsp+2F0h+uiContext]; pProcessUIContext
0x18003c59b  mov     dword ptr [rsp+2F0h+uiContext.m_ptr], 0
0x18003c5a3  mov     edi, eax
0x18003c5a5  call    ?GetCallingProcessType@CallerIdentity@@YAJPEAW4PROCESS_UICONTEXT@@@Z; CallerIdentity::GetCallingProcessType(PROCESS_UICONTEXT *)
0x18003c5aa  test    eax, eax
0x18003c5ac  js      loc_18003C749
0x18003c5b2  mov     ecx, dword ptr [rsp+2F0h+uiContext.m_ptr]; uiContext
0x18003c5b6  call    ?GetStringFromUIContext@DragDropTelemetryHelper@@SAPEBGW4PROCESS_UICONTEXT@@@Z; DragDropTelemetryHelper::GetStringFromUIContext(PROCESS_UICONTEXT)
0x18003c5bb  mov     ecx, edi; processId
0x18003c5bd  lea     pszDataFormats, [rbp+1F0h+dragSourceName]; processName
0x18003c5c1  mov     r15, rax
0x18003c5c4  call    ?GetProcessNameFromId@DragDropTelemetryHelper@@SA_NKPEAGK@Z; DragDropTelemetryHelper::GetProcessNameFromId(ulong,ushort *,ulong)
0x18003c5c9  test    al, al
0x18003c5cb  jz      loc_18003C749
0x18003c5d1  lea     this, [rbp+1F0h+dragSourceName]; pszPath
0x18003c5d5  call    cs:__imp_PathIsFileSpecW
0x18003c5db  test    eax, eax
0x18003c5dd  jnz     short loc_18003C5EE
0x18003c5df  lea     this, [rbp+1F0h+dragSourceName]; pszPath
0x18003c5e3  call    cs:__imp_PathFindFileNameW
0x18003c5e9  mov     rsi, rax
0x18003c5ec  jmp     short loc_18003C5F2
0x18003c5ee  lea     rsi, [rbp+1F0h+dragSourceName]
0x18003c5f2  lea     pszDataFormats, [rsp+2F0h+uiContext]; result
0x18003c5f7  mov     this, rbx; this
0x18003c5fa  call    ?LockExclusive@?$ActivityBase@VDragDropLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003c5ff  mov     rdi, [rbx+110h]
0x18003c606  call    ?Provider@DragDropLogging@@SAPEBU_tlgProvider_t@@XZ; DragDropLogging::Provider(void)
0x18003c60b  mov     ecx, [rax]
0x18003c60d  cmp     ecx, 5
0x18003c610  jbe     short loc_18003C639
0x18003c612  mov     pszDataFormats, 400000000000h; keyword
0x18003c61c  mov     this, rax; hProvider
0x18003c61f  call    _tlgKeywordOn
0x18003c624  test    al, al
0x18003c626  jz      short loc_18003C639
0x18003c628  lea     pszDataFormats, [rdi+8]; ActivityId
0x18003c62c  mov     ecx, 3; ControlCode
0x18003c631  call    cs:__imp_EventActivityIdControl
0x18003c637  jmp     short loc_18003C640
0x18003c639  xorps   xmm0, xmm0
0x18003c63c  movups  xmmword ptr [rdi+8], xmm0
0x18003c640  lea     this, [rsp+2F0h+uiContext]; this
0x18003c645  mov     dword ptr [rdi], 1
0x18003c64b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003c650  call    ?Provider@DragDropLogging@@SAPEBU_tlgProvider_t@@XZ; DragDropLogging::Provider(void)
0x18003c655  mov     rdi, rax
0x18003c658  mov     ecx, [rax]
0x18003c65a  cmp     ecx, 5
0x18003c65d  jbe     loc_18003C737
0x18003c663  mov     pszDataFormats, 400000000000h; keyword
0x18003c66d  mov     this, rax; hProvider
0x18003c670  call    _tlgKeywordOn
0x18003c675  test    al, al
0x18003c677  jz      loc_18003C737
0x18003c67d  lea     rax, aOledragdrop; __annotation("_TlgWrite:|117|TraceLoggingType::Provider()|("DragDropSession")=~^"*this"^~|"PartA_PrivTags"=|"wilActivity"=|"threadId"=Identifier of the thread the activity was run on|"DragSourceName"=|"DragSourceUiContext"=|"DataFormat"=|"OperationType"=|"PartA_PrivTags"=")
0x18003c684  mov     [rsp+2F0h+var_288.Value], 2000000h
0x18003c68d  mov     [rsp+2F0h+var_280.Psz], rax
0x18003c692  mov     [rsp+2F0h+var_278.Psz], r14
0x18003c697  mov     [rbp+1F0h+var_270.Psz], r15
0x18003c69b  mov     [rbp+1F0h+var_268.Psz], rsi
0x18003c69f  call    cs:__imp_GetCurrentThreadId
0x18003c6a5  mov     r8, [rbx+110h]
0x18003c6ac  mov     dword ptr [rsp+2F0h+uiContext.m_ptr], eax
0x18003c6b0  mov     [rbp+1F0h+var_260.Value], 2000000h
0x18003c6b8  cmp     byte ptr [r8+4], 0
0x18003c6bd  jz      short loc_18003C6DE
0x18003c6bf  lea     r9, [r8+18h]
0x18003c6c3  cmp     dword ptr [r9], 0
0x18003c6c7  jnz     short loc_18003C6E1
0x18003c6c9  cmp     dword ptr [r9+4], 0
0x18003c6ce  jnz     short loc_18003C6E1
0x18003c6d0  cmp     dword ptr [r9+8], 0
0x18003c6d5  jnz     short loc_18003C6E1
0x18003c6d7  cmp     dword ptr [r9+0Ch], 0
0x18003c6dc  jnz     short loc_18003C6E1
0x18003c6de  xor     r9d, r9d; <writerArgs_1>
0x18003c6e1  lea     rax, [rsp+2F0h+var_288]
0x18003c6e6  add     r8, 8; <writerArgs_0>
0x18003c6ea  mov     [rsp+2F0h+var_2A0], rax; <wrappedArgs_6>
0x18003c6ef  lea     pszDataFormats, ?_tlgEvent@?P@??DragStarted@DragDropSession@DragDropTelemetry@@QEAAXPEBG@Z@4U_unnamed_type__tlgEvent_@?P@??123@QEAAX0@Z@B._tlgChannel; pEventMetadata
0x18003c6f6  lea     rax, [rsp+2F0h+var_280]
0x18003c6fb  mov     this, rdi; hProvider
0x18003c6fe  mov     [rsp+2F0h+var_2A8], rax; <wrappedArgs_5>
0x18003c703  lea     rax, [rsp+2F0h+var_278]
0x18003c708  mov     [rsp+2F0h+var_2B0], rax; <wrappedArgs_4>
0x18003c70d  lea     rax, [rbp+1F0h+var_270]
0x18003c711  mov     [rsp+2F0h+var_2B8], rax; <wrappedArgs_3>
0x18003c716  lea     rax, [rbp+1F0h+var_268]
0x18003c71a  mov     [rsp+2F0h+var_2C0], rax; <wrappedArgs_2>
0x18003c71f  lea     rax, [rsp+2F0h+uiContext]
0x18003c724  mov     [rsp+2F0h+var_2C8], rax; <wrappedArgs_1>
0x18003c729  lea     rax, [rbp+1F0h+var_260]
0x18003c72d  mov     [rsp+2F0h+var_2D0], rax; <wrappedArgs_0>
0x18003c732  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5553@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18003c737  lea     this, [rbx+120h]; this
0x18003c73e  cmp     dword ptr [this+18h], 0
0x18003c742  jnz     short loc_18003C749
0x18003c744  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18003c749  mov     this, [rbp+1F0h+var_40]
0x18003c750  xor     this, rsp; StackCookie
0x18003c753  call    __security_check_cookie
0x18003c758  add     rsp, 2C8h
0x18003c75f  pop     r15
0x18003c761  pop     r14
0x18003c763  pop     rdi
0x18003c764  pop     rsi
0x18003c765  pop     rbx
0x18003c766  pop     rbp
0x18003c767  retn
```
