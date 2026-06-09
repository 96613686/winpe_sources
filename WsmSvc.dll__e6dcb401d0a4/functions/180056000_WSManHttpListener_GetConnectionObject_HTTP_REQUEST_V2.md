# WSManHttpListener::GetConnectionObject(_HTTP_REQUEST_V2 *)

- ea: `0x180056000`
- end: `0x1800565b2`
- name: `?GetConnectionObject@WSManHttpListener@@QEAAPEAVWSManHttpListenerConnection@@PEAU_HTTP_REQUEST_V2@@@Z`
- size: `1458`
- prototype: `struct WSManHttpListenerConnection *__fastcall(WSManHttpListener *__hidden this, struct _HTTP_REQUEST_V2 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x180054c30`

## callees

- `0x180005d10`
- `0x18002dd20`
- `0x180056000`
- `0x1800567e0`
- `0x18005a8c8`
- `0x1800621e0`
- `0x180075e00`
- `0x180077514`
- `0x1800e0ae0`
- `0x1800eb810`
- `0x1800f7d00`
- `0x1800ff9e4`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x18011349c`
- `0x18016c4a8`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056143`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056175`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056445`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005657b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800565a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056143`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056175`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056445`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005657b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800565a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005603e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005603e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800560d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800560d8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180056482`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180056482`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180056255`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180056255`
- `HTTPAPI!HttpWaitForDisconnect` at `0x180056467`
- `HTTPAPI!HttpWaitForDisconnect` at `0x180056467`

## string_xrefs

- `0x180056164`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x1800563a3`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180056517`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
struct WSManHttpListenerConnection *__fastcall WSManHttpListener::GetConnectionObject(
        WSManHttpListener *this,
        struct _HTTP_REQUEST_V2 *a2)
{
  char *v3; // r14
  DWORD v4; // ecx
  _QWORD *v5; // r13
  __int64 v6; // r15
  __int64 i; // rdx
  WSManHttpListenerConnection *v8; // rbx
  _OWORD *p_sa_family; // rdi
  _OWORD *v10; // rsi
  __int128 v11; // xmm0
  WSManHttpListenerConnection *v13; // rax
  bool IsValid; // al
  __int64 v15; // r8
  HTTP_CONNECTION_ID v16; // r15
  void *v17; // rcx
  ULONG v18; // r15d
  DWORD v19; // ecx
  struct _HTTP_REQUEST_V2 *v20; // [rsp+88h] [rbp+10h] BYREF
  WSManHttpListenerConnection *v21; // [rsp+90h] [rbp+18h]
  HTTP_CONNECTION_ID ConnectionId; // [rsp+98h] [rbp+20h]

  v20 = a2;
  ConnectionId = a2->ConnectionId;
  v3 = (char *)this + 176;
  v4 = *((_DWORD *)this + 44);
  if ( v4 )
  {
    SetLastError(v4);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  }
  v5 = (_QWORD *)((char *)this + 224);
  v6 = (__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
      this,
      (__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3);
  for ( i = 0; (_DWORD)i != (_DWORD)v6; i = (unsigned int)(i + 1) )
  {
    v8 = *(WSManHttpListenerConnection **)(*v5 + 8LL * (int)i);
    if ( *((_QWORD *)v8 + 8) == ConnectionId )
    {
      (**(void (__fastcall ***)(_QWORD, __int64, HTTP_CONNECTION_ID))v8)(
        *(_QWORD *)(*v5 + 8LL * (int)i),
        i,
        ConnectionId);
      if ( _InterlockedIncrement((volatile signed __int32 *)v8 + 37) < 1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 1555, L"1555", 0x54Fu, 0);
      if ( *(_DWORD *)v3 )
        SetLastError(*(_DWORD *)v3);
      else
        LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          v8,
          *((_QWORD *)v8 + 8));
      p_sa_family = &v20->Address.pRemoteAddress->sa_family;
      v10 = (_OWORD *)((char *)v8 + 376);
      memset_0((char *)v8 + 376, 0, 0x80u);
      v11 = *p_sa_family;
      if ( *(_WORD *)p_sa_family == 2 )
      {
        *v10 = v11;
      }
      else
      {
        *v10 = v11;
        *(_OWORD *)((char *)v8 + 388) = *(_OWORD *)((char *)p_sa_family + 12);
      }
      return v8;
    }
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)this + 42) > 256 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, 256);
    if ( !WSManHttpListener::GarbageCollectUnauthenticatedConnections(this) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      SetLastError(8u);
      WSManHttpListener::DecrementUnauthenticatedConnections(this);
      CWSManCriticalSection::Release((CWSManCriticalSection *)v3);
      return 0;
    }
  }
  CWSManCriticalSection::Release((CWSManCriticalSection *)v3);
  LODWORD(v21) = 0;
  v13 = (WSManHttpListenerConnection *)WSManMemory::Alloc(504, 0, 0);
  if ( v13 )
    v8 = WSManHttpListenerConnection::WSManHttpListenerConnection(v13, this);
  else
    v8 = 0;
  v21 = v8;
  if ( !v8 )
    goto LABEL_60;
  IsValid = WSManHttpListenerConnection::IsValid(v8);
  v15 = *(_QWORD *)v8;
  if ( !IsValid )
  {
    (*(void (__fastcall **)(WSManHttpListenerConnection *, __int64))(v15 + 16))(v8, 1);
LABEL_60:
    WSManHttpListener::DecrementUnauthenticatedConnections(this);
    v19 = 14;
LABEL_61:
    SetLastError(v19);
    return 0;
  }
  (*(void (__fastcall **)(WSManHttpListenerConnection *))v15)(v8);
  v16 = ConnectionId;
  *((_QWORD *)v8 + 8) = ConnectionId;
  WSManHttpListenerConnection::SetClientAddress(v8, v20->Address.pRemoteAddress);
  (**(void (__fastcall ***)(WSManHttpListenerConnection *))v8)(v8);
  StartThreadpoolIo(*((PTP_IO *)this + 15));
  Spinlock::SharedAcquire((WSManHttpListener *)((char *)this + 32));
  v17 = (void *)*((_QWORD *)this + 3);
  if ( v17 )
    v18 = HttpWaitForDisconnect(v17, v16, (LPOVERLAPPED)((char *)v8 + 24));
  else
    v18 = 1115;
  Spinlock::Release((WSManHttpListener *)((char *)this + 32));
  if ( v18 != 997 && v18 )
  {
    CancelThreadpoolIo(*((PTP_IO *)this + 15));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v18);
    (*(void (__fastcall **)(WSManHttpListenerConnection *, __int64))(*(_QWORD *)v8 + 16LL))(v8, 1);
    v19 = v18;
    goto LABEL_61;
  }
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)v3);
  if ( !*((_BYTE *)v8 + 288) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this, v8);
    std::vector<WSManHttpListenerConnection *,transport_allocator<WSManHttpListenerConnection *>>::_Insert_n(
      (char *)this + 224,
      &v20,
      *((_QWORD *)this + 29));
    (**(void (__fastcall ***)(WSManHttpListenerConnection *))v8)(v8);
    if ( _InterlockedIncrement((volatile signed __int32 *)v8 + 37) != 1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 1690, L"1690", 0x54Fu, 0);
    (*(void (__fastcall **)(WSManHttpListenerConnection *, _QWORD, _QWORD))(*(_QWORD *)v8 + 8LL))(v8, 0, 0);
    CWSManCriticalSection::Release((CWSManCriticalSection *)v3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        v8,
        *((_QWORD *)v8 + 8));
    return v8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this, v8);
  CWSManCriticalSection::Release((CWSManCriticalSection *)v3);
  (*(void (__fastcall **)(WSManHttpListenerConnection *, _QWORD, _QWORD))(*(_QWORD *)v8 + 8LL))(v8, 0, 0);
  SetLastError(0x8CAu);
  return 0;
}

```

