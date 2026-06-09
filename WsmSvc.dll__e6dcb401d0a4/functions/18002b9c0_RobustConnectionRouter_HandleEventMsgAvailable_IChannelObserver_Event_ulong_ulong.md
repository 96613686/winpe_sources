# RobustConnectionRouter::HandleEventMsgAvailable(IChannelObserver::Event,ulong,ulong)

- ea: `0x18002b9c0`
- end: `0x18002c416`
- name: `?HandleEventMsgAvailable@RobustConnectionRouter@@MEAAXW4Event@IChannelObserver@@KK@Z`
- size: `2646`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800254d0`
- `0x180025d90`
- `0x180026310`
- `0x180028014`
- `0x18002afe0`
- `0x18002b438`
- `0x18002b738`
- `0x18002b7a0`
- `0x18002b9c0`
- `0x18002c580`
- `0x18002dd20`
- `0x18004a900`
- `0x1800520d0`
- `0x18005d800`
- `0x18005f000`
- `0x180063fa0`
- `0x180064250`
- `0x18009e168`
- `0x1800f4158`
- `0x180112380`
- `0x18011a6d4`
- `0x180123660`
- `0x1801236c8`
- `0x1801295f4`
- `0x18012c2b4`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c314`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c393`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c314`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c393`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bbdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002be19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bbdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002be19`

## string_xrefs

