# tip2::test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>(void)

- ea: `0x18001a138`
- end: `0x18001a1ba`
- name: `??1?$test_data_control@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180025460`

## callees

- `0x18001a0ac`
- `0x18001a138`
- `0x180026270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1a9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 272), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x18001a138  mov     [rsp+arg_8], rbx
0x18001a13d  push    rdi
0x18001a13e  sub     rsp, 20h
0x18001a142  mov     rdi, rcx
0x18001a145  mov     rcx, [rcx]
0x18001a148  test    rcx, rcx
0x18001a14b  jz      short loc_18001A186
0x18001a14d  add     rcx, 8
0x18001a151  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18001a156  mov     rbx, [rdi]
0x18001a159  mov     qword ptr [rdi], 0
0x18001a160  test    rbx, rbx
0x18001a163  jz      short loc_18001A186
0x18001a165  or      eax, 0FFFFFFFFh
0x18001a168  lock xadd [rbx+110h], eax
0x18001a170  cmp     eax, 1
0x18001a173  jnz     short loc_18001A186
0x18001a175  mov     rcx, rbx
0x18001a178  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x18001a17d  mov     rcx, rbx; pv
0x18001a180  call    cs:__imp_CoTaskMemFree
0x18001a186  mov     rbx, [rdi]
0x18001a189  test    rbx, rbx
0x18001a18c  jz      short loc_18001A1AF
0x18001a18e  or      eax, 0FFFFFFFFh
0x18001a191  lock xadd [rbx+110h], eax
0x18001a199  cmp     eax, 1
0x18001a19c  jnz     short loc_18001A1AF
0x18001a19e  mov     rcx, rbx
0x18001a1a1  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x18001a1a6  mov     rcx, rbx; pv
0x18001a1a9  call    cs:__imp_CoTaskMemFree
0x18001a1af  mov     rbx, [rsp+28h+arg_8]
0x18001a1b4  add     rsp, 20h
0x18001a1b8  pop     rdi
0x18001a1b9  retn
```
