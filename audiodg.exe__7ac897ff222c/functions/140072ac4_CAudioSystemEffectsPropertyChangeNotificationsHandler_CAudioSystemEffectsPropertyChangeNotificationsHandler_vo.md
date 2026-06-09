# CAudioSystemEffectsPropertyChangeNotificationsHandler::~CAudioSystemEffectsPropertyChangeNotificationsHandler(void)

- ea: `0x140072ac4`
- end: `0x140072bcc`
- name: `??1CAudioSystemEffectsPropertyChangeNotificationsHandler@@UEAA@XZ`
- size: `264`
- prototype: `void __fastcall(CAudioSystemEffectsPropertyChangeNotificationsHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400654a0`

## callees

- `0x140008124`
- `0x140035554`
- `0x140046dc0`
- `0x140055e94`
- `0x140072ac4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140072b2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140072b2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140072ba4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140072ba4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140072af7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140072af7`

## pseudocode

```c
void __fastcall CAudioSystemEffectsPropertyChangeNotificationsHandler::~CAudioSystemEffectsPropertyChangeNotificationsHandler(
        CAudioSystemEffectsPropertyChangeNotificationsHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx

  *(_QWORD *)this = &CAudioSystemEffectsPropertyChangeNotificationsHandler::`vftable';
  *((_QWORD *)this + 1) = &CAudioSystemEffectsPropertyChangeNotificationsHandler::`vftable'{for `IAudioSystemEffectsPropertyChangeNotificationClient'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioSystemEffectsPropertyChangeNotificationClient>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_BYTE *)this + 136) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 18) + 72LL))(
      *((_QWORD *)this + 18),
      *((_QWORD *)this + 23));
  if ( v2 )
    LeaveCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 184);
  v3 = (_QWORD *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 168);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 160);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 152);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 144);
  DeleteCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 88);
  std::wstring::~wstring((char *)this + 56);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(this);
}

```

## disassembly

```asm
0x140072ac4  push    rbx
0x140072ac6  push    rbp
0x140072ac7  push    rsi
0x140072ac8  push    rdi
0x140072ac9  sub     rsp, 28h
0x140072acd  mov     rdi, rcx
0x140072ad0  lea     rax, ??_7CAudioSystemEffectsPropertyChangeNotificationsHandler@@6B@; const CAudioSystemEffectsPropertyChangeNotificationsHandler::`vftable'
0x140072ad7  mov     [rcx], rax
0x140072ada  lea     rax, ??_7CAudioSystemEffectsPropertyChangeNotificationsHandler@@6BIAudioSystemEffectsPropertyChangeNotificationClient@@@; const CAudioSystemEffectsPropertyChangeNotificationsHandler::`vftable'{for `IAudioSystemEffectsPropertyChangeNotificationClient'}
0x140072ae1  mov     [rcx+8], rax
0x140072ae5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioSystemEffectsPropertyChangeNotificationClient@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioSystemEffectsPropertyChangeNotificationClient>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x140072aec  mov     [rcx+10h], rax
0x140072af0  lea     rbp, [rcx+60h]
0x140072af4  mov     rcx, rbp; lpCriticalSection
0x140072af7  call    cs:__imp_EnterCriticalSection
0x140072afd  lea     rbx, [rdi+0B8h]
0x140072b04  cmp     byte ptr [rdi+88h], 0
0x140072b0b  jz      short loc_140072B23
0x140072b0d  mov     rcx, [rdi+90h]
0x140072b14  mov     rax, [rcx]
0x140072b17  mov     rdx, [rbx]
0x140072b1a  mov     rax, [rax+48h]
0x140072b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072b23  test    rbp, rbp
0x140072b26  jz      short loc_140072B31
0x140072b28  mov     rcx, rbp; lpCriticalSection
0x140072b2b  call    cs:__imp_LeaveCriticalSection
0x140072b31  mov     rcx, rbx
0x140072b34  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072b39  mov     rsi, [rdi+0B0h]
0x140072b40  mov     qword ptr [rdi+0B0h], 0
0x140072b4b  test    rsi, rsi
0x140072b4e  jz      short loc_140072B71
0x140072b50  mov     rbx, [rsi]
0x140072b53  lea     rcx, [rsi+8]
0x140072b57  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072b5c  mov     edx, 10h
0x140072b61  mov     rcx, rsi
0x140072b64  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140072b69  mov     rsi, rbx
0x140072b6c  test    rbx, rbx
0x140072b6f  jnz     short loc_140072B50
0x140072b71  lea     rcx, [rdi+0A8h]
0x140072b78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072b7d  lea     rcx, [rdi+0A0h]
0x140072b84  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072b89  lea     rcx, [rdi+98h]
0x140072b90  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072b95  lea     rcx, [rdi+90h]
0x140072b9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072ba1  mov     rcx, rbp; lpCriticalSection
0x140072ba4  call    cs:__imp_DeleteCriticalSection
0x140072baa  lea     rcx, [rdi+58h]
0x140072bae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140072bb3  lea     rcx, [rdi+38h]
0x140072bb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140072bbc  mov     rcx, rdi
0x140072bbf  add     rsp, 28h
0x140072bc3  pop     rdi
0x140072bc4  pop     rsi
0x140072bc5  pop     rbp
0x140072bc6  pop     rbx
0x140072bc7  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioSystemEffectsPropertyChangeNotificationClient@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioSystemEffectsPropertyChangeNotificationClient>(void)
```
