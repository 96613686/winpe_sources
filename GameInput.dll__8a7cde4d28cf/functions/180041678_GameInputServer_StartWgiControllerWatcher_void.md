# GameInputServer::StartWgiControllerWatcher(void)

- ea: `0x180041678`
- end: `0x180041d14`
- name: `?StartWgiControllerWatcher@GameInputServer@@AEAAJXZ`
- size: `1692`
- prototype: `__int64 __fastcall(GameInputServer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bcd8`

## callees

- `0x180001304`
- `0x18002cce8`
- `0x18003e1b0`
- `0x18003fe64`
- `0x180041678`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800416eb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800416eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800416c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800416c2`

## pseudocode

```c
__int64 __fastcall GameInputServer::StartWgiControllerWatcher(GameInputServer *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  _QWORD *v5; // rsi
  int ActivationFactory; // ebx
  int v7; // r9d
  int v9; // r8d
  int v10; // r9d
  struct Windows::Gaming::Input::IRawGameController *v11; // rbx
  int v12; // r15d
  __int64 v13; // rdx
  int v14; // edi
  __int64 v15; // r8
  int v16; // r9d
  int v17; // r8d
  int v18; // r9d
  struct Windows::Gaming::Input::IRawGameController *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r9d
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // esi
  __int64 v26; // r8
  int v27; // r9d
  int v28; // ecx
  char *v29; // rdx
  __int64 v30; // rcx
  unsigned int v31; // esi
  int v32; // r9d
  struct Windows::Gaming::Input::IRawGameController *v33; // rcx
  __int64 v34; // rcx
  int v35; // ecx
  char *v36; // rdx
  struct Windows::Gaming::Input::IRawGameController *v37; // rcx
  __int64 v38; // rcx
  int v39; // [rsp+40h] [rbp-19h] BYREF
  int v40; // [rsp+44h] [rbp-15h] BYREF
  struct Windows::Gaming::Input::IRawGameController *v41; // [rsp+48h] [rbp-11h] BYREF
  __int64 v42; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v43; // [rsp+58h] [rbp-1h] BYREF
  const char *v44; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF

  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Gaming.Input.RawGameController", 0x26u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180041D13LL);
  }
  v5 = (_QWORD *)((char *)this + 232);
  ActivationFactory = RoGetActivationFactory(string, &GUID_eb8d0792_e95a_4b19_afc7_0a59f8bf759e, (char *)this + 232);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v39 = ActivationFactory;
      v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      v40 = 1821;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_18005F959,
        qword_180069018,
        v7,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39);
    }
    return (unsigned int)ActivationFactory;
  }
  Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(
    &v41,
    this,
    GameInputServer::OnWgiControllerAdded);
  v11 = v41;
  v12 = -2147024882;
  if ( !v41 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v40 = -2147024882;
      v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      v39 = 1827;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)word_18006255A,
        v9,
        v10,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)&v40);
    }
    return (unsigned int)v12;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Gaming::Input::IRawGameController *, char *))(*(_QWORD *)*v5 + 48LL))(
          *v5,
          v41,
          (char *)this + 240);
  if ( v14 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v15 = qword_180069018;
      v13 = 1024;
      if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v40 = v14;
        v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
        v39 = 1830;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18006085B,
          qword_180069018,
          v16,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)&v40);
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v11 + 16LL))(
        v11,
        v13,
        v15);
    return (unsigned int)v14;
  }
  Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(
    &v41,
    this,
    GameInputServer::OnWgiControllerRemoved);
  v19 = v41;
  if ( !v41 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v40 = -2147024882;
      v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      v39 = 1836;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005FCC5,
        v17,
        v18,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)&v40);
    }
    if ( !v11 )
      return (unsigned int)v12;
    goto LABEL_27;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Gaming::Input::IRawGameController *, char *))(*(_QWORD *)*v5 + 64LL))(
          *v5,
          v41,
          (char *)this + 248);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v21 = qword_180069018;
      v20 = 1024;
      if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v40 = v12;
        v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
        v39 = 1839;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005FBD1,
          qword_180069018,
          v22,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)&v40);
      }
    }
    goto LABEL_34;
  }
  v23 = *v5;
  v42 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 80LL))(v23, &v42);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_44;
    v26 = qword_180069018;
    v24 = 1024;
    v28 = qword_180069010;
    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
      goto LABEL_44;
    v39 = 1842;
    v29 = byte_18005F16D;
LABEL_43:
    v41 = (struct Windows::Gaming::Input::IRawGameController *)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    v40 = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v28,
      (_DWORD)v29,
      v26,
      v27,
      (__int64)&v41,
      (__int64)&v39,
      (__int64)&v40);
