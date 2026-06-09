# CHostedCacheProtocol::Shutdown(void)

- ea: `0x1800fdbe4`
- end: `0x1800fdfcc`
- name: `?Shutdown@CHostedCacheProtocol@@QEAAJXZ`
- size: `1000`
- prototype: `__int64 __fastcall(CHostedCacheProtocol *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800f0800`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18000ff2c`
- `0x18001f2e0`
- `0x1800f64ec`
- `0x1800f6ac8`
- `0x1800f6df0`
- `0x1800f6e40`
- `0x1800fb5ac`
- `0x1800fdbe4`
- `0x1800ff2f0`
- `0x1800ff60c`
- `0x1800ff658`
- `0x18013fc9c`
- `0x18013fcc0`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fdd63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fddc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fdd63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fddc4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fdd56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fddb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fdd56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fddb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fdd44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fdd96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fdd44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fdd96`
- `WS2_32!__imp_WSACleanup` at `0x1800fdf6a`
- `WS2_32!__imp_WSACleanup` at `0x1800fdf6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHostedCacheProtocol::Shutdown(CHostedCacheProtocol *this)
{
  __int64 v2; // rax
  CHostedCacheProtocol *v3; // rcx
  CHostedCacheProtocol *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  struct _TP_TIMER *v6; // rcx
  char *v7; // r15
  __int64 v8; // rbx
  bool v9; // r12
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int128 v17; // [rsp+20h] [rbp-118h] BYREF
  _OWORD v18[2]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v20; // [rsp+70h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+78h] [rbp-C0h]
  _BYTE v22[152]; // [rsp+88h] [rbp-B0h] BYREF
  char v23; // [rsp+140h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_54be81ea90983cb591d6a2d511652152_Traceguids);
  }
  _InterlockedExchange((volatile __int32 *)this + 224, 1);
  InCritSec::InCritSec((InCritSec *)v18, this, 1);
  std::_Tree<std::_Tmap_traits<TnoHoHoDk,unsigned long,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,unsigned long>>,0>>::clear((char *)this + 832);
  InCritSec::~InCritSec((InCritSec *)v18);
  InCritSec::InCritSec((InCritSec *)v18, (CHostedCacheProtocol *)((char *)this + 928), 1);
  while ( *((_QWORD *)this + 126) )
  {
    v20 = 0;
    v21 = 0u;
    memset_0(v22, 0, 0x90u);
    v2 = std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::front((CHostedCacheProtocol *)((char *)this + 976));
    tag_HOSTED_CACHE_QUEUED_OFFER::operator=(&v20, v2);
    std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::pop_front((char *)this + 976);
    v17 = v21;
    CHostedCacheProtocol::CancelProcessRequest(this, v20, &v17);
  }
  InCritSec::~InCritSec((InCritSec *)v18);
  CHostedCacheProtocol::RemoveHostedCacheProtocolFromTrans(v3, *((void **)this + 155));
  CHostedCacheProtocol::RemoveHostedCacheProtocolFromTrans(v4, *((void **)this + 164));
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 102);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 102), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 102));
  }
  if ( *((_QWORD *)this + 139) )
  {
    InCritSec::InCritSec((InCritSec *)v18, (CHostedCacheProtocol *)((char *)this + 1056), 1);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 139), 0, 0, 0);
    InCritSec::~InCritSec((InCritSec *)v18);
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 139);
  if ( v6 )
  {
    WaitForThreadpoolTimerCallbacks(v6, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 139));
  }
  CThreadpoolEnvironment::CleanupGroupMembers((CHostedCacheProtocol *)((char *)this + 704), 1);
  if ( *((_BYTE *)this + 144) )
  {
    if ( *((_QWORD *)this + 155) )
      (*((void (**)(void))this + 148))();
    if ( *((_QWORD *)this + 164) )
      (*((void (**)(void))this + 157))();
  }
  try
  {
    PEERDIST_INCREMENTAL_HANDLE::PEERDIST_INCREMENTAL_HANDLE((PEERDIST_INCREMENTAL_HANDLE *)&v17, 0);
    v7 = (char *)this + 848;
    InCritSec::InCritSec((InCritSec *)v19, (CHostedCacheProtocol *)((char *)this + 848), 1);
    while ( *((_QWORD *)this + 128) )
    {
      v8 = **((_QWORD **)this + 127);
      PEERDIST_INCREMENTAL_HANDLE::operator=(&v17, v8 + 32);
      v9 = *(_DWORD *)(v8 + 48) != 3;
      operator delete(*(void **)(v8 + 88));
      v10 = *(void (__fastcall ****)(_QWORD, __int64))(v8 + 96);
      if ( v10 )
        (**v10)(v10, 1);
      std::_Tree<std::_Tmap_traits<void *,DiscoveryProviderProxy *,std::less<void *>,std::allocator<std::pair<void * const,DiscoveryProviderProxy *>>,0>>::erase(
        (char *)this + 1016,
        &v23,
        v8);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))((char *)this + 848);
      v18[0] = v17;
      LOBYTE(v11) = v9;
      v12 = CHostedCacheProtocol::CloseRequestWrapper(this, v11, v18);
      if ( v12
        && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_54be81ea90983cb591d6a2d511652152_Traceguids, v12);
      }
      CHostedCacheProtocol::DecrementPendingRequestCount(this);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 848);
    }
    InCritSec::~InCritSec((InCritSec *)v19);
  }
  catch ( std::bad_alloc )
  {
    v16 = WSACleanup();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_54be81ea90983cb591d6a2d511652152_Traceguids, v16);
    }
    return 2147942414LL;
  }
  catch ( ... )
  {
    v15 = WSACleanup();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_54be81ea90983cb591d6a2d511652152_Traceguids, v15);
    }
    return 2147943174LL;
  }
  if ( !*((_BYTE *)this + 144) )
  {
    if ( *((_QWORD *)this + 155) )
      (*((void (**)(void))this + 148))();
    if ( *((_QWORD *)this + 164) )
      (*((void (**)(void))this + 157))();
  }
  v13 = WSACleanup();
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_54be81ea90983cb591d6a2d511652152_Traceguids, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1800fdbe4  mov     [rsp+arg_8], rbx
0x1800fdbe9  mov     [rsp+arg_10], rsi
0x1800fdbee  push    rdi
0x1800fdbef  push    r12
0x1800fdbf1  push    r15
0x1800fdbf3  sub     rsp, 120h
0x1800fdbfa  mov     rdi, rcx
0x1800fdbfd  lea     rbx, WPP_GLOBAL_Control
0x1800fdc04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fdc0b  cmp     rcx, rbx
0x1800fdc0e  jz      short loc_1800FDC34
0x1800fdc10  test    dword ptr [rcx+6Ch], 1000h
0x1800fdc17  jz      short loc_1800FDC34
0x1800fdc19  cmp     byte ptr [rcx+69h], 4
0x1800fdc1d  jb      short loc_1800FDC34
0x1800fdc1f  mov     edx, 11h
0x1800fdc24  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fdc2b  mov     rcx, [rcx+60h]
0x1800fdc2f  call    WPP_SF_
0x1800fdc34  mov     eax, 1
0x1800fdc39  xchg    eax, [rdi+380h]
0x1800fdc3f  mov     r8b, 1; bool
0x1800fdc42  mov     rdx, rdi; struct CritSec *
0x1800fdc45  lea     rcx, [rsp+138h+var_108]; this
0x1800fdc4a  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800fdc4f  lea     rcx, [rdi+340h]
0x1800fdc56  call    ?clear@?$_Tree@V?$_Tmap_traits@VTnoHoHoDk@@KUTnoHoHoDkLess@@V?$allocator@U?$pair@$$CBVTnoHoHoDk@@K@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<TnoHoHoDk,ulong,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,ulong>>,0>>::clear(void)
0x1800fdc5b  lea     rcx, [rsp+138h+var_108]; this
0x1800fdc60  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800fdc65  lea     rdx, [rdi+3A0h]; struct CritSec *
0x1800fdc6c  mov     r8b, 1; bool
0x1800fdc6f  lea     rcx, [rsp+138h+var_108]; this
0x1800fdc74  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800fdc79  cmp     qword ptr [rdi+3F0h], 0
0x1800fdc81  jbe     loc_1800FDD0E
0x1800fdc87  lea     rbx, [rdi+3D0h]
0x1800fdc8e  xor     eax, eax
0x1800fdc90  mov     [rsp+138h+var_C8], rax
0x1800fdc95  mov     qword ptr [rsp+138h+var_C0], rax
0x1800fdc9a  mov     qword ptr [rsp+138h+var_C0+8], rax
0x1800fdca2  xor     edx, edx; Val
0x1800fdca4  mov     r8d, 90h; Size
0x1800fdcaa  lea     rcx, [rsp+138h+var_B0]; void *
0x1800fdcb2  call    memset_0
0x1800fdcb7  mov     rcx, rbx; struct std::_Container_base12 *
0x1800fdcba  call    ?front@?$deque@Utag_HOSTED_CACHE_QUEUED_OFFER@@V?$allocator@Utag_HOSTED_CACHE_QUEUED_OFFER@@@std@@@std@@QEAAAEAUtag_HOSTED_CACHE_QUEUED_OFFER@@XZ; std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::front(void)
0x1800fdcbf  mov     rdx, rax
0x1800fdcc2  lea     rcx, [rsp+138h+var_C8]
0x1800fdcc7  call    ??4tag_HOSTED_CACHE_QUEUED_OFFER@@QEAAAEAU0@AEBU0@@Z; tag_HOSTED_CACHE_QUEUED_OFFER::operator=(tag_HOSTED_CACHE_QUEUED_OFFER const &)
0x1800fdccc  mov     rcx, rbx
0x1800fdccf  call    ?pop_front@?$deque@Utag_HOSTED_CACHE_QUEUED_OFFER@@V?$allocator@Utag_HOSTED_CACHE_QUEUED_OFFER@@@std@@@std@@QEAAXXZ; std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::pop_front(void)
0x1800fdcd4  mov     rcx, qword ptr [rsp+138h+var_C0]
0x1800fdcd9  mov     qword ptr [rsp+138h+var_118], rcx
0x1800fdcde  mov     rax, qword ptr [rsp+138h+var_C0+8]
0x1800fdce6  mov     qword ptr [rsp+138h+var_118+8], rax
0x1800fdceb  lea     r8, [rsp+138h+var_118]
0x1800fdcf0  mov     rdx, [rsp+138h+var_C8]
0x1800fdcf5  mov     rcx, rdi
0x1800fdcf8  call    ?CancelProcessRequest@CHostedCacheProtocol@@QEAAXPEAXVPEERDIST_INCREMENTAL_HANDLE@@@Z; CHostedCacheProtocol::CancelProcessRequest(void *,PEERDIST_INCREMENTAL_HANDLE)
0x1800fdcfd  cmp     qword ptr [rdi+3F0h], 0
0x1800fdd05  ja      short loc_1800FDC8E
0x1800fdd07  lea     rbx, WPP_GLOBAL_Control
0x1800fdd0e  lea     rcx, [rsp+138h+var_108]; this
0x1800fdd13  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800fdd18  mov     rdx, [rdi+4D8h]; void *
0x1800fdd1f  call    ?RemoveHostedCacheProtocolFromTrans@CHostedCacheProtocol@@AEAAXPEAX@Z; CHostedCacheProtocol::RemoveHostedCacheProtocolFromTrans(void *)
0x1800fdd24  mov     rdx, [rdi+520h]; void *
0x1800fdd2b  call    ?RemoveHostedCacheProtocolFromTrans@CHostedCacheProtocol@@AEAAXPEAX@Z; CHostedCacheProtocol::RemoveHostedCacheProtocolFromTrans(void *)
0x1800fdd30  mov     rcx, [rdi+330h]; pti
0x1800fdd37  test    rcx, rcx
0x1800fdd3a  jz      short loc_1800FDD69
0x1800fdd3c  xor     r9d, r9d; msWindowLength
0x1800fdd3f  xor     r8d, r8d; msPeriod
0x1800fdd42  xor     edx, edx; pftDueTime
0x1800fdd44  call    cs:__imp_SetThreadpoolTimer
0x1800fdd4a  mov     edx, 1; fCancelPendingCallbacks
0x1800fdd4f  mov     rcx, [rdi+330h]; pti
0x1800fdd56  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800fdd5c  mov     rcx, [rdi+330h]; pti
0x1800fdd63  call    cs:__imp_CloseThreadpoolTimer
0x1800fdd69  cmp     qword ptr [rdi+458h], 0
0x1800fdd71  jz      short loc_1800FDDA6
0x1800fdd73  lea     rdx, [rdi+420h]; struct CritSec *
0x1800fdd7a  mov     r8b, 1; bool
0x1800fdd7d  lea     rcx, [rsp+138h+var_108]; this
0x1800fdd82  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800fdd87  xor     r9d, r9d; msWindowLength
0x1800fdd8a  xor     r8d, r8d; msPeriod
0x1800fdd8d  xor     edx, edx; pftDueTime
0x1800fdd8f  mov     rcx, [rdi+458h]; pti
0x1800fdd96  call    cs:__imp_SetThreadpoolTimer
0x1800fdd9c  lea     rcx, [rsp+138h+var_108]; this
0x1800fdda1  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800fdda6  mov     rcx, [rdi+458h]; pti
0x1800fddad  test    rcx, rcx
0x1800fddb0  jz      short loc_1800FDDCA
0x1800fddb2  mov     edx, 1; fCancelPendingCallbacks
0x1800fddb7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800fddbd  mov     rcx, [rdi+458h]; pti
0x1800fddc4  call    cs:__imp_CloseThreadpoolTimer
0x1800fddca  lea     rcx, [rdi+2C0h]; this
0x1800fddd1  mov     dl, 1; bool
0x1800fddd3  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x1800fddd8  cmp     byte ptr [rdi+90h], 0
0x1800fdddf  jz      short loc_1800FDE12
0x1800fdde1  mov     rcx, [rdi+4D8h]
0x1800fdde8  test    rcx, rcx
0x1800fddeb  jz      short loc_1800FDDF9
0x1800fdded  mov     rax, [rdi+4A0h]
0x1800fddf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fddf9  mov     rcx, [rdi+520h]
0x1800fde00  test    rcx, rcx
0x1800fde03  jz      short loc_1800FDE12
0x1800fde05  mov     rax, [rdi+4E8h]
0x1800fde0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fde11  nop
0x1800fde12  xor     edx, edx; struct PEERDIST_INCREMENTAL_HANDLE *
0x1800fde14  lea     rcx, [rsp+138h+var_118]; this
0x1800fde19  call    ??0PEERDIST_INCREMENTAL_HANDLE@@QEAA@PEBV0@@Z; PEERDIST_INCREMENTAL_HANDLE::PEERDIST_INCREMENTAL_HANDLE(PEERDIST_INCREMENTAL_HANDLE const *)
0x1800fde1e  lea     r15, [rdi+350h]
0x1800fde25  mov     r8b, 1; bool
0x1800fde28  mov     rdx, r15; struct CritSec *
0x1800fde2b  lea     rcx, [rsp+138h+var_E8]; this
0x1800fde30  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800fde35  nop
0x1800fde36  lea     rsi, [rdi+3F8h]
0x1800fde3d  cmp     qword ptr [rsi+8], 0
0x1800fde42  jbe     loc_1800FDF26
0x1800fde48  mov     rbx, [rsi]
0x1800fde4b  mov     rbx, [rbx]
0x1800fde4e  lea     rdx, [rbx+20h]
0x1800fde52  lea     rcx, [rsp+138h+var_118]
0x1800fde57  call    ??4PEERDIST_INCREMENTAL_HANDLE@@QEAAAEAV0@AEBV0@@Z; PEERDIST_INCREMENTAL_HANDLE::operator=(PEERDIST_INCREMENTAL_HANDLE const &)
0x1800fde5c  cmp     dword ptr [rbx+30h], 3
0x1800fde60  setnz   r12b
0x1800fde64  mov     rcx, [rbx+58h]; Block
0x1800fde68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800fde6d  mov     rcx, [rbx+60h]
0x1800fde71  test    rcx, rcx
0x1800fde74  jz      short loc_1800FDE86
0x1800fde76  mov     rax, [rcx]
0x1800fde79  mov     edx, 1
0x1800fde7e  mov     rax, [rax]
0x1800fde81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fde86  mov     r8, rbx
0x1800fde89  lea     rdx, [rsp+138h+arg_0]
0x1800fde91  mov     rcx, rsi
0x1800fde94  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAXPEAVDiscoveryProviderProxy@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXPEAVDiscoveryProviderProxy@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXPEAVDiscoveryProviderProxy@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXPEAVDiscoveryProviderProxy@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<void *,DiscoveryProviderProxy *,std::less<void *>,std::allocator<std::pair<void * const,DiscoveryProviderProxy *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,DiscoveryProviderProxy *>>>>)
0x1800fde99  mov     rax, [r15]
0x1800fde9c  mov     rcx, r15
0x1800fde9f  mov     rax, [rax+10h]
0x1800fdea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdea8  movaps  xmm0, [rsp+138h+var_118]
0x1800fdead  movdqa  [rsp+138h+var_108], xmm0
0x1800fdeb3  lea     r8, [rsp+138h+var_108]
0x1800fdeb8  mov     dl, r12b
0x1800fdebb  mov     rcx, rdi
0x1800fdebe  call    ?CloseRequestWrapper@CHostedCacheProtocol@@AEAAK_NVPEERDIST_INCREMENTAL_HANDLE@@@Z; CHostedCacheProtocol::CloseRequestWrapper(bool,PEERDIST_INCREMENTAL_HANDLE)
0x1800fdec3  test    eax, eax
0x1800fdec5  jz      short loc_1800FDF03
0x1800fdec7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fdece  lea     rbx, WPP_GLOBAL_Control
0x1800fded5  cmp     rcx, rbx
0x1800fded8  jz      short loc_1800FDF0A
0x1800fdeda  test    dword ptr [rcx+6Ch], 1000h
0x1800fdee1  jz      short loc_1800FDF0A
0x1800fdee3  cmp     byte ptr [rcx+69h], 1
0x1800fdee7  jb      short loc_1800FDF0A
0x1800fdee9  mov     edx, 12h
0x1800fdeee  mov     r9d, eax
0x1800fdef1  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fdef8  mov     rcx, [rcx+60h]
0x1800fdefc  call    WPP_SF_d
0x1800fdf01  jmp     short loc_1800FDF0A
0x1800fdf03  lea     rbx, WPP_GLOBAL_Control
0x1800fdf0a  mov     rcx, rdi; this
0x1800fdf0d  call    ?DecrementPendingRequestCount@CHostedCacheProtocol@@AEAAXXZ; CHostedCacheProtocol::DecrementPendingRequestCount(void)
0x1800fdf12  mov     rax, [r15]
0x1800fdf15  mov     rcx, r15
0x1800fdf18  mov     rax, [rax+8]
0x1800fdf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdf21  jmp     loc_1800FDE36
0x1800fdf26  lea     rcx, [rsp+138h+var_E8]; this
0x1800fdf2b  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800fdf30  nop
0x1800fdf31  cmp     byte ptr [rdi+90h], 0
0x1800fdf38  jnz     short loc_1800FDF6A
0x1800fdf3a  mov     rcx, [rdi+4D8h]
0x1800fdf41  test    rcx, rcx
0x1800fdf44  jz      short loc_1800FDF52
0x1800fdf46  mov     rax, [rdi+4A0h]
0x1800fdf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdf52  mov     rcx, [rdi+520h]
0x1800fdf59  test    rcx, rcx
0x1800fdf5c  jz      short loc_1800FDF6A
0x1800fdf5e  mov     rax, [rdi+4E8h]
0x1800fdf65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdf6a  call    cs:__imp_WSACleanup
0x1800fdf70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fdf77  cmp     rcx, rbx
0x1800fdf7a  jz      short loc_1800FDFA3
0x1800fdf7c  test    dword ptr [rcx+6Ch], 1000h
0x1800fdf83  jz      short loc_1800FDFA3
0x1800fdf85  cmp     byte ptr [rcx+69h], 4
0x1800fdf89  jb      short loc_1800FDFA3
0x1800fdf8b  mov     edx, 15h
0x1800fdf90  mov     r9d, eax
0x1800fdf93  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fdf9a  mov     rcx, [rcx+60h]
0x1800fdf9e  call    WPP_SF_d
0x1800fdfa3  xor     eax, eax
0x1800fdfa5  jmp     short loc_1800FDFB3
0x1800fdfa7  mov     eax, 80070306h
0x1800fdfac  jmp     short loc_1800FDFB3
0x1800fdfae  mov     eax, 8007000Eh
0x1800fdfb3  lea     r11, [rsp+138h+var_18]
0x1800fdfbb  mov     rbx, [r11+28h]
0x1800fdfbf  mov     rsi, [r11+30h]
0x1800fdfc3  mov     rsp, r11
0x1800fdfc6  pop     r15
0x1800fdfc8  pop     r12
0x1800fdfca  pop     rdi
0x1800fdfcb  retn
```
