# WSManHttpSenderConnection::SendRequest(ulong,ulong,int,bool)

- ea: `0x18004a9b0`
- end: `0x18004bb5e`
- name: `?SendRequest@WSManHttpSenderConnection@@AEAAKKKH_N@Z`
- size: `4526`
- prototype: `unsigned int __usercall@<eax>(WSManHttpSenderConnection *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, int@<r9d>, bool)`
- caller_count: `7`
- callee_count: `28`
- tags: `service_task`

## callers

- `0x1800654b4`
- `0x180065ab8`
- `0x180066364`
- `0x180073620`
- `0x1800af400`
- `0x180101d98`
- `0x180131b08`

## callees

- `0x180005d10`
- `0x18002c580`
- `0x18004a9b0`
- `0x18004bb70`
- `0x18004e188`
- `0x180053ea8`
- `0x180055d98`
- `0x180065a7c`
- `0x180067150`
- `0x180076834`
- `0x1800afe6c`
- `0x1800bf830`
- `0x1800c9420`
- `0x1800fb3e0`
- `0x1800fee70`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011d870`
- `0x180123fa0`
- `0x1801296dc`
- `0x1801297b8`
- `0x18012c548`
- `0x18015a96c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004afd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004afd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b5cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b5cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ab8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ab8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abeb`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004abd7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004abd7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004ae2d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004ae2d`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b742`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b742`
- `WINHTTP!WinHttpWriteData` at `0x18004b5bf`
- `WINHTTP!WinHttpWriteData` at `0x18004b5bf`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004b8b2`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004b8b2`
- `WINHTTP!WinHttpOpenRequest` at `0x18004ab57`
- `WINHTTP!WinHttpOpenRequest` at `0x18004ab57`
- `WINHTTP!WinHttpSendRequest` at `0x18004aade`
- `WINHTTP!WinHttpSendRequest` at `0x18004b965`
- `WINHTTP!WinHttpSendRequest` at `0x18004aade`
- `WINHTTP!WinHttpSendRequest` at `0x18004b965`

## string_xrefs

