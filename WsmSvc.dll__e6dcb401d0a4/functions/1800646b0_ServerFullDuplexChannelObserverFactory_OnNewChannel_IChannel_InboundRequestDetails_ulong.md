# ServerFullDuplexChannelObserverFactory::OnNewChannel(IChannel *,InboundRequestDetails *,ulong)

- ea: `0x1800646b0`
- end: `0x1800652ac`
- name: `?OnNewChannel@ServerFullDuplexChannelObserverFactory@@UEAAPEAVIChannelObserver@@PEAVIChannel@@PEAVInboundRequestDetails@@K@Z`
- size: `3068`
- prototype: `struct IChannelObserver *__fastcall(ServerFullDuplexChannelObserverFactory *__hidden this, struct IChannel *, struct InboundRequestDetails *, unsigned int)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x1800254d0`
- `0x180028014`
- `0x18002b7a0`
- `0x18004a900`
- `0x1800567e0`
- `0x18005d800`
- `0x180063fa0`
- `0x180064250`
- `0x1800646b0`
- `0x1800652b4`
- `0x180065370`
- `0x180068b24`
- `0x1800be5a0`
- `0x1800c2d30`
- `0x1800ed634`
- `0x180112380`
- `0x1801133b0`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011d96c`
- `0x18012c2b4`
- `0x180171a18`
- `0x18018b4ec`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006492a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006495c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006492a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006495c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064848`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800649b1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064a10`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064d83`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064848`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800649b1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064a10`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180064d83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006472c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006472c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006485f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006485f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800647ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800647ec`

## string_xrefs

- `0x18006494b`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x180064dc4`: `onecore\admin\wmi\wmx\service\serverfullduplexchannel.cpp`
- `0x1800650a4`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180064e49`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x180064f9c`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x180064fce`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x180065141`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x1800651f6`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x18006521e`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct IChannelObserver *__fastcall ServerFullDuplexChannelObserverFactory::OnNewChannel(
        ServerFullDuplexChannelObserverFactory *this,
        struct IChannel *a2,
        struct InboundRequestDetails *a3)
{
  unsigned __int16 **v5; // rdi
  unsigned __int16 *v6; // rsi
  char v7; // bl
  ServerFullDuplexChannel *v8; // r12
  char *v9; // r13
  DWORD v10; // ecx
  void *v11; // rdx
  CHeap *v12; // rcx
  unsigned int v13; // ebx
  struct IChannelObserver *v14; // rbx
  CHeap *v15; // rcx
  void *Handle; // rax
  ServerFullDuplexChannel *v17; // rax
  ServerFullDuplexChannel *v18; // rdi
  HLOCAL v19; // rcx
  const unsigned __int16 *Value; // rax
  void **v22; // rax
  HLOCAL v23; // rcx
  __int64 v24; // rdx
  HLOCAL v25; // rcx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rdx
  __int64 *v28; // rax
  __int64 *v29; // r9
  __int64 *v30; // rcx
  __int64 *v31; // rbx
  char *v32; // rax
  signed __int64 v33; // r8
  unsigned __int16 v34; // dx
  int v35; // eax
  __int64 v36; // rax
  unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  unsigned __int16 v39; // dx
  int v40; // eax
  unsigned __int16 ***v41; // rbx
  __int64 v42; // r13
  int v43; // eax
  __int64 v44; // rbx
  int v45; // r15d
  int v46; // r12d
  HLOCAL v47; // r15
  const unsigned __int16 *v48; // rax
  __int64 v49; // r9
  HLOCAL v50; // rcx
  PVOID *v51; // rcx
  unsigned __int8 v52; // al
  int v53; // r8d
  _QWORD *v54; // rbx
  int v55; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  void *v57; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v58; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v59; // [rsp+50h] [rbp-20h] BYREF
  char *v60; // [rsp+58h] [rbp-18h] BYREF
  int v61; // [rsp+60h] [rbp-10h]
  void *v62; // [rsp+B0h] [rbp+40h] BYREF
  struct IChannel *v63; // [rsp+B8h] [rbp+48h]
  ServerFullDuplexChannel *v64; // [rsp+C0h] [rbp+50h] BYREF

