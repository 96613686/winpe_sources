# tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)

- ea: `0x180043764`
- end: `0x1800437e6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180046cf0`

## callees

- `0x180016ff4`
- `0x18004368c`
- `0x180043764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437d5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180043764  mov     [rsp+arg_8], rbx
0x180043769  push    rdi
0x18004376a  sub     rsp, 20h
0x18004376e  mov     rdi, rcx
0x180043771  mov     rcx, [rcx]
0x180043774  test    rcx, rcx
0x180043777  jz      short loc_1800437B2
0x180043779  add     rcx, 8
0x18004377d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180043782  mov     rbx, [rdi]
0x180043785  mov     qword ptr [rdi], 0
0x18004378c  test    rbx, rbx
0x18004378f  jz      short loc_1800437B2
0x180043791  or      eax, 0FFFFFFFFh
0x180043794  lock xadd [rbx+118h], eax
0x18004379c  cmp     eax, 1
0x18004379f  jnz     short loc_1800437B2
0x1800437a1  mov     rcx, rbx
0x1800437a4  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x1800437a9  mov     rcx, rbx; pv
0x1800437ac  call    cs:__imp_CoTaskMemFree
0x1800437b2  mov     rbx, [rdi]
0x1800437b5  test    rbx, rbx
0x1800437b8  jz      short loc_1800437DB
0x1800437ba  or      eax, 0FFFFFFFFh
0x1800437bd  lock xadd [rbx+118h], eax
0x1800437c5  cmp     eax, 1
0x1800437c8  jnz     short loc_1800437DB
0x1800437ca  mov     rcx, rbx
0x1800437cd  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x1800437d2  mov     rcx, rbx; pv
0x1800437d5  call    cs:__imp_CoTaskMemFree
0x1800437db  mov     rbx, [rsp+28h+arg_8]
0x1800437e0  add     rsp, 20h
0x1800437e4  pop     rdi
0x1800437e5  retn
```
