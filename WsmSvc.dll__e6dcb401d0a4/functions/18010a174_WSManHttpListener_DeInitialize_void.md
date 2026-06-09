# WSManHttpListener::DeInitialize(void)

- ea: `0x18010a174`
- end: `0x18010a506`
- name: `?DeInitialize@WSManHttpListener@@QEAAKXZ`
- size: `914`
- prototype: `unsigned int __fastcall(WSManHttpListener *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x1801019b0`
- `0x18016ccdc`

## callees

- `0x180005d10`
- `0x180010490`
- `0x180028070`
- `0x18002dd20`
- `0x18002dd80`
- `0x18003f208`
- `0x180068b24`
- `0x180077514`
- `0x18010a174`
- `0x180112380`
- `0x180112460`
- `0x18011a6d4`
- `0x18016c444`
- `0x18016f284`
- `0x18016f3ac`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a218`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010a4a7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010a4b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010a4a7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010a4b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a241`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a2fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a499`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a241`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a2fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a499`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18010a4e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18010a4e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18010a4df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18010a4df`
- `SspiCli!FreeCredentialsHandle` at `0x18010a42e`
- `SspiCli!FreeCredentialsHandle` at `0x18010a45d`
- `SspiCli!FreeCredentialsHandle` at `0x18010a42e`
- `SspiCli!FreeCredentialsHandle` at `0x18010a45d`
- `HTTPAPI!HttpTerminate` at `0x18010a3d1`
- `HTTPAPI!HttpTerminate` at `0x18010a3d1`

## string_xrefs

