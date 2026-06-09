# CTnoDownloadMgr::StartInternal(void)

- ea: `0x1800bd818`
- end: `0x1800be09c`
- name: `?StartInternal@CTnoDownloadMgr@@AEAAXXZ`
- size: `2180`
- prototype: `void __fastcall(CTnoDownloadMgr *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bcb20`

## callees

- `0x1800024a4`
- `0x180004374`
- `0x180008290`
- `0x1800094d4`
- `0x180009ec4`
- `0x1800118bc`
- `0x180011a54`
- `0x180015c28`
- `0x180018170`
- `0x180018340`
- `0x180018924`
- `0x180018dc0`
- `0x180019030`
- `0x180020058`
- `0x18002a878`
- `0x1800391e0`
- `0x1800a3a20`
- `0x1800a59bc`
- `0x1800a7634`
- `0x1800a7a28`
- `0x1800a7a98`
- `0x1800b08d4`
- `0x1800b4970`
- `0x1800b4b50`
- `0x1800b5f88`
- `0x1800bd818`
- `0x1800c0708`
- `0x180144882`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800bda92`
- `msvcrt!wcsrchr` at `0x1800bda92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be000`
- `KERNEL32!GetSystemDirectoryW` at `0x1800bda6d`
- `KERNEL32!GetSystemDirectoryW` at `0x1800bda6d`
- `WS2_32!__imp_WSAStartup` at `0x1800bd92d`
- `WS2_32!__imp_WSAStartup` at `0x1800bd92d`
- `WS2_32!__imp_WSACleanup` at `0x1800bd93b`

## string_xrefs

- `0x1800bdf25`: `CTnoDownloadMgr::StartInternal - IHostedCacheMgr::RetrieveInterface(IID_HostedCacheListMgr)  failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CTnoDownloadMgr::StartInternal(CTnoDownloadMgr *this)
{
  int v2; // eax
  int v3; // edi
  CHostedCacheMsgEncoding *v4; // rcx
  UINT SystemDirectoryW; // eax
  char *v6; // rsi
  wchar_t *v7; // rax
  const unsigned __int16 *v8; // r14
  int v9; // edi
  __int64 (__fastcall *ProcAddress)(int *, char *, char *, __int64 *, __int64 *); // r14
  int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // eax
  void *Block; // rax
  DownloadMgrWatchdogTimer *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  DWORD LastError; // eax
  DWORD v20; // ebx
  DWORD v21; // eax
  unsigned int v22; // ebx
  DWORD v23; // eax
  DWORD v24; // ebx
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  int (__stdcall *v29)(); // [rsp+58h] [rbp-A8h]
  char v30[8]; // [rsp+60h] [rbp-A0h] BYREF
  CTnoDownloadMgr *v31; // [rsp+68h] [rbp-98h]
  void (__fastcall *v32)(CTnoDownloadMgr *__hidden); // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  _BYTE v35[12]; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+8Ch] [rbp-74h]
  int v37; // [rsp+90h] [rbp-70h] BYREF
  __int16 v38; // [rsp+94h] [rbp-6Ch]
  __int16 v39; // [rsp+96h] [rbp-6Ah]
  int v40; // [rsp+98h] [rbp-68h]
  int v41; // [rsp+9Ch] [rbp-64h]
  int v42; // [rsp+A0h] [rbp-60h]
  int v43; // [rsp+A4h] [rbp-5Ch]
  int v44; // [rsp+A8h] [rbp-58h]
  __int16 v45; // [rsp+ACh] [rbp-54h]
  unsigned __int16 v46[41]; // [rsp+AEh] [rbp-52h] BYREF
  struct WSAData WSAData; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v26 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(&v37, 0, 0x6Cu);
  v25 = 1;
  memset_0(Buffer, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 176, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))(**((_QWORD **)this + 37) + 16LL))(
         *((_QWORD *)this + 37),
         &IID_HostedCacheListMgr,
         (char *)this + 304);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        177,
        WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        (unsigned int)v2);
    }
    ApplicationError::Throw(
      L"CTnoDownloadMgr::StartInternal - IHostedCacheMgr::RetrieveInterface(IID_HostedCacheListMgr)  failed",
      v3);
  }
  CTnoDownloadMgr::RegisterHostedCacheListObserver(this);
  v30[0] = 0;
  v31 = this;
  v32 = CTnoDownloadMgr::UnregisterHostedCacheListObserver;
  v33 = 0;
  v34 = v36;
  CTnoDownloadMgr::RetrieveSettings(this);
  if ( WSAStartup(0x202u, &WSAData) )
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 178, WPP_99bbad5960d7305007009c99b002d393_Traceguids, LastError);
    }
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", v20);
  }
  v28[0] = 0;
  v29 = WSACleanup;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 179, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 108) & 8) != 0 && *((_BYTE *)v4 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v4 + 12), 180, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 108) & 8) != 0 && *((_BYTE *)v4 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v4 + 12), 181, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v4 + 108) & 8) != 0 && *((_BYTE *)v4 + 105) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)v4 + 12),
              182,
              WPP_99bbad5960d7305007009c99b002d393_Traceguids,
              *((unsigned int *)this + 117));
            v4 = WPP_GLOBAL_Control;
          }
          if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v4 + 108) & 8) != 0 && *((_BYTE *)v4 + 105) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)v4 + 12),
                183,
                WPP_99bbad5960d7305007009c99b002d393_Traceguids,
                *((unsigned int *)this + 118));
              v4 = WPP_GLOBAL_Control;
            }
            if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v4 + 108) & 8) != 0
              && *((_BYTE *)v4 + 105) >= 3u )
            {
              WPP_SF_(*((_QWORD *)v4 + 12), 184, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
            }
          }
        }
      }
    }
  }
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    v21 = GetLastError();
    v22 = v21;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 185, WPP_99bbad5960d7305007009c99b002d393_Traceguids, v21);
    }
    if ( !v22 )
      v22 = 774;
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", v22);
  }
  if ( SystemDirectoryW >= 0x104 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        186,
        WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        SystemDirectoryW);
    }
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", 774);
  }
  v6 = (char *)this + 720;
  v7 = wcsrchr((const wchar_t *)this + 360, 0x5Cu);
  v8 = (const unsigned __int16 *)((char *)this + 720);
  if ( v7 )
    v8 = v7 + 1;
  v9 = StringCchCatW(Buffer, 0x104u, L"\\");
  if ( v9 < 0 || (v9 = StringCchCatW(Buffer, 0x104u, v8), v9 < 0) )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        187,
        WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        (unsigned int)v9);
    }
    v18 = TnoWin32ErrFromHR(v9);
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", v18);
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 188, WPP_99bbad5960d7305007009c99b002d393_Traceguids, Buffer);
  }
  DllHandle::Load((CTnoDownloadMgr *)((char *)this + 1760), Buffer);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 189, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
  }
  ProcAddress = (__int64 (__fastcall *)(int *, char *, char *, __int64 *, __int64 *))DllHandle::GetProcAddress(
                                                                                       (char *)this + 1760,
                                                                                       "PeerDistTransportStartup");
  if ( !ProcAddress )
  {
    v23 = GetLastError();
    v24 = v23;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_sDS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        190,
        (unsigned int)WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        (unsigned int)"PeerDistTransportStartup",
        v23,
        (__int64)v6);
    }
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", v24);
  }
  *((_DWORD *)this + 92) = 1;
  *((_DWORD *)this + 78) = 1;
  *((_QWORD *)this + 40) = &CTnoDownloadMgr::OnSendRequestCompleted;
  *((_QWORD *)this + 41) = &CTnoDownloadMgr::OnSendResponseCompleted;
  *((_QWORD *)this + 43) = &CTnoDownloadMgr::OnResendRequestNeeded;
  *((_QWORD *)this + 44) = &CTnoDownloadMgr::OnRequest;
  *((_QWORD *)this + 45) = &CTnoDownloadMgr::OnResponse;
  v37 = 1;
  v40 = *((_DWORD *)this + 117);
  v41 = 0;
  v42 = *((_DWORD *)this + 118);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_56311274>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_56311274>::GetImpl'::`2'::impl) )
    v43 = *((_DWORD *)this + 145);
  v38 = *((_WORD *)this + 336);
  v39 = *((_WORD *)this + 337);
  v44 = 2;
  v45 = 0;
  v11 = StringCchCopyW(v46, 0x27u, L"116B50EB-ECE2-41ac-8429-9F9E963361B7");
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        191,
        (unsigned int)WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        v11,
        (__int64)this + 720);
    }
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", (unsigned __int16)v11);
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 192, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
  }
  v12 = ProcAddress(&v37, (char *)this + 312, (char *)this + 368, &v26, &v25);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_sDS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        193,
        (unsigned int)WPP_99bbad5960d7305007009c99b002d393_Traceguids,
        (unsigned int)"PeerDistTransportStartup",
        v12,
        (__int64)this + 720);
    }
    if ( v12 == 32 )
      CTnoDownloadMgr::LogDownloadListenPortInUse(*((_WORD *)this + 336));
    SystemError::Throw<unsigned long>(L"CTnoDownloadMgr::StartInternal", v12);
  }
  *((_QWORD *)this + 30) = v26;
  v13 = (**((__int64 (__fastcall ***)(char *, char *))this + 545))((char *)this + 4360, (char *)this + 1240);
  if ( v13 )
  {
    if ( v13 == 4064 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 194, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 195, WPP_99bbad5960d7305007009c99b002d393_Traceguids, v13);
    }
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(
    (__int64)v35,
    (RTL_SRWLOCK *)&CTnoDownloadMgr::s_rwMgrsLock);
  v27[0] = *((_QWORD *)this + 30);
  v27[1] = this;
  Block = (void *)std::_Tree_buy<std::pair<void * const,CTnoDownloadMgr *>>::_Buynode<std::pair<void *,CTnoDownloadMgr *>>(
                    &qword_1801A7260,
                    v27);
  std::_Tree<std::_Tmap_traits<void *,CContentFileInfo *,std::less<void *>,std::allocator<std::pair<void * const,CContentFileInfo *>>,0>>::_Insert_nohint<std::pair<void * const,CContentFileInfo *> &,std::_Tree_node<std::pair<void * const,CContentFileInfo *>,void *> *>(
    (int)&qword_1801A7260,
    Block);
  ++CTnoDownloadMgr::s_cTransports;
  LockSentry<ReadersWriterLock,0>::Unlock(v35);
  v15 = (DownloadMgrWatchdogTimer *)operator new(0x38u);
  v27[0] = v15;
  if ( v15 )
    v15 = DownloadMgrWatchdogTimer::DownloadMgrWatchdogTimer(v15, *((void **)this + 30));
  std::auto_ptr<TnoHashKey>::reset((char *)this + 4296, v15, v16, v17);
  CTnoDownloadMgr::RegisterForNotifications(this);
  v28[0] = 1;
  v30[0] = 1;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 196, WPP_99bbad5960d7305007009c99b002d393_Traceguids);
  }
  ScopeGuardImpl0<int (*)(void)>::~ScopeGuardImpl0<int (*)(void)>(v28);
  ObjScopeGuardImpl0<CTnoDownloadMgr,void (CTnoDownloadMgr::*)(void)>::~ObjScopeGuardImpl0<CTnoDownloadMgr,void (CTnoDownloadMgr::*)(void)>(v30);
}

