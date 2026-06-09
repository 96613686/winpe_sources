# Windows::UI::Input::Inking::DirectInkCoreServer::remove_HighContrastAdjustmentChanged(EventRegistrationToken)

- ea: `0x180090210`
- end: `0x180090309`
- name: `?remove_HighContrastAdjustmentChanged@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJUEventRegistrationToken@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180032d4c`
- `0x18008b1e4`
- `0x180090210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009022b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009022b`

## string_xrefs

- `0x1800902c1`: `DirectInkCoreServer::remove_HighContrastAdjustmentChanged[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::remove_HighContrastAdjustmentChanged(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        struct EventRegistrationToken a2)
{
  int v2; // edi
  __int64 v5; // r8
  int v6; // edi
  __int64 v7; // rcx
  __int16 *v8; // rdx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v11; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_DWORD *)this + 700);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 120));
    if ( v6 >= 0 )
    {
      v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 1784));
      if ( v6 >= 0 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v7 + 128,
               a2.value);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v8 = word_18013537A;
LABEL_13:
          v11 = L"DirectInkCoreServer::remove_HighContrastAdjustmentChanged[Exit]";
          v10 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18015B128,
            (_DWORD)v8,
            0,
            0,
            (__int64)&v11,
            (__int64)&v10);
          return (unsigned int)v6;
        }
        return (unsigned int)v6;
      }
    }
  }
  else
  {
    v6 = -2147417842;
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
  {
    v8 = (__int16 *)&dword_18013551C;
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090210  mov     [rsp+arg_8], rbx
0x180090215  mov     [rsp+arg_18], rsi
0x18009021a  push    rdi
0x18009021b  sub     rsp, 30h
0x18009021f  mov     edi, [rcx+0AF0h]
0x180090225  mov     rbx, rdx
0x180090228  mov     rsi, rcx
0x18009022b  call    cs:__imp_GetCurrentThreadId
0x180090231  cmp     eax, edi
0x180090233  jnz     short loc_180090295
0x180090235  lea     rcx, [rsi+78h]; this
0x180090239  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18009023e  mov     edi, eax
0x180090240  test    eax, eax
0x180090242  js      short loc_18009029A
0x180090244  lea     rcx, [rsi+6F8h]; this
0x18009024b  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090250  mov     edi, eax
0x180090252  test    eax, eax
0x180090254  js      short loc_180090264
0x180090256  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18009025a  mov     rdx, rbx
0x18009025d  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180090262  mov     edi, eax
0x180090264  test    edi, edi
0x180090266  js      short loc_18009029A
0x180090268  mov     eax, cs:dword_18015B128
0x18009026e  cmp     eax, 4
0x180090271  jbe     loc_1800902F7
0x180090277  mov     edx, 1
0x18009027c  lea     rcx, dword_18015B128
0x180090283  call    _tlgKeywordOn
0x180090288  test    al, al
0x18009028a  jz      short loc_1800902F7
0x18009028c  lea     rdx, word_18013537A
0x180090293  jmp     short loc_1800902C1
0x180090295  mov     edi, 8001010Eh
0x18009029a  mov     eax, cs:dword_18015B128
0x1800902a0  cmp     eax, 2
0x1800902a3  jbe     short loc_1800902F7
0x1800902a5  mov     edx, 1
0x1800902aa  lea     rcx, dword_18015B128
0x1800902b1  call    _tlgKeywordOn
0x1800902b6  test    al, al
0x1800902b8  jz      short loc_1800902F7
0x1800902ba  lea     rdx, dword_18013551C
0x1800902c1  lea     rax, aDirectinkcores_19; "DirectInkCoreServer::remove_HighContras"...
0x1800902c8  mov     [rsp+38h+arg_10], rax
0x1800902cd  lea     rax, [rsp+38h+arg_0]
0x1800902d2  mov     [rsp+38h+var_10], rax
0x1800902d7  lea     rax, [rsp+38h+arg_10]
0x1800902dc  mov     [rsp+38h+var_18], rax
0x1800902e1  xor     r9d, r9d
0x1800902e4  mov     [rsp+38h+arg_0], edi
0x1800902e8  xor     r8d, r8d
0x1800902eb  lea     rcx, dword_18015B128
0x1800902f2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800902f7  mov     rbx, [rsp+38h+arg_8]
0x1800902fc  mov     eax, edi
0x1800902fe  mov     rsi, [rsp+38h+arg_18]
0x180090303  add     rsp, 30h
0x180090307  pop     rdi
0x180090308  retn
```
