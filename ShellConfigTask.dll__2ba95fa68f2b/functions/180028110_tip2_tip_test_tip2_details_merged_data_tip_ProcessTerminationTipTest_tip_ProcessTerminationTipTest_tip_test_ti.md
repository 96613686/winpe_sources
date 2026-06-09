# tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(void)

- ea: `0x180028110`
- end: `0x180028145`
- name: `??1?$tip_test@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800318aa`

## callees

- `0x180027d0c`
- `0x180028110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028139`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180028110  push    rbx
0x180028112  sub     rsp, 20h
0x180028116  mov     rbx, [rcx]
0x180028119  test    rbx, rbx
0x18002811c  jz      short loc_18002813F
0x18002811e  or      eax, 0FFFFFFFFh
0x180028121  lock xadd [rbx+118h], eax
0x180028129  cmp     eax, 1
0x18002812c  jnz     short loc_18002813F
0x18002812e  mov     rcx, rbx
0x180028131  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x180028136  mov     rcx, rbx; pv
0x180028139  call    cs:__imp_CoTaskMemFree
0x18002813f  add     rsp, 20h
0x180028143  pop     rbx
0x180028144  retn
```
