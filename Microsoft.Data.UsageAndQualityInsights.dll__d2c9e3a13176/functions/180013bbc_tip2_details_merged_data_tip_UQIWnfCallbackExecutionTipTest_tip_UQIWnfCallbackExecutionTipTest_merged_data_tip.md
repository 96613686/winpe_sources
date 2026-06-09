# tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)

- ea: `0x180013bbc`
- end: `0x180013c41`
- name: `??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012998`
- `0x180013dbc`
- `0x180013ecc`
- `0x180015930`
- `0x18001d95c`

## callees

- `0x180013bbc`
- `0x180013f8c`
- `0x180014340`
- `0x1800143c4`
- `0x180014444`
- `0x180016dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013bfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013bfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c30`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::`vftable';
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
0x180013bbc  mov     [rsp+arg_0], rbx
0x180013bc1  push    rdi
0x180013bc2  sub     rsp, 20h
0x180013bc6  lea     rax, ??_7?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::`vftable'
0x180013bcd  mov     rbx, rcx
0x180013bd0  mov     [rcx], rax
0x180013bd3  add     rcx, 8
0x180013bd7  lea     rdi, [rcx+0F0h]
0x180013bde  cmp     qword ptr [rdi], 0
0x180013be2  jz      short loc_180013BF4
0x180013be4  test    byte ptr [rcx+14h], 1
0x180013be8  jnz     short loc_180013BF4
0x180013bea  mov     edx, 4
0x180013bef  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180013bf4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180013bfb  call    cs:__imp_DeleteCriticalSection
0x180013c01  mov     rcx, rdi
0x180013c04  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180013c09  lea     rcx, [rbx+80h]
0x180013c10  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180013c15  lea     rcx, [rbx+68h]
0x180013c19  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180013c1e  lea     rcx, [rbx+50h]
0x180013c22  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180013c27  mov     rcx, [rbx+10h]; pv
0x180013c2b  test    rcx, rcx
0x180013c2e  jz      short loc_180013C36
0x180013c30  call    cs:__imp_CoTaskMemFree
0x180013c36  mov     rbx, [rsp+28h+arg_0]
0x180013c3b  add     rsp, 20h
0x180013c3f  pop     rdi
0x180013c40  retn
```
