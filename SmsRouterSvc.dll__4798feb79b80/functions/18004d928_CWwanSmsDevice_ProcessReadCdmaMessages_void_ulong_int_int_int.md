# CWwanSmsDevice::ProcessReadCdmaMessages(void *,ulong,int,int,int)

- ea: `0x18004d928`
- end: `0x18004e36f`
- name: `?ProcessReadCdmaMessages@CWwanSmsDevice@@AEAAXPEAXKHHH@Z`
- size: `2631`
- prototype: `void __usercall(CWwanSmsDevice *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, int@<r9d>, int, int)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004c268`
- `0x18004cb00`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180004912`
- `0x180004998`
- `0x1800069f0`
- `0x180006c84`
- `0x18000cfe8`
- `0x18000e05c`
- `0x18000e534`
- `0x18000e8c0`
- `0x180013a10`
- `0x180013d40`
- `0x180027cb4`
- `0x180027f4c`
- `0x18004885c`
- `0x18004982c`
- `0x18004a8d0`
- `0x18004b2e4`
- `0x18004d1d8`
- `0x18004d928`
- `0x18004ef50`
- `0x180051420`
- `0x180051628`
- `0x180051980`
- `0x180053ba4`
- `0x180058d30`
- `0x18005f580`
- `0x18005faac`
- `0x1800609fc`
- `0x18006133c`
- `0x1800614e8`
- `0x180061e78`
- `0x18006adac`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18004db5b`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18004db5b`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004df35`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004df35`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004de86`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004dedb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004df1a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004de86`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004dedb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004df1a`

## string_xrefs

