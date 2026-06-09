# tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)

- ea: `0x18004368c`
- end: `0x180043711`
- name: `??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043764`
- `0x1800437ec`
- `0x180046cf0`

## callees

- `0x180013f8c`
- `0x180014340`
- `0x1800143c4`
- `0x180014444`
- `0x180016dcc`
- `0x18004368c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800436cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800436cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043700`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
  DeleteCriticalSection(a1 + 5);
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(v3);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[3].LockCount);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&a1[2].LockSemaphore);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(&a1[2]);
  OwningThread = a1->OwningThread;
  if ( OwningThread )
    CoTaskMemFree(OwningThread);
}

```

## disassembly

```asm
0x18004368c  mov     [rsp+arg_0], rbx
0x180043691  push    rdi
0x180043692  sub     rsp, 20h
0x180043696  lea     rax, ??_7?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::`vftable'
0x18004369d  mov     rbx, rcx
0x1800436a0  mov     [rcx], rax
0x1800436a3  add     rcx, 8
0x1800436a7  lea     rdi, [rcx+0F0h]
0x1800436ae  cmp     qword ptr [rdi], 0
0x1800436b2  jz      short loc_1800436C4
0x1800436b4  test    byte ptr [rcx+14h], 1
0x1800436b8  jnz     short loc_1800436C4
0x1800436ba  mov     edx, 4
0x1800436bf  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800436c4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800436cb  call    cs:__imp_DeleteCriticalSection
0x1800436d1  mov     rcx, rdi
0x1800436d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800436d9  lea     rcx, [rbx+80h]
0x1800436e0  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800436e5  lea     rcx, [rbx+68h]
0x1800436e9  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800436ee  lea     rcx, [rbx+50h]
0x1800436f2  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x1800436f7  mov     rcx, [rbx+10h]; pv
0x1800436fb  test    rcx, rcx
0x1800436fe  jz      short loc_180043706
0x180043700  call    cs:__imp_CoTaskMemFree
0x180043706  mov     rbx, [rsp+28h+arg_0]
0x18004370b  add     rsp, 20h
0x18004370f  pop     rdi
0x180043710  retn
```
