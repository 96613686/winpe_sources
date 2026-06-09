# CWwanSmsDevice::ProcessReadPduMessages(void *,ulong,int,int,int)

- ea: `0x18004e378`
- end: `0x18004ee9d`
- name: `?ProcessReadPduMessages@CWwanSmsDevice@@AEAAXPEAXKHHH@Z`
- size: `2853`
- prototype: `void __usercall(CWwanSmsDevice *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, int@<r9d>, int, int)`
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004c268`
- `0x18004cb00`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180004912`
- `0x180004980`
- `0x180004998`
- `0x1800069f0`
- `0x180006c84`
- `0x18000e8c0`
- `0x180013a10`
- `0x180027cb4`
- `0x180027f4c`
- `0x18004885c`
- `0x18004982c`
- `0x18004a8d0`
- `0x18004b2e4`
- `0x18004d1d8`
- `0x18004e378`
- `0x18004ef50`
- `0x180051420`
- `0x180051628`
- `0x180051a90`
- `0x180053ba4`
- `0x18005d8a8`
- `0x18005f000`
- `0x18005f368`
- `0x18005faac`
- `0x1800609fc`
- `0x18006133c`
- `0x1800614e8`
- `0x180061e78`
- `0x18006adac`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004ea3b`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004ea3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e7b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e99b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e9e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004ea20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e7b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e99b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004e9e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004ea20`

## string_xrefs

