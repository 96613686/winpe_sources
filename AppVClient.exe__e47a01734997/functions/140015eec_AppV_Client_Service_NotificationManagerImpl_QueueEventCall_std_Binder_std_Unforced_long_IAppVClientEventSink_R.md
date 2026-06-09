# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &> const &)

- ea: `0x140015eec`
- end: `0x140016245`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017c10`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x14000a2e8`
- `0x1400147fc`
- `0x140015eec`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140016075`
- `KERNEL32!CloseHandle` at `0x14001609b`
- `KERNEL32!CloseHandle` at `0x1400161da`
- `KERNEL32!CloseHandle` at `0x140016075`
- `KERNEL32!CloseHandle` at `0x14001609b`
- `KERNEL32!CloseHandle` at `0x1400161da`
- `KERNEL32!GetCurrentThreadId` at `0x1400160cf`
- `KERNEL32!GetCurrentThreadId` at `0x1400160cf`
- `KERNEL32!LeaveCriticalSection` at `0x1400161cb`
- `KERNEL32!LeaveCriticalSection` at `0x1400161cb`
- `KERNEL32!EnterCriticalSection` at `0x1400160be`
- `KERNEL32!EnterCriticalSection` at `0x1400160be`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140015fc2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140015fc2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140015fce`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140015fce`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(enum RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,enum RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &>>(
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
    LODWORD(hObject) = 0x40000;
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
  v5 = operator new(0x48u);
  hObject = v5;
  *v5 = &`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(enum RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,enum RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &>>'::`2'::EventCallImpl::`vftable';
  v5[1] = *(_QWORD *)a3;
  v5[2] = *(_QWORD *)(a3 + 8);
  *((_DWORD *)v5 + 6) = *(_DWORD *)(a3 + 16);
  *(_QWORD *)((char *)v5 + 28) = *(_QWORD *)(a3 + 20);
  *((_DWORD *)v5 + 9) = *(_DWORD *)(a3 + 28);
  *((_WORD *)v5 + 20) = *(_WORD *)(a3 + 32);
  *((_WORD *)v5 + 22) = *(_WORD *)(a3 + 36);
  v6 = *(OLECHAR **)(a3 + 40);
  if ( v6 )
  {
    v8 = SysStringByteLen(v6);
    v7 = SysAllocStringByteLen(*(LPCSTR *)(a3 + 40), v8);
  }
  else
  {
    v7 = 0;
  }
  v5[6] = v7;
  if ( *(_QWORD *)(a3 + 40) && !v7 )
    ATL::AtlThrowImpl(-2147024882);
  *((_DWORD *)v5 + 14) = *(_DWORD *)(a3 + 48);
  *((_BYTE *)v5 + 64) = *(_BYTE *)(a3 + 56);
  hObject = v5;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJW4RefreshStatusType__PEA_WFFUPublishCounter__2_ZAEBU___Ph__00_2_AEAW44_VCComBSTR_ATL__FFAEAU5_AEAU5__std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJW4RefreshStatusType__PEA_WFFUPublishCounter__2_ZAEBU___Ph__00_2_AEAW44_VCComBSTR_ATL__FFAEAU5_AEAU5__std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
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
    v21 = 0x40000;
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
      LODWORD(hObject) = 0x40000;
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
0x140015eec  push    rbp
0x140015eee  push    rbx
0x140015eef  push    rsi
0x140015ef0  push    rdi
0x140015ef1  push    r14
0x140015ef3  push    r15
0x140015ef5  lea     rbp, [rsp-18h]
0x140015efa  sub     rsp, 118h
0x140015f01  mov     rax, cs:__security_cookie
0x140015f08  xor     rax, rsp
0x140015f0b  mov     [rbp+40h+var_40], rax
0x140015f0f  mov     rbx, r8
0x140015f12  mov     r15, rcx
0x140015f15  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015f1c  jz      short loc_140015F59
0x140015f1e  mov     dword ptr [rsp+140h+hObject], 40000h
0x140015f26  lea     rax, [rsp+140h+hObject]
0x140015f2b  mov     [rbp+40h+var_70], rax
0x140015f2f  mov     [rbp+40h+var_68], 4
0x140015f37  lea     rax, [rbp+40h+var_80]
0x140015f3b  mov     [rsp+140h+var_120], rax
0x140015f40  mov     r9d, 2
0x140015f46  lea     rdx, Service_QueueClientEventBegin
0x140015f4d  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015f54  call    McGenEventWrite_EventWriteTransfer
0x140015f59  xorps   xmm0, xmm0
0x140015f5c  movdqu  [rsp+140h+var_108], xmm0
0x140015f62  mov     ecx, 48h ; 'H'; Size
0x140015f67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015f6c  mov     rsi, rax
0x140015f6f  mov     [rsp+140h+hObject], rax
0x140015f74  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x140015f7b  mov     [rsi], rax
0x140015f7e  mov     rcx, [rbx]
0x140015f81  mov     [rsi+8], rcx
0x140015f85  movsd   xmm0, qword ptr [rbx+8]
0x140015f8a  movsd   qword ptr [rsi+10h], xmm0
0x140015f8f  mov     eax, [rbx+10h]
0x140015f92  mov     [rsi+18h], eax
0x140015f95  movsd   xmm0, qword ptr [rbx+14h]
0x140015f9a  movsd   qword ptr [rsi+1Ch], xmm0
0x140015f9f  mov     eax, [rbx+1Ch]
0x140015fa2  mov     [rsi+24h], eax
0x140015fa5  movzx   eax, word ptr [rbx+20h]
0x140015fa9  mov     [rsi+28h], ax
0x140015fad  movzx   eax, word ptr [rbx+24h]
0x140015fb1  mov     [rsi+2Ch], ax
0x140015fb5  mov     rcx, [rbx+28h]; bstr
0x140015fb9  test    rcx, rcx
0x140015fbc  jnz     short loc_140015FC2
0x140015fbe  xor     eax, eax
0x140015fc0  jmp     short loc_140015FD4
0x140015fc2  call    cs:__imp_SysStringByteLen
0x140015fc8  mov     edx, eax; len
0x140015fca  mov     rcx, [rbx+28h]; psz
0x140015fce  call    cs:__imp_SysAllocStringByteLen
0x140015fd4  mov     [rsi+30h], rax
0x140015fd8  cmp     qword ptr [rbx+28h], 0
0x140015fdd  jz      short loc_140015FE8
0x140015fdf  test    rax, rax
0x140015fe2  jz      loc_14001623A
0x140015fe8  mov     eax, [rbx+30h]
0x140015feb  mov     [rsi+38h], eax
0x140015fee  mov     al, [rbx+38h]
0x140015ff1  mov     [rsi+40h], al
0x140015ff4  mov     [rsp+140h+hObject], rsi
0x140015ff9  mov     ecx, 18h; Size
0x140015ffe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016003  mov     rdi, rax
0x140016006  mov     [rsp+140h+hObject], rax
0x14001600b  xorps   xmm0, xmm0
0x14001600e  movups  xmmword ptr [rax], xmm0
0x140016011  mov     dword ptr [rax+8], 1
0x140016018  mov     dword ptr [rax+0Ch], 1
0x14001601f  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJW4RefreshStatusType@@PEA_WFFUPublishCounter@@2@ZAEBU?$_Ph@$00@2@AEAW44@VCComBSTR@ATL@@FFAEAU5@AEAU5@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(RefreshStatusType,wchar_t *,short,short,PublishCounter,PublishCounter),std::_Ph<1> const &,RefreshStatusType &,ATL::CComBSTR,short,short,PublishCounter &,PublishCounter &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x140016026  mov     [rdi], rax
0x140016029  mov     [rdi+10h], rsi
0x14001602d  mov     qword ptr [rsp+140h+var_108], rsi
0x140016032  mov     qword ptr [rsp+140h+var_108+8], rdi
0x140016037  movups  [rbp+40h+var_80], xmm0
0x14001603b  mov     [rbp+40h+var_70], 0
0x140016043  mov     [rbp+40h+var_68], 7
0x14001604b  xor     eax, eax
0x14001604d  mov     word ptr [rbp+40h+var_80], ax
0x140016051  mov     [rsp+140h+hObject], rax
0x140016056  lea     rdx, [rsp+140h+hObject]
0x14001605b  lea     rcx, [rbp+40h+var_80]
0x14001605f  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x140016064  bt      rax, 27h ; '''
0x140016069  jb      short loc_14001608E
0x14001606b  mov     rcx, [rsp+140h+hObject]; hObject
0x140016070  test    rcx, rcx
0x140016073  jz      short loc_14001607C
0x140016075  call    cs:__imp_CloseHandle
0x14001607b  nop
0x14001607c  lea     rcx, [rbp+40h+var_80]
0x140016080  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016085  nop
0x140016086  or      esi, 0FFFFFFFFh
0x140016089  jmp     loc_1400161EB
0x14001608e  mov     rbx, [rsp+140h+hObject]
0x140016093  test    rbx, rbx
0x140016096  jz      short loc_1400160A8
0x140016098  mov     rcx, rbx; hObject
0x14001609b  call    cs:__imp_CloseHandle
0x1400160a1  xor     ebx, ebx
0x1400160a3  mov     [rsp+140h+hObject], rbx
0x1400160a8  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400160af  mov     [rbp+40h+var_60], rax
0x1400160b3  lea     r14, [r15+10h]
0x1400160b7  mov     [rbp+40h+var_50], r14
0x1400160bb  mov     rcx, r14; lpCriticalSection
0x1400160be  call    cs:__imp_EnterCriticalSection
0x1400160c4  inc     dword ptr [r14+28h]
0x1400160c8  cmp     dword ptr [r14+28h], 1
0x1400160cd  jnz     short loc_1400160D9
0x1400160cf  call    cs:__imp_GetCurrentThreadId
0x1400160d5  mov     [r14+2Ch], eax
0x1400160d9  mov     [rbp+40h+var_58], 1
0x1400160dd  lea     rax, [rsp+140h+var_F0]
0x1400160e2  mov     [rsp+140h+var_F8], rax
0x1400160e7  xorps   xmm0, xmm0
0x1400160ea  movdqu  [rsp+140h+var_F0], xmm0
0x1400160f0  lock inc dword ptr [rdi+8]
0x1400160f4  mov     qword ptr [rsp+140h+var_F0], rsi
0x1400160f9  mov     qword ptr [rsp+140h+var_F0+8], rdi
0x1400160fe  lea     rdx, [rbp+40h+var_80]
0x140016102  lea     rcx, [rsp+140h+var_E0]
0x140016107  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001610c  mov     [rbp+40h+var_C0], 40000h
0x140016113  mov     rdx, [r15+48h]
0x140016117  lea     r9, [rsp+140h+var_F0]
0x14001611c  mov     r8, rdx
0x14001611f  mov     rdx, [rdx]
0x140016122  lea     rcx, [rbp+40h+var_B8]
0x140016126  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x14001612b  lea     rcx, [rbp+40h+var_A8]
0x14001612f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016134  mov     r15, [rbp+40h+var_B0]
0x140016138  or      esi, 0FFFFFFFFh
0x14001613b  test    r15, r15
0x14001613e  jz      short loc_140016175
0x140016140  mov     eax, esi
0x140016142  lock xadd [r15+8], eax
0x140016148  add     eax, esi
0x14001614a  jnz     short loc_140016175
0x14001614c  mov     rax, [r15]
0x14001614f  mov     rcx, r15
0x140016152  mov     rax, [rax]
0x140016155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001615a  mov     eax, esi
0x14001615c  lock xadd [r15+0Ch], eax
0x140016162  add     eax, esi
0x140016164  jnz     short loc_140016175
0x140016166  mov     rax, [r15]
0x140016169  mov     rcx, r15
0x14001616c  mov     rax, [rax+8]
0x140016170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016175  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14001617c  jz      short loc_1400161BA
0x14001617e  mov     dword ptr [rsp+140h+hObject], 40000h
0x140016186  lea     rax, [rsp+140h+hObject]
0x14001618b  mov     [rbp+40h+var_50], rax
0x14001618f  mov     [rbp+40h+var_48], 4
0x140016197  lea     rax, [rbp+40h+var_60]
0x14001619b  mov     [rsp+140h+var_120], rax
0x1400161a0  mov     r9d, 2
0x1400161a6  lea     rdx, Service_QueueClientEventEnd
0x1400161ad  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400161b4  call    McGenEventWrite_EventWriteTransfer
0x1400161b9  nop
0x1400161ba  add     [r14+28h], esi
0x1400161be  jnz     short loc_1400161C8
0x1400161c0  mov     dword ptr [r14+2Ch], 0
0x1400161c8  mov     rcx, r14; lpCriticalSection
0x1400161cb  call    cs:__imp_LeaveCriticalSection
0x1400161d1  nop
0x1400161d2  test    rbx, rbx
0x1400161d5  jz      short loc_1400161E1
0x1400161d7  mov     rcx, rbx; hObject
0x1400161da  call    cs:__imp_CloseHandle
0x1400161e0  nop
0x1400161e1  lea     rcx, [rbp+40h+var_80]
0x1400161e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400161ea  nop
0x1400161eb  mov     eax, esi
0x1400161ed  lock xadd [rdi+8], eax
0x1400161f2  add     eax, esi
0x1400161f4  jnz     short loc_14001621E
0x1400161f6  mov     rax, [rdi]
0x1400161f9  mov     rcx, rdi
0x1400161fc  mov     rax, [rax]
0x1400161ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016204  mov     eax, esi
0x140016206  lock xadd [rdi+0Ch], eax
0x14001620b  add     eax, esi
0x14001620d  jnz     short loc_14001621E
0x14001620f  mov     rax, [rdi]
0x140016212  mov     rcx, rdi
0x140016215  mov     rax, [rax+8]
0x140016219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001621e  mov     rcx, [rbp+40h+var_40]
0x140016222  xor     rcx, rsp; StackCookie
0x140016225  call    __security_check_cookie
0x14001622a  add     rsp, 118h
0x140016231  pop     r15
0x140016233  pop     r14
0x140016235  pop     rdi
0x140016236  pop     rsi
0x140016237  pop     rbx
0x140016238  pop     rbp
0x140016239  retn
0x14001623a  mov     ecx, 8007000Eh; int
0x14001623f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
