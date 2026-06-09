# tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(void)

- ea: `0x1800c7fe0`
- end: `0x1800c8090`
- name: `??1?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7cec`
- `0x1800d0cb0`

## callees

- `0x1800c7fe0`
- `0x1800c8098`
- `0x1800c8104`
- `0x1800c8188`
- `0x1800c8208`
- `0x1800ca33c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c8045`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c8045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c807a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c807a`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rsi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,1>::complete_helper(p_LockCount, 4);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[7].SpinCount);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[7].LockCount);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[6].LockSemaphore);
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
0x1800c7fe0  mov     [rsp+arg_0], rbx
0x1800c7fe5  mov     [rsp+arg_8], rsi
0x1800c7fea  push    rdi
0x1800c7feb  sub     rsp, 20h
0x1800c7fef  lea     rax, ??_7?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::`vftable'
0x1800c7ff6  mov     rdi, rcx
0x1800c7ff9  mov     [rcx], rax
0x1800c7ffc  add     rcx, 8
0x1800c8000  lea     rsi, [rcx+0F0h]
0x1800c8007  cmp     qword ptr [rsi], 0
0x1800c800b  jz      short loc_1800C801D
0x1800c800d  test    byte ptr [rcx+14h], 1
0x1800c8011  jnz     short loc_1800C801D
0x1800c8013  mov     edx, 4
0x1800c8018  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x1800c801d  lea     rbx, [rdi+108h]
0x1800c8024  lea     rcx, [rbx+30h]
0x1800c8028  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800c802d  lea     rcx, [rbx+18h]
0x1800c8031  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800c8036  mov     rcx, rbx
0x1800c8039  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800c803e  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x1800c8045  call    cs:__imp_DeleteCriticalSection
0x1800c804b  mov     rcx, rsi
0x1800c804e  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800c8053  lea     rcx, [rdi+80h]
0x1800c805a  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800c805f  lea     rcx, [rdi+68h]
0x1800c8063  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800c8068  lea     rcx, [rdi+50h]
0x1800c806c  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x1800c8071  mov     rcx, [rdi+10h]; pv
0x1800c8075  test    rcx, rcx
0x1800c8078  jz      short loc_1800C8080
0x1800c807a  call    cs:__imp_CoTaskMemFree
0x1800c8080  mov     rbx, [rsp+28h+arg_0]
0x1800c8085  mov     rsi, [rsp+28h+arg_8]
0x1800c808a  add     rsp, 20h
0x1800c808e  pop     rdi
0x1800c808f  retn
```