```

## disassembly

```asm
0x1800bd818  push    rbp
0x1800bd81a  push    rbx
0x1800bd81b  push    rsi
0x1800bd81c  push    rdi
0x1800bd81d  push    r12
0x1800bd81f  push    r13
0x1800bd821  push    r14
0x1800bd823  push    r15
0x1800bd825  lea     rbp, [rsp-3C8h]
0x1800bd82d  sub     rsp, 4C8h
0x1800bd834  mov     rax, cs:__security_cookie
0x1800bd83b  xor     rax, rsp
0x1800bd83e  mov     [rbp+400h+var_50], rax
0x1800bd845  mov     rbx, rcx
0x1800bd848  xor     r14d, r14d
0x1800bd84b  mov     [rsp+500h+var_4C8], r14
0x1800bd850  xor     edx, edx; Val
0x1800bd852  mov     r8d, 198h; Size
0x1800bd858  lea     rcx, [rbp+400h+WSAData]; void *
0x1800bd85c  call    memset_0
0x1800bd861  xor     edx, edx; Val
0x1800bd863  lea     r8d, [r14+6Ch]; Size
0x1800bd867  lea     rcx, [rbp+400h+var_470]; void *
0x1800bd86b  call    memset_0
0x1800bd870  lea     esi, [r14+1]
0x1800bd874  mov     [rsp+500h+var_4D0], rsi
0x1800bd879  xor     edx, edx; Val
0x1800bd87b  mov     r8d, 208h; Size
0x1800bd881  lea     rcx, [rbp+400h+Buffer]; void *
0x1800bd888  call    memset_0
0x1800bd88d  lea     r15, WPP_GLOBAL_Control
0x1800bd894  lea     r12, WPP_99bbad5960d7305007009c99b002d393_Traceguids
0x1800bd89b  mov     r13b, 8
0x1800bd89e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd8a5  cmp     rcx, r15
0x1800bd8a8  jz      short loc_1800BD8C7
0x1800bd8aa  test    [rcx+6Ch], r13b
0x1800bd8ae  jz      short loc_1800BD8C7
0x1800bd8b0  cmp     byte ptr [rcx+69h], 4
0x1800bd8b4  jb      short loc_1800BD8C7
0x1800bd8b6  mov     edx, 0B0h
0x1800bd8bb  mov     r8, r12
0x1800bd8be  mov     rcx, [rcx+60h]
0x1800bd8c2  call    WPP_SF_
0x1800bd8c7  mov     rcx, [rbx+128h]
0x1800bd8ce  mov     rax, [rcx]
0x1800bd8d1  lea     r8, [rbx+130h]
0x1800bd8d8  lea     rdx, IID_HostedCacheListMgr
0x1800bd8df  mov     rax, [rax+10h]
0x1800bd8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8e8  mov     edi, eax
0x1800bd8ea  test    eax, eax
0x1800bd8ec  js      loc_1800BDEF7
0x1800bd8f2  mov     rcx, rbx; this
0x1800bd8f5  call    ?RegisterHostedCacheListObserver@CTnoDownloadMgr@@AEAAXXZ; CTnoDownloadMgr::RegisterHostedCacheListObserver(void)
0x1800bd8fa  mov     [rsp+500h+var_4A0], r14b
0x1800bd8ff  mov     [rsp+500h+var_498], rbx
0x1800bd904  lea     rax, ?UnregisterHostedCacheListObserver@CTnoDownloadMgr@@AEAAXXZ; CTnoDownloadMgr::UnregisterHostedCacheListObserver(void)
0x1800bd90b  mov     [rsp+500h+var_490], rax
0x1800bd910  mov     [rsp+500h+var_488], r14d
0x1800bd915  mov     eax, [rbp+400h+var_474]
0x1800bd918  mov     [rsp+500h+var_484], eax
0x1800bd91c  mov     rcx, rbx; this
0x1800bd91f  call    ?RetrieveSettings@CTnoDownloadMgr@@AEAAXXZ; CTnoDownloadMgr::RetrieveSettings(void)
0x1800bd924  mov     ecx, 202h; wVersionRequested
0x1800bd929  lea     rdx, [rbp+400h+WSAData]; lpWSAData
0x1800bd92d  call    cs:__imp_WSAStartup
0x1800bd933  test    eax, eax
0x1800bd935  jnz     loc_1800BDF32
0x1800bd93b  mov     rax, cs:__imp_WSACleanup
0x1800bd942  mov     [rsp+500h+var_4B0], r14b
0x1800bd947  mov     [rsp+500h+var_4A8], rax
0x1800bd94c  mov     dil, 3
0x1800bd94f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd956  cmp     rcx, r15
0x1800bd959  jz      loc_1800BDA5F
0x1800bd95f  test    [rcx+6Ch], r13b
0x1800bd963  jz      short loc_1800BD983
0x1800bd965  cmp     [rcx+69h], dil
0x1800bd969  jb      short loc_1800BD983
0x1800bd96b  mov     edx, 0B3h
0x1800bd970  mov     r8, r12
0x1800bd973  mov     rcx, [rcx+60h]
0x1800bd977  call    WPP_SF_
0x1800bd97c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd983  cmp     rcx, r15
0x1800bd986  jz      loc_1800BDA5F
0x1800bd98c  test    [rcx+6Ch], r13b
0x1800bd990  jz      short loc_1800BD9B0
0x1800bd992  cmp     [rcx+69h], dil
0x1800bd996  jb      short loc_1800BD9B0
0x1800bd998  mov     edx, 0B4h
0x1800bd99d  mov     r8, r12
0x1800bd9a0  mov     rcx, [rcx+60h]
0x1800bd9a4  call    WPP_SF_
0x1800bd9a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd9b0  cmp     rcx, r15
0x1800bd9b3  jz      loc_1800BDA5F
0x1800bd9b9  test    [rcx+6Ch], r13b
0x1800bd9bd  jz      short loc_1800BD9DD
0x1800bd9bf  cmp     [rcx+69h], dil
0x1800bd9c3  jb      short loc_1800BD9DD
0x1800bd9c5  mov     edx, 0B5h
0x1800bd9ca  mov     r8, r12
0x1800bd9cd  mov     rcx, [rcx+60h]
0x1800bd9d1  call    WPP_SF_
0x1800bd9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd9dd  cmp     rcx, r15
0x1800bd9e0  jz      short loc_1800BDA5F
0x1800bd9e2  test    [rcx+6Ch], r13b
0x1800bd9e6  jz      short loc_1800BDA0D
0x1800bd9e8  cmp     [rcx+69h], dil
0x1800bd9ec  jb      short loc_1800BDA0D
0x1800bd9ee  mov     edx, 0B6h
0x1800bd9f3  mov     r9d, [rbx+1D4h]
0x1800bd9fa  mov     r8, r12
0x1800bd9fd  mov     rcx, [rcx+60h]
0x1800bda01  call    WPP_SF_d
0x1800bda06  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bda0d  cmp     rcx, r15
0x1800bda10  jz      short loc_1800BDA5F
0x1800bda12  test    [rcx+6Ch], r13b
0x1800bda16  jz      short loc_1800BDA3D
0x1800bda18  cmp     [rcx+69h], dil
0x1800bda1c  jb      short loc_1800BDA3D
0x1800bda1e  mov     edx, 0B7h
0x1800bda23  mov     r9d, [rbx+1D8h]
0x1800bda2a  mov     r8, r12
0x1800bda2d  mov     rcx, [rcx+60h]
0x1800bda31  call    WPP_SF_d
0x1800bda36  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bda3d  cmp     rcx, r15
0x1800bda40  jz      short loc_1800BDA5F
0x1800bda42  test    [rcx+6Ch], r13b
0x1800bda46  jz      short loc_1800BDA5F
0x1800bda48  cmp     [rcx+69h], dil
0x1800bda4c  jb      short loc_1800BDA5F
0x1800bda4e  mov     edx, 0B8h
0x1800bda53  mov     r8, r12
0x1800bda56  mov     rcx, [rcx+60h]
0x1800bda5a  call    WPP_SF_
0x1800bda5f  mov     edi, 104h
0x1800bda64  mov     edx, edi; uSize
0x1800bda66  lea     rcx, [rbp+400h+Buffer]; lpBuffer
0x1800bda6d  call    cs:__imp_GetSystemDirectoryW
0x1800bda73  test    eax, eax
0x1800bda75  jz      loc_1800BDF75
0x1800bda7b  cmp     eax, edi
0x1800bda7d  jnb     loc_1800BDFC2
0x1800bda83  lea     rsi, [rbx+2D0h]
0x1800bda8a  mov     edx, 5Ch ; '\'; Ch
0x1800bda8f  mov     rcx, rsi; Str
0x1800bda92  call    cs:__imp_wcsrchr
0x1800bda98  lea     rcx, [rax+2]
0x1800bda9c  mov     r14, rsi
0x1800bda9f  test    rax, rax
0x1800bdaa2  cmovnz  r14, rcx
0x1800bdaa6  lea     r8, asc_18016BFBC; "\\"
0x1800bdaad  mov     edx, edi; unsigned __int64
0x1800bdaaf  lea     rcx, [rbp+400h+Buffer]; unsigned __int16 *
0x1800bdab6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bdabb  mov     edi, eax
0x1800bdabd  test    eax, eax
0x1800bdabf  js      loc_1800BDEB5
0x1800bdac5  mov     r8, r14; unsigned __int16 *
0x1800bdac8  mov     edx, 104h; unsigned __int64
0x1800bdacd  lea     rcx, [rbp+400h+Buffer]; unsigned __int16 *
0x1800bdad4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bdad9  mov     edi, eax
0x1800bdadb  test    eax, eax
0x1800bdadd  js      loc_1800BDEB5
0x1800bdae3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdaea  cmp     rcx, r15
0x1800bdaed  jz      short loc_1800BDB13
0x1800bdaef  test    [rcx+6Ch], r13b
0x1800bdaf3  jz      short loc_1800BDB13
0x1800bdaf5  cmp     byte ptr [rcx+69h], 3
0x1800bdaf9  jb      short loc_1800BDB13
0x1800bdafb  mov     edx, 0BCh
0x1800bdb00  lea     r9, [rbp+400h+Buffer]
0x1800bdb07  mov     r8, r12
0x1800bdb0a  mov     rcx, [rcx+60h]
0x1800bdb0e  call    WPP_SF_S
0x1800bdb13  lea     rdi, [rbx+6E0h]
0x1800bdb1a  lea     rdx, [rbp+400h+Buffer]; lpLibFileName
0x1800bdb21  mov     rcx, rdi; this
0x1800bdb24  call    ?Load@DllHandle@@QEAAXPEBG@Z; DllHandle::Load(ushort const *)
0x1800bdb29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdb30  cmp     rcx, r15
0x1800bdb33  jz      short loc_1800BDB52
0x1800bdb35  test    [rcx+6Ch], r13b
0x1800bdb39  jz      short loc_1800BDB52
0x1800bdb3b  cmp     byte ptr [rcx+69h], 3
0x1800bdb3f  jb      short loc_1800BDB52
0x1800bdb41  mov     edx, 0BDh
0x1800bdb46  mov     r8, r12
0x1800bdb49  mov     rcx, [rcx+60h]
0x1800bdb4d  call    WPP_SF_
0x1800bdb52  lea     rdx, aPeerdisttransp; "PeerDistTransportStartup"
0x1800bdb59  mov     rcx, rdi
0x1800bdb5c  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x1800bdb61  mov     r14, rax
0x1800bdb64  xor     edi, edi
0x1800bdb66  test    rax, rax
0x1800bdb69  jz      loc_1800BE000
0x1800bdb6f  lea     r15, [rbx+170h]
0x1800bdb76  lea     ecx, [rdi+1]
0x1800bdb79  mov     [r15], ecx
0x1800bdb7c  lea     r12, [rbx+138h]
0x1800bdb83  mov     [r12], ecx
0x1800bdb87  lea     rax, ?OnSendRequestCompleted@CTnoDownloadMgr@@SAKPEAXVPEERDIST_INCREMENTAL_HANDLE@@K@Z; CTnoDownloadMgr::OnSendRequestCompleted(void *,PEERDIST_INCREMENTAL_HANDLE,ulong)
0x1800bdb8e  mov     [rbx+140h], rax
0x1800bdb95  lea     rax, ?OnSendResponseCompleted@CTnoDownloadMgr@@SAKPEAXVPEERDIST_INCREMENTAL_HANDLE@@K@Z; CTnoDownloadMgr::OnSendResponseCompleted(void *,PEERDIST_INCREMENTAL_HANDLE,ulong)
0x1800bdb9c  mov     [rbx+148h], rax
0x1800bdba3  lea     rax, ?OnResendRequestNeeded@CTnoDownloadMgr@@SAKPEAXVPEERDIST_INCREMENTAL_HANDLE@@K@Z; CTnoDownloadMgr::OnResendRequestNeeded(void *,PEERDIST_INCREMENTAL_HANDLE,ulong)
0x1800bdbaa  mov     [rbx+158h], rax
0x1800bdbb1  lea     rax, ?OnRequest@CTnoDownloadMgr@@SAKPEAXVPEERDIST_INCREMENTAL_HANDLE@@PEBUpeerdist_request_tag@@KPEBE@Z; CTnoDownloadMgr::OnRequest(void *,PEERDIST_INCREMENTAL_HANDLE,peerdist_request_tag const *,ulong,uchar const *)
0x1800bdbb8  mov     [rbx+160h], rax
0x1800bdbbf  lea     rax, ?OnResponse@CTnoDownloadMgr@@SAKPEAXVPEERDIST_INCREMENTAL_HANDLE@@KPEBE@Z; CTnoDownloadMgr::OnResponse(void *,PEERDIST_INCREMENTAL_HANDLE,ulong,uchar const *)
0x1800bdbc6  mov     [rbx+168h], rax
0x1800bdbcd  mov     [rbp+400h+var_470], ecx
0x1800bdbd0  mov     eax, [rbx+1D4h]
0x1800bdbd6  mov     [rbp+400h+var_468], eax
0x1800bdbd9  mov     [rbp+400h+var_464], edi
0x1800bdbdc  mov     eax, [rbx+1D8h]
0x1800bdbe2  mov     [rbp+400h+var_460], eax
0x1800bdbe5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_56311274@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_56311274@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_56311274> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_56311274>::GetImpl(void)'::`2'::impl
0x1800bdbec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_56311274@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_56311274>::__private_IsEnabled(void)
0x1800bdbf1  test    al, al
0x1800bdbf3  jz      short loc_1800BDBFE
0x1800bdbf5  mov     eax, [rbx+244h]
0x1800bdbfb  mov     [rbp+400h+var_45C], eax
0x1800bdbfe  movzx   eax, word ptr [rbx+2A0h]
0x1800bdc05  mov     [rbp+400h+var_46C], ax
0x1800bdc09  movzx   eax, word ptr [rbx+2A2h]
0x1800bdc10  mov     [rbp+400h+var_46A], ax
0x1800bdc14  mov     [rbp+400h+var_458], 2
0x1800bdc1b  mov     [rbp+400h+var_454], di
0x1800bdc1f  lea     r8, a116b50ebEce241; "116B50EB-ECE2-41ac-8429-9F9E963361B7"
0x1800bdc26  mov     edx, 27h ; '''; unsigned __int64
0x1800bdc2b  lea     rcx, [rbp+400h+var_452]; unsigned __int16 *
0x1800bdc2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bdc34  mov     edi, eax
0x1800bdc36  test    eax, eax
0x1800bdc38  js      loc_1800BE050
0x1800bdc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdc45  lea     rax, WPP_GLOBAL_Control
0x1800bdc4c  cmp     rcx, rax
0x1800bdc4f  jz      short loc_1800BDC72
0x1800bdc51  test    [rcx+6Ch], r13b
0x1800bdc55  jz      short loc_1800BDC72
0x1800bdc57  cmp     byte ptr [rcx+69h], 3
0x1800bdc5b  jb      short loc_1800BDC72
0x1800bdc5d  mov     edx, 0C0h
0x1800bdc62  lea     r8, WPP_99bbad5960d7305007009c99b002d393_Traceguids
0x1800bdc69  mov     rcx, [rcx+60h]
0x1800bdc6d  call    WPP_SF_
0x1800bdc72  lea     rax, [rsp+500h+var_4D0]
0x1800bdc77  mov     [rsp+500h+Block], rax
0x1800bdc7c  lea     r9, [rsp+500h+var_4C8]
0x1800bdc81  mov     r8, r15
0x1800bdc84  mov     rdx, r12
0x1800bdc87  lea     rcx, [rbp+400h+var_470]
0x1800bdc8b  mov     rax, r14
0x1800bdc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc93  mov     edi, eax
0x1800bdc95  test    eax, eax
0x1800bdc97  jnz     loc_1800BDE51
0x1800bdc9d  mov     rax, [rsp+500h+var_4C8]
0x1800bdca2  mov     [rbx+0F0h], rax
0x1800bdca9  lea     rcx, [rbx+1108h]
0x1800bdcb0  mov     rax, [rcx]
0x1800bdcb3  lea     rdx, [rbx+4D8h]
0x1800bdcba  mov     rax, [rax]
0x1800bdcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdcc2  test    eax, eax
0x1800bdcc4  jz      short loc_1800BDD3C
0x1800bdcc6  cmp     eax, 0FE0h
0x1800bdccb  jnz     short loc_1800BDD03
0x1800bdccd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdcd4  lea     rdi, WPP_GLOBAL_Control
0x1800bdcdb  cmp     rcx, rdi
0x1800bdcde  jz      short loc_1800BDD43
0x1800bdce0  test    [rcx+6Ch], r13b
0x1800bdce4  jz      short loc_1800BDD43
0x1800bdce6  cmp     byte ptr [rcx+69h], 3
0x1800bdcea  jb      short loc_1800BDD43
0x1800bdcec  mov     edx, 0C2h
0x1800bdcf1  lea     r8, WPP_99bbad5960d7305007009c99b002d393_Traceguids
0x1800bdcf8  mov     rcx, [rcx+60h]
0x1800bdcfc  call    WPP_SF_
0x1800bdd01  jmp     short loc_1800BDD43
0x1800bdd03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd0a  lea     rdi, WPP_GLOBAL_Control
0x1800bdd11  cmp     rcx, rdi
0x1800bdd14  jz      short loc_1800BDD43
0x1800bdd16  test    [rcx+6Ch], r13b
0x1800bdd1a  jz      short loc_1800BDD43
0x1800bdd1c  cmp     byte ptr [rcx+69h], 1
0x1800bdd20  jb      short loc_1800BDD43
  ... truncated ...
```
