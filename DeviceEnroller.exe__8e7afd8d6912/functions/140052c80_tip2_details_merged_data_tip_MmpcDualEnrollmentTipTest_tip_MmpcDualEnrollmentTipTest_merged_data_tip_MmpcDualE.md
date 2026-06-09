# tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::~merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>(void)

- ea: `0x140052c80`
- end: `0x140052d05`
- name: `??1?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140052d0c`
- `0x140052d94`
- `0x140052fc0`
- `0x140056784`

## callees

- `0x140052c80`
- `0x140052dd0`
- `0x140052e3c`
- `0x140052ec0`
- `0x140052f40`
- `0x140056498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140052cbf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140052cbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052cf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::~merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::`vftable';
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
0x140052c80  mov     [rsp+arg_0], rbx
0x140052c85  push    rdi
0x140052c86  sub     rsp, 20h
0x140052c8a  lea     rax, ??_7?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::`vftable'
0x140052c91  mov     rbx, rcx
0x140052c94  mov     [rcx], rax
0x140052c97  add     rcx, 8
0x140052c9b  lea     rdi, [rcx+0F0h]
0x140052ca2  cmp     qword ptr [rdi], 0
0x140052ca6  jz      short loc_140052CB8
0x140052ca8  test    byte ptr [rcx+14h], 1
0x140052cac  jnz     short loc_140052CB8
0x140052cae  mov     edx, 4
0x140052cb3  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x140052cb8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140052cbf  call    cs:__imp_DeleteCriticalSection
0x140052cc5  mov     rcx, rdi
0x140052cc8  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x140052ccd  lea     rcx, [rbx+80h]
0x140052cd4  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x140052cd9  lea     rcx, [rbx+68h]
0x140052cdd  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x140052ce2  lea     rcx, [rbx+50h]
0x140052ce6  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x140052ceb  mov     rcx, [rbx+10h]; pv
0x140052cef  test    rcx, rcx
0x140052cf2  jz      short loc_140052CFA
0x140052cf4  call    cs:__imp_CoTaskMemFree
0x140052cfa  mov     rbx, [rsp+28h+arg_0]
0x140052cff  add     rsp, 20h
0x140052d03  pop     rdi
0x140052d04  retn
```
