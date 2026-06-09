# Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::ProcessCustomEvent(_GUID const &,unsigned __int64,uchar *)

- ea: `0x180054be4`
- end: `0x180054d2b`
- name: `?ProcessCustomEvent@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@AEAAXAEBU_GUID@@_KPEAE@Z`
- size: `327`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *__hidden this, const struct _GUID *, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055d30`

## callees

- `0x1800021dc`
- `0x180004040`
- `0x180004060`
- `0x180012b38`
- `0x180048154`
- `0x180051e94`
- `0x18005280c`
- `0x180054be4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054c0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054c0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180054cab`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180054cab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::ProcessCustomEvent(
        Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *this,
        const struct _GUID *a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  struct _GUID *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rdi
  struct _GUID *v12; // rax
  const char *v13; // r9
  __int64 v14; // [rsp+20h] [rbp-28h] BYREF
  char *v15; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _GUID *v17; // [rsp+50h] [rbp+8h] BYREF

  v8 = (struct _GUID *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v17 = v8;
  v9 = *((_QWORD *)this + 19);
  if ( v9 && *(_DWORD *)(v9 + 8) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
    AcquireSRWLockExclusive((PSRWLOCK)this + 24);
    try
    {
      v15 = (char *)this + 192;
      v17 = (struct _GUID *)operator new(0x18u);
      v10 = std::vector<unsigned char>::vector<unsigned char>(v17, a4, &a4[a3]);
      v14 = v10;
      if ( !*((_QWORD *)this + 26) )
      {
        v11 = *((_QWORD *)this + 27);
        AcquireSRWLockExclusive((PSRWLOCK)(v11 + 88));
        v17 = (struct _GUID *)(v11 + 88);
        ++*(_DWORD *)(v11 + 96);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
        SubmitThreadpoolWork(*(PTP_WORK *)(v11 + 80));
      }
      v12 = (struct _GUID *)operator new(0x18u);
      *v12 = *a2;
      v14 = 0;
      *(_QWORD *)&v12[1].Data1 = v10;
      v17 = v12;
      std::list<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>::emplace_back<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>(
        (__int64 *)this + 25,
        (__int64)&v17);
      std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>(&v17);
      std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>(&v14);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
        v13);
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  }
}

```

## disassembly

```asm
0x180054be4  mov     [rsp+arg_8], rbx
0x180054be9  mov     [rsp+arg_10], rsi
0x180054bee  push    rdi
0x180054bef  push    r14
0x180054bf1  push    r15
0x180054bf3  sub     rsp, 30h
0x180054bf7  mov     rdi, r9
0x180054bfa  mov     r14, r8
0x180054bfd  mov     r15, rdx
0x180054c00  mov     rsi, rcx
0x180054c03  lea     rbx, [rcx+60h]
0x180054c07  mov     rcx, rbx; lpCriticalSection
0x180054c0a  call    cs:__imp_EnterCriticalSection
0x180054c10  mov     [rsp+48h+arg_0], rbx
0x180054c15  mov     rax, [rsi+98h]
0x180054c1c  test    rax, rax
0x180054c1f  jz      loc_180054D0A
0x180054c25  cmp     dword ptr [rax+8], 0
0x180054c29  jz      loc_180054D0A
0x180054c2f  lea     rcx, [rsp+48h+arg_0]
0x180054c34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180054c39  lea     rbx, [rsi+0C0h]
0x180054c40  mov     rcx, rbx; SRWLock
0x180054c43  call    cs:__imp_AcquireSRWLockExclusive
0x180054c49  mov     [rsp+48h+var_20], rbx
0x180054c4e  lea     rbx, [r14+rdi]
0x180054c52  mov     ecx, 18h; Size
0x180054c57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054c5c  mov     [rsp+48h+arg_0], rax
0x180054c61  mov     r8, rbx
0x180054c64  mov     rdx, rdi
0x180054c67  mov     rcx, rax
0x180054c6a  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180054c6f  mov     r14, rax
0x180054c72  mov     [rsp+48h+var_28], rax
0x180054c77  cmp     qword ptr [rsi+0D0h], 0
0x180054c7f  jnz     short loc_180054CB1
0x180054c81  mov     rdi, [rsi+0D8h]
0x180054c88  lea     rbx, [rdi+58h]
0x180054c8c  mov     rcx, rbx; SRWLock
0x180054c8f  call    cs:__imp_AcquireSRWLockExclusive
0x180054c95  mov     [rsp+48h+arg_0], rbx
0x180054c9a  inc     dword ptr [rdi+60h]
0x180054c9d  lea     rcx, [rsp+48h+arg_0]
0x180054ca2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054ca7  mov     rcx, [rdi+50h]; pwk
0x180054cab  call    cs:__imp_SubmitThreadpoolWork
0x180054cb1  mov     ecx, 18h; Size
0x180054cb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054cbb  movups  xmm0, xmmword ptr [r15]
0x180054cbf  movdqu  xmmword ptr [rax], xmm0
0x180054cc3  mov     [rsp+48h+var_28], 0
0x180054ccc  mov     [rax+10h], r14
0x180054cd0  mov     [rsp+48h+arg_0], rax
0x180054cd5  lea     rdx, [rsp+48h+arg_0]
0x180054cda  lea     rcx, [rsi+0C8h]
0x180054ce1  call    ??$emplace_back@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@@?$list@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@V?$allocator@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@1@$$QEAV21@@Z; std::list<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>::emplace_back<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>(std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT> &&)
0x180054ce6  nop
0x180054ce7  lea     rcx, [rsp+48h+arg_0]
0x180054cec  call    ??1?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>(void)
0x180054cf1  nop
0x180054cf2  lea     rcx, [rsp+48h+var_28]
0x180054cf7  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x180054cfc  nop
0x180054cfd  lea     rcx, [rsp+48h+var_20]
0x180054d02  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054d07  nop
0x180054d08  jmp     short loc_180054D17
0x180054d0a  lea     rcx, [rsp+48h+arg_0]
0x180054d0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180054d14  nop
0x180054d15  jmp     short $+2
0x180054d17  mov     rbx, [rsp+48h+arg_8]
0x180054d1c  mov     rsi, [rsp+48h+arg_10]
0x180054d21  add     rsp, 30h
0x180054d25  pop     r15
0x180054d27  pop     r14
0x180054d29  pop     rdi
0x180054d2a  retn
```
