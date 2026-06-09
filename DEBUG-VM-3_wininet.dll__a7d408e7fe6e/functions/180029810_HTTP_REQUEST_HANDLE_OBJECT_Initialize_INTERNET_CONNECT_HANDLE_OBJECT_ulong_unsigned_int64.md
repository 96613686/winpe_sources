# HTTP_REQUEST_HANDLE_OBJECT::Initialize(INTERNET_CONNECT_HANDLE_OBJECT *,ulong,unsigned __int64)

- ea: `0x180029810`
- end: `0x180029e08`
- name: `?Initialize@HTTP_REQUEST_HANDLE_OBJECT@@AEAAJPEAVINTERNET_CONNECT_HANDLE_OBJECT@@K_K@Z`
- size: `1528`
- prototype: `__int64 __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, struct INTERNET_CONNECT_HANDLE_OBJECT *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009d60`

## callees

- `0x1800288b0`
- `0x180029810`
- `0x180029e10`
- `0x18002a134`
- `0x18002a344`
- `0x18002a398`
- `0x18002ba10`
- `0x18004edf0`
- `0x1800586fc`
- `0x1800694a4`
- `0x18006a1cc`
- `0x18006a584`
- `0x18007ad20`
- `0x180086ae8`
- `0x1800c00ec`
- `0x1800ce01c`
- `0x1801297b8`
- `0x18014b3b4`
- `0x1801d4e28`
- `0x1801e1790`
- `0x1801e285c`
- `0x1801e2f30`
- `0x1801e3c24`
- `0x1801e490c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180029a52`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180029a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029a2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029a2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002993c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002993c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029b0b`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::Initialize(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        struct INTERNET_CONNECT_HANDLE_OBJECT *a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // edi
  SECURITY_CACHE_LIST_ENTRY *v8; // r15
  int Instance; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  signed int ThreadpoolTimer; // ebx
  __int64 ThreadInfo; // rax
  int v15; // eax
  int v16; // eax
  volatile signed __int32 *v17; // rsi
  HANDLE v18; // rcx
  CBlockFsmSync *v19; // rax
  CBlockFsmSync *v20; // rbx
  struct _TP_TIMER **v21; // rax
  struct _TP_CALLBACK_ENVIRON_V3 *v22; // r8
  struct _TP_TIMER **v23; // rdi
  CCancelFsmSyncList *v24; // rcx
  unsigned int v25; // edi
  __int16 v26; // r14
  __int64 v27; // rsi
  SECURITY_CACHE_LIST_ENTRY *i; // rdi
  struct SECURITY_CACHE_LIST_ENTRY *v29; // rbx
  int Handle; // eax
  int v31; // edi
  signed __int32 v32; // esi
  DWORD CurrentProcessId; // ebx
  DWORD CurrentThreadId; // eax
  int v35; // eax
  int v36; // eax
  const char *HostName; // rax
  int v39; // eax
  struct SECURITY_CACHE_LIST_ENTRY *v40; // [rsp+30h] [rbp-38h] BYREF
  int v41; // [rsp+3Ch] [rbp-2Ch]

  v41 = 0;
  v5 = a3;
  v8 = 0;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_qDP(this, a2, a3, a2, a3, a4);
  Instance = INTERNET_CONNECT_HANDLE_OBJECT::InitializeFromParent(this, a2);
  ThreadpoolTimer = Instance;
  if ( Instance < 0 )
  {
    v41 = 231;
LABEL_72:
    v25 = Instance;
    goto LABEL_63;
  }
  *((_DWORD *)this + 317) = v5;
  *((_QWORD *)this + 23) = a4;
  if ( (v5 & 0x10000000) != 0 )
  {
    *((_DWORD *)this + 116) |= 0x10000000u;
    *((_DWORD *)this + 131) = 1;
  }
  ThreadInfo = InternetGetThreadInfo(v11, v10, v12);
  if ( !ThreadInfo )
  {
    ThreadpoolTimer = -2147012892;
    v41 = 243;
    goto LABEL_81;
  }
  *((_DWORD *)this + 1414) = *(_DWORD *)(ThreadInfo + 72);
  if ( !*((_DWORD *)this + 131) )
  {
    v39 = INTERNET_HANDLE_OBJECT::EnableSyncPending(this);
    ThreadpoolTimer = v39;
    if ( v39 > 0 )
      ThreadpoolTimer = (unsigned __int16)v39 | 0x80070000;
    if ( ThreadpoolTimer < 0 )
    {
      v41 = 254;
LABEL_81:
      v25 = ThreadpoolTimer;
      goto LABEL_63;
    }
  }
  *(_OWORD *)((char *)this + 1044) = *(_OWORD *)((char *)a2 + 164);
  v15 = CHttpHeaders::Initialize((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280));
  ThreadpoolTimer = v15;
  if ( v15 > 0 )
    ThreadpoolTimer = (unsigned __int16)v15 | 0x80070000;
  if ( ThreadpoolTimer < 0 )
  {
    v41 = 265;
    goto LABEL_81;
  }
  v16 = CHttpHeaders::Initialize((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 3104));
  ThreadpoolTimer = v16;
  if ( v16 > 0 )
    ThreadpoolTimer = (unsigned __int16)v16 | 0x80070000;
  if ( ThreadpoolTimer < 0 )
  {
    v41 = 266;
    goto LABEL_81;
  }
  Instance = CCancelFsmSyncList::CreateInstance((struct CCancelFsmSyncList **)this + 70);
  ThreadpoolTimer = Instance;
  if ( Instance < 0 )
  {
    v41 = 269;
    goto LABEL_72;
  }
  v17 = (volatile signed __int32 *)*((_QWORD *)this + 70);
  HIDWORD(v40) = 0;
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_qq(1033, 10, (unsigned int)&WPP_e42fad3f836b3b0f98f370db60552e41_Traceguids, (_DWORD)v17, 0);
  v18 = g_hWxProcessHeap;
  *((_QWORD *)this + 714) = 0;
  v19 = (CBlockFsmSync *)HeapAlloc(v18, 0, 0x58u);
  v20 = v19;
  if ( v19 && (memset_0(v19, 0, 0x58u), v21 = (struct _TP_TIMER **)CBlockFsmSync::CBlockFsmSync(v20), (v23 = v21) != 0) )
  {
    ThreadpoolTimer = WxCreateThreadpoolTimer(
                        FailFastThreadpoolTimerCallback<&private: static void CBlockFsmSync::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)>,
                        v21,
                        v22,
                        v21 + 3);
    if ( ThreadpoolTimer < 0 )
    {
      HIDWORD(v40) = 55;
      *((_DWORD *)v23 + 4) = 1;
      CBlockFsmSync::Release((CBlockFsmSync *)v23);
    }
    else
    {
      _InterlockedAdd((volatile signed __int32 *)v23, 1u);
      if ( v17 )
      {
        _InterlockedAdd(v17, 1u);
        v24 = v23[9];
        if ( v24 )
        {
          CCancelFsmSyncList::Release(v24);
          v23[9] = 0;
        }
        v23[9] = (struct _TP_TIMER *)v17;
      }
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        WPP_SF_q(1033, 11, &WPP_e42fad3f836b3b0f98f370db60552e41_Traceguids, v23);
      *((_QWORD *)this + 714) = v23;
    }
  }
  else
  {
    ThreadpoolTimer = -2147024882;
    HIDWORD(v40) = 50;
  }
  v25 = ThreadpoolTimer;
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_d(1033, 12, &WPP_e42fad3f836b3b0f98f370db60552e41_Traceguids, (unsigned int)ThreadpoolTimer);
  if ( ThreadpoolTimer < 0 )
  {
    v41 = 272;
    goto LABEL_63;
  }
  if ( !GlobalCertCacheNoValidate && (*((_DWORD *)this + 317) & 0x800000) != 0 )
  {
    v26 = *((_WORD *)this + 466);
    if ( *((_DWORD *)this + 216) )
      v27 = *((_QWORD *)this + 107);
    else
      v27 = 0;
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_s(1025, 25, &WPP_c739a4d1cc5f3596af17db4ca44bd9b2_Traceguids, v27);
    EnterCriticalSection(&stru_180268068);
    for ( i = GlobalCertCache; ; i = *(SECURITY_CACHE_LIST_ENTRY **)i )
    {
      v29 = 0;
      if ( i == (SECURITY_CACHE_LIST_ENTRY *)&GlobalCertCache )
        break;
      if ( !(unsigned int)_o__stricmp(*((_QWORD *)i + 104), v27) )
      {
        v29 = i;
        if ( *((_WORD *)i + 424) == v26 )
        {
          SECURITY_CACHE_LIST_ENTRY::AddRef(i);
          break;
        }
      }
    }
    LeaveCriticalSection(&stru_180268068);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_q(1025, 26, &WPP_c739a4d1cc5f3596af17db4ca44bd9b2_Traceguids, v29);
    v40 = v29;
    if ( !v29 )
    {
      HostName = INTERNET_CONNECT_HANDLE_OBJECT::GetHostName(this);
      ThreadpoolTimer = SECURITY_CACHE_LIST_ENTRY::CreateInstance(HostName, *((_WORD *)this + 466), &v40);
      if ( ThreadpoolTimer < 0 )
      {
        v8 = v40;
        v25 = ThreadpoolTimer;
        v41 = 285;
        goto LABEL_61;
      }
      v29 = v40;
    }
    *((_QWORD *)this + 666) = v29;
    v8 = 0;
  }
  HIDWORD(v40) = 0;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_qqD(
      1032,
      10,
      (unsigned int)&WPP_a85fccec657a30c16cbc767298893445_Traceguids,
      *((_QWORD *)this + 16),
      (__int64)this);
  Handle = AllocateHandle(this, (char *)this + 128);
  ThreadpoolTimer = Handle;
  if ( Handle > 0 )
    ThreadpoolTimer = (unsigned __int16)Handle | 0x80070000;
  if ( ThreadpoolTimer < 0 )
  {
    HIDWORD(v40) = 76;
  }
  else
  {
    v31 = *((_DWORD *)this + 32);
    *((_DWORD *)this + 34) = 1902465608;
    v32 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    CurrentProcessId = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)this + 41) = v31;
    *((_DWORD *)this + 42) = v32;
    *((_DWORD *)this + 43) = CurrentProcessId ^ (CurrentThreadId << 16);
    *((_DWORD *)this + 44) = (_DWORD)this;
    v35 = HANDLE_OBJECT::AddToLists(this);
    ThreadpoolTimer = v35;
    if ( v35 > 0 )
      ThreadpoolTimer = (unsigned __int16)v35 | 0x80070000;
    if ( ThreadpoolTimer < 0 )
    {
      HIDWORD(v40) = 86;
    }
    else
    {
      *((_DWORD *)this + 40) = 1;
      v36 = InternetIndicateStatusNewHandle(this);
      ThreadpoolTimer = v36;
      if ( v36 > 0 )
        ThreadpoolTimer = (unsigned __int16)v36 | 0x80070000;
      if ( ThreadpoolTimer < 0 )
        HIDWORD(v40) = 92;
    }
  }
  v25 = ThreadpoolTimer;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_d(1032, 11, &WPP_a85fccec657a30c16cbc767298893445_Traceguids, (unsigned int)ThreadpoolTimer);
  if ( ThreadpoolTimer < 0 )
  {
    v41 = 292;
    goto LABEL_63;
  }
LABEL_61:
  if ( v8 )
    SECURITY_CACHE_LIST_ENTRY::Release(v8);
LABEL_63:
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_d(1032, 11, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, (unsigned int)ThreadpoolTimer);
  return v25;
}

```

