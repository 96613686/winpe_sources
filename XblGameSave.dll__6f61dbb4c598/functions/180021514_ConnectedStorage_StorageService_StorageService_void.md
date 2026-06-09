# ConnectedStorage::StorageService::~StorageService(void)

- ea: `0x180021514`
- end: `0x1800215f5`
- name: `??1StorageService@ConnectedStorage@@UEAA@XZ`
- size: `225`
- prototype: `void __fastcall(ConnectedStorage::StorageService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800219c0`

## callees

- `0x18000aae4`
- `0x18000cb9c`
- `0x180013e1c`
- `0x1800160c8`
- `0x180016d84`
- `0x1800170d4`
- `0x180021368`
- `0x180021514`
- `0x180024f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800215cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800215cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002159a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002159a`

## string_xrefs

- `0x1800215e3`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectedStorage::StorageService::~StorageService(
        ConnectedStorage::StorageService *this,
        __int64 a2,
        char *a3)
{
  char *v4; // r8
  const unsigned __int16 *v5; // r8
  struct ConnectedStorage::Mutex *v6; // rbx
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &ConnectedStorage::StorageService::`vftable'{for `IStorageService'};
  *((_QWORD *)this + 1) = &ConnectedStorage::StorageService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  if ( !ConnectedStorage::gShutdown )
  {
    ConnectedStorage::StorageService::SendPackageStateChange((__int64)this, 4, a3);
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v4);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v5);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v6 = qword_1800C0858;
    ConnectedStorage::Service::UnregisterClient(qword_1800C0858, this);
    if ( v6 )
      ConnectedStorage::Service::ReturnInstance();
  }
  ConnectedStorage::CallerInfoWithResult::~CallerInfoWithResult((ConnectedStorage::StorageService *)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180021514  mov     [rsp+arg_0], rbx
0x180021519  push    rdi
0x18002151a  sub     rsp, 30h
0x18002151e  mov     rdi, rcx
0x180021521  lea     rax, ??_7StorageService@ConnectedStorage@@6BIStorageService@@@; const ConnectedStorage::StorageService::`vftable'{for `IStorageService'}
0x180021528  mov     [rcx], rax
0x18002152b  lea     rax, ??_7StorageService@ConnectedStorage@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@Microsoft@@@; const ConnectedStorage::StorageService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180021532  mov     [rcx+8], rax
0x180021536  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x18002153d  jnz     short loc_1800215BE
0x18002153f  mov     edx, 4
0x180021544  call    ?SendPackageStateChange@StorageService@ConnectedStorage@@AEAAJW4PACKAGE_EXECUTION_STATE@@@Z; ConnectedStorage::StorageService::SendPackageStateChange(PACKAGE_EXECUTION_STATE)
0x180021549  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x180021550  jnz     short loc_1800215A0
0x180021552  or      edx, 0FFFFFFFFh; unsigned int
0x180021555  lea     rcx, qword_1800C0998; this
0x18002155c  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180021561  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180021568  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x18002156d  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180021572  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180021578  test    eax, eax
0x18002157a  jz      short loc_1800215E3
0x18002157c  inc     eax
0x18002157e  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180021584  mov     edx, 2
0x180021589  mov     rcx, cs:qword_1800C0858
0x180021590  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180021595  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x18002159a  call    cs:__imp_LeaveCriticalSection
0x1800215a0  mov     rbx, cs:qword_1800C0858
0x1800215a7  mov     rdx, rdi; struct IStorageService *
0x1800215aa  mov     rcx, rbx; this
0x1800215ad  call    ?UnregisterClient@Service@ConnectedStorage@@QEAAXPEAUIStorageService@@@Z; ConnectedStorage::Service::UnregisterClient(IStorageService *)
0x1800215b2  nop
0x1800215b3  test    rbx, rbx
0x1800215b6  jz      short loc_1800215BE
0x1800215b8  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x1800215bd  nop
0x1800215be  lea     rcx, [rdi+40h]; this
0x1800215c2  call    ??1CallerInfoWithResult@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfoWithResult::~CallerInfoWithResult(void)
0x1800215c7  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800215cb  call    cs:__imp_DeleteCriticalSection
0x1800215d1  mov     dword ptr [rdi+14h], 0C0000001h
0x1800215d8  mov     rbx, [rsp+38h+arg_0]
0x1800215dd  add     rsp, 30h
0x1800215e1  pop     rdi
0x1800215e2  retn
0x1800215e3  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x1800215ea  mov     ecx, 80004005h; this
0x1800215ef  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
