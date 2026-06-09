# Windows::UI::Input::Inking::DirectInkCoreServer::remove_StrokesCollected(EventRegistrationToken)

- ea: `0x180090310`
- end: `0x18009040c`
- name: `?remove_StrokesCollected@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJUEventRegistrationToken@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180032d4c`
- `0x18008b1e4`
- `0x180090310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009032b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009032b`

## string_xrefs

- `0x1800903c4`: `DirectInkCoreServer::remove_StrokesCollected[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::remove_StrokesCollected(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        struct EventRegistrationToken a2)
{
  int v2; // edi
  __int64 v5; // r8
  int v6; // edi
  __int64 v7; // rcx
  int *v8; // rdx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v11; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_DWORD *)this + 724);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 216));
    if ( v6 >= 0 )
    {
      v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 1880));
      if ( v6 >= 0 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v7 + 80,
               a2.value);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v8 = (int *)byte_180135A5B;
LABEL_13:
          v11 = L"DirectInkCoreServer::remove_StrokesCollected[Exit]";
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
    v8 = &dword_180135784;
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090310  mov     [rsp+arg_8], rbx
0x180090315  mov     [rsp+arg_18], rsi
0x18009031a  push    rdi
0x18009031b  sub     rsp, 30h
0x18009031f  mov     edi, [rcx+0B50h]
0x180090325  mov     rbx, rdx
0x180090328  mov     rsi, rcx
0x18009032b  call    cs:__imp_GetCurrentThreadId
0x180090331  cmp     eax, edi
0x180090333  jnz     short loc_180090398
0x180090335  lea     rcx, [rsi+0D8h]; this
0x18009033c  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090341  mov     edi, eax
0x180090343  test    eax, eax
0x180090345  js      short loc_18009039D
0x180090347  lea     rcx, [rsi+758h]; this
0x18009034e  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090353  mov     edi, eax
0x180090355  test    eax, eax
0x180090357  js      short loc_180090367
0x180090359  add     rcx, 50h ; 'P'
0x18009035d  mov     rdx, rbx
0x180090360  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180090365  mov     edi, eax
0x180090367  test    edi, edi
0x180090369  js      short loc_18009039D
0x18009036b  mov     eax, cs:dword_18015B128
0x180090371  cmp     eax, 4
0x180090374  jbe     loc_1800903FA
0x18009037a  mov     edx, 1
0x18009037f  lea     rcx, dword_18015B128
0x180090386  call    _tlgKeywordOn
0x18009038b  test    al, al
0x18009038d  jz      short loc_1800903FA
0x18009038f  lea     rdx, byte_180135A5B
0x180090396  jmp     short loc_1800903C4
0x180090398  mov     edi, 8001010Eh
0x18009039d  mov     eax, cs:dword_18015B128
0x1800903a3  cmp     eax, 2
0x1800903a6  jbe     short loc_1800903FA
0x1800903a8  mov     edx, 1
0x1800903ad  lea     rcx, dword_18015B128
0x1800903b4  call    _tlgKeywordOn
0x1800903b9  test    al, al
0x1800903bb  jz      short loc_1800903FA
0x1800903bd  lea     rdx, dword_180135784
0x1800903c4  lea     rax, aDirectinkcores; "DirectInkCoreServer::remove_StrokesColl"...
0x1800903cb  mov     [rsp+38h+arg_10], rax
0x1800903d0  lea     rax, [rsp+38h+arg_0]
0x1800903d5  mov     [rsp+38h+var_10], rax
0x1800903da  lea     rax, [rsp+38h+arg_10]
0x1800903df  mov     [rsp+38h+var_18], rax
0x1800903e4  xor     r9d, r9d
0x1800903e7  mov     [rsp+38h+arg_0], edi
0x1800903eb  xor     r8d, r8d
0x1800903ee  lea     rcx, dword_18015B128
0x1800903f5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800903fa  mov     rbx, [rsp+38h+arg_8]
0x1800903ff  mov     eax, edi
0x180090401  mov     rsi, [rsp+38h+arg_18]
0x180090406  add     rsp, 30h
0x18009040a  pop     rdi
0x18009040b  retn
```
