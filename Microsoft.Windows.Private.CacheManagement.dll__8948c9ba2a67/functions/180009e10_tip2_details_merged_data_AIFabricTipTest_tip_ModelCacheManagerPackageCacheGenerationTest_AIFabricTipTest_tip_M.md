# tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)

- ea: `0x180009e10`
- end: `0x180009ec8`
- name: `?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ`
- size: `184`
- prototype: `__int64 __fastcall(char *pv)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007410`
- `0x180007e10`
- `0x180008480`
- `0x1800095d0`

## callees

- `0x180002370`
- `0x180009e10`
- `0x18000adb0`
- `0x18000c600`
- `0x18000c6f0`
- `0x18000c780`
- `0x18000dfa0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009e6e`
- `KERNEL32!DeleteCriticalSection` at `0x180009e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(
        char *pv)
{
  unsigned __int32 v2; // edi
  char *v3; // rcx
  void *v4; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)pv + 74);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::`vftable';
    v3 = pv + 8;
    if ( *((_QWORD *)v3 + 29) && (v3[20] & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)v3, 4u);
    std::wstring::~wstring(pv + 264);
    DeleteCriticalSection((LPCRITICAL_SECTION)pv + 5);
    if ( *((_QWORD *)pv + 30) )
      TestClose();
    tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(pv + 128);
    tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>((void **)pv + 13);
    tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(pv + 80);
    v4 = (void *)*((_QWORD *)pv + 2);
    if ( v4 )
      CoTaskMemFree(v4);
    CoTaskMemFree(pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180009e10  mov     [rsp+arg_0], rbx
0x180009e15  push    rdi
0x180009e16  sub     rsp, 20h
0x180009e1a  mov     rbx, rcx
0x180009e1d  mov     edi, 0FFFFFFFFh
0x180009e22  lock xadd [rcx+128h], edi
0x180009e2a  sub     edi, 1
0x180009e2d  jnz     loc_180009EBB
0x180009e33  lea     rax, ??_7?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::`vftable'
0x180009e3a  mov     [rcx], rax
0x180009e3d  add     rcx, 8
0x180009e41  cmp     qword ptr [rcx+0E8h], 0
0x180009e49  jz      short loc_180009E5B
0x180009e4b  test    byte ptr [rcx+14h], 1
0x180009e4f  jnz     short loc_180009E5B
0x180009e51  mov     edx, 4
0x180009e56  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180009e5b  lea     rcx, [rbx+108h]
0x180009e62  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009e67  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009e6e  call    cs:__imp_DeleteCriticalSection
0x180009e74  mov     rcx, [rbx+0F0h]
0x180009e7b  test    rcx, rcx
0x180009e7e  jz      short loc_180009E85
0x180009e80  call    TestClose
0x180009e85  lea     rcx, [rbx+80h]
0x180009e8c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180009e91  lea     rcx, [rbx+68h]
0x180009e95  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180009e9a  lea     rcx, [rbx+50h]
0x180009e9e  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180009ea3  mov     rcx, [rbx+10h]; pv
0x180009ea7  test    rcx, rcx
0x180009eaa  jz      short loc_180009EB2
0x180009eac  call    cs:__imp_CoTaskMemFree
0x180009eb2  mov     rcx, rbx; pv
0x180009eb5  call    cs:__imp_CoTaskMemFree
0x180009ebb  mov     rbx, [rsp+28h+arg_0]
0x180009ec0  mov     eax, edi
0x180009ec2  add     rsp, 20h
0x180009ec6  pop     rdi
0x180009ec7  retn
```
