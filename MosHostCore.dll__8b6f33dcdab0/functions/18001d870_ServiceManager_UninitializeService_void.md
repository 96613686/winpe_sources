# ServiceManager::UninitializeService(void)

- ea: `0x18001d870`
- end: `0x18001d997`
- name: `?UninitializeService@ServiceManager@@AEAAXXZ`
- size: `295`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012cf0`
- `0x180015200`
- `0x18001cb60`
- `0x18001d760`

## callees

- `0x18000ec6c`
- `0x180015ed0`
- `0x18001d7c4`
- `0x18001d870`
- `0x18001eec4`
- `0x18001f650`
- `0x180022884`

## import_xrefs

- `mapsbtsvc!MapsBackgroundTransferService_UnregisterCallbacks` at `0x18001d8aa`
- `mapsbtsvc!MapsBackgroundTransferService_UnregisterCallbacks` at `0x18001d8aa`
- `MosStorage!MosStorageResetCacheValues` at `0x18001d8b8`
- `MosStorage!MosStorageResetCacheValues` at `0x18001d8b8`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d8a4`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d986`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d8a4`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d986`

## string_xrefs

- `0x18001d880`: `[MosHost] Service - Shutdown - uninitializing ...`
- `0x18001d892`: `ServiceManager::UninitializeService`
- `0x18001d97a`: `ServiceManager::UninitializeService`
- `0x18001d965`: `[MosHost] Service - Shutdown - uninitializing complete`

## pseudocode

```c
void __fastcall ServiceManager::UninitializeService(ServiceManager *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 882);
  ZTraceHelper(
    5,
    "ServiceManager::UninitializeService",
    2672,
    this,
    "[MosHost] Service - Shutdown - uninitializing ...");
  MapsBackgroundTransferService_UnregisterCallbacks();
  ServiceManager::UninitializeMOSAndBing(this);
  MosStorageResetCacheValues();
  TimerQueue::Uninitialize((ServiceManager *)((char *)this + 4280));
  ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
  TransferMonitor::Stop((ServiceManager *)((char *)this + 4112));
  *((_BYTE *)this + 4316) = 0;
  *((_DWORD *)this + 882) = 0;
  *((_DWORD *)this + 862) = -2080374773;
  PackageManager::ClearPackageInformation((ServiceManager *)((char *)this + 3568));
  *((_DWORD *)this + 887) = 0;
  *((_DWORD *)this + 1080) = 0;
  *(_QWORD *)((char *)this + 4332) = 0;
  *((_QWORD *)this + 543) = 0;
  *((_QWORD *)this + 544) = 0;
  if ( v1 && ((*((_DWORD *)this + 881) - 7) & 0xFFFFFFFD) != 0 )
  {
    *((_QWORD *)this + 442) = 0;
    ServiceManager::FireOdmlStateChange(this);
  }
  ZTraceHelper(
    5,
    "ServiceManager::UninitializeService",
    2700,
    this,
    "[MosHost] Service - Shutdown - uninitializing complete");
}

```

## disassembly

```asm
0x18001d870  mov     [rsp+arg_0], rbx
0x18001d875  push    rdi
0x18001d876  sub     rsp, 30h
0x18001d87a  mov     ebx, [rcx+0DC8h]
0x18001d880  lea     rax, aMoshostService_5; "[MosHost] Service - Shutdown - uninitia"...
0x18001d887  mov     rdi, rcx
0x18001d88a  mov     [rsp+38h+var_18], rax
0x18001d88f  mov     r9, rcx
0x18001d892  lea     rdx, aServicemanager_56; "ServiceManager::UninitializeService"
0x18001d899  mov     ecx, 5
0x18001d89e  mov     r8d, 0A70h
0x18001d8a4  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001d8aa  call    cs:__imp_?MapsBackgroundTransferService_UnregisterCallbacks@@YAJXZ; MapsBackgroundTransferService_UnregisterCallbacks(void)
0x18001d8b0  mov     rcx, rdi; this
0x18001d8b3  call    ?UninitializeMOSAndBing@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeMOSAndBing(void)
0x18001d8b8  call    cs:__imp_?MosStorageResetCacheValues@@YAXXZ; MosStorageResetCacheValues(void)
0x18001d8be  lea     rcx, [rdi+10B8h]; this
0x18001d8c5  call    ?Uninitialize@TimerQueue@@QEAAXXZ; TimerQueue::Uninitialize(void)
0x18001d8ca  lea     rcx, [rdi+0F68h]; this
0x18001d8d1  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x18001d8d6  lea     rcx, [rdi+1010h]; this
0x18001d8dd  call    ?Stop@TransferMonitor@@QEAAXXZ; TransferMonitor::Stop(void)
0x18001d8e2  lea     rcx, [rdi+0DF0h]; this
0x18001d8e9  mov     byte ptr [rdi+10DCh], 0
0x18001d8f0  mov     dword ptr [rdi+0DC8h], 0
0x18001d8fa  mov     dword ptr [rdi+0D78h], 8400000Bh
0x18001d904  call    ?ClearPackageInformation@PackageManager@@QEAAXXZ; PackageManager::ClearPackageInformation(void)
0x18001d909  mov     dword ptr [rdi+0DDCh], 0
0x18001d913  mov     dword ptr [rdi+10E0h], 0
0x18001d91d  mov     qword ptr [rdi+10ECh], 0
0x18001d928  mov     qword ptr [rdi+10F8h], 0
0x18001d933  mov     qword ptr [rdi+1100h], 0
0x18001d93e  test    ebx, ebx
0x18001d940  jz      short loc_18001D965
0x18001d942  mov     eax, [rdi+0DC4h]
0x18001d948  sub     eax, 7
0x18001d94b  test    eax, 0FFFFFFFDh
0x18001d950  jz      short loc_18001D965
0x18001d952  mov     rcx, rdi; this
0x18001d955  mov     qword ptr [rdi+0DD0h], 0
0x18001d960  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001d965  lea     rax, aMoshostService_1; "[MosHost] Service - Shutdown - uninitia"...
0x18001d96c  mov     r9, rdi
0x18001d96f  mov     r8d, 0A8Ch
0x18001d975  mov     [rsp+38h+var_18], rax
0x18001d97a  lea     rdx, aServicemanager_56; "ServiceManager::UninitializeService"
0x18001d981  mov     ecx, 5
0x18001d986  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001d98c  mov     rbx, [rsp+38h+arg_0]
0x18001d991  add     rsp, 30h
0x18001d995  pop     rdi
0x18001d996  retn
```
