# COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)

- ea: `0x180085b38`
- end: `0x1800865a0`
- name: `?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z`
- size: `2664`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, struct CReportCabStream *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180084380`

## callees

- `0x180004198`
- `0x180004bb4`
- `0x180009ad4`
- `0x18000c390`
- `0x18000dad0`
- `0x18001fe24`
- `0x18002556c`
- `0x18002c220`
- `0x1800303dc`
- `0x180039d00`
- `0x180039e60`
- `0x18003c24c`
- `0x18003df8c`
- `0x18004559c`
- `0x180045bdc`
- `0x1800489f0`
- `0x18004c774`
- `0x18007209c`
- `0x180072d40`
- `0x1800777f4`
- `0x180083b8c`
- `0x180085184`
- `0x18008555c`
- `0x180085b38`
- `0x18008f31c`
- `0x18008f494`
- `0x18008f768`
- `0x1800a1d20`
- `0x1800a2864`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085de8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085de8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085d97`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085ee9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008614d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085d97`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085ee9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008614d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085d04`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085e8e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180086059`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085d04`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085e8e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180086059`

## string_xrefs

- `0x180085fae`: `uploadcompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall COCATpTransport::UploadToAzure(
        COCATpTransport *this,
        struct CReportCabStream *a2,
        wchar_t *a3,
        const wchar_t *a4)
{
  struct IWerByteStream *v4; // r14
  BOOL v6; // r15d
  __int64 v7; // rcx
  CResponse *v8; // rsi
  unsigned int v9; // r13d
  int v10; // r12d
  const wchar_t *v11; // rbx
  _WORD *v12; // rcx
  wchar_t *v13; // rax
  unsigned __int64 v14; // rax
  int v15; // eax
  int BlockIdFromString; // ebx
  __int64 v17; // rax
  void *v18; // r14
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rbx
  unsigned __int64 v21; // rax
  int v22; // eax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // esi
  struct ITpCallbacks *v27; // r15
  __int64 v28; // r8
  CTransport *v29; // rcx
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  int v33; // eax
  wchar_t *v34; // rcx
  int v36; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v41; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v42[2]; // [rsp+98h] [rbp-70h] BYREF
  _WORD v43[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+C0h] [rbp-48h] BYREF
  struct ITpCallbacks *v46; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *v47; // [rsp+D0h] [rbp-38h] BYREF
  wchar_t *v48; // [rsp+D8h] [rbp-30h]
  _WORD v49[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v50[8]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-10h]
  __int64 v52; // [rsp+100h] [rbp-8h]
  _BYTE v53[880]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v54[944]; // [rsp+488h] [rbp+380h] BYREF
  int v55; // [rsp+848h] [rbp+740h] BYREF
  struct IWerByteStream *v56; // [rsp+850h] [rbp+748h] BYREF
  wchar_t *v57; // [rsp+858h] [rbp+750h]
  __int64 v58; // [rsp+860h] [rbp+758h]

  v58 = (__int64)a4;
  v57 = a3;
  v56 = a2;
  v4 = a2;
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v54);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v50);
  v6 = 0;
  v55 = 0;
  v40 = 0;
  v7 = *((_QWORD *)this + 6);
  v8 = (CResponse *)(v7 + 8);
  LODWORD(v44) = CRegSetting::GetDwordData((CRegSetting *)(v7 + 51472));
  v9 = 0;
  v47 = v49;
  v48 = v49;
  v49[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &v47,
                           *(_QWORD *)v8)
    && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 2147942414LL);
  }
  v10 = 0;
  if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
    && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
  {
    v10 = 2;
  }
  while ( 1 )
  {
    v11 = L"zip";
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, ++v9);
    CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v53);
    CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v42);
    v12 = *(_WORD **)(*((_QWORD *)this + 6) + 6568LL);
    if ( !v12 || (v13 = L"renewsas", !*v12) )
      v13 = L"getdestination";
    v41 = v13;
    if ( !*((_DWORD *)v4 + 4) )
      v11 = L"cab";
    v14 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 0);
    v15 = COCATpTransport::PrepareResumableUploadRequest(this, v57, v14, v11, v41, (struct CTpRequestMessage *)v53);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 77;
      goto LABEL_116;
    }
    v17 = *((_QWORD *)this + 6);
    v18 = *(void **)(v17 + 52056);
    if ( v18 )
    {
      v6 = ImpersonateLoggedOnUser(*(HANDLE *)(v17 + 52056));
      v55 = v6;
    }
    v46 = (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v53,
                          v46,
                          v10,
                          0,
                          (__int64)v18,
                          *((_QWORD *)this + 5),
                          (__int64)this + 192,
                          (__int64)v41,
                          0,
                          v58,
                          (__int64)&httpTimeoutsLongerReceiveTimeout,
                          0);
    if ( v6 )
    {
      RevertToSelf();
      v6 = 0;
      v55 = 0;
    }
    if ( BlockIdFromString < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 78;
      goto LABEL_78;
    }
    v15 = COCATpTransport::ParseResumableUploadResponse(this, (struct CTpResponseMessage *)v42);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 79;
