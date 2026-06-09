# tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)

- ea: `0x18001359c`
- end: `0x18001364c`
- name: `??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001366c`
- `0x180026a18`
- `0x1800283e0`
- `0x180031910`
- `0x180031dd0`

## callees

- `0x18001359c`
- `0x1800137f8`
- `0x180013c6c`
- `0x180013cf0`
- `0x180013d70`
- `0x180027e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013601`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013601`
- `ole32!CoTaskMemFree` at `0x180013636`
- `ole32!CoTaskMemFree` at `0x180013636`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rsi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<1,0,1>::complete_helper(p_LockCount, 4);
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
0x18001359c  mov     [rsp+arg_0], rbx
0x1800135a1  mov     [rsp+arg_8], rsi
0x1800135a6  push    rdi
0x1800135a7  sub     rsp, 20h
0x1800135ab  lea     rax, ??_7?$merged_data@U_tip_MercuryBackupJsonSuccess_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable'
0x1800135b2  mov     rdi, rcx
0x1800135b5  mov     [rcx], rax
0x1800135b8  add     rcx, 8
0x1800135bc  lea     rsi, [rcx+0F0h]
0x1800135c3  cmp     qword ptr [rsi], 0
0x1800135c7  jz      short loc_1800135D9
0x1800135c9  test    byte ptr [rcx+14h], 1
0x1800135cd  jnz     short loc_1800135D9
0x1800135cf  mov     edx, 4
0x1800135d4  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestQueryOptions)
0x1800135d9  lea     rbx, [rdi+108h]
0x1800135e0  lea     rcx, [rbx+30h]
0x1800135e4  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800135e9  lea     rcx, [rbx+18h]
0x1800135ed  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800135f2  mov     rcx, rbx
0x1800135f5  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800135fa  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180013601  call    cs:__imp_DeleteCriticalSection
0x180013607  mov     rcx, rsi
0x18001360a  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18001360f  lea     rcx, [rdi+80h]
0x180013616  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x18001361b  lea     rcx, [rdi+68h]
0x18001361f  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180013624  lea     rcx, [rdi+50h]
0x180013628  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18001362d  mov     rcx, [rdi+10h]; pv
0x180013631  test    rcx, rcx
0x180013634  jz      short loc_18001363C
0x180013636  call    cs:__imp_CoTaskMemFree
0x18001363c  mov     rbx, [rsp+28h+arg_0]
0x180013641  mov     rsi, [rsp+28h+arg_8]
0x180013646  add     rsp, 20h
0x18001364a  pop     rdi
0x18001364b  retn
```