- `0x18004e56f`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004e5a8`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004e737`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004eb6a`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004ec14`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004ec4a`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004ec64`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004ecbd`: `CWwanSmsDevice::ProcessReadPduMessages`
- `0x18004e563`: `Incoming pdu message for iccid=%S, MessageIndex=%d, VoiceDomain=%d.`
- `0x18004eb5e`: `Saved incoming message segment type=%d, partindex=%d, totalparts=%d, uid=%s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CWwanSmsDevice::ProcessReadPduMessages(CWwanSmsDevice *this, char *a2, unsigned int a3, int a4, int a5)
{
  int FragmentInfoCdmaPdu; // ebx
  char *v9; // rdi
  __int64 v10; // r8
  __int64 v11; // r8
  unsigned __int8 *v12; // rsi
  int v13; // r10d
  __int16 *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  _WORD *v17; // rcx
  __int16 v18; // r8
  const wchar_t *v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  int v22; // r8d
  const unsigned __int16 *v23; // rcx
  unsigned int v24; // ebx
  struct _SPerIMSIConfig *PSPerIMSIConfig; // rax
  int v26; // r14d
  unsigned int v27; // r15d
  __int64 v28; // r8
  int v29; // eax
  const char *DisplayString; // rax
  unsigned __int16 **v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  CWwanSmsDevice *v35; // rcx
  _BYTE *v36; // rdx
  int v37; // r9d
  int v38; // edi
  const char *v39; // rax
  void *v40; // rax
  struct SmsStoreItem_tag *v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // r8
  _OWORD *v44; // rcx
  unsigned int *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  volatile signed __int32 *v48; // rdi
  volatile signed __int32 *v49; // rdi
  const char *v50; // rax
  volatile signed __int32 *v51; // rbx
  int v52; // esi
  const char *v53; // rax
  const wchar_t *v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // rcx
  unsigned int *v57; // r14
  __int64 v58; // rdx
  struct SmsFragmentInfo *v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+28h] [rbp-D8h]
  unsigned int v61; // [rsp+40h] [rbp-C0h]
  struct _SYSTEMTIME v62; // [rsp+50h] [rbp-B0h] BYREF
  int v63; // [rsp+60h] [rbp-A0h]
  unsigned int v64; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v65; // [rsp+68h] [rbp-98h]
  struct _SYSTEMTIME v66; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME v67; // [rsp+80h] [rbp-80h]
  void **v68; // [rsp+90h] [rbp-70h]
  char *v69; // [rsp+98h] [rbp-68h]
  struct SmsStoreItem_tag *v70; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v71; // [rsp+A8h] [rbp-58h]
  void **v72; // [rsp+B0h] [rbp-50h]
  char *v73; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v74[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v75; // [rsp+D0h] [rbp-30h]
  __int128 v76; // [rsp+E0h] [rbp-20h]
  __int128 v77; // [rsp+F0h] [rbp-10h]
  __int128 v78; // [rsp+100h] [rbp+0h]
  __int128 v79; // [rsp+110h] [rbp+10h] BYREF
  __int64 v80; // [rsp+120h] [rbp+20h]
  unsigned __int64 v81; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v82[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v83; // [rsp+140h] [rbp+40h]
  unsigned __int64 v84; // [rsp+148h] [rbp+48h]
  struct _SYSTEMTIME v85; // [rsp+150h] [rbp+50h] BYREF
  __int128 v86; // [rsp+160h] [rbp+60h] BYREF
  __int64 v87[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v88; // [rsp+180h] [rbp+80h]
  __int64 v89; // [rsp+188h] [rbp+88h]
  _OWORD v90[3]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v91; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v92; // [rsp+1D0h] [rbp+D0h]
  __int64 v93; // [rsp+1D8h] [rbp+D8h]
  __int128 v94; // [rsp+1E0h] [rbp+E0h] BYREF
  char v95[56]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v96; // [rsp+228h] [rbp+128h]
  unsigned int v97; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int8 v98; // [rsp+234h] [rbp+134h] BYREF
  unsigned __int8 v99[523]; // [rsp+235h] [rbp+135h] BYREF

  v63 = a4;
  v64 = a3;
  *(_OWORD *)v82 = 0;
  v83 = 0;
  v84 = 7;
  LOWORD(v82[0]) = 0;
  v91 = 0;
  v92 = 0;
  v93 = 7;
  LOWORD(v91) = 0;
  v79 = 0;
  v80 = 0;
  v81 = 7;
  LOWORD(v79) = 0;
  FragmentInfoCdmaPdu = 0;
  v68 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v9 = (char *)this + 32;
  v69 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  std::wstring::operator=((__int64)v82, (_QWORD *)this + 68, v10);
  std::wstring::operator=((__int64)&v79, (_QWORD *)this + 72, v11);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
  v61 = 0;
  if ( a3 )
  {
    v12 = (unsigned __int8 *)(a2 + 9);
    v65 = (unsigned __int8 *)(a2 + 9);
    do
    {
      *(_DWORD *)v74 = 0;
      memset_0(&v74[4], 0, 0x4Cu);
      *(_QWORD *)&v62.wYear = 0;
      memset_0(&v98, 0, 0x204u);
      memset(v90, 0, 44);
      *(_QWORD *)&v66.wYear = a2;
      *(_OWORD *)v87 = 0;
      v88 = 0;
      v89 = 7;
      LOWORD(v87[0]) = 0;
      v85 = 0;
      v97 = 512;
      v13 = *(_DWORD *)a2;
      DWORD2(v90[2]) = *(_DWORD *)a2;
      v14 = (__int16 *)&v79;
      if ( v81 > 7 )
        v14 = (__int16 *)v79;
      v15 = 20;
      v16 = 2147483646;
      v17 = v90;
      while ( v16 )
      {
        v18 = *v14;
        if ( *v14 )
        {
          ++v14;
          *v17++ = v18;
          --v16;
          if ( --v15 )
            continue;
        }
        if ( !v15 )
          --v17;
        break;
      }
      *v17 = 0;
      v19 = (const wchar_t *)&v79;
      if ( v81 > 7 )
        v19 = (const wchar_t *)v79;
      LogSmsRouterInfo(
        "CWwanSmsDevice::ProcessReadPduMessages",
        0x594u,
        "Incoming pdu message for iccid=%S, MessageIndex=%d, VoiceDomain=%d.",
        v19,
        v13,
        *((_DWORD *)this + 168));
      if ( *((_DWORD *)this + 168) != 1 )
      {
        v98 = 1;
        if ( g_fLogPduData && FragmentInfoCdmaPdu >= 0 )
        {
          DisplayString = GetDisplayString(v12, (unsigned __int8)a2[8]);
          LogSmsRouterInfo("CWwanSmsDevice::ProcessReadPduMessages", 0x5BBu, "CDMA Pdu: %s", DisplayString);
        }
        v31 = v82;
        if ( v84 > 7 )
          v31 = (unsigned __int16 **)v82[0];
        FragmentInfoCdmaPdu = CSmsEncodingHelper::GetFragmentInfoCdmaPdu(
                                v12,
                                (unsigned __int8)a2[8],
                                v31,
                                v74,
                                &v62,
                                v87,
                                &v85);
        if ( FragmentInfoCdmaPdu < 0 )
        {
          v59 = (struct SmsFragmentInfo *)GetDisplayString(v12, (unsigned __int8)a2[8]);
          LogSmsRouterError(
            "CWwanSmsDevice::ProcessReadPduMessages",
            0x5CBu,
            FragmentInfoCdmaPdu,
            "Fragment info could not be obtained for pdu: %s",
            v59);
          goto LABEL_103;
        }
        if ( a2[8] )
        {
          if ( v12 )
          {
            memcpy_0(v99, v12, (unsigned __int8)a2[8]);
          }
          else
          {
            memset_0(v99, 0, 0x200u);
            *(_DWORD *)_o__errno(v33, v32, v34) = 22;
            invalid_parameter_noinfo();
          }
        }
        v97 = (unsigned __int8)a2[8];
        v27 = *(_DWORD *)&v62.wDayOfWeek;
        v26 = *(_DWORD *)&v62.wYear;
LABEL_48:
        v72 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
        v73 = v9;
        (**(void (__fastcall ***)(char *))v9)(v9);
        DWORD1(v86) = 0;
        LODWORD(v86) = *(_DWORD *)a2;
        v62 = v85;
        *((_QWORD *)&v86 + 1) = CWwanSmsDevice::GetDateTimeFromSystemTime(v35, &v62);
        v36 = (_BYTE *)*((_QWORD *)this + 57);
        if ( v36 == *((_BYTE **)this + 58) )
        {
          std::vector<SmsReadMsgData>::_Emplace_reallocate<SmsReadMsgData const &>((_QWORD *)this + 56, v36, &v86);
        }
        else
        {
          *(_OWORD *)v36 = v86;
          *((_QWORD *)this + 57) += 16LL;
        }
        v37 = *((_DWORD *)a2 + 1);
        if ( v37 )
        {
          LogSmsRouterInfo(
            "CWwanSmsDevice::ProcessReadPduMessages",
            0x5FFu,
            "Skipping saving to the store as it is not a new message MsgStatus = %d",
            v37);
        }
        else if ( *((_QWORD *)this + 103) == -1 )
        {
          v54 = (const wchar_t *)&v79;
          if ( v81 > 7 )
            v54 = (const wchar_t *)v79;
          LogSmsRouterError(
            "CWwanSmsDevice::ProcessReadPduMessages",
            0x5F9u,
            -2147418113,
            "Sms parts store closed while processing pdu for IccId: %S",
            v54);
        }
        else
        {
          v38 = DWORD2(v78);
          if ( !HIDWORD(v78) && (DWORD2(v78) > DWORD1(v78) || !DWORD2(v78)) || *(_DWORD *)v74 > 0x40u )
          {
            FragmentInfoCdmaPdu = -2147024809;
            goto LABEL_95;
          }
          if ( (unsigned int)CSmsConcatenateStore::HandleDuplicateMessage(
                               (CWwanSmsDevice *)((char *)this + 696),
                               (struct SmsFragmentInfo *)v74,
                               v26) )
          {
            v39 = GetDisplayString(&v74[4], *(unsigned int *)v74);
            LogSmsRouterInfo(
              "CSmsConcatenateStore::Add",
              0x22Du,
              "Duplicate message partindex=%d, totalparts=%d, uid=%s, IccId=%S",
              DWORD2(v78),
              DWORD1(v78),
              v39,
              (const wchar_t *)v90);
            FragmentInfoCdmaPdu = 0;
            goto LABEL_86;
          }
          v40 = operator new(0x298u);
          std::shared_ptr<SmsStoreItem_tag>::shared_ptr<SmsStoreItem_tag>(&v70, v40);
          v41 = v70;
          if ( v70 )
          {
            memset_0(v70, 0, 0x298u);
            *(_DWORD *)v41 = 664;
            *((_DWORD *)v41 + 1) = v27 != 0 ? 3 : 1;
            v44 = (_OWORD *)((char *)v41 + 8);
            if ( v41 == (struct SmsStoreItem_tag *)-8LL )
            {
              *(_DWORD *)_o__errno(v44, v42, v43) = 22;
              invalid_parameter_noinfo();
            }
            else
            {
              v45 = &v97;
              v46 = 4;
              v47 = 128;
              do
              {
                *v44 = *(_OWORD *)v45;
                v44[1] = *((_OWORD *)v45 + 1);
                v44[2] = *((_OWORD *)v45 + 2);
                v44[3] = *((_OWORD *)v45 + 3);
                v44[4] = *((_OWORD *)v45 + 4);
                v44[5] = *((_OWORD *)v45 + 5);
                v44[6] = *((_OWORD *)v45 + 6);
                v44[7] = *((_OWORD *)v45 + 7);
                v44 += 8;
                v45 += 32;
                --v46;
              }
              while ( v46 );
              *(_QWORD *)v44 = *(_QWORD *)v45;
            }
            if ( v41 == (struct SmsStoreItem_tag *)-528LL )
            {
              *(_DWORD *)_o__errno(v44, v46, v47) = 22;
              invalid_parameter_noinfo();
            }
            else
            {
              *((_OWORD *)v41 + 33) = *(_OWORD *)v74;
              *((_OWORD *)v41 + 34) = v75;
              *((_OWORD *)v41 + 35) = v76;
              *((_OWORD *)v41 + 36) = v77;
              *((_OWORD *)v41 + 37) = v78;
            }
            if ( v41 == (struct SmsStoreItem_tag *)-608LL )
            {
              *(_DWORD *)_o__errno(v44, v46, v47) = 22;
              invalid_parameter_noinfo();
            }
            else
            {
              *((_OWORD *)v41 + 38) = v90[0];
              *((_OWORD *)v41 + 39) = v90[1];
              *(_OWORD *)((char *)v41 + 636) = *(_OWORD *)((char *)&v90[1] + 12);
            }
            _time64((__time64_t *)v41 + 82);
            CSmsConcatenateStore::GetNextAvailableFreeLocation((CWwanSmsDevice *)((char *)this + 696));
            if ( *(_QWORD *)&v67.wYear )
            {
              **(_QWORD **)&v67.wYear = *((_QWORD *)v41 + 82);
              FragmentInfoCdmaPdu = CSmsConcatenateStore::SaveMessage(
                                      (CWwanSmsDevice *)((char *)this + 696),
                                      *(_DWORD *)(*(_QWORD *)&v67.wYear + 8LL),
                                      v41);
              if ( FragmentInfoCdmaPdu >= 0 )
              {
                v62 = 0;
                if ( *(_QWORD *)&v67.wHour )
                  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v67.wHour + 8LL));
                v62 = v67;
                FragmentInfoCdmaPdu = CSmsConcatenateStore::AddInternal((char *)this + 696, v74, &v62, v27);
              }
            }
            else
            {
              FragmentInfoCdmaPdu = -2147024882;
            }
            v48 = *(volatile signed __int32 **)&v67.wHour;
            if ( *(_QWORD *)&v67.wHour )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v67.wHour + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
              }
            }
            v49 = v71;
            if ( v71 )
            {
              if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
                if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
              }
            }
            if ( FragmentInfoCdmaPdu >= 0 )
            {
LABEL_86:
              v50 = GetDisplayString(&v74[4], *(unsigned int *)v74);
              LogSmsRouterInfo(
                "CWwanSmsDevice::ProcessReadPduMessages",
                0x5E2u,
                "Saved incoming message segment type=%d, partindex=%d, totalparts=%d, uid=%s.",
                v98,
                DWORD2(v78),
                DWORD1(v78),
                v50);
              goto LABEL_87;
            }
            v38 = DWORD2(v78);
LABEL_95:
            v52 = FragmentInfoCdmaPdu;
          }
          else
          {
            v51 = v71;
            if ( v71 )
            {
              if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
                if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
              }
            }
            v52 = -2147024882;
            FragmentInfoCdmaPdu = -2147024882;
            v38 = DWORD2(v78);
          }
          v53 = GetDisplayString(&v74[4], *(unsigned int *)v74);
          LogSmsRouterError(
            "CWwanSmsDevice::ProcessReadPduMessages",
            0x5EDu,
            v52,
            "Failed to save message segment type=%d, partindex=%d, totalparts=%d, uid=%s.",
            v98,
            v38,
            DWORD1(v78),
            v53);
LABEL_87:
          v9 = (char *)this + 32;
          v12 = v65;
        }
        CWwanSmsDevice::MaintainSmsListAtHalfFull(this, 0);
        v72 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
        (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
        goto LABEL_103;
      }
      v98 = 0;
      if ( g_fLogPduData )
        LogSmsRouterInfo("CWwanSmsDevice::ProcessReadPduMessages", 0x59Eu, "GSM Pdu: %s", (const char *)v12);
      v20 = -1;
      do
        ++v20;
      while ( v12[v20] );
      if ( (unsigned int)v20 > 2 * v97 )
      {
        v22 = -2147024809;
        FragmentInfoCdmaPdu = -2147024809;
        goto LABEL_36;
      }
      v21 = CWwanMessageXmlHelper::ConvertHexCstringToBinary((char *)v12, v20, v99, &v97);
      FragmentInfoCdmaPdu = v21;
      if ( v21 < 0 )
      {
        v22 = v21;
LABEL_36:
        LogSmsRouterError("CWwanSmsDevice::ProcessReadPduMessages", 0x5B0u, v22, "Failed to decode gsm pdu: %s", a2);
        goto LABEL_103;
      }
      v23 = (const unsigned __int16 *)v82;
      if ( v84 > 7 )
        v23 = v82[0];
      v24 = v97;
      PSPerIMSIConfig = SmsEncodingHelper::GetPSPerIMSIConfig(v23);
      if ( v24 )
      {
        v26 = *((_DWORD *)PSPerIMSIConfig + 19);
        v27 = v26;
        v28 = (unsigned int)v99[0] + 1;
        if ( (unsigned int)v99[0] + 13 <= v24 )
        {
          if ( (v99[v28] & 3) == 0 )
          {
            v29 = ParseGsmDeliverMessageFragmentInfo(
                    (int)v99,
                    v24,
                    v28,
                    (int)PSPerIMSIConfig,
                    (struct SmsFragmentInfo *)v74,
                    (__int64)v87,
                    (__int64)&v85);
            goto LABEL_31;
          }
          if ( (v99[v28] & 3) == 2 )
          {
            v29 = ParseGsmStatusReportMessageFragmentInfo(
                    (int)v99,
                    v24,
                    v28,
                    (int)PSPerIMSIConfig,
                    (struct SmsFragmentInfo *)v74,
                    (__int64)v87,
                    &v85);
LABEL_31:
            FragmentInfoCdmaPdu = v29;
            if ( v29 >= 0 )
              goto LABEL_48;
            goto LABEL_26;
          }
          v29 = -2147023266;
          FragmentInfoCdmaPdu = -2147023266;
        }
        else
        {
          v29 = -2147024809;
          FragmentInfoCdmaPdu = -2147024809;
        }
      }
      else
      {
        v29 = -2147024809;
        FragmentInfoCdmaPdu = -2147024809;
      }
