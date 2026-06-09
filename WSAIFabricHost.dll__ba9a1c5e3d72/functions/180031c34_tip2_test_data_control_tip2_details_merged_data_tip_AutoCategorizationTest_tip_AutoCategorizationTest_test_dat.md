# tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(void)

- ea: `0x180031c34`
- end: `0x180031cb6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180045790`
- `0x1800844c4`
- `0x1800845ce`

## callees

- `0x180031950`
- `0x180031c34`
- `0x18004e8f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ca5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update((__int64)&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180031c34  mov     [rsp+arg_8], rbx
0x180031c39  push    rdi
0x180031c3a  sub     rsp, 20h
0x180031c3e  mov     rdi, rcx
0x180031c41  mov     rcx, [rcx]
0x180031c44  test    rcx, rcx
0x180031c47  jz      short loc_180031C82
0x180031c49  add     rcx, 8
0x180031c4d  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180031c52  mov     rbx, [rdi]
0x180031c55  mov     qword ptr [rdi], 0
0x180031c5c  test    rbx, rbx
0x180031c5f  jz      short loc_180031C82
0x180031c61  or      eax, 0FFFFFFFFh
0x180031c64  lock xadd [rbx+120h], eax
0x180031c6c  cmp     eax, 1
0x180031c6f  jnz     short loc_180031C82
0x180031c71  mov     rcx, rbx
0x180031c74  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180031c79  mov     rcx, rbx; pv
0x180031c7c  call    cs:__imp_CoTaskMemFree
0x180031c82  mov     rbx, [rdi]
0x180031c85  test    rbx, rbx
0x180031c88  jz      short loc_180031CAB
0x180031c8a  or      eax, 0FFFFFFFFh
0x180031c8d  lock xadd [rbx+120h], eax
0x180031c95  cmp     eax, 1
0x180031c98  jnz     short loc_180031CAB
0x180031c9a  mov     rcx, rbx
0x180031c9d  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180031ca2  mov     rcx, rbx; pv
0x180031ca5  call    cs:__imp_CoTaskMemFree
0x180031cab  mov     rbx, [rsp+28h+arg_8]
0x180031cb0  add     rsp, 20h
0x180031cb4  pop     rdi
0x180031cb5  retn
```
