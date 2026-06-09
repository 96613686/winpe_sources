# tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy> &)

- ea: `0x18001ec9c`
- end: `0x18001ed37`
- name: `??0?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800194b0`

## callees

- `0x180012fc0`
- `0x18001ec9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed08`

## pseudocode

```c
__int64 __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rsi
  __int64 v4; // rbx
  _QWORD *Local; // rax
  __int64 v6; // rax

  v2 = a2;
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::`vftable';
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
0x18001ec9c  mov     [rsp+arg_0], rbx
0x18001eca1  mov     [rsp+arg_8], rsi
0x18001eca6  push    rdi
0x18001eca7  sub     rsp, 20h
0x18001ecab  mov     rsi, rdx
0x18001ecae  mov     rdi, rcx
0x18001ecb1  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::`vftable'
0x18001ecb8  mov     [rcx], rax
0x18001ecbb  lea     rbx, [rcx+8]
0x18001ecbf  mov     qword ptr [rbx], 0
0x18001ecc6  mov     [rbx+8], rcx
0x18001ecca  mov     qword ptr [rbx+10h], 0
0x18001ecd2  mov     dword ptr [rbx+18h], 0
0x18001ecd9  mov     qword ptr [rbx+20h], 0
0x18001ece1  mov     byte ptr [rbx+28h], 0
0x18001ece5  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001eced  jz      short loc_18001ED11
0x18001ecef  mov     dl, 1
0x18001ecf1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001ecf6  mov     [rbx], rax
0x18001ecf9  test    rax, rax
0x18001ecfc  jz      short loc_18001ED11
0x18001ecfe  mov     rcx, [rax]
0x18001ed01  mov     [rbx+10h], rcx
0x18001ed05  mov     [rax], rbx
0x18001ed08  call    cs:__imp_GetCurrentThreadId
0x18001ed0e  mov     [rbx+18h], eax
0x18001ed11  mov     rax, [rsi]
0x18001ed14  mov     [rdi+38h], rax
0x18001ed18  test    rax, rax
0x18001ed1b  jz      short loc_18001ED24
0x18001ed1d  lock inc dword ptr [rax+128h]
0x18001ed24  mov     rax, rdi
0x18001ed27  mov     rbx, [rsp+28h+arg_0]
0x18001ed2c  mov     rsi, [rsp+28h+arg_8]
0x18001ed31  add     rsp, 20h
0x18001ed35  pop     rdi
0x18001ed36  retn
```
