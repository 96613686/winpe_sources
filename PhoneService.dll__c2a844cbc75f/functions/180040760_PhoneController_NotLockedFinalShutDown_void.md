# PhoneController::_NotLockedFinalShutDown(void)

- ea: `0x180040760`
- end: `0x18004094b`
- name: `?_NotLockedFinalShutDown@PhoneController@@AEAAXXZ`
- size: `491`
- prototype: `void __fastcall(PhoneController *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b120`
- `0x180033990`

## callees

- `0x1800056a0`
- `0x18000f870`
- `0x18002c574`
- `0x180040760`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800408a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800408a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040906`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040770`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180040835`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180040861`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180040835`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180040861`

## string_xrefs

- `0x180040785`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
void __fastcall PhoneController::_NotLockedFinalShutDown(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  InternalSinkMessageDispatcher *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbp
  __int64 v10; // rbx
  void (__fastcall ***v11)(_QWORD, __int64); // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  _QWORD *v13; // r15
  _QWORD *i; // rbx
  __int64 v15; // rax
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  void (__fastcall ***v18)(_QWORD, __int64); // rcx

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 447);
    __int2c();
  }
  v3 = *((_QWORD *)this + 60);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
  v4 = *((_QWORD *)this + 26);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
  v5 = (InternalSinkMessageDispatcher *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    InternalSinkMessageDispatcher::Uninitialize(v5);
    v6 = *((_QWORD *)this + 11);
    if ( v6 )
    {
      *((_QWORD *)this + 11) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v7 = *((_QWORD *)this + 33);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
    v8 = *((_QWORD *)this + 33);
    if ( v8 )
    {
      *((_QWORD *)this + 33) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  if ( *((_QWORD *)this + 37) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 37) = 0;
    (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 16LL))(this);
  }
  if ( *((_QWORD *)this + 38) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 38) = 0;
    (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 16LL))(this);
  }
  v9 = *((_QWORD *)this + 71);
  if ( v9 )
  {
    v10 = *((_QWORD *)this + 63);
    v11 = 0;
    v12 = (struct _RTL_CRITICAL_SECTION *)(v10 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
    v13 = (_QWORD *)(v10 + 48);
    for ( i = *(_QWORD **)(v10 + 48); i != v13; i = (_QWORD *)*i )
    {
      v15 = i[2];
      if ( *(_QWORD *)(v15 + 8) == v9 )
      {
        i[2] = 0;
        v11 = (void (__fastcall ***)(_QWORD, __int64))v15;
        v16 = (_QWORD *)i[1];
        v17 = (_QWORD *)*i;
        *v16 = *i;
        v17[1] = v16;
        v18 = (void (__fastcall ***)(_QWORD, __int64))i[2];
        if ( v18 )
          (**v18)(v18, 1);
        operator delete(i);
        --v13[2];
        break;
      }
    }
    LeaveCriticalSection(v12);
    if ( v11 )
      (**v11)(v11, 1);
    (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 16LL))(this);
    *((_QWORD *)this + 71) = 0;
  }
}