- `0x18002bbc2`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18002bdf5`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18002ba7c`: `onecore\admin\wmi\wmx\service\robustconnectionrouter.cpp`
- `0x18002bb1f`: `onecore\admin\wmi\wmx\service\robustconnectionrouter.cpp`
- `0x18002bd55`: `onecore\admin\wmi\wmx\service\robustconnectionrouter.cpp`
- `0x18002bf91`: `onecore\admin\wmi\wmx\service\robustconnectionrouter.cpp`
- `0x18002c271`: `onecore\admin\wmi\wmx\service\robustconnectionrouter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RobustConnectionRouter::HandleEventMsgAvailable(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r14d
  unsigned int v5; // esi
  unsigned __int8 v7; // r15
  __int64 v8; // rax
  PacketParser *v9; // r12
  _DWORD *v10; // rbx
  __int64 Value; // rax
  const unsigned __int16 *v12; // rbx
  __int64 v13; // rcx
  unsigned __int64 v14; // r14
  SIZE_T v15; // rsi
  void *Handle; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  unsigned int v19; // r8d
  struct CRequestContext *v20; // rdx
  __int16 **v21; // rbx
  void *v22; // rdx
  unsigned int RobustConnection; // eax
  __int16 *v24; // rsi
  __int64 v25; // rbx
  unsigned __int64 v26; // rbx
  SIZE_T v27; // r14
  void *v28; // r14
  void *v29; // rax
  _WORD *v30; // rax
  __int64 v31; // rcx
  __int16 v32; // dx
  _WORD *v33; // rdx
  __int64 v34; // r8
  int v35; // r12d
  struct ServerRobustConnection *v36; // rsi
  int v37; // ebx
  struct CRequestContext *v38; // rbx
  unsigned __int16 *v39; // rax
  __int64 v40; // r8
  __int64 v41; // rbx
  bool v42; // cf
  unsigned __int8 v43; // bl
  __int64 v44; // rcx
  char v45; // al
  unsigned int v46; // eax
  __int64 v47; // rcx
  PVOID *v48; // rcx
  unsigned int v49; // esi
  __int64 v50; // rbx
  HLOCAL v51; // rcx
  unsigned int RobustConnectionAndListenerOperation; // eax
  struct CRequestContext *v53; // rdx
  __int64 v54; // rcx
  HLOCAL v55; // rcx
  bool v56; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v58; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v59; // [rsp+58h] [rbp-A8h] BYREF
  int v60; // [rsp+60h] [rbp-A0h]
  unsigned int v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v62; // [rsp+6Ch] [rbp-94h]
  struct ServerRobustConnection *v63; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v64; // [rsp+78h] [rbp-88h]
  unsigned int v65; // [rsp+7Ch] [rbp-84h]
  unsigned __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v67[85]; // [rsp+90h] [rbp-70h] BYREF

  v4 = a4;
  v62 = a4;
  v5 = a3;
  v64 = a3;
  v65 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids, a3, a4, a1);
  v59 = a1 + 1280;
  v60 = 0;
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)(a1 + 1280));
  if ( *(_BYTE *)(a1 + 42) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\robustconnectionrouter.cpp", 289, L"289", 0x54Fu, 0);
  v7 = 1;
  *(_BYTE *)(a1 + 42) = 1;
  if ( *(_BYTE *)(a1 + 53) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids, a1);
    InCritSecWithConditionVar::Release((InCritSecWithConditionVar *)&v59);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
    goto LABEL_11;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 48LL))(*(_QWORD *)(a1 + 24));
  v9 = (PacketParser *)v8;
  if ( !v8 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\robustconnectionrouter.cpp", 306, L"306", 0x54Fu, 0);
LABEL_11:
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v59);
    return;
  }
  hMem = 0;
  v10 = (_DWORD *)(v8 + 2864);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v58 = 0;
    if ( !*v10 )
    {
      *(_BYTE *)(a1 + 52) = 0;
      RobustConnectionAndListenerOperation = RobustConnectionRouter::CreateRobustConnectionAndListenerOperation((RobustConnectionRouter *)a1);
      if ( RobustConnectionAndListenerOperation )
      {
        v53 = *(struct CRequestContext **)(a1 + 1272);
        v54 = *(_QWORD *)(a1 + 1472);
        if ( v54 && *(_QWORD *)(v54 + 72) )
          v53 = *(struct CRequestContext **)(v54 + 72);
        RobustConnectionRouter::HandleIrrecoverableErrorsForRequestNotPassedToUpperLayer(
          (RobustConnectionRouter *)a1,
          v53,
          RobustConnectionAndListenerOperation,
          (struct InCritSecWithConditionVar *)&v59);
        goto LABEL_28;
      }
      v28 = v58;
      goto LABEL_122;
    }
    RobustConnectionRouter::TakeOwnershipOfInboundRequestDetails((RobustConnectionRouter *)a1);
    CRequestContext::CRequestContext((CRequestContext *)v67);
    Value = PacketParser::PacketElement<unsigned short const *>::GetValue(v10);
    v12 = (const unsigned __int16 *)Value;
    if ( !Value )
    {
LABEL_25:
      v19 = 14;
LABEL_26:
      v20 = *(struct CRequestContext **)(a1 + 1272);
LABEL_27:
      RobustConnectionRouter::HandleIrrecoverableErrorsForRequestNotPassedToUpperLayer(
        (RobustConnectionRouter *)a1,
        v20,
        v19,
        (struct InCritSecWithConditionVar *)&v59);
      CRequestContext::~CRequestContext((CRequestContext *)v67);
LABEL_28:
      StringKeyStore::Release((StringKeyStore *)&v58);
LABEL_29:
      AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&hMem);
      goto LABEL_11;
    }
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(Value + 2 * v13) );
    v14 = v13 + 1;
    v15 = 2 * (v13 + 1);
    if ( !is_mul_ok(v13 + 1, 2u) )
      v15 = -1;
    if ( !CHeap::GetHandle((CHeap *)v13) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
LABEL_24:
      (*(void (__fastcall **)(_QWORD *))(v67[0] + 24LL))(v67);
      goto LABEL_25;
    }
    Handle = CHeap::GetHandle(0);
    v17 = (unsigned __int16 *)HeapAlloc(Handle, 0, v15);
    v18 = v17;
    if ( !v17 )
      goto LABEL_24;
    if ( (int)StringCchCopyW(v17, v14, v12) < 0 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 287, L"287", 0x54Fu, 0);
      goto LABEL_25;
    }
    v21 = (__int16 **)(a1 + 1536);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(a1 + 1536);
    *(_QWORD *)(a1 + 1536) = v18;
    v61 = 2;
    v56 = 0;
    v66 = 0;
    v63 = 0;
    if ( PacketParser::ParseRobustConnectionMessages(
           v9,
           (enum PacketParser::PacketType *)&v61,
           &v56,
           &v66,
           (unsigned __int64 *)&v63) )
    {
      goto LABEL_25;
    }
    v22 = *(void **)(*(_QWORD *)(a1 + 1472) + 672LL);
    if ( v22 && !(unsigned int)CSecurity::ExtractSidFromToken(*(struct IRequestContext **)(a1 + 1272), v22, &hMem) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1272) + 144LL))(*(_QWORD *)(a1 + 1272)) )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\robustconnectionrouter.cpp", 373, L"373", 0x54Fu, 0);
      RobustConnection = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1272) + 152LL))(*(_QWORD *)(a1 + 1272));
      goto LABEL_41;
    }
    v63 = 0;
    v24 = *v21;
    if ( !*v21 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\SafeMap.h", 666, L"666", 0x54Fu, 0);
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v26 = v25 + 1;
    v27 = 2 * v26;
    if ( !is_mul_ok(v26, 2u) )
      v27 = -1;
    if ( !CHeap::GetHandle((CHeap *)0xFFFFFFFFFFFFFFFFLL) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
      v28 = 0;
      goto LABEL_62;
    }
    v29 = CHeap::GetHandle(0);
    v30 = HeapAlloc(v29, 0, v27);
    v28 = v30;
    if ( v30 )
    {
      if ( !v26 )
      {
LABEL_61:
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\SafeMap.h", 676, L"676", 0x54Fu, 0);
        goto LABEL_62;
      }
      if ( v26 > 0x7FFFFFFF )
      {
        *v30 = 0;
        goto LABEL_61;
      }
      v31 = 2147483646;
      do
      {
        if ( !v31 )
          break;
        v32 = *v24;
        if ( !*v24 )
          break;
        ++v24;
        *v30++ = v32;
        --v31;
        --v26;
      }
      while ( v26 );
      v33 = v30 - 1;
      if ( v26 )
        v33 = v30;
      *v33 = 0;
      if ( !v26 )
        goto LABEL_61;
    }
LABEL_62:
    v58 = v28;
    if ( !v28 )
      goto LABEL_25;
    RobustConnection = RobustConnectionHistoryTable::FindRobustConnection(
                         *(RobustConnectionHistoryTable **)(a1 + 1440),
                         (struct StringKeyStore *)&v58,
                         &v63);
    v35 = *((_DWORD *)v9 + 720);
    if ( RobustConnection )
    {
      if ( RobustConnection != 1168 )
      {
LABEL_41:
        v19 = RobustConnection;
        goto LABEL_26;
      }
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 1472) + 464LL) - 13) <= 8
        || v35 != 1
        || (v41 = *(_QWORD *)(a1 + 1440),
            v42 = (unsigned __int64)(***(__int64 (__fastcall ****)(_QWORD))(v41 + 152))(*(_QWORD *)(v41 + 152)) < *(_QWORD *)(v41 + 128),
            v43 = 1,
            !v42) )
      {
        v43 = 0;
      }
      v44 = *(_QWORD *)(a1 + 1472);
      if ( (unsigned int)(*(_DWORD *)(v44 + 464) - 13) <= 8 || v35 != 1 || *(_DWORD *)(v44 + 688) )
        v7 = 0;
      LOBYTE(v34) = v56;
      v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64))(*(_QWORD *)a1 + 568LL))(
              a1,
              v61,
              v34,
              v66);
      if ( v43 || v7 || !v45 )
      {
        v48 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WPP_SF_qddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids,
            a1,
            v43,
            v7,
            v45 == 0);
          v48 = (PVOID *)WPP_GLOBAL_Control;
        }
        v49 = v43 != 0 ? -2144108038 : -2144108529;
        v50 = *(_QWORD *)(a1 + 1272);
        if ( v48 != &WPP_GLOBAL_Control && (*((_DWORD *)v48 + 7) & 0x400) != 0 )
          WPP_SF_qLq(v48[2], 49, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids, a1, v49, *(_QWORD *)(a1 + 1272));
        if ( !v50 )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\robustconnectionrouter.cpp",
            985,
            L"985",
            0x54Fu,
            0);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v50 + 144LL))(v50) )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 72LL))(v50, v49);
        (*(void (__fastcall **)(__int64, __int64, __int64 *, _QWORD, _DWORD))(*(_QWORD *)a1 + 208LL))(
          a1,
          v50,
          &v59,
          0,
          0);
        if ( (unsigned int)CWSManCriticalSection::DoesThreadOwnLock((CWSManCriticalSection *)(a1 + 1280)) )
          InCritSecWithConditionVar::Release((InCritSecWithConditionVar *)&v59);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
        CRequestContext::~CRequestContext((CRequestContext *)v67);
        WSManMemory::Free(v28, 0);
        v51 = hMem;
        hMem = 0;
        if ( v51 )
          LocalFree(v51);
        goto LABEL_11;
      }
      v46 = RobustConnectionRouter::CreateRobustConnectionAndListenerOperation((RobustConnectionRouter *)a1);
      if ( v46 )
      {
        v20 = *(struct CRequestContext **)(a1 + 1272);
        v47 = *(_QWORD *)(a1 + 1472);
        if ( v47 && *(_QWORD *)(v47 + 72) )
          v20 = *(struct CRequestContext **)(v47 + 72);
        v19 = v46;
        goto LABEL_27;
      }
      v28 = v58;
      goto LABEL_101;
    }
    v36 = v63;
    if ( !v63 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids, a1);
      v37 = -2144108529;
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 1272) + 72LL))(*(_QWORD *)(a1 + 1272), 2150858767LL);
      goto LABEL_69;
    }
    v38 = *(struct CRequestContext **)(a1 + 1272);
    v39 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct ServerRobustConnection *))(*(_QWORD *)v63 + 512LL))(v63);
    if ( AllowRequestToJoinOriginalChannel(v39, (struct AutoLocalFree *)&hMem, v38) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(struct ServerRobustConnection *, __int64))(*(_QWORD *)v36 + 504LL))(
             v36,
             a1) )
      {
        goto LABEL_74;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids, a1);
      v37 = -2144108529;
    }
    else
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1272) + 144LL))(*(_QWORD *)(a1 + 1272)) )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\robustconnectionrouter.cpp", 431, L"431", 0x54Fu, 0);
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1272) + 152LL))(*(_QWORD *)(a1 + 1272));
      if ( !v37 )
      {
LABEL_74:
        (*(void (__fastcall **)(struct ServerRobustConnection *, const char *))(*(_QWORD *)v36 + 520LL))(
          v36,
          "@OnFindInTable");
        *(_QWORD *)(a1 + 1552) = v36;
        *(_QWORD *)(a1 + 8) = (char *)v36 + 16;
        (*(void (__fastcall **)(struct ServerRobustConnection *, _QWORD))(*(_QWORD *)v36 + 496LL))(
          v36,
          *(_QWORD *)(a1 + 1472));
        if ( v35 != 1 )
        {
          LOBYTE(v40) = v56;
          if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64))(*(_QWORD *)a1 + 568LL))(
                 a1,
                 v61,
                 v40,
                 v66) )
          {
            v19 = -2144108529;
            goto LABEL_26;
          }
        }
LABEL_101:
        CRequestContext::~CRequestContext((CRequestContext *)v67);
        v5 = v64;
LABEL_122:
        if ( v28 )
          WSManMemory::Free(v28, 0);
        v4 = v62;
        goto LABEL_125;
      }
    }
    (*(void (__fastcall **)(struct ServerRobustConnection *, const char *))(*(_QWORD *)v36 + 520LL))(
      v36,
      "@OnFindInTable");
LABEL_69:
    v19 = v37;
    goto LABEL_26;
  }
  if ( *(_BYTE *)(a1 + 52) )
  {
    if ( !*v10 )
      goto LABEL_132;
  }
  else if ( *v10 )
  {
LABEL_132:
    RobustConnectionRouter::HandleIrrecoverableErrorsForRequestNotPassedToUpperLayer(
      (RobustConnectionRouter *)a1,
      *(struct CRequestContext **)(a1 + 1272),
      0x8033800F,
      (struct InCritSecWithConditionVar *)&v59);
    goto LABEL_29;
  }
LABEL_125:
  v55 = hMem;
  hMem = 0;
  if ( v55 )
    LocalFree(v55);
  InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v59);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(
    *(_QWORD *)(a1 + 8),
    v65,
    v5,
    v4);
}

```

