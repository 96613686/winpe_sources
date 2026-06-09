# tip2::test_data_control<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>::~test_data_control<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>(void)

- ea: `0x180031dcc`
- end: `0x180031e4e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003f5d0`

## callees

- `0x180031af4`
- `0x180031dcc`
- `0x18004ea30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e3d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>::~test_data_control<tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>>(
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
        tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180031dcc  mov     [rsp+arg_8], rbx
0x180031dd1  push    rdi
0x180031dd2  sub     rsp, 20h
0x180031dd6  mov     rdi, rcx
0x180031dd9  mov     rcx, [rcx]
0x180031ddc  test    rcx, rcx
0x180031ddf  jz      short loc_180031E1A
0x180031de1  add     rcx, 8
0x180031de5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180031dea  mov     rbx, [rdi]
0x180031ded  mov     qword ptr [rdi], 0
0x180031df4  test    rbx, rbx
0x180031df7  jz      short loc_180031E1A
0x180031df9  or      eax, 0FFFFFFFFh
0x180031dfc  lock xadd [rbx+118h], eax
0x180031e04  cmp     eax, 1
0x180031e07  jnz     short loc_180031E1A
0x180031e09  mov     rcx, rbx
0x180031e0c  call    ??1?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(void)
0x180031e11  mov     rcx, rbx; pv
0x180031e14  call    cs:__imp_CoTaskMemFree
0x180031e1a  mov     rbx, [rdi]
0x180031e1d  test    rbx, rbx
0x180031e20  jz      short loc_180031E43
0x180031e22  or      eax, 0FFFFFFFFh
0x180031e25  lock xadd [rbx+118h], eax
0x180031e2d  cmp     eax, 1
0x180031e30  jnz     short loc_180031E43
0x180031e32  mov     rcx, rbx
0x180031e35  call    ??1?$merged_data@U_tip_QueryBlocklistedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>::~merged_data<_tip_QueryBlocklistedTest,_tip_QueryBlocklistedTest>(void)
0x180031e3a  mov     rcx, rbx; pv
0x180031e3d  call    cs:__imp_CoTaskMemFree
0x180031e43  mov     rbx, [rsp+28h+arg_8]
0x180031e48  add     rsp, 20h
0x180031e4c  pop     rdi
0x180031e4d  retn
```
