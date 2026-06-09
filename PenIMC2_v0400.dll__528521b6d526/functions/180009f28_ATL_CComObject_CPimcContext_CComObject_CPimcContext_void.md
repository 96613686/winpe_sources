# ATL::CComObject<CPimcContext>::~CComObject<CPimcContext>(void)

- ea: `0x180009f28`
- end: `0x18000a02d`
- name: `??1?$CComObject@VCPimcContext@@@ATL@@UEAA@XZ`
- size: `261`
- prototype: `__int64 __fastcall(CPimcContext *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a030`

## callees

- `0x180001360`
- `0x180006b10`
- `0x180007e24`
- `0x180009f28`
- `0x18000a064`
- `0x18000b39c`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009fa4`
- `KERNEL32!DeleteCriticalSection` at `0x180009fa4`
- `ole32!CoTaskMemFree` at `0x180009f7a`
- `ole32!CoTaskMemFree` at `0x180009f89`
- `ole32!CoTaskMemFree` at `0x180009f92`
- `ole32!CoTaskMemFree` at `0x180009f7a`
- `ole32!CoTaskMemFree` at `0x180009f89`
- `ole32!CoTaskMemFree` at `0x180009f92`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ATL::CComObject<CPimcContext>::~CComObject<CPimcContext>(struct _RTL_CRITICAL_SECTION *this)
{
  CPimcManager *LockSemaphore; // rcx
  _QWORD *v3; // rdi
  void *v4; // rcx
  void *v5; // rcx
  HANDLE v6; // rcx
  HANDLE v7; // [rsp+38h] [rbp+10h] BYREF

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CPimcContext>::`vftable';
  this->LockCount = -1073741823;
  LockSemaphore = (CPimcManager *)this->LockSemaphore;
  if ( LockSemaphore )
  {
    CPimcManager::UninstallWindowHook(LockSemaphore, (struct CPimcContext *)this);
    CPimcContext::ShutdownSharedMemoryCommunications((CPimcContext *)this);
    v3 = *(_QWORD **)&this[1].LockCount;
    if ( v3 )
    {
      v4 = (void *)v3[1];
      if ( v4 )
        CoTaskMemFree(v4);
      v5 = (void *)v3[3];
      if ( v5 )
        CoTaskMemFree(v5);
      CoTaskMemFree(v3);
      *(_QWORD *)&this[1].LockCount = 0;
    }
    DeleteCriticalSection(this + 5);
    SafeCloseHandle(&this[4].LockSemaphore);
    if ( LODWORD(this[7].OwningThread) )
    {
      LODWORD(v7) = this[7].OwningThread;
      ATL::CComGITPtr<ITabletContextP>::Revoke(&v7);
      ATL::CComGITPtr<ITabletContextP>::Revoke(&v7);
    }
    if ( this->LockSemaphore )
    {
      v7 = 0;
      v7 = this->LockSemaphore;
      v6 = v7;
      this->LockSemaphore = 0;
      if ( v6 )
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPimcContext::~CPimcContext((CPimcContext *)this);
}

```

## disassembly

```asm
0x180009f28  mov     [rsp+arg_10], rbx
0x180009f2d  mov     [rsp+arg_0], rcx
0x180009f32  push    rdi
0x180009f33  sub     rsp, 20h
0x180009f37  mov     rbx, rcx
0x180009f3a  lea     rax, ??_7?$CComObject@VCPimcContext@@@ATL@@6B@; const ATL::CComObject<CPimcContext>::`vftable'
0x180009f41  mov     [rcx], rax
0x180009f44  mov     dword ptr [rcx+8], 0C0000001h
0x180009f4b  mov     rcx, [rcx+18h]; this
0x180009f4f  test    rcx, rcx
0x180009f52  jz      loc_18000A006
0x180009f58  mov     rdx, rbx; struct CPimcContext *
0x180009f5b  call    ?UninstallWindowHook@CPimcManager@@QEAAJPEAVCPimcContext@@@Z; CPimcManager::UninstallWindowHook(CPimcContext *)
0x180009f60  mov     rcx, rbx; this
0x180009f63  call    ?ShutdownSharedMemoryCommunications@CPimcContext@@QEAAXXZ; CPimcContext::ShutdownSharedMemoryCommunications(void)
0x180009f68  mov     rdi, [rbx+30h]
0x180009f6c  test    rdi, rdi
0x180009f6f  jz      short loc_180009F9D
0x180009f71  mov     rcx, [rdi+8]; pv
0x180009f75  test    rcx, rcx
0x180009f78  jz      short loc_180009F80
0x180009f7a  call    cs:__imp_CoTaskMemFree
0x180009f80  mov     rcx, [rdi+18h]; pv
0x180009f84  test    rcx, rcx
0x180009f87  jz      short loc_180009F8F
0x180009f89  call    cs:__imp_CoTaskMemFree
0x180009f8f  mov     rcx, rdi; pv
0x180009f92  call    cs:__imp_CoTaskMemFree
0x180009f98  and     qword ptr [rbx+30h], 0
0x180009f9d  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009fa4  call    cs:__imp_DeleteCriticalSection
0x180009faa  lea     rcx, [rbx+0B8h]; void **
0x180009fb1  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180009fb6  mov     eax, [rbx+128h]
0x180009fbc  test    eax, eax
0x180009fbe  jz      short loc_180009FD9
0x180009fc0  mov     dword ptr [rsp+28h+arg_8], eax
0x180009fc4  lea     rcx, [rsp+28h+arg_8]
0x180009fc9  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x180009fce  nop
0x180009fcf  lea     rcx, [rsp+28h+arg_8]
0x180009fd4  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x180009fd9  cmp     qword ptr [rbx+18h], 0
0x180009fde  jz      short loc_18000A006
0x180009fe0  and     [rsp+28h+arg_8], 0
0x180009fe6  mov     rcx, [rbx+18h]
0x180009fea  mov     [rsp+28h+arg_8], rcx
0x180009fef  and     qword ptr [rbx+18h], 0
0x180009ff4  test    rcx, rcx
0x180009ff7  jz      short loc_18000A006
0x180009ff9  mov     rax, [rcx]
0x180009ffc  mov     rax, [rax+10h]
0x18000a000  call    cs:__guard_dispatch_icall_fptr
0x18000a006  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a00d  mov     rax, [rcx]
0x18000a010  mov     rax, [rax+10h]
0x18000a014  call    cs:__guard_dispatch_icall_fptr
0x18000a01a  nop
0x18000a01b  mov     rcx, rbx; this
0x18000a01e  mov     rbx, [rsp+28h+arg_10]
0x18000a023  add     rsp, 20h
0x18000a027  pop     rdi
0x18000a028  jmp     ??1CPimcContext@@QEAA@XZ; CPimcContext::~CPimcContext(void)
```
