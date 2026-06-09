# tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)

- ea: `0x180013d08`
- end: `0x180013d8a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001448c`
- `0x18001b7fc`

## callees

- `0x180013ae0`
- `0x180013d08`
- `0x180021ecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d79`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(
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
        tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013d08  mov     [rsp+arg_8], rbx
0x180013d0d  push    rdi
0x180013d0e  sub     rsp, 20h
0x180013d12  mov     rdi, rcx
0x180013d15  mov     rcx, [rcx]
0x180013d18  test    rcx, rcx
0x180013d1b  jz      short loc_180013D56
0x180013d1d  add     rcx, 8
0x180013d21  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013d26  mov     rbx, [rdi]
0x180013d29  mov     qword ptr [rdi], 0
0x180013d30  test    rbx, rbx
0x180013d33  jz      short loc_180013D56
0x180013d35  or      eax, 0FFFFFFFFh
0x180013d38  lock xadd [rbx+118h], eax
0x180013d40  cmp     eax, 1
0x180013d43  jnz     short loc_180013D56
0x180013d45  mov     rcx, rbx
0x180013d48  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x180013d4d  mov     rcx, rbx; pv
0x180013d50  call    cs:__imp_CoTaskMemFree
0x180013d56  mov     rbx, [rdi]
0x180013d59  test    rbx, rbx
0x180013d5c  jz      short loc_180013D7F
0x180013d5e  or      eax, 0FFFFFFFFh
0x180013d61  lock xadd [rbx+118h], eax
0x180013d69  cmp     eax, 1
0x180013d6c  jnz     short loc_180013D7F
0x180013d6e  mov     rcx, rbx
0x180013d71  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x180013d76  mov     rcx, rbx; pv
0x180013d79  call    cs:__imp_CoTaskMemFree
0x180013d7f  mov     rbx, [rsp+28h+arg_8]
0x180013d84  add     rsp, 20h
0x180013d88  pop     rdi
0x180013d89  retn
```