- `0x18004aff5`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18004b027`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WSManHttpSenderConnection::SendRequest(
        WSManHttpSenderConnection *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        char a5)
{
  int v5; // r15d
  char v9; // si
  char v10; // r13
  __int64 LastError; // rdi
  PVOID *v12; // rcx
  char v13; // dl
  __int64 v14; // rax
  CHAR *v15; // rdi
  DWORD v16; // esi
  DWORD dwOptionalLength; // eax
  DWORD v19; // eax
  void *v20; // r15
  DWORD *v21; // rdi
  DWORD v22; // ecx
  Packet **v23; // r14
  const char *v24; // rdx
  DWORD LowPart; // r8d
  unsigned int *v26; // rsi
  _QWORD *v27; // rcx
  __int64 v28; // r15
  WSMan::Client::ProxyManager *v29; // rcx
  __int64 v30; // r9
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int ProxySelection; // eax
  int NegotiationAuthMode; // eax
  __int64 v35; // rbp
  void (__fastcall ***v36)(_QWORD, __int64); // rcx
  const char *v37; // r8
  unsigned int v38; // eax
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  LARGE_INTEGER v41; // rax
  __int64 v42; // rcx
  struct Packet *v43; // rax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  Packet *v46; // rcx
  struct Packet *v47; // rax
  unsigned int v48; // eax
  int v49; // eax
  PacketParser *v50; // rcx
  PacketParser *v51; // rcx
  int dwTotalLength; // [rsp+28h] [rbp-70h]
  LPCVOID lpBuffer; // [rsp+50h] [rbp-48h] BYREF
  int v54; // [rsp+58h] [rbp-40h]
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp+8h] BYREF
  int v56; // [rsp+B8h] [rbp+20h]

  v56 = a4;
  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qqddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      342,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      this,
      *((_QWORD *)this + 1),
      *((unsigned __int8 *)this + 9019),
      *((unsigned __int8 *)this + 11349),
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) == 2);
  if ( !*((_QWORD *)this + 1) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 6353, L"6353", 0x54Fu, 0);
  v9 = a5;
  *((_BYTE *)this + 11351) = a5;
  if ( *((_BYTE *)this + 9019) )
  {
    *((_BYTE *)this + 9019) = 0;
    if ( *((_BYTE *)this + 11349) )
    {
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
        *((_BYTE *)this + 9018) = 1;
      }
    }
  }
  if ( *((_BYTE *)this + 9018) && !*((_QWORD *)this + 1130) )
  {
    if ( !*((_QWORD *)this + 1) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 6387, L"6387", 0x54Fu, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 345, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
    PerformanceCount.QuadPart = 0;
    LODWORD(LastError) = FullDuplexChannel::BuildPacket(
                           *(_QWORD *)(*((_QWORD *)this + 1) + 16LL),
                           (struct Packet **)&PerformanceCount,
                           1u);
    if ( (_DWORD)LastError )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_128;
      v40 = 346;
      goto LABEL_139;
    }
    if ( *((_QWORD *)this + 1129) != *((_QWORD *)this + 1132) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 6411, L"6411", 0x54Fu, 0);
    *((_QWORD *)this + 1130) = *((_QWORD *)this + 1129);
    v41 = PerformanceCount;
    *((LARGE_INTEGER *)this + 1132) = PerformanceCount;
    *((LARGE_INTEGER *)this + 1129) = v41;
    *((_BYTE *)this + 11349) = 0;
    *((_BYTE *)this + 9016) = 1;
  }
  v10 = 0;
  if ( *((_BYTE *)this + 8254) && *((_BYTE *)this + 11349) && !*((_BYTE *)this + 11350) )
  {
    lpBuffer = 0;
    PerformanceCount.LowPart = 0;
    v23 = (Packet **)((char *)this + 9056);
    if ( !v9 || *v23 )
    {
      v42 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
      if ( (*(_BYTE *)(v42 + 896) & 1) != 0 || *(_DWORD *)(v42 + 528) == 2 || *((_BYTE *)this + 48) )
      {
        v43 = Packet::Clone(*((Packet **)this + 1129), 0);
        *v23 = v43;
        if ( !v43 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 350, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
          LODWORD(LastError) = 14;
          goto LABEL_141;
        }
      }
      else
      {
        NegotiationAuthMode = WSManHttpSenderConnection::GetNegotiationAuthMode(this);
        v35 = NegotiationAuthMode;
        a5 = 0;
        if ( NegotiationAuthMode == 3 )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
            6441,
            L"6441",
            0x54Fu,
            0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 348, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        v36 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1132);
        if ( v36 && v36 != *((void (__fastcall ****)(_QWORD, __int64))this + 1129) )
          (**v36)(v36, 1);
        *((_QWORD *)this + 1132) = 0;
        v37 = "UTF-16";
        if ( !*((_BYTE *)this + 54) )
          v37 = "UTF-8";
        LOBYTE(dwTotalLength) = 0;
        v38 = EncryptDecryptHelper::DoEncryption(
                (char *)this + 11332,
                (char *)this + 8328,
                *((_QWORD *)this + 1129),
                (char *)this + 9056,
                v37,
                dwTotalLength,
                *(&g_authStrings + 15 * v35 + 1),
                *((_DWORD *)&g_authStrings + 30 * v35 + 4),
                v35,
                &a5);
        LODWORD(LastError) = v38;
        if ( v38 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 349, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v38);
          WSManHttpSenderConnection::ResetNegotiationContext(this);
          goto LABEL_128;
        }
      }
      LODWORD(LastError) = PrepareChunk(v9, (struct Packet **)this + 1132);
      if ( (_DWORD)LastError )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_128;
        v40 = 351;
LABEL_139:
        WPP_SF_d(v39[2], v40, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, (unsigned int)LastError);
LABEL_128:
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1128) + 72LL))(
          *((_QWORD *)this + 1128),
          (unsigned int)LastError);
LABEL_141:
        v10 = 1;
        goto LABEL_46;
      }
      Packet::GetBuffer(*v23, (unsigned __int8 **)&lpBuffer, (unsigned int *)&PerformanceCount);
      v24 = (const char *)lpBuffer;
      LowPart = PerformanceCount.LowPart;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
      v24 = "0\r\n\r\n";
      LowPart = 5;
    }
    if ( !WinHttpWriteData(*((HINTERNET *)this + 1134), v24, LowPart, 0) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          352,
          &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          (unsigned int)LastError);
      goto LABEL_46;
    }
    return 0;
  }
  if ( !*((_QWORD *)this + 1033) )
  {
    v28 = *((_QWORD *)this + 5);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        *((_QWORD *)this + 5));
    v29 = *(WSMan::Client::ProxyManager **)(v28 + 144);
    if ( v29 )
    {
      ProxySelection = WSMan::Client::ProxyManager::GetProxySelection(
                         v29,
                         (struct WSMan::Client::ProxySelection **)this + 1033);
      LODWORD(LastError) = ProxySelection;
      if ( ProxySelection == 997 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_qq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            353,
            &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
            this,
            *((_QWORD *)this + 1));
        *((_BYTE *)this + 8272) = 1;
        return 0;
      }
      if ( ProxySelection )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1128) + 72LL))(
          *((_QWORD *)this + 1128),
          ProxySelection);
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_45;
        v45 = 354;
        goto LABEL_165;
      }
    }
    else
    {
      *((_QWORD *)this + 1033) = 0;
    }
  }
  if ( *((_QWORD *)this + 1134) )
  {
LABEL_9:
    LODWORD(LastError) = WSManHttpSenderConnection::SetRequestOptions(this, a2, a3, 0);
    if ( !(_DWORD)LastError )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          358,
          &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          (LARGE_INTEGER)PerformanceCount.QuadPart,
          this);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      v13 = *((_BYTE *)this + 8254);
      if ( !v13 || !*((_BYTE *)this + 11349) )
      {
        v14 = *((_QWORD *)this + 1132);
        v15 = *(CHAR **)(v14 + 40);
        if ( v15 )
        {
          v16 = *(_DWORD *)(v14 + 48);
        }
        else
        {
          v15 = (CHAR *)Buf1;
          v16 = 0;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x200) != 0 )
        {
          v30 = 0;
          if ( v13 )
            v30 = v16;
          WPP_SF_dq(v12[2], 366, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v30, this);
        }
        dwOptionalLength = 0;
        if ( *((_BYTE *)this + 8254) )
          dwOptionalLength = v16;
        if ( WinHttpSendRequest(
               *((HINTERNET *)this + 1134),
               0,
               0,
               v15,
               dwOptionalLength,
               dwOptionalLength,
               (DWORD_PTR)this) )
        {
          return 0;
        }
        LastError = GetLastError();
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(
          *((_QWORD *)this + 1128),
          LastError);
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v45 = 367;
          goto LABEL_165;
        }
        goto LABEL_45;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
        WPP_SF_qD(
          v12[2],
          359,
          &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          this,
          *((unsigned __int8 *)this + 11350));
      v46 = (Packet *)*((_QWORD *)this + 1129);
      if ( *((Packet **)this + 1132) != v46 || (v47 = Packet::Clone(v46, 0), (*((_QWORD *)this + 1132) = v47) != 0) )
      {
        v48 = PrepareChunk(v9, (struct Packet **)this + 1132);
        LODWORD(LastError) = v48;
        if ( v48 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 361, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v48);
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1128) + 72LL))(
            *((_QWORD *)this + 1128),
            (unsigned int)LastError);
        }
        else
        {
          if ( !*((_BYTE *)this + 11350) )
            return 0;
          if ( WinHttpAddRequestHeaders(*((HINTERNET *)this + 1134), L"Transfer-Encoding:chunked", 0x19u, 0xA0000000) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 363, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
            if ( WinHttpSendRequest(*((HINTERNET *)this + 1134), 0, 0, 0, 0, 0, (DWORD_PTR)this) )
              return 0;
            LastError = GetLastError();
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(
              *((_QWORD *)this + 1128),
              LastError);
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              v45 = 364;
LABEL_165:
              WPP_SF_d(v44[2], v45, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, (unsigned int)LastError);
            }
LABEL_45:
            v5 = v56;
            goto LABEL_46;
          }
          LastError = GetLastError();
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(
            *((_QWORD *)this + 1128),
            LastError);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              362,
              &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
              (unsigned int)LastError);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 360, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        LODWORD(LastError) = 14;
      }
    }
    v10 = 1;
    goto LABEL_45;
  }
  *((_DWORD *)this + 2275) = 1;
  v19 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) == 2 )
    v19 = 0x800000;
  v20 = WinHttpOpenRequest(*((HINTERNET *)this + 1036), L"POST", (LPCWSTR)this + 30, 0, 0, 0, v19);
  *((_DWORD *)this + 2275) = 0;
  if ( v20 )
  {
    v21 = (DWORD *)((char *)this + 9184);
    lpBuffer = (char *)this + 9184;
    v54 = 0;
    v22 = *((_DWORD *)this + 2296);
    if ( v22 )
    {
      SetLastError(v22);
      WSManError(
        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
        59,
        L"59",
        0x54Fu,
        0);
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 9192));
    }
    if ( !*((_BYTE *)this + 9097) )
    {
      *((_QWORD *)this + 1134) = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          357,
          &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          this,
          *((_QWORD *)this + 1134),
          *((_QWORD *)this + 1036));
      if ( *v21 )
      {
        SetLastError(*v21);
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
          102,
          L"102",
          0x54Fu,
          0);
      }
      else
      {
        WakeAllConditionVariable((PCONDITION_VARIABLE)this + 1154);
      }
      if ( *v21 )
        SetLastError(*v21);
      else
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 9192));
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
    *((_DWORD *)this + 2275) = 1;
    WinHttpCloseHandle(v20);
    *((_DWORD *)this + 2275) = 0;
    v10 = 1;
    LODWORD(LastError) = 995;
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&lpBuffer);
    v5 = v56;
  }
  else
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        355,
        (unsigned int)&WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        (_DWORD)this + 60,
        LastError);
    v10 = 1;
    v5 = v56;
  }
LABEL_46:
  if ( _InterlockedExchange((volatile __int32 *)this + 2839, 0) == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
    if ( !*((_QWORD *)this + 1) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 2899, L"2899", 0x54Fu, 0);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
      *((_QWORD *)this + 1),
      3,
      (unsigned int)LastError,
      0);
  }
  v26 = (unsigned int *)((char *)this + 9116);
  if ( v5 )
  {
    *v26 = LastError;
    *((_DWORD *)this + 2280) = 2 * !IsErrorRecoverable(LastError);
  }
  *((_BYTE *)this + 9016) = 0;
  if ( !*((_QWORD *)this + 1134) )
  {
    if ( !(_DWORD)LastError )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 6724, L"6724", 0x54Fu, 0);
    *v26 = LastError;
    if ( v10 )
      v49 = 2;
    else
      v49 = 2 * !IsErrorRecoverable(LastError);
    *((_DWORD *)this + 2280) = v49;
    WSManHttpSenderConnection::InitiateNotifyClient(this);
  }
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqdl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        447,
        &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        this,
        *((_QWORD *)this + 1),
        LastError,
        0);
    if ( !*((_QWORD *)this + 1) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 8357, L"8357", 0x54Fu, 0);
    WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(this);
    if ( *((_BYTE *)this + 11381) && (v51 = (PacketParser *)*((_QWORD *)this + 1145)) != 0 )
    {
      if ( (_DWORD)LastError )
      {
        PacketParser::EndOfStream(v51, LastError);
        goto LABEL_214;
      }
    }
    else if ( (_DWORD)LastError )
    {
LABEL_214:
      *((_DWORD *)this + 2278) = 0;
      *v26 = LastError;
      *((_DWORD *)this + 2280) = 2 * !IsErrorRecoverable(LastError);
      goto LABEL_62;
    }
    *v26 = LastError;
    *((_DWORD *)this + 2280) = 2 * !IsErrorRecoverable(LastError);
    if ( *((_BYTE *)this + 9018) )
    {
      *v26 = 0;
      *((_DWORD *)this + 2280) = 0;
    }
    else
    {
      v32 = WSManHttpSenderConnection::ProcessConnectionCookie(this);
      *v26 = v32;
      *((_DWORD *)this + 2280) = 2 * !IsErrorRecoverable(v32);
      if ( *v26 )
      {
        *((_DWORD *)this + 2278) = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128));
      }
    }
LABEL_62:
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_63;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qqdl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      447,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      this,
      *((_QWORD *)this + 1),
      LastError,
      2);
  if ( !*((_QWORD *)this + 1) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 8357, L"8357", 0x54Fu, 0);
  WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(this);
  if ( *((_BYTE *)this + 11381) && (v50 = (PacketParser *)*((_QWORD *)this + 1145)) != 0 )
  {
    if ( (_DWORD)LastError )
    {
      PacketParser::EndOfStream(v50, LastError);
      goto LABEL_210;
    }
  }
  else if ( (_DWORD)LastError )
  {
LABEL_210:
    *((_DWORD *)this + 2278) = 0;
    *v26 = LastError;
    *((_DWORD *)this + 2280) = 2;
    goto LABEL_73;
  }
  *v26 = LastError;
  *((_DWORD *)this + 2280) = 2;
  if ( *((_BYTE *)this + 9018) )
  {
    *v26 = 0;
    *((_DWORD *)this + 2280) = 0;
  }
  else
  {
    v31 = WSManHttpSenderConnection::ProcessConnectionCookie(this);
    *v26 = v31;
    *((_DWORD *)this + 2280) = 2 * !IsErrorRecoverable(v31);
    if ( *v26 )
    {
      *((_DWORD *)this + 2278) = 0;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128));
    }
  }
LABEL_73:
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    goto LABEL_63;
LABEL_75:
  WPP_SF_q(v27[2], 448, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
LABEL_63:
  (*(void (__fastcall **)(WSManHttpSenderConnection *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 96LL))(this, 0, 0, 0);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004a9b0  mov     [rsp+arg_8], rbx
0x18004a9b5  mov     [rsp+arg_18], r9d
0x18004a9ba  push    rbp
0x18004a9bb  push    rsi
0x18004a9bc  push    rdi
0x18004a9bd  push    r12
0x18004a9bf  push    r13
0x18004a9c1  push    r14
0x18004a9c3  push    r15
0x18004a9c5  sub     rsp, 60h
0x18004a9c9  mov     r15d, r9d
0x18004a9cc  mov     ebp, r8d
0x18004a9cf  mov     r14d, edx
0x18004a9d2  mov     rbx, rcx
0x18004a9d5  lea     r12, WPP_GLOBAL_Control
0x18004a9dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9e3  cmp     rcx, r12
0x18004a9e6  jnz     loc_18004AC86
0x18004a9ec  cmp     qword ptr [rbx+8], 0
0x18004a9f1  jz      loc_18004B37C
0x18004a9f7  movzx   esi, [rsp+98h+arg_20]
0x18004a9ff  mov     [rbx+2C57h], sil
0x18004aa06  cmp     byte ptr [rbx+233Bh], 0
0x18004aa0d  jnz     loc_18004AF3A
0x18004aa13  cmp     byte ptr [rbx+233Ah], 0
0x18004aa1a  jnz     loc_18004B3A8
0x18004aa20  xor     r13b, r13b
0x18004aa23  cmp     [rbx+203Eh], r13b
0x18004aa2a  jnz     loc_18004ABFF
0x18004aa30  cmp     qword ptr [rbx+2048h], 0
0x18004aa38  jz      loc_18004AF01
0x18004aa3e  mov     rax, [rbx+2370h]
0x18004aa45  test    rax, rax
0x18004aa48  jz      loc_18004AB06
0x18004aa4e  xor     r9d, r9d; bool
0x18004aa51  mov     r8d, ebp; unsigned int
0x18004aa54  mov     edx, r14d; unsigned int
0x18004aa57  mov     rcx, rbx; this
0x18004aa5a  call    ?SetRequestOptions@WSManHttpSenderConnection@@AEAAKKK_N@Z; WSManHttpSenderConnection::SetRequestOptions(ulong,ulong,bool)
0x18004aa5f  mov     edi, eax
0x18004aa61  test    eax, eax
0x18004aa63  jnz     loc_18004ACEF
0x18004aa69  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa70  cmp     rcx, r12
0x18004aa73  jnz     loc_18004AE0F
0x18004aa79  movzx   edx, byte ptr [rbx+203Eh]
0x18004aa80  test    dl, dl
0x18004aa82  jz      short loc_18004AA91
0x18004aa84  cmp     byte ptr [rbx+2C55h], 0
0x18004aa8b  jnz     loc_18004B7A6
0x18004aa91  mov     rax, [rbx+2360h]
0x18004aa98  mov     rdi, [rax+28h]
0x18004aa9c  test    rdi, rdi
0x18004aa9f  jnz     loc_18004ABF7
0x18004aaa5  lea     rdi, Buf1
0x18004aaac  xor     esi, esi
0x18004aaae  cmp     rcx, r12
0x18004aab1  jnz     loc_18004AF9F
0x18004aab7  xor     eax, eax
0x18004aab9  cmp     [rbx+203Eh], al
0x18004aabf  cmovnz  eax, esi
0x18004aac2  mov     [rsp+98h+dwContext], rbx; dwContext
0x18004aac7  mov     [rsp+98h+dwTotalLength], eax; dwTotalLength
0x18004aacb  mov     [rsp+98h+dwOptionalLength], eax; dwOptionalLength
0x18004aacf  mov     r9, rdi; lpOptional
0x18004aad2  xor     r8d, r8d; dwHeadersLength
0x18004aad5  xor     edx, edx; lpszHeaders
0x18004aad7  mov     rcx, [rbx+2370h]; hRequest
0x18004aade  call    cs:__imp_WinHttpSendRequest
0x18004aae4  test    eax, eax
0x18004aae6  jz      loc_18004B9B7
0x18004aaec  xor     eax, eax
0x18004aaee  mov     rbx, [rsp+98h+arg_8]
0x18004aaf6  add     rsp, 60h
0x18004aafa  pop     r15
0x18004aafc  pop     r14
0x18004aafe  pop     r13
0x18004ab00  pop     r12
0x18004ab02  pop     rdi
0x18004ab03  pop     rsi
0x18004ab04  pop     rbp
0x18004ab05  retn
0x18004ab06  mov     dword ptr [rbx+238Ch], 1
0x18004ab10  mov     rax, [rbx+28h]
0x18004ab14  mov     rcx, [rax+80h]
0x18004ab1b  xor     eax, eax
0x18004ab1d  mov     edx, 800000h
0x18004ab22  cmp     dword ptr [rcx+210h], 2
0x18004ab29  cmovz   eax, edx
0x18004ab2c  mov     dword ptr [rsp+98h+dwContext], eax; dwFlags
0x18004ab30  mov     qword ptr [rsp+98h+dwTotalLength], 0; ppwszAcceptTypes
0x18004ab39  mov     qword ptr [rsp+98h+dwOptionalLength], 0; pwszReferrer
0x18004ab42  xor     r9d, r9d; pwszVersion
0x18004ab45  lea     r8, [rbx+3Ch]; pwszObjectName
0x18004ab49  lea     rdx, pwszVerb; "POST"
0x18004ab50  mov     rcx, [rbx+2060h]; hConnect
0x18004ab57  call    cs:__imp_WinHttpOpenRequest
0x18004ab5d  mov     r15, rax
0x18004ab60  xor     eax, eax
0x18004ab62  mov     [rbx+238Ch], eax
0x18004ab68  test    r15, r15
0x18004ab6b  jz      loc_18004B06D
0x18004ab71  lea     rdi, [rbx+23E0h]
0x18004ab78  mov     [rsp+98h+lpBuffer], rdi
0x18004ab7d  mov     [rsp+98h+var_40], eax
0x18004ab81  mov     ecx, [rdi]; dwErrCode
0x18004ab83  test    ecx, ecx
0x18004ab85  jnz     loc_18004AFD4
0x18004ab8b  lea     rcx, [rdi+8]; lpCriticalSection
0x18004ab8f  call    cs:__imp_EnterCriticalSection
0x18004ab95  cmp     [rbx+2389h], r13b
0x18004ab9c  jnz     loc_18004B701
0x18004aba2  mov     [rbx+2370h], r15
0x18004aba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004abb0  lea     r12, WPP_GLOBAL_Control
0x18004abb7  cmp     rcx, r12
0x18004abba  jz      short loc_18004ABC9
0x18004abbc  test    dword ptr [rcx+1Ch], 400h
0x18004abc3  jnz     loc_18004B771
0x18004abc9  mov     ecx, [rdi]; dwErrCode
0x18004abcb  test    ecx, ecx
0x18004abcd  jnz     loc_18004B006
0x18004abd3  lea     rcx, [rdi+30h]; ConditionVariable
0x18004abd7  call    cs:__imp_WakeAllConditionVariable
0x18004abdd  mov     ecx, [rdi]; dwErrCode
0x18004abdf  test    ecx, ecx
0x18004abe1  jnz     loc_18004B038
0x18004abe7  lea     rcx, [rdi+8]; lpCriticalSection
0x18004abeb  call    cs:__imp_LeaveCriticalSection
0x18004abf1  nop
0x18004abf2  jmp     loc_18004AA4E
0x18004abf7  mov     esi, [rax+30h]
0x18004abfa  jmp     loc_18004AAAE
0x18004abff  cmp     [rbx+2C55h], r13b
0x18004ac06  jz      loc_18004AA30
0x18004ac0c  cmp     [rbx+2C56h], r13b
0x18004ac13  jnz     loc_18004AA30
0x18004ac19  mov     [rsp+98h+lpBuffer], 0
0x18004ac22  mov     dword ptr [rsp+98h+PerformanceCount], 0
0x18004ac2d  lea     r14, [rbx+2360h]
0x18004ac34  test    sil, sil
0x18004ac37  jz      loc_18004B50F
0x18004ac3d  cmp     qword ptr [r14], 0
0x18004ac41  jnz     loc_18004B50F
0x18004ac47  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ac4e  cmp     rcx, r12
0x18004ac51  jz      short loc_18004AC74
0x18004ac53  test    dword ptr [rcx+1Ch], 400h
0x18004ac5a  jz      short loc_18004AC74
0x18004ac5c  mov     edx, 15Bh
0x18004ac61  mov     r9, rbx
0x18004ac64  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004ac6b  mov     rcx, [rcx+10h]
0x18004ac6f  call    WPP_SF_q
0x18004ac74  lea     rdx, a0; "0\r\n\r\n"
0x18004ac7b  mov     r8d, 5
0x18004ac81  jmp     loc_18004B5B5
0x18004ac86  test    dword ptr [rcx+1Ch], 400h
0x18004ac8d  jz      loc_18004A9EC
0x18004ac93  mov     rax, [rbx+28h]
0x18004ac97  mov     rdx, [rax+80h]
0x18004ac9e  xor     r9d, r9d
0x18004aca1  cmp     dword ptr [rdx+210h], 2
0x18004aca8  setz    r9b
0x18004acac  movzx   eax, byte ptr [rbx+2C55h]
0x18004acb3  movzx   r8d, byte ptr [rbx+233Bh]
0x18004acbb  mov     edx, 156h
0x18004acc0  mov     [rsp+98h+var_60], r9d
0x18004acc5  mov     dword ptr [rsp+98h+dwContext], eax
0x18004acc9  mov     [rsp+98h+dwTotalLength], r8d
0x18004acce  mov     rax, [rbx+8]
0x18004acd2  mov     qword ptr [rsp+98h+dwOptionalLength], rax
0x18004acd7  mov     r9, rbx
0x18004acda  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004ace1  mov     rcx, [rcx+10h]
0x18004ace5  call    WPP_SF_qqddd
0x18004acea  jmp     loc_18004A9EC
0x18004acef  mov     r13b, 1
0x18004acf2  mov     r15d, [rsp+98h+arg_18]
0x18004acfa  lea     rbp, WPP_GLOBAL_Control
0x18004ad01  xor     eax, eax
0x18004ad03  xchg    eax, [rbx+2C5Ch]
0x18004ad09  cmp     eax, 1
0x18004ad0c  jnz     short loc_18004AD44
0x18004ad0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad15  cmp     rcx, rbp
0x18004ad18  jnz     loc_18004B043
0x18004ad1e  cmp     qword ptr [rbx+8], 0
0x18004ad23  jz      loc_18004B9F6
0x18004ad29  mov     rcx, [rbx+8]
0x18004ad2d  mov     rax, [rcx]
0x18004ad30  xor     r9d, r9d
0x18004ad33  mov     r8d, edi
0x18004ad36  mov     edx, 3
0x18004ad3b  mov     rax, [rax+10h]
0x18004ad3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad44  lea     rsi, [rbx+239Ch]
0x18004ad4b  test    r15d, r15d
0x18004ad4e  jnz     loc_18004BA22
0x18004ad54  mov     byte ptr [rbx+2338h], 0
0x18004ad5b  mov     rax, [rbx+2370h]
0x18004ad62  xor     r15d, r15d
0x18004ad65  test    rax, rax
0x18004ad68  jz      loc_18004BA3E
0x18004ad6e  test    r13b, r13b
0x18004ad71  jnz     loc_18004AE68
0x18004ad77  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad7e  cmp     rcx, rbp
0x18004ad81  jnz     loc_18004B0F0
0x18004ad87  cmp     qword ptr [rbx+8], 0
0x18004ad8c  jz      loc_18004BAF4
0x18004ad92  mov     rcx, rbx; this
0x18004ad95  call    ?EndQueryingMoreDataFromHttp@WSManHttpSenderConnection@@QEAAXXZ; WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(void)
0x18004ad9a  cmp     byte ptr [rbx+2C75h], 0
0x18004ada1  jnz     loc_18004BB1C
0x18004ada7  test    edi, edi
0x18004ada9  jnz     loc_18004BB3B
0x18004adaf  mov     [rsi], edi
0x18004adb1  mov     ecx, edi; unsigned int
0x18004adb3  call    ?IsErrorRecoverable@@YA_NK@Z; IsErrorRecoverable(ulong)
0x18004adb8  movzx   eax, al
0x18004adbb  xor     eax, 1
0x18004adbe  add     eax, eax
0x18004adc0  mov     [rbx+23A0h], eax
0x18004adc6  test    edi, edi
0x18004adc8  jnz     short loc_18004ADE1
0x18004adca  cmp     [rbx+233Ah], dil
0x18004add1  jz      loc_18004B174
0x18004add7  mov     [rsi], r15d
0x18004adda  mov     [rbx+23A0h], r15d
0x18004ade1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ade8  cmp     rcx, rbp
0x18004adeb  jnz     loc_18004B1BC
0x18004adf1  mov     rax, [rbx]
0x18004adf4  xor     r9d, r9d
0x18004adf7  xor     r8d, r8d
0x18004adfa  xor     edx, edx
0x18004adfc  mov     rcx, rbx
0x18004adff  mov     rax, [rax+60h]
0x18004ae03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae08  mov     eax, edi
0x18004ae0a  jmp     loc_18004AAEE
0x18004ae0f  test    byte ptr [rcx+1Ch], 40h
0x18004ae13  jz      loc_18004AA79
0x18004ae19  mov     qword ptr [rsp+98h+PerformanceCount], 0
0x18004ae25  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x18004ae2d  call    cs:__imp_QueryPerformanceCounter
0x18004ae33  mov     edx, 166h
0x18004ae38  mov     qword ptr [rsp+98h+dwOptionalLength], rbx
0x18004ae3d  mov     r9, qword ptr [rsp+98h+PerformanceCount]
0x18004ae45  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004ae4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae53  mov     rcx, [rcx+10h]
0x18004ae57  call    WPP_SF_qq
0x18004ae5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae63  jmp     loc_18004AA79
0x18004ae68  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae6f  cmp     rcx, rbp
0x18004ae72  jnz     loc_18004B0B1
0x18004ae78  cmp     qword ptr [rbx+8], 0
0x18004ae7d  jz      loc_18004BA95
0x18004ae83  mov     rcx, rbx; this
0x18004ae86  call    ?EndQueryingMoreDataFromHttp@WSManHttpSenderConnection@@QEAAXXZ; WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(void)
0x18004ae8b  cmp     byte ptr [rbx+2C75h], 0
0x18004ae92  jnz     loc_18004BABD
0x18004ae98  test    edi, edi
0x18004ae9a  jnz     loc_18004BADC
0x18004aea0  mov     [rsi], edi
0x18004aea2  mov     dword ptr [rbx+23A0h], 2
0x18004aeac  test    edi, edi
0x18004aeae  jnz     short loc_18004AEC7
0x18004aeb0  cmp     [rbx+233Ah], dil
0x18004aeb7  jz      loc_18004B12C
0x18004aebd  mov     [rsi], r15d
0x18004aec0  mov     [rbx+23A0h], r15d
0x18004aec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aece  cmp     rcx, rbp
0x18004aed1  jz      loc_18004ADF1
0x18004aed7  test    dword ptr [rcx+1Ch], 400h
0x18004aede  jz      loc_18004ADF1
0x18004aee4  mov     r9, rbx
0x18004aee7  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004aeee  mov     edx, 1C0h
0x18004aef3  mov     rcx, [rcx+10h]
0x18004aef7  call    WPP_SF_q
0x18004aefc  jmp     loc_18004ADF1
0x18004af01  mov     r15, [rbx+28h]
0x18004af05  mov     rcx, cs:WPP_GLOBAL_Control
0x18004af0c  cmp     rcx, r12
0x18004af0f  jz      short loc_18004AF1E
0x18004af11  test    dword ptr [rcx+1Ch], 400h
0x18004af18  jnz     loc_18004B624
0x18004af1e  mov     rcx, [r15+90h]; this
0x18004af25  test    rcx, rcx
0x18004af28  jnz     loc_18004B1CE
0x18004af2e  mov     [rbx+2048h], rcx
0x18004af35  jmp     loc_18004AA3E
0x18004af3a  mov     byte ptr [rbx+233Bh], 0
0x18004af41  cmp     byte ptr [rbx+2C55h], 0
0x18004af48  jz      loc_18004AA13
  ... truncated ...
```