- `0x18004dab5`: `Incoming cdmatext message for iccid=%S, MessageIndex=%d, VoiceDomain=%d.`
- `0x18004e07e`: `Received incoming message segment type=%d, partindex=%d, totalparts=%d, uid=%s.`
- `0x18004dac1`: `CWwanSmsDevice::ProcessReadCdmaMessages`
- `0x18004e08a`: `CWwanSmsDevice::ProcessReadCdmaMessages`
- `0x18004e131`: `CWwanSmsDevice::ProcessReadCdmaMessages`
- `0x18004e17d`: `CWwanSmsDevice::ProcessReadCdmaMessages`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CWwanSmsDevice::ProcessReadCdmaMessages(
        CWwanSmsDevice *this,
        char *a2,
        unsigned int a3,
        int a4,
        int a5)
{
  char *v8; // r15
  __int64 v9; // r8
  __int64 v10; // r8
  _QWORD *v11; // rbx
  const wchar_t *v12; // r9
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // r13d
  struct _SYSTEMTIME v15; // xmm6
  CWwanSmsDevice *v16; // rcx
  _BYTE *v17; // rdx
  __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  _WORD *v21; // rcx
  __int16 v22; // r9
  int v23; // ebx
  const char *DisplayString; // rax
  void *v25; // rax
  struct SmsStoreItem_tag *v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  _OWORD *v29; // rcx
  int *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // r14d
  volatile signed __int32 *v34; // rbx
  const char *v35; // rax
  volatile signed __int32 *v36; // rbx
  const char *v37; // rax
  const wchar_t *v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  unsigned int *v41; // r14
  __int64 v42; // rdx
  __int64 v43; // [rsp+30h] [rbp-D8h]
  int v44; // [rsp+48h] [rbp-C0h]
  unsigned int *v47; // [rsp+58h] [rbp-B0h]
  struct _SYSTEMTIME v48; // [rsp+68h] [rbp-A0h]
  struct SmsStoreItem_tag *v49; // [rsp+88h] [rbp-80h] BYREF
  volatile signed __int32 *v50; // [rsp+90h] [rbp-78h]
  void **v51; // [rsp+98h] [rbp-70h]
  char *v52; // [rsp+A0h] [rbp-68h]
  struct _SYSTEMTIME v53; // [rsp+A8h] [rbp-60h] BYREF
  char v54[16]; // [rsp+B8h] [rbp-50h] BYREF
  char v55[8]; // [rsp+C8h] [rbp-40h] BYREF
  char v56[128]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int8 v57[104]; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int8 v58[16]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v59; // [rsp+1C8h] [rbp+C0h]
  __int128 v60; // [rsp+1D8h] [rbp+D0h]
  __int128 v61; // [rsp+1E8h] [rbp+E0h]
  __int128 v62; // [rsp+1F8h] [rbp+F0h]
  __int128 v63; // [rsp+208h] [rbp+100h] BYREF
  __int64 v64; // [rsp+218h] [rbp+110h]
  unsigned __int64 v65; // [rsp+220h] [rbp+118h]
  struct _SYSTEMTIME v66; // [rsp+228h] [rbp+120h] BYREF
  __int128 v67; // [rsp+248h] [rbp+140h] BYREF
  unsigned __int16 *v68[2]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v69; // [rsp+268h] [rbp+160h]
  unsigned __int64 v70; // [rsp+270h] [rbp+168h]
  __int128 v71; // [rsp+278h] [rbp+170h] BYREF
  __int64 v72; // [rsp+288h] [rbp+180h]
  __int64 v73; // [rsp+290h] [rbp+188h]
  _OWORD v74[3]; // [rsp+298h] [rbp+190h] BYREF
  __int128 v75; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int64 v76; // [rsp+2D8h] [rbp+1D0h]
  __int64 v77; // [rsp+2E0h] [rbp+1D8h]
  __int128 v78; // [rsp+2E8h] [rbp+1E0h] BYREF
  char v79[56]; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int64 v80; // [rsp+330h] [rbp+228h]
  int v81; // [rsp+338h] [rbp+230h] BYREF
  unsigned __int8 v82; // [rsp+33Ch] [rbp+234h]
  __int128 v83; // [rsp+33Dh] [rbp+235h]
  __int128 v84; // [rsp+34Dh] [rbp+245h]
  __int128 v85; // [rsp+35Dh] [rbp+255h]
  __int128 v86; // [rsp+36Dh] [rbp+265h]
  __int128 v87; // [rsp+37Dh] [rbp+275h]
  __int128 v88; // [rsp+38Dh] [rbp+285h]
  __int128 v89; // [rsp+39Dh] [rbp+295h]
  __int128 v90; // [rsp+3ADh] [rbp+2A5h]
  __int128 v91; // [rsp+3BDh] [rbp+2B5h]
  __int128 v92; // [rsp+3CDh] [rbp+2C5h]
  __int128 v93; // [rsp+3DDh] [rbp+2D5h]
  __int128 v94; // [rsp+3EDh] [rbp+2E5h]
  __int128 v95; // [rsp+3FDh] [rbp+2F5h]
  __int128 v96; // [rsp+40Dh] [rbp+305h]
  _OWORD v97[18]; // [rsp+41Dh] [rbp+315h]

  *(_OWORD *)v68 = 0;
  v69 = 0;
  v70 = 7;
  LOWORD(v68[0]) = 0;
  v75 = 0;
  v76 = 0;
  v77 = 7;
  LOWORD(v75) = 0;
  v63 = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(v63) = 0;
  v71 = 0;
  v72 = 0;
  v73 = 7;
  LOWORD(v71) = 0;
  v8 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  std::wstring::operator=((__int64)v68, (_QWORD *)this + 68, v9);
  std::wstring::operator=((__int64)&v63, (_QWORD *)this + 72, v10);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  v44 = 0;
  if ( a3 )
  {
    v11 = (_QWORD *)((char *)this + 448);
    while ( 1 )
    {
      *(_DWORD *)v58 = 0;
      memset_0(&v58[4], 0, 0x4Cu);
      memset_0(&v81, 0, 0x208u);
      v47 = (unsigned int *)a2;
      v12 = (const wchar_t *)&v63;
      if ( v65 > 7 )
        v12 = (const wchar_t *)v63;
      LogSmsRouterInfo(
        "CWwanSmsDevice::ProcessReadCdmaMessages",
        0x636u,
        "Incoming cdmatext message for iccid=%S, MessageIndex=%d, VoiceDomain=%d.",
        v12,
        *(_DWORD *)a2,
        *((_DWORD *)this + 168));
      v13 = (const unsigned __int16 *)v68;
      if ( v70 > 7 )
        v13 = v68[0];
      v14 = *((_DWORD *)SmsEncodingHelper::GetPSPerIMSIConfig(v13) + 19);
      SetUniqueMessageId((struct SmsFragmentInfo *)v58);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v54);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, a2 + 8);
      std::basic_stringbuf<unsigned short>::str(v56, &v66);
      std::wstring::operator=(&v71, &v66);
      std::wstring::~wstring((char **)&v66);
      v15 = *DecodeCdmaTimeStamp(&v53, (const unsigned __int8 *)a2 + 58);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v57);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v57);
      v51 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
      v52 = v8;
      (**(void (__fastcall ***)(char *))v8)(v8);
      DWORD1(v67) = 0;
      LODWORD(v67) = *(_DWORD *)a2;
      v66 = v15;
      *((_QWORD *)&v67 + 1) = CWwanSmsDevice::GetDateTimeFromSystemTime(v16, &v66);
      v17 = (_BYTE *)v11[1];
      if ( v17 == (_BYTE *)v11[2] )
      {
        std::vector<SmsReadMsgData>::_Emplace_reallocate<SmsReadMsgData const &>(v11, v17, &v67);
      }
      else
      {
        *(_OWORD *)v17 = v67;
        v11[1] += 16LL;
      }
      if ( *((_QWORD *)this + 103) == -1 )
      {
        CWwanSmsDevice::MaintainSmsListAtHalfFull(this, 0);
        v38 = (const wchar_t *)&v63;
        if ( v65 > 7 )
          v38 = (const wchar_t *)v63;
        LogSmsRouterError(
          "CWwanSmsDevice::ProcessReadCdmaMessages",
          0x66Au,
          -2147418113,
          "Shutdown while processing cdma message for iccid: %S",
          v38);
        goto LABEL_65;
      }
      memset(v74, 0, 44);
      v81 = 252;
      v82 = 2;
      DWORD2(v74[2]) = *(_DWORD *)a2;
      v18 = (__int16 *)&v63;
      if ( v65 > 7 )
        v18 = (__int16 *)v63;
      v19 = 20;
      v20 = 2147483646;
      v21 = v74;
      while ( v20 )
      {
        v22 = *v18;
        if ( *v18 )
        {
          ++v18;
          *v21++ = v22;
          --v20;
          if ( --v19 )
            continue;
        }
        if ( !v19 )
          --v21;
        break;
      }
      *v21 = 0;
      v83 = *(_OWORD *)a2;
      v84 = *((_OWORD *)a2 + 1);
      v85 = *((_OWORD *)a2 + 2);
      v86 = *((_OWORD *)a2 + 3);
      v87 = *((_OWORD *)a2 + 4);
      v88 = *((_OWORD *)a2 + 5);
      v89 = *((_OWORD *)a2 + 6);
      v90 = *((_OWORD *)a2 + 7);
      v91 = *((_OWORD *)a2 + 8);
      v92 = *((_OWORD *)a2 + 9);
      v93 = *((_OWORD *)a2 + 10);
      v94 = *((_OWORD *)a2 + 11);
      v95 = *((_OWORD *)a2 + 12);
      v96 = *((_OWORD *)a2 + 13);
      v97[0] = *((_OWORD *)a2 + 14);
      *(_OWORD *)((char *)v97 + 12) = *(_OWORD *)(a2 + 236);
      v23 = DWORD2(v62);
      if ( !HIDWORD(v62) && (DWORD2(v62) > DWORD1(v62) || !DWORD2(v62)) )
        break;
      if ( *(_DWORD *)v58 > 0x40u )
        break;
      if ( (unsigned int)CSmsConcatenateStore::HandleDuplicateMessage(
                           (CWwanSmsDevice *)((char *)this + 696),
                           (struct SmsFragmentInfo *)v58,
                           v14) )
      {
        DisplayString = GetDisplayString(&v58[4], *(unsigned int *)v58);
        LogSmsRouterInfo(
          "CSmsConcatenateStore::Add",
          0x22Du,
          "Duplicate message partindex=%d, totalparts=%d, uid=%s, IccId=%S",
          DWORD2(v62),
          DWORD1(v62),
          DisplayString,
          (const wchar_t *)v74);
      }
      else
      {
        v25 = operator new(0x298u);
        std::shared_ptr<SmsStoreItem_tag>::shared_ptr<SmsStoreItem_tag>(&v49, v25);
        v26 = v49;
        if ( !v49 )
        {
          v36 = v50;
          if ( v50 )
          {
            if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
              if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
            }
          }
          v33 = -2147024882;
LABEL_58:
          v23 = DWORD2(v62);
LABEL_60:
          v37 = GetDisplayString(&v58[4], *(unsigned int *)v58);
          LogSmsRouterError(
            "CWwanSmsDevice::ProcessReadCdmaMessages",
            0x65Du,
            v33,
            "Failed to save message segment type=%d, partindex=%d, totalparts=%d, uid=%s.",
            v82,
            v23,
            DWORD1(v62),
            v37);
          goto LABEL_61;
        }
        memset_0(v49, 0, 0x298u);
        *(_DWORD *)v26 = 664;
        *((_DWORD *)v26 + 1) = v14 != 0 ? 3 : 1;
        v29 = (_OWORD *)((char *)v26 + 8);
        if ( v26 == (struct SmsStoreItem_tag *)-8LL )
        {
          *(_DWORD *)_o__errno(v29, v27, v28) = 22;
          invalid_parameter_noinfo();
        }
        else
        {
          v30 = &v81;
          v31 = 4;
          v32 = 128;
          do
          {
            *v29 = *(_OWORD *)v30;
            v29[1] = *((_OWORD *)v30 + 1);
            v29[2] = *((_OWORD *)v30 + 2);
            v29[3] = *((_OWORD *)v30 + 3);
            v29[4] = *((_OWORD *)v30 + 4);
            v29[5] = *((_OWORD *)v30 + 5);
            v29[6] = *((_OWORD *)v30 + 6);
            v29[7] = *((_OWORD *)v30 + 7);
            v29 += 8;
            v30 += 32;
            --v31;
          }
          while ( v31 );
          *(_QWORD *)v29 = *(_QWORD *)v30;
        }
        if ( v26 == (struct SmsStoreItem_tag *)-528LL )
        {
          *(_DWORD *)_o__errno(v29, v31, v32) = 22;
          invalid_parameter_noinfo();
        }
        else
        {
          *((_OWORD *)v26 + 33) = *(_OWORD *)v58;
          *((_OWORD *)v26 + 34) = v59;
          *((_OWORD *)v26 + 35) = v60;
          *((_OWORD *)v26 + 36) = v61;
          *((_OWORD *)v26 + 37) = v62;
        }
        if ( v26 == (struct SmsStoreItem_tag *)-608LL )
        {
          *(_DWORD *)_o__errno(v29, v31, v32) = 22;
          invalid_parameter_noinfo();
        }
        else
        {
          *((_OWORD *)v26 + 38) = v74[0];
          *((_OWORD *)v26 + 39) = v74[1];
          *(_OWORD *)((char *)v26 + 636) = *(_OWORD *)((char *)&v74[1] + 12);
        }
        _time64((__time64_t *)v26 + 82);
        CSmsConcatenateStore::GetNextAvailableFreeLocation((CWwanSmsDevice *)((char *)this + 696));
        if ( *(_QWORD *)&v48.wYear )
        {
          **(_QWORD **)&v48.wYear = *((_QWORD *)v26 + 82);
          v33 = CSmsConcatenateStore::SaveMessage(
                  (CWwanSmsDevice *)((char *)this + 696),
                  *(_DWORD *)(*(_QWORD *)&v48.wYear + 8LL),
                  v26);
          if ( v33 >= 0 )
          {
            v66 = 0;
            if ( *(_QWORD *)&v48.wHour )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v48.wHour + 8LL));
            v66 = v48;
            v33 = CSmsConcatenateStore::AddInternal((char *)this + 696, v58, &v66, v14);
          }
        }
        else
        {
          v33 = -2147024882;
        }
        if ( *(_QWORD *)&v48.wHour )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v48.wHour + 8LL), 0xFFFFFFFF) == 1 )
          {
            (***(void (__fastcall ****)())&v48.wHour)();
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v48.wHour + 12LL), 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)())(**(_QWORD **)&v48.wHour + 8LL))();
          }
        }
        v34 = v50;
        if ( v50 )
        {
          if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          }
        }
        if ( v33 < 0 )
          goto LABEL_58;
      }
      v35 = GetDisplayString(&v58[4], *(unsigned int *)v58);
      LogSmsRouterInfo(
        "CWwanSmsDevice::ProcessReadCdmaMessages",
        0x652u,
        "Received incoming message segment type=%d, partindex=%d, totalparts=%d, uid=%s.",
        v82,
        DWORD2(v62),
        DWORD1(v62),
        v35);
