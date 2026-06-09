# tip2::test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>(void)

- ea: `0x180031d44`
- end: `0x180031dc6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003acac`
- `0x18003d104`
- `0x18003e364`
- `0x180082bc0`
- `0x180082c6c`
- `0x180082e87`
- `0x180082ef6`
- `0x180082fa2`

## callees

- `0x180031a68`
- `0x180031d44`
- `0x18004ea30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031db5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031db5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>(
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
        tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180031d44  mov     [rsp+arg_8], rbx
0x180031d49  push    rdi
0x180031d4a  sub     rsp, 20h
0x180031d4e  mov     rdi, rcx
0x180031d51  mov     rcx, [rcx]
0x180031d54  test    rcx, rcx
0x180031d57  jz      short loc_180031D92
0x180031d59  add     rcx, 8
0x180031d5d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180031d62  mov     rbx, [rdi]
0x180031d65  mov     qword ptr [rdi], 0
0x180031d6c  test    rbx, rbx
0x180031d6f  jz      short loc_180031D92
0x180031d71  or      eax, 0FFFFFFFFh
0x180031d74  lock xadd [rbx+120h], eax
0x180031d7c  cmp     eax, 1
0x180031d7f  jnz     short loc_180031D92
0x180031d81  mov     rcx, rbx
0x180031d84  call    ??1?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(void)
0x180031d89  mov     rcx, rbx; pv
0x180031d8c  call    cs:__imp_CoTaskMemFree
0x180031d92  mov     rbx, [rdi]
0x180031d95  test    rbx, rbx
0x180031d98  jz      short loc_180031DBB
0x180031d9a  or      eax, 0FFFFFFFFh
0x180031d9d  lock xadd [rbx+120h], eax
0x180031da5  cmp     eax, 1
0x180031da8  jnz     short loc_180031DBB
0x180031daa  mov     rcx, rbx
0x180031dad  call    ??1?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(void)
0x180031db2  mov     rcx, rbx; pv
0x180031db5  call    cs:__imp_CoTaskMemFree
0x180031dbb  mov     rbx, [rsp+28h+arg_8]
0x180031dc0  add     rsp, 20h
0x180031dc4  pop     rdi
0x180031dc5  retn
```