```

## disassembly

```asm
0x180040760  push    rbx
0x180040762  push    rbp
0x180040763  push    rsi
0x180040764  push    rdi
0x180040765  push    r14
0x180040767  push    r15
0x180040769  sub     rsp, 28h
0x18004076d  mov     r14, rcx
0x180040770  call    cs:__imp_GetCurrentThreadId
0x180040776  cmp     [r14+0F0h], eax
0x18004077d  jnz     short loc_180040793
0x18004077f  mov     r8d, 1BFh
0x180040785  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004078c  call    Log_AssertionEvent_3
0x180040791  int     2Ch; Windows NT - assertion failure
0x180040793  mov     rcx, [r14+1E0h]
0x18004079a  test    rcx, rcx
0x18004079d  jz      short loc_1800407AB
0x18004079f  mov     rax, [rcx]
0x1800407a2  mov     rax, [rax+28h]
0x1800407a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ab  mov     rcx, [r14+0D0h]
0x1800407b2  test    rcx, rcx
0x1800407b5  jz      short loc_1800407C3
0x1800407b7  mov     rax, [rcx]
0x1800407ba  mov     rax, [rax+20h]
0x1800407be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407c3  mov     rcx, [r14+58h]; this
0x1800407c7  test    rcx, rcx
0x1800407ca  jz      short loc_1800407EE
0x1800407cc  call    ?Uninitialize@InternalSinkMessageDispatcher@@QEAAXXZ; InternalSinkMessageDispatcher::Uninitialize(void)
0x1800407d1  mov     rcx, [r14+58h]
0x1800407d5  test    rcx, rcx
0x1800407d8  jz      short loc_1800407EE
0x1800407da  mov     qword ptr [r14+58h], 0
0x1800407e2  mov     rax, [rcx]
0x1800407e5  mov     rax, [rax+10h]
0x1800407e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ee  mov     rcx, [r14+108h]
0x1800407f5  test    rcx, rcx
0x1800407f8  jz      short loc_180040829
0x1800407fa  mov     rax, [rcx]
0x1800407fd  mov     rax, [rax+20h]
0x180040801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040806  mov     rcx, [r14+108h]
0x18004080d  test    rcx, rcx
0x180040810  jz      short loc_180040829
0x180040812  mov     qword ptr [r14+108h], 0
0x18004081d  mov     rax, [rcx]
0x180040820  mov     rax, [rax+10h]
0x180040824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040829  mov     rcx, [r14+128h]
0x180040830  test    rcx, rcx
0x180040833  jz      short loc_180040855
0x180040835  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18004083b  mov     qword ptr [r14+128h], 0
0x180040846  mov     rcx, r14
0x180040849  mov     rax, [r14]
0x18004084c  mov     rax, [rax+10h]
0x180040850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040855  mov     rcx, [r14+130h]
0x18004085c  test    rcx, rcx
0x18004085f  jz      short loc_180040881
0x180040861  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180040867  mov     qword ptr [r14+130h], 0
0x180040872  mov     rcx, r14
0x180040875  mov     rax, [r14]
0x180040878  mov     rax, [rax+10h]
0x18004087c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040881  mov     rbp, [r14+238h]
0x180040888  test    rbp, rbp
0x18004088b  jz      loc_18004093E
0x180040891  mov     rbx, [r14+1F8h]
0x180040898  xor     edi, edi
0x18004089a  lea     rsi, [rbx+8]
0x18004089e  mov     rcx, rsi; lpCriticalSection
0x1800408a1  call    cs:__imp_EnterCriticalSection
0x1800408a7  lea     r15, [rbx+30h]
0x1800408ab  mov     rbx, [r15]
0x1800408ae  cmp     rbx, r15
0x1800408b1  jz      short loc_180040903
0x1800408b3  mov     rax, [rbx+10h]
0x1800408b7  cmp     [rax+8], rbp
0x1800408bb  jz      short loc_1800408C2
0x1800408bd  mov     rbx, [rbx]
0x1800408c0  jmp     short loc_1800408AE
0x1800408c2  mov     [rbx+10h], rdi
0x1800408c6  mov     rdi, rax
0x1800408c9  mov     rcx, [rbx+8]
0x1800408cd  mov     rax, [rbx]
0x1800408d0  mov     [rcx], rax
0x1800408d3  mov     [rax+8], rcx
0x1800408d7  mov     rcx, [rbx+10h]
0x1800408db  test    rcx, rcx
0x1800408de  jz      short loc_1800408F0
0x1800408e0  mov     rax, [rcx]
0x1800408e3  mov     edx, 1
0x1800408e8  mov     rax, [rax]
0x1800408eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800408f7  mov     rcx, rbx; Block
0x1800408fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800408ff  dec     qword ptr [r15+10h]
0x180040903  mov     rcx, rsi; lpCriticalSection
0x180040906  call    cs:__imp_LeaveCriticalSection
0x18004090c  test    rdi, rdi
0x18004090f  jz      short loc_180040924
0x180040911  mov     rax, [rdi]
0x180040914  mov     edx, 1
0x180040919  mov     rcx, rdi
0x18004091c  mov     rax, [rax]
0x18004091f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040924  mov     rax, [r14]
0x180040927  mov     rcx, r14
0x18004092a  mov     rax, [rax+10h]
0x18004092e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040933  mov     qword ptr [r14+238h], 0
0x18004093e  add     rsp, 28h
0x180040942  pop     r15
0x180040944  pop     r14
0x180040946  pop     rdi
0x180040947  pop     rsi
0x180040948  pop     rbp
0x180040949  pop     rbx
0x18004094a  retn
```