  v63 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, this, a2);
  v5 = 0;
  v6 = 0;
  v57 = 0;
  v7 = 0;
  LOBYTE(v62) = 0;
  v8 = (ServerFullDuplexChannel *)*((_QWORD *)a3 + 33);
  v64 = v8;
  if ( !v8 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 1623, L"1623", 0x54Fu, 0);
  v9 = (char *)this + 64;
  v60 = (char *)this + 64;
  v61 = 0;
  v10 = *((_DWORD *)this + 16);
  if ( v10 )
  {
    SetLastError(v10);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
  if ( *((_DWORD *)v8 + 716) )
  {
    Value = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue((char *)v8 + 2864);
    v22 = (void **)StringKeyStore::StringKeyStore((StringKeyStore *)&v62, Value);
    v6 = (unsigned __int16 *)*v22;
    v57 = *v22;
    *v22 = 0;
    if ( v62 )
      WSManMemory::Free(v62, 0);
    if ( !v6 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 24LL))(*((_QWORD *)a3 + 9));
      goto LABEL_117;
    }
    if ( !*((_QWORD *)this + 3) || !*((_QWORD *)this + 7) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 24LL))(*((_QWORD *)a3 + 9));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, v6);
      goto LABEL_117;
    }
    LOBYTE(v62) = 1;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 16LL))((char *)this + 16);
    v28 = (__int64 *)*((_QWORD *)this + 3);
    v29 = (__int64 *)*v28;
    v30 = *(__int64 **)(*v28 + 8);
    v31 = (__int64 *)*v28;
    if ( *((_BYTE *)v30 + 25) )
      goto LABEL_72;
    do
    {
      v32 = (char *)v30[4];
      if ( !v32 )
        goto LABEL_63;
      v33 = (char *)v6 - v32;
      while ( 1 )
      {
        v34 = *(_WORD *)v32;
        if ( *(_WORD *)v32 != *(_WORD *)&v32[v33] )
          break;
        v32 += 2;
        if ( !v34 )
        {
          v35 = 0;
          goto LABEL_62;
        }
      }
      v35 = v34 < *(_WORD *)&v32[v33] ? -1 : 1;
LABEL_62:
      if ( v35 >= 0 )
      {
        v31 = v30;
        v30 = (__int64 *)*v30;
      }
      else
      {
LABEL_63:
        v30 = (__int64 *)v30[2];
      }
    }
    while ( !*((_BYTE *)v30 + 25) );
    if ( v31 == v29 )
      goto LABEL_72;
    v36 = v31[4];
    if ( v36 )
    {
      v37 = v6;
      v38 = v36 - (_QWORD)v6;
      while ( 1 )
      {
        v39 = *v37;
        if ( *v37 != *(unsigned __int16 *)((char *)v37 + v38) )
          break;
        ++v37;
        if ( !v39 )
        {
          v40 = 0;
          goto LABEL_71;
        }
      }
      v40 = v39 < *(unsigned __int16 *)((char *)v37 + v38) ? -1 : 1;
LABEL_71:
      if ( v40 < 0 )
        goto LABEL_72;
    }
    if ( *((_BYTE *)v31 + 48) )
