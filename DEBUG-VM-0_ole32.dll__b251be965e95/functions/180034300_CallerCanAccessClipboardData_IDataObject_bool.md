# CallerCanAccessClipboardData(IDataObject *,bool *)

- ea: `0x180034300`
- end: `0x1800344b0`
- name: `?CallerCanAccessClipboardData@@YAJPEAUIDataObject@@PEA_N@Z`
- size: `432`
- prototype: `HRESULT __fastcall(IDataObject *dataObject, bool *result)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b3a0`

## callees

- `0x1800185ec`
- `0x180034300`
- `0x1800405b8`
- `0x180040640`
- `0x180055f30`
- `0x1800560c4`
- `0x18005639c`
- `0x18008d380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034414`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x18003445b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x18003445b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x1800343d1`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x1800343d1`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180034345`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180034345`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180034329`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180034329`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003431b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003431b`

## string_xrefs

- `0x180034355`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800343e6`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall CallerCanAccessClipboardData(IDataObject *dataObject, bool *result)
{
  HRESULT ContextForWindow; // eax
  unsigned int v5; // ebx
  wchar_t *m_ptr; // rbx
  HRESULT EnterpriseIdForClipboard; // eax
  unsigned int v8; // edx
  wil::last_error_context v10; // [rsp+40h] [rbp-40h] BYREF
  CallerCanAccessClipboardData::__l5::AUDIT_CALLBACK_CONTEXT callbackContext; // [rsp+48h] [rbp-38h] BYREF
  EDP_REQUEST_ACCESS_OPTIONS options; // [rsp+50h] [rbp-30h] BYREF
  void *retaddr; // [rsp+98h] [rbp+18h]
  EDP_POLICY_RESULT edpResult; // [rsp+A8h] [rbp+28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > sourceEnterpriseId; // [rsp+B0h] [rbp+30h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+B8h] [rbp+38h] BYREF

  *result = 1;
  if ( !(unsigned int)EdpGetIsManaged() || !(unsigned int)EdpIsUIPolicyEvaluationEnabledForThread() )
    return 0;
  edpContext.m_ptr = 0;
  ContextForWindow = EdpGetContextForWindow(0, &edpContext);
  v5 = ContextForWindow;
  if ( ContextForWindow >= 0 )
  {
    if ( (edpContext.m_ptr->contextStates & 1) != 0
      || (edpContext.m_ptr->contextStates & 2) != 0 && edpContext.m_ptr->allowedEnterpriseIdCount )
    {
      v5 = 0;
      goto LABEL_19;
    }
    sourceEnterpriseId.m_ptr = 0;
    if ( GetDataObjectEnterpriseId(dataObject, &sourceEnterpriseId.m_ptr) < 0 )
    {
      m_ptr = sourceEnterpriseId.m_ptr;
      if ( sourceEnterpriseId.m_ptr )
      {
        wil::last_error_context::last_error_context(&v10);
        wil::details::FreeProcessHeap(m_ptr);
        wil::last_error_context::~last_error_context(&v10);
      }
      sourceEnterpriseId.m_ptr = 0;
      EnterpriseIdForClipboard = EdpGetEnterpriseIdForClipboard(&sourceEnterpriseId);
      v5 = EnterpriseIdForClipboard;
      if ( EnterpriseIdForClipboard < 0 )
      {
        v8 = 2625;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          v8,
          "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
          EnterpriseIdForClipboard);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceEnterpriseId);
        goto LABEL_19;
      }
    }
    memset(&options, 0, sizeof(options));
    options.processIdForClipboardConsentCache = GetCurrentProcessId();
    options.overrideOption = EDP_REQUEST_ACCESS_OVERRIDE_NO_DIALOG;
    callbackContext.dataObject = dataObject;
    edpResult = EdpPolicyResult_Unknown;
    EnterpriseIdForClipboard = EdpRequestAccessForContext(
                                 0,
                                 sourceEnterpriseId.m_ptr,
                                 edpContext.m_ptr,
                                 lambda_2aa60daf810bf981192e67453d2e1fb5_::_lambda_invoker_cdecl_,
                                 &callbackContext,
                                 &options,
                                 &edpResult);
    v5 = EnterpriseIdForClipboard;
    if ( EnterpriseIdForClipboard < 0 )
    {
      v8 = 2655;
      goto LABEL_13;
    }
    *result = edpResult == EdpPolicyResult_Allowed;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceEnterpriseId);
    wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0xA2Du, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", ContextForWindow);
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
  return v5;
}

