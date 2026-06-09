# ControllerWatcher::Create(ControllerWatcher * *)

- ea: `0x180045090`
- end: `0x180045b11`
- name: `?Create@ControllerWatcher@@SAJPEAPEAV1@@Z`
- size: `2689`
- prototype: `__int64 __fastcall(struct ControllerWatcher **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cf1c`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18002cce8`
- `0x18003fe64`
- `0x18004458c`
- `0x180045090`
- `0x1800465e0`
- `0x18004c8a5`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800450d4`
- `ntdll!RtlAllocateHeap` at `0x1800452f2`
- `ntdll!RtlAllocateHeap` at `0x1800450d4`
- `ntdll!RtlAllocateHeap` at `0x1800452f2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800451ed`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800451ed`
- `ntdll!RtlPublishWnfStateData` at `0x18004513e`
- `ntdll!RtlPublishWnfStateData` at `0x18004513e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004510a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004510a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004515f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004515f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004524e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180045456`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004524e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180045456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004522b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004522b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045430`

## string_xrefs

- `0x1800451ab`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x1800452ac`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x1800453a5`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x1800454ec`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x18004559c`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x180045634`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x180045729`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x1800457c9`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x1800459e0`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`
- `0x180045aa4`: `onecore\xbox\gameinput\xboxgipservices\ControllerWatcher.cpp`

## pseudocode

```c
__int64 __fastcall ControllerWatcher::Create(struct ControllerWatcher **a1)
{
  struct _RTL_CRITICAL_SECTION *Heap; // rsi
  int v2; // r8d
  int v3; // r9d
  int v4; // ebx
  int v5; // r9d
  int v6; // ecx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  int v11; // r9d
  int v12; // r8d
  int v13; // ecx
  __int16 *v14; // rdx
  struct Windows::Gaming::Input::IRawGameController *v15; // rax
  int v16; // r8d
  int v17; // r9d
  struct Windows::Gaming::Input::IRawGameController *v18; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v19; // rcx
  __int64 v20; // rdx
  int v21; // edi
  __int64 v22; // r8
  int v23; // r9d
  const struct std::nothrow_t *v24; // rdx
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  HANDLE *p_LockSemaphore; // r14
  const struct std::nothrow_t *v30; // rdx
  int v31; // r8d
  int v32; // r9d
  int v33; // r9d
  int v34; // ecx
  int *v35; // rdx
  struct Windows::Gaming::Input::IRawGameController *v36; // rdi
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // r9d
  int v40; // r15d
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // r9d
  int v44; // r14d
  int v45; // ecx
  __int16 *v46; // rdx
  __int64 v47; // rcx
  unsigned int v48; // r14d
  int v49; // r9d
  struct Windows::Gaming::Input::IRawGameController *v50; // rcx
  __int64 v51; // rcx
  int v52; // ecx
  __int16 *v53; // rdx
  struct Windows::Gaming::Input::IRawGameController *v54; // rcx
  __int64 v55; // rcx
  int v56; // [rsp+40h] [rbp-29h] BYREF
  int v57; // [rsp+44h] [rbp-25h] BYREF
  struct Windows::Gaming::Input::IRawGameController *v58; // [rsp+48h] [rbp-21h] BYREF
  __int64 v59; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v60; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v61; // [rsp+5Ch] [rbp-Dh] BYREF
  const char *v62; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF

  qword_180069878 = 0;
  Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xC0u);
  if ( !Heap )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v57 = -2147024882;
      v62 = "onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
      v56 = 56;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&dword_180062B74,
        v2,
        v3,
        (__int64)&v62,
        (__int64)&v56,
        (__int64)&v57);
    }
    return 2147942414LL;
  }
  Heap->DebugInfo = 0;
  *(_QWORD *)&Heap->LockCount = 0;
  Heap->OwningThread = 0;
  Heap->LockSemaphore = 0;
  Heap->SpinCount = 0;
  InitializeCriticalSectionEx(Heap + 1, 0, 0);
  memset_0(&Heap[2].OwningThread, 0, 0x58u);
  RtlPublishWnfStateData(WNF_ISM_GAMECONTROLLER_ZEPHYRUS_FAULT, 0, &Heap[2].OwningThread, 88, 0);
  LOBYTE(Heap[4].LockSemaphore) = 0;
  *(_QWORD *)&Heap[2].LockCount = Heap + 2;
  Heap[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Heap[2];
  v4 = RoInitialize(1);
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v56 = v4;
      v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
      v57 = 58;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_180062C7B,
        qword_180069018,
        v5,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56);
    }
    goto LABEL_27;
  }
  LOBYTE(Heap[4].LockSemaphore) = 1;
  v61 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v61, 0);
  if ( v61 <= 0xD )
  {
    v6 = 8778;
    if ( _bittest(&v6, v61) )
    {
      string = 0;
      v7 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
      if ( v7 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
        JUMPOUT(0x180045B10LL);
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_1292a652_a1b2_483b_ae29_3d90012c77c1, &Heap->SpinCount);
      string = 0;
      v4 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_27;
        v12 = qword_180069018;
        v13 = qword_180069010;
        if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
          goto LABEL_27;
        v56 = 78;
        v14 = &word_1800633B6;
        goto LABEL_15;
      }
      v15 = (struct Windows::Gaming::Input::IRawGameController *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v18 = v15;
      if ( v15 )
      {
        v19 = Microsoft::WRL::Details::ModuleBase::module_;
        *(_QWORD *)v15 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileActivatedEventArgs *>::`vftable';
        *(_QWORD *)v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserProfileEventArgs *>>::`vftable';
        *((_DWORD *)v15 + 3) = 1;
        if ( v19 )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v19 + 8LL))(v19);
        *((_QWORD *)v18 + 2) = Heap;
        *((_QWORD *)v18 + 3) = ControllerWatcher::OnUserProfileChanged;
        *(_QWORD *)v18 = ___7__DelegateInvokeHelper_U__IEventHandler_PEAVUserProfileEventArgs_Internal_System_Windows___Foundation_Windows__V_lambda_1___1____Callback_U__IEventHandler_PEAVUserProfileEventArgs_Internal_System_Windows___Foundation_Windows__VControllerWatcher__PEAUIInspectable__PEAUIUserProfileEventArgs_Internal_System_3__WRL_Microsoft__YA_AV__ComPtr_U__IEventHandler_PEAVUserProfileEventArgs_Internal_System_Windows___Foundation_Windows___56_PEAVControllerWatcher__P88_EAAJPEAUIInspectable__PEAUIUserProfileEventArgs_Internal_System_3__Z_Z__0_0PEAU9_PEAUIUserProfileEventArgs_Internal_System_3____DelegateArgTraits_P8__IEventHandler_impl_U__AggregateType_PEAVUserProfileEventArgs_Internal_System_Windows__PEAUIUserProfileEventArgs_234__Internal_Foundation_Windows___Foundation_Windows__EAAJPEAUIInspectable__PEAUIUserProfileEventArgs_Internal_System_3__Z_Details_WRL_Microsoft__6B_;
        v21 = (*(__int64 (__fastcall **)(ULONG_PTR, struct Windows::Gaming::Input::IRawGameController *, HANDLE *))(*(_QWORD *)Heap->SpinCount + 48LL))(
                Heap->SpinCount,
                v18,
                &Heap->OwningThread);
        if ( v21 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 )
          {
            v22 = qword_180069018;
            v20 = 2048;
            if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
            {
              v57 = v21;
              v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\Cont"
                                                                         "rollerWatcher.cpp";
              v56 = 87;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_180069010,
                (unsigned int)byte_180063061,
                qword_180069018,
                v23,
                (__int64)&v58,
                (__int64)&v56,
                (__int64)&v57);
            }
          }
