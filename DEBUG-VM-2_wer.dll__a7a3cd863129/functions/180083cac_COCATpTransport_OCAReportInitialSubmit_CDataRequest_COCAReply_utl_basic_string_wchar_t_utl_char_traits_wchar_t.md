# COCATpTransport::OCAReportInitialSubmit(CDataRequest *,COCAReply *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)

- ea: `0x180083cac`
- end: `0x18008437a`
- name: `?OCAReportInitialSubmit@COCATpTransport@@IEAAJPEAVCDataRequest@@PEAVCOCAReply@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z`
- size: `1742`
- prototype: `__int64 __usercall@<rax>(COCATpTransport *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008273c`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000dad0`
- `0x18001fe24`
- `0x18002556c`
- `0x180026498`
- `0x180038ce4`
- `0x180039d00`
- `0x18003c24c`
- `0x18003df8c`
- `0x18003f364`
- `0x180045854`
- `0x1800489f0`
- `0x18004c774`
- `0x180070aa4`
- `0x18007209c`
- `0x180082eb0`
- `0x1800832cc`
- `0x180083cac`
- `0x180084b14`
- `0x180084f78`
- `0x18008539c`
- `0x18008f354`
- `0x18008f3d0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180083f3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084168`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180083f3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084168`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180083eb8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800840d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180083eb8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800840d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall COCATpTransport::OCAReportInitialSubmit(
        COCATpTransport *this,
        CDataRequest *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        _DWORD *a6)
{
  int DeviceTicketHeader; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  const wchar_t *v13; // rcx
  _DWORD *v14; // rsi
  BOOL v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rbx
  struct IWerByteStream *v18; // r15
  const wchar_t *v19; // rbx
  unsigned __int64 v20; // rax
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rsi
  unsigned __int64 *v24; // rsi
  CDataRequest *v25; // r14
  int v26; // eax
  unsigned int i; // r9d
  CReport *v28; // rcx
  int v29; // r9d
  struct CReportCabStream *v31[2]; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *v32[4]; // [rsp+A0h] [rbp-68h] BYREF
  const wchar_t *v33[4]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v34[4]; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t *v35[4]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v36[32]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v37[40]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v38[880]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v39[928]; // [rsp+4D8h] [rbp+3D0h] BYREF
  struct CReportFile *v40; // [rsp+888h] [rbp+780h] BYREF
  CDataRequest *v41; // [rsp+890h] [rbp+788h]
  __int64 v42; // [rsp+898h] [rbp+790h]

  v42 = a3;
  v41 = a2;
  v31[0] = 0;
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v39);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v37);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v38);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v36);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v33);
  v31[1] = 0;
  LODWORD(v40) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  DeviceTicketHeader = CTpRequestMessage::SetCommercialInfo(
                         v39,
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
                         *((_QWORD *)this + 6) + 51920LL);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 13;
