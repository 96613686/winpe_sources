# tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)

- ea: `0x180031bac`
- end: `0x180031c2e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `40`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180033500`
- `0x180033c40`
- `0x18003418c`
- `0x180034730`
- `0x180034a00`
- `0x180035640`
- `0x180035cb0`
- `0x180036330`
- `0x180036610`
- `0x180037488`
- `0x18003acac`
- `0x18003ba74`
- `0x18003c340`
- `0x18003d104`
- `0x18003e364`
- `0x18003e914`
- `0x18003eb7c`
- `0x18003f5d0`
- `0x180040a70`
- `0x180042ab0`
- `0x180044780`
- `0x180044f80`
- `0x180046140`
- `0x180048c60`
- `0x180049b80`
- `0x18004a3a0`
- `0x180074cb0`
- `0x180074e4c`
- `0x180075068`
- `0x180075748`
- `0x1800758e4`
- `0x180075a80`
- `0x180075c1c`
- `0x180075dd0`
- `0x1800765d0`
- `0x180076a40`
- `0x180076ec0`
- `0x180077570`
- `0x180077c10`
- `0x180083f1d`

## callees

- `0x1800318c4`
- `0x180031bac`
- `0x18004ea30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c1d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update((__int64)&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180031bac  mov     [rsp+arg_8], rbx
0x180031bb1  push    rdi
0x180031bb2  sub     rsp, 20h
0x180031bb6  mov     rdi, rcx
0x180031bb9  mov     rcx, [rcx]
0x180031bbc  test    rcx, rcx
0x180031bbf  jz      short loc_180031BFA
0x180031bc1  add     rcx, 8
0x180031bc5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180031bca  mov     rbx, [rdi]
0x180031bcd  mov     qword ptr [rdi], 0
0x180031bd4  test    rbx, rbx
0x180031bd7  jz      short loc_180031BFA
0x180031bd9  or      eax, 0FFFFFFFFh
0x180031bdc  lock xadd [rbx+120h], eax
0x180031be4  cmp     eax, 1
0x180031be7  jnz     short loc_180031BFA
0x180031be9  mov     rcx, rbx
0x180031bec  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180031bf1  mov     rcx, rbx; pv
0x180031bf4  call    cs:__imp_CoTaskMemFree
0x180031bfa  mov     rbx, [rdi]
0x180031bfd  test    rbx, rbx
0x180031c00  jz      short loc_180031C23
0x180031c02  or      eax, 0FFFFFFFFh
0x180031c05  lock xadd [rbx+120h], eax
0x180031c0d  cmp     eax, 1
0x180031c10  jnz     short loc_180031C23
0x180031c12  mov     rcx, rbx
0x180031c15  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180031c1a  mov     rcx, rbx; pv
0x180031c1d  call    cs:__imp_CoTaskMemFree
0x180031c23  mov     rbx, [rsp+28h+arg_8]
0x180031c28  add     rsp, 20h
0x180031c2c  pop     rdi
0x180031c2d  retn
```