LABEL_25:
          (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v18 + 16LL))(
            v18,
            v20,
            v22);
LABEL_26:
          v4 = v21;
LABEL_27:
          ControllerWatcher::~ControllerWatcher((ControllerWatcher *)Heap);
          operator delete(Heap, v24);
          return (unsigned int)v4;
        }
        (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v18 + 16LL))(v18);
        goto LABEL_29;
      }
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x800) != 0
        && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v57 = -2147024882;
        v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
        v56 = 84;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)&unk_180063168,
          v16,
          v17,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v57);
      }
      ControllerWatcher::~ControllerWatcher((ControllerWatcher *)Heap);
      operator delete(Heap, v30);
      return 2147942414LL;
    }
  }
LABEL_29:
  string = 0;
  v26 = WindowsCreateStringReference(L"Windows.Gaming.Input.RawGameController", 0x26u, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    __debugbreak();
  }
  p_LockSemaphore = &Heap->LockSemaphore;
  v4 = RoGetActivationFactory(string, &GUID_eb8d0792_e95a_4b19_afc7_0a59f8bf759e, &Heap->LockSemaphore);
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_27;
    v12 = qword_180069018;
    v13 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_27;
    v56 = 93;
    v14 = (__int16 *)&byte_180063577;
LABEL_15:
    v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
    v57 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (_DWORD)v14,
      v12,
      v11,
      (__int64)&v58,
      (__int64)&v56,
      (__int64)&v57);
    goto LABEL_27;
  }
  Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(
    &v58,
    Heap,
    ControllerWatcher::OnControllerAdded);
  v18 = v58;
  if ( !v58 )
  {
    v21 = -2147024882;
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v57 = -2147024882;
      v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
      v56 = 99;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_1800633F3,
        v31,
        v32,
        (__int64)&v58,
        (__int64)&v56,
        (__int64)&v57);
    }
    goto LABEL_26;
  }
  v21 = (*(__int64 (__fastcall **)(HANDLE, struct Windows::Gaming::Input::IRawGameController *, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)*p_LockSemaphore + 48LL))(
          *p_LockSemaphore,
          v58,
          Heap);
  if ( v21 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v22 = qword_180069018;
      v20 = 2048;
      v34 = qword_180069010;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = 102;
        v35 = &dword_180062DAC;
LABEL_50:
        v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
        v57 = v21;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v34,
          (_DWORD)v35,
          v22,
          v33,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v57);
        goto LABEL_51;
      }
    }
    goto LABEL_51;
  }
  Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(
    &v58,
    Heap,
    ControllerWatcher::OnControllerRemoved);
  v36 = v58;
  if ( !v58 )
  {
    v21 = -2147024882;
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v34 = qword_180069018;
      v20 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = 108;
        v35 = &dword_180062FD4;
        goto LABEL_50;
      }
    }
