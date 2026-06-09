# tip2::test_watcher<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)

- ea: `0x180013f1c`
- end: `0x180013f66`
- name: `??1?$test_watcher@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180102ae1`
- `0x180102e3f`
- `0x18010302d`
- `0x180104ee9`
- `0x180105e68`

## callees

- `0x180013c48`
- `0x180013f1c`
- `0x1800149fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f4d`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 272), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x180013f1c  mov     [rsp+arg_8], rbx
0x180013f21  push    rdi
0x180013f22  sub     rsp, 20h
0x180013f26  mov     rbx, [rcx+38h]
0x180013f2a  mov     rdi, rcx
0x180013f2d  test    rbx, rbx
0x180013f30  jz      short loc_180013F53
0x180013f32  or      eax, 0FFFFFFFFh
0x180013f35  lock xadd [rbx+110h], eax
0x180013f3d  cmp     eax, 1
0x180013f40  jnz     short loc_180013F53
0x180013f42  mov     rcx, rbx
0x180013f45  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180013f4a  mov     rcx, rbx; pv
0x180013f4d  call    cs:__imp_CoTaskMemFree
0x180013f53  lea     rcx, [rdi+8]; this
0x180013f57  mov     rbx, [rsp+28h+arg_8]
0x180013f5c  add     rsp, 20h
0x180013f60  pop     rdi
0x180013f61  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
