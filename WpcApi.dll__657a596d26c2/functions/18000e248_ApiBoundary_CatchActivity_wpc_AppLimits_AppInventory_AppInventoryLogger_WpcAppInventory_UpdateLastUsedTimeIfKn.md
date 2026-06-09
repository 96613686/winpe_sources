# ApiBoundary::CatchActivity<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser,>(std::function<void (void)> const &)

- ea: `0x18000e248`
- end: `0x18000e302`
- name: `??$CatchActivity@VWpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@$$V@ApiBoundary@@YAJAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013e60`

## callees

- `0x1800032a0`
- `0x18000e248`
- `0x18000e560`
- `0x18000ea88`
- `0x18000ed54`
- `0x18000ff10`
- `0x180012e98`

## string_xrefs

- `0x18000e26a`: `WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser`

## pseudocode

```c
__int64 __fastcall ApiBoundary::CatchActivity<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser,>(
        __int64 a1)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // [rsp+0h] [rbp-198h] BYREF
  unsigned int v6; // [rsp+20h] [rbp-178h]
  _QWORD v7[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v7,
    "WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser");
  v7[0] = &wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::`vftable';
  wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StartActivity((wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser *)v7);
  try
  {
    TraceLog::Providers::Reliability::LogFailures<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp>(
      v7,
      a1);
    v7[0] = &wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::`vftable';
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(v7);
    result = 0;
  }
  catch ( ... )
  {
    v6 = wil::details::in1diag3::Return_CaughtException(retaddr, &v5, v2, v3);
    v7[0] = &wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::`vftable';
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(v7);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000e248  mov     [rsp+arg_8], rbx
0x18000e24d  push    rdi
0x18000e24e  sub     rsp, 190h
0x18000e255  mov     rax, cs:__security_cookie
0x18000e25c  xor     rax, rsp
0x18000e25f  mov     [rsp+198h+var_18], rax
0x18000e267  mov     rdi, rcx
0x18000e26a  lea     rdx, aWpcappinventor_1; "WpcAppInventory_UpdateLastUsedTimeIfKno"...
0x18000e271  lea     rcx, [rsp+198h+var_168]
0x18000e276  call    ??0?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e27b  lea     rbx, ??_7WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@6B@; const wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::`vftable'
0x18000e282  mov     [rsp+198h+var_168], rbx
0x18000e287  lea     rcx, [rsp+198h+var_168]; this
0x18000e28c  call    ?StartActivity@WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXXZ; wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StartActivity(void)
0x18000e291  nop
0x18000e292  mov     rdx, rdi
0x18000e295  lea     rcx, [rsp+198h+var_168]
0x18000e29a  call    ??$LogFailures@VWpcAppInventory_GetDisplayNameForUserApp@AppInventoryLogger@AppInventory@AppLimits@wpc@@@Reliability@Providers@TraceLog@@SAXAEAVWpcAppInventory_GetDisplayNameForUserApp@AppInventoryLogger@AppInventory@AppLimits@wpc@@AEBV?$function@$$A6AXXZ@std@@@Z; TraceLog::Providers::Reliability::LogFailures<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp>(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp &,std::function<void (void)> const &)
0x18000e29f  nop
0x18000e2a0  mov     [rsp+198h+var_168], rbx
0x18000e2a5  lea     rcx, [rsp+198h+var_168]
0x18000e2aa  call    ?Destroy@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e2af  lea     rcx, [rsp+198h+var_168]
0x18000e2b4  call    ??1?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e2b9  xor     eax, eax
0x18000e2bb  jmp     short loc_18000E2E1
0x18000e2bd  lea     rbx, ??_7WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@6B@; const wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::`vftable'
0x18000e2c4  mov     [rsp+198h+var_168], rbx
0x18000e2c9  lea     rcx, [rsp+198h+var_168]
0x18000e2ce  call    ?Destroy@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e2d3  lea     rcx, [rsp+198h+var_168]
0x18000e2d8  call    ??1?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e2dd  mov     eax, [rsp+198h+var_178]
0x18000e2e1  mov     rcx, [rsp+198h+var_18]
0x18000e2e9  xor     rcx, rsp; StackCookie
0x18000e2ec  call    __security_check_cookie
0x18000e2f1  mov     rbx, [rsp+198h+arg_8]
0x18000e2f9  add     rsp, 190h
0x18000e300  pop     rdi
0x18000e301  retn
```
