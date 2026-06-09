# Windows::Networking::UX::Internal::WlanInterface::SetRadioState(uchar)

- ea: `0x1800454f8`
- end: `0x180045857`
- name: `?SetRadioState@WlanInterface@Internal@UX@Networking@Windows@@QEAAJE@Z`
- size: `863`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026d50`

## callees

- `0x180003ed0`
- `0x1800121e8`
- `0x1800141a0`
- `0x180016a1c`
- `0x18001d4d4`
- `0x180037530`
- `0x1800375a8`
- `0x18003a4ac`
- `0x18003f7bc`
- `0x1800454f8`
- `0x18004beb8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800455cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800455cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004564e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004564e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::SetRadioState(
        Windows::Networking::UX::Internal::WlanInterface *this,
        unsigned __int8 a2)
{
  unsigned int v2; // esi
  int v4; // ecx
  BOOL v5; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  Windows::Networking::UX::Internal::WlanInterface *v8; // rcx
  HRESULT v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  Windows::Networking::UX::Internal::WlanInterface *v12; // rcx
  unsigned int PowerBackOnOption; // eax
  int v14; // eax
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v18; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[336]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[336]; // [rsp+1B0h] [rbp+B0h] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, a2);
  NetworkUxTelemetry::SetRadioState::Start<_GUID &>(
    (NetworkUxTelemetry::SetRadioState *)v20,
    (struct _GUID *)((char *)this + 1204));
  wil::EnterCriticalSection(&ppv, (char *)this + 1304);
  v4 = ((_BYTE)v2 != 0) + 3;
  *((_DWORD *)this + 322) = v4;
  if ( *((_BYTE *)this + 1186) )
    *((_DWORD *)this + 323) = v4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&ppv);
  if ( (_BYTE)v2 )
    GetSystemTimeAsFileTime((LPFILETIME)this + 171);
  else
    Windows::Networking::UX::Internal::WlanInterface::_SaveNetworkListStateBeforePowerOff(this);
  v5 = (_BYTE)v2 != 0;
  v6 = Windows::Networking::UX::Internal::WlanClient::SetOperationalState(
         *((Windows::Networking::UX::Internal::WlanClient **)this + 3),
         (const struct _GUID *)((char *)this + 1204),
         (enum _WLAN_OPERATIONAL_STATE)(v5 + 1));
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (Windows::Networking::UX::Internal::WlanInterface *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
        (unsigned int)v6);
    goto LABEL_24;
  }
  ppv = 0;
  v9 = CoCreateInstance(
         &GUID_581333f6_28db_41be_bc7a_ff201f12f3f6,
         0,
         4u,
         &GUID_e1ca5ff8_f674_4a99_831e_727e1e31504b,
         &ppv);
  if ( v9 >= 0 )
  {
    v18 = CLSID_WLANRM;
    v9 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, &v18, v2);
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 58;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 57;
LABEL_21:
      WPP_SF_d(v10[2], v11, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, (unsigned int)v9);
    }
  }
  v8 = (Windows::Networking::UX::Internal::WlanInterface *)ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(Windows::Networking::UX::Internal::WlanInterface *))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_24:
  v17[0] = 0;
  LODWORD(ppv) = 0;
  if ( (int)Windows::Networking::UX::Internal::WlanInterface::GetPowerBackOnOption(
              v8,
              (enum Windows::Networking::UX::WiFiPowerBackOnOption *)&ppv,
              v17) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    PowerBackOnOption = Windows::Networking::UX::Internal::WlanInterface::GetPowerBackOnOption(
                          v12,
                          (enum Windows::Networking::UX::WiFiPowerBackOnOption *)&ppv,
                          v17);
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      PowerBackOnOption);
  }
  NetworkUxTelemetry::SetRadioState::StopWithResult<bool,enum Windows::Networking::UX::WiFiPowerBackOnOption &,unsigned int &>(
    (NetworkUxTelemetry::SetRadioState *)v20,
    v7);
  if ( *((_BYTE *)this + 1186) )
  {
    NetworkUxTelemetry::SetRadioState::Start<_GUID &>(
      (NetworkUxTelemetry::SetRadioState *)v19,
      (struct _GUID *)((char *)this + 1188));
    v14 = Windows::Networking::UX::Internal::WlanClient::SetOperationalState(
            *((Windows::Networking::UX::Internal::WlanClient **)this + 3),
            (const struct _GUID *)((char *)this + 1188),
            (enum _WLAN_OPERATIONAL_STATE)(v5 + 1));
    v7 = v14;
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
        (unsigned int)v14);
    NetworkUxTelemetry::SetRadioState::StopWithResult<bool,enum Windows::Networking::UX::WiFiPowerBackOnOption &,unsigned int &>(
      (NetworkUxTelemetry::SetRadioState *)v19,
      v7);
    NetworkUxTelemetry::SetRadioState::~SetRadioState((NetworkUxTelemetry::SetRadioState *)v19);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v7);
  NetworkUxTelemetry::SetRadioState::~SetRadioState((NetworkUxTelemetry::SetRadioState *)v20);
  return v7;
}