LABEL_44:
    v30 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v30 + 16LL))(v30, v24, v26);
    }
    if ( v19 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v19 + 16LL))(
        v19,
        v24,
        v26);
    if ( v11 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v11 + 16LL))(
        v11,
        v24,
        v26);
    return (unsigned int)v25;
  }
  v43 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 56LL))(v42, &v43);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_44;
    v26 = qword_180069018;
    v24 = 1024;
    v28 = qword_180069010;
    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
      goto LABEL_44;
    v39 = 1845;
    v29 = &byte_180061AB7;
    goto LABEL_43;
  }
  v31 = 0;
  if ( v43 )
  {
    while ( 1 )
    {
      v41 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Gaming::Input::IRawGameController **))(*(_QWORD *)v42 + 48LL))(
              v42,
              v31,
              &v41);
      if ( v12 < 0 )
        break;
      v12 = GameInputServer::OnWgiControllerAdded(this, 0, v41);
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v35 = qword_180069018;
          v20 = 1024;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v39 = 1850;
            v36 = &byte_18005F1E7;
LABEL_77:
            v44 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
            v40 = v12;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v35,
              (_DWORD)v36,
              v21,
              v32,
              (__int64)&v44,
              (__int64)&v39,
              (__int64)&v40);
            goto LABEL_78;
          }
        }
        goto LABEL_78;
      }
      v33 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      if ( ++v31 >= v43 )
        goto LABEL_62;
    }
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v35 = qword_180069018;
      v20 = 1024;
      if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v39 = 1849;
        v36 = &byte_18005FB57;
        goto LABEL_77;
      }
    }
LABEL_78:
    v37 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
LABEL_34:
    if ( v19 )
      (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, __int64, __int64))(*(_QWORD *)v19 + 16LL))(
        v19,
        v20,
        v21);
    if ( !v11 )
      return (unsigned int)v12;
LABEL_27:
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)v12;
  }