## disassembly

```asm
0x18002b9c0  push    rbp
0x18002b9c2  push    rbx
0x18002b9c3  push    rsi
0x18002b9c4  push    rdi
0x18002b9c5  push    r12
0x18002b9c7  push    r13
0x18002b9c9  push    r14
0x18002b9cb  push    r15
0x18002b9cd  lea     rbp, [rsp-248h]
0x18002b9d5  sub     rsp, 348h
0x18002b9dc  mov     rax, cs:__security_cookie
0x18002b9e3  xor     rax, rsp
0x18002b9e6  mov     [rbp+280h+var_48], rax
0x18002b9ed  mov     r14d, r9d
0x18002b9f0  mov     [rsp+380h+var_314], r9d
0x18002b9f5  mov     esi, r8d
0x18002b9f8  mov     [rsp+380h+var_308], r8d
0x18002b9fd  mov     [rsp+380h+var_304], edx
0x18002ba01  mov     rdi, rcx
0x18002ba04  lea     rax, WPP_GLOBAL_Control
0x18002ba0b  mov     r12d, 400h
0x18002ba11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba18  cmp     rcx, rax
0x18002ba1b  jz      short loc_18002BA45
0x18002ba1d  test    [rcx+1Ch], r12d
0x18002ba21  jz      short loc_18002BA45
0x18002ba23  mov     edx, 19h
0x18002ba28  mov     [rsp+380h+var_358], rdi
0x18002ba2d  mov     dword ptr [rsp+380h+var_360], r9d
0x18002ba32  mov     r9d, r8d
0x18002ba35  lea     r8, WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids
0x18002ba3c  mov     rcx, [rcx+10h]
0x18002ba40  call    WPP_SF_ddq
0x18002ba45  lea     r13, [rdi+500h]
0x18002ba4c  mov     [rsp+380h+var_328], r13
0x18002ba51  xor     ebx, ebx
0x18002ba53  mov     [rsp+380h+var_320], ebx
0x18002ba57  mov     rcx, r13; this
0x18002ba5a  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18002ba5f  nop
0x18002ba60  cmp     [rdi+2Ah], bl
0x18002ba63  jz      short loc_18002BA88
0x18002ba65  mov     [rsp+380h+var_360], rbx; struct IRequestContext *
0x18002ba6a  mov     r9d, 54Fh; unsigned int
0x18002ba70  lea     r8, a289; "289"
0x18002ba77  mov     edx, 121h; unsigned int
0x18002ba7c  lea     rcx, aOnecoreAdminWm_80; "onecore\\admin\\wmi\\wmx\\service\\robu"...
0x18002ba83  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002ba88  mov     r15d, 1
0x18002ba8e  mov     [rdi+2Ah], r15b
0x18002ba92  cmp     [rdi+35h], bl
0x18002ba95  jz      short loc_18002BAF0
0x18002ba97  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba9e  lea     rdx, WPP_GLOBAL_Control
0x18002baa5  cmp     rcx, rdx
0x18002baa8  jz      short loc_18002BAC7
0x18002baaa  test    [rcx+1Ch], r12d
0x18002baae  jz      short loc_18002BAC7
0x18002bab0  lea     edx, [r15+19h]
0x18002bab4  mov     r9, rdi
0x18002bab7  lea     r8, WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids
0x18002babe  mov     rcx, [rcx+10h]
0x18002bac2  call    WPP_SF_q
0x18002bac7  lea     rcx, [rsp+380h+var_328]; this
0x18002bacc  call    ?Release@InCritSecWithConditionVar@@QEAAXXZ; InCritSecWithConditionVar::Release(void)
0x18002bad1  mov     rax, [rdi]
0x18002bad4  mov     rcx, rdi
0x18002bad7  mov     rax, [rax+48h]
0x18002badb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae0  nop
0x18002bae1  lea     rcx, [rsp+380h+var_328]; this
0x18002bae6  call    ??1InCritSecWithConditionVar@@QEAA@XZ; InCritSecWithConditionVar::~InCritSecWithConditionVar(void)
0x18002baeb  jmp     loc_18002C3BE
0x18002baf0  mov     rcx, [rdi+18h]
0x18002baf4  mov     rax, [rcx]
0x18002baf7  mov     rax, [rax+30h]
0x18002bafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb00  mov     r12, rax
0x18002bb03  test    rax, rax
0x18002bb06  jnz     short loc_18002BB2D
0x18002bb08  mov     [rsp+380h+var_360], rbx; struct IRequestContext *
0x18002bb0d  mov     r9d, 54Fh; unsigned int
0x18002bb13  lea     r8, a306; "306"
0x18002bb1a  mov     edx, 132h; unsigned int
0x18002bb1f  lea     rcx, aOnecoreAdminWm_80; "onecore\\admin\\wmi\\wmx\\service\\robu"...
0x18002bb26  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002bb2b  jmp     short loc_18002BAE1
0x18002bb2d  mov     [rsp+380h+hMem], rbx
0x18002bb32  lea     rbx, [rax+0B30h]
0x18002bb39  cmp     qword ptr [rdi+8], 0
0x18002bb3e  jnz     loc_18002C3E1
0x18002bb44  xor     r14d, r14d
0x18002bb47  mov     [rsp+380h+var_330], r14
0x18002bb4c  mov     rcx, rdi; this
0x18002bb4f  cmp     [rbx], r14d
0x18002bb52  jz      loc_18002C31F
0x18002bb58  call    ?TakeOwnershipOfInboundRequestDetails@RobustConnectionRouter@@IEAAXXZ; RobustConnectionRouter::TakeOwnershipOfInboundRequestDetails(void)
0x18002bb5d  lea     rcx, [rbp+280h+var_2F0]; this
0x18002bb61  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x18002bb66  nop
0x18002bb67  mov     rcx, rbx
0x18002bb6a  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x18002bb6f  mov     rbx, rax
0x18002bb72  test    rax, rax
0x18002bb75  jz      loc_18002BBFC
0x18002bb7b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bb7f  mov     rcx, r8
0x18002bb82  inc     rcx; this
0x18002bb85  cmp     [rax+rcx*2], r14w
0x18002bb8a  jnz     short loc_18002BB82
0x18002bb8c  lea     r14, [rcx+1]
0x18002bb90  mov     eax, 2
0x18002bb95  mul     r14
0x18002bb98  mov     rsi, rax
0x18002bb9b  cmovb   rsi, r8
0x18002bb9f  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18002bba4  xor     ecx, ecx; this
0x18002bba6  test    rax, rax
0x18002bba9  jnz     short loc_18002BBD0
0x18002bbab  mov     [rsp+380h+var_360], rcx; struct IRequestContext *
0x18002bbb0  mov     r9d, 54Fh; unsigned int
0x18002bbb6  lea     r8, a170; "170"
0x18002bbbd  mov     edx, 0AAh; unsigned int
0x18002bbc2  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002bbc9  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002bbce  jmp     short loc_18002BBEB
0x18002bbd0  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18002bbd5  mov     r8, rsi; dwBytes
0x18002bbd8  xor     edx, edx; dwFlags
0x18002bbda  mov     rcx, rax; hHeap
0x18002bbdd  call    cs:__imp_HeapAlloc
0x18002bbe3  mov     rsi, rax
0x18002bbe6  test    rax, rax
0x18002bbe9  jnz     short loc_18002BC3B
0x18002bbeb  mov     rax, [rbp+280h+var_2F0]
0x18002bbef  lea     rcx, [rbp+280h+var_2F0]
0x18002bbf3  mov     rax, [rax+18h]
0x18002bbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbfc  mov     r8d, 0Eh; unsigned int
0x18002bc02  mov     rdx, [rdi+4F8h]; struct CRequestContext *
0x18002bc09  lea     r9, [rsp+380h+var_328]; struct InCritSecWithConditionVar *
0x18002bc0e  mov     rcx, rdi; this
0x18002bc11  call    ?HandleIrrecoverableErrorsForRequestNotPassedToUpperLayer@RobustConnectionRouter@@IEAAXPEAVCRequestContext@@KPEAVInCritSecWithConditionVar@@@Z; RobustConnectionRouter::HandleIrrecoverableErrorsForRequestNotPassedToUpperLayer(CRequestContext *,ulong,InCritSecWithConditionVar *)
0x18002bc16  nop
0x18002bc17  lea     rcx, [rbp+280h+var_2F0]; this
0x18002bc1b  call    ??1CRequestContext@@UEAA@XZ; CRequestContext::~CRequestContext(void)
0x18002bc20  nop
0x18002bc21  lea     rcx, [rsp+380h+var_330]; this
0x18002bc26  call    ?Release@StringKeyStore@@AEAAXXZ; StringKeyStore::Release(void)
0x18002bc2b  nop
0x18002bc2c  lea     rcx, [rsp+380h+hMem]; void *
0x18002bc31  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18002bc36  jmp     loc_18002BAE1
0x18002bc3b  mov     r8, rbx; unsigned __int16 *
0x18002bc3e  mov     rdx, r14; unsigned __int64
0x18002bc41  mov     rcx, rsi; unsigned __int16 *
0x18002bc44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bc49  xor     r14d, r14d
0x18002bc4c  test    eax, eax
0x18002bc4e  jns     short loc_18002BC75
0x18002bc50  mov     [rsp+380h+var_360], r14; struct IRequestContext *
0x18002bc55  mov     r9d, 54Fh; unsigned int
0x18002bc5b  lea     r8, a287; "287"
0x18002bc62  mov     edx, 11Fh; unsigned int
0x18002bc67  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18002bc6e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002bc73  jmp     short loc_18002BBFC
0x18002bc75  lea     rbx, [rdi+600h]
0x18002bc7c  mov     rcx, rbx
0x18002bc7f  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18002bc84  mov     [rbx], rsi
0x18002bc87  mov     [rsp+380h+var_318], 2
0x18002bc8f  mov     [rsp+380h+var_340], r14b
0x18002bc94  mov     [rbp+280h+var_300], r14
0x18002bc98  mov     [rsp+380h+var_310], r14
0x18002bc9d  lea     rax, [rsp+380h+var_310]
0x18002bca2  mov     [rsp+380h+var_360], rax; unsigned __int64 *
0x18002bca7  lea     r9, [rbp+280h+var_300]; unsigned __int64 *
0x18002bcab  lea     r8, [rsp+380h+var_340]; bool *
0x18002bcb0  lea     rdx, [rsp+380h+var_318]; enum PacketParser::PacketType *
0x18002bcb5  mov     rcx, r12; this
0x18002bcb8  call    ?ParseRobustConnectionMessages@PacketParser@@QEAAKPEAW4PacketType@1@PEA_NPEA_K2@Z; PacketParser::ParseRobustConnectionMessages(PacketParser::PacketType *,bool *,unsigned __int64 *,unsigned __int64 *)
0x18002bcbd  test    eax, eax
0x18002bcbf  jnz     loc_18002BBFC
0x18002bcc5  mov     rax, [rdi+5C0h]
0x18002bccc  mov     rdx, [rax+2A0h]; TokenHandle
0x18002bcd3  test    rdx, rdx
0x18002bcd6  jz      loc_18002BD7F
0x18002bcdc  lea     r8, [rsp+380h+hMem]; struct AutoLocalFree *
0x18002bce1  mov     rcx, [rdi+4F8h]; struct IRequestContext *
0x18002bce8  call    ?ExtractSidFromToken@CSecurity@@SAHPEAVIRequestContext@@PEAXAEAVAutoLocalFree@@@Z; CSecurity::ExtractSidFromToken(IRequestContext *,void *,AutoLocalFree &)
0x18002bced  test    eax, eax
0x18002bcef  jnz     loc_18002BD7F
0x18002bcf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcfc  lea     rdx, WPP_GLOBAL_Control
0x18002bd03  cmp     rcx, rdx
0x18002bd06  jz      short loc_18002BD24
0x18002bd08  test    dword ptr [rcx+1Ch], 400h
0x18002bd0f  jz      short loc_18002BD24
0x18002bd11  lea     edx, [rax+1Dh]
0x18002bd14  lea     r8, WPP_4f5d0f7214083e411e1be0c1ba34cdba_Traceguids
0x18002bd1b  mov     rcx, [rcx+10h]
0x18002bd1f  call    WPP_SF_
0x18002bd24  mov     rcx, [rdi+4F8h]
0x18002bd2b  mov     rax, [rcx]
0x18002bd2e  mov     rax, [rax+90h]
0x18002bd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd3a  test    eax, eax
0x18002bd3c  jz      short loc_18002BD61
0x18002bd3e  mov     [rsp+380h+var_360], r14; struct IRequestContext *
0x18002bd43  mov     r9d, 54Fh; unsigned int
0x18002bd49  lea     r8, a373; "373"
0x18002bd50  mov     edx, 175h; unsigned int
0x18002bd55  lea     rcx, aOnecoreAdminWm_80; "onecore\\admin\\wmi\\wmx\\service\\robu"...
0x18002bd5c  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002bd61  mov     rcx, [rdi+4F8h]
0x18002bd68  mov     rax, [rcx]
0x18002bd6b  mov     rax, [rax+98h]
0x18002bd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd77  mov     r8d, eax
0x18002bd7a  jmp     loc_18002BC02
0x18002bd7f  mov     [rsp+380h+var_310], r14
0x18002bd84  mov     rsi, [rbx]
0x18002bd87  test    rsi, rsi
0x18002bd8a  jnz     short loc_18002BDAF
0x18002bd8c  mov     [rsp+380h+var_360], r14; struct IRequestContext *
0x18002bd91  mov     r9d, 54Fh; unsigned int
0x18002bd97  lea     r8, a666; "666"
0x18002bd9e  mov     edx, 29Ah; unsigned int
0x18002bda3  lea     rcx, aOnecoreAdminWm_144; "onecore\\admin\\wmi\\wmx\\stdlib\\SafeM"...
0x18002bdaa  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002bdaf  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x18002bdb3  mov     rbx, rcx
0x18002bdb6  inc     rbx
0x18002bdb9  cmp     [rsi+rbx*2], r14w
0x18002bdbe  jnz     short loc_18002BDB6
0x18002bdc0  inc     rbx
0x18002bdc3  mov     eax, 2
0x18002bdc8  mul     rbx
0x18002bdcb  mov     r14, rax
0x18002bdce  cmovb   r14, rcx
0x18002bdd2  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18002bdd7  xor     ecx, ecx; this
0x18002bdd9  test    rax, rax
0x18002bddc  jnz     short loc_18002BE0C
0x18002bdde  mov     [rsp+380h+var_360], rcx; struct IRequestContext *
0x18002bde3  mov     r9d, 54Fh; unsigned int
0x18002bde9  lea     r8, a170; "170"
0x18002bdf0  mov     edx, 0AAh; unsigned int
0x18002bdf5  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002bdfc  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002be01  xor     r8d, r8d
0x18002be04  mov     r14d, r8d
0x18002be07  jmp     loc_18002BE98
0x18002be0c  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18002be11  mov     r8, r14; dwBytes
0x18002be14  xor     edx, edx; dwFlags
0x18002be16  mov     rcx, rax; hHeap
0x18002be19  call    cs:__imp_HeapAlloc
0x18002be1f  mov     r14, rax
0x18002be22  xor     r8d, r8d
0x18002be25  test    rax, rax
0x18002be28  jz      short loc_18002BE98
0x18002be2a  test    rbx, rbx
0x18002be2d  jz      short loc_18002BE74
0x18002be2f  cmp     rbx, 7FFFFFFFh
0x18002be36  jbe     short loc_18002BE3E
0x18002be38  mov     [rax], r8w
0x18002be3c  jmp     short loc_18002BE74
0x18002be3e  mov     ecx, 7FFFFFFEh
0x18002be43  test    rcx, rcx
0x18002be46  jz      short loc_18002BE63
0x18002be48  movzx   edx, word ptr [rsi]
0x18002be4b  test    dx, dx
0x18002be4e  jz      short loc_18002BE63
0x18002be50  add     rsi, 2
0x18002be54  mov     [rax], dx
0x18002be57  add     rax, 2
0x18002be5b  sub     rcx, r15
0x18002be5e  sub     rbx, r15
0x18002be61  jnz     short loc_18002BE43
0x18002be63  lea     rdx, [rax-2]
0x18002be67  test    rbx, rbx
0x18002be6a  cmovnz  rdx, rax
0x18002be6e  mov     [rdx], r8w
0x18002be72  jnz     short loc_18002BE98
0x18002be74  mov     [rsp+380h+var_360], r8; struct IRequestContext *
0x18002be79  mov     r9d, 54Fh; unsigned int
0x18002be7f  lea     r8, a676; "676"
0x18002be86  mov     edx, 2A4h; unsigned int
0x18002be8b  lea     rcx, aOnecoreAdminWm_144; "onecore\\admin\\wmi\\wmx\\stdlib\\SafeM"...
0x18002be92  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002be97  nop
0x18002be98  mov     [rsp+380h+var_330], r14
0x18002be9d  test    r14, r14
0x18002bea0  jz      loc_18002BBFC
0x18002bea6  lea     r8, [rsp+380h+var_310]; struct ServerRobustConnection **
0x18002beab  lea     rdx, [rsp+380h+var_330]; struct StringKeyStore *
0x18002beb0  mov     rcx, [rdi+5A0h]; this
0x18002beb7  call    ?FindRobustConnection@RobustConnectionHistoryTable@@QEAAKAEAVStringKeyStore@@PEAPEAVServerRobustConnection@@@Z; RobustConnectionHistoryTable::FindRobustConnection(StringKeyStore &,ServerRobustConnection * *)
  ... truncated ...
```
