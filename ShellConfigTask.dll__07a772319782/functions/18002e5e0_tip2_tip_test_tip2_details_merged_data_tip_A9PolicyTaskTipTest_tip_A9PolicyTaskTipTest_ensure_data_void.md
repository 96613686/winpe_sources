# tip2::tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::ensure_data(void)

- ea: `0x18002e5e0`
- end: `0x18002e66c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a69c`
- `0x18002d050`

## callees

- `0x18002710c`
- `0x180027bf4`
- `0x18002e5e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e62d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e62d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e658`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e5e0  mov     [rsp+arg_10], rbx
0x18002e5e5  push    rdi
0x18002e5e6  sub     rsp, 20h
0x18002e5ea  cmp     qword ptr [rcx], 0
0x18002e5ee  mov     rdi, rcx
0x18002e5f1  jnz     short loc_18002E65E
0x18002e5f3  lea     rcx, [rsp+28h+pv]
0x18002e5f8  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>,>(void)
0x18002e5fd  mov     rdx, [rax]
0x18002e600  mov     qword ptr [rax], 0
0x18002e607  mov     rbx, [rdi]
0x18002e60a  mov     [rdi], rdx
0x18002e60d  test    rbx, rbx
0x18002e610  jz      short loc_18002E633
0x18002e612  or      eax, 0FFFFFFFFh
0x18002e615  lock xadd [rbx+118h], eax
0x18002e61d  cmp     eax, 1
0x18002e620  jnz     short loc_18002E633
0x18002e622  mov     rcx, rbx
0x18002e625  call    ??1?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(void)
0x18002e62a  mov     rcx, rbx; pv
0x18002e62d  call    cs:__imp_CoTaskMemFree
0x18002e633  mov     rbx, [rsp+28h+pv]
0x18002e638  test    rbx, rbx
0x18002e63b  jz      short loc_18002E65E
0x18002e63d  or      eax, 0FFFFFFFFh
0x18002e640  lock xadd [rbx+118h], eax
0x18002e648  cmp     eax, 1
0x18002e64b  jnz     short loc_18002E65E
0x18002e64d  mov     rcx, rbx
0x18002e650  call    ??1?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(void)
0x18002e655  mov     rcx, rbx; pv
0x18002e658  call    cs:__imp_CoTaskMemFree
0x18002e65e  mov     rbx, [rsp+28h+arg_10]
0x18002e663  mov     rax, rdi
0x18002e666  add     rsp, 20h
0x18002e66a  pop     rdi
0x18002e66b  retn
```
