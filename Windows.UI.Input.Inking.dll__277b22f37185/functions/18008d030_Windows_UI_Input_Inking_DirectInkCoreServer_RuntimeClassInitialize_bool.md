# Windows::UI::Input::Inking::DirectInkCoreServer::RuntimeClassInitialize(bool)

- ea: `0x18008d030`
- end: `0x18008d417`
- name: `?RuntimeClassInitialize@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJ_N@Z`
- size: `999`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, bool)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180001c68`
- `0x180002c28`
- `0x18000346c`
- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x18001dd14`
- `0x180089af0`
- `0x18008d030`
- `0x18008e28c`
- `0x18008e3f0`
- `0x18008e8d8`
- `0x18008e934`
- `0x18008ea04`
- `0x18008eaec`
- `0x180092c7c`
- `0x180092e34`
- `0x180093164`
- `0x1800932fc`
- `0x180093420`
- `0x180093500`
- `0x1800936f8`
- `0x18009381c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d05d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d05d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008d2a9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008d2a9`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::RuntimeClassInitialize(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        char a2)
{
  DWORD CurrentThreadId; // eax
  int v5; // eax
  HRESULT AsyncInputMgr; // ebx
  __int64 v7; // rdx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, char *); // rdi
  bool v10; // dl
  _BOOL8 v11; // r8
  bool v12; // r9
  int v13; // r9d
  _OWORD *v14; // rdi
  HSTRING v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v20; // [rsp+20h] [rbp-50h]
  struct IInkDrawingAttributes *v21; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  CurrentThreadId = GetCurrentThreadId();
  v22 = 0;
  *((_DWORD *)this + 724) = CurrentThreadId;
  *((_DWORD *)this + 474) = CurrentThreadId;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.DispatcherQueue",
    0x1Fu,
    0x1Eu);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueueStatics>>(
         v24,
         &v22);
  AsyncInputMgr = v5;
  if ( v5 < 0 )
  {
    v7 = 52;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\directinkcoreserver.cpp",
      (const char *)(unsigned int)v5,
      v20);
    goto LABEL_35;
  }
  v8 = v22;
  v9 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2904);
  v5 = v9(v8, (char *)this + 2904);
  AsyncInputMgr = v5;
  if ( v5 < 0 )
  {
    v7 = 53;
    goto LABEL_5;
  }
  AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_LazyCreateAsyncInputMgr(this);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_InitializeInputConfig(this, v10, v11, v12);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_EnsureInputProcessingConfig(this);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = CDirectInkImpl::Initialize(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                    this,
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 1880),
                    *((struct Windows::UI::Input::Inking::IInkInputProcessingConfiguration **)this + 352),
                    *((_BYTE *)this + 233));
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  *((_DWORD *)this + 61) = 2;
  *((_BYTE *)this + 232) = 1;
  *(_QWORD *)((char *)this + 236) = 0;
  AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_EnsureDefaultDrawingAttributes(this);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = CDirectInkImpl::SetInputTypes((char *)this + 256, *((unsigned int *)this + 61));
  if ( (unsigned int)dword_18015B128 > 5 )
  {
    LODWORD(v21) = *((_DWORD *)this + 61);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18015B128,
      (unsigned int)&word_180136646,
      v11,
      v13,
      (__int64)&v21);
  }
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = CDirectInkImpl::SetInputConfiguration(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                    1,
                    1,
                    1);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = CDirectInkImpl::Enable(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                    *((_BYTE *)this + 232));
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  AsyncInputMgr = CDirectInkImpl::SetMultiPointerEnabled(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                    0);
  if ( AsyncInputMgr < 0 )
    goto LABEL_38;
  if ( !a2 )
  {
    AsyncInputMgr = CDirectInkImpl::SetSize((char *)this + 256, *(_QWORD *)((char *)this + 236));
    if ( AsyncInputMgr < 0 )
      goto LABEL_38;
  }
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_GetDefaultDrawingAttributes(this, &v21);
  if ( AsyncInputMgr >= 0 )
    AsyncInputMgr = CDirectInkImpl::SetDrawingAttributes(
                      (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                      v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  if ( AsyncInputMgr >= 0
    && (AsyncInputMgr = Windows::UI::Input::Inking::DirectInkCoreServer::_InitializeHighContrastConfiguration(this),
        AsyncInputMgr >= 0)
    && (v14 = (_OWORD *)((char *)this + 2868),
        AsyncInputMgr = CoCreateGuid((GUID *)((char *)this + 2868)),
        AsyncInputMgr >= 0)
    && (v15 = (HSTRING)*((_QWORD *)this + 361),
        *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *v14,
        AsyncInputMgr = CDirectInkImpl::SetTag(
                          (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 256),
                          (struct _GUID *)&hstringHeader,
                          v15),
        AsyncInputMgr >= 0) )
  {
    if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v11) )
    {
      LODWORD(v21) = AsyncInputMgr;
      hstringHeader.Reserved.Reserved1 = L"DirectInkCoreServer::RuntimeClassInitialize[Exit]";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18015B128,
        (unsigned int)byte_18013670D,
        0,
        0,
        (__int64)&hstringHeader,
        (__int64)&v21);
    }
  }
  else
  {
LABEL_38:
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v11) )
    {
      LODWORD(v21) = AsyncInputMgr;
      hstringHeader.Reserved.Reserved1 = L"DirectInkCoreServer::RuntimeClassInitialize[Exit]";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18015B128,
        (unsigned int)byte_180136675,
        0,
        0,
        (__int64)&hstringHeader,
        (__int64)&v21);
    }
    v14 = (_OWORD *)((char *)this + 2868);
  }
  if ( (unsigned int)dword_18015B128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 0x400000000000LL, v11) )
  {
    LODWORD(v21) = AsyncInputMgr;
    hstringHeader.Reserved.Reserved1 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)&word_1801366D6,
      v17,
      v18,
      (__int64)&hstringHeader,
      (__int64)&v21);
  }
