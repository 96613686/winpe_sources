# Container::Manager::Core::Details::SystemConfigurationManager::~SystemConfigurationManager(void)

- ea: `0x1800f970c`
- end: `0x1800f9936`
- name: `??1SystemConfigurationManager@Details@Core@Manager@Container@@QEAA@XZ`
- size: `554`
- prototype: `void __fastcall(Container::Manager::Core::Details::SystemConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180076530`

## callees

- `0x180004fc4`
- `0x180016658`
- `0x1800471dc`
- `0x18004eff8`
- `0x1800f970c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f97c0`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f97ff`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f9894`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f98b9`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f97c0`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f97ff`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f9894`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800f98b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f975b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f975b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f9780`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f9870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f9780`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f9870`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f973a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f976f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f97af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f97ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f976f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f97af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f97ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f978e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f97ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f980d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f978e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f97ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f980d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f984f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f984f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::SystemConfigurationManager::~SystemConfigurationManager(
        HANDLE *this)
{
  PTP_WORK *v2; // rsi
  unsigned int v3; // r8d
  const char *v4; // r9
  struct _TP_WORK *v5; // rbp
  DWORD LastError; // ebx
  HANDLE v7; // rbp
  DWORD v8; // ebx
  HANDLE v9; // rbp
  DWORD v10; // ebx
  HANDLE *v11; // rcx
  HANDLE v12; // rcx
  unsigned int v13; // r8d
  const char *v14; // r9
  const struct std::nothrow_t *v15; // rdx
  HANDLE v16; // rcx
  utl::_RefCountBase *v17; // rcx
  HANDLE v18; // rcx
  HANDLE v19; // rcx
  HANDLE *v20; // rcx
  HANDLE v21; // rcx
  utl::_RefCountBase *v22; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (PTP_WORK *)(this + 29);
  if ( this[7] != this[8] )
  {
    if ( *v2 )
    {
      if ( !SetEvent(this[30]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v3, v4);
      WaitForThreadpoolWorkCallbacks(*v2, 1);
      v5 = *v2;
      if ( *v2 )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(v5);
        SetLastError(LastError);
      }
      *v2 = 0;
    }
    else
    {
      v7 = this[16];
      if ( v7 )
      {
        v8 = GetLastError();
        RtlUnsubscribeWnfStateChangeNotification(v7);
        SetLastError(v8);
      }
      this[16] = 0;
    }
    v9 = this[12];
    if ( v9 )
    {
      v10 = GetLastError();
      RtlUnsubscribeWnfStateChangeNotification(v9);
      SetLastError(v10);
    }
    this[12] = 0;
  }
  v11 = (HANDLE *)this[31];
  if ( v11 != this + 33 )
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  v12 = this[30];
  if ( v12 && !CloseHandle(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
  if ( *v2 )
    CloseThreadpoolWork(*v2);
  utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(this + 22);
  v16 = this[16];
  if ( v16 )
    RtlUnsubscribeWnfStateChangeNotification(v16);
  v17 = (utl::_RefCountBase *)this[15];
  if ( v17 )
    utl::_RefCountBase::_DecStrong(v17);
  v18 = this[12];
  if ( v18 )
    RtlUnsubscribeWnfStateChangeNotification(v18);
  v19 = this[11];
  this[11] = 0;
  if ( v19 )
    operator delete(v19, v15);
  v20 = (HANDLE *)this[7];
  if ( v20 != this + 9 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  v21 = this[4];
  if ( v21 != (HANDLE)-1LL )
  {
    this[5] = v21;
    operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
  }
  v22 = (utl::_RefCountBase *)this[3];
  if ( v22 )
    utl::_RefCountBase::_DecStrong(v22);
}

```

## disassembly

