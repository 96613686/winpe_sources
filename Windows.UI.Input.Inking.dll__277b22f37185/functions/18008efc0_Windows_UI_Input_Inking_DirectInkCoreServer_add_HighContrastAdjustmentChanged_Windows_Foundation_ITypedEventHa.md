# Windows::UI::Input::Inking::DirectInkCoreServer::add_HighContrastAdjustmentChanged(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::Internal::HighContrastAdjustmentEventArgs *> *,EventRegistrationToken *)

- ea: `0x18008efc0`
- end: `0x18008f0d1`
- name: `?add_HighContrastAdjustmentChanged@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVHighContrastAdjustmentEventArgs@Internal@2345@@Foundation@5@PEAUEventRegistrationToken@@@Z`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180026140`
- `0x18008b1e4`
- `0x18008efc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008efdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008efdb`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::add_HighContrastAdjustmentChanged(
        _DWORD *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // ebx
  __int64 v7; // r8
  int v8; // ebx
  __int64 v9; // rcx
  char *v10; // rdx
  int v12; // [rsp+50h] [rbp+8h] BYREF
  const wchar_t *v13; // [rsp+68h] [rbp+20h] BYREF

  v3 = a1[700];
  if ( GetCurrentThreadId() == v3 )
  {
    v8 = CObjLifetime::CheckAlive((CObjLifetime *)(a1 + 30));
    if ( v8 >= 0 )
    {
      if ( a2 && a3 )
      {
        v8 = CObjLifetime::CheckAlive((CObjLifetime *)(a1 + 446));
        if ( v8 >= 0 )
          v8 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
                 v9 + 128,
                 a2,
                 *(_QWORD *)(*(_QWORD *)a2 + 24LL),
                 a3);
        if ( v8 >= 0 )
        {
          if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
          {
            v10 = byte_1801353E9;
LABEL_16:
            v13 = L"DirectInkCoreServer::add_HighContrastAdjustmentChanged[Exit]";
            v12 = v8;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18015B128,
              (_DWORD)v10,
              0,
              0,
              (__int64)&v13,
              (__int64)&v12);
            return (unsigned int)v8;
          }
          return (unsigned int)v8;
        }
      }
      else
      {
        v8 = -2147467261;
      }
    }
  }
  else
  {
    v8 = -2147417842;
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
  {
    v10 = byte_180135455;
    goto LABEL_16;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008efc0  mov     [rsp+arg_8], rbx
0x18008efc5  push    rbp
0x18008efc6  push    rsi
0x18008efc7  push    rdi
0x18008efc8  sub     rsp, 30h
0x18008efcc  mov     ebx, [rcx+0AF0h]
0x18008efd2  mov     rbp, r8
0x18008efd5  mov     rsi, rdx
0x18008efd8  mov     rdi, rcx
0x18008efdb  call    cs:__imp_GetCurrentThreadId
0x18008efe1  cmp     eax, ebx
0x18008efe3  jnz     short loc_18008F060
0x18008efe5  lea     rcx, [rdi+78h]; this
0x18008efe9  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008efee  mov     ebx, eax
0x18008eff0  test    eax, eax
0x18008eff2  js      short loc_18008F065
0x18008eff4  test    rsi, rsi
0x18008eff7  jz      short loc_18008F059
0x18008eff9  test    rbp, rbp
0x18008effc  jz      short loc_18008F059
0x18008effe  lea     rcx, [rdi+6F8h]; this
0x18008f005  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008f00a  mov     ebx, eax
0x18008f00c  test    eax, eax
0x18008f00e  js      short loc_18008F028
0x18008f010  mov     r8, [rsi]
0x18008f013  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18008f017  mov     r9, rbp
0x18008f01a  mov     rdx, rsi
0x18008f01d  mov     r8, [r8+18h]
0x18008f021  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,void *,EventRegistrationToken *)
0x18008f026  mov     ebx, eax
0x18008f028  test    ebx, ebx
0x18008f02a  js      short loc_18008F065
0x18008f02c  mov     eax, cs:dword_18015B128
0x18008f032  cmp     eax, 4
0x18008f035  jbe     loc_18008F0C2
0x18008f03b  mov     edx, 1
0x18008f040  lea     rcx, dword_18015B128
0x18008f047  call    _tlgKeywordOn
0x18008f04c  test    al, al
0x18008f04e  jz      short loc_18008F0C2
0x18008f050  lea     rdx, byte_1801353E9
0x18008f057  jmp     short loc_18008F08C
0x18008f059  mov     ebx, 80004003h
0x18008f05e  jmp     short loc_18008F065
0x18008f060  mov     ebx, 8001010Eh
0x18008f065  mov     eax, cs:dword_18015B128
0x18008f06b  cmp     eax, 2
0x18008f06e  jbe     short loc_18008F0C2
0x18008f070  mov     edx, 1
0x18008f075  lea     rcx, dword_18015B128
0x18008f07c  call    _tlgKeywordOn
0x18008f081  test    al, al
0x18008f083  jz      short loc_18008F0C2
0x18008f085  lea     rdx, byte_180135455
0x18008f08c  lea     rax, aDirectinkcores_11; "DirectInkCoreServer::add_HighContrastAd"...
0x18008f093  mov     [rsp+48h+arg_18], rax
0x18008f098  lea     rax, [rsp+48h+arg_0]
0x18008f09d  mov     [rsp+48h+var_20], rax
0x18008f0a2  lea     rax, [rsp+48h+arg_18]
0x18008f0a7  mov     [rsp+48h+var_28], rax
0x18008f0ac  xor     r9d, r9d
0x18008f0af  mov     [rsp+48h+arg_0], ebx
0x18008f0b3  xor     r8d, r8d
0x18008f0b6  lea     rcx, dword_18015B128
0x18008f0bd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008f0c2  mov     eax, ebx
0x18008f0c4  mov     rbx, [rsp+48h+arg_8]
0x18008f0c9  add     rsp, 30h
0x18008f0cd  pop     rdi
0x18008f0ce  pop     rsi
0x18008f0cf  pop     rbp
0x18008f0d0  retn
```
