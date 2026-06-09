# std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::__Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_

- ea: `0x18003bb90`
- end: `0x18003bbd7`
- name: `std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::__Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003bf80`

## callees

- `0x18003bb90`
- `0x18003bc34`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bbc3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bbc3`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18003bbb9`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18003bbb9`

## pseudocode

```c
HRESULT __fastcall std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::__Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_(
        __int64 a1)
{
  bool v1; // zf

  v1 = *(_BYTE *)(a1 + 217) == 0;
  *(_QWORD *)a1 = &___7___Associated_state_UAppServiceResponseData__1__AppServiceSendMessageAsync_AppServiceHelper__AEAAJPEAUIAppServiceConnection_AppService_ApplicationModel_Windows__PEAUIPropertySet_Collections_Foundation_7_PEAPEAU89Foundation_7_PEAPEAUHSTRING_____Z__std__6B_;
  if ( !v1 && !*(_DWORD *)(a1 + 212) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 56));
  __ExceptionPtrDestroy((void *)(a1 + 40));
  return AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData::_AppServiceResponseData(a1 + 16);
}

```

## disassembly

```asm
0x18003bb90  push    rbx
0x18003bb92  sub     rsp, 20h
0x18003bb96  cmp     byte ptr [rcx+0D9h], 0
0x18003bb9d  lea     rax, ??_7?$_Associated_state@UAppServiceResponseData@?1??AppServiceSendMessageAsync@AppServiceHelper@@AEAAJPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAUIPropertySet@Collections@Foundation@7@PEAPEAU89Foundation@7@PEAPEAUHSTRING__@@@Z@@std@@6B@; const std::_Associated_state<`AppServiceHelper::AppServiceSendMessageAsync(Windows::ApplicationModel::AppService::IAppServiceConnection *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)'::`2'::AppServiceResponseData>::`vftable'
0x18003bba4  mov     [rcx], rax
0x18003bba7  mov     rbx, rcx
0x18003bbaa  jz      short loc_18003BBBF
0x18003bbac  cmp     dword ptr [rcx+0D4h], 0
0x18003bbb3  jnz     short loc_18003BBBF
0x18003bbb5  add     rcx, 38h ; '8'; _Mtx_t
0x18003bbb9  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18003bbbf  lea     rcx, [rbx+28h]
0x18003bbc3  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003bbc9  lea     rcx, [rbx+10h]
0x18003bbcd  add     rsp, 20h
0x18003bbd1  pop     rbx
0x18003bbd2  jmp     _AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___AppServiceResponseData
```
