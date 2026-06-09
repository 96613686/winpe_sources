# AudioFrameImpl::AudioFrameImpl(uint)

- ea: `0x18000ea68`
- end: `0x18000ebd3`
- name: `??0AudioFrameImpl@@QEAA@I@Z`
- size: `363`
- prototype: `AudioFrameImpl *__fastcall(AudioFrameImpl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000822c`

## callees

- `0x1800019c0`
- `0x180001ec0`
- `0x180005cd0`
- `0x1800093d4`
- `0x18000a9e0`
- `0x18000ea68`
- `0x18000ebdc`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000eb89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000eb89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eb6d`
- `MFPlat!MFCreateSample` at `0x18000eafe`
- `MFPlat!MFCreateSample` at `0x18000eafe`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
AudioFrameImpl *__fastcall AudioFrameImpl::AudioFrameImpl(AudioFrameImpl *this, int a2)
{
  unsigned int v3; // eax
  int v4; // edx
  IMFSample *v5; // rsi
  HRESULT (__stdcall *AddBuffer)(IMFSample *, IMFMediaBuffer *); // rbp
  __int64 v7; // rbx
  unsigned int v8; // eax
  int v9; // edx
  unsigned int String; // eax
  int v11; // edx
  IMFSample *v12; // rcx
  int v14; // [rsp+58h] [rbp+10h] BYREF
  IMFSample *ppIMFSample; // [rsp+60h] [rbp+18h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h]

  v14 = a2;
  Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>();
  *(_QWORD *)this = &AudioFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
  *((_QWORD *)this + 1) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &AudioFrameImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 15) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
  *((_QWORD *)this + 16) = &AudioFrameImpl::`vftable'{for `Windows::Media::IAudioFrame'};
  *((_QWORD *)this + 17) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
  Microsoft::WRL::Details::Make<AudioFrameState,unsigned int &>((char *)this + 160, &v14);
  MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>((char *)this + 160);
  ppIMFSample = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppIMFSample);
  v3 = MFCreateSample(&ppIMFSample);
  MF::ThrowIfFailed((MF *)v3, v4);
  v5 = ppIMFSample;
  AddBuffer = ppIMFSample->lpVtbl->AddBuffer;
  v7 = *(_QWORD *)(*((_QWORD *)this + 20) + 40LL);
  v16 = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v8 = ((__int64 (__fastcall *)(IMFSample *, __int64))AddBuffer)(v5, v7);
  MF::ThrowIfFailed((MF *)v8, v9);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  String = WindowsCreateString(L"AudioFrame", 0xAu, (HSTRING *)this + 12);
  MF::ThrowIfFailed((MF *)String, v11);
  MediaFrameImpl::Initialize(this);
  v12 = ppIMFSample;
  if ( ppIMFSample )
  {
    ppIMFSample = 0;
    ((void (__fastcall *)(IMFSample *))v12->lpVtbl->Release)(v12);
  }
  return this;
}