- `0x18010a386`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WSManHttpListener::DeInitialize(WSManHttpListener *this)
{
  CWSManCriticalSection *v2; // rsi
  __int64 v3; // rbp
  ULONGLONG TickCount64; // r14
  __int64 v5; // rbx
  __int64 v6; // rax
  void (__fastcall ***v7)(_QWORD, __int64); // rsi
  PVOID *v8; // rcx
  struct _TP_IO *v9; // rcx
  CWSManCriticalSection *v11; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+38h] [rbp-40h]

  v2 = (WSManHttpListener *)((char *)this + 176);
  if ( (unsigned int)CWSManCriticalSection::IsValid((WSManHttpListener *)((char *)this + 176)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    WSManHttpListener::DisableRequests(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    if ( *((_QWORD *)this + 3) )
    {
      Spinlock::ExclusiveAcquire((WSManHttpListener *)((char *)this + 32));
      CloseHandle(*((HANDLE *)this + 3));
      *((_QWORD *)this + 3) = 0;
      Spinlock::Release((WSManHttpListener *)((char *)this + 32));
    }
    if ( (unsigned int)CWSManCriticalSection::IsValid(v2) )
    {
      v3 = 0;
      TickCount64 = GetTickCount64();
      v11 = v2;
      v12 = 0;
      CWSManCriticalSection::Acquire(v2);
      WSManHttpListener::ResetConnectionsImp(this);
      v5 = (__int64)(*((_QWORD *)this + 19) - *((_QWORD *)this + 18)) >> 3;
      InCritSec::~InCritSec((InCritSec *)&v11);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this, v5);
      while ( v5 )
      {
        v11 = v2;
        v12 = 0;
        CWSManCriticalSection::Acquire(v2);
        v5 = (__int64)(*((_QWORD *)this + 19) - *((_QWORD *)this + 18)) >> 3;
        InCritSec::~InCritSec((InCritSec *)&v11);
        if ( !v5 )
          break;
        if ( v3 == v5 )
        {
          if ( GetTickCount64() - TickCount64 > 0x2BF20 )
          {
            do
            {
              --v5;
              v6 = *((_QWORD *)this + 18);
              v7 = *(void (__fastcall ****)(_QWORD, __int64))(v6 + 8 * v5);
              if ( v7 )
              {
                WSManHttpListener::RemoveRequestFromQueue(this, *(struct WSManHttpListenerRequest **)(v6 + 8 * v5));
                (**v7)(v7, 1);
              }
            }
            while ( v5 );
            break;
          }
        }
        else
        {
          v3 = v5;
          TickCount64 = GetTickCount64();
        }
        Sleep(0x1F4u);
      }
    }
    if ( *((_QWORD *)this + 60)
      && *((_QWORD *)this + 64)
      && (unsigned int)SafeMap<UserKey,BlockedRecord *,SafeMap_Iterator<UserKey,BlockedRecord *>>::Size((char *)this + 472) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 769, L"769", 0x54Fu, 0);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)this + 32) == 1 )
    {
      HttpTerminate(1u, 0);
      *((_DWORD *)this + 32) = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x400) != 0 )
    {
      WPP_SF_q(v8[2], 52, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)this + 31) != -1 && *((_QWORD *)this + 32) != -1 )
    {
      FreeCredentialsHandle((PCredHandle)((char *)this + 248));
      *((_QWORD *)this + 32) = -1;
      *((_QWORD *)this + 31) = -1;
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)this + 34) != -1 && *((_QWORD *)this + 35) != -1 )
    {
      FreeCredentialsHandle((PCredHandle)this + 17);
      *((_QWORD *)this + 35) = -1;
      *((_QWORD *)this + 34) = -1;
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x400) != 0 )
      WPP_SF_(v8[2], 53, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    while ( *((int *)this + 2) > 1 )
      Sleep(0x32u);
    SlimTimer::FireTimer((WSManHttpListener *)((char *)this + 640), 1);
    v9 = (struct _TP_IO *)*((_QWORD *)this + 15);
    if ( v9 )
    {
      WaitForThreadpoolIoCallbacks(v9, 1);
      CloseThreadpoolIo(*((PTP_IO *)this + 15));
      *((_QWORD *)this + 15) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18010a174  push    rbx
0x18010a176  push    rbp
0x18010a177  push    rsi
0x18010a178  push    rdi
0x18010a179  push    r13
0x18010a17b  push    r14
0x18010a17d  sub     rsp, 48h
0x18010a181  mov     rdi, rcx
0x18010a184  lea     rsi, [rcx+0B0h]
0x18010a18b  mov     rcx, rsi; this
0x18010a18e  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x18010a193  test    eax, eax
0x18010a195  jz      loc_18010A4F7
0x18010a19b  lea     rbp, WPP_GLOBAL_Control
0x18010a1a2  mov     r13d, 400h
0x18010a1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a1af  cmp     rcx, rbp
0x18010a1b2  jz      short loc_18010A1D2
0x18010a1b4  test    [rcx+1Ch], r13d
0x18010a1b8  jz      short loc_18010A1D2
0x18010a1ba  mov     edx, 30h ; '0'
0x18010a1bf  mov     r9, rdi
0x18010a1c2  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a1c9  mov     rcx, [rcx+10h]
0x18010a1cd  call    WPP_SF_q
0x18010a1d2  mov     rcx, rdi; this
0x18010a1d5  call    ?DisableRequests@WSManHttpListener@@QEAAXXZ; WSManHttpListener::DisableRequests(void)
0x18010a1da  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a1e1  cmp     rcx, rbp
0x18010a1e4  jz      short loc_18010A204
0x18010a1e6  test    [rcx+1Ch], r13d
0x18010a1ea  jz      short loc_18010A204
0x18010a1ec  mov     edx, 31h ; '1'
0x18010a1f1  mov     r9, rdi
0x18010a1f4  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a1fb  mov     rcx, [rcx+10h]
0x18010a1ff  call    WPP_SF_q
0x18010a204  cmp     qword ptr [rdi+18h], 0
0x18010a209  jz      short loc_18010A22F
0x18010a20b  lea     rcx, [rdi+20h]; this
0x18010a20f  call    ?ExclusiveAcquire@Spinlock@@QEAAXXZ; Spinlock::ExclusiveAcquire(void)
0x18010a214  mov     rcx, [rdi+18h]; hObject
0x18010a218  call    cs:__imp_CloseHandle
0x18010a21e  mov     qword ptr [rdi+18h], 0
0x18010a226  lea     rcx, [rdi+20h]; this
0x18010a22a  call    ?Release@Spinlock@@QEAAJXZ; Spinlock::Release(void)
0x18010a22f  mov     rcx, rsi; this
0x18010a232  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x18010a237  test    eax, eax
0x18010a239  jz      loc_18010A34D
0x18010a23f  xor     ebp, ebp
0x18010a241  call    cs:__imp_GetTickCount64
0x18010a247  mov     r14, rax
0x18010a24a  mov     [rsp+78h+var_48], rsi
0x18010a24f  mov     [rsp+78h+var_40], ebp
0x18010a253  mov     rcx, rsi; this
0x18010a256  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18010a25b  nop
0x18010a25c  mov     rcx, rdi; this
0x18010a25f  call    ?ResetConnectionsImp@WSManHttpListener@@AEAAXXZ; WSManHttpListener::ResetConnectionsImp(void)
0x18010a264  mov     rbx, [rdi+98h]
0x18010a26b  sub     rbx, [rdi+90h]
0x18010a272  sar     rbx, 3
0x18010a276  lea     rcx, [rsp+78h+var_48]; this
0x18010a27b  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18010a280  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a287  lea     rax, WPP_GLOBAL_Control
0x18010a28e  cmp     rcx, rax
0x18010a291  jz      short loc_18010A2B3
0x18010a293  test    [rcx+1Ch], r13d
0x18010a297  jz      short loc_18010A2B3
0x18010a299  lea     edx, [rbp+32h]
0x18010a29c  mov     dword ptr [rsp+78h+var_58], ebx
0x18010a2a0  mov     r9, rdi
0x18010a2a3  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a2aa  mov     rcx, [rcx+10h]
0x18010a2ae  call    WPP_SF_qD
0x18010a2b3  test    rbx, rbx
0x18010a2b6  jz      loc_18010A346
0x18010a2bc  mov     [rsp+78h+var_48], rsi
0x18010a2c1  mov     [rsp+78h+var_40], 0
0x18010a2c9  mov     rcx, rsi; this
0x18010a2cc  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18010a2d1  mov     rbx, [rdi+98h]
0x18010a2d8  sub     rbx, [rdi+90h]
0x18010a2df  sar     rbx, 3
0x18010a2e3  lea     rcx, [rsp+78h+var_48]; this
0x18010a2e8  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18010a2ed  test    rbx, rbx
0x18010a2f0  jz      short loc_18010A346
0x18010a2f2  cmp     rbp, rbx
0x18010a2f5  jnz     loc_18010A496
0x18010a2fb  call    cs:__imp_GetTickCount64
0x18010a301  sub     rax, r14
0x18010a304  cmp     rax, 2BF20h
0x18010a30a  jbe     loc_18010A4A2
0x18010a310  dec     rbx
0x18010a313  mov     rax, [rdi+90h]
0x18010a31a  mov     rsi, [rax+rbx*8]
0x18010a31e  test    rsi, rsi
0x18010a321  jz      short loc_18010A341
0x18010a323  mov     rdx, rsi; struct WSManHttpListenerRequest *
0x18010a326  mov     rcx, rdi; this
0x18010a329  call    ?RemoveRequestFromQueue@WSManHttpListener@@AEAAXPEAVWSManHttpListenerRequest@@@Z; WSManHttpListener::RemoveRequestFromQueue(WSManHttpListenerRequest *)
0x18010a32e  mov     rax, [rsi]
0x18010a331  mov     edx, 1
0x18010a336  mov     rcx, rsi
0x18010a339  mov     rax, [rax]
0x18010a33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a341  test    rbx, rbx
0x18010a344  jnz     short loc_18010A310
0x18010a346  lea     rbp, WPP_GLOBAL_Control
0x18010a34d  lea     rcx, [rdi+1D8h]
0x18010a354  cmp     qword ptr [rcx+8], 0
0x18010a359  jz      short loc_18010A392
0x18010a35b  cmp     qword ptr [rcx+28h], 0
0x18010a360  jz      short loc_18010A392
0x18010a362  call    ?Size@?$SafeMap@UUserKey@@PEAVBlockedRecord@@V?$SafeMap_Iterator@UUserKey@@PEAVBlockedRecord@@@@@@QEBAHXZ; SafeMap<UserKey,BlockedRecord *,SafeMap_Iterator<UserKey,BlockedRecord *>>::Size(void)
0x18010a367  test    eax, eax
0x18010a369  jz      short loc_18010A392
0x18010a36b  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x18010a374  mov     r9d, 54Fh; unsigned int
0x18010a37a  lea     r8, a769; "769"
0x18010a381  mov     edx, 301h; unsigned int
0x18010a386  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18010a38d  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18010a392  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a399  cmp     rcx, rbp
0x18010a39c  jz      short loc_18010A3C3
0x18010a39e  test    [rcx+1Ch], r13d
0x18010a3a2  jz      short loc_18010A3C3
0x18010a3a4  mov     edx, 33h ; '3'
0x18010a3a9  mov     r9, rdi
0x18010a3ac  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a3b3  mov     rcx, [rcx+10h]
0x18010a3b7  call    WPP_SF_q
0x18010a3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a3c3  cmp     dword ptr [rdi+80h], 1
0x18010a3ca  jnz     short loc_18010A3E8
0x18010a3cc  xor     edx, edx; pReserved
0x18010a3ce  lea     ecx, [rdx+1]; Flags
0x18010a3d1  call    cs:__imp_HttpTerminate
0x18010a3d7  mov     dword ptr [rdi+80h], 0
0x18010a3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a3e8  cmp     rcx, rbp
0x18010a3eb  jz      short loc_18010A412
0x18010a3ed  test    [rcx+1Ch], r13d
0x18010a3f1  jz      short loc_18010A412
0x18010a3f3  mov     edx, 34h ; '4'
0x18010a3f8  mov     r9, rdi
0x18010a3fb  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a402  mov     rcx, [rcx+10h]
0x18010a406  call    WPP_SF_q
0x18010a40b  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a412  lea     rbx, [rdi+0F8h]
0x18010a419  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010a41d  cmp     [rbx], rsi
0x18010a420  jz      short loc_18010A445
0x18010a422  cmp     [rdi+100h], rsi
0x18010a429  jz      short loc_18010A445
0x18010a42b  mov     rcx, rbx; phCredential
0x18010a42e  call    cs:__imp_FreeCredentialsHandle
0x18010a434  mov     [rdi+100h], rsi
0x18010a43b  mov     [rbx], rsi
0x18010a43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a445  lea     rbx, [rdi+110h]
0x18010a44c  cmp     [rbx], rsi
0x18010a44f  jz      short loc_18010A474
0x18010a451  cmp     [rdi+118h], rsi
0x18010a458  jz      short loc_18010A474
0x18010a45a  mov     rcx, rbx; phCredential
0x18010a45d  call    cs:__imp_FreeCredentialsHandle
0x18010a463  mov     [rdi+118h], rsi
0x18010a46a  mov     [rbx], rsi
0x18010a46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a474  cmp     rcx, rbp
0x18010a477  jz      short loc_18010A4BD
0x18010a479  test    [rcx+1Ch], r13d
0x18010a47d  jz      short loc_18010A4BD
0x18010a47f  mov     edx, 35h ; '5'
0x18010a484  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18010a48b  mov     rcx, [rcx+10h]
0x18010a48f  call    WPP_SF_
0x18010a494  jmp     short loc_18010A4BD
0x18010a496  mov     rbp, rbx
0x18010a499  call    cs:__imp_GetTickCount64
0x18010a49f  mov     r14, rax
0x18010a4a2  mov     ecx, 1F4h; dwMilliseconds
0x18010a4a7  call    cs:__imp_Sleep
0x18010a4ad  jmp     loc_18010A2B3
0x18010a4b2  mov     ecx, 32h ; '2'; dwMilliseconds
0x18010a4b7  call    cs:__imp_Sleep
0x18010a4bd  cmp     dword ptr [rdi+8], 1
0x18010a4c1  jg      short loc_18010A4B2
0x18010a4c3  lea     rcx, [rdi+280h]; this
0x18010a4ca  mov     dl, 1; bool
0x18010a4cc  call    ?FireTimer@SlimTimer@@UEAAX_N@Z; SlimTimer::FireTimer(bool)
0x18010a4d1  mov     rcx, [rdi+78h]; pio
0x18010a4d5  test    rcx, rcx
0x18010a4d8  jz      short loc_18010A4F7
0x18010a4da  mov     edx, 1; fCancelPendingCallbacks
0x18010a4df  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18010a4e5  mov     rcx, [rdi+78h]; pio
0x18010a4e9  call    cs:__imp_CloseThreadpoolIo
0x18010a4ef  mov     qword ptr [rdi+78h], 0
0x18010a4f7  xor     eax, eax
0x18010a4f9  add     rsp, 48h
0x18010a4fd  pop     r14
0x18010a4ff  pop     r13
0x18010a501  pop     rdi
0x18010a502  pop     rsi
0x18010a503  pop     rbp
0x18010a504  pop     rbx
0x18010a505  retn
```
