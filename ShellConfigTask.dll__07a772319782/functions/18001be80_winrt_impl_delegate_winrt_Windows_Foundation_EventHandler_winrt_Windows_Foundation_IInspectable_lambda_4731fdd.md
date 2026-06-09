# winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_4731fdd0c968f4c9f982732a23b7d9b0___::Invoke

- ea: `0x18001be80`
- end: `0x18001bf1c`
- name: `winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_4731fdd0c968f4c9f982732a23b7d9b0___::Invoke`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c5d4`
- `0x180013d90`
- `0x18001a8e4`
- `0x18001be80`
- `0x18001d6d0`
- `0x18002222c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bee7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bebb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bebb`

## string_xrefs

- `0x18001bf09`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_4731fdd0c968f4c9f982732a23b7d9b0___::Invoke(
        __int64 a1)
{
  __int64 v2; // rbx
  const char *v3; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    if ( (unsigned int)winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState() == 2 )
    {
      v2 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(*(__int64 **)(a1 + 24));
      v6 = v2;
      if ( v2 )
        _InterlockedIncrement((volatile signed __int32 *)(v2 + 280));
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
      ++*(_DWORD *)(v2 + 240);
      *(_DWORD *)(v2 + 272) = 3;
      tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(&v6);
      AIXTelemetry::InitialTask_OOBECompleteSignalReceived();
      if ( !SetEvent(**(HANDLE **)(a1 + 16)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v3);
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001be80  mov     [rsp+arg_8], rbx
0x18001be85  push    rdi
0x18001be86  sub     rsp, 20h
0x18001be8a  mov     rdi, rcx
0x18001be8d  call    ?OutOfBoxExperienceState@SystemSetupInfo@Profile@System@Windows@winrt@@SA@XZ; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState(void)
0x18001be92  cmp     eax, 2
0x18001be95  jnz     short loc_18001BEF6
0x18001be97  mov     rcx, [rdi+18h]
0x18001be9b  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x18001bea0  mov     rbx, [rax]
0x18001bea3  mov     [rsp+28h+arg_0], rbx
0x18001bea8  test    rbx, rbx
0x18001beab  jz      short loc_18001BEB4
0x18001bead  lock inc dword ptr [rbx+118h]
0x18001beb4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001bebb  call    cs:__imp_EnterCriticalSection
0x18001bec1  inc     dword ptr [rbx+0F0h]
0x18001bec7  mov     dword ptr [rbx+110h], 3
0x18001bed1  lea     rcx, [rsp+28h+arg_0]
0x18001bed6  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001bedb  call    ?InitialTask_OOBECompleteSignalReceived@AIXTelemetry@@SAXXZ; AIXTelemetry::InitialTask_OOBECompleteSignalReceived(void)
0x18001bee0  mov     rcx, [rdi+10h]
0x18001bee4  mov     rcx, [rcx]; hEvent
0x18001bee7  call    cs:__imp_SetEvent
0x18001beed  mov     rcx, [rsp+28h]; this
0x18001bef2  test    eax, eax
0x18001bef4  jz      short loc_18001BF09
0x18001bef6  xor     eax, eax
0x18001bef8  jmp     short loc_18001BEFE
0x18001befa  mov     eax, dword ptr [rsp+28h+arg_0]
0x18001befe  mov     rbx, [rsp+28h+arg_8]
0x18001bf03  add     rsp, 20h
0x18001bf07  pop     rdi
0x18001bf08  retn
0x18001bf09  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bf10  mov     edx, 0A01h; void *
0x18001bf15  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
