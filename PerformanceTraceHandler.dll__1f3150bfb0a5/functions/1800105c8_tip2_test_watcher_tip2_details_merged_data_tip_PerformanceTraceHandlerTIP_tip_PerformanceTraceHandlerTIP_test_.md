# tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy> &)

- ea: `0x1800105c8`
- end: `0x180010663`
- name: `??0?$test_watcher@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012890`

## callees

- `0x180005c5c`
- `0x1800105c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010634`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010634`

## pseudocode

```c
__int64 __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rsi
  __int64 v4; // rbx
  _QWORD *Local; // rax
  __int64 v6; // rax

  v2 = a2;
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::`vftable';
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
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 288));
  return a1;
}

```

## disassembly

```asm
0x1800105c8  mov     [rsp+arg_0], rbx
0x1800105cd  mov     [rsp+arg_8], rsi
0x1800105d2  push    rdi
0x1800105d3  sub     rsp, 20h
0x1800105d7  mov     rsi, rdx
0x1800105da  mov     rdi, rcx
0x1800105dd  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::`vftable'
0x1800105e4  mov     [rcx], rax
0x1800105e7  lea     rbx, [rcx+8]
0x1800105eb  mov     qword ptr [rbx], 0
0x1800105f2  mov     [rbx+8], rcx
0x1800105f6  mov     qword ptr [rbx+10h], 0
0x1800105fe  mov     dword ptr [rbx+18h], 0
0x180010605  mov     qword ptr [rbx+20h], 0
0x18001060d  mov     byte ptr [rbx+28h], 0
0x180010611  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180010619  jz      short loc_18001063D
0x18001061b  mov     dl, 1
0x18001061d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180010622  mov     [rbx], rax
0x180010625  test    rax, rax
0x180010628  jz      short loc_18001063D
0x18001062a  mov     rcx, [rax]
0x18001062d  mov     [rbx+10h], rcx
0x180010631  mov     [rax], rbx
0x180010634  call    cs:__imp_GetCurrentThreadId
0x18001063a  mov     [rbx+18h], eax
0x18001063d  mov     rax, [rsi]
0x180010640  mov     [rdi+38h], rax
0x180010644  test    rax, rax
0x180010647  jz      short loc_180010650
0x180010649  lock inc dword ptr [rax+120h]
0x180010650  mov     rax, rdi
0x180010653  mov     rbx, [rsp+28h+arg_0]
0x180010658  mov     rsi, [rsp+28h+arg_8]
0x18001065d  add     rsp, 20h
0x180010661  pop     rdi
0x180010662  retn
```