LABEL_51:
    if ( !v18 )
      goto LABEL_26;
    goto LABEL_25;
  }
  v40 = (*(__int64 (__fastcall **)(HANDLE, struct Windows::Gaming::Input::IRawGameController *, LONG *))(*(_QWORD *)*p_LockSemaphore + 64LL))(
          *p_LockSemaphore,
          v58,
          &Heap->LockCount);
  if ( v40 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v38 = qword_180069018;
      v37 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v57 = v40;
        v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
        v56 = 111;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)word_180062F5A,
          qword_180069018,
          v39,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v57);
      }
    }
LABEL_107:
    if ( v36 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v36 + 16LL))(
        v36,
        v37,
        v38);
    if ( v18 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v18 + 16LL))(
        v18,
        v37,
        v38);
    v4 = v40;
    goto LABEL_27;
  }
  v59 = 0;
  v44 = (*(__int64 (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)*p_LockSemaphore + 80LL))(*p_LockSemaphore, &v59);
  if ( v44 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_69;
    v42 = qword_180069018;
    v41 = 2048;
    v45 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_69;
    v56 = 114;
    v46 = (__int16 *)byte_180062EA3;
LABEL_68:
    v58 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
    v57 = v44;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v45,
      (_DWORD)v46,
      v42,
      v43,
      (__int64)&v58,
      (__int64)&v56,
      (__int64)&v57);
