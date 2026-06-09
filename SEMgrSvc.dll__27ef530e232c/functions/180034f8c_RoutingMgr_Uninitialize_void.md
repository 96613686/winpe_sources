# RoutingMgr::Uninitialize(void)

- ea: `0x180034f8c`
- end: `0x180035105`
- name: `?Uninitialize@RoutingMgr@@AEAAXXZ`
- size: `377`
- prototype: `void __fastcall(RoutingMgr *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002f36c`
- `0x180031614`
- `0x1800358b8`

## callees

- `0x1800049c4`
- `0x180016284`
- `0x180032aa0`
- `0x180034f8c`
- `0x18008f720`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800350d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800350d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800350e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800350e3`

## pseudocode

```c
void __fastcall RoutingMgr::Uninitialize(RoutingMgr *this)
{
  void *v2; // rdi
  char v3; // bp
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void *v6; // rdi
  void *v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // r8
  __int64 i; // rax
  struct _TP_WORK *v11; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v2 = (void *)*((_QWORD *)this + 7);
  v3 = *((_BYTE *)this + 177);
  if ( v2 )
  {
    Broker::BILayer::NotificationChannel::~NotificationChannel(*((Broker::BILayer::NotificationChannel **)this + 7));
    operator delete(v2);
    *((_QWORD *)this + 7) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = 0;
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = 0;
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (void *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 18) = 0;
  if ( v6 )
  {
    std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(v6);
    operator delete(v6);
  }
  v7 = (void *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 21) = 0;
  if ( v7 )
    operator delete(v7);
  v8 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 5) > 7u )
    v8 = (_QWORD *)*v8;
  *(_WORD *)v8 = 0;
  *((_QWORD *)this + 8) = 0;
  *((_BYTE *)this + 177) = 0;
  v9 = *((_QWORD *)this + 16);
  for ( i = *((_QWORD *)this + 15); i != v9; i += 140 )
    *(_BYTE *)(i + 136) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( v3 )
  {
    v11 = (struct _TP_WORK *)*((_QWORD *)this + 51);
    if ( v11 )
    {
      WaitForThreadpoolWorkCallbacks(v11, 1);
      CloseThreadpoolWork(*((PTP_WORK *)this + 51));
      *((_QWORD *)this + 51) = 0;
      RoutingMgr::ReleaseUnusedApplicationForegroundMonitors(this);
    }
  }
}

```

## disassembly

```asm
0x180034f8c  push    rbx
0x180034f8e  push    rbp
0x180034f8f  push    rsi
0x180034f90  push    rdi
0x180034f91  sub     rsp, 28h
0x180034f95  mov     rbx, rcx
0x180034f98  add     rcx, 50h ; 'P'; lpCriticalSection
0x180034f9c  call    cs:__imp_EnterCriticalSection
0x180034fa2  mov     rdi, [rbx+38h]
0x180034fa6  mov     bpl, [rbx+0B1h]
0x180034fad  test    rdi, rdi
0x180034fb0  jz      short loc_180034FCF
0x180034fb2  mov     rcx, rdi; this
0x180034fb5  call    ??1NotificationChannel@BILayer@Broker@@QEAA@XZ; Broker::BILayer::NotificationChannel::~NotificationChannel(void)
0x180034fba  mov     edx, 40h ; '@'
0x180034fbf  mov     rcx, rdi; Block
0x180034fc2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034fc7  mov     qword ptr [rbx+38h], 0
0x180034fcf  mov     rcx, [rbx+0A0h]
0x180034fd6  mov     qword ptr [rbx+0A0h], 0
0x180034fe1  test    rcx, rcx
0x180034fe4  jz      short loc_180034FF6
0x180034fe6  mov     rax, [rcx]
0x180034fe9  mov     edx, 1
0x180034fee  mov     rax, [rax]
0x180034ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ff6  mov     rcx, [rbx+98h]
0x180034ffd  mov     qword ptr [rbx+98h], 0
0x180035008  test    rcx, rcx
0x18003500b  jz      short loc_18003501D
0x18003500d  mov     rax, [rcx]
0x180035010  mov     edx, 1
0x180035015  mov     rax, [rax]
0x180035018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501d  mov     rdi, [rbx+90h]
0x180035024  mov     qword ptr [rbx+90h], 0
0x18003502f  test    rdi, rdi
0x180035032  jz      short loc_180035049
0x180035034  mov     rcx, rdi
0x180035037  call    ??1?$vector@U_SECURE_ELEMENT_ENDPOINT_INFO@@V?$allocator@U_SECURE_ELEMENT_ENDPOINT_INFO@@@std@@@std@@QEAA@XZ; std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(void)
0x18003503c  mov     edx, 18h
0x180035041  mov     rcx, rdi; Block
0x180035044  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035049  mov     rcx, [rbx+0A8h]; Block
0x180035050  mov     qword ptr [rbx+8], 0
0x180035058  mov     qword ptr [rbx+0A8h], 0
0x180035063  test    rcx, rcx
0x180035066  jz      short loc_180035072
0x180035068  mov     edx, 8
0x18003506d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035072  lea     rcx, [rbx+10h]
0x180035076  mov     qword ptr [rcx+10h], 0
0x18003507e  cmp     qword ptr [rcx+18h], 7
0x180035083  jbe     short loc_180035088
0x180035085  mov     rcx, [rcx]
0x180035088  xor     eax, eax
0x18003508a  mov     [rcx], ax
0x18003508d  mov     [rbx+40h], rax
0x180035091  mov     [rbx+0B1h], al
0x180035097  mov     r8, [rbx+80h]
0x18003509e  mov     rax, [rbx+78h]
0x1800350a2  jmp     short loc_1800350B1
0x1800350a4  mov     byte ptr [rax+88h], 1
0x1800350ab  add     rax, 8Ch
0x1800350b1  cmp     rax, r8
0x1800350b4  jnz     short loc_1800350A4
0x1800350b6  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800350ba  call    cs:__imp_LeaveCriticalSection
0x1800350c0  test    bpl, bpl
0x1800350c3  jz      short loc_1800350FC
0x1800350c5  mov     rcx, [rbx+198h]; pwk
0x1800350cc  test    rcx, rcx
0x1800350cf  jz      short loc_1800350FC
0x1800350d1  mov     edx, 1; fCancelPendingCallbacks
0x1800350d6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800350dc  mov     rcx, [rbx+198h]; pwk
0x1800350e3  call    cs:__imp_CloseThreadpoolWork
0x1800350e9  mov     rcx, rbx; this
0x1800350ec  mov     qword ptr [rbx+198h], 0
0x1800350f7  call    ?ReleaseUnusedApplicationForegroundMonitors@RoutingMgr@@AEAAJXZ; RoutingMgr::ReleaseUnusedApplicationForegroundMonitors(void)
0x1800350fc  add     rsp, 28h
0x180035100  pop     rdi
0x180035101  pop     rsi
0x180035102  pop     rbp
0x180035103  pop     rbx
0x180035104  retn
```
