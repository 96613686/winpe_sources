# tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)

- ea: `0x180013e54`
- end: `0x180013e89`
- name: `??1?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030c30`

## callees

- `0x180013ae0`
- `0x180013e54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e7d`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180013e54  push    rbx
0x180013e56  sub     rsp, 20h
0x180013e5a  mov     rbx, [rcx]
0x180013e5d  test    rbx, rbx
0x180013e60  jz      short loc_180013E83
0x180013e62  or      eax, 0FFFFFFFFh
0x180013e65  lock xadd [rbx+118h], eax
0x180013e6d  cmp     eax, 1
0x180013e70  jnz     short loc_180013E83
0x180013e72  mov     rcx, rbx
0x180013e75  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x180013e7a  mov     rcx, rbx; pv
0x180013e7d  call    cs:__imp_CoTaskMemFree
0x180013e83  add     rsp, 20h
0x180013e87  pop     rbx
0x180013e88  retn
```
