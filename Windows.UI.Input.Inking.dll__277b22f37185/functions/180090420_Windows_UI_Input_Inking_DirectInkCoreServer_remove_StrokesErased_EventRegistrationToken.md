# Windows::UI::Input::Inking::DirectInkCoreServer::remove_StrokesErased(EventRegistrationToken)

- ea: `0x180090420`
- end: `0x18009051c`
- name: `?remove_StrokesErased@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJUEventRegistrationToken@@@Z`
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
- `0x180090420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009043b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009043b`

## string_xrefs

- `0x1800904d4`: `DirectInkCoreServer::remove_StrokesErased[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::remove_StrokesErased(
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

  v2 = *((_DWORD *)this + 724);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 216));
    if ( v6 >= 0 )
    {
      v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 1880));
      if ( v6 >= 0 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v7 + 104,
               a2.value);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v8 = &word_1801357E6;
LABEL_13:
          v11 = L"DirectInkCoreServer::remove_StrokesErased[Exit]";
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
    v8 = (__int16 *)byte_180135845;
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090420  mov     [rsp+arg_8], rbx
0x180090425  mov     [rsp+arg_18], rsi
0x18009042a  push    rdi
0x18009042b  sub     rsp, 30h
0x18009042f  mov     edi, [rcx+0B50h]
0x180090435  mov     rbx, rdx
0x180090438  mov     rsi, rcx
0x18009043b  call    cs:__imp_GetCurrentThreadId
0x180090441  cmp     eax, edi
0x180090443  jnz     short loc_1800904A8
0x180090445  lea     rcx, [rsi+0D8h]; this
0x18009044c  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090451  mov     edi, eax
0x180090453  test    eax, eax
0x180090455  js      short loc_1800904AD
0x180090457  lea     rcx, [rsi+758h]; this
0x18009045e  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090463  mov     edi, eax
0x180090465  test    eax, eax
0x180090467  js      short loc_180090477
0x180090469  add     rcx, 68h ; 'h'
0x18009046d  mov     rdx, rbx
0x180090470  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180090475  mov     edi, eax
0x180090477  test    edi, edi
0x180090479  js      short loc_1800904AD
0x18009047b  mov     eax, cs:dword_18015B128
0x180090481  cmp     eax, 4
0x180090484  jbe     loc_18009050A
0x18009048a  mov     edx, 1
0x18009048f  lea     rcx, dword_18015B128
0x180090496  call    _tlgKeywordOn
0x18009049b  test    al, al
0x18009049d  jz      short loc_18009050A
0x18009049f  lea     rdx, word_1801357E6
0x1800904a6  jmp     short loc_1800904D4
0x1800904a8  mov     edi, 8001010Eh
0x1800904ad  mov     eax, cs:dword_18015B128
0x1800904b3  cmp     eax, 2
0x1800904b6  jbe     short loc_18009050A
0x1800904b8  mov     edx, 1
0x1800904bd  lea     rcx, dword_18015B128
0x1800904c4  call    _tlgKeywordOn
0x1800904c9  test    al, al
0x1800904cb  jz      short loc_18009050A
0x1800904cd  lea     rdx, byte_180135845
0x1800904d4  lea     rax, aDirectinkcores_22; "DirectInkCoreServer::remove_StrokesEras"...
0x1800904db  mov     [rsp+38h+arg_10], rax
0x1800904e0  lea     rax, [rsp+38h+arg_0]
0x1800904e5  mov     [rsp+38h+var_10], rax
0x1800904ea  lea     rax, [rsp+38h+arg_10]
0x1800904ef  mov     [rsp+38h+var_18], rax
0x1800904f4  xor     r9d, r9d
0x1800904f7  mov     [rsp+38h+arg_0], edi
0x1800904fb  xor     r8d, r8d
0x1800904fe  lea     rcx, dword_18015B128
0x180090505  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009050a  mov     rbx, [rsp+38h+arg_8]
0x18009050f  mov     eax, edi
0x180090511  mov     rsi, [rsp+38h+arg_18]
0x180090516  add     rsp, 30h
0x18009051a  pop     rdi
0x18009051b  retn
```
