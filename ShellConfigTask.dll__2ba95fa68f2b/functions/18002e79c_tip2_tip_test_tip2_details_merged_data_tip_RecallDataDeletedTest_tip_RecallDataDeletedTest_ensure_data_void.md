# tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)

- ea: `0x18002e79c`
- end: `0x18002e828`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bf50`
- `0x18002eb00`
- `0x18002ebe0`

## callees

- `0x180027354`
- `0x180027d98`
- `0x18002e79c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e814`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e79c  mov     [rsp+arg_10], rbx
0x18002e7a1  push    rdi
0x18002e7a2  sub     rsp, 20h
0x18002e7a6  cmp     qword ptr [rcx], 0
0x18002e7aa  mov     rdi, rcx
0x18002e7ad  jnz     short loc_18002E81A
0x18002e7af  lea     rcx, [rsp+28h+pv]
0x18002e7b4  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>,>(void)
0x18002e7b9  mov     rdx, [rax]
0x18002e7bc  mov     qword ptr [rax], 0
0x18002e7c3  mov     rbx, [rdi]
0x18002e7c6  mov     [rdi], rdx
0x18002e7c9  test    rbx, rbx
0x18002e7cc  jz      short loc_18002E7EF
0x18002e7ce  or      eax, 0FFFFFFFFh
0x18002e7d1  lock xadd [rbx+120h], eax
0x18002e7d9  cmp     eax, 1
0x18002e7dc  jnz     short loc_18002E7EF
0x18002e7de  mov     rcx, rbx
0x18002e7e1  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x18002e7e6  mov     rcx, rbx; pv
0x18002e7e9  call    cs:__imp_CoTaskMemFree
0x18002e7ef  mov     rbx, [rsp+28h+pv]
0x18002e7f4  test    rbx, rbx
0x18002e7f7  jz      short loc_18002E81A
0x18002e7f9  or      eax, 0FFFFFFFFh
0x18002e7fc  lock xadd [rbx+120h], eax
0x18002e804  cmp     eax, 1
0x18002e807  jnz     short loc_18002E81A
0x18002e809  mov     rcx, rbx
0x18002e80c  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x18002e811  mov     rcx, rbx; pv
0x18002e814  call    cs:__imp_CoTaskMemFree
0x18002e81a  mov     rbx, [rsp+28h+arg_10]
0x18002e81f  mov     rax, rdi
0x18002e822  add     rsp, 20h
0x18002e826  pop     rdi
0x18002e827  retn
```
