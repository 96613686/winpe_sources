# Windows::UI::Input::Inking::DirectInkCoreServer::add_CommitNeeded(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,IInspectable *> *,EventRegistrationToken *)

- ea: `0x18008eed0`
- end: `0x18008efba`
- name: `?add_CommitNeeded@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@5@PEAUEventRegistrationToken@@@Z`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x18008b1e4`
- `0x18008eed0`
- `0x180096ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008eeeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008eeeb`

## string_xrefs

- `0x18008ef75`: `DirectInkCoreServer::add_CommitNeeded[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::add_CommitNeeded(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // ebx
  __int64 v7; // r8
  int v8; // ebx
  char *v9; // rdx
  int v11; // [rsp+50h] [rbp+8h] BYREF
  const wchar_t *v12; // [rsp+68h] [rbp+20h] BYREF

  v3 = *(_DWORD *)(a1 + 2784);
  if ( GetCurrentThreadId() == v3 )
  {
    v8 = CObjLifetime::CheckAlive((CObjLifetime *)(a1 + 104));
    if ( v8 >= 0 )
    {
      v8 = CCallbackHelper::add_CommitNeeded(a1 + 1768, a2, a3);
      if ( v8 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
        {
          v9 = byte_18013558B;
LABEL_11:
          v12 = L"DirectInkCoreServer::add_CommitNeeded[Exit]";
          v11 = v8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18015B128,
            (_DWORD)v9,
            0,
            0,
            (__int64)&v12,
            (__int64)&v11);
          return (unsigned int)v8;
        }
        return (unsigned int)v8;
      }
    }
  }
  else
  {
    v8 = -2147417842;
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v7) )
  {
    v9 = byte_1801354C1;
    goto LABEL_11;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008eed0  mov     [rsp+arg_8], rbx
0x18008eed5  push    rbp
0x18008eed6  push    rsi
0x18008eed7  push    rdi
0x18008eed8  sub     rsp, 30h
0x18008eedc  mov     ebx, [rcx+0AE0h]
0x18008eee2  mov     rsi, r8
0x18008eee5  mov     rbp, rdx
0x18008eee8  mov     rdi, rcx
0x18008eeeb  call    cs:__imp_GetCurrentThreadId
0x18008eef1  cmp     eax, ebx
0x18008eef3  jnz     short loc_18008EF49
0x18008eef5  lea     rcx, [rdi+68h]; this
0x18008eef9  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008eefe  mov     ebx, eax
0x18008ef00  test    eax, eax
0x18008ef02  js      short loc_18008EF4E
0x18008ef04  lea     rcx, [rdi+6E8h]
0x18008ef0b  mov     r8, rsi
0x18008ef0e  mov     rdx, rbp
0x18008ef11  call    ?add_CommitNeeded@CCallbackHelper@@QEAAJPEAU?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; CCallbackHelper::add_CommitNeeded(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,IInspectable *> *,EventRegistrationToken *)
0x18008ef16  mov     ebx, eax
0x18008ef18  test    eax, eax
0x18008ef1a  js      short loc_18008EF4E
0x18008ef1c  mov     ecx, cs:dword_18015B128
0x18008ef22  cmp     ecx, 4
0x18008ef25  jbe     loc_18008EFAB
0x18008ef2b  mov     edx, 1
0x18008ef30  lea     rcx, dword_18015B128
0x18008ef37  call    _tlgKeywordOn
0x18008ef3c  test    al, al
0x18008ef3e  jz      short loc_18008EFAB
0x18008ef40  lea     rdx, byte_18013558B
0x18008ef47  jmp     short loc_18008EF75
0x18008ef49  mov     ebx, 8001010Eh
0x18008ef4e  mov     eax, cs:dword_18015B128
0x18008ef54  cmp     eax, 2
0x18008ef57  jbe     short loc_18008EFAB
0x18008ef59  mov     edx, 1
0x18008ef5e  lea     rcx, dword_18015B128
0x18008ef65  call    _tlgKeywordOn
0x18008ef6a  test    al, al
0x18008ef6c  jz      short loc_18008EFAB
0x18008ef6e  lea     rdx, byte_1801354C1
0x18008ef75  lea     rax, aDirectinkcores_4; "DirectInkCoreServer::add_CommitNeeded[E"...
0x18008ef7c  mov     [rsp+48h+arg_18], rax
0x18008ef81  lea     rax, [rsp+48h+arg_0]
0x18008ef86  mov     [rsp+48h+var_20], rax
0x18008ef8b  lea     rax, [rsp+48h+arg_18]
0x18008ef90  mov     [rsp+48h+var_28], rax
0x18008ef95  xor     r9d, r9d
0x18008ef98  mov     [rsp+48h+arg_0], ebx
0x18008ef9c  xor     r8d, r8d
0x18008ef9f  lea     rcx, dword_18015B128
0x18008efa6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008efab  mov     eax, ebx
0x18008efad  mov     rbx, [rsp+48h+arg_8]
0x18008efb2  add     rsp, 30h
0x18008efb6  pop     rdi
0x18008efb7  pop     rsi
0x18008efb8  pop     rbp
0x18008efb9  retn
```
