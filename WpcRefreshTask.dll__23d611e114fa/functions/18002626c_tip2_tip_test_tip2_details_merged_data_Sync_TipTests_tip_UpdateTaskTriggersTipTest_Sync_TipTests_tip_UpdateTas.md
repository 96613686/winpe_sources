# tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data(void)

- ea: `0x18002626c`
- end: `0x1800262f8`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800221d4`

## callees

- `0x18001f1c0`
- `0x180020c18`
- `0x18002626c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800262b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800262e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800262b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800262e4`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *updated; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    updated = (__int64 *)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>,>(&pv);
    v3 = *updated;
    *updated = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 296), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 74, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002626c  mov     [rsp+arg_10], rbx
0x180026271  push    rdi
0x180026272  sub     rsp, 20h
0x180026276  cmp     qword ptr [rcx], 0
0x18002627a  mov     rdi, rcx
0x18002627d  jnz     short loc_1800262EA
0x18002627f  lea     rcx, [rsp+28h+pv]
0x180026284  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>,>(void)
0x180026289  mov     rdx, [rax]
0x18002628c  mov     qword ptr [rax], 0
0x180026293  mov     rbx, [rdi]
0x180026296  mov     [rdi], rdx
0x180026299  test    rbx, rbx
0x18002629c  jz      short loc_1800262BF
0x18002629e  or      eax, 0FFFFFFFFh
0x1800262a1  lock xadd [rbx+128h], eax
0x1800262a9  cmp     eax, 1
0x1800262ac  jnz     short loc_1800262BF
0x1800262ae  mov     rcx, rbx
0x1800262b1  call    ??1?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(void)
0x1800262b6  mov     rcx, rbx; pv
0x1800262b9  call    cs:__imp_CoTaskMemFree
0x1800262bf  mov     rbx, [rsp+28h+pv]
0x1800262c4  test    rbx, rbx
0x1800262c7  jz      short loc_1800262EA
0x1800262c9  or      eax, 0FFFFFFFFh
0x1800262cc  lock xadd [rbx+128h], eax
0x1800262d4  cmp     eax, 1
0x1800262d7  jnz     short loc_1800262EA
0x1800262d9  mov     rcx, rbx
0x1800262dc  call    ??1?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(void)
0x1800262e1  mov     rcx, rbx; pv
0x1800262e4  call    cs:__imp_CoTaskMemFree
0x1800262ea  mov     rbx, [rsp+28h+arg_10]
0x1800262ef  mov     rax, rdi
0x1800262f2  add     rsp, 20h
0x1800262f6  pop     rdi
0x1800262f7  retn
```
