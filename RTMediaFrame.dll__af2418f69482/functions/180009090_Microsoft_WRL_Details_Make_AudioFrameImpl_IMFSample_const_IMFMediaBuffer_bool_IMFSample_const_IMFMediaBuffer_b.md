# Microsoft::WRL::Details::Make<AudioFrameImpl,IMFSample * const &,IMFMediaBuffer *,bool>(IMFSample * const &,IMFMediaBuffer * &&,bool &&)

- ea: `0x180009090`
- end: `0x1800093a5`
- name: `??$Make@VAudioFrameImpl@@AEBQEAUIMFSample@@PEAUIMFMediaBuffer@@_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAudioFrameImpl@@@12@AEBQEAUIMFSample@@$$QEAPEAUIMFMediaBuffer@@$$QEA_N@Z`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x1800087c0`
- `0x180008ee0`
- `0x180009090`
- `0x1800095c0`
- `0x18000a220`
- `0x18000aa70`
- `0x18000ac60`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800091fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800091fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800091e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800091e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
MediaFrameImpl **__fastcall Microsoft::WRL::Details::Make<AudioFrameImpl,IMFSample * const &,IMFMediaBuffer *,bool>(
        MediaFrameImpl **a1,
        __int64 *a2,
        __int64 *a3,
        char *a4)
{
  MediaFrameImpl *v8; // rax
  MediaFrameImpl *v9; // rbx
  char v10; // r15
  __int64 v11; // rdi
  HRESULT String; // eax
  __int64 v13; // rcx
  char *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  char v19[8]; // [rsp+20h] [rbp-39h] BYREF
  __int64 v20; // [rsp+28h] [rbp-31h] BYREF
  int v21; // [rsp+30h] [rbp-29h]
  __int64 v22; // [rsp+38h] [rbp-21h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v24[7]; // [rsp+48h] [rbp-11h]
  char v25; // [rsp+80h] [rbp+27h] BYREF

  *a1 = 0;
  v21 = 1;
  v8 = (MediaFrameImpl *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v24[3] = v8;
  v24[4] = v8;
  if ( v8 )
  {
    v24[5] = v8;
    v10 = *a4;
    v20 = *a3;
    v11 = *a2;
    MediaFrameImpl::MediaFrameImpl(v8);
    *((_QWORD *)v9 + 19) = 1;
    *(_QWORD *)v9 = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Windows::Media::IMediaFrame'};
    *((_QWORD *)v9 + 1) = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v9 + 14) = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `IWeakReferenceSource'};
    *((_QWORD *)v9 + 15) = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
    *((_QWORD *)v9 + 16) = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Windows::Media::IAudioFrame'};
    *((_QWORD *)v9 + 17) = &Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v9 = &AudioFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
    *((_QWORD *)v9 + 1) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v9 + 14) = &AudioFrameImpl::`vftable'{for `IWeakReferenceSource'};
    *((_QWORD *)v9 + 15) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
    *((_QWORD *)v9 + 16) = &AudioFrameImpl::`vftable'{for `Windows::Media::IAudioFrame'};
    *((_QWORD *)v9 + 17) = &AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'};
    Microsoft::WRL::Details::Make<AudioFrameState,IMFMediaBuffer * &>((char *)v9 + 160, &v20);
    if ( !*((_QWORD *)v9 + 20) )
    {
      v24[1] = 0;
      v24[0] = "bad allocation";
      pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    WindowsDeleteString(*((HSTRING *)v9 + 12));
    *((_QWORD *)v9 + 12) = 0;
    String = WindowsCreateString(L"AudioFrame", 0xAu, (HSTRING *)v9 + 12);
    if ( String < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      LODWORD(v24[0]) = String;
      *(_OWORD *)&v24[1] = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v20 = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v19[0] = v10;
    v24[6] = v9;
    if ( *((_QWORD *)v9 + 11) != v11 )
    {
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v13 = *((_QWORD *)v9 + 11);
      *((_QWORD *)v9 + 11) = v11;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    *((_BYTE *)v9 + 48) = v10;
    MediaFrameImpl::ReadMfSample(v9);
    v14 = (char *)Microsoft::WRL::Details::Make<MediaFramePropertySetImpl,Microsoft::WRL::ComPtr<IMFSample> const &,bool &>(
                    &v22,
                    &v20,
                    v19);
    v15 = 0;
    if ( &v25 != v14 )
    {
      v15 = *(_QWORD *)v14;
      *(_QWORD *)v14 = 0;
    }
    v16 = *((_QWORD *)v9 + 10);
    *((_QWORD *)v9 + 10) = v15;
    if ( v16 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(v16);
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(v17);
    }
    if ( !*((_QWORD *)v9 + 10) )
    {
      v24[1] = 0;
      v24[0] = "bad allocation";
      pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::Release(*a1);
    *a1 = v9;
    v9 = 0;
  }
  if ( v9 )
    operator delete(v9);
  return a1;
}

```

## disassembly

```asm
0x180009090  mov     [rsp-8+arg_8], rbx
0x180009095  mov     [rsp-8+arg_10], rsi
0x18000909a  mov     [rsp-8+arg_0], rcx
0x18000909f  push    rbp
0x1800090a0  push    rdi
0x1800090a1  push    r12
0x1800090a3  push    r14
0x1800090a5  push    r15
0x1800090a7  lea     rbp, [rsp-37h]
0x1800090ac  sub     rsp, 90h
0x1800090b3  mov     r15, r9
0x1800090b6  mov     rdi, r8
0x1800090b9  mov     rsi, rdx
0x1800090bc  mov     r14, rcx
0x1800090bf  xor     r12d, r12d
0x1800090c2  mov     [rbp+57h+var_80], r12d
0x1800090c6  mov     [rcx], r12
0x1800090c9  mov     [rbp+57h+var_80], 1
0x1800090d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800090d7  mov     ecx, 0A8h; unsigned __int64
0x1800090dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800090e1  mov     rbx, rax
0x1800090e4  mov     [rbp+57h+var_50], rax
0x1800090e8  mov     [rbp+57h+var_48], rax
0x1800090ec  test    rax, rax
0x1800090ef  jz      loc_1800092EB
0x1800090f5  mov     [rbp+57h+var_40], rax
0x1800090f9  movzx   r15d, byte ptr [r15]
0x1800090fd  mov     rax, [rdi]
0x180009100  mov     [rbp+57h+var_88], rax
0x180009104  mov     rdi, [rsi]
0x180009107  mov     rcx, rbx; this
0x18000910a  call    ??0MediaFrameImpl@@QEAA@XZ; MediaFrameImpl::MediaFrameImpl(void)
0x18000910f  mov     qword ptr [rbx+98h], 1
0x18000911a  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6BIMediaFrame@Media@Windows@@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Windows::Media::IMediaFrame'}
0x180009121  mov     [rbx], rax
0x180009124  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000912b  mov     [rbx+8], rax
0x18000912f  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `IWeakReferenceSource'}
0x180009136  mov     [rbx+70h], rax
0x18000913a  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIAudioFrame@Media@6@U?$CloakedIid@UIAudioFrameNative@@@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x180009141  mov     [rbx+78h], rax
0x180009145  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6BIAudioFrame@Media@Windows@@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Windows::Media::IAudioFrame'}
0x18000914c  mov     [rbx+80h], rax
0x180009153  lea     rax, ??_7?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@4@U?$CloakedIid@UIAudioFrameNative@@@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIAudioFrameNative@@@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x18000915a  mov     [rbx+88h], rax
0x180009161  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009168  test    rcx, rcx
0x18000916b  jz      short loc_18000917A
0x18000916d  mov     rax, [rcx]
0x180009170  mov     rax, [rax+8]
0x180009174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009179  nop
0x18000917a  lea     rax, ??_7AudioFrameImpl@@6BIMediaFrame@Media@Windows@@@; const AudioFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180009181  mov     [rbx], rax
0x180009184  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000918b  mov     [rbx+8], rax
0x18000918f  lea     rax, ??_7AudioFrameImpl@@6BIWeakReferenceSource@@@; const AudioFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x180009196  mov     [rbx+70h], rax
0x18000919a  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIAudioFrame@Media@6@U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x1800091a1  mov     [rbx+78h], rax
0x1800091a5  lea     rax, ??_7AudioFrameImpl@@6BIAudioFrame@Media@Windows@@@; const AudioFrameImpl::`vftable'{for `Windows::Media::IAudioFrame'}
0x1800091ac  mov     [rbx+80h], rax
0x1800091b3  lea     rax, ??_7AudioFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@@; const AudioFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<IAudioFrameNative>>'}
0x1800091ba  mov     [rbx+88h], rax
0x1800091c1  lea     rdx, [rbp+57h+var_88]
0x1800091c5  lea     rcx, [rbx+0A0h]
0x1800091cc  call    ??$Make@VAudioFrameState@@AEAPEAUIMFMediaBuffer@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAudioFrameState@@@12@AEAPEAUIMFMediaBuffer@@@Z; Microsoft::WRL::Details::Make<AudioFrameState,IMFMediaBuffer * &>(IMFMediaBuffer * &)
0x1800091d1  nop
0x1800091d2  cmp     qword ptr [rbx+0A0h], 0
0x1800091da  jz      loc_180009317
0x1800091e0  mov     rcx, [rbx+60h]; string
0x1800091e4  call    cs:__imp_WindowsDeleteString
0x1800091ea  mov     [rbx+60h], r12
0x1800091ee  lea     r8, [rbx+60h]; string
0x1800091f2  mov     edx, 0Ah; length
0x1800091f7  lea     rcx, aAudioframe; "AudioFrame"
0x1800091fe  call    cs:__imp_WindowsCreateString
0x180009204  test    eax, eax
0x180009206  js      loc_180009345
0x18000920c  mov     [rbp+57h+var_88], rdi
0x180009210  test    rdi, rdi
0x180009213  jz      short loc_180009225
0x180009215  mov     rax, [rdi]
0x180009218  mov     rcx, rdi
0x18000921b  mov     rax, [rax+8]
0x18000921f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009224  nop
0x180009225  mov     [rbp+57h+var_90], r15b
0x180009229  mov     [rbp+57h+var_38], rbx
0x18000922d  cmp     [rbx+58h], rdi
0x180009231  jz      short loc_180009262
0x180009233  test    rdi, rdi
0x180009236  jz      short loc_180009248
0x180009238  mov     rax, [rdi]
0x18000923b  mov     rcx, rdi
0x18000923e  mov     rax, [rax+8]
0x180009242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009247  nop
0x180009248  mov     rcx, [rbx+58h]
0x18000924c  mov     [rbx+58h], rdi
0x180009250  test    rcx, rcx
0x180009253  jz      short loc_180009262
0x180009255  mov     rax, [rcx]
0x180009258  mov     rax, [rax+10h]
0x18000925c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009261  nop
0x180009262  mov     [rbx+30h], r15b
0x180009266  mov     rcx, rbx; this
0x180009269  call    ?ReadMfSample@MediaFrameImpl@@AEAAXXZ; MediaFrameImpl::ReadMfSample(void)
0x18000926e  lea     r8, [rbp+57h+var_90]
0x180009272  lea     rdx, [rbp+57h+var_88]
0x180009276  lea     rcx, [rbp+57h+var_78]
0x18000927a  call    ??$Make@VMediaFramePropertySetImpl@@AEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@AEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMediaFramePropertySetImpl@@@12@AEBV?$ComPtr@UIMFSample@@@12@AEA_N@Z; Microsoft::WRL::Details::Make<MediaFramePropertySetImpl,Microsoft::WRL::ComPtr<IMFSample> const &,bool &>(Microsoft::WRL::ComPtr<IMFSample> const &,bool &)
0x18000927f  mov     rcx, r12
0x180009282  lea     rdx, [rbp+57h+var_30]
0x180009286  cmp     rdx, rax
0x180009289  jz      short loc_180009291
0x18000928b  mov     rcx, [rax]
0x18000928e  mov     [rax], r12
0x180009291  mov     rax, [rbx+50h]
0x180009295  mov     [rbx+50h], rcx
0x180009299  test    rax, rax
0x18000929c  jz      short loc_1800092A6
0x18000929e  mov     rcx, rax
0x1800092a1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(void)
0x1800092a6  mov     rcx, [rbp+57h+var_78]
0x1800092aa  test    rcx, rcx
0x1800092ad  jz      short loc_1800092B8
0x1800092af  mov     [rbp+57h+var_78], r12
0x1800092b3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(void)
0x1800092b8  cmp     qword ptr [rbx+50h], 0
0x1800092bd  jz      loc_18000936C
0x1800092c3  mov     rcx, [rbp+57h+var_88]
0x1800092c7  test    rcx, rcx
0x1800092ca  jz      short loc_1800092D9
0x1800092cc  mov     rax, [rcx]
0x1800092cf  mov     rax, [rax+10h]
0x1800092d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d8  nop
0x1800092d9  mov     rcx, [r14]
0x1800092dc  test    rcx, rcx
0x1800092df  jnz     loc_18000939A
0x1800092e5  mov     [r14], rbx
0x1800092e8  mov     rbx, r12
0x1800092eb  test    rbx, rbx
0x1800092ee  jz      short loc_1800092F8
0x1800092f0  mov     rcx, rbx; Block
0x1800092f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800092f8  mov     rax, r14
0x1800092fb  lea     r11, [rsp+0B0h+var_20]
0x180009303  mov     rbx, [r11+38h]
0x180009307  mov     rsi, [r11+40h]
0x18000930b  mov     rsp, r11
0x18000930e  pop     r15
0x180009310  pop     r14
0x180009312  pop     r12
0x180009314  pop     rdi
0x180009315  pop     rbp
0x180009316  retn
0x180009317  xorps   xmm0, xmm0
0x18000931a  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18000931e  lea     rax, aBadAllocation; "bad allocation"
0x180009325  mov     qword ptr [rbp+57h+var_68], rax
0x180009329  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009330  mov     [rbp+57h+pExceptionObject], rax
0x180009334  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000933b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000933f  call    _CxxThrowException_0
0x180009345  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000934c  mov     [rbp+57h+pExceptionObject], rcx
0x180009350  mov     dword ptr [rbp+57h+var_68], eax
0x180009353  xorps   xmm0, xmm0
0x180009356  movdqu  xmmword ptr [rbp+57h+var_68+8], xmm0
0x18000935b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180009362  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009366  call    _CxxThrowException_0
0x18000936c  xorps   xmm0, xmm0
0x18000936f  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180009373  lea     rax, aBadAllocation; "bad allocation"
0x18000937a  mov     qword ptr [rbp+57h+var_68], rax
0x18000937e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009385  mov     [rbp+57h+pExceptionObject], rax
0x180009389  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009390  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009394  call    _CxxThrowException_0
0x18000939a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@7@U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>::Release(void)
0x18000939f  jmp     loc_1800092E5
```
