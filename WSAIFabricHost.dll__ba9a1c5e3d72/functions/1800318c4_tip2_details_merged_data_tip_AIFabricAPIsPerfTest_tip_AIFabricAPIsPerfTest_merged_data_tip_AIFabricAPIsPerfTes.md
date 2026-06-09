# tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)

- ea: `0x1800318c4`
- end: `0x180031949`
- name: `??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `45`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f924`
- `0x180031bac`
- `0x180031e54`
- `0x180031f94`
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
- `0x18004eb70`
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
- `0x180083c35`

## callees

- `0x1800318c4`
- `0x1800320b0`
- `0x18003244c`
- `0x1800324d0`
- `0x180032550`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031903`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031938`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::`vftable';
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
0x1800318c4  mov     [rsp+arg_0], rbx
0x1800318c9  push    rdi
0x1800318ca  sub     rsp, 20h
0x1800318ce  lea     rax, ??_7?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::`vftable'
0x1800318d5  mov     rbx, rcx
0x1800318d8  mov     [rcx], rax
0x1800318db  add     rcx, 8
0x1800318df  lea     rdi, [rcx+0F0h]
0x1800318e6  cmp     qword ptr [rdi], 0
0x1800318ea  jz      short loc_1800318FC
0x1800318ec  test    byte ptr [rcx+14h], 1
0x1800318f0  jnz     short loc_1800318FC
0x1800318f2  mov     edx, 4
0x1800318f7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800318fc  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180031903  call    cs:__imp_DeleteCriticalSection
0x180031909  mov     rcx, rdi
0x18003190c  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180031911  lea     rcx, [rbx+80h]
0x180031918  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x18003191d  lea     rcx, [rbx+68h]
0x180031921  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180031926  lea     rcx, [rbx+50h]
0x18003192a  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18003192f  mov     rcx, [rbx+10h]; pv
0x180031933  test    rcx, rcx
0x180031936  jz      short loc_18003193E
0x180031938  call    cs:__imp_CoTaskMemFree
0x18003193e  mov     rbx, [rsp+28h+arg_0]
0x180031943  add     rsp, 20h
0x180031947  pop     rdi
0x180031948  retn
```
