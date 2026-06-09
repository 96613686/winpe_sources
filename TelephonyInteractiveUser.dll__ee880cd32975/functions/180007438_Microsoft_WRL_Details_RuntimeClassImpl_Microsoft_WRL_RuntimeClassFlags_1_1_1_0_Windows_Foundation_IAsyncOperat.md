# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____

- ea: `0x180007438`
- end: `0x180007486`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007a24`

## callees

- `0x180007264`
- `0x180007438`
- `0x18000e730`
- `0x180019010`

## pseudocode

```c
_UNKNOWN **__fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *(_QWORD *)(a1 + 168);
  if ( v2 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release((volatile signed __int32 *)(2 * v2));
  v3 = *(_QWORD *)(a1 + 136);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 136) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return Microsoft::WRL::Details::ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_::_ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_(a1 + 16);
}

```

## disassembly

```asm
0x180007438  push    rbx
0x18000743a  sub     rsp, 20h
0x18000743e  mov     rbx, rcx
0x180007441  mov     rcx, [rcx+0A8h]
0x180007448  test    rcx, rcx
0x18000744b  jns     short loc_180007455
0x18000744d  add     rcx, rcx
0x180007450  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180007455  mov     rcx, [rbx+88h]
0x18000745c  test    rcx, rcx
0x18000745f  jz      short loc_180007478
0x180007461  mov     qword ptr [rbx+88h], 0
0x18000746c  mov     rax, [rcx]
0x18000746f  mov     rax, [rax+10h]
0x180007473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007478  lea     rcx, [rbx+10h]
0x18000747c  add     rsp, 20h
0x180007480  pop     rbx
0x180007481  jmp     Microsoft__WRL__Details__ImplementsHelper_Microsoft__WRL__RuntimeClassFlags_3__1_Microsoft__WRL__Details__ImplementsMarker_Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft__WRL__FtmBase____ImplementsHelper_Microsoft__WRL__RuntimeClassFlags_3__1_Microsoft__WRL__Details__ImplementsMarker_Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft__WRL__FtmBase_
```
