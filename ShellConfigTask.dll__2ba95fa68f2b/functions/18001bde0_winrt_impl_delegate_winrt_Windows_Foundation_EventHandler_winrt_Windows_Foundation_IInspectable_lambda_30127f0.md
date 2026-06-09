# winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_30127f0a1cbc4838c5482e35506583e1___::Invoke

- ea: `0x18001bde0`
- end: `0x18001be77`
- name: `winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_30127f0a1cbc4838c5482e35506583e1___::Invoke`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c5d4`
- `0x180013d90`
- `0x18001bde0`
- `0x18001d6d0`
- `0x1800222c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001be42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001be42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be1b`

## string_xrefs

- `0x18001be64`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::Foundation::EventHandler_winrt::Windows::Foundation::IInspectable___lambda_30127f0a1cbc4838c5482e35506583e1___::Invoke(
        __int64 a1)
{
  volatile signed __int32 *v2; // rbx
  const char *v3; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  volatile signed __int32 *v6; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    if ( (unsigned int)winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState() == 2 )
    {
      v2 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(*(volatile signed __int32 ***)(a1 + 24));
      v6 = v2;
      if ( v2 )
        _InterlockedIncrement(v2 + 70);
      EnterCriticalSection((LPCRITICAL_SECTION)v2 + 5);
      ++*((_DWORD *)v2 + 60);
      *((_DWORD *)v2 + 68) = 3;
      tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>((__int64 *)&v6);
      if ( !SetEvent(**(HANDLE **)(a1 + 16)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x18001bde0  mov     [rsp+arg_8], rbx
0x18001bde5  push    rdi
0x18001bde6  sub     rsp, 20h
0x18001bdea  mov     rdi, rcx
0x18001bded  call    ?OutOfBoxExperienceState@SystemSetupInfo@Profile@System@Windows@winrt@@SA@XZ; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState(void)
0x18001bdf2  cmp     eax, 2
0x18001bdf5  jnz     short loc_18001BE51
0x18001bdf7  mov     rcx, [rdi+18h]
0x18001bdfb  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)
0x18001be00  mov     rbx, [rax]
0x18001be03  mov     [rsp+28h+arg_0], rbx
0x18001be08  test    rbx, rbx
0x18001be0b  jz      short loc_18001BE14
0x18001be0d  lock inc dword ptr [rbx+118h]
0x18001be14  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001be1b  call    cs:__imp_EnterCriticalSection
0x18001be21  inc     dword ptr [rbx+0F0h]
0x18001be27  mov     dword ptr [rbx+110h], 3
0x18001be31  lea     rcx, [rsp+28h+arg_0]
0x18001be36  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001be3b  mov     rcx, [rdi+10h]
0x18001be3f  mov     rcx, [rcx]; hEvent
0x18001be42  call    cs:__imp_SetEvent
0x18001be48  mov     rcx, [rsp+28h]; this
0x18001be4d  test    eax, eax
0x18001be4f  jz      short loc_18001BE64
0x18001be51  xor     eax, eax
0x18001be53  jmp     short loc_18001BE59
0x18001be55  mov     eax, dword ptr [rsp+28h+arg_0]
0x18001be59  mov     rbx, [rsp+28h+arg_8]
0x18001be5e  add     rsp, 20h
0x18001be62  pop     rdi
0x18001be63  retn
0x18001be64  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001be6b  mov     edx, 0A01h; void *
0x18001be70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