LABEL_5:
    v12 = (unsigned int)DeviceTicketHeader;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v12);
    goto LABEL_60;
  }
  DeviceTicketHeader = CTpRequestMessage::SetCommercialInfo(
                         v38,
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
                         *((_QWORD *)this + 6) + 51920LL);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 14;
    goto LABEL_5;
  }
  v13 = *(const wchar_t **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v13 = 0;
  *a5 = 0;
  v14 = a6;
  *a6 = 0;
  DeviceTicketHeader = COCATpTransport::HandleAsyncStage2Prolog(this);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 15;
    goto LABEL_5;
  }
  DeviceTicketHeader = CTransport::GetDeviceTicketHeader(v34, *((_QWORD *)this + 5));
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      goto LABEL_60;
    v11 = 16;
    goto LABEL_5;
  }
  v15 = 0;
  v9 = COCATpTransport::PrepareReqUploadRequest(*((struct CReport **)this + 6), (struct CTpRequestMessage *)v39);
  if ( v9 < 0 )
    goto LABEL_60;
  v16 = *((_QWORD *)this + 6);
  v17 = *(_QWORD *)(v16 + 52056);
  if ( v17 )
    v15 = ImpersonateLoggedOnUser(*(HANDLE *)(v16 + 52056));
  v9 = CTpTransport::DoExchange(
         (struct CTpRequestMessage *)v39,
         0,
         (CTpResponseMessage *)v37,
         (__int64)&COCATpTransport::tpCommandConstructors,
         (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
         0,
         0,
         v17,
         *((void **)this + 5),
         (COCATpTransport *)((char *)this + 192),
         (wchar_t *)L"request-upload/minidump",
         0,
         (wchar_t *)v34[0],
         0,
         0);
  if ( v15 )
  {
    RevertToSelf();
    v15 = 0;
  }
  if ( v9 < 0 )
    goto LABEL_60;
  v9 = COCATpTransport::ParseReqUploadResponse((CTpResponseMessage *)v37);
  if ( v9 < 0 )
    goto LABEL_60;
  if ( (_DWORD)v40 )
  {
    *v14 = 1;
    v9 = 1769483;
    goto LABEL_60;
  }
  if ( v33[0] == v33[1] )
  {
    v9 = 1;
    goto LABEL_60;
  }
  DeviceTicketHeader = CTransport::EventGetUploadCab(this, v31, *((void **)this + 5), 0);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 17;
    goto LABEL_5;
  }
  v18 = v31[0];
  if ( !v31[0] )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(LODWORD(v31[0]) + 18),
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    goto LABEL_60;
  }
  v19 = L"zip";
  if ( !*((_DWORD *)v31[0] + 4) )
    v19 = L"cab";
  v20 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v31[0] + 32LL))(v31[0]);
  v9 = COCATpTransport::PrepareCabUploadRequest(
         *((struct CReport **)this + 6),
         L"minidump",
         0,
         v33[0],
         v20,
         v19,
         1,
         0,
         (struct CTpRequestMessage *)v38);
  if ( v9 >= 0 )
  {
    v21 = 0;
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
    {
      v21 = 2;
    }
    v22 = *((_QWORD *)this + 6);
    v23 = *(_QWORD *)(v22 + 52056);
    if ( v23 )
      v15 = ImpersonateLoggedOnUser(*(HANDLE *)(v22 + 52056));
    v9 = CTpTransport::DoExchange(
           (struct CTpRequestMessage *)v38,
           v18,
           (CTpResponseMessage *)v36,
           (__int64)&COCATpTransport::tpCommandConstructors,
           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           v21,
           0,
           v23,
           *((void **)this + 5),
           (COCATpTransport *)((char *)this + 192),
           (wchar_t *)L"data-upload/minidump",
           0,
           (wchar_t *)v34[0],
           (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
           0);
    if ( v15 )
      RevertToSelf();
    if ( v9 >= 0 )
    {
      v24 = a5;
      v25 = v41;
      v9 = COCATpTransport::ParseCabUploadResponse(
             (CTpResponseMessage *)v36,
             (CResponse *)(*((_QWORD *)this + 6) + 8LL),
             a4,
             (__int64)a5,
             (__int64)&v40,
             (__int64)v32);
      if ( v9 >= 0 )
      {
        CDataRequest::ReadRegistryValues(
          v25,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug\\DataRequest");
        DeviceTicketHeader = COCATpTransport::HandleAsyncStage2Epilog(this, v32[0], *(const wchar_t **)a4, *v24, 0);
        v9 = DeviceTicketHeader;
        if ( DeviceTicketHeader != 1769476 )
        {
          if ( DeviceTicketHeader >= 0 )
          {
            v26 = CReport::AddStateParam(*((CReport **)this + 6), L"Transport.DoneStage1", L"1");
            if ( v26 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
                (unsigned int)v26);
            v9 = 0;
            goto LABEL_60;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_60;
          v11 = 19;
          goto LABEL_5;
        }
      }
    }
  }
LABEL_60:
  if ( v9 < 0 || v9 == 1769476 )
  {
    for ( i = 0; ; i = v29 + 1 )
    {
      v28 = (CReport *)*((_QWORD *)this + 6);
      if ( i >= (unsigned int)((__int64)(*((_QWORD *)v28 + 728) - *((_QWORD *)v28 + 727)) >> 3) )
        break;
      v40 = 0;
      if ( (int)CReport::GetFileByIndex(v28, i, &v40) < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 21;
          v12 = (unsigned int)v9;
          goto LABEL_69;
        }
        goto LABEL_60;
      }
      *((_DWORD *)v40 + 1) &= ~0x80000u;
    }
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v36);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v38);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v37);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180083cac  mov     rax, rsp
0x180083caf  mov     [rax+20h], rbx
0x180083cb3  mov     [rax+18h], r8
0x180083cb7  mov     [rax+10h], rdx
0x180083cbb  push    rbp
0x180083cbc  push    rsi
0x180083cbd  push    rdi
0x180083cbe  push    r12
0x180083cc0  push    r13
0x180083cc2  push    r14
0x180083cc4  push    r15
0x180083cc6  lea     rbp, [rax-778h]
0x180083ccd  sub     rsp, 840h
0x180083cd4  mov     r13, r9
0x180083cd7  mov     rdi, rcx
0x180083cda  xor     r15d, r15d
0x180083cdd  mov     [rbp+770h+var_7E8], r15
0x180083ce1  lea     rcx, [rbp+770h+var_3A0]; this
0x180083ce8  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180083ced  nop
0x180083cee  lea     rcx, [rbp+770h+var_738]; this
0x180083cf2  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180083cf7  nop
0x180083cf8  lea     rcx, [rbp+770h+var_710]; this
0x180083cfc  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180083d01  nop
0x180083d02  lea     rcx, [rbp+770h+var_758]; this
0x180083d06  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180083d0b  nop
0x180083d0c  lea     rcx, [rbp+770h+var_7B8]; void *
0x180083d10  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d15  nop
0x180083d16  mov     [rbp+770h+var_7E0], r15
0x180083d1a  mov     dword ptr [rbp+770h+arg_0], r15d
0x180083d21  lea     rcx, [rbp+770h+var_798]; void *
0x180083d25  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d2a  nop
0x180083d2b  lea     rcx, [rbp+770h+var_7D8]; void *
0x180083d2f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d34  nop
0x180083d35  lea     rcx, [rbp+770h+var_778]; void *
0x180083d39  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d3e  nop
0x180083d3f  mov     [rbp+770h+var_7F0], r15d
0x180083d43  mov     rdx, [rdi+30h]
0x180083d47  lea     r9, [rdx+0CAD0h]
0x180083d4e  mov     r8d, [rdx+0CACCh]
0x180083d55  mov     edx, [rdx+0CAC8h]
0x180083d5b  lea     rcx, [rbp+770h+var_3A0]
0x180083d62  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180083d67  mov     ebx, eax
0x180083d69  lea     r14, WPP_GLOBAL_Control
0x180083d70  test    eax, eax
0x180083d72  jns     short loc_180083D9A
0x180083d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180083d7b  cmp     rcx, r14
0x180083d7e  jz      loc_180084287
0x180083d84  test    byte ptr [rcx+1Ch], 1
0x180083d88  jz      loc_180084287
0x180083d8e  lea     edx, [r15+0Dh]
0x180083d92  mov     r9d, eax
0x180083d95  jmp     loc_1800842F6
0x180083d9a  mov     rdx, [rdi+30h]
0x180083d9e  lea     r9, [rdx+0CAD0h]
0x180083da5  mov     r8d, [rdx+0CACCh]
0x180083dac  mov     edx, [rdx+0CAC8h]
0x180083db2  lea     rcx, [rbp+770h+var_710]
0x180083db6  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180083dbb  mov     ebx, eax
0x180083dbd  test    eax, eax
0x180083dbf  jns     short loc_180083DE2
0x180083dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180083dc8  cmp     rcx, r14
0x180083dcb  jz      loc_180084287
0x180083dd1  test    byte ptr [rcx+1Ch], 1
0x180083dd5  jz      loc_180084287
0x180083ddb  mov     edx, 0Eh
0x180083de0  jmp     short loc_180083D92
0x180083de2  mov     rcx, [r13+0]
0x180083de6  mov     [r13+8], rcx
0x180083dea  mov     [rcx], r15w
0x180083dee  mov     rax, [rbp+770h+arg_20]
0x180083df5  mov     [rax], r15
0x180083df8  mov     rsi, [rbp+770h+arg_28]
0x180083dff  mov     [rsi], r15d
0x180083e02  lea     r9, [rbp+770h+var_7F0]
0x180083e06  lea     r8, [rbp+770h+var_778]
0x180083e0a  lea     rdx, [rbp+770h+var_7D8]
0x180083e0e  mov     rcx, rdi; this
0x180083e11  call    ?HandleAsyncStage2Prolog@COCATpTransport@@IEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAH@Z; COCATpTransport::HandleAsyncStage2Prolog(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *)
0x180083e16  mov     ebx, eax
0x180083e18  test    eax, eax
0x180083e1a  jns     short loc_180083E40
0x180083e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e23  cmp     rcx, r14
0x180083e26  jz      loc_180084287
0x180083e2c  test    byte ptr [rcx+1Ch], 1
0x180083e30  jz      loc_180084287
0x180083e36  mov     edx, 0Fh
0x180083e3b  jmp     loc_180083D92
0x180083e40  mov     rdx, [rdi+28h]
0x180083e44  lea     rcx, [rbp+770h+var_798]
0x180083e48  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180083e4d  mov     ebx, eax
0x180083e4f  test    eax, eax
0x180083e51  jns     short loc_180083E7B
0x180083e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e5a  cmp     rcx, r14
0x180083e5d  jz      loc_180084287
0x180083e63  mov     edx, 2
0x180083e68  test    [rcx+1Ch], dl
0x180083e6b  jz      loc_180084287
0x180083e71  mov     edx, 10h
0x180083e76  jmp     loc_180083D92
0x180083e7b  mov     r14d, r15d
0x180083e7e  mov     r12d, [rbp+770h+var_7F0]
0x180083e82  test    r12d, r12d
0x180083e85  jnz     loc_180083F9E
0x180083e8b  lea     rdx, [rbp+770h+var_3A0]; this
0x180083e92  mov     rcx, [rdi+30h]; struct CReport *
0x180083e96  call    ?PrepareReqUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareReqUploadRequest(CReport *,CTpRequestMessage *)
0x180083e9b  mov     ebx, eax
0x180083e9d  test    eax, eax
0x180083e9f  js      loc_180084280
0x180083ea5  mov     rax, [rdi+30h]
0x180083ea9  mov     rbx, [rax+0CB58h]
0x180083eb0  test    rbx, rbx
0x180083eb3  jz      short loc_180083EC1
0x180083eb5  mov     rcx, rbx; hToken
0x180083eb8  call    cs:__imp_ImpersonateLoggedOnUser
0x180083ebe  mov     r14d, eax
0x180083ec1  mov     r8, [rbp+770h+var_798]
0x180083ec5  lea     r9, [rdi+0C0h]
0x180083ecc  mov     rcx, rdi
0x180083ecf  lea     rdx, [rdi+20h]
0x180083ed3  neg     rcx
0x180083ed6  sbb     r10, r10
0x180083ed9  and     r10, rdx
0x180083edc  mov     [rsp+70h], r15d; int
0x180083ee1  mov     [rsp+870h+var_808], r15; __int64
0x180083ee6  mov     [rsp+870h+var_810], r8; __int64
0x180083eeb  mov     qword ptr [rsp+870h+var_818], r15; int
0x180083ef0  lea     rax, aRequestUploadM; "request-upload/minidump"
0x180083ef7  mov     [rsp+870h+var_820], rax; __int64
0x180083efc  mov     [rsp+870h+var_828], r9; __int64
0x180083f01  mov     rax, [rdi+28h]
0x180083f05  mov     [rsp+870h+var_830], rax; __int64
0x180083f0a  mov     [rsp+870h+var_838], rbx; __int64
0x180083f0f  mov     [rsp+870h+var_840], r15; int
0x180083f14  mov     dword ptr [rsp+870h+var_848], r15d; int
0x180083f19  mov     [rsp+870h+var_850], r10; struct ITpCallbacks *
0x180083f1e  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180083f25  lea     r8, [rbp+770h+var_738]
0x180083f29  xor     edx, edx
0x180083f2b  lea     rcx, [rbp+770h+var_3A0]; this
0x180083f32  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180083f37  mov     ebx, eax
0x180083f39  test    r14d, r14d
0x180083f3c  jz      short loc_180083F47
0x180083f3e  call    cs:__imp_RevertToSelf
0x180083f44  mov     r14d, r15d
0x180083f47  test    ebx, ebx
0x180083f49  js      loc_180084280
0x180083f4f  lea     r9, [rbp+770h+arg_0]
0x180083f56  lea     r8, [rbp+770h+var_7E0]
0x180083f5a  lea     rdx, [rbp+770h+var_7B8]
0x180083f5e  lea     rcx, [rbp+770h+var_738]; this
0x180083f62  call    ?ParseReqUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z; COCATpTransport::ParseReqUploadResponse(CTpResponseMessage *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)
0x180083f67  mov     ebx, eax
0x180083f69  test    eax, eax
0x180083f6b  js      loc_180084280
0x180083f71  cmp     dword ptr [rbp+770h+arg_0], r15d
0x180083f78  jz      short loc_180083F8A
0x180083f7a  mov     dword ptr [rsi], 1
0x180083f80  mov     ebx, 1B000Bh
0x180083f85  jmp     loc_180084280
0x180083f8a  mov     rax, [rbp+770h+var_7B0]
0x180083f8e  cmp     [rbp+770h+var_7B8], rax
0x180083f92  jnz     short loc_180083F9E
0x180083f94  mov     ebx, 1
0x180083f99  jmp     loc_180084280
0x180083f9e  xor     r9d, r9d; int
0x180083fa1  mov     r8, [rdi+28h]; void *
0x180083fa5  lea     rdx, [rbp+770h+var_7E8]; struct CReportCabStream **
0x180083fa9  mov     rcx, rdi; this
0x180083fac  call    ?EventGetUploadCab@CTransport@@IEAAJPEAPEAVCReportCabStream@@PEAXH@Z; CTransport::EventGetUploadCab(CReportCabStream * *,void *,int)
0x180083fb1  mov     ebx, eax
0x180083fb3  test    eax, eax
0x180083fb5  jns     short loc_180083FE2
0x180083fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180083fbe  lea     r14, WPP_GLOBAL_Control
0x180083fc5  cmp     rcx, r14
0x180083fc8  jz      loc_180084287
0x180083fce  test    byte ptr [rcx+1Ch], 1
0x180083fd2  jz      loc_180084287
0x180083fd8  mov     edx, 11h
0x180083fdd  jmp     loc_180083D92
0x180083fe2  mov     r15, [rbp+770h+var_7E8]
0x180083fe6  test    r15, r15
0x180083fe9  jnz     short loc_180084020
0x180083feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180083ff2  lea     r14, WPP_GLOBAL_Control
0x180083ff9  cmp     rcx, r14
0x180083ffc  jz      short loc_180084018
0x180083ffe  test    byte ptr [rcx+1Ch], 1
0x180084002  jz      short loc_180084018
0x180084004  lea     edx, [r15+12h]
0x180084008  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008400f  mov     rcx, [rcx+10h]
0x180084013  call    WPP_SF_
0x180084018  xor     r15d, r15d
0x18008401b  jmp     loc_180084287
0x180084020  test    r12d, r12d
0x180084023  jnz     short loc_180084052
0x180084025  lea     rax, aCab_1; "cab"
0x18008402c  lea     rbx, aZip_0; "zip"
0x180084033  cmp     [r15+10h], r12d
0x180084037  cmovz   rbx, rax
0x18008403b  mov     rax, [r15]
0x18008403e  mov     rcx, r15
0x180084041  mov     rax, [rax+20h]
0x180084045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008404a  mov     r9, [rbp+770h+var_7B8]
0x18008404e  xor     ecx, ecx
0x180084050  jmp     short loc_18008405E
0x180084052  mov     r9, [rbp+770h+var_778]; wchar_t *
0x180084056  xor     eax, eax
0x180084058  xor     ebx, ebx
0x18008405a  mov     rcx, [rbp+770h+var_7D8]
0x18008405e  lea     rdx, [rbp+770h+var_710]
0x180084062  mov     [rsp+870h+var_830], rdx; struct CTpRequestMessage *
0x180084067  mov     [rsp+870h+var_838], rcx; wchar_t *
0x18008406c  mov     dword ptr [rsp+870h+var_840], 1; int
0x180084074  mov     [rsp+870h+var_848], rbx; wchar_t *
0x180084079  mov     [rsp+870h+var_850], rax; unsigned __int64
0x18008407e  xor     r8d, r8d; wchar_t *
0x180084081  lea     rdx, aMinidump_0; "minidump"
0x180084088  mov     rcx, [rdi+30h]; struct CReport *
0x18008408c  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x180084091  mov     ebx, eax
0x180084093  test    eax, eax
0x180084095  js      loc_18008427D
0x18008409b  xor     ebx, ebx
0x18008409d  mov     rcx, [rdi+30h]
0x1800840a1  add     rcx, 0B660h; this
0x1800840a8  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x1800840ad  test    eax, eax
0x1800840af  jz      short loc_1800840C2
0x1800840b1  mov     rcx, [rdi+30h]; this
0x1800840b5  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x1800840ba  lea     edx, [rbx+2]
0x1800840bd  test    eax, eax
0x1800840bf  cmovz   ebx, edx
0x1800840c2  mov     rax, [rdi+30h]
0x1800840c6  mov     rsi, [rax+0CB58h]
0x1800840cd  test    rsi, rsi
0x1800840d0  jz      short loc_1800840DE
0x1800840d2  mov     rcx, rsi; hToken
0x1800840d5  call    cs:__imp_ImpersonateLoggedOnUser
0x1800840db  mov     r14d, eax
0x1800840de  mov     r8, [rbp+770h+var_798]
0x1800840e2  mov     r10, [rdi+28h]
0x1800840e6  mov     rax, rdi
0x1800840e9  lea     rcx, [rdi+20h]
0x1800840ed  neg     rax
0x1800840f0  sbb     r11, r11
0x1800840f3  and     r11, rcx
0x1800840f6  xor     edx, edx
0x1800840f8  test    r12d, r12d
0x1800840fb  cmovz   rdx, r15
0x1800840ff  lea     rax, [rdi+0C0h]
0x180084106  xor     r15d, r15d
0x180084109  mov     [rsp+70h], r15d; int
0x18008410e  lea     rcx, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180084115  mov     [rsp+870h+var_808], rcx; __int64
0x18008411a  mov     [rsp+870h+var_810], r8; __int64
0x18008411f  mov     qword ptr [rsp+870h+var_818], r15; int
0x180084124  lea     rcx, aDataUploadMini; "data-upload/minidump"
0x18008412b  mov     [rsp+870h+var_820], rcx; __int64
0x180084130  mov     [rsp+870h+var_828], rax; __int64
0x180084135  mov     [rsp+870h+var_830], r10; __int64
0x18008413a  mov     [rsp+870h+var_838], rsi; __int64
0x18008413f  mov     [rsp+870h+var_840], r15; int
0x180084144  mov     dword ptr [rsp+870h+var_848], ebx; int
0x180084148  mov     [rsp+870h+var_850], r11; struct ITpCallbacks *
0x18008414d  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180084154  lea     r8, [rbp+770h+var_758]
0x180084158  lea     rcx, [rbp+770h+var_710]; this
0x18008415c  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180084161  mov     ebx, eax
0x180084163  test    r14d, r14d
0x180084166  jz      short loc_18008416E
0x180084168  call    cs:__imp_RevertToSelf
0x18008416e  test    ebx, ebx
0x180084170  js      loc_180084280
0x180084176  mov     rdx, [rdi+30h]
0x18008417a  add     rdx, 8; CResponse *
0x18008417e  lea     rax, [rbp+770h+var_7D8]
0x180084182  mov     [rsp+870h+var_838], rax; __int64
0x180084187  lea     rax, [rbp+770h+arg_0]
  ... truncated ...
```
