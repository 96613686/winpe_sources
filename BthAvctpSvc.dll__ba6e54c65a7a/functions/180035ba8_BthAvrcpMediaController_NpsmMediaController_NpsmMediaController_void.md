# BthAvrcpMediaController::NpsmMediaController::~NpsmMediaController(void)

- ea: `0x180035ba8`
- end: `0x180035d78`
- name: `??1NpsmMediaController@BthAvrcpMediaController@@UEAA@XZ`
- size: `464`
- prototype: `void __fastcall(BthAvrcpMediaController::NpsmMediaController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037120`

## callees

- `0x18000d0c0`
- `0x1800235bc`
- `0x180023da8`
- `0x1800332fc`
- `0x180035b80`
- `0x180035ba8`
- `0x18003a0f4`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d5f`

## pseudocode

```c
void __fastcall BthAvrcpMediaController::NpsmMediaController::~NpsmMediaController(
        BthAvrcpMediaController::NpsmMediaController *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rcx
  int v5; // eax

  *(_QWORD *)this = &BthAvrcpMediaController::NpsmMediaController::`vftable';
  *((_QWORD *)this + 1) = &BthAvrcpMediaController::NpsmMediaController::`vftable'{for `INowPlayingSessionManagerEventHandler'};
  *((_QWORD *)this + 2) = &BthAvrcpMediaController::NpsmMediaController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaPlaybackDataChangedEventHandler>'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v2 = *((_QWORD *)this + 41);
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 64LL))(v2, *((_QWORD *)this + 42));
    if ( v3 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_95e767cb7999366f67a133efb5540c97_Traceguids,
        (unsigned int)v3);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 328);
  }
  v4 = *((_QWORD *)this + 39);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 112LL))(v4, *((_QWORD *)this + 40));
    if ( v5 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_95e767cb7999366f67a133efb5540c97_Traceguids,
        (unsigned int)v5);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 312);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) == 0xFF )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, this);
  }
  if ( this != (BthAvrcpMediaController::NpsmMediaController *)-96LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 344);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 328);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 312);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 288);
  BthAvrcpMediaController::BthAvMediaTrack::~BthAvMediaTrack((BthAvrcpMediaController::NpsmMediaController *)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>((__int64 *)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_DWORD *)this + 7) = -1073741823;
}

