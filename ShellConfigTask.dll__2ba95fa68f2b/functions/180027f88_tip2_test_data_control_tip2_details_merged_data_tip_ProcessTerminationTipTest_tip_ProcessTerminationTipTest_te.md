# tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(void)

- ea: `0x180027f88`
- end: `0x18002800a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002bc5c`

## callees

- `0x180021ecc`
- `0x180027d0c`
- `0x180027f88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ff9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(
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
        tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180027f88  mov     [rsp+arg_8], rbx
0x180027f8d  push    rdi
0x180027f8e  sub     rsp, 20h
0x180027f92  mov     rdi, rcx
0x180027f95  mov     rcx, [rcx]
0x180027f98  test    rcx, rcx
0x180027f9b  jz      short loc_180027FD6
0x180027f9d  add     rcx, 8
0x180027fa1  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180027fa6  mov     rbx, [rdi]
0x180027fa9  mov     qword ptr [rdi], 0
0x180027fb0  test    rbx, rbx
0x180027fb3  jz      short loc_180027FD6
0x180027fb5  or      eax, 0FFFFFFFFh
0x180027fb8  lock xadd [rbx+118h], eax
0x180027fc0  cmp     eax, 1
0x180027fc3  jnz     short loc_180027FD6
0x180027fc5  mov     rcx, rbx
0x180027fc8  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x180027fcd  mov     rcx, rbx; pv
0x180027fd0  call    cs:__imp_CoTaskMemFree
0x180027fd6  mov     rbx, [rdi]
0x180027fd9  test    rbx, rbx
0x180027fdc  jz      short loc_180027FFF
0x180027fde  or      eax, 0FFFFFFFFh
0x180027fe1  lock xadd [rbx+118h], eax
0x180027fe9  cmp     eax, 1
0x180027fec  jnz     short loc_180027FFF
0x180027fee  mov     rcx, rbx
0x180027ff1  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x180027ff6  mov     rcx, rbx; pv
0x180027ff9  call    cs:__imp_CoTaskMemFree
0x180027fff  mov     rbx, [rsp+28h+arg_8]
0x180028004  add     rsp, 20h
0x180028008  pop     rdi
0x180028009  retn
```