LABEL_69:
    v47 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v47 + 16LL))(v47, v41, v42);
    }
    if ( v36 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v36 + 16LL))(
        v36,
        v41,
        v42);
    if ( v18 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v18 + 16LL))(
        v18,
        v41,
        v42);
    v4 = v44;
    goto LABEL_27;
  }
  v60 = 0;
  v44 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v59 + 56LL))(v59, &v60);
  if ( v44 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_69;
    v42 = qword_180069018;
    v41 = 2048;
    v45 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_69;
    v56 = 124;
    v46 = &word_18006309E;
    goto LABEL_68;
  }
  v48 = 0;
  if ( v60 )
  {
    while ( 1 )
    {
      v58 = 0;
      v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Gaming::Input::IRawGameController **))(*(_QWORD *)v59 + 48LL))(
              v59,
              v48,
              &v58);
      if ( v40 < 0 )
        break;
      v40 = ControllerWatcher::OnControllerAdded((ControllerWatcher *)Heap, 0, v58);
      if ( v40 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v52 = qword_180069018;
          v37 = 2048;
          if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
          {
            v56 = 129;
            v53 = (__int16 *)&byte_180063987;
LABEL_102:
            v62 = "onecore\\xbox\\gameinput\\xboxgipservices\\ControllerWatcher.cpp";
            v57 = v40;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v52,
              (_DWORD)v53,
              v38,
              v49,
              (__int64)&v62,
              (__int64)&v56,
              (__int64)&v57);
            goto LABEL_103;
          }
        }
        goto LABEL_103;
      }
      v50 = v58;
      if ( v58 )
      {
        v58 = 0;
        (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v50 + 16LL))(v50);
      }
      if ( ++v48 >= v60 )
        goto LABEL_87;
    }
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v52 = qword_180069018;
      v37 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = 128;
        v53 = &word_18006362E;
        goto LABEL_102;
      }
    }
LABEL_103:
    v54 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    goto LABEL_107;
  }
LABEL_87:
  v51 = v59;
  qword_180069878 = Heap;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  if ( v36 )
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v18 )
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v18 + 16LL))(v18);
  return 0;
}

