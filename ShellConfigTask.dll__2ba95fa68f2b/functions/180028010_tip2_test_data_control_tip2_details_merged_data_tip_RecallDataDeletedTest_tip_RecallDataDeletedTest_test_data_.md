# tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)

- ea: `0x180028010`
- end: `0x180028092`
- name: `??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002bf50`
- `0x18002eb00`
- `0x18002ebe0`

## callees

- `0x180021ecc`
- `0x180027d98`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028081`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update((__int64)&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180028010  mov     [rsp+arg_8], rbx
0x180028015  push    rdi
0x180028016  sub     rsp, 20h
0x18002801a  mov     rdi, rcx
0x18002801d  mov     rcx, [rcx]
0x180028020  test    rcx, rcx
0x180028023  jz      short loc_18002805E
0x180028025  add     rcx, 8
0x180028029  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18002802e  mov     rbx, [rdi]
0x180028031  mov     qword ptr [rdi], 0
0x180028038  test    rbx, rbx
0x18002803b  jz      short loc_18002805E
0x18002803d  or      eax, 0FFFFFFFFh
0x180028040  lock xadd [rbx+120h], eax
0x180028048  cmp     eax, 1
0x18002804b  jnz     short loc_18002805E
0x18002804d  mov     rcx, rbx
0x180028050  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x180028055  mov     rcx, rbx; pv
0x180028058  call    cs:__imp_CoTaskMemFree
0x18002805e  mov     rbx, [rdi]
0x180028061  test    rbx, rbx
0x180028064  jz      short loc_180028087
0x180028066  or      eax, 0FFFFFFFFh
0x180028069  lock xadd [rbx+120h], eax
0x180028071  cmp     eax, 1
0x180028074  jnz     short loc_180028087
0x180028076  mov     rcx, rbx
0x180028079  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x18002807e  mov     rcx, rbx; pv
0x180028081  call    cs:__imp_CoTaskMemFree
0x180028087  mov     rbx, [rsp+28h+arg_8]
0x18002808c  add     rsp, 20h
0x180028090  pop     rdi
0x180028091  retn
```
