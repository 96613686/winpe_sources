# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR> const &)

- ea: `0x140015ba0`
- end: `0x140015ee3`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017b00`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x14000a2e8`
- `0x1400147fc`
- `0x140015ba0`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140015d13`
- `KERNEL32!CloseHandle` at `0x140015d39`
- `KERNEL32!CloseHandle` at `0x140015e78`
- `KERNEL32!CloseHandle` at `0x140015d13`
- `KERNEL32!CloseHandle` at `0x140015d39`
- `KERNEL32!CloseHandle` at `0x140015e78`
- `KERNEL32!GetCurrentThreadId` at `0x140015d6d`
- `KERNEL32!GetCurrentThreadId` at `0x140015d6d`
- `KERNEL32!LeaveCriticalSection` at `0x140015e69`
- `KERNEL32!LeaveCriticalSection` at `0x140015e69`
- `KERNEL32!EnterCriticalSection` at `0x140015d5c`
- `KERNEL32!EnterCriticalSection` at `0x140015d5c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140015c46`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140015c46`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140015c52`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140015c52`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(enum PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,enum PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR>>(
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
    LODWORD(hObject) = 0x80000;
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
  *v5 = &`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(enum PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,enum PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR>>'::`2'::EventCallImpl::`vftable';
  v5[1] = *(_QWORD *)a3;
  v6 = *(OLECHAR **)(a3 + 8);
  if ( v6 )
  {
    v8 = SysStringByteLen(v6);
    v7 = SysAllocStringByteLen(*(LPCSTR *)(a3 + 8), v8);
  }
  else
  {
    v7 = 0;
  }
  v5[2] = v7;
  if ( *(_QWORD *)(a3 + 8) && !v7 )
    ATL::AtlThrowImpl(-2147024882);
  *((_WORD *)v5 + 12) = *(_WORD *)(a3 + 16);
  *((_OWORD *)v5 + 2) = *(_OWORD *)(a3 + 24);
  *((_OWORD *)v5 + 3) = *(_OWORD *)(a3 + 40);
  *((_DWORD *)v5 + 16) = *(_DWORD *)(a3 + 56);
  *((_BYTE *)v5 + 72) = *(_BYTE *)(a3 + 64);
  hObject = v5;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJW4PublishingStatusType__U_GUID__1FPEA_W_ZAEBU___Ph__00_2_AEAW44_AEBU5_AEBU5_FVCComBSTR_ATL___std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJW4PublishingStatusType__U_GUID__1FPEA_W_ZAEBU___Ph__00_2_AEAW44_AEBU5_AEBU5_FVCComBSTR_ATL___std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
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
    v21 = 0x80000;
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
      LODWORD(hObject) = 0x80000;
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
0x140015ba0  push    rbp
0x140015ba2  push    rbx
0x140015ba3  push    rsi
0x140015ba4  push    rdi
0x140015ba5  push    r14
0x140015ba7  push    r15
0x140015ba9  lea     rbp, [rsp-18h]
0x140015bae  sub     rsp, 118h
0x140015bb5  mov     rax, cs:__security_cookie
0x140015bbc  xor     rax, rsp
0x140015bbf  mov     [rbp+40h+var_40], rax
0x140015bc3  mov     rbx, r8
0x140015bc6  mov     r15, rcx
0x140015bc9  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015bd0  jz      short loc_140015C0D
0x140015bd2  mov     dword ptr [rsp+140h+hObject], 80000h
0x140015bda  lea     rax, [rsp+140h+hObject]
0x140015bdf  mov     [rbp+40h+var_70], rax
0x140015be3  mov     [rbp+40h+var_68], 4
0x140015beb  lea     rax, [rbp+40h+var_80]
0x140015bef  mov     [rsp+140h+var_120], rax
0x140015bf4  mov     r9d, 2
0x140015bfa  lea     rdx, Service_QueueClientEventBegin
0x140015c01  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015c08  call    McGenEventWrite_EventWriteTransfer
0x140015c0d  xorps   xmm0, xmm0
0x140015c10  movdqu  [rsp+140h+var_108], xmm0
0x140015c16  mov     ecx, 50h ; 'P'; Size
0x140015c1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015c20  mov     rsi, rax
0x140015c23  mov     [rsp+140h+hObject], rax
0x140015c28  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x140015c2f  mov     [rsi], rax
0x140015c32  mov     rcx, [rbx]
0x140015c35  mov     [rsi+8], rcx
0x140015c39  mov     rcx, [rbx+8]; bstr
0x140015c3d  test    rcx, rcx
0x140015c40  jnz     short loc_140015C46
0x140015c42  xor     eax, eax
0x140015c44  jmp     short loc_140015C58
0x140015c46  call    cs:__imp_SysStringByteLen
0x140015c4c  mov     edx, eax; len
0x140015c4e  mov     rcx, [rbx+8]; psz
0x140015c52  call    cs:__imp_SysAllocStringByteLen
0x140015c58  mov     [rsi+10h], rax
0x140015c5c  cmp     qword ptr [rbx+8], 0
0x140015c61  jz      short loc_140015C6C
0x140015c63  test    rax, rax
0x140015c66  jz      loc_140015ED8
0x140015c6c  movzx   eax, word ptr [rbx+10h]
0x140015c70  mov     [rsi+18h], ax
0x140015c74  movups  xmm0, xmmword ptr [rbx+18h]
0x140015c78  movdqu  xmmword ptr [rsi+20h], xmm0
0x140015c7d  movups  xmm1, xmmword ptr [rbx+28h]
0x140015c81  movdqu  xmmword ptr [rsi+30h], xmm1
0x140015c86  mov     eax, [rbx+38h]
0x140015c89  mov     [rsi+40h], eax
0x140015c8c  mov     al, [rbx+40h]
0x140015c8f  mov     [rsi+48h], al
0x140015c92  mov     [rsp+140h+hObject], rsi
0x140015c97  mov     ecx, 18h; Size
0x140015c9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015ca1  mov     rdi, rax
0x140015ca4  mov     [rsp+140h+hObject], rax
0x140015ca9  xorps   xmm0, xmm0
0x140015cac  movups  xmmword ptr [rax], xmm0
0x140015caf  mov     dword ptr [rax+8], 1
0x140015cb6  mov     dword ptr [rax+0Ch], 1
0x140015cbd  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4PublishingStatusType@@U_GUID@@1FPEA_W@ZAEBU?$_Ph@$00@2@AEAW44@AEBU5@AEBU5@FVCComBSTR@ATL@@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(PublishingStatusType,_GUID,_GUID,short,wchar_t *),std::_Ph<1> const &,PublishingStatusType &,_GUID const &,_GUID const &,short,ATL::CComBSTR> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x140015cc4  mov     [rdi], rax
0x140015cc7  mov     [rdi+10h], rsi
0x140015ccb  mov     qword ptr [rsp+140h+var_108], rsi
0x140015cd0  mov     qword ptr [rsp+140h+var_108+8], rdi
0x140015cd5  movups  [rbp+40h+var_80], xmm0
0x140015cd9  mov     [rbp+40h+var_70], 0
0x140015ce1  mov     [rbp+40h+var_68], 7
0x140015ce9  xor     eax, eax
0x140015ceb  mov     word ptr [rbp+40h+var_80], ax
0x140015cef  mov     [rsp+140h+hObject], rax
0x140015cf4  lea     rdx, [rsp+140h+hObject]
0x140015cf9  lea     rcx, [rbp+40h+var_80]
0x140015cfd  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x140015d02  bt      rax, 27h ; '''
0x140015d07  jb      short loc_140015D2C
0x140015d09  mov     rcx, [rsp+140h+hObject]; hObject
0x140015d0e  test    rcx, rcx
0x140015d11  jz      short loc_140015D1A
0x140015d13  call    cs:__imp_CloseHandle
0x140015d19  nop
0x140015d1a  lea     rcx, [rbp+40h+var_80]
0x140015d1e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015d23  nop
0x140015d24  or      esi, 0FFFFFFFFh
0x140015d27  jmp     loc_140015E89
0x140015d2c  mov     rbx, [rsp+140h+hObject]
0x140015d31  test    rbx, rbx
0x140015d34  jz      short loc_140015D46
0x140015d36  mov     rcx, rbx; hObject
0x140015d39  call    cs:__imp_CloseHandle
0x140015d3f  xor     ebx, ebx
0x140015d41  mov     [rsp+140h+hObject], rbx
0x140015d46  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140015d4d  mov     [rbp+40h+var_60], rax
0x140015d51  lea     r14, [r15+10h]
0x140015d55  mov     [rbp+40h+var_50], r14
0x140015d59  mov     rcx, r14; lpCriticalSection
0x140015d5c  call    cs:__imp_EnterCriticalSection
0x140015d62  inc     dword ptr [r14+28h]
0x140015d66  cmp     dword ptr [r14+28h], 1
0x140015d6b  jnz     short loc_140015D77
0x140015d6d  call    cs:__imp_GetCurrentThreadId
0x140015d73  mov     [r14+2Ch], eax
0x140015d77  mov     [rbp+40h+var_58], 1
0x140015d7b  lea     rax, [rsp+140h+var_F0]
0x140015d80  mov     [rsp+140h+var_F8], rax
0x140015d85  xorps   xmm0, xmm0
0x140015d88  movdqu  [rsp+140h+var_F0], xmm0
0x140015d8e  lock inc dword ptr [rdi+8]
0x140015d92  mov     qword ptr [rsp+140h+var_F0], rsi
0x140015d97  mov     qword ptr [rsp+140h+var_F0+8], rdi
0x140015d9c  lea     rdx, [rbp+40h+var_80]
0x140015da0  lea     rcx, [rsp+140h+var_E0]
0x140015da5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140015daa  mov     [rbp+40h+var_C0], 80000h
0x140015db1  mov     rdx, [r15+48h]
0x140015db5  lea     r9, [rsp+140h+var_F0]
0x140015dba  mov     r8, rdx
0x140015dbd  mov     rdx, [rdx]
0x140015dc0  lea     rcx, [rbp+40h+var_B8]
0x140015dc4  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x140015dc9  lea     rcx, [rbp+40h+var_A8]
0x140015dcd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015dd2  mov     r15, [rbp+40h+var_B0]
0x140015dd6  or      esi, 0FFFFFFFFh
0x140015dd9  test    r15, r15
0x140015ddc  jz      short loc_140015E13
0x140015dde  mov     eax, esi
0x140015de0  lock xadd [r15+8], eax
0x140015de6  add     eax, esi
0x140015de8  jnz     short loc_140015E13
0x140015dea  mov     rax, [r15]
0x140015ded  mov     rcx, r15
0x140015df0  mov     rax, [rax]
0x140015df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015df8  mov     eax, esi
0x140015dfa  lock xadd [r15+0Ch], eax
0x140015e00  add     eax, esi
0x140015e02  jnz     short loc_140015E13
0x140015e04  mov     rax, [r15]
0x140015e07  mov     rcx, r15
0x140015e0a  mov     rax, [rax+8]
0x140015e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015e13  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015e1a  jz      short loc_140015E58
0x140015e1c  mov     dword ptr [rsp+140h+hObject], 80000h
0x140015e24  lea     rax, [rsp+140h+hObject]
0x140015e29  mov     [rbp+40h+var_50], rax
0x140015e2d  mov     [rbp+40h+var_48], 4
0x140015e35  lea     rax, [rbp+40h+var_60]
0x140015e39  mov     [rsp+140h+var_120], rax
0x140015e3e  mov     r9d, 2
0x140015e44  lea     rdx, Service_QueueClientEventEnd
0x140015e4b  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015e52  call    McGenEventWrite_EventWriteTransfer
0x140015e57  nop
0x140015e58  add     [r14+28h], esi
0x140015e5c  jnz     short loc_140015E66
0x140015e5e  mov     dword ptr [r14+2Ch], 0
0x140015e66  mov     rcx, r14; lpCriticalSection
0x140015e69  call    cs:__imp_LeaveCriticalSection
0x140015e6f  nop
0x140015e70  test    rbx, rbx
0x140015e73  jz      short loc_140015E7F
0x140015e75  mov     rcx, rbx; hObject
0x140015e78  call    cs:__imp_CloseHandle
0x140015e7e  nop
0x140015e7f  lea     rcx, [rbp+40h+var_80]
0x140015e83  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015e88  nop
0x140015e89  mov     eax, esi
0x140015e8b  lock xadd [rdi+8], eax
0x140015e90  add     eax, esi
0x140015e92  jnz     short loc_140015EBC
0x140015e94  mov     rax, [rdi]
0x140015e97  mov     rcx, rdi
0x140015e9a  mov     rax, [rax]
0x140015e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ea2  mov     eax, esi
0x140015ea4  lock xadd [rdi+0Ch], eax
0x140015ea9  add     eax, esi
0x140015eab  jnz     short loc_140015EBC
0x140015ead  mov     rax, [rdi]
0x140015eb0  mov     rcx, rdi
0x140015eb3  mov     rax, [rax+8]
0x140015eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ebc  mov     rcx, [rbp+40h+var_40]
0x140015ec0  xor     rcx, rsp; StackCookie
0x140015ec3  call    __security_check_cookie
0x140015ec8  add     rsp, 118h
0x140015ecf  pop     r15
0x140015ed1  pop     r14
0x140015ed3  pop     rdi
0x140015ed4  pop     rsi
0x140015ed5  pop     rbx
0x140015ed6  pop     rbp
0x140015ed7  retn
0x140015ed8  mov     ecx, 8007000Eh; int
0x140015edd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
