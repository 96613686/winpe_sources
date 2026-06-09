# RdpVCETWEvents::Enable(void)

- ea: `0x18000fddc`
- end: `0x180010535`
- name: `?Enable@RdpVCETWEvents@@QEAAJXZ`
- size: `1881`
- prototype: `__int64 __fastcall(RdpVCETWEvents *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18013f3d0`

## callees

- `0x18000e4ec`
- `0x18000fb68`
- `0x18000fddc`
- `0x18002aafc`
- `0x18002b14c`
- `0x18004f5bc`
- `0x180076090`
- `0x180079770`
- `0x18007a404`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fe37`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fe37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fe18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fe18`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff02`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff33`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff63`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff8d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ffb7`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ffe8`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180010019`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001004a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001007b`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800100ac`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800100dd`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001010e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001013f`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff02`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff33`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff63`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ff8d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ffb7`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18000ffe8`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180010019`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001004a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001007b`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800100ac`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800100dd`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001010e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18001013f`

## string_xrefs

- `0x1800100cb`: `RDV::RDP::VirtChan::OnTunnelToTransportSwitchForRead`
- `0x1800100fc`: `RDV::RDP::VirtChan::OnTunnelToTransportSwitchForWrite`
- `0x180010069`: `RDV::RDP::VirtChan::ChannelOpened`
- `0x180010436`: `Failed to initialize RDV::RDP::VirtChan::ChannelOpened counter`
- `0x1800104b8`: `Failed to initialize RDV::RDP::VirtChan::OnTunnelToTransportSwitchForRead counter`
- `0x1800104f9`: `Failed to initialize RDV::RDP::VirtChan::OnTunnelToTransportSwitchForWrite counter`

## pseudocode

