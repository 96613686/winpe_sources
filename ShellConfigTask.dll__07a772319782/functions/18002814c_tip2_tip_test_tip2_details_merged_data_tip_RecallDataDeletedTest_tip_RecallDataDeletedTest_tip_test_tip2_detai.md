# tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)

- ea: `0x18002814c`
- end: `0x180028181`
- name: `??1?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800318e0`

## callees

- `0x180027d98`
- `0x18002814c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028175`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v1[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v1);
      CoTaskMemFree(v1);
    }
  }
}

```

## disassembly

```asm
0x18002814c  push    rbx
0x18002814e  sub     rsp, 20h
0x180028152  mov     rbx, [rcx]
0x180028155  test    rbx, rbx
0x180028158  jz      short loc_18002817B
0x18002815a  or      eax, 0FFFFFFFFh
0x18002815d  lock xadd [rbx+120h], eax
0x180028165  cmp     eax, 1
0x180028168  jnz     short loc_18002817B
0x18002816a  mov     rcx, rbx
0x18002816d  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x180028172  mov     rcx, rbx; pv
0x180028175  call    cs:__imp_CoTaskMemFree
0x18002817b  add     rsp, 20h
0x18002817f  pop     rbx
0x180028180  retn
```
