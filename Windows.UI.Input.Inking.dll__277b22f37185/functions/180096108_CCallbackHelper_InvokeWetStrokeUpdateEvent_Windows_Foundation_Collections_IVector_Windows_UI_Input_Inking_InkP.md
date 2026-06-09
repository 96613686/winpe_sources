# CCallbackHelper::InvokeWetStrokeUpdateEvent(Windows::Foundation::Collections::IVector<Windows::UI::Input::Inking::InkPoint *> *,uint,DirectInkPrivate::InputEvent,Windows::UI::Input::Inking::Core::CoreWetStrokeDisposition *)

- ea: `0x180096108`
- end: `0x180096425`
- name: `?InvokeWetStrokeUpdateEvent@CCallbackHelper@@QEAAJPEAU?$IVector@PEAVInkPoint@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@IW4InputEvent@DirectInkPrivate@@PEAW4CoreWetStrokeDisposition@Core@Inking@Input@UI@5@@Z`
- size: `797`
- prototype: `__int64 __usercall@<rax>(CObjLifetime *this@<rcx>, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a1684`
- `0x1800a1b1c`
- `0x1800a4718`
- `0x1800a4b08`
- `0x1800a4e48`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x180042a80`
- `0x18008b1e4`
- `0x180094200`
- `0x1800943cc`
- `0x180096108`
- `0x1800969f8`
- `0x180096ae0`
- `0x1800fb010`

## string_xrefs

- `0x18009618d`: `CCallbackHelper::InvokeWetStrokeUpdateEvent`
- `0x1800961f7`: `CCallbackHelper::InvokeWetStrokeUpdateEvent`
- `0x1800963b6`: `CCallbackHelper::InvokeWetStrokeUpdateEvent`
- `0x1800962ba`: `spWetStrokeUpdateEventArgs->Initialize`
- `0x1800963ab`: `spWetStrokeUpdateEventArgs->get_Disposition`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCallbackHelper::InvokeWetStrokeUpdateEvent(
        CObjLifetime *this,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v8; // rcx
  int WetStrokeUpdateEventSourcePrivate; // ebx
  unsigned int v10; // r9d
  __int64 v11; // r8
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const wchar_t **v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // rdi
  unsigned int *v18; // r12
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  const wchar_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  const wchar_t **v28; // [rsp+30h] [rbp-20h]
  const wchar_t *v29; // [rsp+40h] [rbp-10h] BYREF
  const wchar_t *v30; // [rsp+48h] [rbp-8h] BYREF
  __int64 v31; // [rsp+80h] [rbp+30h] BYREF
  __int64 v32; // [rsp+88h] [rbp+38h]

  v32 = a2;
  v31 = 0;
  v29 = 0;
  WetStrokeUpdateEventSourcePrivate = CObjLifetime::CheckAlive(this);
  if ( WetStrokeUpdateEventSourcePrivate < 0 )
    return (unsigned int)WetStrokeUpdateEventSourcePrivate;
  WetStrokeUpdateEventSourcePrivate = CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(v8, v10, &v31);
  if ( WetStrokeUpdateEventSourcePrivate < 0 )
  {
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v11) )
    {
      v29 = L"_GetEventSource";
      v30 = L"CCallbackHelper::InvokeWetStrokeUpdateEvent";
      v28 = &v29;
      v15 = &v30;
LABEL_10:
      LODWORD(v31) = WetStrokeUpdateEventSourcePrivate;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)word_18013780A,
        v13,
        v14,
        (__int64)v15,
        (__int64)&v31,
        (__int64)v28);
      return (unsigned int)WetStrokeUpdateEventSourcePrivate;
    }
    return (unsigned int)WetStrokeUpdateEventSourcePrivate;
  }
  WetStrokeUpdateEventSourcePrivate = CCallbackHelper::_GetWetStrokeUpdateEventSource(this, a4, &v29);
  if ( WetStrokeUpdateEventSourcePrivate >= 0 )
  {
    if ( !Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(v29)
      && !Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(v31) )
    {
      return (unsigned int)CObjLifetime::CheckAlive(this);
    }
    Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs,>(&v30);
    v17 = v30;
    if ( !v30 )
    {
      WetStrokeUpdateEventSourcePrivate = -2147024882;
      goto LABEL_34;
    }
    v18 = a5;
    WetStrokeUpdateEventSourcePrivate = (*(__int64 (__fastcall **)(const wchar_t *, __int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 88LL))(
                                          v30,
                                          v32,
                                          a3,
                                          *a5);
    if ( WetStrokeUpdateEventSourcePrivate >= 0 )
    {
      if ( Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(v31)
        && (WetStrokeUpdateEventSourcePrivate = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *>(
                                                  v31,
                                                  *((_QWORD *)this + 8),
                                                  v17),
            WetStrokeUpdateEventSourcePrivate < 0) )
      {
        if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v24) )
        {
          v23 = L"evtPointerEventPrivate->InvokeAll";
          goto LABEL_33;
        }
      }
      else if ( Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(v29)
             && (WetStrokeUpdateEventSourcePrivate = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *>(
                                                       v29,
                                                       *((_QWORD *)this + 8),
                                                       v17),
                 WetStrokeUpdateEventSourcePrivate < 0) )
      {
        if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v25) )
        {
          v23 = L"evtPointerEvent->InvokeAll";
          goto LABEL_33;
        }
      }
      else
      {
        WetStrokeUpdateEventSourcePrivate = (*(__int64 (__fastcall **)(const wchar_t *, unsigned int *))(*(_QWORD *)v17 + 64LL))(
                                              v17,
                                              v18);
        if ( WetStrokeUpdateEventSourcePrivate < 0
          && (unsigned int)dword_18015B128 > 2
          && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v26) )
        {
          v23 = L"spWetStrokeUpdateEventArgs->get_Disposition";
          goto LABEL_33;
        }
      }
    }
    else if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v19) )
    {
      v23 = L"spWetStrokeUpdateEventArgs->Initialize";
LABEL_33:
      v30 = v23;
      v29 = L"CCallbackHelper::InvokeWetStrokeUpdateEvent";
      LODWORD(v31) = WetStrokeUpdateEventSourcePrivate;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v20,
        (unsigned int)word_18013780A,
        v21,
        v22,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v30);
    }
LABEL_34:
    if ( v17 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v17 + 16LL))(v17);
    if ( WetStrokeUpdateEventSourcePrivate < 0 )
      return (unsigned int)WetStrokeUpdateEventSourcePrivate;
    return (unsigned int)CObjLifetime::CheckAlive(this);
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v16) )
  {
    v30 = L"_GetEventSource";
    v29 = L"CCallbackHelper::InvokeWetStrokeUpdateEvent";
    v28 = &v30;
    v15 = &v29;
    goto LABEL_10;
  }
  return (unsigned int)WetStrokeUpdateEventSourcePrivate;
}

```

