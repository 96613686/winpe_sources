# tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data(void)

- ea: `0x1800261d8`
- end: `0x180026264`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002252c`

## callees

- `0x18001f0fc`
- `0x180020b8c`
- `0x1800261d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026225`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026250`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800261d8  mov     [rsp+arg_10], rbx
0x1800261dd  push    rdi
0x1800261de  sub     rsp, 20h
0x1800261e2  cmp     qword ptr [rcx], 0
0x1800261e6  mov     rdi, rcx
0x1800261e9  jnz     short loc_180026256
0x1800261eb  lea     rcx, [rsp+28h+pv]
0x1800261f0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>,>(void)
0x1800261f5  mov     rdx, [rax]
0x1800261f8  mov     qword ptr [rax], 0
0x1800261ff  mov     rbx, [rdi]
0x180026202  mov     [rdi], rdx
0x180026205  test    rbx, rbx
0x180026208  jz      short loc_18002622B
0x18002620a  or      eax, 0FFFFFFFFh
0x18002620d  lock xadd [rbx+118h], eax
0x180026215  cmp     eax, 1
0x180026218  jnz     short loc_18002622B
0x18002621a  mov     rcx, rbx
0x18002621d  call    ??1?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(void)
0x180026222  mov     rcx, rbx; pv
0x180026225  call    cs:__imp_CoTaskMemFree
0x18002622b  mov     rbx, [rsp+28h+pv]
0x180026230  test    rbx, rbx
0x180026233  jz      short loc_180026256
0x180026235  or      eax, 0FFFFFFFFh
0x180026238  lock xadd [rbx+118h], eax
0x180026240  cmp     eax, 1
0x180026243  jnz     short loc_180026256
0x180026245  mov     rcx, rbx
0x180026248  call    ??1?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(void)
0x18002624d  mov     rcx, rbx; pv
0x180026250  call    cs:__imp_CoTaskMemFree
0x180026256  mov     rbx, [rsp+28h+arg_10]
0x18002625b  mov     rax, rdi
0x18002625e  add     rsp, 20h
0x180026262  pop     rdi
0x180026263  retn
```
