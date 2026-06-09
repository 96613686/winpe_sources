# ConnectedStorage::UserManager::~UserManager(void)

- ea: `0x180029fcc`
- end: `0x18002a117`
- name: `??1UserManager@ConnectedStorage@@UEAA@XZ`
- size: `331`
- prototype: `void __fastcall(ConnectedStorage::UserManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a4e0`

## callees

- `0x18000a040`
- `0x18000c218`
- `0x18000cb9c`
- `0x1800124b0`
- `0x180012688`
- `0x180029d18`
- `0x180029d68`
- `0x180029fcc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a0e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a0e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a09a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a09a`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002a067`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002a084`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002a067`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002a084`

## pseudocode

```c
void __fastcall ConnectedStorage::UserManager::~UserManager(ConnectedStorage::UserManager *this, __int64 a2, char *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // rcx
  __int64 v6; // rcx
  LPCRITICAL_SECTION lpCriticalSection[7]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = &ConnectedStorage::UserManager::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 168);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
    a3);
  v5 = *((_QWORD *)this + 37);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, *((_QWORD *)this + 40));
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 37) + 96LL))(
      *((_QWORD *)this + 37),
      *((_QWORD *)this + 39));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
  }
  v6 = *((_QWORD *)this + 36);
  if ( v6 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 136LL))(v6, *((_QWORD *)this + 41));
  if ( *((_QWORD *)this + 19) )
  {
    RtlUnsubscribeWnfStateChangeNotification();
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 20) )
  {
    RtlUnsubscribeWnfStateChangeNotification();
    *((_QWORD *)this + 20) = 0;
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  ConnectedStorage::ExecuteQueue::~ExecuteQueue((ConnectedStorage::UserManager *)((char *)this + 336));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 288);
  std::vector<ConnectedStorage::UserManager::LocalUserInfo>::~vector<ConnectedStorage::UserManager::LocalUserInfo>((char *)this + 264);
  std::vector<ConnectedStorage::UserManager::UserInfo>::~vector<ConnectedStorage::UserManager::UserInfo>((char *)this + 240);
  std::vector<ConnectedStorage::UserManager::UserInfo>::~vector<ConnectedStorage::UserManager::UserInfo>((char *)this + 216);
  DeleteCriticalSection(v4);
  std::function<long (void)>::~function<long (void)>((char *)this + 88);
  std::function<long (void)>::~function<long (void)>((char *)this + 24);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 8);
  *(_QWORD *)this = &ConnectedStorage::IUserManager::`vftable';
}

```

## disassembly

```asm
0x180029fcc  push    rbx
0x180029fce  push    rbp
0x180029fcf  push    rsi
0x180029fd0  push    rdi
0x180029fd1  sub     rsp, 38h
0x180029fd5  mov     rbx, rcx
0x180029fd8  lea     rax, ??_7UserManager@ConnectedStorage@@6B@; const ConnectedStorage::UserManager::`vftable'
0x180029fdf  mov     [rcx], rax
0x180029fe2  lea     rbp, [rcx+0A8h]
0x180029fe9  mov     rdx, rbp; struct ConnectedStorage::Mutex *
0x180029fec  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180029ff1  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180029ff6  lea     rdi, [rbx+128h]
0x180029ffd  mov     rcx, [rdi]
0x18002a000  test    rcx, rcx
0x18002a003  jz      short loc_18002A036
0x18002a005  mov     rax, [rcx]
0x18002a008  mov     rdx, [rbx+140h]
0x18002a00f  mov     rax, [rax+50h]
0x18002a013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a018  mov     rcx, [rdi]
0x18002a01b  mov     rax, [rcx]
0x18002a01e  mov     rdx, [rbx+138h]
0x18002a025  mov     rax, [rax+60h]
0x18002a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a02e  mov     rcx, rdi
0x18002a031  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a036  lea     rsi, [rbx+120h]
0x18002a03d  mov     rcx, [rsi]
0x18002a040  test    rcx, rcx
0x18002a043  jz      short loc_18002A05B
0x18002a045  mov     rax, [rcx]
0x18002a048  mov     rdx, [rbx+148h]
0x18002a04f  mov     rax, [rax+88h]
0x18002a056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a05b  mov     rcx, [rbx+98h]
0x18002a062  test    rcx, rcx
0x18002a065  jz      short loc_18002A078
0x18002a067  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18002a06d  mov     qword ptr [rbx+98h], 0
0x18002a078  mov     rcx, [rbx+0A0h]
0x18002a07f  test    rcx, rcx
0x18002a082  jz      short loc_18002A095
0x18002a084  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18002a08a  mov     qword ptr [rbx+0A0h], 0
0x18002a095  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18002a09a  call    cs:__imp_LeaveCriticalSection
0x18002a0a0  lea     rcx, [rbx+150h]; this
0x18002a0a7  call    ??1ExecuteQueue@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ExecuteQueue::~ExecuteQueue(void)
0x18002a0ac  mov     rcx, rdi
0x18002a0af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a0b4  mov     rcx, rsi
0x18002a0b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a0bc  lea     rcx, [rbx+108h]
0x18002a0c3  call    ??1?$vector@ULocalUserInfo@UserManager@ConnectedStorage@@V?$allocator@ULocalUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::UserManager::LocalUserInfo>::~vector<ConnectedStorage::UserManager::LocalUserInfo>(void)
0x18002a0c8  lea     rcx, [rbx+0F0h]
0x18002a0cf  call    ??1?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::UserManager::UserInfo>::~vector<ConnectedStorage::UserManager::UserInfo>(void)
0x18002a0d4  lea     rcx, [rbx+0D8h]
0x18002a0db  call    ??1?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::UserManager::UserInfo>::~vector<ConnectedStorage::UserManager::UserInfo>(void)
0x18002a0e0  mov     rcx, rbp; lpCriticalSection
0x18002a0e3  call    cs:__imp_DeleteCriticalSection
0x18002a0e9  lea     rcx, [rbx+58h]
0x18002a0ed  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18002a0f2  lea     rcx, [rbx+18h]
0x18002a0f6  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18002a0fb  lea     rcx, [rbx+8]
0x18002a0ff  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18002a104  lea     rax, ??_7IUserManager@ConnectedStorage@@6B@; const ConnectedStorage::IUserManager::`vftable'
0x18002a10b  mov     [rbx], rax
0x18002a10e  add     rsp, 38h
0x18002a112  pop     rdi
0x18002a113  pop     rsi
0x18002a114  pop     rbp
0x18002a115  pop     rbx
0x18002a116  retn
```
