# ConnectedStorage::NtmWrapper::~NtmWrapper(void)

- ea: `0x180067048`
- end: `0x1800671c2`
- name: `??1NtmWrapper@ConnectedStorage@@UEAA@XZ`
- size: `378`
- prototype: `void __fastcall(ConnectedStorage::NtmWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067220`

## callees

- `0x18000a040`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18001265c`
- `0x180012fc0`
- `0x180012ff8`
- `0x180013008`
- `0x180013028`
- `0x18001c090`
- `0x18001c2a8`
- `0x18001c63c`
- `0x180066f94`
- `0x180066fc0`
- `0x180066fec`
- `0x180067048`
- `0x180067958`
- `0x180067a28`
- `0x1800682e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006715d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006718b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800671aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006715d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006718b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800671aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800670f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067104`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800670f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067104`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180067130`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180067130`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ConnectedStorage::NtmWrapper::~NtmWrapper(ConnectedStorage::NtmWrapper *this, __int64 a2, char *a3)
{
  ConnectedStorage::NtmWrapper *v3; // rbx
  char *v4; // r8
  __int64 v5; // r8
  __int64 v6; // rdi
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+20h] [rbp-38h] BYREF
  LPCRITICAL_SECTION v8[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  char v12; // [rsp+70h] [rbp+18h] BYREF
  char v13; // [rsp+78h] [rbp+20h] BYREF

  v3 = this;
  *(_QWORD *)this = &ConnectedStorage::NtmWrapper::`vftable';
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v8,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 104),
    a3);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 8),
    v4);
  std::list<ConnectedStorage::NtmTransferWrapper>::begin((char *)v3 + 152, &v12);
  std::vector<ConnectedStorage::ContextDesc>::begin(v5, &v13);
  while ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                             &v12,
                             &v13) )
  {
    v6 = std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<_GUID>>>::operator*(&v12);
    v11 = *((_QWORD *)v3 + 7);
    Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v11);
    try
    {
      ConnectedStorage::NtmTransferWrapper::ScheduleCancelTransfer(v6, &v11);
    }
    catch ( ... )
    {
      v3 = this;
    }
    std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::function<void (enum ConnectedStorage::WebService::Status)>>>>::operator++(&v12);
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  LeaveCriticalSection(v8[0]);
  _InterlockedExchange((volatile __int32 *)v3 + 46, 42);
  if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool((char *)v3 + 192) )
  {
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)v3 + 24), 1);
    std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::reset((char *)v3 + 192, 0);
  }
  ConnectedStorage::NtmWrapper::RundownNtmTransfers(v3);
  ConnectedStorage::Handle::CloseHandle((ConnectedStorage::NtmWrapper *)((char *)v3 + 248));
  DeleteCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::~unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>((char *)v3 + 192);
  std::list<_GUID>::~list<_GUID>((char *)v3 + 168);
  std::list<ConnectedStorage::NtmTransferWrapper>::~list<ConnectedStorage::NtmTransferWrapper>((char *)v3 + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 104));
  std::wstring::_Tidy_deallocate((char *)v3 + 64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v3 + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 8));
  *(_QWORD *)v3 = &ConnectedStorage::INtmWrapper::`vftable';
}

