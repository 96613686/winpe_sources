# tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)

- ea: `0x180013c48`
- end: `0x180013ccd`
- name: `??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012aa4`
- `0x180013e44`
- `0x180013f1c`
- `0x180014c40`
- `0x18001ac5c`
- `0x18001b234`
- `0x18001c060`
- `0x18001c64c`
- `0x18002b6a8`
- `0x180035604`
- `0x1800366f4`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`
- `0x1800f4eb4`

## callees

- `0x180013c48`
- `0x180013f8c`
- `0x180014340`
- `0x1800143c4`
- `0x180014444`
- `0x180016dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cbc`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable';
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
0x180013c48  mov     [rsp+arg_0], rbx
0x180013c4d  push    rdi
0x180013c4e  sub     rsp, 20h
0x180013c52  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x180013c59  mov     rbx, rcx
0x180013c5c  mov     [rcx], rax
0x180013c5f  add     rcx, 8
0x180013c63  lea     rdi, [rcx+0F0h]
0x180013c6a  cmp     qword ptr [rdi], 0
0x180013c6e  jz      short loc_180013C80
0x180013c70  test    byte ptr [rcx+14h], 1
0x180013c74  jnz     short loc_180013C80
0x180013c76  mov     edx, 4
0x180013c7b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180013c80  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180013c87  call    cs:__imp_DeleteCriticalSection
0x180013c8d  mov     rcx, rdi
0x180013c90  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180013c95  lea     rcx, [rbx+80h]
0x180013c9c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180013ca1  lea     rcx, [rbx+68h]
0x180013ca5  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180013caa  lea     rcx, [rbx+50h]
0x180013cae  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180013cb3  mov     rcx, [rbx+10h]; pv
0x180013cb7  test    rcx, rcx
0x180013cba  jz      short loc_180013CC2
0x180013cbc  call    cs:__imp_CoTaskMemFree
0x180013cc2  mov     rbx, [rsp+28h+arg_0]
0x180013cc7  add     rsp, 20h
0x180013ccb  pop     rdi
0x180013ccc  retn
```
