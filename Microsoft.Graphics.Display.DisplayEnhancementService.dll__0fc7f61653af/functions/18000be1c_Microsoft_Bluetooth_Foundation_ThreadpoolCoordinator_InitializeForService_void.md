# Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(void)

- ea: `0x18000be1c`
- end: `0x18000bec1`
- name: `?InitializeForService@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bb6c`

## callees

- `0x180005884`
- `0x1800058bc`
- `0x18000be1c`
- `0x18000ff38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000be90`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000be90`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(
        Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *this)
{
  void *v2; // rcx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 v4; // rcx
  _QWORD *v5; // [rsp+30h] [rbp+8h]

  v5 = operator new(0x48u);
  *(_DWORD *)v5 = 3;
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  v5[5] = 0;
  v5[6] = 0;
  *((_DWORD *)v5 + 15) = 1;
  *((_DWORD *)v5 + 16) = 72;
  *((_DWORD *)v5 + 14) = 1;
  v2 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v5;
  if ( v2 )
    operator delete(v2, (const struct std::nothrow_t *)0x48);
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&public: static void wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(
    (char *)this + 16,
    ThreadpoolCleanupGroup);
  v4 = *((_QWORD *)this + 1);
  *(_QWORD *)(v4 + 16) = *((_QWORD *)this + 2);
  *(_QWORD *)(v4 + 24) = 0;
}

```

## disassembly

```asm
0x18000be1c  mov     [rsp+arg_8], rbx
0x18000be21  push    rdi
0x18000be22  sub     rsp, 20h
0x18000be26  mov     rdi, rcx
0x18000be29  mov     ebx, 48h ; 'H'
0x18000be2e  mov     ecx, ebx; Size
0x18000be30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000be35  lea     ecx, [rbx-47h]
0x18000be38  mov     [rsp+28h+arg_0], rax
0x18000be3d  mov     dword ptr [rax], 3
0x18000be43  mov     qword ptr [rax+8], 0
0x18000be4b  mov     qword ptr [rax+10h], 0
0x18000be53  mov     qword ptr [rax+18h], 0
0x18000be5b  mov     qword ptr [rax+20h], 0
0x18000be63  mov     qword ptr [rax+28h], 0
0x18000be6b  mov     qword ptr [rax+30h], 0
0x18000be73  mov     [rax+3Ch], ecx
0x18000be76  mov     [rax+40h], ebx
0x18000be79  mov     [rax+38h], ecx
0x18000be7c  mov     rcx, [rdi+8]; void *
0x18000be80  mov     [rdi+8], rax
0x18000be84  test    rcx, rcx
0x18000be87  jz      short loc_18000BE90
0x18000be89  mov     edx, ebx; struct std::nothrow_t *
0x18000be8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000be90  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000be96  mov     rdx, rax
0x18000be99  lea     rcx, [rdi+10h]
0x18000be9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?Destroy@DestroyThreadpoolCleanupGroup@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CLEANUP_GROUP@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(_TP_CLEANUP_GROUP *)
0x18000bea2  mov     rcx, [rdi+8]
0x18000bea6  mov     rax, [rdi+10h]
0x18000beaa  mov     rbx, [rsp+28h+arg_8]
0x18000beaf  mov     [rcx+10h], rax
0x18000beb3  mov     qword ptr [rcx+18h], 0
0x18000bebb  add     rsp, 20h
0x18000bebf  pop     rdi
0x18000bec0  retn
```