## disassembly

```asm
0x180056000  mov     [rsp+arg_8], rdx
0x180056005  mov     [rsp+arg_0], rcx
0x18005600a  push    rbx
0x18005600b  push    rsi
0x18005600c  push    rdi
0x18005600d  push    r12
0x18005600f  push    r13
0x180056011  push    r14
0x180056013  push    r15
0x180056015  sub     rsp, 40h
0x180056019  mov     rdi, rcx
0x18005601c  mov     rax, [rdx+8]
0x180056020  mov     [rsp+78h+ConnectionId], rax
0x180056028  lea     r14, [rcx+0B0h]
0x18005602f  mov     ecx, [r14]; dwErrCode
0x180056032  test    ecx, ecx
0x180056034  jnz     loc_180056143
0x18005603a  lea     rcx, [r14+8]; lpCriticalSection
0x18005603e  call    cs:__imp_EnterCriticalSection
0x180056044  lea     r13, [rdi+0E0h]
0x18005604b  mov     r15, [r13+8]
0x18005604f  sub     r15, [r13+0]
0x180056053  sar     r15, 3
0x180056057  lea     rbx, WPP_GLOBAL_Control
0x18005605e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056065  mov     r12d, 400h
0x18005606b  lea     rsi, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056072  cmp     rcx, rbx
0x180056075  jnz     loc_180056360
0x18005607b  xor     edx, edx
0x18005607d  mov     r8, [rsp+78h+ConnectionId]
0x180056085  cmp     edx, r15d
0x180056088  jz      loc_180056186
0x18005608e  movsxd  rcx, edx
0x180056091  mov     rax, [r13+0]
0x180056095  mov     rbx, [rax+rcx*8]
0x180056099  cmp     [rbx+40h], r8
0x18005609d  jz      short loc_1800560A3
0x18005609f  inc     edx
0x1800560a1  jmp     short loc_180056085
0x1800560a3  mov     rax, [rbx]
0x1800560a6  mov     rcx, rbx
0x1800560a9  mov     rax, [rax]
0x1800560ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560b1  mov     eax, 1
0x1800560b6  lock xadd [rbx+94h], eax
0x1800560be  inc     eax
0x1800560c0  cmp     eax, 1
0x1800560c3  jl      loc_180056388
0x1800560c9  mov     ecx, [r14]; dwErrCode
0x1800560cc  test    ecx, ecx
0x1800560ce  jnz     loc_180056175
0x1800560d4  lea     rcx, [r14+8]; lpCriticalSection
0x1800560d8  call    cs:__imp_LeaveCriticalSection
0x1800560de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560e5  lea     rax, WPP_GLOBAL_Control
0x1800560ec  cmp     rcx, rax
0x1800560ef  jnz     loc_1800563B4
0x1800560f5  mov     rdx, [rsp+78h+arg_8]
0x1800560fd  mov     rdi, [rdx+68h]
0x180056101  lea     rsi, [rbx+178h]
0x180056108  xor     edx, edx; Val
0x18005610a  mov     r8d, 80h; Size
0x180056110  mov     rcx, rsi; void *
0x180056113  call    memset_0
0x180056118  mov     eax, 2
0x18005611d  movups  xmm0, xmmword ptr [rdi]
0x180056120  cmp     ax, [rdi]
0x180056123  jz      short loc_180056180
0x180056125  movups  xmmword ptr [rsi], xmm0
0x180056128  movups  xmm1, xmmword ptr [rdi+0Ch]
0x18005612c  movups  xmmword ptr [rsi+0Ch], xmm1
0x180056130  mov     rax, rbx
0x180056133  add     rsp, 40h
0x180056137  pop     r15
0x180056139  pop     r14
0x18005613b  pop     r13
0x18005613d  pop     r12
0x18005613f  pop     rdi
0x180056140  pop     rsi
0x180056141  pop     rbx
0x180056142  retn
0x180056143  call    cs:__imp_SetLastError
0x180056149  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x180056152  mov     r9d, 54Fh; unsigned int
0x180056158  lea     r8, a59; "59"
0x18005615f  mov     edx, 3Bh ; ';'; unsigned int
0x180056164  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18005616b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180056170  jmp     loc_180056044
0x180056175  call    cs:__imp_SetLastError
0x18005617b  jmp     loc_1800560DE
0x180056180  movdqu  xmmword ptr [rsi], xmm0
0x180056184  jmp     short loc_180056130
0x180056186  mov     eax, 1
0x18005618b  lock xadd [rdi+0A8h], eax
0x180056193  inc     eax
0x180056195  mov     r9d, 100h
0x18005619b  cmp     eax, r9d
0x18005619e  jg      loc_1800563E0
0x1800561a4  mov     rcx, r14; this
0x1800561a7  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x1800561ac  mov     dword ptr [rsp+78h+arg_10], 0
0x1800561b7  lea     rax, [rsp+78h+arg_10]
0x1800561bf  mov     [rsp+78h+var_48], rax
0x1800561c4  xor     r8d, r8d
0x1800561c7  xor     edx, edx
0x1800561c9  mov     ecx, 1F8h
0x1800561ce  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800561d3  mov     [rsp+78h+var_40], rax
0x1800561d8  test    rax, rax
0x1800561db  jz      loc_180056359
0x1800561e1  mov     rdx, rdi; struct WSManHttpListener *
0x1800561e4  mov     rcx, rax; this
0x1800561e7  call    ??0WSManHttpListenerConnection@@QEAA@PEAVWSManHttpListener@@@Z; WSManHttpListenerConnection::WSManHttpListenerConnection(WSManHttpListener *)
0x1800561ec  mov     rbx, rax
0x1800561ef  mov     [rsp+78h+arg_10], rbx
0x1800561f7  mov     [rsp+78h+var_48], rbx
0x1800561fc  test    rbx, rbx
0x1800561ff  jz      loc_180056598
0x180056205  mov     rcx, rbx; this
0x180056208  call    ?IsValid@WSManHttpListenerConnection@@QEAA_NXZ; WSManHttpListenerConnection::IsValid(void)
0x18005620d  mov     r8, [rbx]
0x180056210  mov     rcx, rbx
0x180056213  test    al, al
0x180056215  jz      loc_18005658A
0x18005621b  mov     rax, [r8]
0x18005621e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056223  mov     r15, [rsp+78h+ConnectionId]
0x18005622b  mov     [rbx+40h], r15
0x18005622f  mov     rdx, [rsp+78h+arg_8]
0x180056237  mov     rdx, [rdx+68h]; struct sockaddr *
0x18005623b  mov     rcx, rbx; this
0x18005623e  call    ?SetClientAddress@WSManHttpListenerConnection@@QEAAXPEAUsockaddr@@@Z; WSManHttpListenerConnection::SetClientAddress(sockaddr *)
0x180056243  mov     rax, [rbx]
0x180056246  mov     rcx, rbx
0x180056249  mov     rax, [rax]
0x18005624c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056251  mov     rcx, [rdi+78h]; pio
0x180056255  call    cs:__imp_StartThreadpoolIo
0x18005625b  lea     rcx, [rdi+20h]; this
0x18005625f  call    ?SharedAcquire@Spinlock@@QEAAXXZ; Spinlock::SharedAcquire(void)
0x180056264  mov     rcx, [rdi+18h]; RequestQueueHandle
0x180056268  test    rcx, rcx
0x18005626b  jnz     loc_180056460
0x180056271  mov     r15d, 45Bh
0x180056277  lea     rcx, [rdi+20h]; this
0x18005627b  call    ?Release@Spinlock@@QEAAJXZ; Spinlock::Release(void)
0x180056280  cmp     r15d, 3E5h
0x180056287  jnz     loc_180056475
0x18005628d  mov     rcx, r14; this
0x180056290  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x180056295  nop
0x180056296  cmp     byte ptr [rbx+120h], 0
0x18005629d  jnz     loc_180056528
0x1800562a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562aa  lea     r15, WPP_GLOBAL_Control
0x1800562b1  cmp     rcx, r15
0x1800562b4  jnz     loc_1800564D4
0x1800562ba  lea     rax, [rsp+78h+var_48]
0x1800562bf  mov     [rsp+78h+var_58], rax
0x1800562c4  mov     r8, [rdi+0E8h]
0x1800562cb  lea     rdx, [rsp+78h+arg_8]
0x1800562d3  mov     rcx, r13
0x1800562d6  call    ?_Insert_n@?$vector@PEAVWSManHttpListenerConnection@@V?$transport_allocator@PEAVWSManHttpListenerConnection@@@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVWSManHttpListenerConnection@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAVWSManHttpListenerConnection@@@std@@@std@@@2@_KAEBQEAVWSManHttpListenerConnection@@@Z; std::vector<WSManHttpListenerConnection *,transport_allocator<WSManHttpListenerConnection *>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WSManHttpListenerConnection *>>>,unsigned __int64,WSManHttpListenerConnection * const &)
0x1800562db  mov     rax, [rbx]
0x1800562de  mov     rcx, rbx
0x1800562e1  mov     rax, [rax]
0x1800562e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562e9  mov     eax, 1
0x1800562ee  lock xadd [rbx+94h], eax
0x1800562f6  inc     eax
0x1800562f8  cmp     eax, 1
0x1800562fb  jnz     loc_1800564FC
0x180056301  mov     rax, [rbx]
0x180056304  xor     r8d, r8d
0x180056307  xor     edx, edx
0x180056309  mov     rcx, rbx
0x18005630c  mov     rax, [rax+8]
0x180056310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056315  mov     rcx, r14; this
0x180056318  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x18005631d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056324  cmp     rcx, r15
0x180056327  jz      loc_180056130
0x18005632d  test    [rcx+1Ch], r12d
0x180056331  jz      loc_180056130
0x180056337  mov     edx, 67h ; 'g'
0x18005633c  mov     rax, [rbx+40h]
0x180056340  mov     [rsp+78h+var_58], rax
0x180056345  mov     r9, rbx
0x180056348  mov     r8, rsi
0x18005634b  mov     rcx, [rcx+10h]
0x18005634f  call    WPP_SF_qq
0x180056354  jmp     loc_180056130
0x180056359  xor     ebx, ebx
0x18005635b  jmp     loc_1800561EF
0x180056360  test    [rcx+1Ch], r12d
0x180056364  jz      loc_18005607B
0x18005636a  mov     edx, 5Eh ; '^'
0x18005636f  mov     dword ptr [rsp+78h+var_58], r15d
0x180056374  mov     r9, rdi
0x180056377  mov     r8, rsi
0x18005637a  mov     rcx, [rcx+10h]
0x18005637e  call    WPP_SF_qD
0x180056383  jmp     loc_18005607B
0x180056388  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x180056391  mov     r9d, 54Fh; unsigned int
0x180056397  lea     r8, a1555; "1555"
0x18005639e  mov     edx, 613h; unsigned int
0x1800563a3  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x1800563aa  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800563af  jmp     loc_1800560C9
0x1800563b4  test    [rcx+1Ch], r12d
0x1800563b8  jz      loc_1800560F5
0x1800563be  mov     edx, 5Fh ; '_'
0x1800563c3  mov     rax, [rbx+40h]
0x1800563c7  mov     [rsp+78h+var_58], rax
0x1800563cc  mov     r9, rbx
0x1800563cf  mov     r8, rsi
0x1800563d2  mov     rcx, [rcx+10h]
0x1800563d6  call    WPP_SF_qq
0x1800563db  jmp     loc_1800560F5
0x1800563e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800563e7  lea     rbx, WPP_GLOBAL_Control
0x1800563ee  cmp     rcx, rbx
0x1800563f1  jz      short loc_18005640A
0x1800563f3  test    [rcx+1Ch], r12d
0x1800563f7  jz      short loc_18005640A
0x1800563f9  mov     edx, 60h ; '`'
0x1800563fe  mov     r8, rsi
0x180056401  mov     rcx, [rcx+10h]
0x180056405  call    WPP_SF_d
0x18005640a  mov     rcx, rdi; this
0x18005640d  call    ?GarbageCollectUnauthenticatedConnections@WSManHttpListener@@QEAA_NXZ; WSManHttpListener::GarbageCollectUnauthenticatedConnections(void)
0x180056412  test    al, al
0x180056414  jnz     loc_1800561A4
0x18005641a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056421  cmp     rcx, rbx
0x180056424  jz      short loc_180056440
0x180056426  test    dword ptr [rcx+1Ch], 200h
0x18005642d  jz      short loc_180056440
0x18005642f  mov     edx, 61h ; 'a'
0x180056434  mov     r8, rsi
0x180056437  mov     rcx, [rcx+10h]
0x18005643b  call    WPP_SF_
0x180056440  mov     ecx, 8; dwErrCode
0x180056445  call    cs:__imp_SetLastError
0x18005644b  mov     rcx, rdi; this
0x18005644e  call    ?DecrementUnauthenticatedConnections@WSManHttpListener@@QEAAJXZ; WSManHttpListener::DecrementUnauthenticatedConnections(void)
0x180056453  mov     rcx, r14; this
0x180056456  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x18005645b  jmp     loc_1800565AB
0x180056460  lea     r8, [rbx+18h]; Overlapped
0x180056464  mov     rdx, r15; ConnectionId
0x180056467  call    cs:__imp_HttpWaitForDisconnect
0x18005646d  mov     r15d, eax
0x180056470  jmp     loc_180056277
0x180056475  test    r15d, r15d
0x180056478  jz      loc_18005628D
0x18005647e  mov     rcx, [rdi+78h]; pio
0x180056482  call    cs:__imp_CancelThreadpoolIo
0x180056488  mov     rcx, cs:WPP_GLOBAL_Control
0x18005648f  lea     rax, WPP_GLOBAL_Control
0x180056496  cmp     rcx, rax
0x180056499  jz      short loc_1800564B8
0x18005649b  test    dword ptr [rcx+1Ch], 200h
0x1800564a2  jz      short loc_1800564B8
0x1800564a4  mov     edx, 64h ; 'd'
0x1800564a9  mov     r9d, r15d
0x1800564ac  mov     r8, rsi
0x1800564af  mov     rcx, [rcx+10h]
0x1800564b3  call    WPP_SF_d
0x1800564b8  mov     rax, [rbx]
0x1800564bb  mov     edx, 1
0x1800564c0  mov     rcx, rbx
0x1800564c3  mov     rax, [rax+10h]
0x1800564c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564cc  mov     ecx, r15d
0x1800564cf  jmp     loc_1800565A5
0x1800564d4  test    [rcx+1Ch], r12d
0x1800564d8  jz      loc_1800562BA
0x1800564de  mov     edx, 65h ; 'e'
0x1800564e3  mov     [rsp+78h+var_58], rbx
0x1800564e8  mov     r9, rdi
0x1800564eb  mov     r8, rsi
0x1800564ee  mov     rcx, [rcx+10h]
0x1800564f2  call    WPP_SF_qq
0x1800564f7  jmp     loc_1800562BA
0x1800564fc  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x180056505  mov     r9d, 54Fh; unsigned int
0x18005650b  lea     r8, a1690; "1690"
0x180056512  mov     edx, 69Ah; unsigned int
0x180056517  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18005651e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180056523  jmp     loc_180056301
0x180056528  mov     rcx, cs:WPP_GLOBAL_Control
0x18005652f  lea     rax, WPP_GLOBAL_Control
0x180056536  cmp     rcx, rax
0x180056539  jz      short loc_18005655A
  ... truncated ...
```
