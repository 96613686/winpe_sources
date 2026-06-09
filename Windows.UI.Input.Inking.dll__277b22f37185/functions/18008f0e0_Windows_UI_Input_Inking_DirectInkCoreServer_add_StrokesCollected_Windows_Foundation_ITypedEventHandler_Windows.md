# Windows::UI::Input::Inking::DirectInkCoreServer::add_StrokesCollected(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *> *,EventRegistrationToken *)

- ea: `0x18008f0e0`
- end: `0x18008f23e`
- name: `?add_StrokesCollected@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@5@PEAUEventRegistrationToken@@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180002ff8`
- `0x180026140`
- `0x18008b1e4`
- `0x18008f0e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f104`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::add_StrokesCollected(
        _DWORD *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // r9d
  int *v11; // rdx
  int v13; // [rsp+50h] [rbp+20h] BYREF
  const char *v14; // [rsp+68h] [rbp+38h] BYREF

  v3 = a1[724];
  if ( GetCurrentThreadId() == v3 )
  {
    v9 = CObjLifetime::CheckAlive((CObjLifetime *)(a1 + 54));
    if ( v9 >= 0 )
    {
      if ( a2 && a3 )
      {
        v9 = CObjLifetime::CheckAlive((CObjLifetime *)(a1 + 470));
        if ( v9 >= 0 )
          v9 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
                 v8 + 80,
                 a2,
                 *(_QWORD *)(*(_QWORD *)a2 + 24LL),
                 a3);
      }
      else
      {
        v9 = -2147467261;
      }
      if ( (unsigned int)dword_18015B128 > 5 )
      {
        v13 = 0;
        v14 = "InkEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v8,
          (unsigned int)byte_180135ABD,
          v7,
          v10,
          (__int64)&v14,
          (__int64)&v13);
      }
      if ( v9 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
        {
          v11 = (int *)&unk_180135AF0;
LABEL_18:
          v14 = (const char *)L"DirectInkCoreServer::add_StrokesCollected[Exit]";
          v13 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18015B128,
            (_DWORD)v11,
            0,
            0,
            (__int64)&v14,
            (__int64)&v13);
          return (unsigned int)v9;
        }
        return (unsigned int)v9;
      }
    }
  }
  else
  {
    v9 = -2147417842;
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
  {
    v11 = &dword_1801359FC;
    goto LABEL_18;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008f0e0  mov     [rsp-18h+arg_8], rbx
0x18008f0e5  mov     [rsp-18h+arg_10], rsi
0x18008f0ea  push    rbp
0x18008f0eb  push    rdi
0x18008f0ec  push    r14
0x18008f0ee  mov     rbp, rsp
0x18008f0f1  sub     rsp, 30h
0x18008f0f5  mov     ebx, [rcx+0B50h]
0x18008f0fb  mov     r14, r8
0x18008f0fe  mov     rsi, rdx
0x18008f101  mov     rdi, rcx
0x18008f104  call    cs:__imp_GetCurrentThreadId
0x18008f10a  cmp     eax, ebx
0x18008f10c  jnz     loc_18008F1CB
0x18008f112  lea     rcx, [rdi+0D8h]; this
0x18008f119  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008f11e  mov     ebx, eax
0x18008f120  test    eax, eax
0x18008f122  js      loc_18008F1D0
0x18008f128  test    rsi, rsi
0x18008f12b  jz      short loc_18008F15E
0x18008f12d  test    r14, r14
0x18008f130  jz      short loc_18008F15E
0x18008f132  lea     rcx, [rdi+758h]; this
0x18008f139  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008f13e  mov     ebx, eax
0x18008f140  test    eax, eax
0x18008f142  js      short loc_18008F163
0x18008f144  mov     r8, [rsi]
0x18008f147  add     rcx, 50h ; 'P'
0x18008f14b  mov     r9, r14
0x18008f14e  mov     rdx, rsi
0x18008f151  mov     r8, [r8+18h]
0x18008f155  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,void *,EventRegistrationToken *)
0x18008f15a  mov     ebx, eax
0x18008f15c  jmp     short loc_18008F163
0x18008f15e  mov     ebx, 80004003h
0x18008f163  mov     eax, cs:dword_18015B128
0x18008f169  cmp     eax, 5
0x18008f16c  jbe     short loc_18008F19E
0x18008f16e  lea     rax, aInkevent; "InkEvent"
0x18008f175  mov     [rbp+arg_0], 0
0x18008f17c  mov     [rbp+arg_18], rax
0x18008f180  lea     rdx, byte_180135ABD
0x18008f187  lea     rax, [rbp+arg_0]
0x18008f18b  mov     [rsp+30h+var_8], rax
0x18008f190  lea     rax, [rbp+arg_18]
0x18008f194  mov     [rsp+30h+var_10], rax
0x18008f199  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008f19e  test    ebx, ebx
0x18008f1a0  js      short loc_18008F1D0
0x18008f1a2  mov     eax, cs:dword_18015B128
0x18008f1a8  cmp     eax, 4
0x18008f1ab  jbe     short loc_18008F229
0x18008f1ad  mov     edx, 1
0x18008f1b2  lea     rcx, dword_18015B128
0x18008f1b9  call    _tlgKeywordOn
0x18008f1be  test    al, al
0x18008f1c0  jz      short loc_18008F229
0x18008f1c2  lea     rdx, unk_180135AF0
0x18008f1c9  jmp     short loc_18008F1F7
0x18008f1cb  mov     ebx, 8001010Eh
0x18008f1d0  mov     eax, cs:dword_18015B128
0x18008f1d6  cmp     eax, 2
0x18008f1d9  jbe     short loc_18008F229
0x18008f1db  mov     edx, 1
0x18008f1e0  lea     rcx, dword_18015B128
0x18008f1e7  call    _tlgKeywordOn
0x18008f1ec  test    al, al
0x18008f1ee  jz      short loc_18008F229
0x18008f1f0  lea     rdx, dword_1801359FC
0x18008f1f7  lea     rax, aDirectinkcores_6; "DirectInkCoreServer::add_StrokesCollect"...
0x18008f1fe  mov     [rbp+arg_18], rax
0x18008f202  lea     rax, [rbp+arg_0]
0x18008f206  mov     [rsp+30h+var_8], rax
0x18008f20b  lea     rax, [rbp+arg_18]
0x18008f20f  mov     [rsp+30h+var_10], rax
0x18008f214  xor     r9d, r9d
0x18008f217  mov     [rbp+arg_0], ebx
0x18008f21a  xor     r8d, r8d
0x18008f21d  lea     rcx, dword_18015B128
0x18008f224  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008f229  mov     rsi, [rsp+30h+arg_10]
0x18008f22e  mov     eax, ebx
0x18008f230  mov     rbx, [rsp+30h+arg_8]
0x18008f235  add     rsp, 30h
0x18008f239  pop     r14
0x18008f23b  pop     rdi
0x18008f23c  pop     rbp
0x18008f23d  retn
```
