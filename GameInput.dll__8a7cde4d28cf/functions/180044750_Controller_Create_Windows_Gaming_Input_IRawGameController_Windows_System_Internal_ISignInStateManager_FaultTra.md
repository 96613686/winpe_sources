# Controller::Create(Windows::Gaming::Input::IRawGameController *,Windows::System::Internal::ISignInStateManager *,FaultTracker *,Controller * *)

- ea: `0x180044750`
- end: `0x180045088`
- name: `?Create@Controller@@SAJPEAUIRawGameController@Input@Gaming@Windows@@PEAUISignInStateManager@Internal@System@5@PEAVFaultTracker@@PEAPEAV1@@Z`
- size: `2360`
- prototype: `__int64 __fastcall(struct Windows::Gaming::Input::IRawGameController *, struct Windows::System::Internal::ISignInStateManager *, struct FaultTracker *, struct Controller **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800465e0`

## callees

- `0x180001304`
- `0x1800443d8`
- `0x180044750`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180044e55`
- `ntdll!RtlAllocateHeap` at `0x180044e55`

## string_xrefs

- `0x18004480a`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044949`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x1800449cb`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044a53`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044adb`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044b5d`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044bdf`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044c71`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044d03`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180044f89`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`

## pseudocode

```c
__int64 __fastcall Controller::Create(
        struct Windows::Gaming::Input::IRawGameController *a1,
        struct Windows::System::Internal::ISignInStateManager *a2,
        struct FaultTracker *a3,
        struct Controller **a4)
{
  struct Windows::Gaming::Input::IRawGameController *v8; // rbx
  __int64 v9; // rdx
  int v10; // edi
  __int64 v11; // r8
  int v12; // r9d
  _QWORD *v13; // rcx
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v14; // rcx
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v15; // rcx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **); // rcx
  struct Windows::Gaming::Input::IGameController *v18; // rcx
  void (*v19)(void); // rax
  int v20; // r9d
  int v21; // r9d
  int v22; // r9d
  int v23; // r9d
  int v24; // r9d
  int v25; // r9d
  __int64 v26; // rax
  int v27; // r9d
  __int64 v28; // rax
  int v29; // r9d
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v30; // rcx
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v31; // rcx
  _QWORD *v32; // rcx
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v33; // rcx
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **); // rcx
  struct Windows::Gaming::Input::IGameController *v37; // rcx
  Controller *Heap; // rax
  int v40; // r8d
  int v41; // r9d
  struct Controller *v42; // rax
  _QWORD *v43; // rcx
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v44; // rcx
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v45; // rcx
  __int64 v46; // rcx
  __int64 (__fastcall ***v47)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **); // rcx
  struct Windows::Gaming::Input::IGameController *v48; // rcx
  _QWORD *v49; // rcx
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v50; // rcx
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v51; // rcx
  __int64 v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **); // rcx
  struct Windows::Gaming::Input::IGameController *v54; // rcx
  int v55; // [rsp+40h] [rbp-39h] BYREF
  int v56; // [rsp+44h] [rbp-35h] BYREF
  struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *v57; // [rsp+48h] [rbp-31h] BYREF
  struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *v58; // [rsp+50h] [rbp-29h] BYREF
  _QWORD *v59; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::Gaming::Input::IGameController *v60; // [rsp+60h] [rbp-19h] BYREF
  __int64 v61; // [rsp+68h] [rbp-11h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **); // [rsp+70h] [rbp-9h] BYREF
  GUID v63; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v64[8]; // [rsp+90h] [rbp+17h] BYREF
  char v65; // [rsp+E0h] [rbp+67h] BYREF
  char v66; // [rsp+F8h] [rbp+7Fh] BYREF

  *a4 = 0;
  v64[0] = 0;
  v60 = 0;
  v62 = 0;
  v8 = 0;
  v61 = 0;
  v58 = 0;
  v57 = 0;
  v59 = 0;
  v65 = 0;
  v66 = 0;
  if ( a1 )
  {
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)a1 + 8LL))(a1);
    v8 = a1;
  }
  v10 = (**(__int64 (__fastcall ***)(struct Windows::Gaming::Input::IRawGameController *, GUID *, struct Windows::Gaming::Input::IGameController **))v8)(
          v8,
          &GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd,
          &v60);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v55 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v56 = 43;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&byte_180062D6F,
          qword_180069018,
          v12,
          (__int64)&v63,
          (__int64)&v56,
          (__int64)&v55);
      }
    }