LABEL_61:
      v11 = (_QWORD *)((char *)this + 448);
LABEL_65:
      v51 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      a2 += 252;
      if ( a4 )
      {
        (**(void (__fastcall ***)(char *))v8)(v8);
        if ( *((_QWORD *)this + 103) == -1 )
        {
          v41 = v47;
        }
        else
        {
          v78 = 0;
          v80 = 0;
          v39 = operator new(0x18u);
          *v39 = 0;
          v39[1] = 0;
          v39[2] = 0;
          std::shared_ptr<std::vector<unsigned char>>::reset<std::vector<unsigned char>,0>(&v78, v39);
          std::vector<unsigned char>::resize(v78, 32);
          v40 = *(_QWORD *)v78;
          *(_DWORD *)(v40 + 16) = 1;
          *(_DWORD *)(v40 + 20) = 4;
          v41 = v47;
          *(_DWORD *)(v40 + 24) = *v47;
          *(_OWORD *)v40 = *(_OWORD *)((char *)this + 152);
          std::function<void (std::shared_ptr<std::vector<unsigned char>> &)>::operator=(v79, (char *)this + 840);
          CExecutionManager::ScheduleWorkItem(*((CExecutionManager **)this + 113), (struct CSmsWorkItem *)&v78);
          CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)&v78, v42);
        }
        v66 = v15;
        LODWORD(v43) = a5;
        CWwanSmsDevice::PublishSmsWNF(this, &v81, *v41, &v71, &v66, v43, v68);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      if ( ++v44 >= a3 )
        goto LABEL_71;
    }
    v33 = -2147024809;
    goto LABEL_60;
  }