```

## disassembly

```asm
0x180067048  mov     [rsp+arg_0], rcx
0x18006704d  push    rbx
0x18006704e  push    rdi
0x18006704f  sub     rsp, 48h
0x180067053  mov     rbx, rcx
0x180067056  lea     rax, ??_7NtmWrapper@ConnectedStorage@@6B@; const ConnectedStorage::NtmWrapper::`vftable'
0x18006705d  mov     [rcx], rax
0x180067060  lea     rdx, [rcx+68h]; struct ConnectedStorage::Mutex *
0x180067064  lea     rcx, [rsp+58h+var_28]; this
0x180067069  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18006706e  nop
0x18006706f  lea     rdx, [rbx+8]; struct ConnectedStorage::Mutex *
0x180067073  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180067078  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18006707d  nop
0x18006707e  lea     r8, [rbx+98h]
0x180067085  lea     rdx, [rsp+58h+arg_10]
0x18006708a  mov     rcx, r8
0x18006708d  call    ?begin@?$list@VNtmTransferWrapper@ConnectedStorage@@V?$allocator@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@2@XZ; std::list<ConnectedStorage::NtmTransferWrapper>::begin(void)
0x180067092  lea     rdx, [rsp+58h+arg_18]
0x180067097  mov     rcx, r8
0x18006709a  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18006709f  lea     rdx, [rsp+58h+arg_18]
0x1800670a4  lea     rcx, [rsp+58h+arg_10]
0x1800670a9  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x1800670ae  test    al, al
0x1800670b0  jz      short loc_1800670F3
0x1800670b2  lea     rcx, [rsp+58h+arg_10]
0x1800670b7  call    ??D?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U_GUID@@@std@@@std@@@std@@QEBAAEAU_GUID@@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<_GUID>>>::operator*(void)
0x1800670bc  mov     rdi, rax
0x1800670bf  mov     rcx, [rbx+38h]
0x1800670c3  mov     [rsp+58h+arg_8], rcx
0x1800670c8  lea     rcx, [rsp+58h+arg_8]
0x1800670cd  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x1800670d2  lea     rdx, [rsp+58h+arg_8]
0x1800670d7  mov     rcx, rdi
0x1800670da  call    ?ScheduleCancelTransfer@NtmTransferWrapper@ConnectedStorage@@QEAAXV?$ComPtr@UINetworkTransferManager@@@WRL@Microsoft@@@Z; ConnectedStorage::NtmTransferWrapper::ScheduleCancelTransfer(Microsoft::WRL::ComPtr<INetworkTransferManager>)
0x1800670df  nop
0x1800670e0  jmp     short loc_1800670E7
0x1800670e2  mov     rbx, [rsp+58h+arg_0]
0x1800670e7  lea     rcx, [rsp+58h+arg_10]
0x1800670ec  call    ??E?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::function<void (ConnectedStorage::WebService::Status)>>>>::operator++(void)
0x1800670f1  jmp     short loc_18006709F
0x1800670f3  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800670f8  call    cs:__imp_LeaveCriticalSection
0x1800670fe  nop
0x1800670ff  mov     rcx, [rsp+58h+var_28]; lpCriticalSection
0x180067104  call    cs:__imp_LeaveCriticalSection
0x18006710a  mov     eax, 2Ah ; '*'
0x18006710f  xchg    eax, [rbx+0B8h]
0x180067115  lea     rdi, [rbx+0C0h]
0x18006711c  mov     rcx, rdi
0x18006711f  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180067124  test    al, al
0x180067126  jz      short loc_180067140
0x180067128  mov     edx, 1; fCancelPendingCallbacks
0x18006712d  mov     rcx, [rdi]; pwa
0x180067130  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180067136  xor     edx, edx
0x180067138  mov     rcx, rdi
0x18006713b  call    ?reset@?$unique_ptr@U_TP_WAIT@@UTpWaitCloser@ConnectedStorage@@@std@@QEAAXPEAU_TP_WAIT@@@Z; std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::reset(_TP_WAIT *)
0x180067140  mov     rcx, rbx; this
0x180067143  call    ?RundownNtmTransfers@NtmWrapper@ConnectedStorage@@AEBAXXZ; ConnectedStorage::NtmWrapper::RundownNtmTransfers(void)
0x180067148  nop
0x180067149  lea     rcx, [rbx+0F8h]; this
0x180067150  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x180067155  nop
0x180067156  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18006715d  call    cs:__imp_DeleteCriticalSection
0x180067163  nop
0x180067164  mov     rcx, rdi
0x180067167  call    ??1?$unique_ptr@U_TP_WAIT@@UTpWaitCloser@ConnectedStorage@@@std@@QEAA@XZ; std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::~unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>(void)
0x18006716c  nop
0x18006716d  lea     rcx, [rbx+0A8h]
0x180067174  call    ??1?$list@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::list<_GUID>::~list<_GUID>(void)
0x180067179  nop
0x18006717a  lea     rcx, [rbx+98h]
0x180067181  call    ??1?$list@VNtmTransferWrapper@ConnectedStorage@@V?$allocator@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::list<ConnectedStorage::NtmTransferWrapper>::~list<ConnectedStorage::NtmTransferWrapper>(void)
0x180067186  nop
0x180067187  lea     rcx, [rbx+68h]; lpCriticalSection
0x18006718b  call    cs:__imp_DeleteCriticalSection
0x180067191  nop
0x180067192  lea     rcx, [rbx+40h]
0x180067196  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006719b  nop
0x18006719c  lea     rcx, [rbx+38h]
0x1800671a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800671a5  nop
0x1800671a6  lea     rcx, [rbx+8]; lpCriticalSection
0x1800671aa  call    cs:__imp_DeleteCriticalSection
0x1800671b0  nop
0x1800671b1  lea     rax, ??_7INtmWrapper@ConnectedStorage@@6B@; const ConnectedStorage::INtmWrapper::`vftable'
0x1800671b8  mov     [rbx], rax
0x1800671bb  add     rsp, 48h
0x1800671bf  pop     rdi
0x1800671c0  pop     rbx
0x1800671c1  retn
```