LABEL_72:
      v41 = 0;
    else
      v41 = (unsigned __int16 ***)(v31 + 5);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16);
    v8 = v64;
    if ( v41 )
      v5 = *v41;
    v7 = (char)v62;
  }
  v11 = (void *)*((_QWORD *)a3 + 84);
  hMem = 0;
  if ( v11 && !(unsigned int)CSecurity::ExtractSidFromToken(*((struct IRequestContext **)a3 + 9), v11, &hMem) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids);
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 144LL))(*((_QWORD *)a3 + 9)) )
      goto LABEL_131;
    v26 = L"1658";
    v27 = 1658;
    goto LABEL_130;
  }
  if ( v5 )
  {
    v51 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)&WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids,
        (_DWORD)v5,
        (__int64)v6);
      v51 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)a3 + 704) )
    {
      if ( !AllowRequestToJoinOriginalChannel(
              v5[146],
              (struct AutoLocalFree *)&hMem,
              *((struct CRequestContext **)a3 + 9)) )
      {
        if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 144LL))(*((_QWORD *)a3 + 9)) )
        {
LABEL_131:
          v14 = 0;
LABEL_151:
          AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&hMem);
          InCritSec::~InCritSec((InCritSec *)&v60);
          StringKeyStore::Release((StringKeyStore *)&v57);
          return v14;
        }
        v26 = L"1677";
        v27 = 1677;
LABEL_130:
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", v27, v26, 0x54Fu, 0);
        goto LABEL_131;
      }
      if ( !v7 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 1681, L"1681", 0x54Fu, 0);
      if ( !*((_DWORD *)v8 + 720) )
      {
        v14 = ServerFullDuplexChannel::SetSecondaryChannel(
                (ServerFullDuplexChannel *)v5,
                v63,
                *((struct CRequestContext **)a3 + 9));
        goto LABEL_151;
      }
      v52 = SafeMap<StringKeyStore,ServerFullDuplexChannel *,SafeMap_Iterator<StringKeyStore,ServerFullDuplexChannel *>>::Remove(
              (char *)this + 16,
              &v57);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_dqS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          v53,
          v52,
          (char)v5,
          (__int64)v6);
      v54 = v5 + 108;
      StringKeyStore::Release((StringKeyStore *)(v5 + 108));
      v5 = 0;
      *v54 = 0;
      goto LABEL_9;
    }
    if ( v51 != &WPP_GLOBAL_Control && (*((_DWORD *)v51 + 7) & 0x400) != 0 )
      WPP_SF_q(v51[2], 72, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, this);
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)a3 + 9) + 64LL))(
      *((_QWORD *)a3 + 9),
      2150858767LL,
      1077134620);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&hMem);
LABEL_117:
    InCritSec::~InCritSec((InCritSec *)&v60);
    StringKeyStore::Release((StringKeyStore *)&v57);
    return 0;
  }
LABEL_9:
  if ( *((_DWORD *)v8 + 1075) != (_DWORD)v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a3 + 9) + 72LL))(*((_QWORD *)a3 + 9), 2150858767LL);
    v23 = hMem;
    hMem = v5;
    if ( v23 )
      LocalFree(v23);
    CWSManCriticalSection::Release((ServerFullDuplexChannelObserverFactory *)((char *)this + 64));
    if ( v6 )
      WSManMemory::Free(v6, 0);
    return 0;
  }
  v55 = 2;
  v59 = (unsigned __int64)v5;
  v58 = (unsigned __int64)v5;
  LOBYTE(v64) = (_BYTE)v5;
  v13 = PacketParser::ParseRobustConnectionMessages(v8, (enum PacketParser::PacketType *)&v55, (bool *)&v64, &v58, &v59);
  if ( v13 || v55 != 2 || (_BYTE)v64 != (_BYTE)v5 && v58 > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids);
    v24 = 2150858767LL;
    if ( v13 )
      v24 = v13;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a3 + 9) + 72LL))(*((_QWORD *)a3 + 9), v24);
    v25 = hMem;
    hMem = v5;
    if ( v25 )
      LocalFree(v25);
    CWSManCriticalSection::Release((ServerFullDuplexChannelObserverFactory *)((char *)this + 64));
    if ( !v6 )
      return 0;
    goto LABEL_49;
  }
  v14 = 0;
  LODWORD(v64) = 0;
  v59 = (unsigned __int64)&v64;
  if ( CHeap::GetHandle(v12) )
  {
    Handle = CHeap::GetHandle(v15);
    v17 = (ServerFullDuplexChannel *)HeapAlloc(Handle, 0, 0x4A8u);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v17 = 0;
  }
  v58 = (unsigned __int64)v17;
  if ( v17 )
    v18 = ServerFullDuplexChannel::ServerFullDuplexChannel(v17);
  else
    v18 = 0;
  v64 = v18;
  if ( !v18 )
    goto LABEL_18;
  if ( !FullDuplexChannel::IsValid(v18) )
  {
    (**(void (__fastcall ***)(ServerFullDuplexChannel *, __int64))v18)(v18, 1);
LABEL_18:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 24LL))(*((_QWORD *)a3 + 9));
    v18 = 0;
