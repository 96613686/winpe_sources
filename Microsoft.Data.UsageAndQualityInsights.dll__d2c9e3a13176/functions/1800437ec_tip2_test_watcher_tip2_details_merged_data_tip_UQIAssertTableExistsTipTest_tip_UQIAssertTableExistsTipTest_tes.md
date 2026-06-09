# tip2::test_watcher<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)

- ea: `0x1800437ec`
- end: `0x180043836`
- name: `??1?$test_watcher@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801046fa`

## callees

- `0x1800149fc`
- `0x18004368c`
- `0x1800437ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004381d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004381d`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x1800437ec  mov     [rsp+arg_8], rbx
0x1800437f1  push    rdi
0x1800437f2  sub     rsp, 20h
0x1800437f6  mov     rbx, [rcx+38h]
0x1800437fa  mov     rdi, rcx
0x1800437fd  test    rbx, rbx
0x180043800  jz      short loc_180043823
0x180043802  or      eax, 0FFFFFFFFh
0x180043805  lock xadd [rbx+118h], eax
0x18004380d  cmp     eax, 1
0x180043810  jnz     short loc_180043823
0x180043812  mov     rcx, rbx
0x180043815  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x18004381a  mov     rcx, rbx; pv
0x18004381d  call    cs:__imp_CoTaskMemFree
0x180043823  lea     rcx, [rdi+8]; this
0x180043827  mov     rbx, [rsp+28h+arg_8]
0x18004382c  add     rsp, 20h
0x180043830  pop     rdi
0x180043831  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
