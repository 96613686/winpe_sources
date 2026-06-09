# tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)

- ea: `0x180013e90`
- end: `0x180013ec5`
- name: `??1?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030f40`

## callees

- `0x180013b6c`
- `0x180013e90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013eb9`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180013e90  push    rbx
0x180013e92  sub     rsp, 20h
0x180013e96  mov     rbx, [rcx]
0x180013e99  test    rbx, rbx
0x180013e9c  jz      short loc_180013EBF
0x180013e9e  or      eax, 0FFFFFFFFh
0x180013ea1  lock xadd [rbx+118h], eax
0x180013ea9  cmp     eax, 1
0x180013eac  jnz     short loc_180013EBF
0x180013eae  mov     rcx, rbx
0x180013eb1  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x180013eb6  mov     rcx, rbx; pv
0x180013eb9  call    cs:__imp_CoTaskMemFree
0x180013ebf  add     rsp, 20h
0x180013ec3  pop     rbx
0x180013ec4  retn
```
