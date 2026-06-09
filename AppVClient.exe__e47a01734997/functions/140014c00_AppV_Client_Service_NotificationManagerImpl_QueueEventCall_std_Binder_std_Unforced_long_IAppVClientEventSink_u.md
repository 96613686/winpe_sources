# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short> const &)

- ea: `0x140014c00`
- end: `0x140014f43`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140018520`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x14000a2e8`
- `0x1400147fc`
- `0x140014c00`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140014d73`
- `KERNEL32!CloseHandle` at `0x140014d99`
- `KERNEL32!CloseHandle` at `0x140014ed8`
- `KERNEL32!CloseHandle` at `0x140014d73`
- `KERNEL32!CloseHandle` at `0x140014d99`
- `KERNEL32!CloseHandle` at `0x140014ed8`
- `KERNEL32!GetCurrentThreadId` at `0x140014dcd`
- `KERNEL32!GetCurrentThreadId` at `0x140014dcd`
- `KERNEL32!LeaveCriticalSection` at `0x140014ec9`
- `KERNEL32!LeaveCriticalSection` at `0x140014ec9`
- `KERNEL32!EnterCriticalSection` at `0x140014dbc`
- `KERNEL32!EnterCriticalSection` at `0x140014dbc`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140014cc0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140014cc0`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140014ccc`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140014ccc`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(unsigned long,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,unsigned long &,ATL::CComBSTR,_GUID const &,_GUID const &,short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // rsi
  OLECHAR *v6; // rcx
  BSTR v7; // rax
  UINT v8; // eax
  void *v9; // rdi
  HANDLE v10; // rbx
  __int64 v11; // r14
  __int64 v12; // r8
  volatile signed __int32 *v13; // r15
  __int64 result; // rax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+38h] [rbp-C8h]
  __int128 *v18; // [rsp+48h] [rbp-B8h]
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[8]; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[40]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE *p_hObject; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  void **v28; // [rsp+E0h] [rbp-20h] BYREF
  char v29; // [rsp+E8h] [rbp-18h]
  HANDLE *v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+F8h] [rbp-8h]

  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(hObject) = 0x10000;
    p_hObject = &hObject;
    v27 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventBegin,
      a3,
      2,
      &v25);
  }
  v17 = 0;
  v5 = operator new(0x50u);
  hObject = v5;
  *v5 = &`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(unsigned long,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,unsigned long &,ATL::CComBSTR,_GUID const &,_GUID const &,short>>'::`2'::EventCallImpl::`vftable';
  v5[1] = *(_QWORD *)a3;
  *((_WORD *)v5 + 8) = *(_WORD *)(a3 + 8);
  *(_OWORD *)((char *)v5 + 20) = *(_OWORD *)(a3 + 12);
  *(_OWORD *)((char *)v5 + 36) = *(_OWORD *)(a3 + 28);
  v6 = *(OLECHAR **)(a3 + 48);
  if ( v6 )
  {
    v8 = SysStringByteLen(v6);
    v7 = SysAllocStringByteLen(*(LPCSTR *)(a3 + 48), v8);
  }
  else
  {
    v7 = 0;
  }
  v5[7] = v7;
  if ( *(_QWORD *)(a3 + 48) && !v7 )
    ATL::AtlThrowImpl(-2147024882);
  *((_DWORD *)v5 + 16) = *(_DWORD *)(a3 + 56);
  *((_BYTE *)v5 + 72) = *(_BYTE *)(a3 + 64);
  hObject = v5;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJKPEA_WU_GUID__1F_ZAEBU___Ph__00_2_AEAKVCComBSTR_ATL__AEBU4_AEBU4_F_std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJKPEA_WU_GUID__1F_ZAEBU___Ph__00_2_AEAKVCComBSTR_ATL__AEBU4_AEBU4_F_std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
  *((_QWORD *)v9 + 2) = v5;
  *(_QWORD *)&v17 = v5;
  *((_QWORD *)&v17 + 1) = v9;
  v25 = 0;
  p_hObject = 0;
  v27 = 7;
  LOWORD(v25) = 0;
  hObject = 0;
  if ( (AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(&v25, &hObject) & 0x8000000000LL) != 0 )
  {
    v10 = hObject;
    if ( hObject )
    {
      CloseHandle(hObject);
      v10 = 0;
      hObject = 0;
    }
    v28 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    v11 = a1 + 16;
    v30 = (HANDLE *)(a1 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( ++*(_DWORD *)(a1 + 56) == 1 )
      *(_DWORD *)(a1 + 60) = GetCurrentThreadId();
    v29 = 1;
    v18 = &v19;
    v19 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
    *(_QWORD *)&v19 = v5;
    *((_QWORD *)&v19 + 1) = v9;
    std::wstring::wstring(v20, &v25);
    v21 = 0x10000;
    std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(
      (__int64)v22,
      **(__int64 ***)(a1 + 72),
      *(__int64 **)(a1 + 72),
      (__int64)&v19);
    std::wstring::~wstring(v24);
    v13 = v23;
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    {
      LODWORD(hObject) = 0x10000;
      v30 = &hObject;
      v31 = 4;
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        Service_QueueClientEventEnd,
        v12,
        2,
        &v28);
    }
    if ( (*(_DWORD *)(v11 + 40))-- == 1 )
      *(_DWORD *)(v11 + 44) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v11);
    if ( v10 )
      CloseHandle(v10);
  }
  else if ( hObject )
  {
    CloseHandle(hObject);
  }
  std::wstring::~wstring(&v25);
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v9 + 2);
  if ( !(_DWORD)result )
  {
    (**(void (__fastcall ***)(void *))v9)(v9);
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v9 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  return result;
}

