# ApplyMinimizeDestinationsPolicyFilter(std::vector<std::shared_ptr<WCM_CANDIDATE>,std::allocator<std::shared_ptr<WCM_CANDIDATE>>> const &,std::vector<std::shared_ptr<WCM_CANDIDATE>,std::allocator<std::shared_ptr<WCM_CANDIDATE>>> const &)

- ea: `0x1800188cc`
- end: `0x18001942b`
- name: `?ApplyMinimizeDestinationsPolicyFilter@@YAXAEBV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@0@Z`
- size: `2911`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001716c`

## callees

- `0x180010080`
- `0x180011bb0`
- `0x180011c20`
- `0x180017110`
- `0x1800188cc`
- `0x180019434`
- `0x18001efec`
- `0x180031f44`
- `0x180037c80`
- `0x18003a628`
- `0x18003cf28`
- `0x18003feec`
- `0x18004187c`
- `0x18004cdd8`
- `0x18004df8c`
- `0x180084f50`

## string_xrefs

- `0x180018b84`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180018f66`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180018fe0`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x18001905e`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180019164`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x1800191d8`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x18001924c`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x1800192b2`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180019327`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180019386`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x1800193ed`: `onecoreuap\net\wcm\service\base\tokenmanager\lib\tokenmanager.cpp`
- `0x180018b79`: `TokenManager is removing all tokens because the power policy dictate everything must disconnect`
- `0x180018d0d`: `Minimize: Drop, MC token already revoked`
- `0x180018ceb`: `Minimize: Drop, AC token already revoked and not manually connected`
- `0x180018ccc`: `Minimize: Keep, earlier Wi-Fi was already preferred`
- `0x180018f5b`: `TokenManager is not disconnecting this interface - device is in low power`
- `0x180018fd5`: `TokenManager is removing AC token because the interface was manually connected`
- `0x180018f91`: `Minimize: Not changing token while the device is in low power`
- `0x1800191cd`: `TokenManager is disconnecting, not initiating soft-disconnect - NLA probe is not yet completed`
- `0x180019192`: `Minimize: Cleared AC token, won't initiate soft disconnect when not in a good state`
- `0x180019241`: `TokenManager is disconnecting, not initiating soft-disconnect - soft disconnect is not enabled`
- `0x180019206`: `Minimize: Cleared AC token, won't initiate soft disconnect when NLA probe is not yet completed`
- `0x180019053`: `TokenManager is disconnecting because soft-disconnect completed`
- `0x18001901f`: `Minimize: Cleared AC token, won't initiate soft disconnect manually connected`
- `0x180019159`: `TokenManager is disconnecting, not initiating soft-disconnect - not in a good state`
- `0x1800190aa`: `Minimize: Cleared AC token, won't initiate soft disconnect because soft disconnect complete`
- `0x18001937b`: `TokenManager is initiating soft-disconnect`
- `0x180019355`: `Minimize: Cleared AC token, won't initiate soft disconnect on cellular`
- `0x1800193e2`: `TokenManager is not initiating soft-disconnect - AC token was not previously given to this profile`
- `0x1800193b4`: `Minimize: Soft disconnecting, as it is an Internet-connected, auto-connected interface, and NLA probes have completed`
- `0x1800192a7`: `TokenManager is disconnecting, not initiating soft-disconnect - AC token was not previously given to this profile`
- `0x18001927a`: `Minimize: Cleared AC token, won't initiate soft disconnect when soft disconnect is not enabled`
- `0x18001931c`: `TokenManager is disconnecting, not initiating soft-disconnect - cellular must be immediately disconnected`
- `0x1800192e0`: `Minimize: Cleared AC token, won't initiate soft disconnect when AC token was not previously given`

## pseudocode