LABEL_62:
  v34 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  if ( v19 )
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v11 )
    (*(void (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x180041678  mov     [rsp-8+arg_8], rbx
0x18004167d  mov     [rsp-8+arg_10], rsi
0x180041682  push    rbp
0x180041683  push    rdi
0x180041684  push    r12
0x180041686  push    r14
0x180041688  push    r15
0x18004168a  lea     rbp, [rsp-37h]
0x18004168f  sub     rsp, 90h
0x180041696  mov     rax, cs:__security_cookie
0x18004169d  xor     rax, rsp
0x1800416a0  mov     [rbp+57h+var_28], rax
0x1800416a4  xor     r12d, r12d
0x1800416a7  lea     r9, [rbp+57h+string]; string
0x1800416ab  mov     r14, rcx
0x1800416ae  mov     [rbp+57h+string], r12
0x1800416b2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800416b6  lea     rcx, ?RuntimeClass_Windows_Gaming_Input_RawGameController@@3QBGB; "Windows.Gaming.Input.RawGameController"
0x1800416bd  lea     edx, [r12+26h]; length
0x1800416c2  call    cs:__imp_WindowsCreateStringReference
0x1800416c9  nop     dword ptr [rax+rax+00h]
0x1800416ce  test    eax, eax
0x1800416d0  js      loc_180041D0C
0x1800416d6  mov     rcx, [rbp+57h+string]
0x1800416da  lea     rsi, [r14+0E8h]
0x1800416e1  mov     r8, rsi
0x1800416e4  lea     rdx, _GUID_eb8d0792_e95a_4b19_afc7_0a59f8bf759e
0x1800416eb  call    cs:__imp_RoGetActivationFactory
0x1800416f2  nop     dword ptr [rax+rax+00h]
0x1800416f7  mov     ebx, eax
0x1800416f9  test    eax, eax
0x1800416fb  jns     short loc_18004176E
0x1800416fd  mov     ecx, cs:dword_180069000
0x180041703  cmp     ecx, 2
0x180041706  jbe     short loc_180041767
0x180041708  mov     r8, cs:qword_180069018
0x18004170f  mov     edx, 400h
0x180041714  mov     rcx, cs:qword_180069010
0x18004171b  test    rdx, rcx
0x18004171e  jz      short loc_180041767
0x180041720  mov     rax, r8
0x180041723  and     rax, rdx
0x180041726  cmp     rax, r8
0x180041729  jnz     short loc_180041767
0x18004172b  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x180041732  mov     [rbp+57h+var_70], ebx
0x180041735  mov     [rbp+57h+var_68], rax
0x180041739  lea     rdx, byte_18005F959
0x180041740  lea     rax, [rbp+57h+var_70]
0x180041744  mov     [rbp+57h+var_6C], 71Dh
0x18004174b  mov     [rsp+0B0h+var_80], rax
0x180041750  lea     rax, [rbp+57h+var_6C]
0x180041754  mov     [rsp+0B0h+var_88], rax
0x180041759  lea     rax, [rbp+57h+var_68]
0x18004175d  mov     [rsp+0B0h+var_90], rax
0x180041762  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041767  mov     eax, ebx
0x180041769  jmp     loc_180041BF7
0x18004176e  lea     r8, ?OnWgiControllerAdded@GameInputServer@@AEAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; GameInputServer::OnWgiControllerAdded(IInspectable *,Windows::Gaming::Input::IRawGameController *)
0x180041775  mov     rdx, r14
0x180041778  lea     rcx, [rbp+57h+var_68]
0x18004177c  call    ??$Callback@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@VGameInputServer@@PEAUIInspectable@@PEAUIRawGameController@Input@Gaming@3@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@@01@PEAVGameInputServer@@P83@EAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(GameInputServer *,long (GameInputServer::*)(IInspectable *,Windows::Gaming::Input::IRawGameController *))
0x180041781  mov     rbx, [rbp+57h+var_68]
0x180041785  mov     r15d, 8007000Eh
0x18004178b  test    rbx, rbx
0x18004178e  jnz     short loc_18004180C
0x180041790  mov     eax, cs:dword_180069000
0x180041796  cmp     eax, 2
0x180041799  jbe     loc_180041953
0x18004179f  mov     rcx, cs:qword_180069018
0x1800417a6  mov     edx, 400h
0x1800417ab  mov     rax, cs:qword_180069010
0x1800417b2  test    rdx, rax
0x1800417b5  jz      loc_180041953
0x1800417bb  mov     rax, rcx
0x1800417be  and     rax, rdx
0x1800417c1  cmp     rax, rcx
0x1800417c4  jnz     loc_180041953
0x1800417ca  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x1800417d1  mov     [rbp+57h+var_6C], r15d
0x1800417d5  mov     [rbp+57h+var_68], rax
0x1800417d9  lea     rdx, word_18006255A
0x1800417e0  lea     rax, [rbp+57h+var_6C]
0x1800417e4  mov     [rbp+57h+var_70], 723h
0x1800417eb  mov     [rsp+0B0h+var_80], rax
0x1800417f0  lea     rax, [rbp+57h+var_70]
0x1800417f4  mov     [rsp+0B0h+var_88], rax
0x1800417f9  lea     rax, [rbp+57h+var_68]
0x1800417fd  mov     [rsp+0B0h+var_90], rax
0x180041802  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041807  jmp     loc_180041953
0x18004180c  mov     rcx, [rsi]
0x18004180f  lea     r8, [r14+0F0h]
0x180041816  mov     rdx, rbx
0x180041819  mov     rax, [rcx]
0x18004181c  mov     rax, [rax+30h]
0x180041820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041825  mov     edi, eax
0x180041827  test    eax, eax
0x180041829  jns     loc_1800418B4
0x18004182f  mov     ecx, cs:dword_180069000
0x180041835  cmp     ecx, 2
0x180041838  jbe     short loc_180041899
0x18004183a  mov     r8, cs:qword_180069018
0x180041841  mov     edx, 400h
0x180041846  mov     rcx, cs:qword_180069010
0x18004184d  test    rdx, rcx
0x180041850  jz      short loc_180041899
0x180041852  mov     rax, r8
0x180041855  and     rax, rdx
0x180041858  cmp     rax, r8
0x18004185b  jnz     short loc_180041899
0x18004185d  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x180041864  mov     [rbp+57h+var_6C], edi
0x180041867  mov     [rbp+57h+var_68], rax
0x18004186b  lea     rdx, byte_18006085B
0x180041872  lea     rax, [rbp+57h+var_6C]
0x180041876  mov     [rbp+57h+var_70], 726h
0x18004187d  mov     [rsp+0B0h+var_80], rax
0x180041882  lea     rax, [rbp+57h+var_70]
0x180041886  mov     [rsp+0B0h+var_88], rax
0x18004188b  lea     rax, [rbp+57h+var_68]
0x18004188f  mov     [rsp+0B0h+var_90], rax
0x180041894  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041899  test    rbx, rbx
0x18004189c  jz      short loc_1800418AD
0x18004189e  mov     rax, [rbx]
0x1800418a1  mov     rcx, rbx
0x1800418a4  mov     rax, [rax+10h]
0x1800418a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418ad  mov     eax, edi
0x1800418af  jmp     loc_180041BF7
0x1800418b4  lea     r8, ?OnWgiControllerRemoved@GameInputServer@@AEAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; GameInputServer::OnWgiControllerRemoved(IInspectable *,Windows::Gaming::Input::IRawGameController *)
0x1800418bb  mov     rdx, r14
0x1800418be  lea     rcx, [rbp+57h+var_68]
0x1800418c2  call    ??$Callback@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@VGameInputServer@@PEAUIInspectable@@PEAUIRawGameController@Input@Gaming@3@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAVRawGameController@Input@Gaming@Windows@@@Foundation@Windows@@@01@PEAVGameInputServer@@P83@EAAJPEAUIInspectable@@PEAUIRawGameController@Input@Gaming@Windows@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<Windows::Gaming::Input::RawGameController *>,GameInputServer,IInspectable *,Windows::Gaming::Input::IRawGameController *>(GameInputServer *,long (GameInputServer::*)(IInspectable *,Windows::Gaming::Input::IRawGameController *))
0x1800418c7  mov     rdi, [rbp+57h+var_68]
0x1800418cb  test    rdi, rdi
0x1800418ce  jnz     loc_18004195B
0x1800418d4  mov     eax, cs:dword_180069000
0x1800418da  cmp     eax, 2
0x1800418dd  jbe     short loc_18004193F
0x1800418df  mov     rcx, cs:qword_180069018
0x1800418e6  mov     edx, 400h
0x1800418eb  mov     rax, cs:qword_180069010
0x1800418f2  test    rdx, rax
0x1800418f5  jz      short loc_18004193F
0x1800418f7  mov     rax, rcx
0x1800418fa  and     rax, rdx
0x1800418fd  cmp     rax, rcx
0x180041900  jnz     short loc_18004193F
0x180041902  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x180041909  mov     [rbp+57h+var_6C], r15d
0x18004190d  mov     [rbp+57h+var_68], rax
0x180041911  lea     rdx, byte_18005FCC5
0x180041918  lea     rax, [rbp+57h+var_6C]
0x18004191c  mov     [rbp+57h+var_70], 72Ch
0x180041923  mov     [rsp+0B0h+var_80], rax
0x180041928  lea     rax, [rbp+57h+var_70]
0x18004192c  mov     [rsp+0B0h+var_88], rax
0x180041931  lea     rax, [rbp+57h+var_68]
0x180041935  mov     [rsp+0B0h+var_90], rax
0x18004193a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004193f  test    rbx, rbx
0x180041942  jz      short loc_180041953
0x180041944  mov     rcx, [rbx]
0x180041947  mov     rax, [rcx+10h]
0x18004194b  mov     rcx, rbx
0x18004194e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041953  mov     eax, r15d
0x180041956  jmp     loc_180041BF7
0x18004195b  mov     rcx, [rsi]
0x18004195e  lea     r8, [r14+0F8h]
0x180041965  mov     rdx, rdi
0x180041968  mov     rax, [rcx]
0x18004196b  mov     rax, [rax+40h]
0x18004196f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041974  mov     r15d, eax
0x180041977  test    eax, eax
0x180041979  jns     loc_180041A13
0x18004197f  mov     ecx, cs:dword_180069000
0x180041985  cmp     ecx, 2
0x180041988  jbe     short loc_1800419EA
0x18004198a  mov     r8, cs:qword_180069018
0x180041991  mov     edx, 400h
0x180041996  mov     rcx, cs:qword_180069010
0x18004199d  test    rdx, rcx
0x1800419a0  jz      short loc_1800419EA
0x1800419a2  mov     rax, r8
0x1800419a5  and     rax, rdx
0x1800419a8  cmp     rax, r8
0x1800419ab  jnz     short loc_1800419EA
0x1800419ad  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x1800419b4  mov     [rbp+57h+var_6C], r15d
0x1800419b8  mov     [rbp+57h+var_68], rax
0x1800419bc  lea     rdx, byte_18005FBD1
0x1800419c3  lea     rax, [rbp+57h+var_6C]
0x1800419c7  mov     [rbp+57h+var_70], 72Fh
0x1800419ce  mov     [rsp+0B0h+var_80], rax
0x1800419d3  lea     rax, [rbp+57h+var_70]
0x1800419d7  mov     [rsp+0B0h+var_88], rax
0x1800419dc  lea     rax, [rbp+57h+var_68]
0x1800419e0  mov     [rsp+0B0h+var_90], rax
0x1800419e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800419ea  test    rdi, rdi
0x1800419ed  jz      short loc_1800419FE
0x1800419ef  mov     rax, [rdi]
0x1800419f2  mov     rcx, rdi
0x1800419f5  mov     rax, [rax+10h]
0x1800419f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419fe  test    rbx, rbx
0x180041a01  jz      loc_180041953
0x180041a07  mov     rax, [rbx]
0x180041a0a  mov     rax, [rax+10h]
0x180041a0e  jmp     loc_18004194B
0x180041a13  mov     rcx, [rsi]
0x180041a16  lea     rdx, [rbp+57h+var_60]
0x180041a1a  mov     [rbp+57h+var_60], r12
0x180041a1e  mov     rax, [rcx]
0x180041a21  mov     rax, [rax+50h]
0x180041a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a2a  mov     esi, eax
0x180041a2c  test    eax, eax
0x180041a2e  jns     loc_180041AE6
0x180041a34  mov     ecx, cs:dword_180069000
0x180041a3a  cmp     ecx, 2
0x180041a3d  jbe     short loc_180041A9E
0x180041a3f  mov     r8, cs:qword_180069018
0x180041a46  mov     edx, 400h
0x180041a4b  mov     rcx, cs:qword_180069010
0x180041a52  test    rdx, rcx
0x180041a55  jz      short loc_180041A9E
0x180041a57  mov     rax, r8
0x180041a5a  and     rax, rdx
0x180041a5d  cmp     rax, r8
0x180041a60  jnz     short loc_180041A9E
0x180041a62  mov     [rbp+57h+var_70], 732h
0x180041a69  lea     rdx, byte_18005F16D
0x180041a70  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x180041a77  mov     [rbp+57h+var_68], rax
0x180041a7b  lea     rax, [rbp+57h+var_6C]
0x180041a7f  mov     [rsp+0B0h+var_80], rax
0x180041a84  lea     rax, [rbp+57h+var_70]
0x180041a88  mov     [rsp+0B0h+var_88], rax
0x180041a8d  lea     rax, [rbp+57h+var_68]
0x180041a91  mov     [rsp+0B0h+var_90], rax
0x180041a96  mov     [rbp+57h+var_6C], esi
0x180041a99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041a9e  mov     rcx, [rbp+57h+var_60]
0x180041aa2  test    rcx, rcx
0x180041aa5  jz      short loc_180041AB7
0x180041aa7  mov     [rbp+57h+var_60], r12
0x180041aab  mov     rax, [rcx]
0x180041aae  mov     rax, [rax+10h]
0x180041ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ab7  test    rdi, rdi
0x180041aba  jz      short loc_180041ACB
0x180041abc  mov     rax, [rdi]
0x180041abf  mov     rcx, rdi
0x180041ac2  mov     rax, [rax+10h]
0x180041ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041acb  test    rbx, rbx
0x180041ace  jz      short loc_180041ADF
0x180041ad0  mov     rax, [rbx]
0x180041ad3  mov     rcx, rbx
0x180041ad6  mov     rax, [rax+10h]
0x180041ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041adf  mov     eax, esi
0x180041ae1  jmp     loc_180041BF7
0x180041ae6  mov     rcx, [rbp+57h+var_60]
0x180041aea  lea     rdx, [rbp+57h+var_58]
0x180041aee  mov     [rbp+57h+var_58], r12d
0x180041af2  mov     rax, [rcx]
0x180041af5  mov     rax, [rax+38h]
0x180041af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041afe  mov     esi, eax
0x180041b00  test    eax, eax
0x180041b02  jns     short loc_180041B4D
0x180041b04  mov     ecx, cs:dword_180069000
0x180041b0a  cmp     ecx, 2
0x180041b0d  jbe     short loc_180041A9E
0x180041b0f  mov     r8, cs:qword_180069018
0x180041b16  mov     edx, 400h
0x180041b1b  mov     rcx, cs:qword_180069010
0x180041b22  test    rdx, rcx
0x180041b25  jz      loc_180041A9E
0x180041b2b  mov     rax, r8
0x180041b2e  and     rax, rdx
0x180041b31  cmp     rax, r8
0x180041b34  jnz     loc_180041A9E
0x180041b3a  mov     [rbp+57h+var_70], 735h
0x180041b41  lea     rdx, byte_180061AB7
0x180041b48  jmp     loc_180041A70
0x180041b4d  mov     esi, r12d
0x180041b50  cmp     [rbp+57h+var_58], r12d
0x180041b54  jbe     short loc_180041BB4
0x180041b56  mov     rcx, [rbp+57h+var_60]
0x180041b5a  lea     r8, [rbp+57h+var_68]
0x180041b5e  mov     [rbp+57h+var_68], r12
0x180041b62  mov     edx, esi
  ... truncated ...
```