## disassembly

```asm
0x180029810  mov     [rsp+arg_10], rbx
0x180029815  mov     [rsp+arg_18], rbp
0x18002981a  push    rsi
0x18002981b  push    rdi
0x18002981c  push    r13
0x18002981e  push    r14
0x180029820  push    r15
0x180029822  sub     rsp, 40h
0x180029826  mov     r14, r9
0x180029829  mov     [rsp+68h+var_2C], 0
0x180029831  mov     edi, r8d
0x180029834  mov     rsi, rdx
0x180029837  mov     rbp, rcx
0x18002983a  xor     r15d, r15d
0x18002983d  lea     r13d, [r15+1]
0x180029841  test    byte ptr cs:xmmword_180266B60+1, r13b
0x180029848  jnz     loc_180029CD6
0x18002984e  mov     rdx, rsi; struct INTERNET_CONNECT_HANDLE_OBJECT *
0x180029851  mov     rcx, rbp; this
0x180029854  call    ?InitializeFromParent@INTERNET_CONNECT_HANDLE_OBJECT@@MEAAJPEAV1@@Z; INTERNET_CONNECT_HANDLE_OBJECT::InitializeFromParent(INTERNET_CONNECT_HANDLE_OBJECT *)
0x180029859  mov     ebx, eax
0x18002985b  test    eax, eax
0x18002985d  js      loc_180029C13
0x180029863  mov     eax, 10000000h
0x180029868  mov     [rbp+4F4h], edi
0x18002986e  mov     [rbp+0B8h], r14
0x180029875  test    eax, edi
0x180029877  jnz     loc_180029CEC
0x18002987d  call    InternetGetThreadInfo
0x180029882  test    rax, rax
0x180029885  jz      loc_180029CFE
0x18002988b  mov     edi, 80070000h
0x180029890  mov     eax, [rax+48h]
0x180029893  mov     [rbp+1618h], eax
0x180029899  cmp     [rbp+20Ch], r15d
0x1800298a0  jz      loc_180029C36
0x1800298a6  movups  xmm0, xmmword ptr [rsi+0A4h]
0x1800298ad  lea     rcx, [rbp+500h]; this
0x1800298b4  movdqu  xmmword ptr [rbp+414h], xmm0
0x1800298bc  call    ?Initialize@CHttpHeaders@@QEAAKXZ; CHttpHeaders::Initialize(void)
0x1800298c1  mov     ebx, eax
0x1800298c3  test    eax, eax
0x1800298c5  jle     short loc_1800298CC
0x1800298c7  movzx   ebx, ax
0x1800298ca  or      ebx, edi
0x1800298cc  test    ebx, ebx
0x1800298ce  js      loc_180029D1C
0x1800298d4  lea     rcx, [rbp+0C20h]; this
0x1800298db  call    ?Initialize@CHttpHeaders@@QEAAKXZ; CHttpHeaders::Initialize(void)
0x1800298e0  mov     ebx, eax
0x1800298e2  test    eax, eax
0x1800298e4  jle     short loc_1800298EB
0x1800298e6  movzx   ebx, ax
0x1800298e9  or      ebx, edi
0x1800298eb  test    ebx, ebx
0x1800298ed  js      loc_180029D0D
0x1800298f3  lea     rsi, [rbp+230h]
0x1800298fa  mov     rcx, rsi; struct CCancelFsmSyncList **
0x1800298fd  call    ?CreateInstance@CCancelFsmSyncList@@SAJPEAPEAV1@@Z; CCancelFsmSyncList::CreateInstance(CCancelFsmSyncList * *)
0x180029902  mov     ebx, eax
0x180029904  test    eax, eax
0x180029906  js      loc_180029D26
0x18002990c  mov     rsi, [rsi]
0x18002990f  mov     dword ptr [rsp+68h+var_38+4], r15d
0x180029914  mov     r14b, 2
0x180029917  test    byte ptr cs:xmmword_180266B60+1, r14b
0x18002991e  jnz     loc_180029C6B
0x180029924  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18002992b  mov     edi, 58h ; 'X'
0x180029930  mov     r8d, edi; dwBytes
0x180029933  mov     [rbp+1650h], r15
0x18002993a  xor     edx, edx; dwFlags
0x18002993c  call    cs:__imp_HeapAlloc
0x180029942  mov     rbx, rax
0x180029945  test    rax, rax
0x180029948  jz      loc_180029C01
0x18002994e  mov     r8d, edi; Size
0x180029951  xor     edx, edx; Val
0x180029953  mov     rcx, rax; void *
0x180029956  call    memset_0
0x18002995b  mov     rcx, rbx; this
0x18002995e  call    ??0CBlockFsmSync@@AEAA@XZ; CBlockFsmSync::CBlockFsmSync(void)
0x180029963  mov     rdi, rax
0x180029966  test    rax, rax
0x180029969  jz      loc_180029C01
0x18002996f  lea     r9, [rax+18h]; struct _TP_TIMER **
0x180029973  mov     rdx, rax; void *
0x180029976  lea     rcx, ??$FailFastThreadpoolTimerCallback@$1?TimerCallback@CBlockFsmSync@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x18002997d  call    ?WxCreateThreadpoolTimer@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; WxCreateThreadpoolTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_TIMER * *)
0x180029982  mov     ebx, eax
0x180029984  test    eax, eax
0x180029986  js      loc_180029BBC
0x18002998c  lock add [rdi], r13d
0x180029990  test    rsi, rsi
0x180029993  jz      short loc_1800299AF
0x180029995  lock add [rsi], r13d
0x180029999  mov     rcx, [rdi+48h]; this
0x18002999d  test    rcx, rcx
0x1800299a0  jz      short loc_1800299AB
0x1800299a2  call    ?Release@CCancelFsmSyncList@@QEAAKXZ; CCancelFsmSyncList::Release(void)
0x1800299a7  mov     [rdi+48h], r15
0x1800299ab  mov     [rdi+48h], rsi
0x1800299af  test    byte ptr cs:xmmword_180266B60+1, r14b
0x1800299b6  jnz     loc_180029D33
0x1800299bc  mov     [rbp+1650h], rdi
0x1800299c3  mov     edi, ebx
0x1800299c5  test    byte ptr cs:xmmword_180266B60+1, r14b
0x1800299cc  jnz     loc_180029D51
0x1800299d2  test    edi, edi
0x1800299d4  js      loc_180029D6F
0x1800299da  cmp     cs:GlobalCertCacheNoValidate, r15d
0x1800299e1  jnz     loc_180029AA8
0x1800299e7  test    dword ptr [rbp+4F4h], 800000h
0x1800299f1  jz      loc_180029AA8
0x1800299f7  movzx   r14d, word ptr [rbp+3A4h]
0x1800299ff  cmp     [rbp+360h], r15d
0x180029a06  jz      loc_180029BB5
0x180029a0c  mov     rsi, [rbp+358h]
0x180029a13  test    byte ptr cs:xmmword_180266B60, 2
0x180029a1a  mov     r15d, 401h
0x180029a20  jnz     loc_180029D7C
0x180029a26  lea     rcx, stru_180268068; lpCriticalSection
0x180029a2d  call    cs:__imp_EnterCriticalSection
0x180029a33  mov     rdi, cs:GlobalCertCache
0x180029a3a  xor     ebx, ebx
0x180029a3c  lea     rax, GlobalCertCache
0x180029a43  cmp     rdi, rax
0x180029a46  jz      short loc_180029A76
0x180029a48  mov     rcx, [rdi+340h]
0x180029a4f  mov     rdx, rsi
0x180029a52  call    cs:__imp__o__stricmp
0x180029a58  test    eax, eax
0x180029a5a  jz      short loc_180029A61
0x180029a5c  mov     rdi, [rdi]
0x180029a5f  jmp     short loc_180029A3A
0x180029a61  mov     rbx, rdi
0x180029a64  cmp     [rdi+350h], r14w
0x180029a6c  jnz     short loc_180029A5C
0x180029a6e  mov     rcx, rdi; this
0x180029a71  call    ?AddRef@SECURITY_CACHE_LIST_ENTRY@@QEAAJXZ; SECURITY_CACHE_LIST_ENTRY::AddRef(void)
0x180029a76  lea     rcx, stru_180268068; lpCriticalSection
0x180029a7d  call    cs:__imp_LeaveCriticalSection
0x180029a83  test    byte ptr cs:xmmword_180266B60, 2
0x180029a8a  jnz     loc_180029C8E
0x180029a90  mov     [rsp+68h+var_38], rbx
0x180029a95  test    rbx, rbx
0x180029a98  jz      loc_180029BD5
0x180029a9e  mov     [rbp+14D0h], rbx
0x180029aa5  xor     r15d, r15d
0x180029aa8  mov     dword ptr [rsp+68h+var_38+4], 0
0x180029ab0  test    byte ptr cs:xmmword_180266B60+1, r13b
0x180029ab7  jnz     loc_180029CAA
0x180029abd  lea     rdi, [rbp+80h]
0x180029ac4  mov     rcx, rbp
0x180029ac7  mov     rdx, rdi
0x180029aca  call    AllocateHandle
0x180029acf  mov     ebx, eax
0x180029ad1  mov     r14d, 80070000h
0x180029ad7  test    eax, eax
0x180029ad9  jle     short loc_180029AE1
0x180029adb  movzx   ebx, ax
0x180029ade  or      ebx, r14d
0x180029ae1  test    ebx, ebx
0x180029ae3  js      loc_180029C5E
0x180029ae9  mov     edi, [rdi]
0x180029aeb  mov     esi, r13d
0x180029aee  mov     dword ptr [rbp+88h], 71655248h
0x180029af8  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180029b00  add     esi, r13d
0x180029b03  call    cs:__imp_GetCurrentProcessId
0x180029b09  mov     ebx, eax
0x180029b0b  call    cs:__imp_GetCurrentThreadId
0x180029b11  mov     rcx, rbp; this
0x180029b14  mov     [rbp+0A4h], edi
0x180029b1a  shl     eax, 10h
0x180029b1d  xor     eax, ebx
0x180029b1f  mov     [rbp+0A8h], esi
0x180029b25  mov     [rbp+0ACh], eax
0x180029b2b  mov     [rbp+0B0h], ebp
0x180029b31  call    ?AddToLists@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::AddToLists(void)
0x180029b36  mov     ebx, eax
0x180029b38  test    eax, eax
0x180029b3a  jle     short loc_180029B42
0x180029b3c  movzx   ebx, ax
0x180029b3f  or      ebx, r14d
0x180029b42  test    ebx, ebx
0x180029b44  js      loc_180029D98
0x180029b4a  mov     rcx, rbp; this
0x180029b4d  mov     [rbp+0A0h], r13d
0x180029b54  call    InternetIndicateStatusNewHandle
0x180029b59  mov     ebx, eax
0x180029b5b  test    eax, eax
0x180029b5d  jle     short loc_180029B65
0x180029b5f  movzx   ebx, ax
0x180029b62  or      ebx, r14d
0x180029b65  test    ebx, ebx
0x180029b67  js      loc_180029DA5
0x180029b6d  mov     edi, ebx
0x180029b6f  test    byte ptr cs:xmmword_180266B60+1, r13b
0x180029b76  jnz     loc_180029DB2
0x180029b7c  test    ebx, ebx
0x180029b7e  js      loc_180029DD0
0x180029b84  test    r15, r15
0x180029b87  jnz     loc_180029DDD
0x180029b8d  test    byte ptr cs:xmmword_180266B60+1, r13b
0x180029b94  jnz     loc_180029DEA
0x180029b9a  lea     r11, [rsp+68h+var_28]
0x180029b9f  mov     eax, edi
0x180029ba1  mov     rbx, [r11+40h]
0x180029ba5  mov     rbp, [r11+48h]
0x180029ba9  mov     rsp, r11
0x180029bac  pop     r15
0x180029bae  pop     r14
0x180029bb0  pop     r13
0x180029bb2  pop     rdi
0x180029bb3  pop     rsi
0x180029bb4  retn
0x180029bb5  xor     esi, esi
0x180029bb7  jmp     loc_180029A13
0x180029bbc  mov     rcx, rdi; this
0x180029bbf  mov     dword ptr [rsp+68h+var_38+4], 37h ; '7'
0x180029bc7  mov     [rdi+10h], r13d
0x180029bcb  call    ?Release@CBlockFsmSync@@QEAAKXZ; CBlockFsmSync::Release(void)
0x180029bd0  jmp     loc_1800299C3
0x180029bd5  mov     rcx, rbp; this
0x180029bd8  call    ?GetHostName@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAPEBDXZ; INTERNET_CONNECT_HANDLE_OBJECT::GetHostName(void)
0x180029bdd  movzx   edx, word ptr [rbp+3A4h]; unsigned __int16
0x180029be4  lea     r8, [rsp+68h+var_38]; struct SECURITY_CACHE_LIST_ENTRY **
0x180029be9  mov     rcx, rax; Src
0x180029bec  call    ?CreateInstance@SECURITY_CACHE_LIST_ENTRY@@SAJPEBDGPEAPEAV1@@Z; SECURITY_CACHE_LIST_ENTRY::CreateInstance(char const *,ushort,SECURITY_CACHE_LIST_ENTRY * *)
0x180029bf1  mov     ebx, eax
0x180029bf3  test    eax, eax
0x180029bf5  js      short loc_180029C22
0x180029bf7  mov     rbx, [rsp+68h+var_38]
0x180029bfc  jmp     loc_180029A9E
0x180029c01  mov     ebx, 8007000Eh
0x180029c06  mov     dword ptr [rsp+68h+var_38+4], 32h ; '2'
0x180029c0e  jmp     loc_1800299C3
0x180029c13  mov     [rsp+68h+var_2C], 0E7h
0x180029c1b  mov     edi, eax
0x180029c1d  jmp     loc_180029B8D
0x180029c22  mov     r15, [rsp+68h+var_38]
0x180029c27  mov     edi, ebx
0x180029c29  mov     [rsp+68h+var_2C], 11Dh
0x180029c31  jmp     loc_180029B84
0x180029c36  mov     rcx, rbp; this
0x180029c39  call    ?EnableSyncPending@INTERNET_HANDLE_OBJECT@@IEAAKXZ; INTERNET_HANDLE_OBJECT::EnableSyncPending(void)
0x180029c3e  mov     ebx, eax
0x180029c40  test    eax, eax
0x180029c42  jle     short loc_180029C49
0x180029c44  movzx   ebx, ax
0x180029c47  or      ebx, edi
0x180029c49  test    ebx, ebx
0x180029c4b  jns     loc_1800298A6
0x180029c51  mov     [rsp+68h+var_2C], 0FEh
0x180029c59  jmp     loc_180029D15
0x180029c5e  mov     dword ptr [rsp+68h+var_38+4], 4Ch ; 'L'
0x180029c66  jmp     loc_180029B6D
0x180029c6b  mov     edx, 0Ah
0x180029c70  mov     [rsp+68h+var_48], r15
0x180029c75  mov     ecx, 409h
0x180029c7a  lea     r8, WPP_e42fad3f836b3b0f98f370db60552e41_Traceguids
0x180029c81  mov     r9, rsi
0x180029c84  call    WPP_SF_qq
0x180029c89  jmp     loc_180029924
0x180029c8e  mov     edx, 1Ah
0x180029c93  lea     r8, WPP_c739a4d1cc5f3596af17db4ca44bd9b2_Traceguids
0x180029c9a  mov     ecx, r15d
0x180029c9d  mov     r9, rbx
0x180029ca0  call    WPP_SF_q
0x180029ca5  jmp     loc_180029A90
0x180029caa  mov     r9, [rbp+80h]
0x180029cb1  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x180029cb8  mov     edx, 0Ah
0x180029cbd  mov     dword ptr [rsp+68h+var_40], r13d
0x180029cc2  mov     ecx, 408h
0x180029cc7  mov     [rsp+68h+var_48], rbp
0x180029ccc  call    WPP_SF_qqD
0x180029cd1  jmp     loc_180029ABD
0x180029cd6  mov     [rsp+68h+var_40], r14
0x180029cdb  mov     r9, rsi
0x180029cde  mov     dword ptr [rsp+68h+var_48], edi
0x180029ce2  call    WPP_SF_qDP
0x180029ce7  jmp     loc_18002984E
0x180029cec  or      [rbp+1D0h], eax
0x180029cf2  mov     [rbp+20Ch], r13d
0x180029cf9  jmp     loc_18002987D
0x180029cfe  mov     ebx, 80072EE4h
0x180029d03  mov     [rsp+68h+var_2C], 0F3h
0x180029d0b  jmp     short loc_180029D15
0x180029d0d  mov     [rsp+68h+var_2C], 10Ah
0x180029d15  mov     edi, ebx
0x180029d17  jmp     loc_180029B8D
0x180029d1c  mov     [rsp+68h+var_2C], 109h
0x180029d24  jmp     short loc_180029D15
0x180029d26  mov     [rsp+68h+var_2C], 10Dh
0x180029d2e  jmp     loc_180029C1B
0x180029d33  mov     edx, 0Bh
0x180029d38  lea     r8, WPP_e42fad3f836b3b0f98f370db60552e41_Traceguids
0x180029d3f  mov     ecx, 409h
  ... truncated ...
```
