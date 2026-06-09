# tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)

- ea: `0x180013c80`
- end: `0x180013d02`
- name: `??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f1c4`

## callees

- `0x180013a54`
- `0x180013c80`
- `0x180021ecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cf1`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(
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
        tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013c80  mov     [rsp+arg_8], rbx
0x180013c85  push    rdi
0x180013c86  sub     rsp, 20h
0x180013c8a  mov     rdi, rcx
0x180013c8d  mov     rcx, [rcx]
0x180013c90  test    rcx, rcx
0x180013c93  jz      short loc_180013CCE
0x180013c95  add     rcx, 8
0x180013c99  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013c9e  mov     rbx, [rdi]
0x180013ca1  mov     qword ptr [rdi], 0
0x180013ca8  test    rbx, rbx
0x180013cab  jz      short loc_180013CCE
0x180013cad  or      eax, 0FFFFFFFFh
0x180013cb0  lock xadd [rbx+118h], eax
0x180013cb8  cmp     eax, 1
0x180013cbb  jnz     short loc_180013CCE
0x180013cbd  mov     rcx, rbx
0x180013cc0  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x180013cc5  mov     rcx, rbx; pv
0x180013cc8  call    cs:__imp_CoTaskMemFree
0x180013cce  mov     rbx, [rdi]
0x180013cd1  test    rbx, rbx
0x180013cd4  jz      short loc_180013CF7
0x180013cd6  or      eax, 0FFFFFFFFh
0x180013cd9  lock xadd [rbx+118h], eax
0x180013ce1  cmp     eax, 1
0x180013ce4  jnz     short loc_180013CF7
0x180013ce6  mov     rcx, rbx
0x180013ce9  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x180013cee  mov     rcx, rbx; pv
0x180013cf1  call    cs:__imp_CoTaskMemFree
0x180013cf7  mov     rbx, [rsp+28h+arg_8]
0x180013cfc  add     rsp, 20h
0x180013d00  pop     rdi
0x180013d01  retn
```