## disassembly

```asm
0x180096108  mov     [rsp-28h+arg_10], rbx
0x18009610d  mov     [rsp-28h+arg_8], rdx
0x180096112  push    rbp
0x180096113  push    rsi
0x180096114  push    rdi
0x180096115  push    r12
0x180096117  push    r13
0x180096119  mov     rbp, rsp
0x18009611c  sub     rsp, 50h
0x180096120  mov     edi, r9d
0x180096123  mov     r13d, r8d
0x180096126  mov     rsi, rcx
0x180096129  mov     [rbp+arg_0], 0
0x180096131  mov     [rbp+var_10], 0
0x180096139  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18009613e  mov     ebx, eax
0x180096140  test    eax, eax
0x180096142  js      loc_18009640F
0x180096148  lea     r8, [rbp+arg_0]
0x18009614c  mov     edx, r9d
0x18009614f  call    ?_GetWetStrokeUpdateEventSourcePrivate@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x180096154  mov     ebx, eax
0x180096156  test    eax, eax
0x180096158  jns     short loc_1800961B0
0x18009615a  mov     eax, cs:dword_18015B128
0x180096160  cmp     eax, 2
0x180096163  jbe     loc_18009640F
0x180096169  mov     edx, 100h
0x18009616e  lea     rcx, dword_18015B128
0x180096175  call    _tlgKeywordOn
0x18009617a  test    al, al
0x18009617c  jz      loc_18009640F
0x180096182  lea     rax, aGeteventsource; "_GetEventSource"
0x180096189  mov     [rbp+var_10], rax
0x18009618d  lea     rax, aCcallbackhelpe_7; "CCallbackHelper::InvokeWetStrokeUpdateE"...
0x180096194  mov     [rbp+var_8], rax
0x180096198  lea     rax, [rbp+var_10]
0x18009619c  mov     [rsp+50h+var_20], rax
0x1800961a1  lea     rax, [rbp+arg_0]
0x1800961a5  mov     [rsp+50h+var_28], rax
0x1800961aa  lea     rax, [rbp+var_8]
0x1800961ae  jmp     short loc_180096218
0x1800961b0  lea     r8, [rbp+var_10]
0x1800961b4  mov     edx, edi
0x1800961b6  mov     rcx, rsi
0x1800961b9  call    ?_GetWetStrokeUpdateEventSource@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSource(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x1800961be  mov     ebx, eax
0x1800961c0  test    eax, eax
0x1800961c2  jns     short loc_180096231
0x1800961c4  mov     eax, cs:dword_18015B128
0x1800961ca  cmp     eax, 2
0x1800961cd  jbe     loc_18009640F
0x1800961d3  mov     edx, 100h
0x1800961d8  lea     rcx, dword_18015B128
0x1800961df  call    _tlgKeywordOn
0x1800961e4  test    al, al
0x1800961e6  jz      loc_18009640F
0x1800961ec  lea     rax, aGeteventsource; "_GetEventSource"
0x1800961f3  mov     [rbp+var_8], rax
0x1800961f7  lea     rax, aCcallbackhelpe_7; "CCallbackHelper::InvokeWetStrokeUpdateE"...
0x1800961fe  mov     [rbp+var_10], rax
0x180096202  lea     rax, [rbp+var_8]
0x180096206  mov     [rsp+50h+var_20], rax
0x18009620b  lea     rax, [rbp+arg_0]
0x18009620f  mov     [rsp+50h+var_28], rax
0x180096214  lea     rax, [rbp+var_10]
0x180096218  mov     dword ptr [rbp+arg_0], ebx
0x18009621b  mov     [rsp+50h+var_30], rax
0x180096220  lea     rdx, word_18013780A
0x180096227  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009622c  jmp     loc_18009640F
0x180096231  mov     rcx, [rbp+var_10]
0x180096235  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x18009623a  test    rax, rax
0x18009623d  jnz     short loc_180096251
0x18009623f  mov     rcx, [rbp+arg_0]
0x180096243  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x180096248  test    rax, rax
0x18009624b  jz      loc_180096405
0x180096251  lea     rcx, [rbp+var_8]
0x180096255  call    ??$Make@VCCoreWetStrokeUpdateEventArgs@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCoreWetStrokeUpdateEventArgs@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs,>(void)
0x18009625a  nop
0x18009625b  mov     rdi, [rbp+var_8]
0x18009625f  test    rdi, rdi
0x180096262  jnz     short loc_18009626E
0x180096264  mov     ebx, 8007000Eh
0x180096269  jmp     loc_1800963EC
0x18009626e  mov     rax, [rdi]
0x180096271  mov     r12, [rbp+arg_20]
0x180096275  mov     r9d, [r12]
0x180096279  mov     r8d, r13d
0x18009627c  mov     rdx, [rbp+arg_8]
0x180096280  mov     rcx, rdi
0x180096283  mov     rax, [rax+58h]
0x180096287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009628c  mov     ebx, eax
0x18009628e  test    eax, eax
0x180096290  jns     short loc_1800962C6
0x180096292  mov     eax, cs:dword_18015B128
0x180096298  cmp     eax, 2
0x18009629b  jbe     loc_1800963EC
0x1800962a1  mov     edx, 100h
0x1800962a6  lea     rcx, dword_18015B128
0x1800962ad  call    _tlgKeywordOn
0x1800962b2  test    al, al
0x1800962b4  jz      loc_1800963EC
0x1800962ba  lea     rax, aSpwetstrokeupd_0; "spWetStrokeUpdateEventArgs->Initialize"
0x1800962c1  jmp     loc_1800963B2
0x1800962c6  mov     rcx, [rbp+arg_0]
0x1800962ca  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x1800962cf  test    rax, rax
0x1800962d2  jz      short loc_18009631E
0x1800962d4  mov     r8, rdi
0x1800962d7  mov     rdx, [rsi+40h]
0x1800962db  mov     rcx, [rbp+arg_0]
0x1800962df  call    ??$InvokeAll@PEAUICoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCCoreWetStrokeUpdateEventArgs@3456@@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAUICoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCCoreWetStrokeUpdateEventArgs@5678@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *>(Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *)
0x1800962e4  mov     ebx, eax
0x1800962e6  test    eax, eax
0x1800962e8  jns     short loc_18009631E
0x1800962ea  mov     eax, cs:dword_18015B128
0x1800962f0  cmp     eax, 2
0x1800962f3  jbe     loc_1800963EC
0x1800962f9  mov     edx, 100h
0x1800962fe  lea     rcx, dword_18015B128
0x180096305  call    _tlgKeywordOn
0x18009630a  test    al, al
0x18009630c  jz      loc_1800963EC
0x180096312  lea     rax, aEvtpointereven_0; "evtPointerEventPrivate->InvokeAll"
0x180096319  jmp     loc_1800963B2
0x18009631e  mov     rcx, [rbp+var_10]
0x180096322  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x180096327  test    rax, rax
0x18009632a  jz      short loc_180096373
0x18009632c  mov     r8, rdi
0x18009632f  mov     rdx, [rsi+40h]
0x180096333  mov     rcx, [rbp+var_10]
0x180096337  call    ??$InvokeAll@PEAUICoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCCoreWetStrokeUpdateEventArgs@3456@@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAUICoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCCoreWetStrokeUpdateEventArgs@5678@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *>(Windows::UI::Input::Inking::Core::ICoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::CCoreWetStrokeUpdateEventArgs *)
0x18009633c  mov     ebx, eax
0x18009633e  test    eax, eax
0x180096340  jns     short loc_180096373
0x180096342  mov     eax, cs:dword_18015B128
0x180096348  cmp     eax, 2
0x18009634b  jbe     loc_1800963EC
0x180096351  mov     edx, 100h
0x180096356  lea     rcx, dword_18015B128
0x18009635d  call    _tlgKeywordOn
0x180096362  test    al, al
0x180096364  jz      loc_1800963EC
0x18009636a  lea     rax, aEvtpointereven; "evtPointerEvent->InvokeAll"
0x180096371  jmp     short loc_1800963B2
0x180096373  mov     rax, [rdi]
0x180096376  mov     rdx, r12
0x180096379  mov     rcx, rdi
0x18009637c  mov     rax, [rax+40h]
0x180096380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096385  mov     ebx, eax
0x180096387  test    eax, eax
0x180096389  jns     short loc_1800963EC
0x18009638b  mov     eax, cs:dword_18015B128
0x180096391  cmp     eax, 2
0x180096394  jbe     short loc_1800963EC
0x180096396  mov     edx, 100h
0x18009639b  lea     rcx, dword_18015B128
0x1800963a2  call    _tlgKeywordOn
0x1800963a7  test    al, al
0x1800963a9  jz      short loc_1800963EC
0x1800963ab  lea     rax, aSpwetstrokeupd; "spWetStrokeUpdateEventArgs->get_Disposi"...
0x1800963b2  mov     [rbp+var_8], rax
0x1800963b6  lea     rax, aCcallbackhelpe_7; "CCallbackHelper::InvokeWetStrokeUpdateE"...
0x1800963bd  mov     [rbp+var_10], rax
0x1800963c1  lea     rax, [rbp+var_8]
0x1800963c5  mov     [rsp+50h+var_20], rax
0x1800963ca  lea     rax, [rbp+arg_0]
0x1800963ce  mov     [rsp+50h+var_28], rax
0x1800963d3  lea     rax, [rbp+var_10]
0x1800963d7  mov     [rsp+50h+var_30], rax
0x1800963dc  mov     dword ptr [rbp+arg_0], ebx
0x1800963df  lea     rdx, word_18013780A
0x1800963e6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800963eb  nop
0x1800963ec  test    rdi, rdi
0x1800963ef  jz      short loc_180096401
0x1800963f1  mov     rax, [rdi]
0x1800963f4  mov     rcx, rdi
0x1800963f7  mov     rax, [rax+10h]
0x1800963fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096400  nop
0x180096401  test    ebx, ebx
0x180096403  js      short loc_18009640F
0x180096405  mov     rcx, rsi; this
0x180096408  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18009640d  mov     ebx, eax
0x18009640f  mov     eax, ebx
0x180096411  mov     rbx, [rsp+50h+arg_10]
0x180096419  add     rsp, 50h
0x18009641d  pop     r13
0x18009641f  pop     r12
0x180096421  pop     rdi
0x180096422  pop     rsi
0x180096423  pop     rbp
0x180096424  retn
```
