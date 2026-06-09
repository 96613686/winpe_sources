# COCATpTransport::OCAUploadSecondaryData(wchar_t const *,wchar_t const *)

- ea: `0x180084380`
- end: `0x180084884`
- name: `?OCAUploadSecondaryData@COCATpTransport@@IEAAJPEB_W0@Z`
- size: `1284`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008273c`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000dad0`
- `0x180016514`
- `0x18001fe24`
- `0x18002556c`
- `0x1800293ac`
- `0x180039d00`
- `0x18003bed8`
- `0x18003bf14`
- `0x18003c24c`
- `0x18003df8c`
- `0x180045854`
- `0x1800489f0`
- `0x180049a60`
- `0x18004ae6c`
- `0x18004c774`
- `0x18004cdec`
- `0x18007209c`
- `0x180084380`
- `0x180084b14`
- `0x180085b38`
- `0x18008f39c`
- `0x18008f3d0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084426`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084426`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084716`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084716`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008468e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008468e`

## string_xrefs

- `0x180084778`: `TpToken`
- `0x180084769`: `TpTokenExp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall COCATpTransport::OCAUploadSecondaryData(COCATpTransport *this, wchar_t *a2, wchar_t *a3)
{
  void **v5; // r12
  int v6; // edi
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  struct CReportCabStream *v11; // r15
  void *v12; // rbx
  unsigned __int64 v13; // rax
  int DeviceTicketHeader; // eax
  const wchar_t *v15; // rbx
  unsigned __int64 v16; // rax
  const wchar_t *v17; // r8
  CReport **v18; // r14
  BOOL v19; // r13d
  int v20; // ebx
  __int64 v21; // rdi
  int v22; // eax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  bool v26; // [rsp+28h] [rbp-D8h]
  void *v27; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+88h] [rbp-78h]
  struct CReportCabStream *v29[2]; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+9Ch] [rbp-64h]
  __int64 v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v35[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v36[56]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v37[928]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v38; // [rsp+510h] [rbp+410h] BYREF
  wchar_t *v39; // [rsp+520h] [rbp+420h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+528h] [rbp+428h] BYREF

  v39 = a3;
  CReportCab::CReportCab((CReportCab *)v36);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v37);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v34);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v33);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v31[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
  SystemTimeAsFileTime = 0;
  v5 = (void **)((char *)this + 40);
  *(_OWORD *)v29 = 0;
  v30 = 0;
  v28 = 7;
  v27 = (void *)*((_QWORD *)this + 5);
  CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v27);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *((_QWORD *)this + 49) <= *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    v6 = 1;
    goto LABEL_47;
  }
  v29[0] = 0;
  v29[1] = 0;
  v30 = 0;
  v28 = 10;
  v27 = *v5;
  v7 = CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v27);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)v7);
    goto LABEL_47;
  }
  v11 = *(struct CReportCabStream **)((char *)v29 + 4);
  if ( !*(struct CReportCabStream **)((char *)v29 + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10);
  *((_DWORD *)this + 84) = 1;
  v12 = *v5;
  v13 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v11 + 32LL))(v11);
  CTransport::EventUploadStart(this, v13, v12);
  DeviceTicketHeader = CTransport::GetDeviceTicketHeader(v32, *v5);
  v6 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)DeviceTicketHeader);
    goto LABEL_47;
  }
  if ( UtilRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting",
         L"EnableZip",
         1u,
         0,
         v26) )
  {
    v22 = COCATpTransport::UploadToAzure(this, v11, a2, v32[0]);
    v6 = v22;
    if ( v22 >= 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_47;
      v24 = 27;
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)v22);
        v23 = WPP_GLOBAL_Control;
      }
      if ( !*((_DWORD *)this + 88) )
        goto LABEL_20;
      if ( v23 == (wchar_t *)&WPP_GLOBAL_Control || (v23[14] & 4) == 0 )
        goto LABEL_47;
      v24 = 26;
    }
    WPP_SF_(*((_QWORD *)v23 + 2), v24, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
LABEL_20:
  v15 = L"zip";
  if ( !*((_DWORD *)v11 + 4) )
    v15 = L"cab";
  v16 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v11 + 32LL))(v11);
  v31[1] = (__int64)this + 56;
  v17 = 0;
  if ( *((_QWORD *)this + 11) != *((_QWORD *)this + 12) )
    v17 = (const wchar_t *)*((_QWORD *)this + 11);
  v18 = (CReport **)((char *)this + 48);
  v6 = COCATpTransport::PrepareCabUploadRequest(
         *((struct CReport **)this + 6),
         a2,
         v17,
         v39,
         v16,
         v15,
         0,
         0,
         (struct CTpRequestMessage *)v37);
  if ( v6 >= 0 )
  {
    v19 = 0;
    v20 = 0;
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CReport *)((char *)*v18 + 46688))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*v18) )
    {
      v20 = 2;
    }
    v21 = *((_QWORD *)*v18 + 6507);
    if ( v21 )
      v19 = ImpersonateLoggedOnUser(*((HANDLE *)*v18 + 6507));
    v6 = CTpTransport::DoExchange(
           (struct CTpRequestMessage *)v37,
           v11,
           (CTpResponseMessage *)v34,
           (__int64)&COCATpTransport::tpCommandConstructors,
           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           v20,
           0,
           v21,
           *v5,
           (COCATpTransport *)((char *)this + 192),
           (wchar_t *)L"data-upload/secondary",
           0,
           v32[0],
           (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
           0);
    if ( v19 )
      RevertToSelf();
    if ( v6 >= 0 )
    {
      v6 = COCATpTransport::ParseCabUploadResponse(
             (CTpResponseMessage *)v34,
             (CReport *)((char *)*v18 + 8),
             (__int64)v35,
             (__int64)v31,
             (__int64)&v38,
             0);
      if ( v6 >= 0 )
      {
        CReport::RemoveStateParamByKey(*v18, L"TpTokenExp");
        CReport::RemoveStateParamByKey(*v18, L"TpToken");
        v6 = 0;
      }
    }
  }
LABEL_47:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(v33);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v34);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v37);
  CReportCab::~CReportCab((CReportCab *)v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180084380  mov     [rsp-8+arg_8], rbx
0x180084385  mov     [rsp-8+arg_10], r8
0x18008438a  push    rbp
0x18008438b  push    rsi
0x18008438c  push    rdi
0x18008438d  push    r12
0x18008438f  push    r13
0x180084391  push    r14
0x180084393  push    r15
0x180084395  lea     rbp, [rsp-3D0h]
0x18008439d  sub     rsp, 4D0h
0x1800843a4  mov     r13, rdx
0x1800843a7  mov     rsi, rcx
0x1800843aa  lea     rcx, [rbp+400h+var_3D8]; this
0x1800843ae  call    ??0CReportCab@@QEAA@XZ; CReportCab::CReportCab(void)
0x1800843b3  nop
0x1800843b4  lea     rcx, [rbp+400h+var_3A0]; this
0x1800843b8  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800843bd  nop
0x1800843be  lea     rcx, [rbp+400h+var_418]; this
0x1800843c2  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x1800843c7  nop
0x1800843c8  lea     rcx, [rbp+400h+var_430]
0x1800843cc  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800843d1  nop
0x1800843d2  lea     rcx, [rbp+400h+var_3F8]; void *
0x1800843d6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800843db  nop
0x1800843dc  xor     r14d, r14d
0x1800843df  mov     [rbp+400h+var_460], r14
0x1800843e3  lea     rcx, [rbp+400h+var_450]; void *
0x1800843e7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800843ec  nop
0x1800843ed  mov     qword ptr [rbp+400h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800843f4  lea     r12, [rsi+28h]
0x1800843f8  xorps   xmm0, xmm0
0x1800843fb  movdqu  xmmword ptr [rbp+400h+var_474], xmm0
0x180084400  mov     [rbp+400h+var_464], r14d
0x180084404  mov     [rbp+400h+var_478], 7
0x18008440b  mov     rax, [r12]
0x18008440f  mov     [rbp+400h+var_480], rax
0x180084413  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x180084417  mov     rcx, rsi; this
0x18008441a  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x18008441f  lea     rcx, [rbp+400h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180084426  call    cs:__imp_GetSystemTimeAsFileTime
0x18008442c  mov     ecx, [rbp+400h+SystemTimeAsFileTime.dwHighDateTime]
0x180084432  shl     rcx, 20h
0x180084436  mov     eax, [rbp+400h+SystemTimeAsFileTime.dwLowDateTime]
0x18008443c  or      rcx, rax
0x18008443f  cmp     [rsi+188h], rcx
0x180084446  ja      short loc_180084482
0x180084448  lea     rbx, WPP_GLOBAL_Control
0x18008444f  mov     rcx, cs:WPP_GLOBAL_Control
0x180084456  cmp     rcx, rbx
0x180084459  jz      short loc_180084478
0x18008445b  lea     edx, [r14+2]
0x18008445f  test    [rcx+1Ch], dl
0x180084462  jz      short loc_180084478
0x180084464  lea     edx, [r14+16h]
0x180084468  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008446f  mov     rcx, [rcx+10h]
0x180084473  call    WPP_SF_
0x180084478  mov     edi, 1
0x18008447d  jmp     loc_18008482C
0x180084482  mov     [rbp+400h+var_474], r14
0x180084486  mov     [rbp+400h+var_474+8], r14
0x18008448a  mov     [rbp+400h+var_464], r14d
0x18008448e  mov     [rbp+400h+var_478], 0Ah
0x180084495  mov     rax, [r12]
0x180084499  mov     [rbp+400h+var_480], rax
0x18008449d  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x1800844a1  mov     rcx, rsi; this
0x1800844a4  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x1800844a9  mov     edi, eax
0x1800844ab  test    eax, eax
0x1800844ad  jns     short loc_1800844ED
0x1800844af  lea     rbx, WPP_GLOBAL_Control
0x1800844b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844bd  cmp     rcx, rbx
0x1800844c0  jz      loc_18008482C
0x1800844c6  test    byte ptr [rcx+1Ch], 1
0x1800844ca  jz      loc_18008482C
0x1800844d0  mov     edx, 17h
0x1800844d5  mov     r9d, eax
0x1800844d8  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800844df  mov     rcx, [rcx+10h]
0x1800844e3  call    WPP_SF_d
0x1800844e8  jmp     loc_18008482C
0x1800844ed  mov     r15, [rbp+400h+var_474+4]
0x1800844f1  test    r15, r15
0x1800844f4  jnz     short loc_1800844FB
0x1800844f6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800844fb  mov     dword ptr [rsi+150h], 1
0x180084505  mov     rbx, [r12]
0x180084509  mov     rax, [r15]
0x18008450c  mov     rcx, r15
0x18008450f  mov     rax, [rax+20h]
0x180084513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084518  mov     r8, rbx; void *
0x18008451b  mov     rdx, rax; unsigned __int64
0x18008451e  mov     rcx, rsi; this
0x180084521  call    ?EventUploadStart@CTransport@@IEAAJ_KPEAX@Z; CTransport::EventUploadStart(unsigned __int64,void *)
0x180084526  mov     rdx, [r12]
0x18008452a  lea     rcx, [rbp+400h+var_450]
0x18008452e  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180084533  mov     edi, eax
0x180084535  test    eax, eax
0x180084537  jns     short loc_18008457B
0x180084539  lea     rbx, WPP_GLOBAL_Control
0x180084540  mov     rcx, cs:WPP_GLOBAL_Control
0x180084547  cmp     rcx, rbx
0x18008454a  jz      loc_18008482C
0x180084550  mov     edx, 2
0x180084555  test    [rcx+1Ch], dl
0x180084558  jz      loc_18008482C
0x18008455e  mov     edx, 18h
0x180084563  mov     r9d, eax
0x180084566  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008456d  mov     rcx, [rcx+10h]
0x180084571  call    WPP_SF_d
0x180084576  jmp     loc_18008482C
0x18008457b  mov     [rsp+500h+var_4E0], r14; bool *
0x180084580  mov     r9d, 1; unsigned int
0x180084586  lea     r8, aEnablezip; "EnableZip"
0x18008458d  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x180084594  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18008459b  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800845a0  test    eax, eax
0x1800845a2  jnz     loc_18008478E
0x1800845a8  lea     rbx, WPP_GLOBAL_Control
0x1800845af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800845b6  cmp     rcx, rbx
0x1800845b9  jz      short loc_1800845D4
0x1800845bb  test    byte ptr [rcx+1Ch], 4
0x1800845bf  jz      short loc_1800845D4
0x1800845c1  lea     edx, [rax+49h]
0x1800845c4  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800845cb  mov     rcx, [rcx+10h]
0x1800845cf  call    WPP_SF_
0x1800845d4  lea     rax, aCab_1; "cab"
0x1800845db  lea     rbx, aZip_0; "zip"
0x1800845e2  cmp     [r15+10h], r14d
0x1800845e6  cmovz   rbx, rax
0x1800845ea  mov     rax, [r15]
0x1800845ed  mov     rcx, r15
0x1800845f0  mov     rax, [rax+20h]
0x1800845f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845f9  lea     rdx, [rsi+38h]
0x1800845fd  mov     [rbp+400h+var_458], rdx
0x180084601  mov     rcx, [rdx+20h]
0x180084605  mov     r8, r14
0x180084608  cmp     rcx, [rdx+28h]
0x18008460c  cmovnz  r8, rcx; wchar_t *
0x180084610  lea     r14, [rsi+30h]
0x180084614  lea     rcx, [rbp+400h+var_3A0]
0x180084618  mov     [rsp+500h+var_4C0], rcx; struct CTpRequestMessage *
0x18008461d  mov     [rsp+500h+var_4C8], 0; wchar_t *
0x180084626  mov     dword ptr [rsp+500h+var_4D0], 0; int
0x18008462e  mov     [rsp+500h+var_4D8], rbx; wchar_t *
0x180084633  mov     [rsp+500h+var_4E0], rax; unsigned __int64
0x180084638  mov     r9, [rbp+400h+arg_10]; wchar_t *
0x18008463f  mov     rdx, r13; wchar_t *
0x180084642  mov     rcx, [r14]; struct CReport *
0x180084645  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x18008464a  mov     edi, eax
0x18008464c  test    eax, eax
0x18008464e  js      loc_18008482C
0x180084654  xor     r13d, r13d
0x180084657  xor     ebx, ebx
0x180084659  mov     rcx, [r14]
0x18008465c  add     rcx, 0B660h; this
0x180084663  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x180084668  test    eax, eax
0x18008466a  jz      short loc_18008467C
0x18008466c  mov     rcx, [r14]; this
0x18008466f  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180084674  lea     edx, [rbx+2]
0x180084677  test    eax, eax
0x180084679  cmovz   ebx, edx
0x18008467c  mov     rax, [r14]
0x18008467f  mov     rdi, [rax+0CB58h]
0x180084686  test    rdi, rdi
0x180084689  jz      short loc_180084697
0x18008468b  mov     rcx, rdi; hToken
0x18008468e  call    cs:__imp_ImpersonateLoggedOnUser
0x180084694  mov     r13d, eax
0x180084697  mov     r8, [rbp+400h+var_450]
0x18008469b  lea     r9, [rsi+0C0h]
0x1800846a2  lea     rcx, [rsi+20h]
0x1800846a6  neg     rsi
0x1800846a9  sbb     r10, r10
0x1800846ac  and     r10, rcx
0x1800846af  xor     esi, esi
0x1800846b1  mov     [rsp+500h+var_490], esi; int
0x1800846b5  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x1800846bc  mov     [rsp+500h+var_498], rax; __int64
0x1800846c1  mov     [rsp+500h+var_4A0], r8; __int64
0x1800846c6  mov     qword ptr [rsp+500h+var_4A8], rsi; int
0x1800846cb  lea     rax, aDataUploadSeco; "data-upload/secondary"
0x1800846d2  mov     [rsp+500h+var_4B0], rax; __int64
0x1800846d7  mov     [rsp+500h+var_4B8], r9; __int64
0x1800846dc  mov     rax, [r12]
0x1800846e0  mov     [rsp+500h+var_4C0], rax; __int64
0x1800846e5  mov     [rsp+500h+var_4C8], rdi; __int64
0x1800846ea  mov     [rsp+500h+var_4D0], rsi; int
0x1800846ef  mov     dword ptr [rsp+500h+var_4D8], ebx; int
0x1800846f3  mov     [rsp+500h+var_4E0], r10; struct ITpCallbacks *
0x1800846f8  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x1800846ff  lea     r8, [rbp+400h+var_418]
0x180084703  mov     rdx, r15
0x180084706  lea     rcx, [rbp+400h+var_3A0]; this
0x18008470a  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x18008470f  mov     edi, eax
0x180084711  test    r13d, r13d
0x180084714  jz      short loc_18008471C
0x180084716  call    cs:__imp_RevertToSelf
0x18008471c  test    edi, edi
0x18008471e  js      loc_18008482C
0x180084724  mov     rdx, [r14]
0x180084727  add     rdx, 8; CResponse *
0x18008472b  mov     [rsp+500h+var_4C8], rsi; __int64
0x180084730  lea     rax, [rbp+400h+arg_0]
0x180084737  mov     [rsp+500h+var_4D0], rax; __int64
0x18008473c  lea     rax, [rbp+400h+var_460]
0x180084740  mov     [rsp+500h+var_4D8], rax; __int64
0x180084745  lea     rax, [rbp+400h+var_3F8]
0x180084749  mov     [rsp+500h+var_4E0], rax; __int64
0x18008474e  lea     r9, [rbp+400h+var_430]
0x180084752  mov     r8, [rbp+400h+var_458]
0x180084756  lea     rcx, [rbp+400h+var_418]; this
0x18008475a  call    ?ParseCabUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAVCResponse@@PEAVCOCAReply@@PEAVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH4@Z; COCATpTransport::ParseCabUploadResponse(CTpResponseMessage *,CResponse *,COCAReply *,CDataRequest *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008475f  mov     edi, eax
0x180084761  test    eax, eax
0x180084763  js      loc_18008482C
0x180084769  lea     rdx, aTptokenexp; "TpTokenExp"
0x180084770  mov     rcx, [r14]; this
0x180084773  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x180084778  lea     rdx, aTptoken; "TpToken"
0x18008477f  mov     rcx, [r14]; this
0x180084782  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x180084787  mov     edi, esi
0x180084789  jmp     loc_18008482C
0x18008478e  mov     r9, [rbp+400h+var_450]; wchar_t *
0x180084792  mov     r8, r13; wchar_t *
0x180084795  mov     rdx, r15; struct CReportCabStream *
0x180084798  mov     rcx, rsi; this
0x18008479b  call    ?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z; COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)
0x1800847a0  mov     edi, eax
0x1800847a2  test    eax, eax
0x1800847a4  jns     short loc_1800847FD
0x1800847a6  lea     rbx, WPP_GLOBAL_Control
0x1800847ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800847b4  cmp     rcx, rbx
0x1800847b7  jz      short loc_1800847DE
0x1800847b9  test    byte ptr [rcx+1Ch], 1
0x1800847bd  jz      short loc_1800847DE
0x1800847bf  mov     edx, 19h
0x1800847c4  mov     r9d, eax
0x1800847c7  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800847ce  mov     rcx, [rcx+10h]
0x1800847d2  call    WPP_SF_d
0x1800847d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800847de  cmp     [rsi+160h], r14d
0x1800847e5  jz      loc_1800845D4
0x1800847eb  cmp     rcx, rbx
0x1800847ee  jz      short loc_18008482C
0x1800847f0  test    byte ptr [rcx+1Ch], 4
0x1800847f4  jz      short loc_18008482C
0x1800847f6  mov     edx, 1Ah
0x1800847fb  jmp     short loc_18008481B
0x1800847fd  lea     rbx, WPP_GLOBAL_Control
0x180084804  mov     rcx, cs:WPP_GLOBAL_Control
0x18008480b  cmp     rcx, rbx
0x18008480e  jz      short loc_18008482C
0x180084810  test    byte ptr [rcx+1Ch], 4
0x180084814  jz      short loc_18008482C
0x180084816  mov     edx, 1Bh
0x18008481b  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180084822  mov     rcx, [rcx+10h]
0x180084826  call    WPP_SF_
0x18008482b  nop
0x18008482c  lea     rcx, [rbp+400h+var_450]; void *
0x180084830  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180084835  nop
0x180084836  lea     rcx, [rbp+400h+var_3F8]; void *
0x18008483a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008483f  nop
0x180084840  lea     rcx, [rbp+400h+var_430]
0x180084844  call    ?_Uninit@?$vector@VRequestToken@@V?$allocator@VRequestToken@@@utl@@@utl@@AEAAXXZ; utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(void)
0x180084849  nop
0x18008484a  lea     rcx, [rbp+400h+var_418]; this
0x18008484e  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180084853  nop
0x180084854  lea     rcx, [rbp+400h+var_3A0]; this
0x180084858  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008485d  nop
0x18008485e  lea     rcx, [rbp+400h+var_3D8]; this
0x180084862  call    ??1CReportCab@@QEAA@XZ; CReportCab::~CReportCab(void)
0x180084867  mov     eax, edi
  ... truncated ...
```