```

## disassembly

```asm
0x140014c00  push    rbp
0x140014c02  push    rbx
0x140014c03  push    rsi
0x140014c04  push    rdi
0x140014c05  push    r14
0x140014c07  push    r15
0x140014c09  lea     rbp, [rsp-18h]
0x140014c0e  sub     rsp, 118h
0x140014c15  mov     rax, cs:__security_cookie
0x140014c1c  xor     rax, rsp
0x140014c1f  mov     [rbp+40h+var_40], rax
0x140014c23  mov     rbx, r8
0x140014c26  mov     r15, rcx
0x140014c29  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014c30  jz      short loc_140014C6D
0x140014c32  mov     dword ptr [rsp+140h+hObject], 10000h
0x140014c3a  lea     rax, [rsp+140h+hObject]
0x140014c3f  mov     [rbp+40h+var_70], rax
0x140014c43  mov     [rbp+40h+var_68], 4
0x140014c4b  lea     rax, [rbp+40h+var_80]
0x140014c4f  mov     [rsp+140h+var_120], rax
0x140014c54  mov     r9d, 2
0x140014c5a  lea     rdx, Service_QueueClientEventBegin
0x140014c61  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140014c68  call    McGenEventWrite_EventWriteTransfer
0x140014c6d  xorps   xmm0, xmm0
0x140014c70  movdqu  [rsp+140h+var_108], xmm0
0x140014c76  mov     ecx, 50h ; 'P'; Size
0x140014c7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014c80  mov     rsi, rax
0x140014c83  mov     [rsp+140h+hObject], rax
0x140014c88  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x140014c8f  mov     [rsi], rax
0x140014c92  mov     rcx, [rbx]
0x140014c95  mov     [rsi+8], rcx
0x140014c99  movzx   ecx, word ptr [rbx+8]
0x140014c9d  mov     [rsi+10h], cx
0x140014ca1  movups  xmm0, xmmword ptr [rbx+0Ch]
0x140014ca5  movdqu  xmmword ptr [rsi+14h], xmm0
0x140014caa  movups  xmm1, xmmword ptr [rbx+1Ch]
0x140014cae  movdqu  xmmword ptr [rsi+24h], xmm1
0x140014cb3  mov     rcx, [rbx+30h]; bstr
0x140014cb7  test    rcx, rcx
0x140014cba  jnz     short loc_140014CC0
0x140014cbc  xor     eax, eax
0x140014cbe  jmp     short loc_140014CD2
0x140014cc0  call    cs:__imp_SysStringByteLen
0x140014cc6  mov     edx, eax; len
0x140014cc8  mov     rcx, [rbx+30h]; psz
0x140014ccc  call    cs:__imp_SysAllocStringByteLen
0x140014cd2  mov     [rsi+38h], rax
0x140014cd6  cmp     qword ptr [rbx+30h], 0
0x140014cdb  jz      short loc_140014CE6
0x140014cdd  test    rax, rax
0x140014ce0  jz      loc_140014F38
0x140014ce6  mov     eax, [rbx+38h]
0x140014ce9  mov     [rsi+40h], eax
0x140014cec  mov     al, [rbx+40h]
0x140014cef  mov     [rsi+48h], al
0x140014cf2  mov     [rsp+140h+hObject], rsi
0x140014cf7  mov     ecx, 18h; Size
0x140014cfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014d01  mov     rdi, rax
0x140014d04  mov     [rsp+140h+hObject], rax
0x140014d09  xorps   xmm0, xmm0
0x140014d0c  movups  xmmword ptr [rax], xmm0
0x140014d0f  mov     dword ptr [rax+8], 1
0x140014d16  mov     dword ptr [rax+0Ch], 1
0x140014d1d  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJKPEA_WU_GUID@@1F@ZAEBU?$_Ph@$00@2@AEAKVCComBSTR@ATL@@AEBU4@AEBU4@F@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(ulong,wchar_t *,_GUID,_GUID,short),std::_Ph<1> const &,ulong &,ATL::CComBSTR,_GUID const &,_GUID const &,short> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x140014d24  mov     [rdi], rax
0x140014d27  mov     [rdi+10h], rsi
0x140014d2b  mov     qword ptr [rsp+140h+var_108], rsi
0x140014d30  mov     qword ptr [rsp+140h+var_108+8], rdi
0x140014d35  movups  [rbp+40h+var_80], xmm0
0x140014d39  mov     [rbp+40h+var_70], 0
0x140014d41  mov     [rbp+40h+var_68], 7
0x140014d49  xor     eax, eax
0x140014d4b  mov     word ptr [rbp+40h+var_80], ax
0x140014d4f  mov     [rsp+140h+hObject], rax
0x140014d54  lea     rdx, [rsp+140h+hObject]
0x140014d59  lea     rcx, [rbp+40h+var_80]
0x140014d5d  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x140014d62  bt      rax, 27h ; '''
0x140014d67  jb      short loc_140014D8C
0x140014d69  mov     rcx, [rsp+140h+hObject]; hObject
0x140014d6e  test    rcx, rcx
0x140014d71  jz      short loc_140014D7A
0x140014d73  call    cs:__imp_CloseHandle
0x140014d79  nop
0x140014d7a  lea     rcx, [rbp+40h+var_80]
0x140014d7e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014d83  nop
0x140014d84  or      esi, 0FFFFFFFFh
0x140014d87  jmp     loc_140014EE9
0x140014d8c  mov     rbx, [rsp+140h+hObject]
0x140014d91  test    rbx, rbx
0x140014d94  jz      short loc_140014DA6
0x140014d96  mov     rcx, rbx; hObject
0x140014d99  call    cs:__imp_CloseHandle
0x140014d9f  xor     ebx, ebx
0x140014da1  mov     [rsp+140h+hObject], rbx
0x140014da6  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140014dad  mov     [rbp+40h+var_60], rax
0x140014db1  lea     r14, [r15+10h]
0x140014db5  mov     [rbp+40h+var_50], r14
0x140014db9  mov     rcx, r14; lpCriticalSection
0x140014dbc  call    cs:__imp_EnterCriticalSection
0x140014dc2  inc     dword ptr [r14+28h]
0x140014dc6  cmp     dword ptr [r14+28h], 1
0x140014dcb  jnz     short loc_140014DD7
0x140014dcd  call    cs:__imp_GetCurrentThreadId
0x140014dd3  mov     [r14+2Ch], eax
0x140014dd7  mov     [rbp+40h+var_58], 1
0x140014ddb  lea     rax, [rsp+140h+var_F0]
0x140014de0  mov     [rsp+140h+var_F8], rax
0x140014de5  xorps   xmm0, xmm0
0x140014de8  movdqu  [rsp+140h+var_F0], xmm0
0x140014dee  lock inc dword ptr [rdi+8]
0x140014df2  mov     qword ptr [rsp+140h+var_F0], rsi
0x140014df7  mov     qword ptr [rsp+140h+var_F0+8], rdi
0x140014dfc  lea     rdx, [rbp+40h+var_80]
0x140014e00  lea     rcx, [rsp+140h+var_E0]
0x140014e05  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140014e0a  mov     [rbp+40h+var_C0], 10000h
0x140014e11  mov     rdx, [r15+48h]
0x140014e15  lea     r9, [rsp+140h+var_F0]
0x140014e1a  mov     r8, rdx
0x140014e1d  mov     rdx, [rdx]
0x140014e20  lea     rcx, [rbp+40h+var_B8]
0x140014e24  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x140014e29  lea     rcx, [rbp+40h+var_A8]
0x140014e2d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014e32  mov     r15, [rbp+40h+var_B0]
0x140014e36  or      esi, 0FFFFFFFFh
0x140014e39  test    r15, r15
0x140014e3c  jz      short loc_140014E73
0x140014e3e  mov     eax, esi
0x140014e40  lock xadd [r15+8], eax
0x140014e46  add     eax, esi
0x140014e48  jnz     short loc_140014E73
0x140014e4a  mov     rax, [r15]
0x140014e4d  mov     rcx, r15
0x140014e50  mov     rax, [rax]
0x140014e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e58  mov     eax, esi
0x140014e5a  lock xadd [r15+0Ch], eax
0x140014e60  add     eax, esi
0x140014e62  jnz     short loc_140014E73
0x140014e64  mov     rax, [r15]
0x140014e67  mov     rcx, r15
0x140014e6a  mov     rax, [rax+8]
0x140014e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e73  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014e7a  jz      short loc_140014EB8
0x140014e7c  mov     dword ptr [rsp+140h+hObject], 10000h
0x140014e84  lea     rax, [rsp+140h+hObject]
0x140014e89  mov     [rbp+40h+var_50], rax
0x140014e8d  mov     [rbp+40h+var_48], 4
0x140014e95  lea     rax, [rbp+40h+var_60]
0x140014e99  mov     [rsp+140h+var_120], rax
0x140014e9e  mov     r9d, 2
0x140014ea4  lea     rdx, Service_QueueClientEventEnd
0x140014eab  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140014eb2  call    McGenEventWrite_EventWriteTransfer
0x140014eb7  nop
0x140014eb8  add     [r14+28h], esi
0x140014ebc  jnz     short loc_140014EC6
0x140014ebe  mov     dword ptr [r14+2Ch], 0
0x140014ec6  mov     rcx, r14; lpCriticalSection
0x140014ec9  call    cs:__imp_LeaveCriticalSection
0x140014ecf  nop
0x140014ed0  test    rbx, rbx
0x140014ed3  jz      short loc_140014EDF
0x140014ed5  mov     rcx, rbx; hObject
0x140014ed8  call    cs:__imp_CloseHandle
0x140014ede  nop
0x140014edf  lea     rcx, [rbp+40h+var_80]
0x140014ee3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014ee8  nop
0x140014ee9  mov     eax, esi
0x140014eeb  lock xadd [rdi+8], eax
0x140014ef0  add     eax, esi
0x140014ef2  jnz     short loc_140014F1C
0x140014ef4  mov     rax, [rdi]
0x140014ef7  mov     rcx, rdi
0x140014efa  mov     rax, [rax]
0x140014efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f02  mov     eax, esi
0x140014f04  lock xadd [rdi+0Ch], eax
0x140014f09  add     eax, esi
0x140014f0b  jnz     short loc_140014F1C
0x140014f0d  mov     rax, [rdi]
0x140014f10  mov     rcx, rdi
0x140014f13  mov     rax, [rax+8]
0x140014f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f1c  mov     rcx, [rbp+40h+var_40]
0x140014f20  xor     rcx, rsp; StackCookie
0x140014f23  call    __security_check_cookie
0x140014f28  add     rsp, 118h
0x140014f2f  pop     r15
0x140014f31  pop     r14
0x140014f33  pop     rdi
0x140014f34  pop     rsi
0x140014f35  pop     rbx
0x140014f36  pop     rbp
0x140014f37  retn
0x140014f38  mov     ecx, 8007000Eh; int
0x140014f3d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
