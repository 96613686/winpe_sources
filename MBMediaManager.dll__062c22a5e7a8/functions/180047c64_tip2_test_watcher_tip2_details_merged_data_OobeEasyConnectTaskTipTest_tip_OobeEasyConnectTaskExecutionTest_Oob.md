# tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy> &)

- ea: `0x180047c64`
- end: `0x180047cff`
- name: `??0?$test_watcher@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800215a0`
- `0x180022ee8`

## callees

- `0x180030170`
- `0x180047c64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047cd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047cd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rsi
  __int64 v4; // rbx
  _QWORD *Local; // rax
  __int64 v6; // rax

  v2 = a2;
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::`vftable';
  v4 = a1 + 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        a1,
                        a2);
    *(_QWORD *)v4 = Local;
    if ( Local )
    {
      *(_QWORD *)(v4 + 16) = *Local;
      *Local = v4;
      *(_DWORD *)(v4 + 24) = GetCurrentThreadId();
    }
  }
  v6 = *v2;
  *(_QWORD *)(a1 + 56) = *v2;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 296));
  return a1;
}

```

## disassembly

```asm
0x180047c64  mov     [rsp+arg_0], rbx
0x180047c69  mov     [rsp+arg_8], rsi
0x180047c6e  push    rdi
0x180047c6f  sub     rsp, 20h
0x180047c73  mov     rsi, rdx
0x180047c76  mov     rdi, rcx
0x180047c79  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::`vftable'
0x180047c80  mov     [rcx], rax
0x180047c83  lea     rbx, [rcx+8]
0x180047c87  mov     qword ptr [rbx], 0
0x180047c8e  mov     [rbx+8], rcx
0x180047c92  mov     qword ptr [rbx+10h], 0
0x180047c9a  mov     dword ptr [rbx+18h], 0
0x180047ca1  mov     qword ptr [rbx+20h], 0
0x180047ca9  mov     byte ptr [rbx+28h], 0
0x180047cad  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180047cb5  jz      short loc_180047CD9
0x180047cb7  mov     dl, 1
0x180047cb9  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180047cbe  mov     [rbx], rax
0x180047cc1  test    rax, rax
0x180047cc4  jz      short loc_180047CD9
0x180047cc6  mov     rcx, [rax]
0x180047cc9  mov     [rbx+10h], rcx
0x180047ccd  mov     [rax], rbx
0x180047cd0  call    cs:__imp_GetCurrentThreadId
0x180047cd6  mov     [rbx+18h], eax
0x180047cd9  mov     rax, [rsi]
0x180047cdc  mov     [rdi+38h], rax
0x180047ce0  test    rax, rax
0x180047ce3  jz      short loc_180047CEC
0x180047ce5  lock inc dword ptr [rax+128h]
0x180047cec  mov     rax, rdi
0x180047cef  mov     rbx, [rsp+28h+arg_0]
0x180047cf4  mov     rsi, [rsp+28h+arg_8]
0x180047cf9  add     rsp, 20h
0x180047cfd  pop     rdi
0x180047cfe  retn
```
