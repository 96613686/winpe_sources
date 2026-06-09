# tip2::tip_test<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>>::~tip_test<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>>(void)

- ea: `0x180035604`
- end: `0x180035639`
- name: `??1?$tip_test@V?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010413d`

## callees

- `0x180013c48`
- `0x180035604`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003562d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003562d`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>>::~tip_test<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180035604  push    rbx
0x180035606  sub     rsp, 20h
0x18003560a  mov     rbx, [rcx]
0x18003560d  test    rbx, rbx
0x180035610  jz      short loc_180035633
0x180035612  or      eax, 0FFFFFFFFh
0x180035615  lock xadd [rbx+110h], eax
0x18003561d  cmp     eax, 1
0x180035620  jnz     short loc_180035633
0x180035622  mov     rcx, rbx
0x180035625  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18003562a  mov     rcx, rbx; pv
0x18003562d  call    cs:__imp_CoTaskMemFree
0x180035633  add     rsp, 20h
0x180035637  pop     rbx
0x180035638  retn
```
