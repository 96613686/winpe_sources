# wistd::__function::__func__lambda_7b8c32d8e833bf692b43e3eaa7944fb8__void___cdecl(enum_wil::RegistryChangeKind)_::operator()

- ea: `0x180014760`
- end: `0x1800147f7`
- name: `wistd::__function::__func__lambda_7b8c32d8e833bf692b43e3eaa7944fb8__void___cdecl(enum_wil::RegistryChangeKind)_::operator()`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c5d4`
- `0x180013d90`
- `0x180014760`
- `0x18001a980`
- `0x18001cfb0`
- `0x18002222c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001479f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001479f`

## string_xrefs

- `0x1800147e5`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall wistd::__function::__func__lambda_7b8c32d8e833bf692b43e3eaa7944fb8__void___cdecl_enum_wil::RegistryChangeKind__::operator()(
        __int64 a1,
        __int64 a2)
{
  BOOL v3; // eax
  volatile signed __int32 *v4; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  LOBYTE(v3) = IsOobeInEnduserSession();
  if ( v3 )
  {
    v4 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(*(volatile signed __int32 ***)(a1 + 16));
    v8 = (__int64)v4;
    if ( v4 )
      _InterlockedIncrement(v4 + 70);
    EnterCriticalSection((LPCRITICAL_SECTION)v4 + 5);
    ++*((_DWORD *)v4 + 60);
    *((_DWORD *)v4 + 68) = 4;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(&v8);
    AIXTelemetry::InitialTask_OOBEInEnduserSessionSignalReceived();
    v3 = SetEvent(**(HANDLE **)(a1 + 8));
    if ( !v3 )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180014760  mov     [rsp+arg_0], rbx
0x180014765  mov     [rsp+arg_8], rdx
0x18001476a  push    rdi
0x18001476b  sub     rsp, 20h
0x18001476f  mov     rdi, rcx
0x180014772  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x180014777  test    al, al
0x180014779  jz      short loc_1800147D5
0x18001477b  mov     rcx, [rdi+10h]
0x18001477f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x180014784  mov     rbx, [rax]
0x180014787  mov     [rsp+28h+arg_8], rbx
0x18001478c  test    rbx, rbx
0x18001478f  jz      short loc_180014798
0x180014791  lock inc dword ptr [rbx+118h]
0x180014798  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001479f  call    cs:__imp_EnterCriticalSection
0x1800147a5  inc     dword ptr [rbx+0F0h]
0x1800147ab  lea     rcx, [rsp+28h+arg_8]
0x1800147b0  mov     dword ptr [rbx+110h], 4
0x1800147ba  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x1800147bf  call    ?InitialTask_OOBEInEnduserSessionSignalReceived@AIXTelemetry@@SAXXZ; AIXTelemetry::InitialTask_OOBEInEnduserSessionSignalReceived(void)
0x1800147c4  mov     rcx, [rdi+8]
0x1800147c8  mov     rcx, [rcx]; hEvent
0x1800147cb  call    cs:__imp_SetEvent
0x1800147d1  test    eax, eax
0x1800147d3  jz      short loc_1800147E0
0x1800147d5  mov     rbx, [rsp+28h+arg_0]
0x1800147da  add     rsp, 20h
0x1800147de  pop     rdi
0x1800147df  retn
0x1800147e0  mov     rcx, [rsp+28h]; this
0x1800147e5  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800147ec  mov     edx, 0A01h; void *
0x1800147f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
