# RdpUdpETWEvents::Enable(void)

- ea: `0x180141568`
- end: `0x180142463`
- name: `?Enable@RdpUdpETWEvents@@QEAAJXZ`
- size: `3835`
- prototype: `__int64 __fastcall(RdpUdpETWEvents *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180121af0`

## callees

- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x18001e740`
- `0x180036c18`
- `0x180046a84`
- `0x1800506ac`
- `0x18006f440`
- `0x1800711c8`
- `0x180141568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180141654`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180141654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180141648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180141648`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180141633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180141633`

## string_xrefs

- `0x1801422b1`: `RDV::RDP::TransUDP::ReadData`

## pseudocode

```c
__int64 __fastcall RdpUdpETWEvents::Enable(RdpUdpETWEvents *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD TickCount; // eax
  DWORD CurrentProcessId; // eax
  int GenericCounter; // ebx
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  DWORD pSessionId; // [rsp+70h] [rbp+40h] BYREF
  char *v11; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_983e9120d0c2358f75571d1a5f47b62c_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  *((_DWORD *)this + 84) = 2;
  *(_QWORD *)((char *)this + 300) = 0;
  *(_QWORD *)((char *)this + 308) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *(_QWORD *)((char *)this + 316) = 0;
  *((_WORD *)this + 174) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_WORD *)this + 186) = 0;
  *(_QWORD *)((char *)this + 340) = 1;
  *((_QWORD *)this + 36) = 1;
  TickCount = GetTickCount();
  pSessionId = 0;
  *((_DWORD *)this + 74) = TickCount - 1001;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    pSessionId = -1;
  v11 = (char *)this + 64;
  CTSCriticalSection::Lock((RdpUdpETWEvents *)((char *)this + 64));
  if ( *((_QWORD *)this + 11) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 88);
    *((_QWORD *)this + 11) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 88);
  }
  if ( *((_QWORD *)this + 12) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 96);
    *((_QWORD *)this + 12) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 96);
  }
  if ( *((_QWORD *)this + 13) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 104);
    *((_QWORD *)this + 13) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 104);
  }
  if ( *((_QWORD *)this + 14) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 112);
    *((_QWORD *)this + 14) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 112);
  }
  if ( *((_QWORD *)this + 15) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 120);
    *((_QWORD *)this + 15) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 120);
  }
  if ( *((_QWORD *)this + 16) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 128);
    *((_QWORD *)this + 16) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 128);
  }
  if ( *((_QWORD *)this + 17) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 136);
    *((_QWORD *)this + 17) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 136);
  }
  if ( *((_QWORD *)this + 18) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 144);
    *((_QWORD *)this + 18) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 144);
  }
  if ( *((_QWORD *)this + 19) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 152);
    *((_QWORD *)this + 19) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 152);
  }
  if ( *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
    *((_QWORD *)this + 20) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
  }
  if ( *((_QWORD *)this + 21) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 168);
    *((_QWORD *)this + 21) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 168);
  }
  if ( *((_QWORD *)this + 22) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 176);
    *((_QWORD *)this + 22) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 176);
  }
  if ( *((_QWORD *)this + 24) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 192);
    *((_QWORD *)this + 24) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 192);
  }
  if ( *((_QWORD *)this + 25) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
    *((_QWORD *)this + 25) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
  }
  if ( *((_QWORD *)this + 26) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 208);
    *((_QWORD *)this + 26) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 208);
  }
  if ( *((_QWORD *)this + 27) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 216);
    *((_QWORD *)this + 27) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 216);
  }
  if ( *((_QWORD *)this + 28) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 224);
    *((_QWORD *)this + 28) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 224);
  }
  if ( *((_QWORD *)this + 29) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 232);
    *((_QWORD *)this + 29) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 232);
  }
  if ( *((_QWORD *)this + 30) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 240);
    *((_QWORD *)this + 30) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 240);
  }
  if ( *((_QWORD *)this + 31) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 248);
    *((_QWORD *)this + 31) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 248);
  }
  if ( *((_QWORD *)this + 32) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 256);
    *((_QWORD *)this + 32) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 256);
  }
  if ( *((_QWORD *)this + 33) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 264);
    *((_QWORD *)this + 33) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 264);
  }
  if ( *((_QWORD *)this + 34) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 272);
    *((_QWORD *)this + 34) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 272);
  }
  if ( *((_QWORD *)this + 35) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 280);
    *((_QWORD *)this + 35) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 280);
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::TransUDP::CwndChange",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 88);
  if ( GenericCounter >= 0 )
  {
    GenericCounter = RDPAPI_GetGenericCounter(
                       (unsigned int)L"RDV::RDP::TransUDP::SSTChange",
                       pSessionId,
                       0,
                       -1,
                       4,
                       (__int64)this + 96);
    if ( GenericCounter >= 0 )
    {
      GenericCounter = RDPAPI_GetGenericCounter(
                         (unsigned int)L"RDV::RDP::TransUDP::SPckSent",
                         pSessionId,
                         0,
                         -1,
                         4,
                         (__int64)this + 104);
      if ( GenericCounter >= 0 )
      {
        GenericCounter = RDPAPI_GetGenericCounter(
                           (unsigned int)L"RDV::RDP::TransUDP::FTPckSent",
                           pSessionId,
                           0,
                           -1,
                           4,
                           (__int64)this + 120);
        if ( GenericCounter >= 0 )
        {
          GenericCounter = RDPAPI_GetGenericCounter(
                             (unsigned int)L"RDV::RDP::TransUDP::LRTPckSent",
                             pSessionId,
                             0,
                             -1,
                             4,
                             (__int64)this + 128);
          if ( GenericCounter >= 0 )
          {
            GenericCounter = RDPAPI_GetGenericCounter(
                               (unsigned int)L"RDV::RDP::TransUDP::FPckSent",
                               pSessionId,
                               0,
                               -1,
                               4,
                               (__int64)this + 112);
            if ( GenericCounter >= 0 )
            {
              GenericCounter = RDPAPI_GetGenericCounter(
                                 (unsigned int)L"RDV::RDP::TransUDP::StateChange",
                                 pSessionId,
                                 0,
                                 -1,
                                 4,
                                 (__int64)this + 136);
              if ( GenericCounter >= 0 )
              {
                GenericCounter = RDPAPI_GetGenericCounter(
                                   (unsigned int)L"RDV::RDP::TransUDP::TimerFired",
                                   pSessionId,
                                   0,
                                   -1,
                                   4,
                                   (__int64)this + 144);
                if ( GenericCounter >= 0 )
                {
                  GenericCounter = RDPAPI_GetGenericCounter(
                                     (unsigned int)L"RDV::RDP::TransUDP::ACKRecvd",
                                     pSessionId,
                                     0,
                                     -1,
                                     4,
                                     (__int64)this + 152);
                  if ( GenericCounter >= 0 )
                  {
                    GenericCounter = RDPAPI_GetGenericCounter(
                                       (unsigned int)L"RDV::RDP::TransUDP::APckRcvd",
                                       pSessionId,
                                       0,
                                       -1,
                                       4,
                                       (__int64)this + 168);
                    if ( GenericCounter >= 0 )
                    {
                      GenericCounter = RDPAPI_GetGenericCounter(
                                         (unsigned int)L"RDV::RDP::TransUDP::RTRPckSent",
                                         pSessionId,
                                         0,
                                         -1,
                                         4,
                                         (__int64)this + 160);
                      if ( GenericCounter >= 0 )
                      {
                        GenericCounter = RDPAPI_GetGenericCounter(
                                           (unsigned int)L"RDV::RDP::TransUDP::PktLost",
                                           pSessionId,
                                           0,
                                           -1,
                                           4,
                                           (__int64)this + 176);
                        if ( GenericCounter >= 0 )
                        {
                          GenericCounter = RDPAPI_GetGenericCounter(
                                             (unsigned int)L"RDV::RDP::TransUDP::SPckRcvd",
                                             pSessionId,
                                             0,
                                             -1,
                                             4,
                                             (__int64)this + 208);
                          if ( GenericCounter >= 0 )
                          {
                            GenericCounter = RDPAPI_GetGenericCounter(
                                               (unsigned int)L"RDV::RDP::TransUDP::FPckRcvd",
                                               pSessionId,
                                               0,
                                               -1,
                                               4,
                                               (__int64)this + 216);
                            if ( GenericCounter >= 0 )
                            {
                              GenericCounter = RDPAPI_GetGenericCounter(
                                                 (unsigned int)L"RDV::RDP::TransUDP::APckSent",
                                                 pSessionId,
                                                 0,
                                                 -1,
                                                 4,
                                                 (__int64)this + 224);
                              if ( GenericCounter >= 0 )
                              {
                                GenericCounter = RDPAPI_GetGenericCounter(
                                                   (unsigned int)L"RDV::RDP::TransUDP::InvPckRcvd",
                                                   pSessionId,
                                                   0,
                                                   -1,
                                                   4,
                                                   (__int64)this + 232);
                                if ( GenericCounter >= 0 )
                                {
                                  GenericCounter = RDPAPI_GetGenericCounter(
                                                     (unsigned int)L"RDV::RDP::TransUDP::SPckDropped",
                                                     pSessionId,
                                                     0,
                                                     -1,
                                                     4,
                                                     (__int64)this + 240);
                                  if ( GenericCounter >= 0 )
                                  {
                                    GenericCounter = RDPAPI_GetGenericCounter(
                                                       (unsigned int)L"RDV::RDP::TransUDP::FPckDropped",
                                                       pSessionId,
                                                       0,
                                                       -1,
                                                       4,
                                                       (__int64)this + 248);
                                    if ( GenericCounter >= 0 )
                                    {
                                      GenericCounter = RDPAPI_GetGenericCounter(
                                                         (unsigned int)L"RDV::RDP::TransUDP::FecRecoverSrc",
                                                         pSessionId,
                                                         0,
                                                         -1,
                                                         4,
                                                         (__int64)this + 256);
                                      if ( GenericCounter >= 0 )
                                      {
                                        GenericCounter = RDPAPI_GetGenericCounter(
                                                           (unsigned int)L"RDV::RDP::TransUDP::ACKSent",
                                                           pSessionId,
                                                           0,
                                                           -1,
                                                           4,
                                                           (__int64)this + 264);
                                        if ( GenericCounter >= 0 )
                                        {
                                          GenericCounter = RDPAPI_GetGenericCounter(
                                                             (unsigned int)L"RDV::RDP::TransUDP::ReadData",
                                                             pSessionId,
                                                             0,
                                                             -1,
                                                             4,
                                                             (__int64)this + 272);
                                          if ( GenericCounter >= 0 )
                                          {
                                            GenericCounter = RDPAPI_GetGenericCounter(
                                                               (unsigned int)L"RDV::RDP::TransUDP::SendQueueSize",
                                                               pSessionId,
                                                               0,
                                                               -1,
                                                               4,
                                                               (__int64)this + 192);
                                            if ( GenericCounter >= 0 )
                                            {
                                              GenericCounter = RDPAPI_GetGenericCounter(
                                                                 (unsigned int)L"RDV::RDP::TransUDP::RecvQueueSize",
                                                                 pSessionId,
                                                                 0,
                                                                 -1,
                                                                 4,
                                                                 (__int64)this + 280);
                                              if ( GenericCounter >= 0 )
                                              {
                                                GenericCounter = RDPAPI_GetGenericCounter(
                                                                   (unsigned int)L"RDV::RDP::TransUDP::SndBufferQueue",
                                                                   pSessionId,
                                                                   0,
                                                                   -1,
                                                                   4,
                                                                   (__int64)this + 200);
                                                if ( GenericCounter >= 0 )
                                                {
                                                  RdpUdpETWEvents::TestLoggingEnabled(this);
                                                  goto LABEL_178;
                                                }
                                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                {
                                                  v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                                  v7 = 40;
                                                  v8 = "RDPAPI_GetGenericCounter TransUDP::SndBufferQueue failed";
                                                  goto LABEL_60;
                                                }
                                              }
                                              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                              {
                                                v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                                v7 = 39;
                                                v8 = "RDPAPI_GetGenericCounter TransUDP::RecvQueueSize failed";
                                                goto LABEL_60;
                                              }
                                            }
                                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                            {
                                              v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                              v7 = 38;
                                              v8 = "RDPAPI_GetGenericCounter TransUDP::SendQueueSize failed";
                                              goto LABEL_60;
                                            }
                                            goto LABEL_178;
                                          }
                                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_178;
                                          }
                                          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                          v7 = 37;
                                        }
                                        else
                                        {
                                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_178;
                                          }
                                          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                          v7 = 36;
                                        }
                                        v8 = "RDPAPI_GetGenericCounter TransUDP::ACKSent failed";
                                        goto LABEL_60;
                                      }
                                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                        v7 = 35;
                                        v8 = "RDPAPI_GetGenericCounter TransUDP::FecRecoverSrc failed";
                                        goto LABEL_60;
                                      }
                                    }
                                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                    {
                                      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                      v7 = 34;
                                      v8 = "RDPAPI_GetGenericCounter TransUDP::FPckDropped failed";
                                      goto LABEL_60;
                                    }
                                  }
                                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                    v7 = 33;
                                    v8 = "RDPAPI_GetGenericCounter TransUDP::SPckDropped failed";
                                    goto LABEL_60;
                                  }
                                }
                                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                  v7 = 32;
                                  v8 = "RDPAPI_GetGenericCounter TransUDP::InvPckRcvd failed";
                                  goto LABEL_60;
                                }
                              }
                              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                                v7 = 31;
                                v8 = "RDPAPI_GetGenericCounter TransUDP::APckSent failed";
                                goto LABEL_60;
                              }
                            }
                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                              v7 = 30;
                              v8 = "RDPAPI_GetGenericCounter TransUDP::FPckRcvd failed";
                              goto LABEL_60;
                            }
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                            v7 = 29;
                            v8 = "RDPAPI_GetGenericCounter TransUDP::SPckRcvd failed";
                            goto LABEL_60;
                          }
                        }
                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                          v7 = 28;
                          v8 = "RDPAPI_GetGenericCounter TransUDP::PKtLost failed";
                          goto LABEL_60;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v7 = 27;
                        v8 = "RDPAPI_GetGenericCounter TransUDP::RTRPckSent failed";
                        goto LABEL_60;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v7 = 26;
                      v8 = "RDPAPI_GetGenericCounter TransUDP::APckRcvd failed";
                      goto LABEL_60;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v7 = 25;
                    v8 = "RDPAPI_GetGenericCounter TransUDP::ACKRecvd failed";
                    goto LABEL_60;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v7 = 24;
                  v8 = "RDPAPI_GetGenericCounter TransUDP::TimerFired failed";
                  goto LABEL_60;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 23;
                v8 = "RDPAPI_GetGenericCounter TransUDP::StateChange failed";
                goto LABEL_60;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v6 = RdpWppGetCurrentThreadActivityIdPrefix();
              v7 = 22;
              v8 = "Failed to initialize RDV::RDP::TransUDP::FPckSent perf counter";
              goto LABEL_60;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 21;
            v8 = "Failed to initialize RDV::RDP::TransUDP::LRTPckSent perf counter";
            goto LABEL_60;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 20;
          v8 = "Failed to initialize RDV::RDP::TransUDP::FTPckSent perf counter";
          goto LABEL_60;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 19;
        v8 = "Failed to initialize RDV::RDP::TransUDP::SPckSent perf counter";
        goto LABEL_60;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 18;
      v8 = "Failed to initialize RDV::RDP::TransUDP::SSTChange counter";
      goto LABEL_60;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 17;
    v8 = "Failed to initialize RDV::RDP::TransUDP::CwndChange counter";
LABEL_60:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_983e9120d0c2358f75571d1a5f47b62c_Traceguids,
      v6,
      (__int64)v8,
      GenericCounter);
  }
LABEL_178:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v11);
  return (unsigned int)GenericCounter;
}