```c
void __fastcall ApplyMinimizeDestinationsPolicyFilter(__int64 a1, _QWORD *a2)
{
  char v3; // si
  __int64 v4; // rcx
  ConfigManager *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rcx
  int v8; // edx
  std::_Ref_count_base *v9; // rax
  char v10; // r13
  const struct _GUID **v11; // rbx
  const struct _GUID *v12; // r9
  int v13; // edi
  unsigned __int8 *v14; // rax
  char v15; // r15
  int v16; // edx
  int *p_Data2; // rax
  bool ShouldForceDisconnectInStandby; // cl
  const struct _GUID *v19; // rax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  char v23; // r14
  char v24; // di
  const struct _GUID *v25; // r9
  int *v26; // rax
  int v27; // edx
  const wchar_t *v28; // rcx
  const struct _GUID *v29; // r8
  unsigned int Data1; // ecx
  const wchar_t *v31; // rcx
  const wchar_t *v32; // rcx
  char v33; // di
  __int64 v34; // rcx
  _QWORD *v35; // r8
  const struct _GUID *v36; // r9
  bool IsInterfaceInGoodState; // r10
  _QWORD *v38; // rdx
  char v39; // dl
  const struct _GUID *v40; // r8
  int v41; // eax
  int v42; // r8d
  int v43; // r9d
  int v44; // r8d
  int v45; // r9d
  int v46; // r8d
  int v47; // r9d
  unsigned int v48; // edx
  int v49; // r8d
  int v50; // r9d
  unsigned int v51; // edx
  char v52; // [rsp+50h] [rbp-39h]
  char v53; // [rsp+51h] [rbp-38h]
  char v54; // [rsp+52h] [rbp-37h]
  char v55; // [rsp+53h] [rbp-36h]
  const char *v56; // [rsp+58h] [rbp-31h] BYREF
  const char *v57; // [rsp+60h] [rbp-29h] BYREF
  char v58; // [rsp+68h] [rbp-21h]
  const struct _GUID *v59; // [rsp+70h] [rbp-19h] BYREF
  bool v60; // [rsp+78h] [rbp-11h]
  _QWORD *v61; // [rsp+80h] [rbp-9h]
  __int64 v62; // [rsp+88h] [rbp-1h] BYREF
  std::_Ref_count_base *v63[2]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v64; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v65; // [rsp+A8h] [rbp+1Fh] BYREF

  v61 = a2;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      73,
      &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
      "ApplyMinimizeDestinationsPolicyFilter");
  }
  v3 = 0;
  v62 = 2;
  v65 = 0;
  v64 = 0;
  v57 = 0;
  ConfigManager::GetCdePolicies(
    (struct WCM_POLICY_VALUE_INTERNAL *)&v62,
    (struct WCM_POLICY_VALUE_INTERNAL *)&v65,
    (struct WCM_POLICY_VALUE_INTERNAL *)&v64,
    (struct WCM_POLICY_VALUE_INTERNAL *)&v57);
  v56 = (const char *)1;
  *(_OWORD *)v63 = 0;
  std::weak_ptr<ConfigManager>::lock(v4, v63);
  if ( v63[0] )
  {
    ConfigManager::InternalGetSoftDisconnectPolicy(v5, (struct WCM_POLICY_VALUE_INTERNAL *)&v56);
    v6 = v63[1];
    if ( !v63[1] )
      goto LABEL_10;
    goto LABEL_9;
  }
  v6 = v63[1];
  if ( v63[1] )
  {
LABEL_9:
    std::_Ref_count_base::_Decref(v6);
LABEL_10:
    v55 = 0;
    if ( !(_DWORD)v56 )
      goto LABEL_12;
  }
  v55 = 1;
LABEL_12:
  if ( (_DWORD)v57 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 5u && (*(_BYTE *)(v7 + 28) & 1) != 0 )
      {
        v8 = 75;
LABEL_53:
        WPP_SF_sL(
          *(_QWORD *)(v7 + 16),
          v8,
          (unsigned int)&WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
          (unsigned int)"ApplyMinimizeDestinationsPolicyFilter",
          0);
        return;
      }
    }
    return;
  }
  v60 = dword_18013F3E8 != 0;
  if ( (_DWORD)v62 )
  {
    v9 = *(std::_Ref_count_base **)(a1 + 8);
    v10 = 0;
    v11 = *(const struct _GUID ***)a1;
    v7 = WPP_GLOBAL_Control;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v58 = 0;
    v63[0] = v9;
    if ( v11 == (const struct _GUID **)v9 )
    {
LABEL_49:
      if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 5u && (*(_BYTE *)(v7 + 28) & 1) != 0 )
      {
        v8 = 81;
        goto LABEL_53;
      }
      return;
    }
    while ( 1 )
    {
      v12 = *v11;
      v13 = *(_DWORD *)&(*v11)[2].Data2;
      v14 = &(*v11)[2].Data4[4];
      if ( v13 == 4 && (*v14 & 4) != 0 )
        break;
      if ( v13 != 1 )
        goto LABEL_34;
      v3 = 0;
      if ( (*v14 & 4) == 0 )
        goto LABEL_34;
      v15 = 1;
LABEL_35:
      if ( (*(_DWORD *)v12[2].Data4 & 0x1000) != 0 )
        goto LABEL_47;
      if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 4u && (*(_BYTE *)(v7 + 28) & 1) != 0 )
      {
        v16 = *(_DWORD *)v14;
        p_Data2 = (int *)&v12[3].Data2;
        if ( (v16 & 1) == 0 )
          p_Data2 = &dword_180103494;
        WPP_SF__guid_SdDDDD(
          *(_QWORD *)(v7 + 16),
          (__int64)p_Data2,
          v12[2].Data1,
          v13,
          v16,
          v12[36].Data1,
          *(_DWORD *)v12[2].Data4);
      }
      ShouldForceDisconnectInStandby = PdcManager::ShouldForceDisconnectInStandby((PdcManager *)v7);
      v19 = *v11;
      if ( (*v11)[2].Data1 != 3 && ShouldForceDisconnectInStandby )
      {
        LogCandidate(L"Minimize: power policies blocking candidate", v11);
        if ( (unsigned int)dword_18013A120 > 5 )
        {
          v57 = (const char *)*v11;
          v56 = "TokenManager is removing all tokens because the power policy dictate everything must disconnect";
          v59 = (const struct _GUID *)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
            v20,
            (unsigned int)byte_18011FA05,
            v21,
            v22,
            (__int64)&v59,
            (__int64)&v56,
            (__int64)&v57);
        }
        TrackInitialTokenRemovalReason(v11, 17);
        *(_DWORD *)(*v11)[2].Data4 &= ~2u;
        *(_DWORD *)(*v11)[2].Data4 &= ~4u;
        v7 = WPP_GLOBAL_Control;
LABEL_47:
        v3 = 0;
        goto LABEL_48;
      }
      if ( v10 )
      {
        v23 = 0;
      }
      else
      {
        v23 = 1;
        LogCandidate(L"Minimize: Keep, no Internet candidate found yet", v11);
        v19 = *v11;
      }
      if ( !v52 && (v19[36].Data1 & 0x30) == 0x30 )
      {
        v23 = 1;
        LogCandidate(L"Minimize: Keep, no domain candidate found yet", v11);
      }
      if ( v3 )
      {
        v24 = 1;
        LogCandidate(L"Minimize: Keep, manually connected", v11);
      }
      else
      {
        v24 = v23;
      }
      if ( v58 && (*v11)[2].Data1 == 2 )
      {
        v24 = 1;
        LogCandidate(L"Minimize: Keep, earlier Wi-Fi was already preferred", v11);
      }
      if ( ((*v11)[2].Data4[0] & 2) != 0 || v3 )
      {
        v3 = 0;
      }
      else
      {
        v3 = 0;
        v24 = 0;
        LogCandidate(L"Minimize: Drop, AC token already revoked and not manually connected", v11);
      }
      if ( ((*v11)[2].Data4[0] & 4) == 0 )
      {
        v24 = 0;
        LogCandidate(L"Minimize: Drop, MC token already revoked", v11);
      }
      if ( v15 )
      {
        LogCandidate(L"Minimize: Drop, manually disconnected", v11);
      }
      else if ( v24 )
      {
        LogCandidate(L"Minimize: Connection desired for candidate", v11);
        if ( (_DWORD)v62 == 3 && *(_DWORD *)&(*v11)[2].Data2 == 4 && (*v11)[2].Data1 == 1 )
        {
          v54 = 1;
          v28 = L"Minimize: [Block Wi-Fi Policy] Found Ethernet connected candidate";
          goto LABEL_103;
        }
        v29 = *v11;
        Data1 = (*v11)[36].Data1;
        if ( ((Data1 & 1) != 0 && (Data1 & 4) != 0 || (Data1 & 0xA) == 0xA) && !v10 )
        {
          if ( *(_DWORD *)&v29[2].Data2 == 4 )
          {
            if ( ((*v11)[36].Data1 & 1) != 0 && (Data1 & 4) != 0 || (Data1 & 0xA) == 0xA || v29[2].Data1 == 1 )
            {
              v54 = 1;
              v28 = L"Minimize: Found Internet connected candidate";
              goto LABEL_103;
            }
LABEL_102:
            v28 = L"Minimize: Found Internet connectable candidate (non Ethernet)";
LABEL_103:
            v10 = 1;
            LogCandidate(v28, v11);
          }
          else if ( v29[2].Data1 != 1 )
          {
            goto LABEL_102;
          }
        }
        if ( ((*v11)[36].Data1 & 0x30) == 0x30 && !v52 )
        {
          v52 = 1;
          if ( *(_DWORD *)&(*v11)[2].Data2 == 4 )
          {
            v53 = 1;
            v31 = L"Minimize: Found domain connected candidate";
          }
          else
          {
            v31 = L"Minimize: Found domain disconnected (connectable) candidate";
          }
          LogCandidate(v31, v11);
        }
        if ( (*v11)[2].Data1 == 2 && v23 && (((_DWORD)v62 - 1) & 0xFFFFFFFD) != 0 )
        {
          v58 = 1;
          v32 = L"Minimize: fWifiPreferredConnectionFound is set with this candidate";
          goto LABEL_179;
        }
        goto LABEL_182;
      }
      if ( (unsigned int)(v62 - 2) <= 1 && (v25 = *v11, (*v11)[2].Data1 == 3) )
      {
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
          goto LABEL_48;
        }
        v26 = (int *)&v25[3].Data2;
        if ( (v25[2].Data4[4] & 1) == 0 )
          v26 = &dword_180103494;
        v27 = 79;
      }
      else
      {
        if ( ((*v11)[36].Data1 & 5) == 5 || (v33 = 0, ((*v11)[36].Data1 & 0xA) == 10 || ((*v11)[36].Data1 & 0x30) == 48) )
          v33 = 1;
        IsInterfaceInGoodState = RouteManager::IsInterfaceInGoodState(*v11);
        v38 = (_QWORD *)*v61;
        if ( *v61 == v61[1] )
        {
LABEL_122:
          LOBYTE(v34) = 0;
        }
        else
        {
          v36 = *v11;
          while ( 1 )
          {
            v35 = (_QWORD *)*v38;
            v34 = *(_QWORD *)&v36->Data1;
            if ( *(_QWORD *)&v36->Data1 == *(_QWORD *)*v38 && *(_QWORD *)v36->Data4 == v35[1] )
              break;
            v38 += 2;
            if ( v38 == (_QWORD *)v61[1] )
              goto LABEL_122;
          }
          LOBYTE(v34) = 1;
        }
        if ( v60 && (_BYTE)v34 )
        {
          if ( (((_DWORD)v62 - 1) & 0xFFFFFFFD) != 0 || (v39 = v53) == 0 )
          {
            if ( (unsigned int)dword_18013A120 > 5 )
            {
              v59 = *v11;
              v57 = "TokenManager is not disconnecting this interface - device is in low power";
              v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                v34,
                (unsigned int)qword_18011FA40,
                (_DWORD)v35,
                (_DWORD)v36,
                (__int64)&v56,
                (__int64)&v57,
                (__int64)&v59);
            }
            v32 = L"Minimize: Not changing token while the device is in low power";
            goto LABEL_179;
          }
        }
        else
        {
          v39 = v53;
        }
        v40 = *v11;
        v41 = *(_DWORD *)(*v11)[2].Data4 & 2;
        if ( ((*v11)[2].Data4[4] & 4) != 0 )
        {
          if ( v41 )
          {
            if ( (unsigned int)dword_18013A120 > 5 )
            {
              v59 = *v11;
              v57 = "TokenManager is removing AC token because the interface was manually connected";
              v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                v34,
                (unsigned int)byte_18011F8A3,
                (_DWORD)v40,
                (_DWORD)v36,
                (__int64)&v56,
                (__int64)&v57,
                (__int64)&v59);
            }
            TrackInitialTokenRemovalReason(v11, 2);
            *(_DWORD *)(*v11)[2].Data4 &= ~2u;
          }
          v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect manually connected";
          goto LABEL_179;
        }
        if ( (v40[2].Data4[0] & 0x20) != 0 )
        {
          if ( v41 )
          {
            if ( (unsigned int)dword_18013A120 > 5 )
            {
              v59 = *v11;
              v57 = "TokenManager is disconnecting because soft-disconnect completed";
              v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                v34,
                (unsigned int)&word_18011F8DE,
                (_DWORD)v40,
                (_DWORD)v36,
                (__int64)&v56,
                (__int64)&v57,
                (__int64)&v59);
            }
            TrackInitialTokenRemovalReason(v11, 4);
            *(_DWORD *)(*v11)[2].Data4 &= ~2u;
          }
          if ( v55 )
            *(_DWORD *)(*v11)[2].Data4 |= 1u;
          v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect because soft disconnect complete";
          goto LABEL_179;
        }
        if ( v54 || v39 )
        {
          if ( v41 )
          {
            if ( IsInterfaceInGoodState )
            {
              if ( v33 )
              {
                if ( v55 )
                {
                  if ( (_BYTE)v34 )
                  {
                    if ( v40[2].Data1 == 3 )
                    {
                      TrackInitialTokenRemovalReason(v11, 5);
                      if ( dword_18013A120 > v51 )
                      {
                        v59 = *v11;
                        v57 = "TokenManager is disconnecting, not initiating soft-disconnect - cellular must be immediately disconnected";
                        v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                          dword_18013A120,
                          (unsigned int)byte_18011F919,
                          v49,
                          v50,
                          (__int64)&v56,
                          (__int64)&v57,
                          (__int64)&v59);
                      }
                      v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect on cellular";
                      *(_DWORD *)(*v11)[2].Data4 &= ~2u;
                    }
                    else
                    {
                      if ( (unsigned int)dword_18013A120 > 5 )
                      {
                        v59 = *v11;
                        v57 = "TokenManager is initiating soft-disconnect";
                        v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                          v34,
                          (unsigned int)&dword_18011F954,
                          (_DWORD)v40,
                          (_DWORD)v36,
                          (__int64)&v56,
                          (__int64)&v57,
                          (__int64)&v59);
                      }
                      v32 = L"Minimize: Soft disconnecting, as it is an Internet-connected, auto-connected interface, and "
                             "NLA probes have completed";
                      *(_DWORD *)(*v11)[2].Data4 |= 1u;
                    }
                  }
                  else
                  {
                    if ( (unsigned int)dword_18013A120 > 5 )
                    {
                      v59 = *v11;
                      v57 = "TokenManager is disconnecting, not initiating soft-disconnect - AC token was not previously "
                            "given to this profile";
                      v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                        v34,
                        (unsigned int)word_18011F9CA,
                        (_DWORD)v40,
                        (_DWORD)v36,
                        (__int64)&v56,
                        (__int64)&v57,
                        (__int64)&v59);
                    }
                    v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect when AC token was not previously given";
                    *(_DWORD *)(*v11)[2].Data4 &= ~2u;
                  }
                }
                else
                {
                  TrackInitialTokenRemovalReason(v11, 5);
                  if ( dword_18013A120 > v48 )
                  {
                    v59 = *v11;
                    v57 = "TokenManager is disconnecting, not initiating soft-disconnect - soft disconnect is not enabled";
                    v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                      dword_18013A120,
                      (unsigned int)&byte_18011F98F,
                      v46,
                      v47,
                      (__int64)&v56,
                      (__int64)&v57,
                      (__int64)&v59);
                  }
                  v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect when soft disconnect is not enabled";
                  *(_DWORD *)(*v11)[2].Data4 &= ~2u;
                }
              }
              else
              {
                TrackInitialTokenRemovalReason(v11, 7);
                if ( (unsigned int)dword_18013A120 > 5 )
                {
                  v59 = *v11;
                  v57 = "TokenManager is disconnecting, not initiating soft-disconnect - NLA probe is not yet completed";
                  v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                    dword_18013A120,
                    (unsigned int)qword_18011F868,
                    v44,
                    v45,
                    (__int64)&v56,
                    (__int64)&v57,
                    (__int64)&v59);
                }
                v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect when NLA probe is not yet completed";
                *(_DWORD *)(*v11)[2].Data4 &= ~2u;
              }
            }
            else
            {
              TrackInitialTokenRemovalReason(v11, 6);
              if ( (unsigned int)dword_18013A120 > 5 )
              {
                v59 = *v11;
                v57 = "TokenManager is disconnecting, not initiating soft-disconnect - not in a good state";
                v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
                  dword_18013A120,
                  (unsigned int)byte_18011F82D,
                  v42,
                  v43,
                  (__int64)&v56,
                  (__int64)&v57,
                  (__int64)&v59);
              }
              v32 = L"Minimize: Cleared AC token, won't initiate soft disconnect when not in a good state";
              *(_DWORD *)(*v11)[2].Data4 &= ~2u;
            }
LABEL_179:
            LogCandidate(v32, v11);
          }
          else if ( (unsigned int)dword_18013A120 > 5 )
          {
            v59 = *v11;
            v57 = "TokenManager is not initiating soft-disconnect - AC token was not previously given to this profile";
            v56 = "onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
              v34,
              (unsigned int)&word_18011F6FE,
              (_DWORD)v40,
              (_DWORD)v36,
              (__int64)&v56,
              (__int64)&v57,
              (__int64)&v59);
          }
LABEL_182:
          v7 = WPP_GLOBAL_Control;
          goto LABEL_48;
        }
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
          goto LABEL_48;
        }
        v26 = (int *)&v40[3].Data2;
        if ( (v40[2].Data4[4] & 1) == 0 )
          v26 = &dword_180103494;
        v27 = 80;
        v25 = *v11;
      }
      WPP_SF__guid_S(
        *(_QWORD *)(v7 + 16),
        v27,
        (unsigned int)&WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
        (_DWORD)v25,
        (__int64)v26);
      v7 = WPP_GLOBAL_Control;
LABEL_48:
      v11 += 2;
      if ( v11 == (const struct _GUID **)v63[0] )
        goto LABEL_49;
    }
    v3 = 1;
LABEL_34:
    v15 = 0;
    goto LABEL_35;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 76, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 5u && (*(_BYTE *)(v7 + 28) & 1) != 0 )
    {
      v8 = 77;
      goto LABEL_53;
    }
  }
}

```