```

## disassembly

```asm
0x180045090  push    rbp
0x180045092  push    rbx
0x180045093  push    rsi
0x180045094  push    rdi
0x180045095  push    r12
0x180045097  push    r14
0x180045099  push    r15
0x18004509b  lea     rbp, [rsp-27h]
0x1800450a0  sub     rsp, 90h
0x1800450a7  mov     rax, cs:__security_cookie
0x1800450ae  xor     rax, rsp
0x1800450b1  mov     [rbp+57h+var_38], rax
0x1800450b5  xor     r12d, r12d
0x1800450b8  xor     edx, edx; Flags
0x1800450ba  mov     cs:qword_180069878, r12
0x1800450c1  mov     r8d, 0C0h; Size
0x1800450c7  mov     rcx, gs:60h
0x1800450d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800450d4  call    cs:__imp_RtlAllocateHeap
0x1800450db  nop     dword ptr [rax+rax+00h]
0x1800450e0  mov     rsi, rax
0x1800450e3  test    rax, rax
0x1800450e6  jz      loc_180045A71
0x1800450ec  xor     eax, eax
0x1800450ee  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800450f2  mov     [rsi], rax
0x1800450f5  xor     r8d, r8d; Flags
0x1800450f8  mov     [rsi+8], rax
0x1800450fc  xor     edx, edx; dwSpinCount
0x1800450fe  mov     [rsi+10h], rax
0x180045102  mov     [rsi+18h], r12
0x180045106  mov     [rsi+20h], r12
0x18004510a  call    cs:__imp_InitializeCriticalSectionEx
0x180045111  nop     dword ptr [rax+rax+00h]
0x180045116  lea     edi, [r12+58h]
0x18004511b  xor     edx, edx; Val
0x18004511d  mov     r8d, edi; Size
0x180045120  lea     rcx, [rsi+60h]; void *
0x180045124  call    memset_0
0x180045129  mov     rcx, cs:WNF_ISM_GAMECONTROLLER_ZEPHYRUS_FAULT
0x180045130  lea     r8, [rsi+60h]
0x180045134  mov     r9d, edi
0x180045137  mov     [rsp+0C0h+var_A0], r12
0x18004513c  xor     edx, edx
0x18004513e  call    cs:__imp_RtlPublishWnfStateData
0x180045145  nop     dword ptr [rax+rax+00h]
0x18004514a  lea     rax, [rsi+50h]
0x18004514e  mov     [rsi+0B8h], r12b
0x180045155  lea     ecx, [rdi-57h]
0x180045158  mov     [rax+8], rax
0x18004515c  mov     [rax], rax
0x18004515f  call    cs:__imp_RoInitialize
0x180045166  nop     dword ptr [rax+rax+00h]
0x18004516b  mov     ebx, eax
0x18004516d  test    eax, eax
0x18004516f  jns     short loc_1800451D9
0x180045171  mov     ecx, cs:dword_180069000
0x180045177  cmp     ecx, 2
0x18004517a  jbe     loc_1800453F2
0x180045180  mov     r8, cs:qword_180069018
0x180045187  mov     edx, 800h
0x18004518c  mov     rcx, cs:qword_180069010
0x180045193  test    rdx, rcx
0x180045196  jz      loc_1800453F2
0x18004519c  mov     rax, r8
0x18004519f  and     rax, rdx
0x1800451a2  cmp     rax, r8
0x1800451a5  jnz     loc_1800453F2
0x1800451ab  lea     rax, aOnecoreXboxGam_30; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800451b2  mov     [rbp+57h+var_80], ebx
0x1800451b5  mov     [rbp+57h+var_78], rax
0x1800451b9  lea     rdx, byte_180062C7B
0x1800451c0  lea     rax, [rbp+57h+var_80]
0x1800451c4  mov     [rbp+57h+var_7C], 3Ah ; ':'
0x1800451cb  mov     [rsp+0C0h+var_90], rax
0x1800451d0  lea     rax, [rbp+57h+var_7C]
0x1800451d4  jmp     loc_1800452C7
0x1800451d9  mov     byte ptr [rsi+0B8h], 1
0x1800451e0  lea     rdx, [rbp+57h+var_64]
0x1800451e4  xor     r8d, r8d
0x1800451e7  mov     [rbp+57h+var_64], r12d
0x1800451eb  xor     ecx, ecx
0x1800451ed  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800451f4  nop     dword ptr [rax+rax+00h]
0x1800451f9  mov     eax, [rbp+57h+var_64]
0x1800451fc  cmp     eax, 0Dh
0x1800451ff  ja      loc_180045418
0x180045205  mov     ecx, 224Ah
0x18004520a  bt      ecx, eax
0x18004520d  jnb     loc_180045418
0x180045213  lea     r9, [rbp+57h+string]; string
0x180045217  mov     [rbp+57h+string], r12
0x18004521b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004521f  mov     edx, 23h ; '#'; length
0x180045224  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18004522b  call    cs:__imp_WindowsCreateStringReference
0x180045232  nop     dword ptr [rax+rax+00h]
0x180045237  test    eax, eax
0x180045239  js      loc_180045B09
0x18004523f  mov     rcx, [rbp+57h+string]
0x180045243  lea     r8, [rsi+20h]
0x180045247  lea     rdx, _GUID_1292a652_a1b2_483b_ae29_3d90012c77c1
0x18004524e  call    cs:__imp_RoGetActivationFactory
0x180045255  nop     dword ptr [rax+rax+00h]
0x18004525a  mov     [rbp+57h+string], r12
0x18004525e  mov     ebx, eax
0x180045260  test    eax, eax
0x180045262  jns     short loc_1800452DF
0x180045264  mov     ecx, cs:dword_180069000
0x18004526a  cmp     ecx, 2
0x18004526d  jbe     loc_1800453F2
0x180045273  mov     r8, cs:qword_180069018
0x18004527a  mov     edx, 800h
0x18004527f  mov     rcx, cs:qword_180069010
0x180045286  test    rdx, rcx
0x180045289  jz      loc_1800453F2
0x18004528f  mov     rax, r8
0x180045292  and     rax, rdx
0x180045295  cmp     rax, r8
0x180045298  jnz     loc_1800453F2
0x18004529e  mov     [rbp+57h+var_80], 4Eh ; 'N'
0x1800452a5  lea     rdx, word_1800633B6
0x1800452ac  lea     rax, aOnecoreXboxGam_30; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800452b3  mov     [rbp+57h+var_78], rax
0x1800452b7  lea     rax, [rbp+57h+var_7C]
0x1800452bb  mov     [rsp+0C0h+var_90], rax
0x1800452c0  lea     rax, [rbp+57h+var_80]
0x1800452c4  mov     [rbp+57h+var_7C], ebx
0x1800452c7  mov     [rsp+0C0h+var_98], rax
0x1800452cc  lea     rax, [rbp+57h+var_78]
0x1800452d0  mov     [rsp+0C0h+var_A0], rax
0x1800452d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800452da  jmp     loc_1800453F2
0x1800452df  mov     rcx, gs:60h
0x1800452e8  xor     edx, edx; Flags
0x1800452ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800452ee  lea     r8d, [rdx+20h]; Size
0x1800452f2  call    cs:__imp_RtlAllocateHeap
0x1800452f9  nop     dword ptr [rax+rax+00h]
0x1800452fe  mov     rbx, rax
0x180045301  test    rax, rax
0x180045304  jz      loc_1800454B9
0x18004530a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180045311  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@PEAVCoreKeyboardInputProfileActivatedEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileActivatedEventArgs *>::`vftable'
0x180045318  mov     [rbx], rax
0x18004531b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVUserProfileEventArgs@Internal@System@Windows@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserProfileEventArgs *>>::`vftable'
0x180045322  mov     [rbx], rax
0x180045325  mov     dword ptr [rbx+0Ch], 1
0x18004532c  test    rcx, rcx
0x18004532f  jz      short loc_18004533D
0x180045331  mov     rdx, [rcx]
0x180045334  mov     rax, [rdx+8]
0x180045338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004533d  mov     [rbx+10h], rsi
0x180045341  lea     rax, ?OnUserProfileChanged@ControllerWatcher@@AEAAJPEAUIInspectable@@PEAUIUserProfileEventArgs@Internal@System@Windows@@@Z; ControllerWatcher::OnUserProfileChanged(IInspectable *,Windows::System::Internal::IUserProfileEventArgs *)
0x180045348  mov     [rbx+18h], rax
0x18004534c  lea     r8, [rsi+10h]
0x180045350  lea     rax, ??_7?$DelegateInvokeHelper@U?$IEventHandler@PEAVUserProfileEventArgs@Internal@System@Windows@@@Foundation@Windows@@V_lambda_1_@?1???$Callback@U?$IEventHandler@PEAVUserProfileEventArgs@Internal@System@Windows@@@Foundation@Windows@@VControllerWatcher@@PEAUIInspectable@@PEAUIUserProfileEventArgs@Internal@System@3@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAVUserProfileEventArgs@Internal@System@Windows@@@Foundation@Windows@@@56@PEAVControllerWatcher@@P88@EAAJPEAUIInspectable@@PEAUIUserProfileEventArgs@Internal@System@3@@Z@Z@$0?0PEAU9@PEAUIUserProfileEventArgs@Internal@System@3@@?$DelegateArgTraits@P8?$IEventHandler_impl@U?$AggregateType@PEAVUserProfileEventArgs@Internal@System@Windows@@PEAUIUserProfileEventArgs@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAUIInspectable@@PEAUIUserProfileEventArgs@Internal@System@3@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::Internal::UserProfileEventArgs *,Windows::System::Internal::IUserProfileEventArgs *>>::*)(IInspectable *,Windows::System::Internal::IUserProfileEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::IEventHandler<Windows::System::Internal::UserProfileEventArgs *>,`Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::System::Internal::UserProfileEventArgs *>,ControllerWatcher,IInspectable *,Windows::System::Internal::IUserProfileEventArgs *>(ControllerWatcher *,long (ControllerWatcher::*)(IInspectable *,Windows::System::Internal::IUserProfileEventArgs *))'::`2'::_lambda_1_,-1,IInspectable *,Windows::System::Internal::IUserProfileEventArgs *>::`vftable'
0x180045357  mov     rdx, rbx
0x18004535a  mov     [rbx], rax
0x18004535d  mov     rcx, [rsi+20h]
0x180045361  mov     rax, [rcx]
0x180045364  mov     rax, [rax+30h]
0x180045368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004536d  mov     edi, eax
0x18004536f  test    eax, eax
0x180045371  jns     loc_180045409
0x180045377  mov     ecx, cs:dword_180069000
0x18004537d  cmp     ecx, 2
0x180045380  jbe     short loc_1800453E1
0x180045382  mov     r8, cs:qword_180069018
0x180045389  mov     edx, 800h
0x18004538e  mov     rcx, cs:qword_180069010
0x180045395  test    rdx, rcx
0x180045398  jz      short loc_1800453E1
0x18004539a  mov     rax, r8
0x18004539d  and     rax, rdx
0x1800453a0  cmp     rax, r8
0x1800453a3  jnz     short loc_1800453E1
0x1800453a5  lea     rax, aOnecoreXboxGam_30; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800453ac  mov     [rbp+57h+var_7C], edi
0x1800453af  mov     [rbp+57h+var_78], rax
0x1800453b3  lea     rdx, byte_180063061
0x1800453ba  lea     rax, [rbp+57h+var_7C]
0x1800453be  mov     [rbp+57h+var_80], 57h ; 'W'
0x1800453c5  mov     [rsp+0C0h+var_90], rax
0x1800453ca  lea     rax, [rbp+57h+var_80]
0x1800453ce  mov     [rsp+0C0h+var_98], rax
0x1800453d3  lea     rax, [rbp+57h+var_78]
0x1800453d7  mov     [rsp+0C0h+var_A0], rax
0x1800453dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800453e1  mov     rax, [rbx]
0x1800453e4  mov     rcx, rbx
0x1800453e7  mov     rax, [rax+10h]
0x1800453eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453f0  mov     ebx, edi
0x1800453f2  mov     rcx, rsi; this
0x1800453f5  call    ??1ControllerWatcher@@QEAA@XZ; ControllerWatcher::~ControllerWatcher(void)
0x1800453fa  mov     rcx, rsi; P
0x1800453fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045402  mov     eax, ebx
0x180045404  jmp     loc_180045AE2
0x180045409  mov     rax, [rbx]
0x18004540c  mov     rcx, rbx
0x18004540f  mov     rax, [rax+10h]
0x180045413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045418  lea     r9, [rbp+57h+string]; string
0x18004541c  mov     [rbp+57h+string], r12
0x180045420  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180045424  mov     edx, 26h ; '&'; length
0x180045429  lea     rcx, ?RuntimeClass_Windows_Gaming_Input_RawGameController@@3QBGB; "Windows.Gaming.Input.RawGameController"
0x180045430  call    cs:__imp_WindowsCreateStringReference
0x180045437  nop     dword ptr [rax+rax+00h]
0x18004543c  test    eax, eax
0x18004543e  js      loc_180045B01
0x180045444  mov     rcx, [rbp+57h+string]
0x180045448  lea     r14, [rsi+18h]
0x18004544c  mov     r8, r14
0x18004544f  lea     rdx, _GUID_eb8d0792_e95a_4b19_afc7_0a59f8bf759e
0x180045456  call    cs:__imp_RoGetActivationFactory
0x18004545d  nop     dword ptr [rax+rax+00h]
0x180045462  mov     ebx, eax
0x180045464  test    eax, eax
0x180045466  jns     loc_18004553D
0x18004546c  mov     ecx, cs:dword_180069000
0x180045472  cmp     ecx, 2
0x180045475  jbe     loc_1800453F2
0x18004547b  mov     r8, cs:qword_180069018
0x180045482  mov     edx, 800h
0x180045487  mov     rcx, cs:qword_180069010
0x18004548e  test    rdx, rcx
0x180045491  jz      loc_1800453F2
0x180045497  mov     rax, r8
0x18004549a  and     rax, rdx
0x18004549d  cmp     rax, r8
0x1800454a0  jnz     loc_1800453F2
0x1800454a6  mov     [rbp+57h+var_80], 5Dh ; ']'
0x1800454ad  lea     rdx, byte_180063577
0x1800454b4  jmp     loc_1800452AC
0x1800454b9  mov     eax, cs:dword_180069000
0x1800454bf  mov     edi, 8007000Eh
0x1800454c4  cmp     eax, 2
0x1800454c7  jbe     short loc_180045528
0x1800454c9  mov     rcx, cs:qword_180069018
0x1800454d0  mov     edx, 800h
0x1800454d5  mov     rax, cs:qword_180069010
0x1800454dc  test    rdx, rax
0x1800454df  jz      short loc_180045528
0x1800454e1  mov     rax, rcx
0x1800454e4  and     rax, rdx
0x1800454e7  cmp     rax, rcx
0x1800454ea  jnz     short loc_180045528
0x1800454ec  lea     rax, aOnecoreXboxGam_30; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800454f3  mov     [rbp+57h+var_7C], edi
0x1800454f6  mov     [rbp+57h+var_78], rax
0x1800454fa  lea     rdx, unk_180063168
0x180045501  lea     rax, [rbp+57h+var_7C]
0x180045505  mov     [rbp+57h+var_80], 54h ; 'T'
0x18004550c  mov     [rsp+0C0h+var_90], rax
0x180045511  lea     rax, [rbp+57h+var_80]
0x180045515  mov     [rsp+0C0h+var_98], rax
0x18004551a  lea     rax, [rbp+57h+var_78]
0x18004551e  mov     [rsp+0C0h+var_A0], rax
0x180045523  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180045528  mov     rcx, rsi; this
0x18004552b  call    ??1ControllerWatcher@@QEAA@XZ; ControllerWatcher::~ControllerWatcher(void)
0x180045530  mov     rcx, rsi; P
0x180045533  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045538  jmp     loc_180045AE0
0x18004553d  lea     r8, ?OnControllerAdded@ControllerWatcher@@AEAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; ControllerWatcher::OnControllerAdded(IInspectable *,Windows::Gaming::Input::IRawGameController *)
0x180045544  mov     rdx, rsi
0x180045547  lea     rcx, [rbp+57h+var_78]
0x18004554b  call    ??$Callback@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@VGameInputServer@@PEAUIInspectable@@PEAUIRawGameController@Input@Gaming@3@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@@01@PEAVGameInputServer@@P83@EAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(GameInputServer *,long (GameInputServer::*)(IInspectable *,Windows::Gaming::Input::IRawGameController *))
0x180045550  mov     rbx, [rbp+57h+var_78]
0x180045554  test    rbx, rbx
0x180045557  jnz     loc_1800455DD
0x18004555d  mov     eax, cs:dword_180069000
0x180045563  mov     edi, 8007000Eh
0x180045568  cmp     eax, 2
0x18004556b  jbe     loc_1800453F0
0x180045571  mov     rcx, cs:qword_180069018
0x180045578  mov     edx, 800h
0x18004557d  mov     rax, cs:qword_180069010
0x180045584  test    rdx, rax
0x180045587  jz      loc_1800453F0
0x18004558d  mov     rax, rcx
0x180045590  and     rax, rdx
0x180045593  cmp     rax, rcx
0x180045596  jnz     loc_1800453F0
0x18004559c  lea     rax, aOnecoreXboxGam_30; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800455a3  mov     [rbp+57h+var_7C], edi
0x1800455a6  mov     [rbp+57h+var_78], rax
0x1800455aa  lea     rdx, byte_1800633F3
0x1800455b1  lea     rax, [rbp+57h+var_7C]
0x1800455b5  mov     [rbp+57h+var_80], 63h ; 'c'
0x1800455bc  mov     [rsp+0C0h+var_90], rax
0x1800455c1  lea     rax, [rbp+57h+var_80]
0x1800455c5  mov     [rsp+0C0h+var_98], rax
0x1800455ca  lea     rax, [rbp+57h+var_78]
0x1800455ce  mov     [rsp+0C0h+var_A0], rax
  ... truncated ...
```