LABEL_26:
      LogSmsRouterError(
        "CWwanSmsDevice::ProcessReadPduMessages",
        0x5ABu,
        v29,
        "Fragment info could not be obtained for gsm pdu: %s",
        a2);
LABEL_103:
      v12 += 376;
      v65 = v12;
      a2 += 376;
      if ( v63 )
      {
        v68 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
        v69 = v9;
        (**(void (__fastcall ***)(char *))v9)(v9);
        if ( *((_QWORD *)this + 103) == -1 )
        {
          v57 = *(unsigned int **)&v66.wYear;
        }
        else
        {
          v94 = 0;
          v96 = 0;
          v55 = operator new(0x18u);
          *v55 = 0;
          v55[1] = 0;
          v55[2] = 0;
          std::shared_ptr<std::vector<unsigned char>>::reset<std::vector<unsigned char>,0>(&v94, v55);
          std::vector<unsigned char>::resize(v94, 32);
          v56 = *(_QWORD *)v94;
          *(_DWORD *)(v56 + 16) = 1;
          *(_DWORD *)(v56 + 20) = 4;
          v57 = *(unsigned int **)&v66.wYear;
          *(_DWORD *)(v56 + 24) = **(_DWORD **)&v66.wYear;
          *(_OWORD *)v56 = *(_OWORD *)((char *)this + 152);
          std::function<void (std::shared_ptr<std::vector<unsigned char>> &)>::operator=(v95, (char *)this + 840);
          CExecutionManager::ScheduleWorkItem(*((CExecutionManager **)this + 113), (struct CSmsWorkItem *)&v94);
          CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)&v94, v58);
        }
        v68 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
        (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      else
      {
        v57 = *(unsigned int **)&v66.wYear;
      }
      v66 = v85;
      LODWORD(v60) = a5;
      CWwanSmsDevice::PublishSmsWNF(this, &v97, *v57, v87, &v66, v60, v82);
      std::wstring::~wstring((char **)v87);
      ++v61;
    }
    while ( v61 < v64 );
  }
  CWwanSmsDevice::ProcessPendingMessages(this);
  std::wstring::~wstring((char **)&v79);
  std::wstring::~wstring((char **)&v91);
  std::wstring::~wstring((char **)v82);
}

