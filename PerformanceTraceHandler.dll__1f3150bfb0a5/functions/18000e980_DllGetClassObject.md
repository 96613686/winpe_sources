# DllGetClassObject

- ea: `0x18000e980`
- end: `0x18000ea68`
- name: `DllGetClassObject`
- size: `232`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000be6c`
- `0x18000bf20`
- `0x18000bfd4`
- `0x18000c7c0`
- `0x18000d0a0`
- `0x18000e980`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v7; // rcx

  if ( *(_OWORD *)&CLSID_PerformanceTraceHandler == *(_OWORD *)rclsid )
    return CWinTaskModuleT<PerformanceTraceHandler,&_GUID const CLSID_PerformanceTraceHandler>::DllGetClassObject(
             rclsid,
             rclsid,
             riid,
             ppv);
  if ( *(_QWORD *)&CLSID_WhesvcUXHandler.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_WhesvcUXHandler.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    return CWinTaskModuleT<WhesvcUXHandler,&_GUID const CLSID_WhesvcUXHandler>::DllGetClassObject(
             rclsid,
             rclsid,
             riid,
             ppv);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetImpl'::`2'::impl) )
    return -2147221231;
  if ( *(_QWORD *)&CLSID_ShowFeedbackToastHandler.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_ShowFeedbackToastHandler.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    return CWinTaskModuleT<ShowFeedbackToastHandler,&_GUID const CLSID_ShowFeedbackToastHandler>::DllGetClassObject(
             v7,
             rclsid,
             riid,
             ppv);
  }
  if ( *(_QWORD *)&CLSID_FeedbackResponseHandler.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_FeedbackResponseHandler.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    return DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::QueryInterface(&off_180027000, riid, ppv);
  }
  else
  {
    return -2147221231;
  }
}

```

## disassembly

```asm
0x18000e980  mov     [rsp+arg_0], rbx
0x18000e985  mov     [rsp+arg_8], rsi
0x18000e98a  push    rdi
0x18000e98b  sub     rsp, 20h
0x18000e98f  mov     rax, qword ptr cs:CLSID_PerformanceTraceHandler.Data1
0x18000e996  mov     rdi, r8
0x18000e999  mov     rsi, rdx
0x18000e99c  mov     rbx, rcx
0x18000e99f  cmp     rax, [rcx]
0x18000e9a2  jnz     short loc_18000E9C4
0x18000e9a4  mov     rax, qword ptr cs:CLSID_PerformanceTraceHandler.Data4
0x18000e9ab  cmp     rax, [rcx+8]
0x18000e9af  jnz     short loc_18000E9C4
0x18000e9b1  mov     r9, r8
0x18000e9b4  mov     r8, rdx
0x18000e9b7  mov     rdx, rcx
0x18000e9ba  call    ?DllGetClassObject@?$CWinTaskModuleT@VPerformanceTraceHandler@@$1?CLSID_PerformanceTraceHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<PerformanceTraceHandler,&_GUID const CLSID_PerformanceTraceHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18000e9bf  jmp     loc_18000EA58
0x18000e9c4  mov     rax, qword ptr cs:CLSID_WhesvcUXHandler.Data1
0x18000e9cb  cmp     rax, [rcx]
0x18000e9ce  jnz     short loc_18000E9ED
0x18000e9d0  mov     rax, qword ptr cs:CLSID_WhesvcUXHandler.Data4
0x18000e9d7  cmp     rax, [rcx+8]
0x18000e9db  jnz     short loc_18000E9ED
0x18000e9dd  mov     r9, rdi
0x18000e9e0  mov     r8, rsi
0x18000e9e3  mov     rdx, rbx
0x18000e9e6  call    ?DllGetClassObject@?$CWinTaskModuleT@VWhesvcUXHandler@@$1?CLSID_WhesvcUXHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<WhesvcUXHandler,&_GUID const CLSID_WhesvcUXHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18000e9eb  jmp     short loc_18000EA58
0x18000e9ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast> `wil::Feature<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetImpl(void)'::`2'::impl
0x18000e9f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::__private_IsEnabled(void)
0x18000e9f9  test    al, al
0x18000e9fb  jz      short loc_18000EA53
0x18000e9fd  mov     rax, qword ptr cs:CLSID_ShowFeedbackToastHandler.Data1
0x18000ea04  cmp     rax, [rbx]
0x18000ea07  jnz     short loc_18000EA26
0x18000ea09  mov     rax, qword ptr cs:CLSID_ShowFeedbackToastHandler.Data4
0x18000ea10  cmp     rax, [rbx+8]
0x18000ea14  jnz     short loc_18000EA26
0x18000ea16  mov     r9, rdi
0x18000ea19  mov     r8, rsi
0x18000ea1c  mov     rdx, rbx
0x18000ea1f  call    ?DllGetClassObject@?$CWinTaskModuleT@VShowFeedbackToastHandler@@$1?CLSID_ShowFeedbackToastHandler@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<ShowFeedbackToastHandler,&_GUID const CLSID_ShowFeedbackToastHandler>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18000ea24  jmp     short loc_18000EA58
0x18000ea26  mov     rax, qword ptr cs:CLSID_FeedbackResponseHandler.Data1
0x18000ea2d  cmp     rax, [rbx]
0x18000ea30  jnz     short loc_18000EA53
0x18000ea32  mov     rax, qword ptr cs:CLSID_FeedbackResponseHandler.Data4
0x18000ea39  cmp     rax, [rbx+8]
0x18000ea3d  jnz     short loc_18000EA53
0x18000ea3f  mov     r8, rdi
0x18000ea42  lea     rcx, off_180027000
0x18000ea49  mov     rdx, rsi
0x18000ea4c  call    _DllGetClassObject____17___FeedbackResponseHandlerFactory__QueryInterface
0x18000ea51  jmp     short loc_18000EA58
0x18000ea53  mov     eax, 80040111h
0x18000ea58  mov     rbx, [rsp+28h+arg_0]
0x18000ea5d  mov     rsi, [rsp+28h+arg_8]
0x18000ea62  add     rsp, 20h
0x18000ea66  pop     rdi
0x18000ea67  retn
```
