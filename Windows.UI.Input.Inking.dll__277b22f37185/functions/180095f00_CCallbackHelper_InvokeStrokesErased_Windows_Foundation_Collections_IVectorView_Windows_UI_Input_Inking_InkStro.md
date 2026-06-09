# CCallbackHelper::InvokeStrokesErased(Windows::Foundation::Collections::IVectorView<Windows::UI::Input::Inking::InkStroke *> *)

- ea: `0x180095f00`
- end: `0x180096102`
- name: `?InvokeStrokesErased@CCallbackHelper@@QEAAJPEAU?$IVectorView@PEAVInkStroke@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(CObjLifetime *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dcf30`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x18001043c`
- `0x1800207b0`
- `0x18002455c`
- `0x180032920`
- `0x18008b1e4`
- `0x18009454c`
- `0x180095f00`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095f86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096032`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095f86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096032`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095f1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095f1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCallbackHelper::InvokeStrokesErased(CObjLifetime *this, __int64 a2)
{
  int v4; // ebx
  int v5; // ebx
  char *v7; // r14
  __int64 v8; // rdi
  const wchar_t *v9; // rdi
  __int64 v10; // r8
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const wchar_t *v14; // rax
  __int64 v15; // r8
  PSRWLOCK v16; // rsi
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v18; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v21; // [rsp+B0h] [rbp+50h] BYREF
  PSRWLOCK v22; // [rsp+B8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v4 )
  {
    v5 = CObjLifetime::CheckAlive(this);
    if ( v5 >= 0 )
    {
      if ( !a2 )
        return 2147500035LL;
      v7 = (char *)this + 104;
      if ( *((_QWORD *)this + 13) )
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 112);
        if ( *(_QWORD *)v7 )
          v8 = (__int64)(*(_QWORD *)(*(_QWORD *)v7 + 24LL) - *(_QWORD *)(*(_QWORD *)v7 + 16LL)) >> 3;
        else
          v8 = 0;
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        if ( v8 )
        {
          Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkErasedEventArgs,>(&v21);
          v9 = v21;
          if ( v21 )
          {
            v5 = (*(__int64 (__fastcall **)(const wchar_t *, __int64))(*(_QWORD *)v21 + 64LL))(v21, a2);
            if ( v5 >= 0 )
            {
              v18 = v9;
              v17 = *((_QWORD *)this + 4);
              v5 = 0;
              SRWLock = 0;
              Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v22, (char *)this + 112);
              Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&SRWLock, (char *)this + 104);
              if ( v22 )
                ReleaseSRWLockExclusive(v22);
              v16 = SRWLock;
              if ( SRWLock )
              {
                v19[0] = &v17;
                v19[1] = &v18;
                v5 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
                       v19,
                       SRWLock,
                       v7);
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v16);
              }
              if ( v5 >= 0
                || (unsigned int)dword_18015B128 <= 2
                || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v15) )
              {
                goto LABEL_27;
              }
              v14 = L"_evtStrokesErased.InvokeAll";
            }
            else
            {
              if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v10) )
                goto LABEL_27;
              v14 = L"spInkErasedEventArgs->Initialize";
            }
            v21 = v14;
            v22 = (PSRWLOCK)L"CCallbackHelper::InvokeStrokesErased";
            LODWORD(SRWLock) = v5;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v11,
              (unsigned int)word_18013780A,
              v12,
              v13,
              (__int64)&v22,
              (__int64)&SRWLock,
              (__int64)&v21);
          }
          else
          {
            v5 = -2147024882;
          }
LABEL_27:
          if ( v9 )
            (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147417842;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180095f00  push    rbp
0x180095f02  push    rbx
0x180095f03  push    rsi
0x180095f04  push    rdi
0x180095f05  push    r12
0x180095f07  push    r14
0x180095f09  push    r15
0x180095f0b  mov     rbp, rsp
0x180095f0e  sub     rsp, 60h
0x180095f12  mov     r15, rdx
0x180095f15  mov     rsi, rcx
0x180095f18  mov     ebx, [rcx+10h]
0x180095f1b  call    cs:__imp_GetCurrentThreadId
0x180095f21  cmp     eax, ebx
0x180095f23  jnz     loc_1800960EC
0x180095f29  mov     rcx, rsi; this
0x180095f2c  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180095f31  mov     ebx, eax
0x180095f33  test    eax, eax
0x180095f35  js      loc_1800960F1
0x180095f3b  test    r15, r15
0x180095f3e  jnz     short loc_180095F4A
0x180095f40  mov     eax, 80004003h
0x180095f45  jmp     loc_1800960F3
0x180095f4a  lea     r14, [rsi+68h]
0x180095f4e  cmp     qword ptr [r14], 0
0x180095f52  jz      loc_1800960F1
0x180095f58  lea     rdx, [r14+8]
0x180095f5c  lea     rcx, [rbp+SRWLock]
0x180095f60  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180095f65  mov     rax, [r14]
0x180095f68  test    rax, rax
0x180095f6b  jnz     short loc_180095F71
0x180095f6d  xor     edi, edi
0x180095f6f  jmp     short loc_180095F7D
0x180095f71  mov     rdi, [rax+18h]
0x180095f75  sub     rdi, [rax+10h]
0x180095f79  sar     rdi, 3
0x180095f7d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180095f81  test    rcx, rcx
0x180095f84  jz      short loc_180095F8C
0x180095f86  call    cs:__imp_ReleaseSRWLockExclusive
0x180095f8c  test    rdi, rdi
0x180095f8f  jz      loc_1800960F1
0x180095f95  lea     rcx, [rbp+arg_10]
0x180095f99  call    ??$Make@VCInkErasedEventArgs@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkErasedEventArgs@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkErasedEventArgs,>(void)
0x180095f9e  nop
0x180095f9f  mov     rdi, [rbp+arg_10]
0x180095fa3  test    rdi, rdi
0x180095fa6  jnz     short loc_180095FB2
0x180095fa8  mov     ebx, 8007000Eh
0x180095fad  jmp     loc_1800960D5
0x180095fb2  mov     rax, [rdi]
0x180095fb5  mov     rdx, r15
0x180095fb8  mov     rcx, rdi
0x180095fbb  mov     rax, [rax+40h]
0x180095fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095fc4  mov     ebx, eax
0x180095fc6  test    eax, eax
0x180095fc8  jns     short loc_180095FFE
0x180095fca  mov     ecx, cs:dword_18015B128
0x180095fd0  cmp     ecx, 2
0x180095fd3  jbe     loc_1800960D5
0x180095fd9  mov     edx, 100h
0x180095fde  lea     rcx, dword_18015B128
0x180095fe5  call    _tlgKeywordOn
0x180095fea  test    al, al
0x180095fec  jz      loc_1800960D5
0x180095ff2  lea     rax, aSpinkerasedeve; "spInkErasedEventArgs->Initialize"
0x180095ff9  jmp     loc_18009609B
0x180095ffe  mov     [rbp+var_18], rdi
0x180096002  mov     rax, [rsi+20h]
0x180096006  mov     [rbp+var_20], rax
0x18009600a  xor     ebx, ebx
0x18009600c  mov     [rbp+SRWLock], rbx
0x180096010  lea     rdx, [r14+8]
0x180096014  lea     rcx, [rbp+arg_18]
0x180096018  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18009601d  mov     rdx, r14
0x180096020  lea     rcx, [rbp+SRWLock]
0x180096024  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180096029  mov     rcx, [rbp+arg_18]; SRWLock
0x18009602d  test    rcx, rcx
0x180096030  jz      short loc_180096038
0x180096032  call    cs:__imp_ReleaseSRWLockExclusive
0x180096038  mov     rsi, [rbp+SRWLock]
0x18009603c  test    rsi, rsi
0x18009603f  jz      short loc_180096070
0x180096041  lea     rax, [rbp+var_20]
0x180096045  mov     [rbp+var_10], rax
0x180096049  lea     rax, [rbp+var_18]
0x18009604d  mov     [rbp+var_8], rax
0x180096051  mov     r8, r14
0x180096054  mov     rdx, rsi
0x180096057  lea     rcx, [rbp+var_10]
0x18009605b  call    ??$InvokeDelegates@V_lambda_9ad4557efc8539190f51ce7cff99b42a_@@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_9ad4557efc8539190f51ce7cff99b42a_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_9ad4557efc8539190f51ce7cff99b42a_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180096060  mov     ebx, eax
0x180096062  test    rsi, rsi
0x180096065  jz      short loc_180096070
0x180096067  mov     rcx, rsi
0x18009606a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18009606f  nop
0x180096070  test    ebx, ebx
0x180096072  jns     short loc_1800960D5
0x180096074  mov     eax, cs:dword_18015B128
0x18009607a  cmp     eax, 2
0x18009607d  jbe     short loc_1800960D5
0x18009607f  mov     edx, 100h
0x180096084  lea     rcx, dword_18015B128
0x18009608b  call    _tlgKeywordOn
0x180096090  test    al, al
0x180096092  jz      short loc_1800960D5
0x180096094  lea     rax, aEvtstrokeseras; "_evtStrokesErased.InvokeAll"
0x18009609b  mov     [rbp+arg_10], rax
0x18009609f  lea     rax, aCcallbackhelpe_1; "CCallbackHelper::InvokeStrokesErased"
0x1800960a6  mov     [rbp+arg_18], rax
0x1800960aa  lea     rax, [rbp+arg_10]
0x1800960ae  mov     [rsp+60h+var_30], rax
0x1800960b3  lea     rax, [rbp+SRWLock]
0x1800960b7  mov     [rsp+60h+var_38], rax
0x1800960bc  lea     rax, [rbp+arg_18]
0x1800960c0  mov     [rsp+60h+var_40], rax
0x1800960c5  mov     dword ptr [rbp+SRWLock], ebx
0x1800960c8  lea     rdx, word_18013780A
0x1800960cf  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800960d4  nop
0x1800960d5  test    rdi, rdi
0x1800960d8  jz      short loc_1800960EA
0x1800960da  mov     rax, [rdi]
0x1800960dd  mov     rcx, rdi
0x1800960e0  mov     rax, [rax+10h]
0x1800960e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800960e9  nop
0x1800960ea  jmp     short loc_1800960F1
0x1800960ec  mov     ebx, 8001010Eh
0x1800960f1  mov     eax, ebx
0x1800960f3  add     rsp, 60h
0x1800960f7  pop     r15
0x1800960f9  pop     r14
0x1800960fb  pop     r12
0x1800960fd  pop     rdi
0x1800960fe  pop     rsi
0x1800960ff  pop     rbx
0x180096100  pop     rbp
0x180096101  retn
```