LABEL_8:
    v13 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v13 + 16LL))(v13, v9, v11);
    }
    v14 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, __int64, __int64))(*(_QWORD *)v14 + 16LL))(
        v14,
        v9,
        v11);
    }
    v15 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, __int64, __int64))(*(_QWORD *)v15 + 16LL))(
        v15,
        v9,
        v11);
    }
    v16 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v16 + 16LL))(v16, v9, v11);
    }
    v17 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*v17)[2](v17, (GUID *)v9, (struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **)v11);
    }
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(
      v8,
      v9,
      v11);
    v18 = v60;
    if ( !v60 )
      return (unsigned int)v10;
    v60 = 0;
    v19 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_115:
    v19();
    return (unsigned int)v10;
  }
  v10 = (**(__int64 (__fastcall ***)(struct Windows::Gaming::Input::IGameController *, GUID *, __int64 *))v60)(
          v60,
          &GUID_debcfefe_f763_4670_940b_57aae2b143ff,
          &v61);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 44;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_180063443,
          qword_180069018,
          v20,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **)))(*(_QWORD *)v61 + 48LL))(
          v61,
          &v62);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 45;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&dword_1800639C4,
          qword_180069018,
          v21,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v10 = (**v62)(v62, &GUID_c3542377_1ea7_4454_8deb_8aa6070db645, &v58);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 46;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_180062E29,
          qword_180069018,
          v22,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v10 = (**(__int64 (__fastcall ***)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate **))v58)(
          v58,
          &GUID_f6d99cef_3636_46f4_a0a9_00751df46bcb,
          &v57);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 47;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_180062CF5,
          qword_180069018,
          v23,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, unsigned __int64 *))(*(_QWORD *)v57 + 64LL))(
          v57,
          v64);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 48;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&unk_1800638D0,
          qword_180069018,
          v24,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *, _QWORD **))(*(_QWORD *)v57 + 120LL))(
          v57,
          &v59);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 49;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&word_180062C3E,
          qword_180069018,
          v25,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v26 = *v59;
  v63 = GUID_GIP_MICROSOFT_XBOX_INPUT_IGAMEPAD;
  v10 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, char *))(v26 + 120))(v59, &v63, &v65);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 50;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18006390D,
          qword_180069018,
          v27,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  v28 = *v59;
  v63 = GUID_GIP_MICROSOFT_XBOX_INPUT_IEXTERNALGAMEPADSTATUS;
  v10 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, char *))(v28 + 120))(v59, &v63, &v66);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v11 = qword_180069018;
      v9 = 2048;
      if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
      {
        v56 = v10;
        *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
        v55 = 51;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18006366B,
          qword_180069018,
          v29,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v56);
      }
    }
    goto LABEL_8;
  }
  if ( !a2 || !v65 )
  {
    v30 = v57;
    a2 = 0;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  if ( !a3 || !v66 )
  {
    v31 = v58;
    a3 = 0;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
  if ( !a2 && !a3 )
  {
    v32 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
    }
    v33 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **)))(*v36)[2])(v36);
    }
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v8 + 16LL))(v8);
    v37 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IGameController *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    return 2147942487LL;
  }
  Heap = (Controller *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x90u);
  if ( !Heap )
  {
    *a4 = 0;
LABEL_99:
    v10 = -2147024882;
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v56 = -2147024882;
      *(_QWORD *)&v63.Data1 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
      v55 = 76;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&dword_1800632EC,
        v40,
        v41,
        (__int64)&v63,
        (__int64)&v55,
        (__int64)&v56);
    }
    v49 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
    }
    v50 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **)))(*v53)[2])(v53);
    }
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v8 + 16LL))(v8);
    v54 = v60;
    if ( !v60 )
      return (unsigned int)v10;
    v60 = 0;
    v19 = *(void (**)(void))(*(_QWORD *)v54 + 16LL);
    goto LABEL_115;
  }
  v42 = Controller::Controller(Heap, v64[0], v60, a1, v58, v57, a2, a3);
  *a4 = v42;
  if ( !v42 )
    goto LABEL_99;
  v43 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
  }
  v44 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v62;
  if ( v62 )
  {
    v62 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate **)))(*v47)[2])(v47);
  }
  (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v8 + 16LL))(v8);
  v48 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IGameController *))(*(_QWORD *)v48 + 16LL))(v48);
  }
  return 0;
}

