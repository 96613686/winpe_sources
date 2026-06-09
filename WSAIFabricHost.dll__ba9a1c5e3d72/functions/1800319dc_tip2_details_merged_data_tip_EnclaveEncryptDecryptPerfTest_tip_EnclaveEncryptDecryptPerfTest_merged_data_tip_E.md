# tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(void)

- ea: `0x1800319dc`
- end: `0x180031a61`
- name: `??1?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fa8c`
- `0x180031cbc`
- `0x180031ef4`
- `0x180036954`
- `0x1800542b4`

## callees

- `0x1800319dc`
- `0x1800320b0`
- `0x18003244c`
- `0x1800324d0`
- `0x180032550`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031a1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031a1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a50`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::`vftable';
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
0x1800319dc  mov     [rsp+arg_0], rbx
0x1800319e1  push    rdi
0x1800319e2  sub     rsp, 20h
0x1800319e6  lea     rax, ??_7?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::`vftable'
0x1800319ed  mov     rbx, rcx
0x1800319f0  mov     [rcx], rax
0x1800319f3  add     rcx, 8
0x1800319f7  lea     rdi, [rcx+0F0h]
0x1800319fe  cmp     qword ptr [rdi], 0
0x180031a02  jz      short loc_180031A14
0x180031a04  test    byte ptr [rcx+14h], 1
0x180031a08  jnz     short loc_180031A14
0x180031a0a  mov     edx, 4
0x180031a0f  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180031a14  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180031a1b  call    cs:__imp_DeleteCriticalSection
0x180031a21  mov     rcx, rdi
0x180031a24  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180031a29  lea     rcx, [rbx+80h]
0x180031a30  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180031a35  lea     rcx, [rbx+68h]
0x180031a39  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180031a3e  lea     rcx, [rbx+50h]
0x180031a42  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180031a47  mov     rcx, [rbx+10h]; pv
0x180031a4b  test    rcx, rcx
0x180031a4e  jz      short loc_180031A56
0x180031a50  call    cs:__imp_CoTaskMemFree
0x180031a56  mov     rbx, [rsp+28h+arg_0]
0x180031a5b  add     rsp, 20h
0x180031a5f  pop     rdi
0x180031a60  retn
```