LABEL_19:
    v14 = (struct IChannelObserver *)(((unsigned __int64)v18 + 16) & -(__int64)(v18 != 0));
    v19 = hMem;
    hMem = 0;
    if ( v19 )
      LocalFree(v19);
    if ( *(_DWORD *)v9 )
      SetLastError(*(_DWORD *)v9);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    if ( v6 )
      WSManMemory::Free(v6, 0);
    return v14;
  }
  if ( !(_BYTE)v62 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, v18);
    goto LABEL_83;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)&WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids,
      (_DWORD)v18,
      (__int64)v6);
  v48 = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue((char *)v8 + 2864);
  StringKeyStore::StringKeyStore((StringKeyStore *)&v62, v48);
  v49 = *((_QWORD *)a3 + 9);
  if ( !v62 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49 + 24LL))(*((_QWORD *)a3 + 9));
LABEL_150:
    (**(void (__fastcall ***)(ServerFullDuplexChannel *, __int64))v18)(v18, 1);
    StringKeyStore::Release((StringKeyStore *)&v62);
    goto LABEL_151;
  }
  if ( !(unsigned __int8)SafeMap<StringKeyStore,ServerFullDuplexChannel *,SafeMap_Iterator<StringKeyStore,ServerFullDuplexChannel *>>::Add(
                           (char *)this + 16,
                           &v62,
                           &v64,
                           v49) )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 144LL))(*((_QWORD *)a3 + 9)) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 1744, L"1744", 0x54Fu, 0);
    goto LABEL_150;
  }
  if ( !v6 || !this )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\serverfullduplexchannel.cpp", 856, L"856", 0x54Fu, 0);
    if ( !v6 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\FullDuplexChannel.h", 62, L"62", 0x54Fu, 0);
  }
  if ( *((_QWORD *)v18 + 108) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\SafeMap.h", 636, L"636", 0x54Fu, 0);
  *((_QWORD *)v18 + 108) = v6;
  v6 = 0;
  v57 = 0;
  *((_QWORD *)v18 + 144) = this;
  if ( v62 )
    WSManMemory::Free(v62, 0);
LABEL_83:
  v42 = (*(__int64 (__fastcall **)(_QWORD, ServerFullDuplexChannel *, struct InboundRequestDetails *, _QWORD))(**((_QWORD **)this + 1) + 8LL))(
          *((_QWORD *)this + 1),
          v18,
          a3,
          0);
  v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 9) + 144LL))(*((_QWORD *)a3 + 9));
  if ( v42 )
  {
    if ( !v43 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 1766, L"1766", 0x54Fu, 0);
    v44 = *((_QWORD *)v8 + 4);
    v45 = *((_DWORD *)a3 + 171);
    v46 = *((_DWORD *)a3 + 170);
    if ( !v44 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\FullDuplexChannel.h", 69, L"69", 0x54Fu, 0);
    *((_DWORD *)v18 + 264) = v46;
    *((_DWORD *)v18 + 265) = v45;
    *((_QWORD *)v18 + 109) = v44;
    (*(void (__fastcall **)(__int64, struct IChannel *))(*((_QWORD *)v18 + 2) + 8LL))((__int64)v18 + 16, v63);
    *((_QWORD *)v18 + 1) = v42;
    v47 = hMem;
    hMem = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_ee2eb9f9b8423112dd090e2de83555b3_Traceguids, v47);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>((void **)v18 + 146);
    *((_QWORD *)v18 + 146) = v47;
    if ( !*((_BYTE *)a3 + 704) )
      *((_BYTE *)v18 + 1184) = 1;
    v9 = v60;
    goto LABEL_19;
  }
  if ( v43 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 1760, L"1760", 0x54Fu, 0);
  (**(void (__fastcall ***)(ServerFullDuplexChannel *, __int64))v18)(v18, 1);
  v50 = hMem;
  hMem = 0;
  if ( v50 )
    LocalFree(v50);
  CWSManCriticalSection::Release((ServerFullDuplexChannelObserverFactory *)((char *)this + 64));
  if ( v6 )
