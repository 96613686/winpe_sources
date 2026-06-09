# tip2::tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::~tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>(void)

- ea: `0x180028098`
- end: `0x1800280cd`
- name: `??1?$tip_test@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031a12`

## callees

- `0x180027bf4`
- `0x180028098`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280c1`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>::~tip_test<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180028098  push    rbx
0x18002809a  sub     rsp, 20h
0x18002809e  mov     rbx, [rcx]
0x1800280a1  test    rbx, rbx
0x1800280a4  jz      short loc_1800280C7
0x1800280a6  or      eax, 0FFFFFFFFh
0x1800280a9  lock xadd [rbx+118h], eax
0x1800280b1  cmp     eax, 1
0x1800280b4  jnz     short loc_1800280C7
0x1800280b6  mov     rcx, rbx
0x1800280b9  call    ??1?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::~merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>(void)
0x1800280be  mov     rcx, rbx; pv
0x1800280c1  call    cs:__imp_CoTaskMemFree
0x1800280c7  add     rsp, 20h
0x1800280cb  pop     rbx
0x1800280cc  retn
```