```

## disassembly

```asm
0x1800454f8  mov     [rsp-8+arg_10], rbx
0x1800454fd  mov     [rsp-8+arg_18], rsi
0x180045502  push    rbp
0x180045503  push    rdi
0x180045504  push    r12
0x180045506  push    r13
0x180045508  push    r14
0x18004550a  lea     rbp, [rsp-210h]
0x180045512  sub     rsp, 310h
0x180045519  mov     rax, cs:__security_cookie
0x180045520  xor     rax, rsp
0x180045523  mov     [rbp+230h+var_30], rax
0x18004552a  movzx   esi, dl
0x18004552d  mov     rdi, rcx
0x180045530  lea     r12, WPP_GLOBAL_Control
0x180045537  lea     r13, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004553e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045545  cmp     rcx, r12
0x180045548  jz      short loc_180045564
0x18004554a  test    byte ptr [rcx+1Ch], 8
0x18004554e  jz      short loc_180045564
0x180045550  mov     r9d, esi
0x180045553  mov     edx, 37h ; '7'
0x180045558  mov     r8, r13
0x18004555b  mov     rcx, [rcx+10h]
0x18004555f  call    WPP_SF_d
0x180045564  lea     rbx, [rdi+4B4h]
0x18004556b  mov     rdx, rbx; struct _GUID *
0x18004556e  lea     rcx, [rbp+230h+var_180]; this
0x180045575  call    ??$Start@AEAU_GUID@@@SetRadioState@NetworkUxTelemetry@@SA?AV01@AEAU_GUID@@@Z; NetworkUxTelemetry::SetRadioState::Start<_GUID &>(_GUID &)
0x18004557a  nop
0x18004557b  lea     rdx, [rdi+518h]
0x180045582  lea     rcx, [rsp+330h+var_2F8]
0x180045587  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004558c  mov     al, sil
0x18004558f  neg     al
0x180045591  sbb     ecx, ecx
0x180045593  neg     ecx
0x180045595  add     ecx, 3
0x180045598  mov     [rdi+508h], ecx
0x18004559e  cmp     byte ptr [rdi+4A2h], 0
0x1800455a5  jz      short loc_1800455AD
0x1800455a7  mov     [rdi+50Ch], ecx
0x1800455ad  lea     rcx, [rsp+330h+var_2F8]
0x1800455b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800455b7  test    sil, sil
0x1800455ba  jnz     short loc_1800455C6
0x1800455bc  mov     rcx, rdi; this
0x1800455bf  call    ?_SaveNetworkListStateBeforePowerOff@WlanInterface@Internal@UX@Networking@Windows@@IEAAXXZ; Windows::Networking::UX::Internal::WlanInterface::_SaveNetworkListStateBeforePowerOff(void)
0x1800455c4  jmp     short loc_1800455D3
0x1800455c6  lea     rcx, [rdi+558h]; lpSystemTimeAsFileTime
0x1800455cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800455d3  mov     al, sil
0x1800455d6  neg     al
0x1800455d8  sbb     r14d, r14d
0x1800455db  neg     r14d
0x1800455de  lea     r8d, [r14+1]; enum _WLAN_OPERATIONAL_STATE
0x1800455e2  mov     rdx, rbx; struct _GUID *
0x1800455e5  mov     rcx, [rdi+18h]; this
0x1800455e9  call    ?SetOperationalState@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@W4_WLAN_OPERATIONAL_STATE@@@Z; Windows::Networking::UX::Internal::WlanClient::SetOperationalState(_GUID const &,_WLAN_OPERATIONAL_STATE)
0x1800455ee  mov     ebx, eax
0x1800455f0  test    eax, eax
0x1800455f2  jns     short loc_180045627
0x1800455f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800455fb  cmp     rcx, r12
0x1800455fe  jz      loc_1800456E2
0x180045604  test    byte ptr [rcx+1Ch], 2
0x180045608  jz      loc_1800456E2
0x18004560e  mov     edx, 38h ; '8'
0x180045613  mov     r9d, eax
0x180045616  mov     r8, r13
0x180045619  mov     rcx, [rcx+10h]
0x18004561d  call    WPP_SF_d
0x180045622  jmp     loc_1800456E2
0x180045627  mov     [rsp+330h+var_2F8], 0
0x180045630  lea     rax, [rsp+330h+var_2F8]
0x180045635  mov     [rsp+330h+ppv], rax; ppv
0x18004563a  lea     r9, _GUID_e1ca5ff8_f674_4a99_831e_727e1e31504b; riid
0x180045641  xor     edx, edx; pUnkOuter
0x180045643  lea     r8d, [rdx+4]; dwClsContext
0x180045647  lea     rcx, _GUID_581333f6_28db_41be_bc7a_ff201f12f3f6; rclsid
0x18004564e  call    cs:__imp_CoCreateInstance
0x180045654  test    eax, eax
0x180045656  jns     short loc_180045671
0x180045658  mov     rcx, cs:WPP_GLOBAL_Control
0x18004565f  cmp     rcx, r12
0x180045662  jz      short loc_1800456C2
0x180045664  test    byte ptr [rcx+1Ch], 2
0x180045668  jz      short loc_1800456C2
0x18004566a  mov     edx, 39h ; '9'
0x18004566f  jmp     short loc_1800456B2
0x180045671  mov     rcx, [rsp+330h+var_2F8]
0x180045676  movups  xmm0, xmmword ptr cs:CLSID_WLANRM.Data1
0x18004567d  movdqu  [rsp+330h+var_2E0], xmm0
0x180045683  mov     rax, [rcx]
0x180045686  mov     r8d, esi
0x180045689  lea     rdx, [rsp+330h+var_2E0]
0x18004568e  mov     rax, [rax+48h]
0x180045692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045697  test    eax, eax
0x180045699  jns     short loc_1800456C2
0x18004569b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456a2  cmp     rcx, r12
0x1800456a5  jz      short loc_1800456C2
0x1800456a7  test    byte ptr [rcx+1Ch], 2
0x1800456ab  jz      short loc_1800456C2
0x1800456ad  mov     edx, 3Ah ; ':'
0x1800456b2  mov     r9d, eax
0x1800456b5  mov     r8, r13
0x1800456b8  mov     rcx, [rcx+10h]
0x1800456bc  call    WPP_SF_d
0x1800456c1  nop
0x1800456c2  mov     rcx, [rsp+330h+var_2F8]
0x1800456c7  test    rcx, rcx
0x1800456ca  jz      short loc_1800456E2
0x1800456cc  mov     [rsp+330h+var_2F8], 0
0x1800456d5  mov     rax, [rcx]
0x1800456d8  mov     rax, [rax+10h]
0x1800456dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456e1  nop
0x1800456e2  mov     [rsp+330h+var_2F0], 0
0x1800456ea  mov     dword ptr [rsp+330h+var_2F8], 0
0x1800456f2  lea     r8, [rsp+330h+var_2F0]; unsigned int *
0x1800456f7  lea     rdx, [rsp+330h+var_2F8]; enum Windows::Networking::UX::WiFiPowerBackOnOption *
0x1800456fc  call    ?GetPowerBackOnOption@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEAW4WiFiPowerBackOnOption@345@PEAI@Z; Windows::Networking::UX::Internal::WlanInterface::GetPowerBackOnOption(Windows::Networking::UX::WiFiPowerBackOnOption *,uint *)
0x180045701  test    eax, eax
0x180045703  jns     short loc_180045741
0x180045705  mov     rax, cs:WPP_GLOBAL_Control
0x18004570c  cmp     rax, r12
0x18004570f  jz      short loc_180045741
0x180045711  test    byte ptr [rax+1Ch], 2
0x180045715  jz      short loc_180045741
0x180045717  lea     r8, [rsp+330h+var_2F0]; unsigned int *
0x18004571c  lea     rdx, [rsp+330h+var_2F8]; enum Windows::Networking::UX::WiFiPowerBackOnOption *
0x180045721  call    ?GetPowerBackOnOption@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEAW4WiFiPowerBackOnOption@345@PEAI@Z; Windows::Networking::UX::Internal::WlanInterface::GetPowerBackOnOption(Windows::Networking::UX::WiFiPowerBackOnOption *,uint *)
0x180045726  mov     edx, 3Bh ; ';'
0x18004572b  mov     r9d, eax
0x18004572e  mov     r8, r13
0x180045731  mov     rcx, cs:WPP_GLOBAL_Control
0x180045738  mov     rcx, [rcx+10h]
0x18004573c  call    WPP_SF_d
0x180045741  test    sil, sil
0x180045744  setnz   sil
0x180045748  mov     [rsp+330h+var_300], sil
0x18004574d  lea     rax, [rsp+330h+var_2F0]
0x180045752  mov     [rsp+330h+ppv], rax
0x180045757  lea     r9, [rsp+330h+var_2F8]
0x18004575c  lea     r8, [rsp+330h+var_300]
0x180045761  mov     edx, ebx; __int64
0x180045763  lea     rcx, [rbp+230h+var_180]; this
0x18004576a  call    ??$StopWithResult@_NAEAW4WiFiPowerBackOnOption@UX@Networking@Windows@@AEAI@SetRadioState@NetworkUxTelemetry@@QEAAXJ$$QEA_NAEAW4WiFiPowerBackOnOption@UX@Networking@Windows@@AEAI@Z; NetworkUxTelemetry::SetRadioState::StopWithResult<bool,Windows::Networking::UX::WiFiPowerBackOnOption &,uint &>(long,bool &&,Windows::Networking::UX::WiFiPowerBackOnOption &,uint &)
0x18004576f  cmp     byte ptr [rdi+4A2h], 0
0x180045776  jz      short loc_1800457F7
0x180045778  lea     rbx, [rdi+4A4h]
0x18004577f  mov     rdx, rbx; struct _GUID *
0x180045782  lea     rcx, [rsp+330h+var_2D0]; this
0x180045787  call    ??$Start@AEAU_GUID@@@SetRadioState@NetworkUxTelemetry@@SA?AV01@AEAU_GUID@@@Z; NetworkUxTelemetry::SetRadioState::Start<_GUID &>(_GUID &)
0x18004578c  lea     r8d, [r14+1]; enum _WLAN_OPERATIONAL_STATE
0x180045790  mov     rdx, rbx; struct _GUID *
0x180045793  mov     rcx, [rdi+18h]; this
0x180045797  call    ?SetOperationalState@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@W4_WLAN_OPERATIONAL_STATE@@@Z; Windows::Networking::UX::Internal::WlanClient::SetOperationalState(_GUID const &,_WLAN_OPERATIONAL_STATE)
0x18004579c  mov     ebx, eax
0x18004579e  test    eax, eax
0x1800457a0  jns     short loc_1800457C8
0x1800457a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457a9  cmp     rcx, r12
0x1800457ac  jz      short loc_1800457C8
0x1800457ae  test    byte ptr [rcx+1Ch], 2
0x1800457b2  jz      short loc_1800457C8
0x1800457b4  mov     edx, 3Ch ; '<'
0x1800457b9  mov     r9d, eax
0x1800457bc  mov     r8, r13
0x1800457bf  mov     rcx, [rcx+10h]
0x1800457c3  call    WPP_SF_d
0x1800457c8  mov     [rsp+330h+var_300], sil
0x1800457cd  lea     rax, [rsp+330h+var_2F0]
0x1800457d2  mov     [rsp+330h+ppv], rax
0x1800457d7  lea     r9, [rsp+330h+var_2F8]
0x1800457dc  lea     r8, [rsp+330h+var_300]
0x1800457e1  mov     edx, ebx; __int64
0x1800457e3  lea     rcx, [rsp+330h+var_2D0]; this
0x1800457e8  call    ??$StopWithResult@_NAEAW4WiFiPowerBackOnOption@UX@Networking@Windows@@AEAI@SetRadioState@NetworkUxTelemetry@@QEAAXJ$$QEA_NAEAW4WiFiPowerBackOnOption@UX@Networking@Windows@@AEAI@Z; NetworkUxTelemetry::SetRadioState::StopWithResult<bool,Windows::Networking::UX::WiFiPowerBackOnOption &,uint &>(long,bool &&,Windows::Networking::UX::WiFiPowerBackOnOption &,uint &)
0x1800457ed  lea     rcx, [rsp+330h+var_2D0]; this
0x1800457f2  call    ??1SetRadioState@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::SetRadioState::~SetRadioState(void)
0x1800457f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457fe  cmp     rcx, r12
0x180045801  jz      short loc_18004581E
0x180045803  test    byte ptr [rcx+1Ch], 8
0x180045807  jz      short loc_18004581E
0x180045809  mov     edx, 3Dh ; '='
0x18004580e  mov     r9d, ebx
0x180045811  mov     r8, r13
0x180045814  mov     rcx, [rcx+10h]
0x180045818  call    WPP_SF_d
0x18004581d  nop
0x18004581e  lea     rcx, [rbp+230h+var_180]; this
0x180045825  call    ??1SetRadioState@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::SetRadioState::~SetRadioState(void)
0x18004582a  mov     eax, ebx
0x18004582c  mov     rcx, [rbp+230h+var_30]
0x180045833  xor     rcx, rsp; StackCookie
0x180045836  call    __security_check_cookie
0x18004583b  lea     r11, [rsp+330h+var_20]
0x180045843  mov     rbx, [r11+40h]
0x180045847  mov     rsi, [r11+48h]
0x18004584b  mov     rsp, r11
0x18004584e  pop     r14
0x180045850  pop     r13
0x180045852  pop     r12
0x180045854  pop     rdi
0x180045855  pop     rbp
0x180045856  retn
```
