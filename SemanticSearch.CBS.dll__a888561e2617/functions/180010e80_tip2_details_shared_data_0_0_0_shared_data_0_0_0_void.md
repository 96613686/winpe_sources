# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x180010e80`
- end: `0x180010edd`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fc60`
- `0x18001a180`

## callees

- `0x180010e80`
- `0x1800120f0`
- `0x180012190`
- `0x180012220`
- `0x180013e40`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010e90`
- `KERNEL32!DeleteCriticalSection` at `0x180010e90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ed0`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(__int64 a1)
{
  void *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  if ( *(_QWORD *)(a1 + 232) )
    TestClose();
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(a1 + 120);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(a1 + 96);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(a1 + 72);
  v2 = *(void **)(a1 + 8);
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180010e80  push    rbx
0x180010e82  sub     rsp, 20h
0x180010e86  mov     rbx, rcx
0x180010e89  add     rcx, 0C0h; lpCriticalSection
0x180010e90  call    cs:__imp_DeleteCriticalSection
0x180010e96  mov     rcx, [rbx+0E8h]
0x180010e9d  test    rcx, rcx
0x180010ea0  jz      short loc_180010EA7
0x180010ea2  call    TestClose
0x180010ea7  lea     rcx, [rbx+78h]
0x180010eab  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180010eb0  lea     rcx, [rbx+60h]
0x180010eb4  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180010eb9  lea     rcx, [rbx+48h]
0x180010ebd  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180010ec2  mov     rcx, [rbx+8]
0x180010ec6  test    rcx, rcx
0x180010ec9  jz      short loc_180010ED7
0x180010ecb  add     rsp, 20h
0x180010ecf  pop     rbx
0x180010ed0  jmp     cs:__imp_CoTaskMemFree
0x180010ed7  add     rsp, 20h
0x180010edb  pop     rbx
0x180010edc  retn
```