```

## disassembly

```asm
0x18004e378  mov     [rsp-8+arg_10], rbx
0x18004e37d  push    rbp
0x18004e37e  push    rsi
0x18004e37f  push    rdi
0x18004e380  push    r12
0x18004e382  push    r13
0x18004e384  push    r14
0x18004e386  push    r15
0x18004e388  lea     rbp, [rsp-350h]
0x18004e390  sub     rsp, 450h
0x18004e397  mov     rax, cs:__security_cookie
0x18004e39e  xor     rax, rsp
0x18004e3a1  mov     [rbp+380h+var_40], rax
0x18004e3a8  mov     [rsp+480h+var_420], r9d
0x18004e3ad  mov     esi, r8d
0x18004e3b0  mov     [rsp+480h+var_41C], r8d
0x18004e3b5  mov     r12, rdx
0x18004e3b8  mov     r13, rcx
0x18004e3bb  xorps   xmm0, xmm0
0x18004e3be  movups  xmmword ptr [rbp+380h+var_350], xmm0
0x18004e3c2  xor     r15d, r15d
0x18004e3c5  mov     [rbp+380h+var_340], r15
0x18004e3c9  lea     ecx, [r15+7]
0x18004e3cd  mov     [rbp+380h+var_338], rcx
0x18004e3d1  mov     word ptr [rbp+380h+var_350], r15w
0x18004e3d6  movups  [rbp+380h+var_2C0], xmm0
0x18004e3dd  mov     [rbp+380h+var_2B0], r15
0x18004e3e4  mov     [rbp+380h+var_2A8], rcx
0x18004e3eb  mov     word ptr [rbp+380h+var_2C0], r15w
0x18004e3f3  movups  [rbp+380h+var_370], xmm0
0x18004e3f7  mov     [rbp+380h+var_360], r15
0x18004e3fb  mov     [rbp+380h+var_358], rcx
0x18004e3ff  mov     word ptr [rbp+380h+var_370], r15w
0x18004e404  mov     ebx, r15d
0x18004e407  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004e40e  mov     [rbp+380h+var_3F0], rax
0x18004e412  lea     rdi, [r13+20h]
0x18004e416  mov     [rbp+380h+var_3E8], rdi
0x18004e41a  mov     rax, [rdi]
0x18004e41d  mov     rcx, rdi
0x18004e420  mov     rax, [rax]
0x18004e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e428  nop
0x18004e429  lea     rdx, [r13+220h]
0x18004e430  lea     rcx, [rbp+380h+var_350]
0x18004e434  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004e439  lea     rdx, [r13+240h]
0x18004e440  lea     rcx, [rbp+380h+var_370]
0x18004e444  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004e449  nop
0x18004e44a  mov     rax, [rdi]
0x18004e44d  mov     rcx, rdi
0x18004e450  mov     rax, [rax+8]
0x18004e454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e459  nop
0x18004e45a  mov     [rsp+480h+var_440], r15d
0x18004e45f  test    esi, esi
0x18004e461  jz      loc_18004EE4A
0x18004e467  lea     rsi, [r12+9]
0x18004e46c  mov     [rsp+480h+var_418], rsi
0x18004e471  mov     r14d, 80070057h
0x18004e477  mov     dword ptr [rbp+380h+var_3C0], r15d
0x18004e47b  xor     edx, edx; Val
0x18004e47d  lea     r8d, [rdx+4Ch]; Size
0x18004e481  lea     rcx, [rbp+380h+var_3C0+4]; void *
0x18004e485  call    memset_0
0x18004e48a  mov     qword ptr [rsp+480h+var_430.wYear], r15
0x18004e48f  xor     edx, edx; Val
0x18004e491  mov     r8d, 204h; Size
0x18004e497  lea     rcx, [rbp+380h+var_24C]; void *
0x18004e49e  call    memset_0
0x18004e4a3  xorps   xmm0, xmm0
0x18004e4a6  movups  [rbp+380h+var_2F0], xmm0
0x18004e4ad  movups  [rbp+380h+var_2E0], xmm0
0x18004e4b4  movups  [rbp+380h+var_2E0+0Ch], xmm0
0x18004e4bb  mov     qword ptr [rsp+480h+var_410], r12
0x18004e4c0  movups  xmmword ptr [rbp+380h+var_310], xmm0
0x18004e4c4  mov     [rbp+380h+var_300], r15
0x18004e4cb  mov     [rbp+380h+var_2F8], 7
0x18004e4d6  mov     word ptr [rbp+380h+var_310], r15w
0x18004e4db  movups  xmmword ptr [rbp+380h+var_330.wYear], xmm0
0x18004e4df  mov     [rbp+380h+var_250], 200h
0x18004e4e9  mov     r10d, [r12]
0x18004e4ed  mov     [rbp+380h+var_2C8], r10d
0x18004e4f4  lea     rdx, [rbp+380h+var_370]
0x18004e4f8  cmp     [rbp+380h+var_358], 7
0x18004e4fd  cmova   rdx, qword ptr [rbp+380h+var_370]
0x18004e502  mov     eax, 14h
0x18004e507  mov     r9d, 7FFFFFFEh
0x18004e50d  lea     rcx, [rbp+380h+var_2F0]
0x18004e514  test    r9, r9
0x18004e517  jz      short loc_18004E541
0x18004e519  movzx   r8d, word ptr [rdx]
0x18004e51d  test    r8w, r8w
0x18004e521  jz      short loc_18004E538
0x18004e523  add     rdx, 2
0x18004e527  mov     [rcx], r8w
0x18004e52b  add     rcx, 2
0x18004e52f  dec     r9
0x18004e532  sub     rax, 1
0x18004e536  jnz     short loc_18004E514
0x18004e538  test    rax, rax
0x18004e53b  jnz     short loc_18004E541
0x18004e53d  sub     rcx, 2
0x18004e541  mov     [rcx], r15w
0x18004e545  mov     eax, [r13+2A0h]
0x18004e54c  lea     r9, [rbp+380h+var_370]
0x18004e550  cmp     [rbp+380h+var_358], 7
0x18004e555  cmova   r9, qword ptr [rbp+380h+var_370]
0x18004e55a  mov     dword ptr [rsp+480h+var_458], eax
0x18004e55e  mov     dword ptr [rsp+480h+var_460], r10d
0x18004e563  lea     r8, aIncomingPduMes; "Incoming pdu message for iccid=%S, Mess"...
0x18004e56a  mov     edx, 594h; unsigned int
0x18004e56f  lea     rcx, aCwwansmsdevice_2; "CWwanSmsDevice::ProcessReadPduMessages"
0x18004e576  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004e57b  cmp     dword ptr [r13+2A0h], 1
0x18004e583  jnz     loc_18004E706
0x18004e589  mov     [rbp+380h+var_24C], r15b
0x18004e590  cmp     cs:?g_fLogPduData@@3HA, r15d; int g_fLogPduData
0x18004e597  jz      short loc_18004E5B4
0x18004e599  mov     r9, rsi
0x18004e59c  lea     r8, aGsmPduS; "GSM Pdu: %s"
0x18004e5a3  mov     edx, 59Eh; unsigned int
0x18004e5a8  lea     rcx, aCwwansmsdevice_2; "CWwanSmsDevice::ProcessReadPduMessages"
0x18004e5af  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004e5b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e5b8  inc     rdx; unsigned int
0x18004e5bb  cmp     [rsi+rdx], r15b
0x18004e5bf  jnz     short loc_18004E5B8
0x18004e5c1  mov     eax, [rbp+380h+var_250]
0x18004e5c7  add     eax, eax
0x18004e5c9  cmp     edx, eax
0x18004e5cb  ja      loc_18004E6EA
0x18004e5d1  lea     r9, [rbp+380h+var_250]; unsigned int *
0x18004e5d8  lea     r8, [rbp+380h+var_24B]; unsigned __int8 *
0x18004e5df  mov     rcx, rsi; char *
0x18004e5e2  call    ?ConvertHexCstringToBinary@CWwanMessageXmlHelper@@SAJPEADKPEAEAEAK@Z; CWwanMessageXmlHelper::ConvertHexCstringToBinary(char *,ulong,uchar *,ulong &)
0x18004e5e7  mov     ebx, eax
0x18004e5e9  test    eax, eax
0x18004e5eb  jns     short loc_18004E5F5
0x18004e5ed  mov     r8d, eax
0x18004e5f0  jmp     loc_18004E6F0
0x18004e5f5  lea     rcx, [rbp+380h+var_350]
0x18004e5f9  cmp     [rbp+380h+var_338], 7
0x18004e5fe  cmova   rcx, [rbp+380h+var_350]; unsigned __int16 *
0x18004e603  mov     ebx, [rbp+380h+var_250]
0x18004e609  call    ?GetPSPerIMSIConfig@SmsEncodingHelper@@SAPEAU_SPerIMSIConfig@@PEBG@Z; SmsEncodingHelper::GetPSPerIMSIConfig(ushort const *)
0x18004e60e  mov     r9, rax; int
0x18004e611  test    ebx, ebx
0x18004e613  jz      loc_18004E6DF
0x18004e619  mov     r14d, [rax+4Ch]
0x18004e61d  mov     r15d, r14d
0x18004e620  movzx   r8d, [rbp+380h+var_24B]
0x18004e628  inc     r8d; int
0x18004e62b  lea     eax, [r8+0Ch]
0x18004e62f  cmp     eax, ebx
0x18004e631  jbe     short loc_18004E65B
0x18004e633  mov     r14d, 80070057h
0x18004e639  mov     eax, r14d
0x18004e63c  mov     ebx, r14d
0x18004e63f  xor     r15d, r15d
0x18004e642  mov     [rsp+480h+var_460], r12
0x18004e647  lea     r9, aFragmentInfoCo; "Fragment info could not be obtained for"...
0x18004e64e  mov     r8d, eax
0x18004e651  mov     edx, 5ABh
0x18004e656  jmp     loc_18004ECBD
0x18004e65b  movzx   ecx, [rbp+r8+380h+var_24B]
0x18004e664  and     ecx, 3
0x18004e667  jnz     short loc_18004E694
0x18004e669  lea     rax, [rbp+380h+var_330]
0x18004e66d  mov     [rsp+480h+var_450], rax; __int64
0x18004e672  lea     rax, [rbp+380h+var_310]
0x18004e676  mov     [rsp+480h+var_458], rax; __int64
0x18004e67b  lea     rax, [rbp+380h+var_3C0]
0x18004e67f  mov     [rsp+480h+var_460], rax; struct SmsFragmentInfo *
0x18004e684  mov     edx, ebx; int
0x18004e686  lea     rcx, [rbp+380h+var_24B]; int
0x18004e68d  call    ?ParseGsmDeliverMessageFragmentInfo@@YAJPEAEKKPEAU_SPerIMSIConfig@@PEAUSmsFragmentInfo@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; ParseGsmDeliverMessageFragmentInfo(uchar *,ulong,ulong,_SPerIMSIConfig *,SmsFragmentInfo *,std::wstring &,_SYSTEMTIME &)
0x18004e692  jmp     short loc_18004E6C2
0x18004e694  cmp     ecx, 2
0x18004e697  jnz     short loc_18004E6D1
0x18004e699  lea     rax, [rbp+380h+var_330]
0x18004e69d  mov     [rsp+480h+var_450], rax; struct _SYSTEMTIME *
0x18004e6a2  lea     rax, [rbp+380h+var_310]
0x18004e6a6  mov     [rsp+480h+var_458], rax; __int64
0x18004e6ab  lea     rax, [rbp+380h+var_3C0]
0x18004e6af  mov     [rsp+480h+var_460], rax; struct SmsFragmentInfo *
0x18004e6b4  mov     edx, ebx; int
0x18004e6b6  lea     rcx, [rbp+380h+var_24B]; int
0x18004e6bd  call    ?ParseGsmStatusReportMessageFragmentInfo@@YAJPEBEKKPEAU_SPerIMSIConfig@@PEAUSmsFragmentInfo@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; ParseGsmStatusReportMessageFragmentInfo(uchar const *,ulong,ulong,_SPerIMSIConfig *,SmsFragmentInfo *,std::wstring &,_SYSTEMTIME &)
0x18004e6c2  mov     ebx, eax
0x18004e6c4  test    eax, eax
0x18004e6c6  js      loc_18004E63F
0x18004e6cc  jmp     loc_18004E7DE
0x18004e6d1  mov     ecx, 8007065Eh
0x18004e6d6  mov     eax, ecx
0x18004e6d8  mov     ebx, ecx
0x18004e6da  jmp     loc_18004E63F
0x18004e6df  mov     eax, r14d
0x18004e6e2  mov     ebx, r14d
0x18004e6e5  jmp     loc_18004E642
0x18004e6ea  mov     r8d, r14d
0x18004e6ed  mov     ebx, r14d
0x18004e6f0  mov     [rsp+480h+var_460], r12
0x18004e6f5  lea     r9, aFailedToDecode; "Failed to decode gsm pdu: %s"
0x18004e6fc  mov     edx, 5B0h
0x18004e701  jmp     loc_18004ECBD
0x18004e706  mov     [rbp+380h+var_24C], 1
0x18004e70d  cmp     cs:?g_fLogPduData@@3HA, r15d; int g_fLogPduData
0x18004e714  jz      short loc_18004E743
0x18004e716  test    ebx, ebx
0x18004e718  js      short loc_18004E743
0x18004e71a  movzx   edx, byte ptr [r12+8]; unsigned int
0x18004e720  mov     rcx, rsi; unsigned __int8 *
0x18004e723  call    ?GetDisplayString@@YAPEBDPEAEK@Z; GetDisplayString(uchar *,ulong)
0x18004e728  mov     r9, rax
0x18004e72b  lea     r8, aCdmaPduS; "CDMA Pdu: %s"
0x18004e732  mov     edx, 5BBh; unsigned int
0x18004e737  lea     rcx, aCwwansmsdevice_2; "CWwanSmsDevice::ProcessReadPduMessages"
0x18004e73e  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004e743  lea     r8, [rbp+380h+var_350]
0x18004e747  cmp     [rbp+380h+var_338], 7
0x18004e74c  cmova   r8, [rbp+380h+var_350]
0x18004e751  movzx   edx, byte ptr [r12+8]
0x18004e757  lea     rax, [rbp+380h+var_330]
0x18004e75b  mov     [rsp+480h+var_450], rax
0x18004e760  lea     rax, [rbp+380h+var_310]
0x18004e764  mov     [rsp+480h+var_458], rax
0x18004e769  lea     rax, [rsp+480h+var_430]
0x18004e76e  mov     [rsp+480h+var_460], rax
0x18004e773  lea     r9, [rbp+380h+var_3C0]
0x18004e777  mov     rcx, rsi
0x18004e77a  call    ?GetFragmentInfoCdmaPdu@CSmsEncodingHelper@@SAJPEBEKPEBGPEAUSmsFragmentInfo@@PEAUSmsHandlingInfo@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; CSmsEncodingHelper::GetFragmentInfoCdmaPdu(uchar const *,ulong,ushort const *,SmsFragmentInfo *,SmsHandlingInfo *,std::wstring &,_SYSTEMTIME &)
0x18004e77f  mov     ebx, eax
0x18004e781  test    eax, eax
0x18004e783  js      loc_18004EC9B
0x18004e789  movzx   r8d, byte ptr [r12+8]; Size
0x18004e78f  test    r8, r8
0x18004e792  jz      short loc_18004E7C8
0x18004e794  lea     rcx, [rbp+380h+var_24B]; void *
0x18004e79b  test    rsi, rsi
0x18004e79e  jz      short loc_18004E7AA
0x18004e7a0  mov     rdx, rsi; Src
0x18004e7a3  call    memcpy_0
0x18004e7a8  jmp     short loc_18004E7C8
0x18004e7aa  xor     edx, edx; Val
0x18004e7ac  mov     r8d, 200h; Size
0x18004e7b2  call    memset_0
0x18004e7b7  call    cs:__imp__o__errno
0x18004e7bd  mov     dword ptr [rax], 16h
0x18004e7c3  call    _invalid_parameter_noinfo
0x18004e7c8  movzx   eax, byte ptr [r12+8]
0x18004e7ce  mov     [rbp+380h+var_250], eax
0x18004e7d4  mov     r15d, dword ptr [rsp+480h+var_430.wDayOfWeek]
0x18004e7d9  mov     r14d, dword ptr [rsp+480h+var_430.wYear]
0x18004e7de  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004e7e5  mov     [rbp+380h+var_3D0], rax
0x18004e7e9  mov     [rbp+380h+var_3C8], rdi
0x18004e7ed  mov     rax, [rdi]
0x18004e7f0  mov     rcx, rdi
0x18004e7f3  mov     rax, [rax]
0x18004e7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7fb  nop
0x18004e7fc  mov     dword ptr [rbp+380h+var_320+4], 0
0x18004e803  mov     eax, [r12]
0x18004e807  mov     dword ptr [rbp+380h+var_320], eax
0x18004e80a  movaps  xmm0, xmmword ptr [rbp+380h+var_330.wYear]
0x18004e80e  movdqa  xmmword ptr [rsp+480h+var_430.wYear], xmm0
0x18004e814  lea     rdx, [rsp+480h+var_430]; struct _SYSTEMTIME
0x18004e819  call    ?GetDateTimeFromSystemTime@CWwanSmsDevice@@AEAA_KU_SYSTEMTIME@@@Z; CWwanSmsDevice::GetDateTimeFromSystemTime(_SYSTEMTIME)
0x18004e81e  mov     qword ptr [rbp+380h+var_320+8], rax
0x18004e822  lea     rcx, [r13+1C0h]
0x18004e829  mov     rdx, [rcx+8]
0x18004e82d  cmp     rdx, [rcx+10h]
0x18004e831  jz      short loc_18004E842
0x18004e833  movups  xmm0, [rbp+380h+var_320]
0x18004e837  movdqu  xmmword ptr [rdx], xmm0
0x18004e83b  add     qword ptr [rcx+8], 10h
0x18004e840  jmp     short loc_18004E84B
0x18004e842  lea     r8, [rbp+380h+var_320]
0x18004e846  call    ??$_Emplace_reallocate@AEBUSmsReadMsgData@@@?$vector@USmsReadMsgData@@V?$allocator@USmsReadMsgData@@@std@@@std@@AEAAPEAUSmsReadMsgData@@QEAU2@AEBU2@@Z; std::vector<SmsReadMsgData>::_Emplace_reallocate<SmsReadMsgData const &>(SmsReadMsgData * const,SmsReadMsgData const &)
0x18004e84b  mov     r9d, [r12+4]
0x18004e850  test    r9d, r9d
0x18004e853  jnz     loc_18004EC58
0x18004e859  cmp     qword ptr [r13+338h], 0FFFFFFFFFFFFFFFFh
0x18004e861  jz      loc_18004EC25
0x18004e867  mov     edi, [rbp+380h+var_378]
0x18004e86a  cmp     [rbp+380h+var_374], r9d
0x18004e86e  jnz     short loc_18004E881
0x18004e870  cmp     edi, [rbp+380h+var_37C]
0x18004e873  ja      loc_18004EBD7
0x18004e879  test    edi, edi
0x18004e87b  jz      loc_18004EBD7
0x18004e881  cmp     dword ptr [rbp+380h+var_3C0], 40h ; '@'
0x18004e885  ja      loc_18004EBD7
0x18004e88b  lea     rsi, [r13+2B8h]
0x18004e892  mov     r8d, r14d; int
0x18004e895  lea     rdx, [rbp+380h+var_3C0]; struct SmsFragmentInfo *
0x18004e899  mov     rcx, rsi; this
0x18004e89c  call    ?HandleDuplicateMessage@CSmsConcatenateStore@@AEAAHPEAUSmsFragmentInfo@@H@Z; CSmsConcatenateStore::HandleDuplicateMessage(SmsFragmentInfo *,int)
  ... truncated ...
```
