# tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(void)

- ea: `0x180022070`
- end: `0x1800220fc`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a754`
- `0x18001dac8`
- `0x18001fd50`

## callees

- `0x1800128c4`
- `0x1800139c8`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220e8`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180022070  mov     [rsp+arg_10], rbx
0x180022075  push    rdi
0x180022076  sub     rsp, 20h
0x18002207a  cmp     qword ptr [rcx], 0
0x18002207e  mov     rdi, rcx
0x180022081  jnz     short loc_1800220EE
0x180022083  lea     rcx, [rsp+28h+pv]
0x180022088  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>,>(void)
0x18002208d  mov     rdx, [rax]
0x180022090  mov     qword ptr [rax], 0
0x180022097  mov     rbx, [rdi]
0x18002209a  mov     [rdi], rdx
0x18002209d  test    rbx, rbx
0x1800220a0  jz      short loc_1800220C3
0x1800220a2  or      eax, 0FFFFFFFFh
0x1800220a5  lock xadd [rbx+118h], eax
0x1800220ad  cmp     eax, 1
0x1800220b0  jnz     short loc_1800220C3
0x1800220b2  mov     rcx, rbx
0x1800220b5  call    ??1?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(void)
0x1800220ba  mov     rcx, rbx; pv
0x1800220bd  call    cs:__imp_CoTaskMemFree
0x1800220c3  mov     rbx, [rsp+28h+pv]
0x1800220c8  test    rbx, rbx
0x1800220cb  jz      short loc_1800220EE
0x1800220cd  or      eax, 0FFFFFFFFh
0x1800220d0  lock xadd [rbx+118h], eax
0x1800220d8  cmp     eax, 1
0x1800220db  jnz     short loc_1800220EE
0x1800220dd  mov     rcx, rbx
0x1800220e0  call    ??1?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(void)
0x1800220e5  mov     rcx, rbx; pv
0x1800220e8  call    cs:__imp_CoTaskMemFree
0x1800220ee  mov     rbx, [rsp+28h+arg_10]
0x1800220f3  mov     rax, rdi
0x1800220f6  add     rsp, 20h
0x1800220fa  pop     rdi
0x1800220fb  retn
```
