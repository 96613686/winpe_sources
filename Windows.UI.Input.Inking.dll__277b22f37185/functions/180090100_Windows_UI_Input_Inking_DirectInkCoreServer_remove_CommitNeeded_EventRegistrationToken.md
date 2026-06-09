# Windows::UI::Input::Inking::DirectInkCoreServer::remove_CommitNeeded(EventRegistrationToken)

- ea: `0x180090100`
- end: `0x1800901fc`
- name: `?remove_CommitNeeded@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJUEventRegistrationToken@@@Z`
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
- `0x180090100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009011b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009011b`

## string_xrefs

- `0x1800901b4`: `DirectInkCoreServer::remove_CommitNeeded[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::remove_CommitNeeded(
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

  v2 = *((_DWORD *)this + 696);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 104));
    if ( v6 >= 0 )
    {
      v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 1768));
      if ( v6 >= 0 )
        v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v7 + 152,
               a2.value);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v8 = &word_1801352BE;
LABEL_13:
          v11 = L"DirectInkCoreServer::remove_CommitNeeded[Exit]";
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
    v8 = (__int16 *)&dword_18013531C;
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090100  mov     [rsp+arg_8], rbx
0x180090105  mov     [rsp+arg_18], rsi
0x18009010a  push    rdi
0x18009010b  sub     rsp, 30h
0x18009010f  mov     edi, [rcx+0AE0h]
0x180090115  mov     rbx, rdx
0x180090118  mov     rsi, rcx
0x18009011b  call    cs:__imp_GetCurrentThreadId
0x180090121  cmp     eax, edi
0x180090123  jnz     short loc_180090188
0x180090125  lea     rcx, [rsi+68h]; this
0x180090129  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18009012e  mov     edi, eax
0x180090130  test    eax, eax
0x180090132  js      short loc_18009018D
0x180090134  lea     rcx, [rsi+6E8h]; this
0x18009013b  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180090140  mov     edi, eax
0x180090142  test    eax, eax
0x180090144  js      short loc_180090157
0x180090146  add     rcx, 98h
0x18009014d  mov     rdx, rbx
0x180090150  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180090155  mov     edi, eax
0x180090157  test    edi, edi
0x180090159  js      short loc_18009018D
0x18009015b  mov     eax, cs:dword_18015B128
0x180090161  cmp     eax, 4
0x180090164  jbe     loc_1800901EA
0x18009016a  mov     edx, 1
0x18009016f  lea     rcx, dword_18015B128
0x180090176  call    _tlgKeywordOn
0x18009017b  test    al, al
0x18009017d  jz      short loc_1800901EA
0x18009017f  lea     rdx, word_1801352BE
0x180090186  jmp     short loc_1800901B4
0x180090188  mov     edi, 8001010Eh
0x18009018d  mov     eax, cs:dword_18015B128
0x180090193  cmp     eax, 2
0x180090196  jbe     short loc_1800901EA
0x180090198  mov     edx, 1
0x18009019d  lea     rcx, dword_18015B128
0x1800901a4  call    _tlgKeywordOn
0x1800901a9  test    al, al
0x1800901ab  jz      short loc_1800901EA
0x1800901ad  lea     rdx, dword_18013531C
0x1800901b4  lea     rax, aDirectinkcores_1; "DirectInkCoreServer::remove_CommitNeede"...
0x1800901bb  mov     [rsp+38h+arg_10], rax
0x1800901c0  lea     rax, [rsp+38h+arg_0]
0x1800901c5  mov     [rsp+38h+var_10], rax
0x1800901ca  lea     rax, [rsp+38h+arg_10]
0x1800901cf  mov     [rsp+38h+var_18], rax
0x1800901d4  xor     r9d, r9d
0x1800901d7  mov     [rsp+38h+arg_0], edi
0x1800901db  xor     r8d, r8d
0x1800901de  lea     rcx, dword_18015B128
0x1800901e5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800901ea  mov     rbx, [rsp+38h+arg_8]
0x1800901ef  mov     eax, edi
0x1800901f1  mov     rsi, [rsp+38h+arg_18]
0x1800901f6  add     rsp, 30h
0x1800901fa  pop     rdi
0x1800901fb  retn
```
