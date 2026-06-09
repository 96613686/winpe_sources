# FSMonitorService::FSMonitorService(void)

- ea: `0x180006d7c`
- end: `0x180006e9d`
- name: `??0FSMonitorService@@IEAA@XZ`
- size: `289`
- prototype: `FSMonitorService *__fastcall(FSMonitorService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800087d0`

## callees

- `0x180003294`
- `0x1800060e8`
- `0x180006d1c`
- `0x180006d7c`
- `0x180006ea4`
- `0x180006f00`
- `0x180006f14`
- `0x180006f28`
- `0x18000d4f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006dc2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e4a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006dc2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e4a`

## pseudocode

```c
FSMonitorService *__fastcall FSMonitorService::FSMonitorService(FSMonitorService *this)
{
  *(_QWORD *)this = &FSMonitorService::`vftable';
  FSMonitorService::ProcessWatcherObjectAsyncCallback::ProcessWatcherObjectAsyncCallback((FSMonitorService *)((char *)this + 8));
  FSMonitorService::ProcessServiceObjectAsyncCallback::ProcessServiceObjectAsyncCallback((FSMonitorService *)((char *)this + 16));
  FSMonitorService::OnIdleTimeoutAsyncCallback::OnIdleTimeoutAsyncCallback((FSMonitorService *)((char *)this + 24));
  FSMonitorService::HandleCameraControlNotificationAsyncCallback::HandleCameraControlNotificationAsyncCallback((FSMonitorService *)((char *)this + 32));
  *((_DWORD *)this + 10) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_WORD *)this + 44) = 0;
  *((_DWORD *)this + 23) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *(_QWORD *)((char *)this + 156) = 0;
  *((_DWORD *)this + 38) = 0;
  `vector constructor iterator'((char *)this + 168, 0x10u, 2u, (void *(*)(void *))FSMWatcherEntry::FSMWatcherEntry);
  *((_QWORD *)this + 25) = 0;
  *(_QWORD *)((char *)this + 212) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_BYTE *)this + 224) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((char *)this + 312);
  *((_DWORD *)this + 86) = -1;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
  return this;
}

```

## disassembly

```asm
0x180006d7c  mov     [rsp+arg_0], rbx
0x180006d81  push    rdi
0x180006d82  sub     rsp, 20h
0x180006d86  lea     rax, ??_7FSMonitorService@@6B@; const FSMonitorService::`vftable'
0x180006d8d  mov     rbx, rcx
0x180006d90  mov     [rcx], rax
0x180006d93  add     rcx, 8; this
0x180006d97  call    ??0ProcessWatcherObjectAsyncCallback@FSMonitorService@@QEAA@XZ; FSMonitorService::ProcessWatcherObjectAsyncCallback::ProcessWatcherObjectAsyncCallback(void)
0x180006d9c  lea     rcx, [rbx+10h]; this
0x180006da0  call    ??0ProcessServiceObjectAsyncCallback@FSMonitorService@@QEAA@XZ; FSMonitorService::ProcessServiceObjectAsyncCallback::ProcessServiceObjectAsyncCallback(void)
0x180006da5  lea     rcx, [rbx+18h]; this
0x180006da9  call    ??0OnIdleTimeoutAsyncCallback@FSMonitorService@@QEAA@XZ; FSMonitorService::OnIdleTimeoutAsyncCallback::OnIdleTimeoutAsyncCallback(void)
0x180006dae  lea     rcx, [rbx+20h]; this
0x180006db2  call    ??0HandleCameraControlNotificationAsyncCallback@FSMonitorService@@QEAA@XZ; FSMonitorService::HandleCameraControlNotificationAsyncCallback::HandleCameraControlNotificationAsyncCallback(void)
0x180006db7  lea     rcx, [rbx+30h]; lpCriticalSection
0x180006dbb  mov     dword ptr [rbx+28h], 1
0x180006dc2  call    cs:__imp_InitializeCriticalSection
0x180006dc8  xor     edi, edi
0x180006dca  lea     rcx, [rbx+0A8h]; void *
0x180006dd1  mov     [rbx+58h], di
0x180006dd5  lea     r9, ??0FSMWatcherEntry@@QEAA@XZ; void *(*)(void *)
0x180006ddc  mov     [rbx+5Ch], edi
0x180006ddf  mov     [rbx+60h], rdi
0x180006de3  mov     [rbx+68h], edi
0x180006de6  lea     edx, [rdi+10h]; unsigned __int64
0x180006de9  mov     [rbx+70h], rdi
0x180006ded  lea     r8d, [rdi+2]; unsigned __int64
0x180006df1  mov     [rbx+78h], edi
0x180006df4  mov     [rbx+80h], rdi
0x180006dfb  mov     [rbx+88h], rdi
0x180006e02  mov     [rbx+90h], rdi
0x180006e09  mov     [rbx+9Ch], rdi
0x180006e10  mov     [rbx+98h], edi
0x180006e16  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180006e1b  mov     [rbx+0C8h], rdi
0x180006e22  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180006e29  mov     [rbx+0D4h], rdi
0x180006e30  mov     [rbx+0D0h], edi
0x180006e36  mov     [rbx+0E0h], dil
0x180006e3d  call    cs:__imp_InitializeCriticalSection
0x180006e43  lea     rcx, [rbx+110h]; lpCriticalSection
0x180006e4a  call    cs:__imp_InitializeCriticalSection
0x180006e50  lea     rcx, [rbx+138h]
0x180006e57  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180006e5c  mov     dword ptr [rbx+158h], 0FFFFFFFFh
0x180006e66  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180006e6b  cmp     al, 10h
0x180006e6d  jb      short loc_180006E8F
0x180006e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e76  lea     edx, [rdi+0Dh]
0x180006e79  mov     r9, rbx
0x180006e7c  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180006e83  mov     rcx, [rcx+0D8h]
0x180006e8a  call    WPP_SF_q
0x180006e8f  mov     rax, rbx
0x180006e92  mov     rbx, [rsp+28h+arg_0]
0x180006e97  add     rsp, 20h
0x180006e9b  pop     rdi
0x180006e9c  retn
```