```

## disassembly

```asm
0x18000ea68  mov     [rsp+arg_8], edx
0x18000ea6c  mov     [rsp+arg_0], rcx
0x18000ea71  push    rbx
0x18000ea72  push    rbp
0x18000ea73  push    rsi
0x18000ea74  push    rdi
0x18000ea75  sub     rsp, 28h
0x18000ea79  mov     rdi, rcx
0x18000ea7c  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>(void)
0x18000ea81  nop
0x18000ea82  lea     rax, ??_7AudioFrameImpl@@6BIMediaFrame@Media@Windows@@@; const AudioFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x18000ea89  mov     [rdi], rax
0x18000ea8c  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ea93  mov     [rdi+8], rax
0x18000ea97  lea     rax, ??_7AudioFrameImpl@@6BIWeakReferenceSource@@@; const AudioFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x18000ea9e  mov     [rdi+70h], rax
0x18000eaa2  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIAudioFrame@Media@6@U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x18000eaa9  mov     [rdi+78h], rax
0x18000eaad  lea     rax, ??_7AudioFrameImpl@@6BIAudioFrame@Media@Windows@@@; const AudioFrameImpl::`vftable'{for `Windows::Media::IAudioFrame'}
0x18000eab4  mov     [rdi+80h], rax
0x18000eabb  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x18000eac2  mov     [rdi+88h], rax
0x18000eac9  lea     rbx, [rdi+0A0h]
0x18000ead0  lea     rdx, [rsp+48h+arg_8]
0x18000ead5  mov     rcx, rbx
0x18000ead8  call    ??$Make@VAudioFrameState@@AEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAudioFrameState@@@12@AEAI@Z; Microsoft::WRL::Details::Make<AudioFrameState,uint &>(uint &)
0x18000eadd  nop
0x18000eade  mov     rcx, rbx
0x18000eae1  call    ??$ThrowIfBadAlloc@V?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@MF@@YAXAEBV?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@Z; MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(Microsoft::WRL::ComPtr<AudioFrameState> const &)
0x18000eae6  mov     [rsp+48h+ppIMFSample], 0
0x18000eaef  lea     rcx, [rsp+48h+ppIMFSample]
0x18000eaf4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000eaf9  lea     rcx, [rsp+48h+ppIMFSample]; ppIMFSample
0x18000eafe  call    cs:__imp_MFCreateSample
0x18000eb04  mov     ecx, eax; this
0x18000eb06  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000eb0b  mov     rsi, [rsp+48h+ppIMFSample]
0x18000eb10  mov     rax, [rsi]
0x18000eb13  mov     rbp, [rax+150h]
0x18000eb1a  mov     rax, [rbx]
0x18000eb1d  mov     rbx, [rax+28h]
0x18000eb21  mov     [rsp+48h+arg_18], rbx
0x18000eb26  test    rbx, rbx
0x18000eb29  jz      short loc_18000EB3B
0x18000eb2b  mov     rax, [rbx]
0x18000eb2e  mov     rcx, rbx
0x18000eb31  mov     rax, [rax+8]
0x18000eb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb3a  nop
0x18000eb3b  mov     rdx, rbx
0x18000eb3e  mov     rcx, rsi
0x18000eb41  mov     rax, rbp
0x18000eb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb49  mov     ecx, eax; this
0x18000eb4b  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000eb50  nop
0x18000eb51  test    rbx, rbx
0x18000eb54  jz      short loc_18000EB66
0x18000eb56  mov     rax, [rbx]
0x18000eb59  mov     rcx, rbx
0x18000eb5c  mov     rax, [rax+10h]
0x18000eb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb65  nop
0x18000eb66  lea     rbx, [rdi+60h]
0x18000eb6a  mov     rcx, [rbx]; string
0x18000eb6d  call    cs:__imp_WindowsDeleteString
0x18000eb73  mov     qword ptr [rbx], 0
0x18000eb7a  mov     r8, rbx; string
0x18000eb7d  mov     edx, 0Ah; length
0x18000eb82  lea     rcx, aAudioframe; "AudioFrame"
0x18000eb89  call    cs:__imp_WindowsCreateString
0x18000eb8f  mov     ecx, eax; this
0x18000eb91  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000eb96  xor     r8d, r8d
0x18000eb99  lea     rdx, [rsp+48h+ppIMFSample]
0x18000eb9e  mov     rcx, rdi; this
0x18000eba1  call    ?Initialize@MediaFrameImpl@@IEAAXAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFrameImpl::Initialize(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x18000eba6  nop
0x18000eba7  mov     rcx, [rsp+48h+ppIMFSample]
0x18000ebac  test    rcx, rcx
0x18000ebaf  jz      short loc_18000EBC7
0x18000ebb1  mov     [rsp+48h+ppIMFSample], 0
0x18000ebba  mov     rax, [rcx]
0x18000ebbd  mov     rax, [rax+10h]
0x18000ebc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebc6  nop
0x18000ebc7  mov     rax, rdi
0x18000ebca  add     rsp, 28h
0x18000ebce  pop     rdi
0x18000ebcf  pop     rsi
0x18000ebd0  pop     rbp
0x18000ebd1  pop     rbx
0x18000ebd2  retn
```
