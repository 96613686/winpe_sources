# CAPOEndpointNotificationsHandler::~CAPOEndpointNotificationsHandler(void)

- ea: `0x140063490`
- end: `0x1400635fb`
- name: `??1CAPOEndpointNotificationsHandler@@UEAA@XZ`
- size: `363`
- prototype: `void __fastcall(CAPOEndpointNotificationsHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140063650`

## callees

- `0x140008124`
- `0x140046dc0`
- `0x140055e94`
- `0x140063490`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400634f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400634f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400635a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400635da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400635a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400635da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400634c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400634c5`

## pseudocode

```c
void __fastcall CAPOEndpointNotificationsHandler::~CAPOEndpointNotificationsHandler(
        CAPOEndpointNotificationsHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  _QWORD *v6; // rbx
  _QWORD *v7; // rsi
  _QWORD *v8; // rbx

  *(_QWORD *)this = &CAPOEndpointNotificationsHandler::`vftable';
  *((_QWORD *)this + 1) = &CAPOEndpointNotificationsHandler::`vftable'{for `IAudioEndpointVolumeInternalCallback'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioEndpointVolumeInternalCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_BYTE *)this + 136) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 18) + 32LL))(
      *((_QWORD *)this + 18),
      *((_QWORD *)this + 23));
  if ( v2 )
    LeaveCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 184);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 176);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 168);
  v3 = (_QWORD *)*((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = 0;
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
  v5 = (_QWORD *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = 0;
  if ( v5 )
  {
    do
    {
      v6 = (_QWORD *)*v5;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v5 + 1);
      std::_Deallocate<16>(v5, 16);
      v5 = v6;
    }
    while ( v6 );
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 144);
  DeleteCriticalSection(v2);
  v7 = (_QWORD *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v7 )
  {
    do
    {
      v8 = (_QWORD *)*v7;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v7 + 1);
      std::_Deallocate<16>(v7, 16);
      v7 = v8;
    }
    while ( v8 );
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 40);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(this);
}

```

## disassembly

```asm
0x140063490  push    rbx
0x140063492  push    rbp
0x140063493  push    rsi
0x140063494  push    rdi
0x140063495  push    r15
0x140063497  sub     rsp, 20h
0x14006349b  mov     rdi, rcx
0x14006349e  lea     rax, ??_7CAPOEndpointNotificationsHandler@@6B@; const CAPOEndpointNotificationsHandler::`vftable'
0x1400634a5  mov     [rcx], rax
0x1400634a8  lea     rax, ??_7CAPOEndpointNotificationsHandler@@6BIAudioEndpointVolumeInternalCallback@@@; const CAPOEndpointNotificationsHandler::`vftable'{for `IAudioEndpointVolumeInternalCallback'}
0x1400634af  mov     [rcx+8], rax
0x1400634b3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioEndpointVolumeInternalCallback@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioEndpointVolumeInternalCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x1400634ba  mov     [rcx+10h], rax
0x1400634be  lea     rbp, [rcx+60h]
0x1400634c2  mov     rcx, rbp; lpCriticalSection
0x1400634c5  call    cs:__imp_EnterCriticalSection
0x1400634cb  lea     rbx, [rdi+0B8h]
0x1400634d2  cmp     byte ptr [rdi+88h], 0
0x1400634d9  jz      short loc_1400634F1
0x1400634db  mov     rcx, [rdi+90h]
0x1400634e2  mov     rax, [rcx]
0x1400634e5  mov     rdx, [rbx]
0x1400634e8  mov     rax, [rax+20h]
0x1400634ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400634f1  test    rbp, rbp
0x1400634f4  jz      short loc_1400634FF
0x1400634f6  mov     rcx, rbp; lpCriticalSection
0x1400634f9  call    cs:__imp_LeaveCriticalSection
0x1400634ff  mov     rcx, rbx
0x140063502  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140063507  lea     rcx, [rdi+0B0h]
0x14006350e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140063513  lea     rcx, [rdi+0A8h]
0x14006351a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006351f  mov     rsi, [rdi+0A0h]
0x140063526  mov     qword ptr [rdi+0A0h], 0
0x140063531  mov     r15d, 10h
0x140063537  test    rsi, rsi
0x14006353a  jz      short loc_14006355B
0x14006353c  mov     rbx, [rsi]
0x14006353f  lea     rcx, [rsi+8]
0x140063543  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140063548  mov     rdx, r15
0x14006354b  mov     rcx, rsi
0x14006354e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140063553  mov     rsi, rbx
0x140063556  test    rbx, rbx
0x140063559  jnz     short loc_14006353C
0x14006355b  mov     rsi, [rdi+98h]
0x140063562  mov     qword ptr [rdi+98h], 0
0x14006356d  test    rsi, rsi
0x140063570  jz      short loc_140063591
0x140063572  mov     rbx, [rsi]
0x140063575  lea     rcx, [rsi+8]
0x140063579  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006357e  mov     rdx, r15
0x140063581  mov     rcx, rsi
0x140063584  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140063589  mov     rsi, rbx
0x14006358c  test    rbx, rbx
0x14006358f  jnz     short loc_140063572
0x140063591  lea     rcx, [rdi+90h]
0x140063598  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006359d  mov     rcx, rbp; lpCriticalSection
0x1400635a0  call    cs:__imp_DeleteCriticalSection
0x1400635a6  mov     rsi, [rdi+58h]
0x1400635aa  mov     qword ptr [rdi+58h], 0
0x1400635b2  test    rsi, rsi
0x1400635b5  jz      short loc_1400635D6
0x1400635b7  mov     rbx, [rsi]
0x1400635ba  lea     rcx, [rsi+8]
0x1400635be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400635c3  mov     rdx, r15
0x1400635c6  mov     rcx, rsi
0x1400635c9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400635ce  mov     rsi, rbx
0x1400635d1  test    rbx, rbx
0x1400635d4  jnz     short loc_1400635B7
0x1400635d6  lea     rcx, [rdi+30h]; lpCriticalSection
0x1400635da  call    cs:__imp_DeleteCriticalSection
0x1400635e0  lea     rcx, [rdi+28h]
0x1400635e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400635e9  mov     rcx, rdi
0x1400635ec  add     rsp, 20h
0x1400635f0  pop     r15
0x1400635f2  pop     rdi
0x1400635f3  pop     rsi
0x1400635f4  pop     rbp
0x1400635f5  pop     rbx
0x1400635f6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioSystemEffectsPropertyChangeNotificationClient@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(void)
```
