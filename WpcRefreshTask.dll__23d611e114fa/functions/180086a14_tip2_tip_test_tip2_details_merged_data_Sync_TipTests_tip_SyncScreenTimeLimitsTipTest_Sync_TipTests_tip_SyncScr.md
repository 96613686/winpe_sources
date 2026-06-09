# tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>::ensure_data(void)

- ea: `0x180086a14`
- end: `0x180086aa0`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180082ad4`

## callees

- `0x1800815d8`
- `0x18008191c`
- `0x180086a14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086a8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086a8c`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180086a14  mov     [rsp+arg_10], rbx
0x180086a19  push    rdi
0x180086a1a  sub     rsp, 20h
0x180086a1e  cmp     qword ptr [rcx], 0
0x180086a22  mov     rdi, rcx
0x180086a25  jnz     short loc_180086A92
0x180086a27  lea     rcx, [rsp+28h+pv]
0x180086a2c  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>,>(void)
0x180086a31  mov     rdx, [rax]
0x180086a34  mov     qword ptr [rax], 0
0x180086a3b  mov     rbx, [rdi]
0x180086a3e  mov     [rdi], rdx
0x180086a41  test    rbx, rbx
0x180086a44  jz      short loc_180086A67
0x180086a46  or      eax, 0FFFFFFFFh
0x180086a49  lock xadd [rbx+118h], eax
0x180086a51  cmp     eax, 1
0x180086a54  jnz     short loc_180086A67
0x180086a56  mov     rcx, rbx
0x180086a59  call    ??1?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(void)
0x180086a5e  mov     rcx, rbx; pv
0x180086a61  call    cs:__imp_CoTaskMemFree
0x180086a67  mov     rbx, [rsp+28h+pv]
0x180086a6c  test    rbx, rbx
0x180086a6f  jz      short loc_180086A92
0x180086a71  or      eax, 0FFFFFFFFh
0x180086a74  lock xadd [rbx+118h], eax
0x180086a7c  cmp     eax, 1
0x180086a7f  jnz     short loc_180086A92
0x180086a81  mov     rcx, rbx
0x180086a84  call    ??1?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(void)
0x180086a89  mov     rcx, rbx; pv
0x180086a8c  call    cs:__imp_CoTaskMemFree
0x180086a92  mov     rbx, [rsp+28h+arg_10]
0x180086a97  mov     rax, rdi
0x180086a9a  add     rsp, 20h
0x180086a9e  pop     rdi
0x180086a9f  retn
```