```

## disassembly

```asm
0x180044750  mov     [rsp-8+arg_8], rbx
0x180044755  push    rbp
0x180044756  push    rsi
0x180044757  push    rdi
0x180044758  push    r12
0x18004475a  push    r13
0x18004475c  push    r14
0x18004475e  push    r15
0x180044760  lea     rbp, [rsp-27h]
0x180044765  sub     rsp, 0A0h
0x18004476c  xor     r13d, r13d
0x18004476f  mov     r12, r9
0x180044772  mov     [r9], r13
0x180044775  mov     rsi, r8
0x180044778  mov     [rbp+57h+var_40], r13
0x18004477c  mov     r14, rdx
0x18004477f  mov     [rbp+57h+var_70], r13
0x180044783  mov     r15, rcx
0x180044786  mov     [rbp+57h+var_60], r13
0x18004478a  mov     ebx, r13d
0x18004478d  mov     [rbp+57h+var_68], r13
0x180044791  mov     [rbp+57h+var_80], r13
0x180044795  mov     [rbp+57h+var_88], r13
0x180044799  mov     [rbp+57h+var_78], r13
0x18004479d  mov     [rbp+57h+arg_0], r13b
0x1800447a1  mov     [rbp+57h+arg_18], r13b
0x1800447a5  test    rcx, rcx
0x1800447a8  jz      short loc_1800447B9
0x1800447aa  mov     rax, [rcx]
0x1800447ad  mov     rax, [rax+8]
0x1800447b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b6  mov     rbx, r15
0x1800447b9  mov     rax, [rbx]
0x1800447bc  lea     r8, [rbp+57h+var_70]
0x1800447c0  lea     rdx, _GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd
0x1800447c7  mov     rcx, rbx
0x1800447ca  mov     rax, [rax]
0x1800447cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447d2  mov     edi, eax
0x1800447d4  test    eax, eax
0x1800447d6  jns     loc_1800448EF
0x1800447dc  mov     ecx, cs:dword_180069000
0x1800447e2  cmp     ecx, 2
0x1800447e5  jbe     short loc_180044846
0x1800447e7  mov     r8, cs:qword_180069018
0x1800447ee  mov     edx, 800h
0x1800447f3  mov     rcx, cs:qword_180069010
0x1800447fa  test    rdx, rcx
0x1800447fd  jz      short loc_180044846
0x1800447ff  mov     rax, r8
0x180044802  and     rax, rdx
0x180044805  cmp     rax, r8
0x180044808  jnz     short loc_180044846
0x18004480a  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044811  mov     [rbp+57h+var_90], edi
0x180044814  mov     qword ptr [rbp+57h+var_50], rax
0x180044818  lea     rdx, byte_180062D6F
0x18004481f  lea     rax, [rbp+57h+var_90]
0x180044823  mov     [rbp+57h+var_8C], 2Bh ; '+'
0x18004482a  mov     [rsp+0D0h+var_A0], rax
0x18004482f  lea     rax, [rbp+57h+var_8C]
0x180044833  mov     [rsp+0D0h+var_A8], rax
0x180044838  lea     rax, [rbp+57h+var_50]
0x18004483c  mov     [rsp+0D0h+var_B0], rax
0x180044841  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180044846  mov     rcx, [rbp+57h+var_78]
0x18004484a  test    rcx, rcx
0x18004484d  jz      short loc_18004485F
0x18004484f  mov     [rbp+57h+var_78], r13
0x180044853  mov     rax, [rcx]
0x180044856  mov     rax, [rax+10h]
0x18004485a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004485f  mov     rcx, [rbp+57h+var_88]
0x180044863  test    rcx, rcx
0x180044866  jz      short loc_180044878
0x180044868  mov     [rbp+57h+var_88], r13
0x18004486c  mov     rax, [rcx]
0x18004486f  mov     rax, [rax+10h]
0x180044873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044878  mov     rcx, [rbp+57h+var_80]
0x18004487c  test    rcx, rcx
0x18004487f  jz      short loc_180044891
0x180044881  mov     [rbp+57h+var_80], r13
0x180044885  mov     rax, [rcx]
0x180044888  mov     rax, [rax+10h]
0x18004488c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044891  mov     rcx, [rbp+57h+var_68]
0x180044895  test    rcx, rcx
0x180044898  jz      short loc_1800448AA
0x18004489a  mov     [rbp+57h+var_68], r13
0x18004489e  mov     rax, [rcx]
0x1800448a1  mov     rax, [rax+10h]
0x1800448a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448aa  mov     rcx, [rbp+57h+var_60]
0x1800448ae  test    rcx, rcx
0x1800448b1  jz      short loc_1800448C3
0x1800448b3  mov     [rbp+57h+var_60], r13
0x1800448b7  mov     rax, [rcx]
0x1800448ba  mov     rax, [rax+10h]
0x1800448be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448c3  mov     rax, [rbx]
0x1800448c6  mov     rcx, rbx
0x1800448c9  mov     rax, [rax+10h]
0x1800448cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448d2  mov     rcx, [rbp+57h+var_70]
0x1800448d6  test    rcx, rcx
0x1800448d9  jz      loc_18004506A
0x1800448df  mov     [rbp+57h+var_70], r13
0x1800448e3  mov     rax, [rcx]
0x1800448e6  mov     rax, [rax+10h]
0x1800448ea  jmp     loc_180045065
0x1800448ef  mov     rcx, [rbp+57h+var_70]
0x1800448f3  lea     r8, [rbp+57h+var_68]
0x1800448f7  lea     rdx, _GUID_debcfefe_f763_4670_940b_57aae2b143ff
0x1800448fe  mov     rax, [rcx]
0x180044901  mov     rax, [rax]
0x180044904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044909  mov     edi, eax
0x18004490b  test    eax, eax
0x18004490d  jns     short loc_180044977
0x18004490f  mov     ecx, cs:dword_180069000
0x180044915  cmp     ecx, 2
0x180044918  jbe     loc_180044846
0x18004491e  mov     r8, cs:qword_180069018
0x180044925  mov     edx, 800h
0x18004492a  mov     rcx, cs:qword_180069010
0x180044931  test    rdx, rcx
0x180044934  jz      loc_180044846
0x18004493a  mov     rax, r8
0x18004493d  and     rax, rdx
0x180044940  cmp     rax, r8
0x180044943  jnz     loc_180044846
0x180044949  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044950  mov     [rbp+57h+var_8C], edi
0x180044953  mov     qword ptr [rbp+57h+var_50], rax
0x180044957  lea     rdx, byte_180063443
0x18004495e  lea     rax, [rbp+57h+var_8C]
0x180044962  mov     [rbp+57h+var_90], 2Ch ; ','
0x180044969  mov     [rsp+0D0h+var_A0], rax
0x18004496e  lea     rax, [rbp+57h+var_90]
0x180044972  jmp     loc_180044833
0x180044977  mov     rcx, [rbp+57h+var_68]
0x18004497b  lea     rdx, [rbp+57h+var_60]
0x18004497f  mov     rax, [rcx]
0x180044982  mov     rax, [rax+30h]
0x180044986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004498b  mov     edi, eax
0x18004498d  test    eax, eax
0x18004498f  jns     short loc_1800449F9
0x180044991  mov     ecx, cs:dword_180069000
0x180044997  cmp     ecx, 2
0x18004499a  jbe     loc_180044846
0x1800449a0  mov     r8, cs:qword_180069018
0x1800449a7  mov     edx, 800h
0x1800449ac  mov     rcx, cs:qword_180069010
0x1800449b3  test    rdx, rcx
0x1800449b6  jz      loc_180044846
0x1800449bc  mov     rax, r8
0x1800449bf  and     rax, rdx
0x1800449c2  cmp     rax, r8
0x1800449c5  jnz     loc_180044846
0x1800449cb  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800449d2  mov     [rbp+57h+var_8C], edi
0x1800449d5  mov     qword ptr [rbp+57h+var_50], rax
0x1800449d9  lea     rdx, dword_1800639C4
0x1800449e0  lea     rax, [rbp+57h+var_8C]
0x1800449e4  mov     [rbp+57h+var_90], 2Dh ; '-'
0x1800449eb  mov     [rsp+0D0h+var_A0], rax
0x1800449f0  lea     rax, [rbp+57h+var_90]
0x1800449f4  jmp     loc_180044833
0x1800449f9  mov     rcx, [rbp+57h+var_60]
0x1800449fd  lea     r8, [rbp+57h+var_80]
0x180044a01  lea     rdx, _GUID_c3542377_1ea7_4454_8deb_8aa6070db645
0x180044a08  mov     rax, [rcx]
0x180044a0b  mov     rax, [rax]
0x180044a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a13  mov     edi, eax
0x180044a15  test    eax, eax
0x180044a17  jns     short loc_180044A81
0x180044a19  mov     ecx, cs:dword_180069000
0x180044a1f  cmp     ecx, 2
0x180044a22  jbe     loc_180044846
0x180044a28  mov     r8, cs:qword_180069018
0x180044a2f  mov     edx, 800h
0x180044a34  mov     rcx, cs:qword_180069010
0x180044a3b  test    rdx, rcx
0x180044a3e  jz      loc_180044846
0x180044a44  mov     rax, r8
0x180044a47  and     rax, rdx
0x180044a4a  cmp     rax, r8
0x180044a4d  jnz     loc_180044846
0x180044a53  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044a5a  mov     [rbp+57h+var_8C], edi
0x180044a5d  mov     qword ptr [rbp+57h+var_50], rax
0x180044a61  lea     rdx, byte_180062E29
0x180044a68  lea     rax, [rbp+57h+var_8C]
0x180044a6c  mov     [rbp+57h+var_90], 2Eh ; '.'
0x180044a73  mov     [rsp+0D0h+var_A0], rax
0x180044a78  lea     rax, [rbp+57h+var_90]
0x180044a7c  jmp     loc_180044833
0x180044a81  mov     rcx, [rbp+57h+var_80]
0x180044a85  lea     r8, [rbp+57h+var_88]
0x180044a89  lea     rdx, _GUID_f6d99cef_3636_46f4_a0a9_00751df46bcb
0x180044a90  mov     rax, [rcx]
0x180044a93  mov     rax, [rax]
0x180044a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a9b  mov     edi, eax
0x180044a9d  test    eax, eax
0x180044a9f  jns     short loc_180044B09
0x180044aa1  mov     ecx, cs:dword_180069000
0x180044aa7  cmp     ecx, 2
0x180044aaa  jbe     loc_180044846
0x180044ab0  mov     r8, cs:qword_180069018
0x180044ab7  mov     edx, 800h
0x180044abc  mov     rcx, cs:qword_180069010
0x180044ac3  test    rdx, rcx
0x180044ac6  jz      loc_180044846
0x180044acc  mov     rax, r8
0x180044acf  and     rax, rdx
0x180044ad2  cmp     rax, r8
0x180044ad5  jnz     loc_180044846
0x180044adb  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044ae2  mov     [rbp+57h+var_8C], edi
0x180044ae5  mov     qword ptr [rbp+57h+var_50], rax
0x180044ae9  lea     rdx, byte_180062CF5
0x180044af0  lea     rax, [rbp+57h+var_8C]
0x180044af4  mov     [rbp+57h+var_90], 2Fh ; '/'
0x180044afb  mov     [rsp+0D0h+var_A0], rax
0x180044b00  lea     rax, [rbp+57h+var_90]
0x180044b04  jmp     loc_180044833
0x180044b09  mov     rcx, [rbp+57h+var_88]
0x180044b0d  lea     rdx, [rbp+57h+var_40]
0x180044b11  mov     rax, [rcx]
0x180044b14  mov     rax, [rax+40h]
0x180044b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b1d  mov     edi, eax
0x180044b1f  test    eax, eax
0x180044b21  jns     short loc_180044B8B
0x180044b23  mov     ecx, cs:dword_180069000
0x180044b29  cmp     ecx, 2
0x180044b2c  jbe     loc_180044846
0x180044b32  mov     r8, cs:qword_180069018
0x180044b39  mov     edx, 800h
0x180044b3e  mov     rcx, cs:qword_180069010
0x180044b45  test    rdx, rcx
0x180044b48  jz      loc_180044846
0x180044b4e  mov     rax, r8
0x180044b51  and     rax, rdx
0x180044b54  cmp     rax, r8
0x180044b57  jnz     loc_180044846
0x180044b5d  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044b64  mov     [rbp+57h+var_8C], edi
0x180044b67  mov     qword ptr [rbp+57h+var_50], rax
0x180044b6b  lea     rdx, unk_1800638D0
0x180044b72  lea     rax, [rbp+57h+var_8C]
0x180044b76  mov     [rbp+57h+var_90], 30h ; '0'
0x180044b7d  mov     [rsp+0D0h+var_A0], rax
0x180044b82  lea     rax, [rbp+57h+var_90]
0x180044b86  jmp     loc_180044833
0x180044b8b  mov     rcx, [rbp+57h+var_88]
0x180044b8f  lea     rdx, [rbp+57h+var_78]
0x180044b93  mov     rax, [rcx]
0x180044b96  mov     rax, [rax+78h]
0x180044b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b9f  mov     edi, eax
0x180044ba1  test    eax, eax
0x180044ba3  jns     short loc_180044C0D
0x180044ba5  mov     ecx, cs:dword_180069000
0x180044bab  cmp     ecx, 2
0x180044bae  jbe     loc_180044846
0x180044bb4  mov     r8, cs:qword_180069018
0x180044bbb  mov     edx, 800h
0x180044bc0  mov     rcx, cs:qword_180069010
0x180044bc7  test    rdx, rcx
0x180044bca  jz      loc_180044846
0x180044bd0  mov     rax, r8
0x180044bd3  and     rax, rdx
0x180044bd6  cmp     rax, r8
0x180044bd9  jnz     loc_180044846
0x180044bdf  lea     rax, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180044be6  mov     [rbp+57h+var_8C], edi
0x180044be9  mov     qword ptr [rbp+57h+var_50], rax
0x180044bed  lea     rdx, word_180062C3E
0x180044bf4  lea     rax, [rbp+57h+var_8C]
0x180044bf8  mov     [rbp+57h+var_90], 31h ; '1'
0x180044bff  mov     [rsp+0D0h+var_A0], rax
0x180044c04  lea     rax, [rbp+57h+var_90]
0x180044c08  jmp     loc_180044833
0x180044c0d  mov     rcx, [rbp+57h+var_78]
0x180044c11  lea     r8, [rbp+57h+arg_0]
0x180044c15  movups  xmm0, xmmword ptr cs:GUID_GIP_MICROSOFT_XBOX_INPUT_IGAMEPAD.Data1
0x180044c1c  lea     rdx, [rbp+57h+var_50]
0x180044c20  mov     rax, [rcx]
0x180044c23  movdqu  [rbp+57h+var_50], xmm0
0x180044c28  mov     rax, [rax+78h]
0x180044c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c31  mov     edi, eax
0x180044c33  test    eax, eax
0x180044c35  jns     short loc_180044C9F
0x180044c37  mov     ecx, cs:dword_180069000
  ... truncated ...
```