```asm
0x1800f970c  push    rbx
0x1800f970e  push    rbp
0x1800f970f  push    rsi
0x1800f9710  push    rdi
0x1800f9711  sub     rsp, 28h
0x1800f9715  mov     rdi, rcx
0x1800f9718  lea     rsi, [rcx+0E8h]
0x1800f971f  mov     rax, [rcx+40h]
0x1800f9723  cmp     [rcx+38h], rax
0x1800f9727  jz      loc_1800F9821
0x1800f972d  cmp     qword ptr [rsi], 0
0x1800f9731  jz      short loc_1800F97A3
0x1800f9733  mov     rcx, [rcx+0F0h]; hEvent
0x1800f973a  call    cs:__imp_SetEvent
0x1800f9741  nop     dword ptr [rax+rax+00h]
0x1800f9746  mov     rcx, [rsp+48h]; this
0x1800f974b  test    eax, eax
0x1800f974d  jz      loc_1800F992B
0x1800f9753  mov     edx, 1; fCancelPendingCallbacks
0x1800f9758  mov     rcx, [rsi]; pwk
0x1800f975b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800f9762  nop     dword ptr [rax+rax+00h]
0x1800f9767  mov     rbp, [rsi]
0x1800f976a  test    rbp, rbp
0x1800f976d  jz      short loc_1800F979A
0x1800f976f  call    cs:__imp_GetLastError
0x1800f9776  nop     dword ptr [rax+rax+00h]
0x1800f977b  mov     ebx, eax
0x1800f977d  mov     rcx, rbp; pwk
0x1800f9780  call    cs:__imp_CloseThreadpoolWork
0x1800f9787  nop     dword ptr [rax+rax+00h]
0x1800f978c  mov     ecx, ebx; dwErrCode
0x1800f978e  call    cs:__imp_SetLastError
0x1800f9795  nop     dword ptr [rax+rax+00h]
0x1800f979a  mov     qword ptr [rsi], 0
0x1800f97a1  jmp     short loc_1800F97E5
0x1800f97a3  mov     rbp, [rcx+80h]
0x1800f97aa  test    rbp, rbp
0x1800f97ad  jz      short loc_1800F97DA
0x1800f97af  call    cs:__imp_GetLastError
0x1800f97b6  nop     dword ptr [rax+rax+00h]
0x1800f97bb  mov     ebx, eax
0x1800f97bd  mov     rcx, rbp
0x1800f97c0  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800f97c7  nop     dword ptr [rax+rax+00h]
0x1800f97cc  mov     ecx, ebx; dwErrCode
0x1800f97ce  call    cs:__imp_SetLastError
0x1800f97d5  nop     dword ptr [rax+rax+00h]
0x1800f97da  mov     qword ptr [rdi+80h], 0
0x1800f97e5  mov     rbp, [rdi+60h]
0x1800f97e9  test    rbp, rbp
0x1800f97ec  jz      short loc_1800F9819
0x1800f97ee  call    cs:__imp_GetLastError
0x1800f97f5  nop     dword ptr [rax+rax+00h]
0x1800f97fa  mov     ebx, eax
0x1800f97fc  mov     rcx, rbp
0x1800f97ff  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800f9806  nop     dword ptr [rax+rax+00h]
0x1800f980b  mov     ecx, ebx; dwErrCode
0x1800f980d  call    cs:__imp_SetLastError
0x1800f9814  nop     dword ptr [rax+rax+00h]
0x1800f9819  mov     qword ptr [rdi+60h], 0
0x1800f9821  mov     rcx, [rdi+0F8h]; void *
0x1800f9828  lea     rax, [rdi+108h]
0x1800f982f  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800f9836  cmp     rcx, rax
0x1800f9839  jz      short loc_1800F9843
0x1800f983b  mov     rdx, rbx; struct std::nothrow_t *
0x1800f983e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9843  mov     rcx, [rdi+0F0h]; hObject
0x1800f984a  test    rcx, rcx
0x1800f984d  jz      short loc_1800F9868
0x1800f984f  call    cs:__imp_CloseHandle
0x1800f9856  nop     dword ptr [rax+rax+00h]
0x1800f985b  mov     rcx, [rsp+48h]; this
0x1800f9860  test    eax, eax
0x1800f9862  jz      loc_1800F9920
0x1800f9868  mov     rcx, [rsi]; pwk
0x1800f986b  test    rcx, rcx
0x1800f986e  jz      short loc_1800F987C
0x1800f9870  call    cs:__imp_CloseThreadpoolWork
0x1800f9877  nop     dword ptr [rax+rax+00h]
0x1800f987c  lea     rcx, [rdi+0B0h]
0x1800f9883  call    ??1?$_OptionalData1@UHotPatches@Common@Manager@Container@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(void)
0x1800f9888  mov     rcx, [rdi+80h]
0x1800f988f  test    rcx, rcx
0x1800f9892  jz      short loc_1800F98A1
0x1800f9894  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800f989b  nop     dword ptr [rax+rax+00h]
0x1800f98a0  nop
0x1800f98a1  mov     rcx, [rdi+78h]; this
0x1800f98a5  test    rcx, rcx
0x1800f98a8  jz      short loc_1800F98B0
0x1800f98aa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f98af  nop
0x1800f98b0  mov     rcx, [rdi+60h]
0x1800f98b4  test    rcx, rcx
0x1800f98b7  jz      short loc_1800F98C5
0x1800f98b9  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800f98c0  nop     dword ptr [rax+rax+00h]
0x1800f98c5  mov     rcx, [rdi+58h]; void *
0x1800f98c9  mov     qword ptr [rdi+58h], 0
0x1800f98d1  test    rcx, rcx
0x1800f98d4  jz      short loc_1800F98DB
0x1800f98d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f98db  mov     rcx, [rdi+38h]; void *
0x1800f98df  lea     rax, [rdi+48h]
0x1800f98e3  cmp     rcx, rax
0x1800f98e6  jz      short loc_1800F98F0
0x1800f98e8  mov     rdx, rbx; struct std::nothrow_t *
0x1800f98eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f98f0  mov     rcx, [rdi+20h]; void *
0x1800f98f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f98f8  jz      short loc_1800F9907
0x1800f98fa  mov     [rdi+28h], rcx
0x1800f98fe  mov     rdx, rbx; struct std::nothrow_t *
0x1800f9901  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9906  nop
0x1800f9907  mov     rcx, [rdi+18h]; this
0x1800f990b  test    rcx, rcx
0x1800f990e  jz      short loc_1800F9916
0x1800f9910  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f9915  nop
0x1800f9916  add     rsp, 28h
0x1800f991a  pop     rdi
0x1800f991b  pop     rsi
0x1800f991c  pop     rbp
0x1800f991d  pop     rbx
0x1800f991e  retn
0x1800f9920  mov     edx, 0A0Bh; void *
0x1800f9925  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f992b  mov     edx, 0A01h; void *
0x1800f9930  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