```

## disassembly

```asm
0x180034300  mov     [rsp-18h+arg_0], rbx
0x180034305  push    rbp
0x180034306  push    rsi
0x180034307  push    rdi
0x180034308  mov     rbp, rsp
0x18003430b  sub     rsp, 80h
0x180034312  mov     rdi, result
0x180034315  mov     byte ptr [result], 1
0x180034318  mov     rsi, dataObject
0x18003431b  call    cs:__imp_EdpGetIsManaged
0x180034321  test    eax, eax
0x180034323  jz      loc_18003448C
0x180034329  call    cs:__imp_EdpIsUIPolicyEvaluationEnabledForThread
0x18003432f  test    eax, eax
0x180034331  jz      loc_18003448C
0x180034337  lea     result, [rbp+edpContext]
0x18003433b  mov     [rbp+edpContext.m_ptr], 0
0x180034343  xor     ecx, ecx
0x180034345  call    cs:__imp_EdpGetContextForWindow
0x18003434b  mov     ebx, eax
0x18003434d  test    eax, eax
0x18003434f  jns     short loc_18003436E
0x180034351  mov     dataObject, [rbp+18h]; callerReturnAddress
0x180034355  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18003435c  mov     r9d, eax; hr
0x18003435f  mov     edx, 0A2Dh; lineNumber
0x180034364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034369  jmp     loc_1800344A3
0x18003436e  mov     rax, [rbp+edpContext.m_ptr]
0x180034372  test    byte ptr [rax], 1
0x180034375  jnz     loc_1800344A1
0x18003437b  test    byte ptr [rax], 2
0x18003437e  jz      short loc_18003438A
0x180034380  cmp     dword ptr [rax+4], 0
0x180034384  ja      loc_1800344A1
0x18003438a  lea     result, [rbp+sourceEnterpriseId]; ppEnterpriseId
0x18003438e  mov     [rbp+sourceEnterpriseId.m_ptr], 0
0x180034396  mov     dataObject, rsi; dataObject
0x180034399  call    ?GetDataObjectEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z; GetDataObjectEnterpriseId(IDataObject *,ushort * *)
0x18003439e  test    eax, eax
0x1800343a0  jns     short loc_180034403
0x1800343a2  mov     rbx, [rbp+sourceEnterpriseId.m_ptr]
0x1800343a6  test    rbx, rbx
0x1800343a9  jz      short loc_1800343C5
0x1800343ab  lea     dataObject, [rbp+var_40]; this
0x1800343af  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800343b4  mov     dataObject, rbx; ptr
0x1800343b7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800343bc  lea     dataObject, [rbp+var_40]; this
0x1800343c0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800343c5  lea     dataObject, [rbp+sourceEnterpriseId]
0x1800343c9  mov     [rbp+sourceEnterpriseId.m_ptr], 0
0x1800343d1  call    cs:__imp_EdpGetEnterpriseIdForClipboard
0x1800343d7  mov     ebx, eax
0x1800343d9  test    eax, eax
0x1800343db  jns     short loc_180034403
0x1800343dd  mov     edx, 0A41h; lineNumber
0x1800343e2  mov     dataObject, [rbp+18h]; callerReturnAddress
0x1800343e6  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800343ed  mov     r9d, eax; hr
0x1800343f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800343f5  lea     dataObject, [rbp+sourceEnterpriseId]; this
0x1800343f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800343fe  jmp     loc_1800344A3
0x180034403  xorps   xmm0, xmm0
0x180034406  xor     eax, eax
0x180034408  movups  xmmword ptr [rbp+options.processIdForClipboardConsentCache], xmm0
0x18003440c  mov     qword ptr [rbp+options.sourceEnterpriseIdOption], rax
0x180034410  movups  xmmword ptr [rbp+options.dialogOverrideBodyText], xmm0
0x180034414  call    cs:__imp_GetCurrentProcessId
0x18003441a  mov     r8, [rbp+edpContext.m_ptr]
0x18003441e  lea     r9, _lambda_2aa60daf810bf981192e67453d2e1fb5____lambda_invoker_cdecl_
0x180034425  mov     result, [rbp+sourceEnterpriseId.m_ptr]
0x180034429  xor     ecx, ecx
0x18003442b  mov     [rbp+options.processIdForClipboardConsentCache], eax
0x18003442e  lea     rax, [rbp+edpResult]
0x180034432  mov     [rsp+80h+var_50], rax
0x180034437  lea     rax, [rbp+options]
0x18003443b  mov     [rsp+80h+var_58], rax
0x180034440  lea     rax, [rbp+callbackContext]
0x180034444  mov     [rsp+80h+var_60], rax
0x180034449  mov     [rbp+options.overrideOption], 4
0x180034450  mov     [rbp+callbackContext.dataObject], rsi
0x180034454  mov     [rbp+edpResult], 0
0x18003445b  call    cs:__imp_EdpRequestAccessForContext
0x180034461  mov     ebx, eax
0x180034463  test    eax, eax
0x180034465  jns     short loc_180034471
0x180034467  mov     edx, 0A5Fh
0x18003446c  jmp     loc_1800343E2
0x180034471  cmp     [rbp+edpResult], 1
0x180034475  lea     dataObject, [rbp+sourceEnterpriseId]; this
0x180034479  setz    al
0x18003447c  mov     [rdi], al
0x18003447e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034483  lea     dataObject, [rbp+edpContext]; this
0x180034487  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x18003448c  xor     eax, eax
0x18003448e  mov     rbx, [rsp+80h+arg_0]
0x180034496  add     rsp, 80h
0x18003449d  pop     rdi
0x18003449e  pop     rsi
0x18003449f  pop     rbp
0x1800344a0  retn
0x1800344a1  xor     ebx, ebx
0x1800344a3  lea     dataObject, [rbp+edpContext]; this
0x1800344a7  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x1800344ac  mov     eax, ebx
0x1800344ae  jmp     short loc_18003448E
```
