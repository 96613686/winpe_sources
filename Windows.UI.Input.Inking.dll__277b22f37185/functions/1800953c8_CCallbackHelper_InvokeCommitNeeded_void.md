# CCallbackHelper::InvokeCommitNeeded(void)

- ea: `0x1800953c8`
- end: `0x1800954ed`
- name: `?InvokeCommitNeeded@CCallbackHelper@@QEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(CCallbackHelper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009b400`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x18001043c`
- `0x1800207b0`
- `0x18002455c`
- `0x180032920`
- `0x18008b1e4`
- `0x1800953c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095439`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800953da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800953da`

## string_xrefs

- `0x1800954a9`: `CCallbackHelper::InvokeCommitNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCallbackHelper::InvokeCommitNeeded(CCallbackHelper *this)
{
  int v2; // ebx
  int v3; // ebx
  char *v4; // rsi
  __int64 v5; // r8
  __int64 v6; // rdi
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  _QWORD v11[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v12; // [rsp+80h] [rbp+28h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+30h] BYREF
  const wchar_t *v14; // [rsp+90h] [rbp+38h] BYREF
  __int64 v15; // [rsp+98h] [rbp+40h] BYREF

  v2 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v2 )
  {
    v3 = CObjLifetime::CheckAlive(this);
    if ( v3 >= 0 )
    {
      v4 = (char *)this + 152;
      v15 = 0;
      v14 = (const wchar_t *)*((_QWORD *)this + 4);
      v3 = 0;
      v12 = 0;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 160);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v12, (char *)this + 152);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v6 = v12;
      if ( v12 )
      {
        v11[0] = &v14;
        v11[1] = &v15;
        v3 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
               v11,
               v12,
               v4);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v6);
      }
      if ( v3 < 0 && (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v5) )
      {
        SRWLock = (PSRWLOCK)L"InvokeAll";
        LODWORD(v12) = v3;
        v14 = L"CCallbackHelper::InvokeCommitNeeded";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v7,
          (unsigned int)word_18013780A,
          v8,
          v9,
          (__int64)&v14,
          (__int64)&v12,
          (__int64)&SRWLock);
      }
    }
  }
  else
  {
    return (unsigned int)-2147417842;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800953c8  push    rbp
0x1800953ca  push    rbx
0x1800953cb  push    rsi
0x1800953cc  push    rdi
0x1800953cd  mov     rbp, rsp
0x1800953d0  sub     rsp, 58h
0x1800953d4  mov     rdi, rcx
0x1800953d7  mov     ebx, [rcx+10h]
0x1800953da  call    cs:__imp_GetCurrentThreadId
0x1800953e0  cmp     eax, ebx
0x1800953e2  jnz     loc_1800954DD
0x1800953e8  mov     rcx, rdi; this
0x1800953eb  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x1800953f0  mov     ebx, eax
0x1800953f2  test    eax, eax
0x1800953f4  js      loc_1800954E2
0x1800953fa  lea     rsi, [rdi+98h]
0x180095401  mov     [rbp+arg_18], 0
0x180095409  mov     rax, [rdi+20h]
0x18009540d  mov     [rbp+arg_10], rax
0x180095411  xor     ebx, ebx
0x180095413  mov     [rbp+arg_0], rbx
0x180095417  lea     rdx, [rsi+8]
0x18009541b  lea     rcx, [rbp+SRWLock]
0x18009541f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180095424  mov     rdx, rsi
0x180095427  lea     rcx, [rbp+arg_0]
0x18009542b  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180095430  mov     rcx, [rbp+SRWLock]; SRWLock
0x180095434  test    rcx, rcx
0x180095437  jz      short loc_18009543F
0x180095439  call    cs:__imp_ReleaseSRWLockExclusive
0x18009543f  mov     rdi, [rbp+arg_0]
0x180095443  test    rdi, rdi
0x180095446  jz      short loc_180095477
0x180095448  lea     rax, [rbp+arg_10]
0x18009544c  mov     [rbp+var_18], rax
0x180095450  lea     rax, [rbp+arg_18]
0x180095454  mov     [rbp+var_10], rax
0x180095458  mov     r8, rsi
0x18009545b  mov     rdx, rdi
0x18009545e  lea     rcx, [rbp+var_18]
0x180095462  call    ??$InvokeDelegates@V_lambda_9ad4557efc8539190f51ce7cff99b42a_@@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_9ad4557efc8539190f51ce7cff99b42a_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_9ad4557efc8539190f51ce7cff99b42a_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180095467  mov     ebx, eax
0x180095469  test    rdi, rdi
0x18009546c  jz      short loc_180095477
0x18009546e  mov     rcx, rdi
0x180095471  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180095476  nop
0x180095477  test    ebx, ebx
0x180095479  jns     short loc_1800954E2
0x18009547b  mov     eax, cs:dword_18015B128
0x180095481  cmp     eax, 2
0x180095484  jbe     short loc_1800954E2
0x180095486  mov     edx, 100h
0x18009548b  lea     rcx, dword_18015B128
0x180095492  call    _tlgKeywordOn
0x180095497  test    al, al
0x180095499  jz      short loc_1800954E2
0x18009549b  lea     rax, aInvokeall; "InvokeAll"
0x1800954a2  mov     [rbp+SRWLock], rax
0x1800954a6  mov     dword ptr [rbp+arg_0], ebx
0x1800954a9  lea     rax, aCcallbackhelpe; "CCallbackHelper::InvokeCommitNeeded"
0x1800954b0  mov     [rbp+arg_10], rax
0x1800954b4  lea     rax, [rbp+SRWLock]
0x1800954b8  mov     [rsp+58h+var_28], rax
0x1800954bd  lea     rax, [rbp+arg_0]
0x1800954c1  mov     [rsp+58h+var_30], rax
0x1800954c6  lea     rax, [rbp+arg_10]
0x1800954ca  mov     [rsp+58h+var_38], rax
0x1800954cf  lea     rdx, word_18013780A
0x1800954d6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800954db  jmp     short loc_1800954E2
0x1800954dd  mov     ebx, 8001010Eh
0x1800954e2  mov     eax, ebx
0x1800954e4  add     rsp, 58h
0x1800954e8  pop     rdi
0x1800954e9  pop     rsi
0x1800954ea  pop     rbx
0x1800954eb  pop     rbp
0x1800954ec  retn
```
