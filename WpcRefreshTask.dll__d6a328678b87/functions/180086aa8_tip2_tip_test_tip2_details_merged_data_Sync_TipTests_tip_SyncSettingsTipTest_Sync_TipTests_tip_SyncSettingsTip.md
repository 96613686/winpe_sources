# tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>::ensure_data(void)

- ea: `0x180086aa8`
- end: `0x180086b34`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180082bd8`

## callees

- `0x1800816a0`
- `0x1800819a8`
- `0x180086aa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086b20`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180086aa8  mov     [rsp+arg_10], rbx
0x180086aad  push    rdi
0x180086aae  sub     rsp, 20h
0x180086ab2  cmp     qword ptr [rcx], 0
0x180086ab6  mov     rdi, rcx
0x180086ab9  jnz     short loc_180086B26
0x180086abb  lea     rcx, [rsp+28h+pv]
0x180086ac0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>,>(void)
0x180086ac5  mov     rdx, [rax]
0x180086ac8  mov     qword ptr [rax], 0
0x180086acf  mov     rbx, [rdi]
0x180086ad2  mov     [rdi], rdx
0x180086ad5  test    rbx, rbx
0x180086ad8  jz      short loc_180086AFB
0x180086ada  or      eax, 0FFFFFFFFh
0x180086add  lock xadd [rbx+118h], eax
0x180086ae5  cmp     eax, 1
0x180086ae8  jnz     short loc_180086AFB
0x180086aea  mov     rcx, rbx
0x180086aed  call    ??1?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>(void)
0x180086af2  mov     rcx, rbx; pv
0x180086af5  call    cs:__imp_CoTaskMemFree
0x180086afb  mov     rbx, [rsp+28h+pv]
0x180086b00  test    rbx, rbx
0x180086b03  jz      short loc_180086B26
0x180086b05  or      eax, 0FFFFFFFFh
0x180086b08  lock xadd [rbx+118h], eax
0x180086b10  cmp     eax, 1
0x180086b13  jnz     short loc_180086B26
0x180086b15  mov     rcx, rbx
0x180086b18  call    ??1?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>(void)
0x180086b1d  mov     rcx, rbx; pv
0x180086b20  call    cs:__imp_CoTaskMemFree
0x180086b26  mov     rbx, [rsp+28h+arg_10]
0x180086b2b  mov     rax, rdi
0x180086b2e  add     rsp, 20h
0x180086b32  pop     rdi
0x180086b33  retn
```