LABEL_35:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return (unsigned int)AsyncInputMgr;
}

```

## disassembly

```asm
0x18008d030  mov     [rsp-28h+arg_8], rbx
0x18008d035  mov     [rsp-28h+arg_10], rsi
0x18008d03a  push    rbp
0x18008d03b  push    rdi
0x18008d03c  push    r12
0x18008d03e  push    r14
0x18008d040  push    r15
0x18008d042  mov     rbp, rsp
0x18008d045  sub     rsp, 70h
0x18008d049  mov     rax, cs:__security_cookie
0x18008d050  xor     rax, rsp
0x18008d053  mov     [rbp+var_10], rax
0x18008d057  mov     r12b, dl
0x18008d05a  mov     r14, rcx
0x18008d05d  call    cs:__imp_GetCurrentThreadId
0x18008d063  mov     r9d, 1Eh; unsigned int
0x18008d069  mov     [rbp+var_38], 0
0x18008d071  lea     r15, [r14+758h]
0x18008d078  mov     [r14+0B50h], eax
0x18008d07f  lea     rdx, ?RuntimeClass_Windows_System_DispatcherQueue@@3QBGB; "Windows.System.DispatcherQueue"
0x18008d086  mov     [r15+10h], eax
0x18008d08a  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008d08e  mov     [rbp+var_18], 0
0x18008d096  lea     r8d, [r9+1]; unsigned int
0x18008d09a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008d09f  mov     rcx, [rbp+var_18]
0x18008d0a3  lea     rdx, [rbp+var_38]
0x18008d0a7  call    ??$GetActivationFactory@V?$ComPtr@UIDispatcherQueueStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDispatcherQueueStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueueStatics>>)
0x18008d0ac  mov     ebx, eax
0x18008d0ae  test    eax, eax
0x18008d0b0  jns     short loc_18008D0B9
0x18008d0b2  mov     edx, 34h ; '4'
0x18008d0b7  jmp     short loc_18008D0EC
0x18008d0b9  mov     rsi, [rbp+var_38]
0x18008d0bd  lea     rbx, [r14+0B58h]
0x18008d0c4  mov     rcx, rbx
0x18008d0c7  mov     rax, [rsi]
0x18008d0ca  mov     rdi, [rax+30h]
0x18008d0ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d0d3  mov     rdx, rbx
0x18008d0d6  mov     rcx, rsi
0x18008d0d9  mov     rax, rdi
0x18008d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d0e1  mov     ebx, eax
0x18008d0e3  test    eax, eax
0x18008d0e5  jns     short loc_18008D104
0x18008d0e7  mov     edx, 35h ; '5'; void *
0x18008d0ec  mov     rcx, [rbp+28h]; this
0x18008d0f0  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18008d0f7  mov     r9d, eax; char *
0x18008d0fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d0ff  jmp     loc_18008D3E7
0x18008d104  mov     rcx, r14; this
0x18008d107  call    ?_LazyCreateAsyncInputMgr@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Inking::DirectInkCoreServer::_LazyCreateAsyncInputMgr(void)
0x18008d10c  mov     ebx, eax
0x18008d10e  test    eax, eax
0x18008d110  js      loc_18008D33D
0x18008d116  mov     rcx, r14; this
0x18008d119  call    ?_InitializeInputConfig@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJ_N00@Z; Windows::UI::Input::Inking::DirectInkCoreServer::_InitializeInputConfig(bool,bool,bool)
0x18008d11e  mov     ebx, eax
0x18008d120  test    eax, eax
0x18008d122  js      loc_18008D33D
0x18008d128  mov     rcx, r14; this
0x18008d12b  call    ?_EnsureInputProcessingConfig@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Inking::DirectInkCoreServer::_EnsureInputProcessingConfig(void)
0x18008d130  mov     ebx, eax
0x18008d132  test    eax, eax
0x18008d134  js      loc_18008D33D
0x18008d13a  mov     al, [r14+0E9h]
0x18008d141  lea     rsi, [r14+100h]
0x18008d148  mov     r9, [r14+0B00h]; struct Windows::UI::Input::Inking::IInkInputProcessingConfiguration *
0x18008d14f  mov     rcx, rsi; this
0x18008d152  mov     r8, r15; struct CCallbackHelper *
0x18008d155  mov     [rsp+70h+var_50], al; bool
0x18008d159  mov     rdx, r14; struct Windows::UI::Input::Inking::IInkPresenter *
0x18008d15c  call    ?Initialize@CDirectInkImpl@@QEAAJPEAUIInkPresenter@Inking@Input@UI@Windows@@PEAVCCallbackHelper@@PEAUIInkInputProcessingConfiguration@3456@_N@Z; CDirectInkImpl::Initialize(Windows::UI::Input::Inking::IInkPresenter *,CCallbackHelper *,Windows::UI::Input::Inking::IInkInputProcessingConfiguration *,bool)
0x18008d161  mov     ebx, eax
0x18008d163  test    eax, eax
0x18008d165  js      loc_18008D33D
0x18008d16b  mov     rcx, r14; this
0x18008d16e  mov     dword ptr [r14+0F4h], 2
0x18008d179  mov     byte ptr [r14+0E8h], 1
0x18008d181  mov     qword ptr [r14+0ECh], 0
0x18008d18c  call    ?_EnsureDefaultDrawingAttributes@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Inking::DirectInkCoreServer::_EnsureDefaultDrawingAttributes(void)
0x18008d191  mov     ebx, eax
0x18008d193  test    eax, eax
0x18008d195  js      loc_18008D33D
0x18008d19b  mov     edx, [r14+0F4h]
0x18008d1a2  mov     rcx, rsi
0x18008d1a5  call    ?SetInputTypes@CDirectInkImpl@@QEAAJW4CoreInputDeviceTypes@Core@UI@Windows@@@Z; CDirectInkImpl::SetInputTypes(Windows::UI::Core::CoreInputDeviceTypes)
0x18008d1aa  mov     ebx, eax
0x18008d1ac  mov     eax, cs:dword_18015B128
0x18008d1b2  cmp     eax, 5
0x18008d1b5  jbe     short loc_18008D1DD
0x18008d1b7  mov     eax, [r14+0F4h]
0x18008d1be  lea     rdx, word_180136646
0x18008d1c5  mov     dword ptr [rbp+var_40], eax
0x18008d1c8  lea     rcx, dword_18015B128
0x18008d1cf  lea     rax, [rbp+var_40]
0x18008d1d3  mov     qword ptr [rsp+70h+var_50], rax
0x18008d1d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d1dd  test    ebx, ebx
0x18008d1df  js      loc_18008D33D
0x18008d1e5  mov     r9b, 1; bool
0x18008d1e8  mov     rcx, rsi; this
0x18008d1eb  mov     r8b, r9b; bool
0x18008d1ee  mov     dl, r9b; bool
0x18008d1f1  call    ?SetInputConfiguration@CDirectInkImpl@@QEAAJ_N00@Z; CDirectInkImpl::SetInputConfiguration(bool,bool,bool)
0x18008d1f6  mov     ebx, eax
0x18008d1f8  test    eax, eax
0x18008d1fa  js      loc_18008D33D
0x18008d200  mov     dl, [r14+0E8h]; bool
0x18008d207  mov     rcx, rsi; this
0x18008d20a  call    ?Enable@CDirectInkImpl@@QEAAJ_N@Z; CDirectInkImpl::Enable(bool)
0x18008d20f  mov     ebx, eax
0x18008d211  test    eax, eax
0x18008d213  js      loc_18008D33D
0x18008d219  xor     edx, edx; bool
0x18008d21b  mov     rcx, rsi; this
0x18008d21e  call    ?SetMultiPointerEnabled@CDirectInkImpl@@QEAAJ_N@Z; CDirectInkImpl::SetMultiPointerEnabled(bool)
0x18008d223  mov     ebx, eax
0x18008d225  test    eax, eax
0x18008d227  js      loc_18008D33D
0x18008d22d  test    r12b, r12b
0x18008d230  jnz     short loc_18008D24B
0x18008d232  mov     rdx, [r14+0ECh]
0x18008d239  mov     rcx, rsi
0x18008d23c  call    ?SetSize@CDirectInkImpl@@QEAAJUSize@Foundation@Windows@@@Z; CDirectInkImpl::SetSize(Windows::Foundation::Size)
0x18008d241  mov     ebx, eax
0x18008d243  test    eax, eax
0x18008d245  js      loc_18008D33D
0x18008d24b  lea     rcx, [rbp+var_40]
0x18008d24f  mov     [rbp+var_40], 0
0x18008d257  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d25c  lea     rdx, [rbp+var_40]; struct IInkDrawingAttributes **
0x18008d260  mov     rcx, r14; this
0x18008d263  call    ?_GetDefaultDrawingAttributes@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJPEAPEAUIInkDrawingAttributes@2345@@Z; Windows::UI::Input::Inking::DirectInkCoreServer::_GetDefaultDrawingAttributes(Windows::UI::Input::Inking::IInkDrawingAttributes * *)
0x18008d268  mov     ebx, eax
0x18008d26a  test    eax, eax
0x18008d26c  js      short loc_18008D27C
0x18008d26e  mov     rdx, [rbp+var_40]; struct IInkDrawingAttributes *
0x18008d272  mov     rcx, rsi; this
0x18008d275  call    ?SetDrawingAttributes@CDirectInkImpl@@QEAAJPEAUIInkDrawingAttributes@Inking@Input@UI@Windows@@@Z; CDirectInkImpl::SetDrawingAttributes(Windows::UI::Input::Inking::IInkDrawingAttributes *)
0x18008d27a  mov     ebx, eax
0x18008d27c  lea     rcx, [rbp+var_40]
0x18008d280  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d285  test    ebx, ebx
0x18008d287  js      loc_18008D33D
0x18008d28d  mov     rcx, r14; this
0x18008d290  call    ?_InitializeHighContrastConfiguration@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Inking::DirectInkCoreServer::_InitializeHighContrastConfiguration(void)
0x18008d295  mov     ebx, eax
0x18008d297  test    eax, eax
0x18008d299  js      loc_18008D33D
0x18008d29f  lea     rdi, [r14+0B34h]
0x18008d2a6  mov     rcx, rdi; pguid
0x18008d2a9  call    cs:__imp_CoCreateGuid
0x18008d2af  mov     ebx, eax
0x18008d2b1  test    eax, eax
0x18008d2b3  js      loc_18008D33D
0x18008d2b9  movups  xmm0, xmmword ptr [rdi]
0x18008d2bc  mov     r8, [r14+0B48h]; HSTRING
0x18008d2c3  lea     rdx, [rbp+hstringHeader]; struct _GUID
0x18008d2c7  mov     rcx, rsi; this
0x18008d2ca  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18008d2cf  call    ?SetTag@CDirectInkImpl@@QEAAJU_GUID@@PEAUHSTRING__@@@Z; CDirectInkImpl::SetTag(_GUID,HSTRING__ *)
0x18008d2d4  mov     ebx, eax
0x18008d2d6  test    eax, eax
0x18008d2d8  js      short loc_18008D33D
0x18008d2da  mov     eax, cs:dword_18015B128
0x18008d2e0  cmp     eax, 4
0x18008d2e3  jbe     loc_18008D39D
0x18008d2e9  mov     edx, 1
0x18008d2ee  lea     rcx, dword_18015B128
0x18008d2f5  call    _tlgKeywordOn
0x18008d2fa  test    al, al
0x18008d2fc  jz      loc_18008D39D
0x18008d302  lea     rax, aDirectinkcores_7; "DirectInkCoreServer::RuntimeClassInitia"...
0x18008d309  mov     dword ptr [rbp+var_40], ebx
0x18008d30c  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18008d310  lea     rdx, byte_18013670D
0x18008d317  lea     rax, [rbp+var_40]
0x18008d31b  xor     r9d, r9d
0x18008d31e  mov     [rsp+70h+var_48], rax
0x18008d323  lea     rcx, dword_18015B128
0x18008d32a  lea     rax, [rbp+hstringHeader]
0x18008d32e  xor     r8d, r8d
0x18008d331  mov     qword ptr [rsp+70h+var_50], rax
0x18008d336  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008d33b  jmp     short loc_18008D39D
0x18008d33d  mov     eax, cs:dword_18015B128
0x18008d343  cmp     eax, 2
0x18008d346  jbe     short loc_18008D396
0x18008d348  mov     edx, 1
0x18008d34d  lea     rcx, dword_18015B128
0x18008d354  call    _tlgKeywordOn
0x18008d359  test    al, al
0x18008d35b  jz      short loc_18008D396
0x18008d35d  lea     rax, aDirectinkcores_7; "DirectInkCoreServer::RuntimeClassInitia"...
0x18008d364  mov     dword ptr [rbp+var_40], ebx
0x18008d367  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18008d36b  lea     rdx, byte_180136675
0x18008d372  lea     rax, [rbp+var_40]
0x18008d376  xor     r9d, r9d
0x18008d379  mov     [rsp+70h+var_48], rax
0x18008d37e  lea     rcx, dword_18015B128
0x18008d385  lea     rax, [rbp+hstringHeader]
0x18008d389  xor     r8d, r8d
0x18008d38c  mov     qword ptr [rsp+70h+var_50], rax
0x18008d391  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008d396  lea     rdi, [r14+0B34h]
0x18008d39d  mov     eax, cs:dword_18015B128
0x18008d3a3  cmp     eax, 5
0x18008d3a6  jbe     short loc_18008D3E7
0x18008d3a8  mov     rdx, 400000000000h
0x18008d3b2  lea     rcx, dword_18015B128
0x18008d3b9  call    _tlgKeywordOn
0x18008d3be  test    al, al
0x18008d3c0  jz      short loc_18008D3E7
0x18008d3c2  lea     rax, [rbp+var_40]
0x18008d3c6  mov     dword ptr [rbp+var_40], ebx
0x18008d3c9  mov     [rsp+70h+var_48], rax
0x18008d3ce  lea     rdx, word_1801366D6
0x18008d3d5  lea     rax, [rbp+hstringHeader]
0x18008d3d9  mov     qword ptr [rbp+hstringHeader.Reserved], rdi
0x18008d3dd  mov     qword ptr [rsp+70h+var_50], rax
0x18008d3e2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008d3e7  lea     rcx, [rbp+var_38]
0x18008d3eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d3f0  mov     eax, ebx
0x18008d3f2  mov     rcx, [rbp+var_10]
0x18008d3f6  xor     rcx, rsp; StackCookie
0x18008d3f9  call    __security_check_cookie
0x18008d3fe  lea     r11, [rsp+70h+var_s0]
0x18008d403  mov     rbx, [r11+38h]
0x18008d407  mov     rsi, [r11+40h]
0x18008d40b  mov     rsp, r11
0x18008d40e  pop     r15
0x18008d410  pop     r14
0x18008d412  pop     r12
0x18008d414  pop     rdi
0x18008d415  pop     rbp
0x18008d416  retn
```