```c
__int64 __fastcall RdpVCETWEvents::Enable(RdpVCETWEvents *this)
{
  DWORD CurrentProcessId; // eax
  int GenericCounter; // edi
  unsigned int v5; // eax
  int v6; // edx
  const char *v7; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  DWORD pSessionId; // [rsp+70h] [rbp+40h] BYREF
  char *v13; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_169544b849a53ab0319c391a750509f8_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  *((_QWORD *)this + 24) = 1;
  *((_DWORD *)this + 50) = GetTickCount();
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    pSessionId = -1;
  v13 = (char *)this + 64;
  CTSCriticalSection::Lock((RdpVCETWEvents *)((char *)this + 64));
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 88, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 96, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 104, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 112, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 120, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 128, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 136, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 144, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 152, 0);
  TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 160, 0);
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::VirtChan::DataSndReq",
                     pSessionId,
                     0,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 88);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_41;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 15;
    v11 = "Failed to initialize RDV::RDP::VirtChan::DataSndReq counter";
    goto LABEL_40;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::VirtChan::DataSndCmplt",
                     pSessionId,
                     0,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 96);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_41;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 16;
    v11 = "Failed to initialize RDV::RDP::VirtChan::DataSndCmplt counter";
    goto LABEL_40;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::VirtChan::OnStreamAlloc",
                     pSessionId,
                     0,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 104);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 17;
      v7 = "Failed to initialize RDV::RDP::VirtChan::OnStreamAlloc counter";
      goto LABEL_28;
    }
  }
  else
  {
    GenericCounter = RDPAPI_GetGenericCounter(
                       L"RDV::RDP::VirtChan::FireSchd",
                       pSessionId,
                       0,
                       0xFFFFFFFFLL,
                       4,
                       (char *)this + 112);
    if ( GenericCounter < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 18;
      v11 = "Failed to initialize RDV::RDP::VirtChan::FireSchd perf counter";
      goto LABEL_40;
    }
    GenericCounter = RDPAPI_GetGenericCounter(
                       L"RDV::RDP::VirtChan::FlushStart",
                       pSessionId,
                       0,
                       0xFFFFFFFFLL,
                       4,
                       (char *)this + 120);
    if ( GenericCounter < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 19;
      v11 = "Failed to initialize RDV::RDP::VirtChan::FlushStart perf counter";
      goto LABEL_40;
    }
    GenericCounter = RDPAPI_GetGenericCounter(
                       L"RDV::RDP::VirtChan::FlushCmplt",
                       pSessionId,
                       0,
                       0xFFFFFFFFLL,
                       4,
                       (char *)this + 128);
    if ( GenericCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 20;
        v7 = "Failed to initialize RDV::RDP::VirtChan::FlushCmplt perf counter";
        goto LABEL_28;
      }
    }
    else
    {
      GenericCounter = RDPAPI_GetGenericCounter(
                         L"RDV::RDP::VirtChan::DataRecv",
                         pSessionId,
                         0,
                         0xFFFFFFFFLL,
                         4,
                         (char *)this + 136);
      if ( GenericCounter >= 0 )
      {
        GenericCounter = RDPAPI_GetGenericCounter(
                           L"RDV::RDP::VirtChan::DataRecvCmplt",
                           pSessionId,
                           0,
                           0xFFFFFFFFLL,
                           4,
                           (char *)this + 144);
        if ( GenericCounter < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_41;
          }
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          v10 = 22;
          v11 = "Failed to initialize RDV::RDP::VirtChan::DataRecvCmplt counter";
        }
        else
        {
          GenericCounter = RDPAPI_GetGenericCounter(
                             L"RDV::RDP::VirtChan::ChannelOpened",
                             pSessionId,
                             0,
                             0xFFFFFFFFLL,
                             4,
                             (char *)this + 152);
          if ( GenericCounter < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_41;
            }
            v9 = RdpWppGetCurrentThreadActivityIdPrefix();
            v10 = 23;
            v11 = "Failed to initialize RDV::RDP::VirtChan::ChannelOpened counter";
          }
          else
          {
            GenericCounter = RDPAPI_GetGenericCounter(
                               L"RDV::RDP::VirtChan::ChannelClosed",
                               pSessionId,
                               0,
                               0xFFFFFFFFLL,
                               4,
                               (char *)this + 160);
            if ( GenericCounter < 0 )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_41;
              }
              v9 = RdpWppGetCurrentThreadActivityIdPrefix();
              v10 = 24;
              v11 = "Failed to initialize RDV::RDP::VirtChan::ChannelClosed counter";
            }
            else
            {
              GenericCounter = RDPAPI_GetGenericCounter(
                                 L"RDV::RDP::VirtChan::OnTunnelToTransportSwitchForRead",
                                 pSessionId,
                                 0,
                                 0xFFFFFFFFLL,
                                 4,
                                 (char *)this + 176);
              if ( GenericCounter < 0 )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_41;
                }
                v9 = RdpWppGetCurrentThreadActivityIdPrefix();
                v10 = 25;
                v11 = "Failed to initialize RDV::RDP::VirtChan::OnTunnelToTransportSwitchForRead counter";
              }
              else
              {
                GenericCounter = RDPAPI_GetGenericCounter(
                                   L"RDV::RDP::VirtChan::OnTunnelToTransportSwitchForWrite",
                                   pSessionId,
                                   0,
                                   0xFFFFFFFFLL,
                                   4,
                                   (char *)this + 184);
                if ( GenericCounter < 0 )
                {
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_41;
                  }
                  v9 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v10 = 26;
                  v11 = "Failed to initialize RDV::RDP::VirtChan::OnTunnelToTransportSwitchForWrite counter";
                }
                else
                {
                  GenericCounter = RDPAPI_GetGenericCounter(
                                     L"RDV::RDP::VirtChan::OnSoftSyncEnabled",
                                     pSessionId,
                                     0,
                                     0xFFFFFFFFLL,
                                     4,
                                     (char *)this + 168);
                  if ( GenericCounter >= 0 )
                  {
                    if ( this != (RdpVCETWEvents *)-64LL )
                      CTSCriticalSection::UnLock((RdpVCETWEvents *)((char *)this + 64));
                    RdpVCETWEvents::TestLoggingEnabled(this);
                    return (unsigned int)GenericCounter;
                  }
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
LABEL_41:
                    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v13);
                    return (unsigned int)GenericCounter;
                  }
                  v9 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v10 = 27;
                  v11 = "Failed to initialize RDV::RDP::VirtChan::OnSoftSyncEnabled counter";
                }
              }
            }
          }
        }
LABEL_40:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          (unsigned int)WPP_169544b849a53ab0319c391a750509f8_Traceguids,
          v9,
          (__int64)v11,
          GenericCounter);
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 21;
        v7 = "Failed to initialize RDV::RDP::VirtChan::DataRecv counter";
LABEL_28:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          (unsigned int)WPP_169544b849a53ab0319c391a750509f8_Traceguids,
          v5,
          (__int64)v7,
          GenericCounter);
      }
    }
  }
  if ( this != (RdpVCETWEvents *)-64LL )
    CTSCriticalSection::UnLock((RdpVCETWEvents *)((char *)this + 64));
  return (unsigned int)GenericCounter;
}

```