## disassembly

```asm
0x1800188cc  mov     [rsp-8+arg_8], rbx
0x1800188d1  mov     [rsp-8+arg_10], rsi
0x1800188d6  push    rbp
0x1800188d7  push    rdi
0x1800188d8  push    r13
0x1800188da  push    r14
0x1800188dc  push    r15
0x1800188de  lea     rbp, [rsp-37h]
0x1800188e3  sub     rsp, 0C0h
0x1800188ea  mov     rax, cs:__security_cookie
0x1800188f1  xor     rax, rsp
0x1800188f4  mov     [rbp+57h+var_30], rax
0x1800188f8  mov     [rbp+57h+var_60], rdx
0x1800188fc  mov     rdi, rcx
0x1800188ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180018906  lea     r14, WPP_GLOBAL_Control
0x18001890d  lea     rbx, aApplyminimized; "ApplyMinimizeDestinationsPolicyFilter"
0x180018914  lea     r15, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x18001891b  cmp     rcx, r14
0x18001891e  jz      short loc_180018940
0x180018920  cmp     byte ptr [rcx+19h], 5
0x180018924  jb      short loc_180018940
0x180018926  test    byte ptr [rcx+1Ch], 1
0x18001892a  jz      short loc_180018940
0x18001892c  mov     rcx, [rcx+10h]
0x180018930  mov     edx, 49h ; 'I'
0x180018935  mov     r9, rbx
0x180018938  mov     r8, r15
0x18001893b  call    WPP_SF_s
0x180018940  xor     esi, esi
0x180018942  mov     [rbp+57h+var_58], 2
0x18001894a  lea     r9, [rbp+57h+var_80]; struct WCM_POLICY_VALUE_INTERNAL *
0x18001894e  mov     [rbp+57h+var_38], rsi
0x180018952  lea     r8, [rbp+57h+var_40]; struct WCM_POLICY_VALUE_INTERNAL *
0x180018956  mov     [rbp+57h+var_40], rsi
0x18001895a  lea     rdx, [rbp+57h+var_38]; struct WCM_POLICY_VALUE_INTERNAL *
0x18001895e  mov     [rbp+57h+var_80], rsi
0x180018962  lea     rcx, [rbp+57h+var_58]; struct WCM_POLICY_VALUE_INTERNAL *
0x180018966  call    ?GetCdePolicies@ConfigManager@@SAKPEAUWCM_POLICY_VALUE_INTERNAL@@000@Z; ConfigManager::GetCdePolicies(WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *,WCM_POLICY_VALUE_INTERNAL *)
0x18001896b  xorps   xmm0, xmm0
0x18001896e  mov     [rbp+57h+var_88], 1
0x180018976  lea     rdx, [rbp+57h+var_50]
0x18001897a  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001897e  call    ?lock@?$weak_ptr@VConfigManager@@@std@@QEBA?AV?$shared_ptr@VConfigManager@@@2@XZ; std::weak_ptr<ConfigManager>::lock(void)
0x180018983  cmp     [rbp+57h+var_50], rsi
0x180018987  jz      short loc_18001899D
0x180018989  lea     rdx, [rbp+57h+var_88]; struct WCM_POLICY_VALUE_INTERNAL *
0x18001898d  call    ?InternalGetSoftDisconnectPolicy@ConfigManager@@AEAAXPEAUWCM_POLICY_VALUE_INTERNAL@@@Z; ConfigManager::InternalGetSoftDisconnectPolicy(WCM_POLICY_VALUE_INTERNAL *)
0x180018992  mov     rcx, [rbp+57h+var_50+8]
0x180018996  test    rcx, rcx
0x180018999  jz      short loc_1800189AB
0x18001899b  jmp     short loc_1800189A6
0x18001899d  mov     rcx, [rbp+57h+var_50+8]; this
0x1800189a1  test    rcx, rcx
0x1800189a4  jz      short loc_1800189B4
0x1800189a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800189ab  mov     [rbp+57h+var_8D], sil
0x1800189af  cmp     dword ptr [rbp+57h+var_88], esi
0x1800189b2  jz      short loc_1800189B8
0x1800189b4  mov     [rbp+57h+var_8D], 1
0x1800189b8  cmp     dword ptr [rbp+57h+var_80], esi
0x1800189bb  jz      short loc_180018A1B
0x1800189bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189c4  cmp     rcx, r14
0x1800189c7  jz      loc_180018C15
0x1800189cd  cmp     byte ptr [rcx+19h], 4
0x1800189d1  jb      short loc_1800189F1
0x1800189d3  test    byte ptr [rcx+1Ch], 1
0x1800189d7  jz      short loc_1800189F1
0x1800189d9  mov     rcx, [rcx+10h]
0x1800189dd  mov     edx, 4Ah ; 'J'
0x1800189e2  mov     r8, r15
0x1800189e5  call    WPP_SF_
0x1800189ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189f1  cmp     rcx, r14
0x1800189f4  jz      loc_180018C15
0x1800189fa  cmp     byte ptr [rcx+19h], 5
0x1800189fe  jb      loc_180018C15
0x180018a04  test    byte ptr [rcx+1Ch], 1
0x180018a08  jz      loc_180018C15
0x180018a0e  mov     edx, 4Bh ; 'K'
0x180018a13  mov     r9, rbx
0x180018a16  jmp     loc_180018C05
0x180018a1b  cmp     cs:dword_18013F3E8, esi
0x180018a21  setnz   [rbp+57h+var_68]
0x180018a25  cmp     dword ptr [rbp+57h+var_58], esi
0x180018a28  jnz     short loc_180018A82
0x180018a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a31  cmp     rcx, r14
0x180018a34  jz      loc_180018C15
0x180018a3a  cmp     byte ptr [rcx+19h], 4
0x180018a3e  jb      short loc_180018A5E
0x180018a40  test    byte ptr [rcx+1Ch], 1
0x180018a44  jz      short loc_180018A5E
0x180018a46  mov     rcx, [rcx+10h]
0x180018a4a  mov     edx, 4Ch ; 'L'
0x180018a4f  mov     r8, r15
0x180018a52  call    WPP_SF_
0x180018a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a5e  cmp     rcx, r14
0x180018a61  jz      loc_180018C15
0x180018a67  cmp     byte ptr [rcx+19h], 5
0x180018a6b  jb      loc_180018C15
0x180018a71  test    byte ptr [rcx+1Ch], 1
0x180018a75  jz      loc_180018C15
0x180018a7b  mov     edx, 4Dh ; 'M'
0x180018a80  jmp     short loc_180018A13
0x180018a82  mov     rax, [rdi+8]
0x180018a86  mov     r13b, sil
0x180018a89  mov     rbx, [rdi]
0x180018a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a93  mov     [rbp+57h+var_90], sil
0x180018a97  mov     [rbp+57h+var_8F], sil
0x180018a9b  mov     [rbp+57h+var_8E], sil
0x180018a9f  mov     [rbp+57h+var_78], sil
0x180018aa3  mov     [rbp+57h+var_50], rax
0x180018aa7  cmp     rbx, rax
0x180018aaa  jz      loc_180018BE8
0x180018ab0  mov     r9, [rbx]
0x180018ab3  mov     edi, [r9+24h]
0x180018ab7  lea     rax, [r9+2Ch]
0x180018abb  cmp     edi, 4
0x180018abe  jnz     loc_180018C3D
0x180018ac4  test    [rax], dil
0x180018ac7  jz      loc_180018C3D
0x180018acd  mov     sil, 1
0x180018ad0  xor     r15b, r15b
0x180018ad3  mov     r11d, [r9+28h]
0x180018ad7  bt      r11d, 0Ch
0x180018adc  jb      loc_180018BD1
0x180018ae2  cmp     rcx, r14
0x180018ae5  jz      short loc_180018B35
0x180018ae7  cmp     byte ptr [rcx+19h], 4
0x180018aeb  jb      short loc_180018B35
0x180018aed  test    byte ptr [rcx+1Ch], 1
0x180018af1  jz      short loc_180018B35
0x180018af3  mov     edx, [rax]
0x180018af5  lea     rax, [r9+34h]
0x180018af9  mov     r8d, [r9+240h]
0x180018b00  mov     r10d, [r9+20h]
0x180018b04  test    dl, 1
0x180018b07  jnz     short loc_180018B10
0x180018b09  lea     rax, dword_180103494
0x180018b10  mov     rcx, [rcx+10h]; LoggerHandle
0x180018b14  mov     dword ptr [rsp+0E0h+var_98], r11d; char
0x180018b19  mov     dword ptr [rsp+0E0h+var_A0], r8d; char
0x180018b1e  mov     dword ptr [rsp+0E0h+var_A8], edx; char
0x180018b22  mov     dword ptr [rsp+0E0h+var_B0], edi; char
0x180018b26  mov     dword ptr [rsp+0E0h+var_B8], r10d; char
0x180018b2b  mov     [rsp+0E0h+var_C0], rax; __int64
0x180018b30  call    WPP_SF__guid_SdDDDD
0x180018b35  call    ?ShouldForceDisconnectInStandby@PdcManager@@YA_NXZ; PdcManager::ShouldForceDisconnectInStandby(void)
0x180018b3a  mov     cl, al
0x180018b3c  mov     rax, [rbx]
0x180018b3f  cmp     dword ptr [rax+20h], 3
0x180018b43  jz      loc_180018C5A
0x180018b49  test    cl, cl
0x180018b4b  jz      loc_180018C5A
0x180018b51  mov     rdx, rbx
0x180018b54  lea     rcx, aMinimizePowerP; "Minimize: power policies blocking candi"...
0x180018b5b  call    LogCandidate
0x180018b60  mov     eax, cs:dword_18013A120
0x180018b66  cmp     eax, 5
0x180018b69  jbe     short loc_180018BAF
0x180018b6b  mov     rax, [rbx]
0x180018b6e  lea     rdx, byte_18011FA05
0x180018b75  mov     [rbp+57h+var_80], rax
0x180018b79  lea     rax, aTokenmanagerIs; "TokenManager is removing all tokens bec"...
0x180018b80  mov     [rbp+57h+var_88], rax
0x180018b84  lea     rax, aOnecoreuapNetW_40; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x180018b8b  mov     [rbp+57h+var_70], rax
0x180018b8f  lea     rax, [rbp+57h+var_80]
0x180018b93  mov     qword ptr [rsp+0E0h+var_B0], rax
0x180018b98  lea     rax, [rbp+57h+var_88]
0x180018b9c  mov     qword ptr [rsp+0E0h+var_B8], rax
0x180018ba1  lea     rax, [rbp+57h+var_70]
0x180018ba5  mov     [rsp+0E0h+var_C0], rax
0x180018baa  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180018baf  mov     edx, 11h
0x180018bb4  mov     rcx, rbx
0x180018bb7  call    TrackInitialTokenRemovalReason
0x180018bbc  mov     rcx, [rbx]
0x180018bbf  and     dword ptr [rcx+28h], 0FFFFFFFDh
0x180018bc3  mov     rax, [rbx]
0x180018bc6  and     dword ptr [rax+28h], 0FFFFFFFBh
0x180018bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bd1  xor     esi, esi
0x180018bd3  add     rbx, 10h
0x180018bd7  cmp     rbx, [rbp+57h+var_50]
0x180018bdb  jnz     loc_180018AB0
0x180018be1  lea     r15, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x180018be8  cmp     rcx, r14
0x180018beb  jz      short loc_180018C15
0x180018bed  cmp     byte ptr [rcx+19h], 5
0x180018bf1  jb      short loc_180018C15
0x180018bf3  test    byte ptr [rcx+1Ch], 1
0x180018bf7  jz      short loc_180018C15
0x180018bf9  mov     edx, 51h ; 'Q'
0x180018bfe  lea     r9, aApplyminimized; "ApplyMinimizeDestinationsPolicyFilter"
0x180018c05  mov     rcx, [rcx+10h]
0x180018c09  mov     r8, r15
0x180018c0c  mov     dword ptr [rsp+0E0h+var_C0], esi
0x180018c10  call    WPP_SF_sL
0x180018c15  mov     rcx, [rbp+57h+var_30]
0x180018c19  xor     rcx, rsp; StackCookie
0x180018c1c  call    __security_check_cookie
0x180018c21  lea     r11, [rsp+0E0h+var_20]
0x180018c29  mov     rbx, [r11+38h]
0x180018c2d  mov     rsi, [r11+40h]
0x180018c31  mov     rsp, r11
0x180018c34  pop     r15
0x180018c36  pop     r14
0x180018c38  pop     r13
0x180018c3a  pop     rdi
0x180018c3b  pop     rbp
0x180018c3c  retn
0x180018c3d  cmp     edi, 1
0x180018c40  jnz     loc_180018AD0
0x180018c46  xor     sil, sil
0x180018c49  test    byte ptr [rax], 4
0x180018c4c  jz      loc_180018AD0
0x180018c52  mov     r15b, dil
0x180018c55  jmp     loc_180018AD3
0x180018c5a  test    r13b, r13b
0x180018c5d  jnz     short loc_180018C76
0x180018c5f  mov     rdx, rbx
0x180018c62  lea     rcx, aMinimizeKeepNo; "Minimize: Keep, no Internet candidate f"...
0x180018c69  mov     r14b, 1
0x180018c6c  call    LogCandidate
0x180018c71  mov     rax, [rbx]
0x180018c74  jmp     short loc_180018C79
0x180018c76  xor     r14b, r14b
0x180018c79  cmp     [rbp+57h+var_90], 0
0x180018c7d  jnz     short loc_180018C9E
0x180018c7f  mov     eax, [rax+240h]
0x180018c85  and     eax, 30h
0x180018c88  cmp     al, 30h ; '0'
0x180018c8a  jnz     short loc_180018C9E
0x180018c8c  mov     rdx, rbx
0x180018c8f  lea     rcx, aMinimizeKeepNo_0; "Minimize: Keep, no domain candidate fou"...
0x180018c96  mov     r14b, 1
0x180018c99  call    LogCandidate
0x180018c9e  test    sil, sil
0x180018ca1  jz      short loc_180018CB7
0x180018ca3  mov     rdx, rbx
0x180018ca6  lea     rcx, aMinimizeKeepMa; "Minimize: Keep, manually connected"
0x180018cad  mov     dil, 1
0x180018cb0  call    LogCandidate
0x180018cb5  jmp     short loc_180018CBA
0x180018cb7  mov     dil, r14b
0x180018cba  cmp     [rbp+57h+var_78], 0
0x180018cbe  jz      short loc_180018CDB
0x180018cc0  mov     rax, [rbx]
0x180018cc3  cmp     dword ptr [rax+20h], 2
0x180018cc7  jnz     short loc_180018CDB
0x180018cc9  mov     rdx, rbx
0x180018ccc  lea     rcx, aMinimizeKeepEa; "Minimize: Keep, earlier Wi-Fi was alrea"...
0x180018cd3  mov     dil, 1
0x180018cd6  call    LogCandidate
0x180018cdb  mov     rax, [rbx]
0x180018cde  test    byte ptr [rax+28h], 2
0x180018ce2  jnz     short loc_180018CFF
0x180018ce4  test    sil, sil
0x180018ce7  jnz     short loc_180018CFF
0x180018ce9  xor     esi, esi
0x180018ceb  lea     rcx, aMinimizeDropAc; "Minimize: Drop, AC token already revoke"...
0x180018cf2  mov     rdx, rbx
0x180018cf5  mov     dil, sil
0x180018cf8  call    LogCandidate
0x180018cfd  jmp     short loc_180018D01
0x180018cff  xor     esi, esi
0x180018d01  mov     rax, [rbx]
0x180018d04  test    byte ptr [rax+28h], 4
0x180018d08  jnz     short loc_180018D1C
0x180018d0a  mov     rdx, rbx
0x180018d0d  lea     rcx, aMinimizeDropMc; "Minimize: Drop, MC token already revoke"...
0x180018d14  mov     dil, sil
0x180018d17  call    LogCandidate
0x180018d1c  test    r15b, r15b
0x180018d1f  jz      short loc_180018D94
0x180018d21  mov     rdx, rbx
0x180018d24  lea     rcx, aMinimizeDropMa; "Minimize: Drop, manually disconnected"
0x180018d2b  call    LogCandidate
0x180018d30  mov     eax, dword ptr [rbp+57h+var_58]
0x180018d33  add     eax, 0FFFFFFFEh
0x180018d36  cmp     eax, 1
0x180018d39  ja      loc_180018EAB
0x180018d3f  mov     r9, [rbx]
0x180018d42  cmp     dword ptr [r9+20h], 3
0x180018d47  jnz     loc_180018EAB
0x180018d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d54  lea     r14, WPP_GLOBAL_Control
0x180018d5b  cmp     rcx, r14
0x180018d5e  jz      loc_180018BD3
0x180018d64  cmp     byte ptr [rcx+19h], 4
0x180018d68  jb      loc_180018BD3
0x180018d6e  test    byte ptr [rcx+1Ch], 1
0x180018d72  jz      loc_180018BD3
0x180018d78  test    byte ptr [r9+2Ch], 1
0x180018d7d  lea     rax, [r9+34h]
  ... truncated ...
```