```

## disassembly

```asm
0x180141568  mov     [rsp-38h+arg_10], rbx
0x18014156d  push    rbp
0x18014156e  push    rsi
0x18014156f  push    rdi
0x180141570  push    r12
0x180141572  push    r13
0x180141574  push    r14
0x180141576  push    r15
0x180141578  mov     rbp, rsp
0x18014157b  sub     rsp, 30h
0x18014157f  mov     rdi, rcx
0x180141582  mov     rax, cs:WPP_GLOBAL_Control
0x180141589  lea     rcx, WPP_GLOBAL_Control
0x180141590  cmp     rax, rcx
0x180141593  jz      short loc_1801415C8
0x180141595  test    dword ptr [rax+1Ch], 800h
0x18014159c  jz      short loc_1801415C8
0x18014159e  cmp     byte ptr [rax+19h], 5
0x1801415a2  jb      short loc_1801415C8
0x1801415a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801415a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801415b0  lea     r8, WPP_983e9120d0c2358f75571d1a5f47b62c_Traceguids
0x1801415b7  mov     edx, 10h
0x1801415bc  mov     r9d, eax
0x1801415bf  mov     rcx, [rcx+10h]
0x1801415c3  call    WPP_SF_d
0x1801415c8  xor     r13d, r13d
0x1801415cb  mov     dword ptr [rdi+150h], 2
0x1801415d5  mov     [rdi+12Ch], r13
0x1801415dc  mov     [rdi+134h], r13
0x1801415e3  mov     [rdi+148h], r13
0x1801415ea  mov     [rdi+160h], r13
0x1801415f1  mov     [rdi+168h], r13
0x1801415f8  mov     [rdi+13Ch], r13
0x1801415ff  mov     [rdi+15Ch], r13w
0x180141607  mov     [rdi+178h], r13
0x18014160e  mov     [rdi+170h], r13d
0x180141615  mov     [rdi+174h], r13w
0x18014161d  mov     qword ptr [rdi+154h], 1
0x180141628  mov     qword ptr [rdi+120h], 1
0x180141633  call    cs:__imp_GetTickCount
0x180141639  sub     eax, 3E9h
0x18014163e  mov     [rbp+pSessionId], r13d
0x180141642  mov     [rdi+128h], eax
0x180141648  call    cs:__imp_GetCurrentProcessId
0x18014164e  mov     ecx, eax; dwProcessId
0x180141650  lea     rdx, [rbp+pSessionId]; pSessionId
0x180141654  call    cs:__imp_ProcessIdToSessionId
0x18014165a  test    eax, eax
0x18014165c  jnz     short loc_180141665
0x18014165e  mov     [rbp+pSessionId], 0FFFFFFFFh
0x180141665  lea     rcx, [rdi+40h]; this
0x180141669  mov     [rbp+arg_8], rcx
0x18014166d  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180141672  lea     rbx, [rdi+58h]
0x180141676  cmp     [rbx], r13
0x180141679  jz      short loc_18014168E
0x18014167b  mov     rcx, rbx; void *
0x18014167e  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141683  mov     rcx, rbx
0x180141686  mov     [rbx], r13
0x180141689  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18014168e  lea     rsi, [rdi+60h]
0x180141692  cmp     [rsi], r13
0x180141695  jz      short loc_1801416AA
0x180141697  mov     rcx, rsi; void *
0x18014169a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18014169f  mov     rcx, rsi
0x1801416a2  mov     [rsi], r13
0x1801416a5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801416aa  lea     r14, [rdi+68h]
0x1801416ae  cmp     [r14], r13
0x1801416b1  jz      short loc_1801416C6
0x1801416b3  mov     rcx, r14; void *
0x1801416b6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801416bb  mov     rcx, r14
0x1801416be  mov     [r14], r13
0x1801416c1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801416c6  lea     r12, [rdi+70h]
0x1801416ca  cmp     [r12], r13
0x1801416ce  jz      short loc_1801416E4
0x1801416d0  mov     rcx, r12; void *
0x1801416d3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801416d8  mov     rcx, r12
0x1801416db  mov     [r12], r13
0x1801416df  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801416e4  lea     r15, [rdi+78h]
0x1801416e8  cmp     [r15], r13
0x1801416eb  jz      short loc_180141700
0x1801416ed  mov     rcx, r15; void *
0x1801416f0  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801416f5  mov     rcx, r15
0x1801416f8  mov     [r15], r13
0x1801416fb  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141700  lea     r13, [rdi+80h]
0x180141707  cmp     qword ptr [r13+0], 0
0x18014170c  jz      short loc_180141726
0x18014170e  mov     rcx, r13; void *
0x180141711  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141716  mov     rcx, r13
0x180141719  mov     qword ptr [r13+0], 0
0x180141721  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141726  lea     rax, [rdi+88h]
0x18014172d  cmp     qword ptr [rax], 0
0x180141731  jz      short loc_180141751
0x180141733  mov     rcx, rax; void *
0x180141736  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18014173b  lea     rax, [rdi+88h]
0x180141742  mov     rcx, rax
0x180141745  mov     qword ptr [rax], 0
0x18014174c  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141751  lea     rax, [rdi+90h]
0x180141758  cmp     qword ptr [rax], 0
0x18014175c  jz      short loc_18014177C
0x18014175e  mov     rcx, rax; void *
0x180141761  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141766  lea     rax, [rdi+90h]
0x18014176d  mov     rcx, rax
0x180141770  mov     qword ptr [rax], 0
0x180141777  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18014177c  lea     rax, [rdi+98h]
0x180141783  cmp     qword ptr [rax], 0
0x180141787  jz      short loc_1801417A7
0x180141789  mov     rcx, rax; void *
0x18014178c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141791  lea     rax, [rdi+98h]
0x180141798  mov     rcx, rax
0x18014179b  mov     qword ptr [rax], 0
0x1801417a2  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801417a7  lea     rax, [rdi+0A0h]
0x1801417ae  cmp     qword ptr [rax], 0
0x1801417b2  jz      short loc_1801417D2
0x1801417b4  mov     rcx, rax; void *
0x1801417b7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801417bc  lea     rax, [rdi+0A0h]
0x1801417c3  mov     rcx, rax
0x1801417c6  mov     qword ptr [rax], 0
0x1801417cd  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801417d2  lea     rax, [rdi+0A8h]
0x1801417d9  cmp     qword ptr [rax], 0
0x1801417dd  jz      short loc_1801417FD
0x1801417df  mov     rcx, rax; void *
0x1801417e2  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801417e7  lea     rax, [rdi+0A8h]
0x1801417ee  mov     rcx, rax
0x1801417f1  mov     qword ptr [rax], 0
0x1801417f8  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801417fd  lea     rax, [rdi+0B0h]
0x180141804  cmp     qword ptr [rax], 0
0x180141808  jz      short loc_180141828
0x18014180a  mov     rcx, rax; void *
0x18014180d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141812  lea     rax, [rdi+0B0h]
0x180141819  mov     rcx, rax
0x18014181c  mov     qword ptr [rax], 0
0x180141823  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141828  lea     rax, [rdi+0C0h]
0x18014182f  cmp     qword ptr [rax], 0
0x180141833  jz      short loc_180141853
0x180141835  mov     rcx, rax; void *
0x180141838  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18014183d  lea     rax, [rdi+0C0h]
0x180141844  mov     rcx, rax
0x180141847  mov     qword ptr [rax], 0
0x18014184e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141853  lea     rax, [rdi+0C8h]
0x18014185a  cmp     qword ptr [rax], 0
0x18014185e  jz      short loc_18014187E
0x180141860  mov     rcx, rax; void *
0x180141863  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141868  lea     rax, [rdi+0C8h]
0x18014186f  mov     rcx, rax
0x180141872  mov     qword ptr [rax], 0
0x180141879  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18014187e  lea     rax, [rdi+0D0h]
0x180141885  cmp     qword ptr [rax], 0
0x180141889  jz      short loc_1801418A9
0x18014188b  mov     rcx, rax; void *
0x18014188e  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141893  lea     rax, [rdi+0D0h]
0x18014189a  mov     rcx, rax
0x18014189d  mov     qword ptr [rax], 0
0x1801418a4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801418a9  lea     rax, [rdi+0D8h]
0x1801418b0  cmp     qword ptr [rax], 0
0x1801418b4  jz      short loc_1801418D4
0x1801418b6  mov     rcx, rax; void *
0x1801418b9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801418be  lea     rax, [rdi+0D8h]
0x1801418c5  mov     rcx, rax
0x1801418c8  mov     qword ptr [rax], 0
0x1801418cf  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801418d4  lea     rax, [rdi+0E0h]
0x1801418db  cmp     qword ptr [rax], 0
0x1801418df  jz      short loc_1801418FF
0x1801418e1  mov     rcx, rax; void *
0x1801418e4  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801418e9  lea     rax, [rdi+0E0h]
0x1801418f0  mov     rcx, rax
0x1801418f3  mov     qword ptr [rax], 0
0x1801418fa  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801418ff  lea     rax, [rdi+0E8h]
0x180141906  cmp     qword ptr [rax], 0
0x18014190a  jz      short loc_18014192A
0x18014190c  mov     rcx, rax; void *
0x18014190f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141914  lea     rax, [rdi+0E8h]
0x18014191b  mov     rcx, rax
0x18014191e  mov     qword ptr [rax], 0
0x180141925  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18014192a  lea     rax, [rdi+0F0h]
0x180141931  cmp     qword ptr [rax], 0
0x180141935  jz      short loc_180141955
0x180141937  mov     rcx, rax; void *
0x18014193a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18014193f  lea     rax, [rdi+0F0h]
0x180141946  mov     rcx, rax
0x180141949  mov     qword ptr [rax], 0
0x180141950  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141955  lea     rax, [rdi+0F8h]
0x18014195c  cmp     qword ptr [rax], 0
0x180141960  jz      short loc_180141980
0x180141962  mov     rcx, rax; void *
0x180141965  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18014196a  lea     rax, [rdi+0F8h]
0x180141971  mov     rcx, rax
0x180141974  mov     qword ptr [rax], 0
0x18014197b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141980  lea     rax, [rdi+100h]
0x180141987  cmp     qword ptr [rax], 0
0x18014198b  jz      short loc_1801419AB
0x18014198d  mov     rcx, rax; void *
0x180141990  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141995  lea     rax, [rdi+100h]
0x18014199c  mov     rcx, rax
0x18014199f  mov     qword ptr [rax], 0
0x1801419a6  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801419ab  lea     rax, [rdi+108h]
0x1801419b2  cmp     qword ptr [rax], 0
0x1801419b6  jz      short loc_1801419D6
0x1801419b8  mov     rcx, rax; void *
0x1801419bb  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801419c0  lea     rax, [rdi+108h]
0x1801419c7  mov     rcx, rax
0x1801419ca  mov     qword ptr [rax], 0
0x1801419d1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801419d6  lea     rax, [rdi+110h]
0x1801419dd  cmp     qword ptr [rax], 0
0x1801419e1  jz      short loc_180141A01
0x1801419e3  mov     rcx, rax; void *
0x1801419e6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801419eb  lea     rax, [rdi+110h]
0x1801419f2  mov     rcx, rax
0x1801419f5  mov     qword ptr [rax], 0
0x1801419fc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141a01  lea     rax, [rdi+118h]
0x180141a08  cmp     qword ptr [rax], 0
0x180141a0c  jz      short loc_180141A2C
0x180141a0e  mov     rcx, rax; void *
0x180141a11  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180141a16  lea     rax, [rdi+118h]
0x180141a1d  mov     rcx, rax
0x180141a20  mov     qword ptr [rax], 0
0x180141a27  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180141a2c  mov     edx, [rbp+pSessionId]
0x180141a2f  lea     rcx, aRdvRdpTransudp_15; "RDV::RDP::TransUDP::CwndChange"
0x180141a36  mov     [rsp+30h+var_8], rbx
0x180141a3b  or      r9d, 0FFFFFFFFh
0x180141a3f  xor     r8d, r8d
0x180141a42  mov     dword ptr [rsp+30h+var_10], 4
0x180141a4a  call    RDPAPI_GetGenericCounter
0x180141a4f  mov     ebx, eax
0x180141a51  test    eax, eax
0x180141a53  jns     short loc_180141AB9
0x180141a55  mov     rax, cs:WPP_GLOBAL_Control
0x180141a5c  lea     rcx, WPP_GLOBAL_Control
0x180141a63  cmp     rax, rcx
0x180141a66  jz      loc_180142440
0x180141a6c  test    byte ptr [rax+1Ch], 8
0x180141a70  jz      loc_180142440
0x180141a76  cmp     byte ptr [rax+19h], 2
0x180141a7a  jb      loc_180142440
0x180141a80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180141a85  mov     edx, 11h
0x180141a8a  lea     rcx, aFailedToInitia_19; "Failed to initialize RDV::RDP::TransUDP"...
0x180141a91  mov     dword ptr [rsp+30h+var_8], ebx
0x180141a95  lea     r8, WPP_983e9120d0c2358f75571d1a5f47b62c_Traceguids
0x180141a9c  mov     [rsp+30h+var_10], rcx
0x180141aa1  mov     r9d, eax
0x180141aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180141aab  mov     rcx, [rcx+10h]
0x180141aaf  call    WPP_SF_DsD
0x180141ab4  jmp     loc_180142440
0x180141ab9  mov     edx, [rbp+pSessionId]
0x180141abc  lea     rcx, aRdvRdpTransudp_17; "RDV::RDP::TransUDP::SSTChange"
0x180141ac3  mov     [rsp+30h+var_8], rsi
0x180141ac8  or      r9d, 0FFFFFFFFh
0x180141acc  mov     esi, 4
0x180141ad1  xor     r8d, r8d
0x180141ad4  mov     dword ptr [rsp+30h+var_10], esi
  ... truncated ...
```
