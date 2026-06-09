# Windows::UI::Input::Inking::DirectInkCoreServer::add_StrokesErased(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesErasedEventArgs *> *,EventRegistrationToken *)

- ea: `0x18008f250`
- end: `0x18008f3ae`
- name: `?add_StrokesErased@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesErasedEventArgs@2345@@Foundation@5@PEAUEventRegistrationToken@@@Z`
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
- `0x18008f250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f274`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::add_StrokesErased(
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
                 v8 + 104,
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
        v13 = 1;
        v14 = "InkEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v8,
          (unsigned int)byte_1801356F5,
          v7,
          v10,
          (__int64)&v14,
          (__int64)&v13);
      }
      if ( v9 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
        {
          v11 = (int *)&unk_180135728;
LABEL_18:
          v14 = (const char *)L"DirectInkCoreServer::add_StrokesErased[Exit]";
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
    v11 = &dword_1801358A4;
    goto LABEL_18;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008f250  mov     [rsp-18h+arg_8], rbx
0x18008f255  mov     [rsp-18h+arg_10], rsi
0x18008f25a  push    rbp
0x18008f25b  push    rdi
0x18008f25c  push    r14
0x18008f25e  mov     rbp, rsp
0x18008f261  sub     rsp, 30h
0x18008f265  mov     ebx, [rcx+0B50h]
0x18008f26b  mov     r14, r8
0x18008f26e  mov     rsi, rdx
0x18008f271  mov     rdi, rcx
0x18008f274  call    cs:__imp_GetCurrentThreadId
0x18008f27a  cmp     eax, ebx
0x18008f27c  jnz     loc_18008F33B
0x18008f282  lea     rcx, [rdi+0D8h]; this
0x18008f289  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008f28e  mov     ebx, eax
0x18008f290  test    eax, eax
0x18008f292  js      loc_18008F340
0x18008f298  test    rsi, rsi
0x18008f29b  jz      short loc_18008F2CE
0x18008f29d  test    r14, r14
0x18008f2a0  jz      short loc_18008F2CE
0x18008f2a2  lea     rcx, [rdi+758h]; this
0x18008f2a9  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008f2ae  mov     ebx, eax
0x18008f2b0  test    eax, eax
0x18008f2b2  js      short loc_18008F2D3
0x18008f2b4  mov     r8, [rsi]
0x18008f2b7  add     rcx, 68h ; 'h'
0x18008f2bb  mov     r9, r14
0x18008f2be  mov     rdx, rsi
0x18008f2c1  mov     r8, [r8+18h]
0x18008f2c5  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,void *,EventRegistrationToken *)
0x18008f2ca  mov     ebx, eax
0x18008f2cc  jmp     short loc_18008F2D3
0x18008f2ce  mov     ebx, 80004003h
0x18008f2d3  mov     eax, cs:dword_18015B128
0x18008f2d9  cmp     eax, 5
0x18008f2dc  jbe     short loc_18008F30E
0x18008f2de  lea     rax, aInkevent; "InkEvent"
0x18008f2e5  mov     [rbp+arg_0], 1
0x18008f2ec  mov     [rbp+arg_18], rax
0x18008f2f0  lea     rdx, byte_1801356F5
0x18008f2f7  lea     rax, [rbp+arg_0]
0x18008f2fb  mov     [rsp+30h+var_8], rax
0x18008f300  lea     rax, [rbp+arg_18]
0x18008f304  mov     [rsp+30h+var_10], rax
0x18008f309  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008f30e  test    ebx, ebx
0x18008f310  js      short loc_18008F340
0x18008f312  mov     eax, cs:dword_18015B128
0x18008f318  cmp     eax, 4
0x18008f31b  jbe     short loc_18008F399
0x18008f31d  mov     edx, 1
0x18008f322  lea     rcx, dword_18015B128
0x18008f329  call    _tlgKeywordOn
0x18008f32e  test    al, al
0x18008f330  jz      short loc_18008F399
0x18008f332  lea     rdx, unk_180135728
0x18008f339  jmp     short loc_18008F367
0x18008f33b  mov     ebx, 8001010Eh
0x18008f340  mov     eax, cs:dword_18015B128
0x18008f346  cmp     eax, 2
0x18008f349  jbe     short loc_18008F399
0x18008f34b  mov     edx, 1
0x18008f350  lea     rcx, dword_18015B128
0x18008f357  call    _tlgKeywordOn
0x18008f35c  test    al, al
0x18008f35e  jz      short loc_18008F399
0x18008f360  lea     rdx, dword_1801358A4
0x18008f367  lea     rax, aDirectinkcores_3; "DirectInkCoreServer::add_StrokesErased["...
0x18008f36e  mov     [rbp+arg_18], rax
0x18008f372  lea     rax, [rbp+arg_0]
0x18008f376  mov     [rsp+30h+var_8], rax
0x18008f37b  lea     rax, [rbp+arg_18]
0x18008f37f  mov     [rsp+30h+var_10], rax
0x18008f384  xor     r9d, r9d
0x18008f387  mov     [rbp+arg_0], ebx
0x18008f38a  xor     r8d, r8d
0x18008f38d  lea     rcx, dword_18015B128
0x18008f394  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008f399  mov     rsi, [rsp+30h+arg_10]
0x18008f39e  mov     eax, ebx
0x18008f3a0  mov     rbx, [rsp+30h+arg_8]
0x18008f3a5  add     rsp, 30h
0x18008f3a9  pop     r14
0x18008f3ab  pop     rdi
0x18008f3ac  pop     rbp
0x18008f3ad  retn
```
