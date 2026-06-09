# CMicBoostNotificationsHandler::~CMicBoostNotificationsHandler(void)

- ea: `0x140064014`
- end: `0x1400640f2`
- name: `??1CMicBoostNotificationsHandler@@UEAA@XZ`
- size: `222`
- prototype: `void __fastcall(CMicBoostNotificationsHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140064100`

## callees

- `0x140008124`
- `0x140046dc0`
- `0x140055e94`
- `0x140064014`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064075`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064075`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400640b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400640b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064047`

## pseudocode

```c
void __fastcall CMicBoostNotificationsHandler::~CMicBoostNotificationsHandler(CMicBoostNotificationsHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx

  *(_QWORD *)this = &CMicBoostNotificationsHandler::`vftable';
  *((_QWORD *)this + 1) = &CMicBoostNotificationsHandler::`vftable'{for `IControlChangeNotify'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IControlChangeNotify>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_BYTE *)this + 112) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 120LL))(
      *((_QWORD *)this + 6),
      *((_QWORD *)this + 16));
  if ( v2 )
    LeaveCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 128);
  v3 = (_QWORD *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v3 + 1);
      std::_Deallocate<16>(v3, 16);
      v3 = v4;
    }
    while ( v4 );
  }
  DeleteCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 64);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 56);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 40);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(this);
}

```

## disassembly

```asm
0x140064014  push    rbx
0x140064016  push    rbp
0x140064017  push    rsi
0x140064018  push    rdi
0x140064019  sub     rsp, 28h
0x14006401d  mov     rdi, rcx
0x140064020  lea     rax, ??_7CMicBoostNotificationsHandler@@6B@; const CMicBoostNotificationsHandler::`vftable'
0x140064027  mov     [rcx], rax
0x14006402a  lea     rax, ??_7CMicBoostNotificationsHandler@@6BIControlChangeNotify@@@; const CMicBoostNotificationsHandler::`vftable'{for `IControlChangeNotify'}
0x140064031  mov     [rcx+8], rax
0x140064035  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIControlChangeNotify@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IControlChangeNotify>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x14006403c  mov     [rcx+10h], rax
0x140064040  lea     rbp, [rcx+48h]
0x140064044  mov     rcx, rbp; lpCriticalSection
0x140064047  call    cs:__imp_EnterCriticalSection
0x14006404d  lea     rbx, [rdi+80h]
0x140064054  cmp     byte ptr [rdi+70h], 0
0x140064058  jz      short loc_14006406D
0x14006405a  mov     rcx, [rdi+30h]
0x14006405e  mov     rax, [rcx]
0x140064061  mov     rdx, [rbx]
0x140064064  mov     rax, [rax+78h]
0x140064068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006406d  test    rbp, rbp
0x140064070  jz      short loc_14006407B
0x140064072  mov     rcx, rbp; lpCriticalSection
0x140064075  call    cs:__imp_LeaveCriticalSection
0x14006407b  mov     rcx, rbx
0x14006407e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140064083  mov     rsi, [rdi+78h]
0x140064087  mov     qword ptr [rdi+78h], 0
0x14006408f  test    rsi, rsi
0x140064092  jz      short loc_1400640B5
0x140064094  mov     rbx, [rsi]
0x140064097  lea     rcx, [rsi+8]
0x14006409b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400640a0  mov     edx, 10h
0x1400640a5  mov     rcx, rsi
0x1400640a8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400640ad  mov     rsi, rbx
0x1400640b0  test    rbx, rbx
0x1400640b3  jnz     short loc_140064094
0x1400640b5  mov     rcx, rbp; lpCriticalSection
0x1400640b8  call    cs:__imp_DeleteCriticalSection
0x1400640be  lea     rcx, [rdi+40h]
0x1400640c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400640c7  lea     rcx, [rdi+38h]
0x1400640cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400640d0  lea     rcx, [rdi+30h]
0x1400640d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400640d9  lea     rcx, [rdi+28h]
0x1400640dd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400640e2  mov     rcx, rdi
0x1400640e5  add     rsp, 28h
0x1400640e9  pop     rdi
0x1400640ea  pop     rsi
0x1400640eb  pop     rbp
0x1400640ec  pop     rbx
0x1400640ed  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioSystemEffectsPropertyChangeNotificationClient@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(void)
```