```

## disassembly

```asm
0x180035ba8  push    rbx
0x180035baa  push    rsi
0x180035bab  push    rdi
0x180035bac  push    r14
0x180035bae  push    r15
0x180035bb0  sub     rsp, 20h
0x180035bb4  mov     rbx, rcx
0x180035bb7  lea     rax, ??_7NpsmMediaController@BthAvrcpMediaController@@6B@; const BthAvrcpMediaController::NpsmMediaController::`vftable'
0x180035bbe  mov     [rcx], rax
0x180035bc1  lea     rax, ??_7NpsmMediaController@BthAvrcpMediaController@@6BINowPlayingSessionManagerEventHandler@@@; const BthAvrcpMediaController::NpsmMediaController::`vftable'{for `INowPlayingSessionManagerEventHandler'}
0x180035bc8  mov     [rcx+8], rax
0x180035bcc  lea     rax, ??_7NpsmMediaController@BthAvrcpMediaController@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMediaPlaybackDataChangedEventHandler@@@Details@WRL@Microsoft@@@; const BthAvrcpMediaController::NpsmMediaController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaPlaybackDataChangedEventHandler>'}
0x180035bd3  mov     [rcx+10h], rax
0x180035bd7  lea     r15, WPP_GLOBAL_Control
0x180035bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180035be5  cmp     rcx, r15
0x180035be8  jz      short loc_180035C0E
0x180035bea  test    byte ptr [rcx+1Ch], 1
0x180035bee  jz      short loc_180035C0E
0x180035bf0  cmp     byte ptr [rcx+19h], 4
0x180035bf4  jb      short loc_180035C0E
0x180035bf6  mov     edx, 0Ch
0x180035bfb  mov     r9, rbx
0x180035bfe  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180035c05  mov     rcx, [rcx+10h]
0x180035c09  call    WPP_SF_q
0x180035c0e  lea     rdi, [rbx+60h]
0x180035c12  mov     rcx, rdi; lpCriticalSection
0x180035c15  call    cs:__imp_EnterCriticalSection
0x180035c1b  lea     r14, [rbx+148h]
0x180035c22  mov     rcx, [r14]
0x180035c25  test    rcx, rcx
0x180035c28  jz      short loc_180035C79
0x180035c2a  mov     rax, [rcx]
0x180035c2d  mov     rdx, [rbx+150h]
0x180035c34  mov     rax, [rax+40h]
0x180035c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c3d  test    eax, eax
0x180035c3f  jns     short loc_180035C71
0x180035c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c48  cmp     rcx, r15
0x180035c4b  jz      short loc_180035C71
0x180035c4d  test    byte ptr [rcx+1Ch], 1
0x180035c51  jz      short loc_180035C71
0x180035c53  cmp     byte ptr [rcx+19h], 2
0x180035c57  jb      short loc_180035C71
0x180035c59  mov     edx, 0Dh
0x180035c5e  mov     r9d, eax
0x180035c61  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180035c68  mov     rcx, [rcx+10h]
0x180035c6c  call    WPP_SF_d
0x180035c71  mov     rcx, r14
0x180035c74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035c79  lea     rsi, [rbx+138h]
0x180035c80  mov     rcx, [rsi]
0x180035c83  test    rcx, rcx
0x180035c86  jz      short loc_180035CD7
0x180035c88  mov     rax, [rcx]
0x180035c8b  mov     rdx, [rbx+140h]
0x180035c92  mov     rax, [rax+70h]
0x180035c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c9b  test    eax, eax
0x180035c9d  jns     short loc_180035CCF
0x180035c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ca6  cmp     rcx, r15
0x180035ca9  jz      short loc_180035CCF
0x180035cab  test    byte ptr [rcx+1Ch], 1
0x180035caf  jz      short loc_180035CCF
0x180035cb1  cmp     byte ptr [rcx+19h], 2
0x180035cb5  jb      short loc_180035CCF
0x180035cb7  mov     edx, 0Eh
0x180035cbc  mov     r9d, eax
0x180035cbf  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180035cc6  mov     rcx, [rcx+10h]
0x180035cca  call    WPP_SF_d
0x180035ccf  mov     rcx, rsi
0x180035cd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cde  cmp     rcx, r15
0x180035ce1  jz      short loc_180035D07
0x180035ce3  test    byte ptr [rcx+1Ch], 1
0x180035ce7  jz      short loc_180035D07
0x180035ce9  cmp     byte ptr [rcx+19h], 0FFh
0x180035ced  jb      short loc_180035D07
0x180035cef  mov     edx, 0Fh
0x180035cf4  mov     r9, rbx
0x180035cf7  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180035cfe  mov     rcx, [rcx+10h]
0x180035d02  call    WPP_SF_q
0x180035d07  test    rdi, rdi
0x180035d0a  jz      short loc_180035D15
0x180035d0c  mov     rcx, rdi; lpCriticalSection
0x180035d0f  call    cs:__imp_LeaveCriticalSection
0x180035d15  lea     rcx, [rbx+158h]
0x180035d1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035d21  mov     rcx, r14
0x180035d24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035d29  mov     rcx, rsi
0x180035d2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035d31  lea     rcx, [rbx+120h]
0x180035d38  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035d3d  lea     rcx, [rbx+88h]; this
0x180035d44  call    ??1BthAvMediaTrack@BthAvrcpMediaController@@QEAA@XZ; BthAvrcpMediaController::BthAvMediaTrack::~BthAvMediaTrack(void)
0x180035d49  mov     rcx, rdi; lpCriticalSection
0x180035d4c  call    cs:__imp_DeleteCriticalSection
0x180035d52  lea     rcx, [rbx+48h]
0x180035d56  call    ??1?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>(void)
0x180035d5b  lea     rcx, [rbx+20h]; lpCriticalSection
0x180035d5f  call    cs:__imp_DeleteCriticalSection
0x180035d65  mov     dword ptr [rbx+1Ch], 0C0000001h
0x180035d6c  add     rsp, 20h
0x180035d70  pop     r15
0x180035d72  pop     r14
0x180035d74  pop     rdi
0x180035d75  pop     rsi
0x180035d76  pop     rbx
0x180035d77  retn
```