LABEL_116:
      v32 = (unsigned int)v15;
LABEL_117:
      WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v32);
LABEL_118:
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_119;
    }
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v8, L"REJECTED_BY_RULE") )
    {
      if ( v47 != v48 )
      {
        v33 = CResponse::SetBucketId(v8, v47);
        if ( v33 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
            goto LABEL_101;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
            (unsigned int)v33);
        }
      }
      v34 = WPP_GLOBAL_Control;
LABEL_101:
      BlockIdFromString = 1769483;
      if ( v34 != (wchar_t *)&WPP_GLOBAL_Control && (v34[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v34 + 2), 81, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 1769483);
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_105;
    }
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v8, L"INVALID_REQUEST") )
    {
      BlockIdFromString = -2147024883;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 2147942413LL);
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_120;
    }
    v15 = COCATpTransport::SaveResumeState(this, v57);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 83;
        goto LABEL_116;
      }
      goto LABEL_118;
    }
    BlockIdFromString = COCAReply::SaveToReport((COCATpTransport *)((char *)this + 56), *((struct CReport **)this + 6));
    if ( BlockIdFromString < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
      goto LABEL_118;
    }
    v19 = (const wchar_t *)*((_QWORD *)v8 + 52);
    if ( !v19 || !*v19 )
    {
      v32 = 2147942413LL;
      BlockIdFromString = -2147024883;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 85;
        goto LABEL_117;
      }
      goto LABEL_118;
    }
    v15 = CReport::SetCabUrl(*((CReport **)this + 6), v19);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 86;
        goto LABEL_116;
      }
      goto LABEL_118;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) = *((_QWORD *)v8 + 64);
    BlockIdFromString = CTpAzureStorageTransport::GetBlockIdFromString(*((const wchar_t **)v8 + 65), &v40);
    if ( BlockIdFromString < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 87;
LABEL_78:
      v32 = (unsigned int)BlockIdFromString;
      goto LABEL_117;
    }
    v45 = 0;
    if ( v18 )
    {
      v6 = ImpersonateLoggedOnUser(v18);
      v55 = v6;
    }
    BlockIdFromString = CTpAzureStorageTransport::UploadFileToAzureUsingSAS(
                          *((LPCWSTR *)v8 + 52),
                          v10,
                          v56,
                          *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL),
                          *((void **)this + 5),
                          &v40,
                          &v45,
                          v46);
    if ( v6 )
    {
      RevertToSelf();
      v6 = 0;
      v55 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 6) + 6552LL) = v40;
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) += v45;
    COCATpTransport::LogAzureExchangeEvent(this, BlockIdFromString);
    if ( BlockIdFromString < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)BlockIdFromString);
      if ( BlockIdFromString != -2145844845 || v9 >= (unsigned int)v44 )
      {
        CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
        CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
        goto LABEL_119;
      }
    }
    CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
    CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
    if ( BlockIdFromString != -2145844845 || v9 >= (unsigned int)v44 )
      break;
    v4 = v56;
  }
  v41 = (wchar_t *)L"uploadcompleted";
  v20 = L"zip";
  if ( !*((_DWORD *)v56 + 4) )
    v20 = L"cab";
  v21 = (*(__int64 (**)(void))(*(_QWORD *)v56 + 32LL))();
  v22 = COCATpTransport::PrepareResumableUploadRequest(
          this,
          v57,
          v21,
          v20,
          L"uploadcompleted",
          (struct CTpRequestMessage *)v54);
  BlockIdFromString = v22;
  if ( v22 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_119;
    v24 = 89;
LABEL_52:
    v25 = (unsigned int)v22;
    goto LABEL_53;
  }
  v26 = 3;
  if ( v18 )
    v55 = ImpersonateLoggedOnUser(v18);
  v27 = v46;
  while ( 2 )
  {
    --v26;
    v28 = v52;
    v52 = v51;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CTpResponseSection,utl::default_delete<CTpResponseSection>>>>(
      v23,
      v51,
      (v28 - v51) >> 3);
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v54,
                          v27,
                          v10,
                          0,
                          (__int64)v18,
                          *((_QWORD *)this + 5),
                          (__int64)this + 192,
                          (__int64)L"uploadcompleted",
                          0,
                          v58,
                          (__int64)&httpTimeoutsLongerReceiveTimeout,
                          0);
    if ( BlockIdFromString >= 0 )
    {
LABEL_61:
      v29 = (CTransport *)WPP_GLOBAL_Control;
    }
    else
    {
      v29 = (CTransport *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)(3 - v26),
          BlockIdFromString);
        goto LABEL_61;
      }
    }
    if ( (unsigned int)CTransport::ShouldRetryExchange(v29, BlockIdFromString) && v26 )
      continue;
    break;
  }
  if ( v55 )
  {
    RevertToSelf();
    v23 = WPP_GLOBAL_Control;
  }
  if ( BlockIdFromString < 0 )
  {
    if ( v23 != (wchar_t *)&WPP_GLOBAL_Control && (v23[14] & 1) != 0 )
    {
      v24 = 91;
      v25 = (unsigned int)BlockIdFromString;
LABEL_53:
      WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v25);
    }
    goto LABEL_119;
  }
  v22 = COCATpTransport::ParseResumableUploadResponse(this, (struct CTpResponseMessage *)v50);
  BlockIdFromString = v22;
  if ( v22 >= 0 )
  {
    CTransport::EventCabUploadComplete(this, v22);
    goto LABEL_119;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v24 = 92;
    goto LABEL_52;
  }