## disassembly

```asm
0x18000fddc  mov     [rsp-38h+arg_10], rbx
0x18000fde1  push    rbp
0x18000fde2  push    rsi
0x18000fde3  push    rdi
0x18000fde4  push    r12
0x18000fde6  push    r13
0x18000fde8  push    r14
0x18000fdea  push    r15
0x18000fdec  mov     rbp, rsp
0x18000fdef  sub     rsp, 30h
0x18000fdf3  mov     rsi, rcx
0x18000fdf6  mov     rax, cs:WPP_GLOBAL_Control
0x18000fdfd  lea     rcx, WPP_GLOBAL_Control
0x18000fe04  cmp     rax, rcx
0x18000fe07  jnz     loc_1800101F9
0x18000fe0d  mov     qword ptr [rsi+0C0h], 1
0x18000fe18  call    cs:__imp_GetTickCount
0x18000fe1e  mov     [rsi+0C8h], eax
0x18000fe24  mov     [rbp+pSessionId], 0
0x18000fe2b  call    cs:__imp_GetCurrentProcessId
0x18000fe31  mov     ecx, eax; dwProcessId
0x18000fe33  lea     rdx, [rbp+pSessionId]; pSessionId
0x18000fe37  call    cs:__imp_ProcessIdToSessionId
0x18000fe3d  test    eax, eax
0x18000fe3f  jnz     short loc_18000FE48
0x18000fe41  mov     [rbp+pSessionId], 0FFFFFFFFh
0x18000fe48  lea     rbx, [rsi+40h]
0x18000fe4c  mov     rcx, rbx; this
0x18000fe4f  mov     [rbp+arg_8], rbx
0x18000fe53  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18000fe58  lea     rdi, [rsi+58h]
0x18000fe5c  xor     edx, edx
0x18000fe5e  mov     rcx, rdi
0x18000fe61  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fe66  lea     r14, [rsi+60h]
0x18000fe6a  xor     edx, edx
0x18000fe6c  mov     rcx, r14
0x18000fe6f  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fe74  lea     r15, [rsi+68h]
0x18000fe78  xor     edx, edx
0x18000fe7a  mov     rcx, r15
0x18000fe7d  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fe82  lea     r12, [rsi+70h]
0x18000fe86  xor     edx, edx
0x18000fe88  mov     rcx, r12
0x18000fe8b  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fe90  lea     r13, [rsi+78h]
0x18000fe94  xor     edx, edx
0x18000fe96  mov     rcx, r13
0x18000fe99  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fe9e  lea     rcx, [rsi+80h]
0x18000fea5  xor     edx, edx
0x18000fea7  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000feac  lea     rcx, [rsi+88h]
0x18000feb3  xor     edx, edx
0x18000feb5  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000feba  lea     rcx, [rsi+90h]
0x18000fec1  xor     edx, edx
0x18000fec3  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fec8  lea     rcx, [rsi+98h]
0x18000fecf  xor     edx, edx
0x18000fed1  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fed6  lea     rcx, [rsi+0A0h]
0x18000fedd  xor     edx, edx
0x18000fedf  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18000fee4  mov     edx, [rbp+pSessionId]
0x18000fee7  lea     rcx, aRdvRdpVirtchan_4; "RDV::RDP::VirtChan::DataSndReq"
0x18000feee  or      r9d, 0FFFFFFFFh
0x18000fef2  mov     [rsp+30h+var_8], rdi
0x18000fef7  xor     r8d, r8d
0x18000fefa  mov     dword ptr [rsp+30h+var_10], 4
0x18000ff02  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ff08  mov     edi, eax
0x18000ff0a  test    eax, eax
0x18000ff0c  js      loc_18001027A
0x18000ff12  mov     edx, [rbp+pSessionId]
0x18000ff15  lea     rcx, aRdvRdpVirtchan_6; "RDV::RDP::VirtChan::DataSndCmplt"
0x18000ff1c  mov     [rsp+30h+var_8], r14
0x18000ff21  xor     r8d, r8d
0x18000ff24  or      r14d, 0FFFFFFFFh
0x18000ff28  mov     dword ptr [rsp+30h+var_10], 4
0x18000ff30  mov     r9d, r14d
0x18000ff33  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ff39  mov     edi, eax
0x18000ff3b  test    eax, eax
0x18000ff3d  js      loc_1800102EE
0x18000ff43  mov     edx, [rbp+pSessionId]
0x18000ff46  lea     rcx, aRdvRdpVirtchan_8; "RDV::RDP::VirtChan::OnStreamAlloc"
0x18000ff4d  mov     [rsp+30h+var_8], r15
0x18000ff52  mov     r9d, r14d
0x18000ff55  mov     r15d, 4
0x18000ff5b  xor     r8d, r8d
0x18000ff5e  mov     dword ptr [rsp+30h+var_10], r15d
0x18000ff63  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ff69  mov     edi, eax
0x18000ff6b  test    eax, eax
0x18000ff6d  js      loc_180010239
0x18000ff73  mov     edx, [rbp+pSessionId]
0x18000ff76  lea     rcx, aRdvRdpVirtchan_9; "RDV::RDP::VirtChan::FireSchd"
0x18000ff7d  mov     [rsp+30h+var_8], r12
0x18000ff82  mov     r9d, r14d
0x18000ff85  xor     r8d, r8d
0x18000ff88  mov     dword ptr [rsp+30h+var_10], r15d
0x18000ff8d  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ff93  mov     edi, eax
0x18000ff95  test    eax, eax
0x18000ff97  js      loc_180010320
0x18000ff9d  mov     edx, [rbp+pSessionId]
0x18000ffa0  lea     rcx, aRdvRdpVirtchan_7; "RDV::RDP::VirtChan::FlushStart"
0x18000ffa7  mov     [rsp+30h+var_8], r13
0x18000ffac  mov     r9d, r14d
0x18000ffaf  xor     r8d, r8d
0x18000ffb2  mov     dword ptr [rsp+30h+var_10], r15d
0x18000ffb7  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ffbd  mov     edi, eax
0x18000ffbf  test    eax, eax
0x18000ffc1  js      loc_180010355
0x18000ffc7  mov     edx, [rbp+pSessionId]
0x18000ffca  lea     rax, [rsi+80h]
0x18000ffd1  mov     [rsp+30h+var_8], rax
0x18000ffd6  lea     rcx, aRdvRdpVirtchan_12; "RDV::RDP::VirtChan::FlushCmplt"
0x18000ffdd  mov     r9d, r14d
0x18000ffe0  mov     dword ptr [rsp+30h+var_10], r15d
0x18000ffe5  xor     r8d, r8d
0x18000ffe8  call    cs:__imp_RDPAPI_GetGenericCounter
0x18000ffee  mov     edi, eax
0x18000fff0  test    eax, eax
0x18000fff2  js      loc_180010166
0x18000fff8  mov     edx, [rbp+pSessionId]
0x18000fffb  lea     rax, [rsi+88h]
0x180010002  mov     [rsp+30h+var_8], rax
0x180010007  lea     rcx, aRdvRdpVirtchan_0; "RDV::RDP::VirtChan::DataRecv"
0x18001000e  mov     r9d, r14d
0x180010011  mov     dword ptr [rsp+30h+var_10], r15d
0x180010016  xor     r8d, r8d
0x180010019  call    cs:__imp_RDPAPI_GetGenericCounter
0x18001001f  mov     edi, eax
0x180010021  test    eax, eax
0x180010023  js      loc_1800101A4
0x180010029  mov     edx, [rbp+pSessionId]
0x18001002c  lea     rax, [rsi+90h]
0x180010033  mov     [rsp+30h+var_8], rax
0x180010038  lea     rcx, aRdvRdpVirtchan_5; "RDV::RDP::VirtChan::DataRecvCmplt"
0x18001003f  mov     r9d, r14d
0x180010042  mov     dword ptr [rsp+30h+var_10], r15d
0x180010047  xor     r8d, r8d
0x18001004a  call    cs:__imp_RDPAPI_GetGenericCounter
0x180010050  mov     edi, eax
0x180010052  test    eax, eax
0x180010054  js      loc_1800103C0
0x18001005a  mov     edx, [rbp+pSessionId]
0x18001005d  lea     rax, [rsi+98h]
0x180010064  mov     [rsp+30h+var_8], rax
0x180010069  lea     rcx, aRdvRdpVirtchan_10; "RDV::RDP::VirtChan::ChannelOpened"
0x180010070  mov     r9d, r14d
0x180010073  mov     dword ptr [rsp+30h+var_10], r15d
0x180010078  xor     r8d, r8d
0x18001007b  call    cs:__imp_RDPAPI_GetGenericCounter
0x180010081  mov     edi, eax
0x180010083  test    eax, eax
0x180010085  js      loc_180010401
0x18001008b  mov     edx, [rbp+pSessionId]
0x18001008e  lea     rax, [rsi+0A0h]
0x180010095  mov     [rsp+30h+var_8], rax
0x18001009a  lea     rcx, aRdvRdpVirtchan; "RDV::RDP::VirtChan::ChannelClosed"
0x1800100a1  mov     r9d, r14d
0x1800100a4  mov     dword ptr [rsp+30h+var_10], r15d
0x1800100a9  xor     r8d, r8d
0x1800100ac  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800100b2  mov     edi, eax
0x1800100b4  test    eax, eax
0x1800100b6  js      loc_180010442
0x1800100bc  mov     edx, [rbp+pSessionId]
0x1800100bf  lea     rax, [rsi+0B0h]
0x1800100c6  mov     [rsp+30h+var_8], rax
0x1800100cb  lea     rcx, aRdvRdpVirtchan_1; "RDV::RDP::VirtChan::OnTunnelToTransport"...
0x1800100d2  mov     r9d, r14d
0x1800100d5  mov     dword ptr [rsp+30h+var_10], r15d
0x1800100da  xor     r8d, r8d
0x1800100dd  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800100e3  mov     edi, eax
0x1800100e5  test    eax, eax
0x1800100e7  js      loc_180010483
0x1800100ed  mov     edx, [rbp+pSessionId]
0x1800100f0  lea     rax, [rsi+0B8h]
0x1800100f7  mov     [rsp+30h+var_8], rax
0x1800100fc  lea     rcx, aRdvRdpVirtchan_3; "RDV::RDP::VirtChan::OnTunnelToTransport"...
0x180010103  mov     r9d, r14d
0x180010106  mov     dword ptr [rsp+30h+var_10], r15d
0x18001010b  xor     r8d, r8d
0x18001010e  call    cs:__imp_RDPAPI_GetGenericCounter
0x180010114  mov     edi, eax
0x180010116  test    eax, eax
0x180010118  js      loc_1800104C4
0x18001011e  mov     edx, [rbp+pSessionId]
0x180010121  lea     rax, [rsi+0A8h]
0x180010128  mov     [rsp+30h+var_8], rax
0x18001012d  lea     rcx, aRdvRdpVirtchan_11; "RDV::RDP::VirtChan::OnSoftSyncEnabled"
0x180010134  mov     r9d, r14d
0x180010137  mov     dword ptr [rsp+30h+var_10], r15d
0x18001013c  xor     r8d, r8d
0x18001013f  call    cs:__imp_RDPAPI_GetGenericCounter
0x180010145  mov     edi, eax
0x180010147  test    eax, eax
0x180010149  js      loc_180010505
0x18001014f  test    rbx, rbx
0x180010152  jz      short loc_18001015C
0x180010154  mov     rcx, rbx; this
0x180010157  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18001015c  mov     rcx, rsi; this
0x18001015f  call    ?TestLoggingEnabled@RdpVCETWEvents@@QEAAXXZ; RdpVCETWEvents::TestLoggingEnabled(void)
0x180010164  jmp     short loc_18001018A
0x180010166  mov     rax, cs:WPP_GLOBAL_Control
0x18001016d  lea     rcx, WPP_GLOBAL_Control
0x180010174  cmp     rax, rcx
0x180010177  jnz     loc_180010396
0x18001017d  test    rbx, rbx
0x180010180  jz      short loc_18001018A
0x180010182  mov     rcx, rbx; this
0x180010185  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18001018a  mov     rbx, [rsp+30h+arg_10]
0x180010192  mov     eax, edi
0x180010194  add     rsp, 30h
0x180010198  pop     r15
0x18001019a  pop     r14
0x18001019c  pop     r13
0x18001019e  pop     r12
0x1800101a0  pop     rdi
0x1800101a1  pop     rsi
0x1800101a2  pop     rbp
0x1800101a3  retn
0x1800101a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800101ab  lea     rcx, WPP_GLOBAL_Control
0x1800101b2  cmp     rax, rcx
0x1800101b5  jz      short loc_18001017D
0x1800101b7  test    byte ptr [rax+1Ch], 8
0x1800101bb  jz      short loc_18001017D
0x1800101bd  cmp     byte ptr [rax+19h], 2
0x1800101c1  jb      short loc_18001017D
0x1800101c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800101c8  mov     edx, 15h
0x1800101cd  lea     rcx, aFailedToInitia_58; "Failed to initialize RDV::RDP::VirtChan"...
0x1800101d4  mov     dword ptr [rsp+30h+var_8], edi
0x1800101d8  lea     r8, WPP_169544b849a53ab0319c391a750509f8_Traceguids
0x1800101df  mov     [rsp+30h+var_10], rcx
0x1800101e4  mov     r9d, eax
0x1800101e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ee  mov     rcx, [rcx+10h]
0x1800101f2  call    WPP_SF_DsD
0x1800101f7  jmp     short loc_18001017D
0x1800101f9  test    dword ptr [rax+1Ch], 800h
0x180010200  jz      loc_18000FE0D
0x180010206  cmp     byte ptr [rax+19h], 5
0x18001020a  jb      loc_18000FE0D
0x180010210  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180010215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001021c  lea     r8, WPP_169544b849a53ab0319c391a750509f8_Traceguids
0x180010223  mov     edx, 0Eh
0x180010228  mov     r9d, eax
0x18001022b  mov     rcx, [rcx+10h]
0x18001022f  call    WPP_SF_d
0x180010234  jmp     loc_18000FE0D
0x180010239  mov     rax, cs:WPP_GLOBAL_Control
0x180010240  lea     rcx, WPP_GLOBAL_Control
0x180010247  cmp     rax, rcx
0x18001024a  jz      loc_18001017D
0x180010250  test    byte ptr [rax+1Ch], 8
0x180010254  jz      loc_18001017D
0x18001025a  cmp     byte ptr [rax+19h], 2
0x18001025e  jb      loc_18001017D
0x180010264  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180010269  mov     edx, 11h
0x18001026e  lea     rcx, aFailedToInitia_13; "Failed to initialize RDV::RDP::VirtChan"...
0x180010275  jmp     loc_1800101D4
0x18001027a  mov     rax, cs:WPP_GLOBAL_Control
0x180010281  lea     rcx, WPP_GLOBAL_Control
0x180010288  cmp     rax, rcx
0x18001028b  jz      short loc_1800102E0
0x18001028d  test    byte ptr [rax+1Ch], 8
0x180010291  jz      short loc_1800102E0
0x180010293  cmp     byte ptr [rax+19h], 2
0x180010297  jb      short loc_1800102E0
0x180010299  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001029e  mov     edx, 0Fh
0x1800102a3  lea     rcx, aFailedToInitia_66; "Failed to initialize RDV::RDP::VirtChan"...
0x1800102aa  jmp     short loc_1800102BD
0x1800102ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800102b1  mov     edx, 1Bh
0x1800102b6  lea     rcx, aFailedToInitia_54; "Failed to initialize RDV::RDP::VirtChan"...
0x1800102bd  mov     dword ptr [rsp+30h+var_8], edi
0x1800102c1  lea     r8, WPP_169544b849a53ab0319c391a750509f8_Traceguids
0x1800102c8  mov     [rsp+30h+var_10], rcx
0x1800102cd  mov     r9d, eax
0x1800102d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102d7  mov     rcx, [rcx+10h]
0x1800102db  call    WPP_SF_DsD
0x1800102e0  lea     rcx, [rbp+arg_8]; this
0x1800102e4  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800102e9  jmp     loc_18001018A
0x1800102ee  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