LABEL_71:
  CWwanSmsDevice::ProcessPendingMessages(this);
  std::wstring::~wstring((char **)&v71);
  std::wstring::~wstring((char **)&v63);
  std::wstring::~wstring((char **)&v75);
  std::wstring::~wstring((char **)v68);
}

```

## disassembly

```asm
0x18004d928  mov     rax, rsp
0x18004d92b  mov     [rax+18h], rbx
0x18004d92f  push    rbp
0x18004d930  push    rsi
0x18004d931  push    rdi
0x18004d932  push    r12
0x18004d934  push    r13
0x18004d936  push    r14
0x18004d938  push    r15
0x18004d93a  lea     rbp, [rax-498h]
0x18004d941  sub     rsp, 560h
0x18004d948  movaps  xmmword ptr [rax-48h], xmm6
0x18004d94c  mov     rax, cs:__security_cookie
0x18004d953  xor     rax, rsp
0x18004d956  mov     [rbp+490h+var_50], rax
0x18004d95d  mov     [rsp+590h+var_54C], r9d
0x18004d962  mov     ebx, r8d
0x18004d965  mov     dword ptr [rsp+590h+var_548], ebx
0x18004d969  mov     rdi, rdx
0x18004d96c  mov     rsi, rcx
0x18004d96f  xor     r12d, r12d
0x18004d972  xorps   xmm0, xmm0
0x18004d975  movups  xmmword ptr [rbp+490h+var_340], xmm0
0x18004d97c  mov     [rbp+490h+var_330], r12
0x18004d983  lea     r14d, [r12+7]
0x18004d988  mov     [rbp+490h+var_328], r14
0x18004d98f  mov     word ptr [rbp+490h+var_340], r12w
0x18004d997  movups  [rbp+490h+var_2D0], xmm0
0x18004d99e  mov     [rbp+490h+var_2C0], r12
0x18004d9a5  mov     [rbp+490h+var_2B8], r14
0x18004d9ac  mov     word ptr [rbp+490h+var_2D0], r12w
0x18004d9b4  movups  [rbp+490h+var_390], xmm0
0x18004d9bb  mov     [rbp+490h+var_380], r12
0x18004d9c2  mov     [rbp+490h+var_378], r14
0x18004d9c9  mov     word ptr [rbp+490h+var_390], r12w
0x18004d9d1  movups  [rbp+490h+var_320], xmm0
0x18004d9d8  mov     [rbp+490h+var_310], r12
0x18004d9df  mov     [rbp+490h+var_308], r14
0x18004d9e6  mov     word ptr [rbp+490h+var_320], r12w
0x18004d9ee  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004d9f5  mov     [rsp+590h+var_520], rax
0x18004d9fa  lea     r15, [rcx+20h]
0x18004d9fe  mov     [rsp+590h+var_518], r15
0x18004da03  mov     rax, [r15]
0x18004da06  mov     rcx, r15
0x18004da09  mov     rax, [rax]
0x18004da0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da11  nop
0x18004da12  lea     rdx, [rsi+220h]
0x18004da19  lea     rcx, [rbp+490h+var_340]
0x18004da20  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004da25  lea     rdx, [rsi+240h]
0x18004da2c  lea     rcx, [rbp+490h+var_390]
0x18004da33  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004da38  nop
0x18004da39  mov     rax, [r15]
0x18004da3c  mov     rcx, r15
0x18004da3f  mov     rax, [rax+8]
0x18004da43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da48  nop
0x18004da49  mov     [rsp+590h+var_550], r12d
0x18004da4e  test    ebx, ebx
0x18004da50  jz      loc_18004E304
0x18004da56  lea     rbx, [rsi+1C0h]
0x18004da5d  mov     dword ptr [rbp+490h+var_3E0], r12d
0x18004da64  xor     edx, edx; Val
0x18004da66  lea     r8d, [rdx+4Ch]; Size
0x18004da6a  lea     rcx, [rbp+490h+var_3E0+4]; void *
0x18004da71  call    memset_0
0x18004da76  xor     edx, edx; Val
0x18004da78  mov     r8d, 208h; Size
0x18004da7e  lea     rcx, [rbp+490h+var_260]; void *
0x18004da85  call    memset_0
0x18004da8a  mov     [rsp+590h+var_540], rdi
0x18004da8f  mov     eax, [rsi+2A0h]
0x18004da95  mov     ecx, [rdi]
0x18004da97  lea     r9, [rbp+490h+var_390]
0x18004da9e  cmp     [rbp+490h+var_378], r14
0x18004daa5  cmova   r9, qword ptr [rbp+490h+var_390]
0x18004daad  mov     dword ptr [rsp+590h+var_568], eax
0x18004dab1  mov     dword ptr [rsp+590h+var_570], ecx
0x18004dab5  lea     r8, aIncomingCdmate; "Incoming cdmatext message for iccid=%S,"...
0x18004dabc  mov     edx, 636h; unsigned int
0x18004dac1  lea     rcx, aCwwansmsdevice_15; "CWwanSmsDevice::ProcessReadCdmaMessages"
0x18004dac8  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004dacd  lea     rcx, [rbp+490h+var_340]
0x18004dad4  cmp     [rbp+490h+var_328], r14
0x18004dadb  cmova   rcx, [rbp+490h+var_340]; unsigned __int16 *
0x18004dae3  call    ?GetPSPerIMSIConfig@SmsEncodingHelper@@SAPEAU_SPerIMSIConfig@@PEBG@Z; SmsEncodingHelper::GetPSPerIMSIConfig(ushort const *)
0x18004dae8  mov     r13d, [rax+4Ch]
0x18004daec  lea     rcx, [rbp+490h+var_3E0]; struct SmsFragmentInfo *
0x18004daf3  call    ?SetUniqueMessageId@@YAXPEAUSmsFragmentInfo@@@Z; SetUniqueMessageId(SmsFragmentInfo *)
0x18004daf8  lea     rcx, [rbp+490h+var_4E0]
0x18004dafc  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18004db01  nop
0x18004db02  lea     rdx, [rdi+8]
0x18004db06  lea     rcx, [rbp+490h+var_4D0]
0x18004db0a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004db0f  lea     rdx, [rbp+490h+var_370]
0x18004db16  lea     rcx, [rbp+490h+var_4C8]
0x18004db1a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18004db1f  lea     rdx, [rbp+490h+var_370]
0x18004db26  lea     rcx, [rbp+490h+var_320]
0x18004db2d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004db32  lea     rcx, [rbp+490h+var_370]; void *
0x18004db39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004db3e  lea     rdx, [rdi+3Ah]; unsigned __int8 *
0x18004db42  lea     rcx, [rbp+490h+var_4F0]; retstr
0x18004db46  call    ?DecodeCdmaTimeStamp@@YA?AU_SYSTEMTIME@@PEBE@Z; DecodeCdmaTimeStamp(uchar const *)
0x18004db4b  movups  xmm6, xmmword ptr [rax]
0x18004db4e  lea     rcx, [rbp+490h+var_448]
0x18004db52  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18004db57  lea     rcx, [rbp+490h+var_448]
0x18004db5b  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18004db61  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004db68  mov     [rbp+490h+var_500], rax
0x18004db6c  mov     [rbp+490h+var_4F8], r15
0x18004db70  mov     rax, [r15]
0x18004db73  mov     rcx, r15
0x18004db76  mov     rax, [rax]
0x18004db79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db7e  nop
0x18004db7f  mov     dword ptr [rbp+490h+var_350+4], r12d
0x18004db86  mov     eax, [rdi]
0x18004db88  mov     dword ptr [rbp+490h+var_350], eax
0x18004db8e  movdqa  xmmword ptr [rbp+490h+var_370.wYear], xmm6
0x18004db96  lea     rdx, [rbp+490h+var_370]; struct _SYSTEMTIME
0x18004db9d  call    ?GetDateTimeFromSystemTime@CWwanSmsDevice@@AEAA_KU_SYSTEMTIME@@@Z; CWwanSmsDevice::GetDateTimeFromSystemTime(_SYSTEMTIME)
0x18004dba2  mov     qword ptr [rbp+490h+var_350+8], rax
0x18004dba9  mov     rdx, [rbx+8]
0x18004dbad  cmp     rdx, [rbx+10h]
0x18004dbb1  jz      short loc_18004DBC5
0x18004dbb3  movups  xmm0, [rbp+490h+var_350]
0x18004dbba  movdqu  xmmword ptr [rdx], xmm0
0x18004dbbe  add     qword ptr [rbx+8], 10h
0x18004dbc3  jmp     short loc_18004DBD4
0x18004dbc5  lea     r8, [rbp+490h+var_350]
0x18004dbcc  mov     rcx, rbx
0x18004dbcf  call    ??$_Emplace_reallocate@AEBUSmsReadMsgData@@@?$vector@USmsReadMsgData@@V?$allocator@USmsReadMsgData@@@std@@@std@@AEAAPEAUSmsReadMsgData@@QEAU2@AEBU2@@Z; std::vector<SmsReadMsgData>::_Emplace_reallocate<SmsReadMsgData const &>(SmsReadMsgData * const,SmsReadMsgData const &)
0x18004dbd4  cmp     qword ptr [rsi+338h], 0FFFFFFFFFFFFFFFFh
0x18004dbdc  jz      loc_18004E146
0x18004dbe2  xorps   xmm0, xmm0
0x18004dbe5  movups  [rbp+490h+var_300], xmm0
0x18004dbec  movups  [rbp+490h+var_2F0], xmm0
0x18004dbf3  movups  [rbp+490h+var_2F0+0Ch], xmm0
0x18004dbfa  mov     [rbp+490h+var_260], 0FCh
0x18004dc04  mov     [rbp+490h+var_25C], 2
0x18004dc0b  mov     eax, [rdi]
0x18004dc0d  mov     [rbp+490h+var_2D8], eax
0x18004dc13  lea     rax, [rbp+490h+var_390]
0x18004dc1a  cmp     [rbp+490h+var_378], r14
0x18004dc21  cmova   rax, qword ptr [rbp+490h+var_390]
0x18004dc29  mov     edx, 14h
0x18004dc2e  mov     r8d, 7FFFFFFEh
0x18004dc34  lea     rcx, [rbp+490h+var_300]
0x18004dc3b  test    r8, r8
0x18004dc3e  jz      short loc_18004DC68
0x18004dc40  movzx   r9d, word ptr [rax]
0x18004dc44  test    r9w, r9w
0x18004dc48  jz      short loc_18004DC5F
0x18004dc4a  add     rax, 2
0x18004dc4e  mov     [rcx], r9w
0x18004dc52  add     rcx, 2
0x18004dc56  dec     r8
0x18004dc59  sub     rdx, 1
0x18004dc5d  jnz     short loc_18004DC3B
0x18004dc5f  test    rdx, rdx
0x18004dc62  jnz     short loc_18004DC68
0x18004dc64  sub     rcx, 2
0x18004dc68  mov     [rcx], r12w
0x18004dc6c  movups  xmm0, xmmword ptr [rdi]
0x18004dc6f  movups  [rbp+490h+var_25B], xmm0
0x18004dc76  movups  xmm1, xmmword ptr [rdi+10h]
0x18004dc7a  movups  [rbp+490h+var_24B], xmm1
0x18004dc81  movups  xmm0, xmmword ptr [rdi+20h]
0x18004dc85  movups  [rbp+490h+var_23B], xmm0
0x18004dc8c  movups  xmm1, xmmword ptr [rdi+30h]
0x18004dc90  movups  [rbp+490h+var_22B], xmm1
0x18004dc97  movups  xmm0, xmmword ptr [rdi+40h]
0x18004dc9b  movups  [rbp+490h+var_21B], xmm0
0x18004dca2  movups  xmm1, xmmword ptr [rdi+50h]
0x18004dca6  movups  [rbp+490h+var_20B], xmm1
0x18004dcad  movups  xmm0, xmmword ptr [rdi+60h]
0x18004dcb1  movups  [rbp+490h+var_1FB], xmm0
0x18004dcb8  movups  xmm1, xmmword ptr [rdi+70h]
0x18004dcbc  movups  [rbp+490h+var_1EB], xmm1
0x18004dcc3  movups  xmm0, xmmword ptr [rdi+80h]
0x18004dcca  movups  [rbp+490h+var_1DB], xmm0
0x18004dcd1  movups  xmm1, xmmword ptr [rdi+90h]
0x18004dcd8  movups  [rbp+490h+var_1CB], xmm1
0x18004dcdf  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18004dce6  movups  [rbp+490h+var_1BB], xmm0
0x18004dced  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18004dcf4  movups  [rbp+490h+var_1AB], xmm1
0x18004dcfb  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18004dd02  movups  [rbp+490h+var_19B], xmm0
0x18004dd09  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18004dd10  movups  [rbp+490h+var_18B], xmm1
0x18004dd17  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18004dd1e  movups  [rbp+490h+var_17B], xmm0
0x18004dd25  movups  xmm1, xmmword ptr [rdi+0ECh]
0x18004dd2c  movups  [rbp+490h+var_17B+0Ch], xmm1
0x18004dd33  mov     ebx, [rbp+490h+var_398]
0x18004dd39  cmp     [rbp+490h+var_394], r12d
0x18004dd40  jnz     short loc_18004DD56
0x18004dd42  cmp     ebx, [rbp+490h+var_39C]
0x18004dd48  ja      loc_18004E0EC
0x18004dd4e  test    ebx, ebx
0x18004dd50  jz      loc_18004E0EC
0x18004dd56  cmp     dword ptr [rbp+490h+var_3E0], 40h ; '@'
0x18004dd5d  ja      loc_18004E0EC
0x18004dd63  lea     r12, [rsi+2B8h]
0x18004dd6a  mov     r8d, r13d; int
0x18004dd6d  lea     rdx, [rbp+490h+var_3E0]; struct SmsFragmentInfo *
0x18004dd74  mov     rcx, r12; this
0x18004dd77  call    ?HandleDuplicateMessage@CSmsConcatenateStore@@AEAAHPEAUSmsFragmentInfo@@H@Z; CSmsConcatenateStore::HandleDuplicateMessage(SmsFragmentInfo *,int)
0x18004dd7c  test    eax, eax
0x18004dd7e  jz      short loc_18004DDD4
0x18004dd80  mov     edx, dword ptr [rbp+490h+var_3E0]; unsigned int
0x18004dd86  lea     rcx, [rbp+490h+var_3E0+4]; unsigned __int8 *
0x18004dd8d  call    ?GetDisplayString@@YAPEBDPEAEK@Z; GetDisplayString(uchar *,ulong)
0x18004dd92  lea     rcx, [rbp+490h+var_300]
0x18004dd99  mov     [rsp+590h+var_560], rcx
0x18004dd9e  mov     [rsp+590h+var_568], rax
0x18004dda3  mov     eax, [rbp+490h+var_39C]
0x18004dda9  mov     dword ptr [rsp+590h+var_570], eax
0x18004ddad  mov     r9d, [rbp+490h+var_398]
0x18004ddb4  lea     r8, aDuplicateMessa; "Duplicate message partindex=%d, totalpa"...
0x18004ddbb  mov     edx, 22Dh; unsigned int
0x18004ddc0  lea     rcx, aCsmsconcatenat_0; "CSmsConcatenateStore::Add"
0x18004ddc7  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004ddcc  xor     r12d, r12d
0x18004ddcf  jmp     loc_18004E04B
0x18004ddd4  mov     r14d, 298h
0x18004ddda  mov     ecx, r14d; Size
0x18004dddd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004dde2  mov     rdx, rax
0x18004dde5  lea     rcx, [rbp+490h+var_510]
0x18004dde9  call    ??$?0USmsStoreItem_tag@@$0A@@?$shared_ptr@USmsStoreItem_tag@@@std@@QEAA@PEAUSmsStoreItem_tag@@@Z; std::shared_ptr<SmsStoreItem_tag>::shared_ptr<SmsStoreItem_tag>(SmsStoreItem_tag *)
0x18004ddee  nop
0x18004ddef  mov     rbx, [rbp+490h+var_510]
0x18004ddf3  test    rbx, rbx
0x18004ddf6  jz      loc_18004E09B
0x18004ddfc  mov     r8d, r14d; Size
0x18004ddff  xor     edx, edx; Val
0x18004de01  mov     rcx, rbx; void *
0x18004de04  call    memset_0
0x18004de09  mov     [rbx], r14d
0x18004de0c  mov     eax, r13d
0x18004de0f  neg     eax
0x18004de11  sbb     ecx, ecx
0x18004de13  and     ecx, 2
0x18004de16  inc     ecx
0x18004de18  mov     [rbx+4], ecx
0x18004de1b  lea     rcx, [rbx+8]
0x18004de1f  test    rcx, rcx
0x18004de22  jz      short loc_18004DE86
0x18004de24  lea     rax, [rbp+490h+var_260]
0x18004de2b  mov     edx, 4
0x18004de30  lea     r8d, [rdx+7Ch]
0x18004de34  movups  xmm0, xmmword ptr [rax]
0x18004de37  movups  xmmword ptr [rcx], xmm0
0x18004de3a  movups  xmm1, xmmword ptr [rax+10h]
0x18004de3e  movups  xmmword ptr [rcx+10h], xmm1
0x18004de42  movups  xmm0, xmmword ptr [rax+20h]
0x18004de46  movups  xmmword ptr [rcx+20h], xmm0
0x18004de4a  movups  xmm1, xmmword ptr [rax+30h]
0x18004de4e  movups  xmmword ptr [rcx+30h], xmm1
0x18004de52  movups  xmm0, xmmword ptr [rax+40h]
0x18004de56  movups  xmmword ptr [rcx+40h], xmm0
0x18004de5a  movups  xmm1, xmmword ptr [rax+50h]
0x18004de5e  movups  xmmword ptr [rcx+50h], xmm1
0x18004de62  movups  xmm0, xmmword ptr [rax+60h]
0x18004de66  movups  xmmword ptr [rcx+60h], xmm0
0x18004de6a  movups  xmm1, xmmword ptr [rax+70h]
0x18004de6e  movups  xmmword ptr [rcx+70h], xmm1
0x18004de72  add     rcx, r8
0x18004de75  add     rax, r8
0x18004de78  sub     rdx, 1
0x18004de7c  jnz     short loc_18004DE34
0x18004de7e  mov     rax, [rax]
0x18004de81  mov     [rcx], rax
0x18004de84  jmp     short loc_18004DE97
0x18004de86  call    cs:__imp__o__errno
0x18004de8c  mov     dword ptr [rax], 16h
0x18004de92  call    _invalid_parameter_noinfo
0x18004de97  lea     rax, [rbx+210h]
0x18004de9e  test    rax, rax
0x18004dea1  jz      short loc_18004DEDB
0x18004dea3  movaps  xmm0, xmmword ptr [rbp+490h+var_3E0]
0x18004deaa  movups  xmmword ptr [rax], xmm0
0x18004dead  movaps  xmm1, [rbp+490h+var_3D0]
0x18004deb4  movups  xmmword ptr [rax+10h], xmm1
0x18004deb8  movaps  xmm0, [rbp+490h+var_3C0]
0x18004debf  movups  xmmword ptr [rax+20h], xmm0
0x18004dec3  movaps  xmm1, [rbp+490h+var_3B0]
0x18004deca  movups  xmmword ptr [rax+30h], xmm1
0x18004dece  movaps  xmm0, xmmword ptr [rbp+0F0h]
0x18004ded5  movups  xmmword ptr [rax+40h], xmm0
0x18004ded9  jmp     short loc_18004DEEC
  ... truncated ...
```