LABEL_49:
    WSManMemory::Free(v6, 0);
  return 0;
}

```

## disassembly

```asm
0x1800646b0  mov     [rsp-38h+arg_18], rbx
0x1800646b5  mov     [rsp-38h+arg_8], rdx
0x1800646ba  push    rbp
0x1800646bb  push    rsi
0x1800646bc  push    rdi
0x1800646bd  push    r12
0x1800646bf  push    r13
0x1800646c1  push    r14
0x1800646c3  push    r15
0x1800646c5  mov     rbp, rsp
0x1800646c8  sub     rsp, 70h
0x1800646cc  mov     r14, r8
0x1800646cf  mov     rax, rdx
0x1800646d2  mov     r15, rcx
0x1800646d5  lea     rdx, WPP_GLOBAL_Control
0x1800646dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800646e3  cmp     rcx, rdx
0x1800646e6  jnz     loc_180064DFF
0x1800646ec  xor     edi, edi
0x1800646ee  xor     esi, esi
0x1800646f0  mov     [rbp+var_30], rsi
0x1800646f4  xor     bl, bl
0x1800646f6  mov     byte ptr [rbp+arg_0], bl
0x1800646f9  mov     r12, [r14+108h]
0x180064700  mov     [rbp+arg_10], r12
0x180064704  test    r12, r12
0x180064707  jz      loc_180064E2E
0x18006470d  lea     r13, [r15+40h]
0x180064711  mov     [rbp+var_18], r13
0x180064715  mov     [rbp+var_10], 0
0x18006471c  mov     ecx, [r13+0]; dwErrCode
0x180064720  test    ecx, ecx
0x180064722  jnz     loc_18006492A
0x180064728  lea     rcx, [r13+8]; lpCriticalSection
0x18006472c  call    cs:__imp_EnterCriticalSection
0x180064732  nop
0x180064733  lea     rax, [r12+0B30h]
0x18006473b  cmp     dword ptr [rax], 0
0x18006473e  jnz     loc_180064892
0x180064744  mov     rdx, [r14+2A0h]; TokenHandle
0x18006474b  mov     [rbp+hMem], 0
0x180064753  test    rdx, rdx
0x180064756  jnz     loc_180064A32
0x18006475c  test    rdi, rdi
0x18006475f  jnz     loc_180064EE6
0x180064765  cmp     [r12+10CCh], edi
0x18006476d  jnz     loc_180064977
0x180064773  mov     [rbp+var_40], 2
0x18006477a  mov     [rbp+var_20], rdi
0x18006477e  mov     [rbp+var_28], rdi
0x180064782  mov     byte ptr [rbp+arg_10], dil
0x180064786  lea     rax, [rbp+var_20]
0x18006478a  mov     [rsp+70h+var_50], rax; unsigned __int64 *
0x18006478f  lea     r9, [rbp+var_28]; unsigned __int64 *
0x180064793  lea     r8, [rbp+arg_10]; bool *
0x180064797  lea     rdx, [rbp+var_40]; enum PacketParser::PacketType *
0x18006479b  mov     rcx, r12; this
0x18006479e  call    ?ParseRobustConnectionMessages@PacketParser@@QEAAKPEAW4PacketType@1@PEA_NPEA_K2@Z; PacketParser::ParseRobustConnectionMessages(PacketParser::PacketType *,bool *,unsigned __int64 *,unsigned __int64 *)
0x1800647a3  mov     ebx, eax
0x1800647a5  test    eax, eax
0x1800647a7  jnz     loc_1800649D1
0x1800647ad  cmp     [rbp+var_40], 2
0x1800647b1  jnz     loc_1800649D1
0x1800647b7  cmp     byte ptr [rbp+arg_10], dil
0x1800647bb  jnz     loc_18006507D
0x1800647c1  xor     ebx, ebx
0x1800647c3  mov     dword ptr [rbp+arg_10], ebx
0x1800647c6  lea     rax, [rbp+arg_10]
0x1800647ca  mov     [rbp+var_20], rax
0x1800647ce  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800647d3  test    rax, rax
0x1800647d6  jz      loc_18006508D
0x1800647dc  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800647e1  xor     edx, edx; dwFlags
0x1800647e3  mov     r8d, 4A8h; dwBytes
0x1800647e9  mov     rcx, rax; hHeap
0x1800647ec  call    cs:__imp_HeapAlloc
0x1800647f2  mov     [rbp+var_28], rax
0x1800647f6  test    rax, rax
0x1800647f9  jz      loc_18006488A
0x1800647ff  mov     rcx, rax; this
0x180064802  call    ??0ServerFullDuplexChannel@@QEAA@XZ; ServerFullDuplexChannel::ServerFullDuplexChannel(void)
0x180064807  mov     rdi, rax
0x18006480a  mov     [rbp+arg_10], rdi
0x18006480e  test    rdi, rdi
0x180064811  jnz     loc_1800650B8
0x180064817  mov     rcx, [r14+48h]
0x18006481b  mov     rax, [rcx]
0x18006481e  mov     rax, [rax+18h]
0x180064822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064827  mov     rdi, rbx
0x18006482a  lea     rax, [rdi+10h]
0x18006482e  neg     rdi
0x180064831  sbb     rbx, rbx
0x180064834  and     rbx, rax
0x180064837  mov     rcx, [rbp+hMem]; hMem
0x18006483b  mov     [rbp+hMem], 0
0x180064843  test    rcx, rcx
0x180064846  jz      short loc_18006484F
0x180064848  call    cs:__imp_LocalFree
0x18006484e  nop
0x18006484f  mov     ecx, [r13+0]; dwErrCode
0x180064853  test    ecx, ecx
0x180064855  jnz     loc_18006495C
0x18006485b  lea     rcx, [r13+8]; lpCriticalSection
0x18006485f  call    cs:__imp_LeaveCriticalSection
0x180064865  nop
0x180064866  test    rsi, rsi
0x180064869  jnz     loc_180064967
0x18006486f  mov     rax, rbx
0x180064872  mov     rbx, [rsp+70h+arg_18]
0x18006487a  add     rsp, 70h
0x18006487e  pop     r15
0x180064880  pop     r14
0x180064882  pop     r13
0x180064884  pop     r12
0x180064886  pop     rdi
0x180064887  pop     rsi
0x180064888  pop     rbp
0x180064889  retn
0x18006488a  mov     rdi, rbx
0x18006488d  jmp     loc_18006480A
0x180064892  mov     rcx, rax
0x180064895  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x18006489a  mov     rdx, rax; unsigned __int16 *
0x18006489d  lea     rcx, [rbp+arg_0]; this
0x1800648a1  call    ??0StringKeyStore@@QEAA@PEBG@Z; StringKeyStore::StringKeyStore(ushort const *)
0x1800648a6  nop
0x1800648a7  mov     rsi, [rax]
0x1800648aa  mov     [rbp+var_30], rsi
0x1800648ae  xor     ebx, ebx
0x1800648b0  mov     [rax], rbx
0x1800648b3  mov     rcx, [rbp+arg_0]; void *
0x1800648b7  test    rcx, rcx
0x1800648ba  jnz     loc_180064AA2
0x1800648c0  test    rsi, rsi
0x1800648c3  jz      loc_180064E5A
0x1800648c9  cmp     [r15+18h], rbx
0x1800648cd  jz      short loc_1800648D9
0x1800648cf  cmp     [r15+38h], rbx
0x1800648d3  jnz     loc_180064ABF
0x1800648d9  mov     rcx, [r14+48h]
0x1800648dd  mov     rax, [rcx]
0x1800648e0  mov     rax, [rax+18h]
0x1800648e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800648f0  lea     rdx, WPP_GLOBAL_Control
0x1800648f7  cmp     rcx, rdx
0x1800648fa  jz      loc_180064EAA
0x180064900  test    dword ptr [rcx+1Ch], 400h
0x180064907  jz      loc_180064EAA
0x18006490d  mov     edx, 45h ; 'E'
0x180064912  mov     r9, rsi
0x180064915  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x18006491c  mov     rcx, [rcx+10h]
0x180064920  call    WPP_SF_S
0x180064925  jmp     loc_180064EAA
0x18006492a  call    cs:__imp_SetLastError
0x180064930  mov     [rsp+70h+var_50], 0; struct IRequestContext *
0x180064939  mov     r9d, 54Fh; unsigned int
0x18006493f  lea     r8, a59; "59"
0x180064946  mov     edx, 3Bh ; ';'; unsigned int
0x18006494b  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180064952  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180064957  jmp     loc_180064733
0x18006495c  call    cs:__imp_SetLastError
0x180064962  jmp     loc_180064866
0x180064967  xor     edx, edx; int
0x180064969  mov     rcx, rsi; void *
0x18006496c  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180064971  nop
0x180064972  jmp     loc_18006486F
0x180064977  mov     rcx, cs:WPP_GLOBAL_Control
0x18006497e  lea     rax, WPP_GLOBAL_Control
0x180064985  cmp     rcx, rax
0x180064988  jnz     loc_180065056
0x18006498e  mov     rcx, [r14+48h]
0x180064992  mov     rax, [rcx]
0x180064995  mov     edx, 8033800Fh
0x18006499a  mov     rax, [rax+48h]
0x18006499e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649a3  nop
0x1800649a4  mov     rcx, [rbp+hMem]; hMem
0x1800649a8  mov     [rbp+hMem], rdi
0x1800649ac  test    rcx, rcx
0x1800649af  jz      short loc_1800649B8
0x1800649b1  call    cs:__imp_LocalFree
0x1800649b7  nop
0x1800649b8  mov     rcx, r13; this
0x1800649bb  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x1800649c0  nop
0x1800649c1  test    rsi, rsi
0x1800649c4  jnz     loc_180064AAF
0x1800649ca  xor     eax, eax
0x1800649cc  jmp     loc_180064872
0x1800649d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800649d8  lea     rax, WPP_GLOBAL_Control
0x1800649df  cmp     rcx, rax
0x1800649e2  jnz     loc_180065284
0x1800649e8  mov     rcx, [r14+48h]
0x1800649ec  mov     rax, [rcx]
0x1800649ef  mov     edx, 8033800Fh
0x1800649f4  test    ebx, ebx
0x1800649f6  cmovnz  edx, ebx
0x1800649f9  mov     rax, [rax+48h]
0x1800649fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a02  nop
0x180064a03  mov     rcx, [rbp+hMem]; hMem
0x180064a07  mov     [rbp+hMem], rdi
0x180064a0b  test    rcx, rcx
0x180064a0e  jz      short loc_180064A17
0x180064a10  call    cs:__imp_LocalFree
0x180064a16  nop
0x180064a17  mov     rcx, r13; this
0x180064a1a  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x180064a1f  nop
0x180064a20  test    rsi, rsi
0x180064a23  jz      short loc_1800649CA
0x180064a25  xor     edx, edx; int
0x180064a27  mov     rcx, rsi; void *
0x180064a2a  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180064a2f  nop
0x180064a30  jmp     short loc_1800649CA
0x180064a32  lea     r8, [rbp+hMem]; struct AutoLocalFree *
0x180064a36  mov     rcx, [r14+48h]; struct IRequestContext *
0x180064a3a  call    ?ExtractSidFromToken@CSecurity@@SAHPEAVIRequestContext@@PEAXAEAVAutoLocalFree@@@Z; CSecurity::ExtractSidFromToken(IRequestContext *,void *,AutoLocalFree &)
0x180064a3f  test    eax, eax
0x180064a41  jnz     loc_18006475C
0x180064a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a4e  lea     rdx, WPP_GLOBAL_Control
0x180064a55  cmp     rcx, rdx
0x180064a58  jz      short loc_180064A76
0x180064a5a  test    dword ptr [rcx+1Ch], 400h
0x180064a61  jz      short loc_180064A76
0x180064a63  lea     edx, [rax+46h]
0x180064a66  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x180064a6d  mov     rcx, [rcx+10h]
0x180064a71  call    WPP_SF_
0x180064a76  mov     rcx, [r14+48h]
0x180064a7a  mov     rax, [rcx]
0x180064a7d  mov     rax, [rax+90h]
0x180064a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a89  test    eax, eax
0x180064a8b  jz      loc_180064FA8
0x180064a91  lea     r8, a1658; "1658"
0x180064a98  mov     edx, 67Ah
0x180064a9d  jmp     loc_180064F8D
0x180064aa2  xor     edx, edx; int
0x180064aa4  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180064aa9  nop
0x180064aaa  jmp     loc_1800648C0
0x180064aaf  xor     edx, edx; int
0x180064ab1  mov     rcx, rsi; void *
0x180064ab4  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180064ab9  nop
0x180064aba  jmp     loc_1800649CA
0x180064abf  mov     byte ptr [rbp+arg_0], 1
0x180064ac3  lea     r12, [r15+10h]
0x180064ac7  mov     rax, [r12]
0x180064acb  mov     rcx, r12
0x180064ace  mov     rax, [rax+10h]
0x180064ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ad7  mov     rax, [r12+8]
0x180064adc  mov     r9, [rax]
0x180064adf  mov     rcx, [r9+8]
0x180064ae3  mov     rbx, r9
0x180064ae6  xor     r10d, r10d
0x180064ae9  cmp     [rcx+19h], r10b
0x180064aed  jnz     short loc_180064B61
0x180064aef  mov     rax, [rcx+20h]
0x180064af3  test    rax, rax
0x180064af6  jz      loc_180064EC2
0x180064afc  mov     r8, rsi
0x180064aff  sub     r8, rax
0x180064b02  movzx   edx, word ptr [rax]
0x180064b05  cmp     dx, [rax+r8]
0x180064b0a  jnz     loc_180064B92
0x180064b10  add     rax, 2
0x180064b14  test    dx, dx
0x180064b17  jnz     short loc_180064B02
0x180064b19  mov     eax, r10d
0x180064b1c  shr     eax, 1Fh
0x180064b1f  test    al, al
0x180064b21  jz      short loc_180064B8A
0x180064b23  mov     rcx, [rcx+10h]
0x180064b27  cmp     [rcx+19h], r10b
0x180064b2b  jz      short loc_180064AEF
0x180064b2d  cmp     rbx, r9
0x180064b30  jz      short loc_180064B61
0x180064b32  mov     rax, [rbx+20h]
0x180064b36  test    rax, rax
0x180064b39  jz      loc_180064ED0
0x180064b3f  mov     rcx, rsi
0x180064b42  sub     rax, rsi
0x180064b45  movzx   edx, word ptr [rcx]
0x180064b48  cmp     dx, [rcx+rax]
0x180064b4c  jnz     short loc_180064B99
0x180064b4e  add     rcx, 2
0x180064b52  test    dx, dx
0x180064b55  jnz     short loc_180064B45
  ... truncated ...
```