LABEL_119:
  if ( BlockIdFromString >= 0 )
  {
LABEL_105:
    CReport::SetCabUrl(*((CReport **)this + 6), 0);
    goto LABEL_106;
  }
LABEL_120:
  v36 = COCATpTransport::SaveResumeState(this, v57);
  if ( v36 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
      (unsigned int)v36);
  v42[0] = v43;
  v42[1] = v43;
  v43[0] = 0;
  if ( (int)CReport::GetUniqueIdentifier(*((_QWORD *)this + 6), v42) < 0 )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      v42,
      L"{00000000-0000-0000-0000-000000000000}");
  if ( (unsigned int)dword_1800D8000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 0x400000000000LL) )
  {
    LODWORD(v56) = BlockIdFromString;
    v55 = *((_DWORD *)this + 88);
    v46 = (struct ITpCallbacks *)L"OCA";
    v45 = v42[0];
    v44 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)&dword_1800C82AC,
      v38,
      v39,
      (__int64)&v44,
      (__int64)&v41,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v55,
      (__int64)&v56);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
LABEL_106:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v47);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v50);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v54);
  return (unsigned int)BlockIdFromString;
}

```

## disassembly

```asm
0x180085b38  mov     rax, rsp
0x180085b3b  mov     [rax+20h], r9
0x180085b3f  mov     [rax+18h], r8
0x180085b43  mov     [rax+10h], rdx
0x180085b47  push    rbp
0x180085b48  push    rbx
0x180085b49  push    rsi
0x180085b4a  push    rdi
0x180085b4b  push    r12
0x180085b4d  push    r13
0x180085b4f  push    r14
0x180085b51  push    r15
0x180085b53  lea     rbp, [rax-738h]
0x180085b5a  sub     rsp, 7F8h
0x180085b61  mov     r14, rdx
0x180085b64  mov     rdi, rcx
0x180085b67  lea     rcx, [rbp+730h+var_3B0]; this
0x180085b6e  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180085b73  nop
0x180085b74  lea     rcx, [rbp+730h+var_748]; this
0x180085b78  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180085b7d  nop
0x180085b7e  xor     ebx, ebx
0x180085b80  mov     r15d, ebx
0x180085b83  mov     [rbp+730h+arg_0], ebx
0x180085b89  mov     [rbp+730h+var_7B0], ebx
0x180085b8c  mov     rcx, [rdi+30h]
0x180085b90  lea     rsi, [rcx+8]
0x180085b94  add     rcx, 0C910h; this
0x180085b9b  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180085ba0  mov     dword ptr [rbp+730h+var_780], eax
0x180085ba3  mov     r13d, ebx
0x180085ba6  lea     rax, [rbp+730h+var_758]
0x180085baa  mov     [rbp+730h+var_768], rax
0x180085bae  lea     rax, [rbp+730h+var_758]
0x180085bb2  mov     [rbp+730h+var_760], rax
0x180085bb6  mov     [rbp+730h+var_758], bx
0x180085bba  mov     rdx, [rsi]
0x180085bbd  lea     rcx, [rbp+730h+var_768]
0x180085bc1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180085bc6  lea     rdx, WPP_GLOBAL_Control
0x180085bcd  test    al, al
0x180085bcf  jnz     short loc_180085BFC
0x180085bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180085bd8  cmp     rcx, rdx
0x180085bdb  jz      short loc_180085BFC
0x180085bdd  test    byte ptr [rcx+1Ch], 2
0x180085be1  jz      short loc_180085BFC
0x180085be3  lea     edx, [rbx+4Bh]
0x180085be6  mov     r9d, 8007000Eh
0x180085bec  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085bf3  mov     rcx, [rcx+10h]
0x180085bf7  call    WPP_SF_d
0x180085bfc  mov     r12d, ebx
0x180085bff  mov     rcx, [rdi+30h]
0x180085c03  add     rcx, 0B660h; this
0x180085c0a  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x180085c0f  test    eax, eax
0x180085c11  jz      short loc_180085C27
0x180085c13  mov     rcx, [rdi+30h]; this
0x180085c17  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180085c1c  test    eax, eax
0x180085c1e  mov     eax, 2
0x180085c23  cmovz   r12d, eax
0x180085c27  lea     rbx, aZip_0; "zip"
0x180085c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180085c35  lea     rax, WPP_GLOBAL_Control
0x180085c3c  cmp     rcx, rax
0x180085c3f  jz      short loc_180085C62
0x180085c41  test    byte ptr [rcx+1Ch], 4
0x180085c45  jz      short loc_180085C62
0x180085c47  inc     r13d
0x180085c4a  mov     edx, 4Ch ; 'L'
0x180085c4f  mov     r9d, r13d
0x180085c52  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085c59  mov     rcx, [rcx+10h]
0x180085c5d  call    WPP_SF_d
0x180085c62  lea     rcx, [rbp+730h+var_720]; this
0x180085c66  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180085c6b  nop
0x180085c6c  lea     rcx, [rbp+730h+var_7A0]; this
0x180085c70  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180085c75  nop
0x180085c76  mov     rax, [rdi+30h]
0x180085c7a  mov     rcx, [rax+19A8h]
0x180085c81  xor     edx, edx
0x180085c83  test    rcx, rcx
0x180085c86  jz      short loc_180085C94
0x180085c88  cmp     [rcx], dx
0x180085c8b  lea     rax, aRenewsas; "renewsas"
0x180085c92  jnz     short loc_180085C9B
0x180085c94  lea     rax, aGetdestination; "getdestination"
0x180085c9b  mov     [rbp+730h+var_7A8], rax
0x180085c9f  cmp     [r14+10h], edx
0x180085ca3  lea     rax, aCab_1; "cab"
0x180085caa  cmovz   rbx, rax
0x180085cae  mov     rax, [r14]
0x180085cb1  mov     rcx, r14
0x180085cb4  mov     rax, [rax+20h]
0x180085cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085cbd  lea     rcx, [rbp+730h+var_720]
0x180085cc1  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x180085cc6  mov     rcx, [rbp+730h+var_7A8]
0x180085cca  mov     [rsp+830h+var_810], rcx; wchar_t *
0x180085ccf  mov     r9, rbx; wchar_t *
0x180085cd2  mov     r8, rax; unsigned __int64
0x180085cd5  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180085cdc  mov     rcx, rdi; this
0x180085cdf  call    ?PrepareResumableUploadRequest@COCATpTransport@@IEAAJPEB_W_K00PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareResumableUploadRequest(wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CTpRequestMessage *)
0x180085ce4  mov     ebx, eax
0x180085ce6  xor     r9d, r9d
0x180085ce9  test    eax, eax
0x180085ceb  js      loc_18008642A
0x180085cf1  mov     rax, [rdi+30h]
0x180085cf5  mov     r14, [rax+0CB58h]
0x180085cfc  test    r14, r14
0x180085cff  jz      short loc_180085D16
0x180085d01  mov     rcx, r14; hToken
0x180085d04  call    cs:__imp_ImpersonateLoggedOnUser
0x180085d0a  mov     r15d, eax
0x180085d0d  mov     [rbp+730h+arg_0], eax
0x180085d13  xor     r9d, r9d
0x180085d16  lea     r8, [rdi+0C0h]
0x180085d1d  mov     rcx, rdi
0x180085d20  lea     rdx, [rdi+20h]
0x180085d24  neg     rcx
0x180085d27  sbb     rcx, rcx
0x180085d2a  and     rcx, rdx
0x180085d2d  mov     [rbp+730h+var_770], rcx
0x180085d31  mov     [rsp+70h], r9d; int
0x180085d36  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180085d3d  mov     [rsp+830h+var_7C8], rax; __int64
0x180085d42  mov     rax, [rbp+730h+arg_18]
0x180085d49  mov     [rsp+830h+var_7D0], rax; __int64
0x180085d4e  mov     qword ptr [rsp+830h+var_7D8], r9; int
0x180085d53  mov     rax, [rbp+730h+var_7A8]
0x180085d57  mov     [rsp+830h+var_7E0], rax; __int64
0x180085d5c  mov     [rsp+830h+var_7E8], r8; __int64
0x180085d61  mov     rax, [rdi+28h]
0x180085d65  mov     [rsp+830h+var_7F0], rax; __int64
0x180085d6a  mov     [rsp+830h+var_7F8], r14; __int64
0x180085d6f  mov     [rsp+830h+var_800], r9; int
0x180085d74  mov     dword ptr [rsp+830h+var_808], r12d; int
0x180085d79  mov     [rsp+830h+var_810], rcx; struct ITpCallbacks *
0x180085d7e  xor     r9d, r9d
0x180085d81  lea     r8, [rbp+730h+var_7A0]
0x180085d85  xor     edx, edx
0x180085d87  lea     rcx, [rbp+730h+var_720]; this
0x180085d8b  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180085d90  mov     ebx, eax
0x180085d92  test    r15d, r15d
0x180085d95  jz      short loc_180085DA8
0x180085d97  call    cs:__imp_RevertToSelf
0x180085d9d  xor     eax, eax
0x180085d9f  mov     r15d, eax
0x180085da2  mov     [rbp+730h+arg_0], eax
0x180085da8  test    ebx, ebx
0x180085daa  js      loc_180086407
0x180085db0  lea     rdx, [rbp+730h+var_7A0]; struct CTpResponseMessage *
0x180085db4  mov     rcx, rdi; this
0x180085db7  call    ?ParseResumableUploadResponse@COCATpTransport@@IEAAJPEAVCTpResponseMessage@@@Z; COCATpTransport::ParseResumableUploadResponse(CTpResponseMessage *)
0x180085dbc  mov     ebx, eax
0x180085dbe  test    eax, eax
0x180085dc0  js      loc_1800863E7
0x180085dc6  lea     rdx, aRejectedByRule; "REJECTED_BY_RULE"
0x180085dcd  mov     rcx, [rsi]
0x180085dd0  call    cs:__imp__o__wcsicmp
0x180085dd6  test    eax, eax
0x180085dd8  jz      loc_180086314
0x180085dde  lea     rdx, aInvalidRequest; "INVALID_REQUEST"
0x180085de5  mov     rcx, [rsi]
0x180085de8  call    cs:__imp__o__wcsicmp
0x180085dee  test    eax, eax
0x180085df0  jz      loc_1800862C4
0x180085df6  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180085dfd  mov     rcx, rdi; this
0x180085e00  call    ?SaveResumeState@COCATpTransport@@IEAAJPEB_W@Z; COCATpTransport::SaveResumeState(wchar_t const *)
0x180085e05  mov     ebx, eax
0x180085e07  test    eax, eax
0x180085e09  js      loc_180086299
0x180085e0f  lea     rcx, [rdi+38h]; this
0x180085e13  mov     rdx, [rdi+30h]; struct CReport *
0x180085e17  call    ?SaveToReport@COCAReply@@QEAAJPEAVCReport@@@Z; COCAReply::SaveToReport(CReport *)
0x180085e1c  mov     ebx, eax
0x180085e1e  xor     eax, eax
0x180085e20  test    ebx, ebx
0x180085e22  js      loc_18008625E
0x180085e28  mov     rdx, [rsi+1A0h]; wchar_t *
0x180085e2f  test    rdx, rdx
0x180085e32  jz      loc_18008622A
0x180085e38  cmp     [rdx], ax
0x180085e3b  jz      loc_18008622A
0x180085e41  mov     rcx, [rdi+30h]; this
0x180085e45  call    ?SetCabUrl@CReport@@QEAAJPEB_W@Z; CReport::SetCabUrl(wchar_t const *)
0x180085e4a  mov     ebx, eax
0x180085e4c  test    eax, eax
0x180085e4e  js      loc_1800861FF
0x180085e54  mov     rcx, [rdi+30h]
0x180085e58  mov     rax, [rsi+200h]
0x180085e5f  mov     [rcx+19A0h], rax
0x180085e66  lea     rdx, [rbp+730h+var_7B0]; unsigned int *
0x180085e6a  mov     rcx, [rsi+208h]; wchar_t *
0x180085e71  call    ?GetBlockIdFromString@CTpAzureStorageTransport@@SAJPEB_WAEAK@Z; CTpAzureStorageTransport::GetBlockIdFromString(wchar_t const *,ulong &)
0x180085e76  mov     ebx, eax
0x180085e78  xor     eax, eax
0x180085e7a  test    ebx, ebx
0x180085e7c  js      loc_1800861D1
0x180085e82  mov     [rbp+730h+var_778], rax
0x180085e86  test    r14, r14
0x180085e89  jz      short loc_180085E9D
0x180085e8b  mov     rcx, r14; hToken
0x180085e8e  call    cs:__imp_ImpersonateLoggedOnUser
0x180085e94  mov     r15d, eax
0x180085e97  mov     [rbp+730h+arg_0], eax
0x180085e9d  mov     r9, [rdi+30h]
0x180085ea1  mov     rax, [rbp+730h+var_770]
0x180085ea5  mov     [rsp+830h+var_7F8], rax; struct ITpCallbacks *
0x180085eaa  lea     rax, [rbp+730h+var_778]
0x180085eae  mov     [rsp+830h+var_800], rax; unsigned __int64 *
0x180085eb3  lea     rax, [rbp+730h+var_7B0]
0x180085eb7  mov     [rsp+830h+var_808], rax; unsigned int *
0x180085ebc  mov     rax, [rdi+28h]
0x180085ec0  mov     [rsp+830h+var_810], rax; void *
0x180085ec5  mov     r9, [r9+19A0h]; unsigned __int64
0x180085ecc  mov     r8, [rbp+730h+arg_8]; struct IWerByteStream *
0x180085ed3  mov     edx, r12d; unsigned int
0x180085ed6  mov     rcx, [rsi+1A0h]; pwszUrl
0x180085edd  call    ?UploadFileToAzureUsingSAS@CTpAzureStorageTransport@@SAJPEB_WKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z; CTpAzureStorageTransport::UploadFileToAzureUsingSAS(wchar_t const *,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)
0x180085ee2  mov     ebx, eax
0x180085ee4  test    r15d, r15d
0x180085ee7  jz      short loc_180085EF9
0x180085ee9  call    cs:__imp_RevertToSelf
0x180085eef  xor     r15d, r15d
0x180085ef2  mov     [rbp+730h+arg_0], r15d
0x180085ef9  mov     rcx, [rdi+30h]
0x180085efd  mov     eax, [rbp+730h+var_7B0]
0x180085f00  mov     [rcx+1998h], eax
0x180085f06  mov     rcx, [rdi+30h]
0x180085f0a  mov     rax, [rbp+730h+var_778]
0x180085f0e  add     [rcx+19A0h], rax
0x180085f15  mov     edx, ebx; int
0x180085f17  mov     rcx, rdi; this
0x180085f1a  call    ?LogAzureExchangeEvent@COCATpTransport@@IEBAXJ@Z; COCATpTransport::LogAzureExchangeEvent(long)
0x180085f1f  test    ebx, ebx
0x180085f21  jns     short loc_180085F62
0x180085f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180085f2a  lea     rax, WPP_GLOBAL_Control
0x180085f31  cmp     rcx, rax
0x180085f34  jz      short loc_180085F54
0x180085f36  test    byte ptr [rcx+1Ch], 1
0x180085f3a  jz      short loc_180085F54
0x180085f3c  mov     edx, 58h ; 'X'
0x180085f41  mov     r9d, ebx
0x180085f44  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085f4b  mov     rcx, [rcx+10h]
0x180085f4f  call    WPP_SF_d
0x180085f54  cmp     ebx, 80190193h
0x180085f5a  jnz     short loc_180085F8F
0x180085f5c  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180085f60  jnb     short loc_180085F8F
0x180085f62  lea     rcx, [rbp+730h+var_7A0]; this
0x180085f66  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180085f6b  nop
0x180085f6c  lea     rcx, [rbp+730h+var_720]; this
0x180085f70  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180085f75  cmp     ebx, 80190193h
0x180085f7b  jnz     short loc_180085FAE
0x180085f7d  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180085f81  jnb     short loc_180085FAE
0x180085f83  mov     r14, [rbp+730h+arg_8]
0x180085f8a  jmp     loc_180085C27
0x180085f8f  lea     rcx, [rbp+730h+var_7A0]; this
0x180085f93  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180085f98  nop
0x180085f99  lea     rcx, [rbp+730h+var_720]; this
0x180085f9d  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180085fa2  lea     rsi, WPP_GLOBAL_Control
0x180085fa9  jmp     loc_18008646F
0x180085fae  lea     r13, aUploadcomplete; "uploadcompleted"
0x180085fb5  mov     [rbp+730h+var_7A8], r13
0x180085fb9  mov     rcx, [rbp+730h+arg_8]
0x180085fc0  cmp     dword ptr [rcx+10h], 0
0x180085fc4  lea     rbx, aZip_0; "zip"
0x180085fcb  lea     rax, aCab_1; "cab"
0x180085fd2  cmovz   rbx, rax
0x180085fd6  mov     rax, [rcx]
0x180085fd9  mov     rax, [rax+20h]
0x180085fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fe2  lea     rcx, [rbp+730h+var_3B0]
0x180085fe9  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x180085fee  mov     [rsp+830h+var_810], r13; wchar_t *
0x180085ff3  mov     r9, rbx; wchar_t *
0x180085ff6  mov     r8, rax; unsigned __int64
0x180085ff9  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180086000  mov     rcx, rdi; this
0x180086003  call    ?PrepareResumableUploadRequest@COCATpTransport@@IEAAJPEB_W_K00PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareResumableUploadRequest(wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CTpRequestMessage *)
0x180086008  mov     ebx, eax
0x18008600a  test    eax, eax
0x18008600c  jns     short loc_18008604C
0x18008600e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
