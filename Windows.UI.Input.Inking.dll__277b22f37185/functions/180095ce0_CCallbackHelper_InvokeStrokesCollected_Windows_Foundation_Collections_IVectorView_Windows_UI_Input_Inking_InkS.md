# CCallbackHelper::InvokeStrokesCollected(Windows::Foundation::Collections::IVectorView<Windows::UI::Input::Inking::InkStroke *> *)

- ea: `0x180095ce0`
- end: `0x180095efa`
- name: `?InvokeStrokesCollected@CCallbackHelper@@QEAAJPEAU?$IVectorView@PEAVInkStroke@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(CObjLifetime *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800da0e0`
- `0x1800dd400`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x18001043c`
- `0x1800207b0`
- `0x18002455c`
- `0x180032920`
- `0x18008b1e4`
- `0x180094610`
- `0x180095ce0`
- `0x180097f20`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095d7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095e2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095d7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095cfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCallbackHelper::InvokeStrokesCollected(CObjLifetime *this, __int64 a2)
{
  int v4; // ebx
  int v5; // ebx
  CAsyncInputMgr *v7; // rcx
  char *v8; // r14
  __int64 v9; // rdi
  const wchar_t *v10; // rdi
  __int64 v11; // r8
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const wchar_t *v15; // rax
  __int64 v16; // r8
  PSRWLOCK v17; // rsi
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v19; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v22; // [rsp+B0h] [rbp+50h] BYREF
  PSRWLOCK v23; // [rsp+B8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v4 )
  {
    v5 = CObjLifetime::CheckAlive(this);
    if ( v5 >= 0 )
    {
      if ( !a2 )
        return 2147500035LL;
      v7 = (CAsyncInputMgr *)*((_QWORD *)this + 3);
      if ( !v7 || (v5 = CAsyncInputMgr::DeliverInput(v7), v5 >= 0) )
      {
        v8 = (char *)this + 80;
        if ( *((_QWORD *)this + 10) )
        {
          Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 88);
          if ( *(_QWORD *)v8 )
            v9 = (__int64)(*(_QWORD *)(*(_QWORD *)v8 + 24LL) - *(_QWORD *)(*(_QWORD *)v8 + 16LL)) >> 3;
          else
            v9 = 0;
          if ( SRWLock )
            ReleaseSRWLockExclusive(SRWLock);
          if ( v9 )
          {
            Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkEventArgs,>(&v22);
            v10 = v22;
            if ( v22 )
            {
              v5 = (*(__int64 (__fastcall **)(const wchar_t *, __int64))(*(_QWORD *)v22 + 64LL))(v22, a2);
              if ( v5 >= 0 )
              {
                v19 = v10;
                v18 = *((_QWORD *)this + 4);
                v5 = 0;
                SRWLock = 0;
                Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v23, (char *)this + 88);
                Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
                  &SRWLock,
                  (char *)this + 80);
                if ( v23 )
                  ReleaseSRWLockExclusive(v23);
                v17 = SRWLock;
                if ( SRWLock )
                {
                  v20[0] = &v18;
                  v20[1] = &v19;
                  v5 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
                         v20,
                         SRWLock,
                         v8);
                  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v17);
                }
                if ( v5 >= 0
                  || (unsigned int)dword_18015B128 <= 2
                  || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v16) )
                {
                  goto LABEL_29;
                }
                v15 = L"_evtStrokesCollected.InvokeAll";
              }
              else
              {
                if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v11) )
                  goto LABEL_29;
                v15 = L"spInkEventArgs->Initialize";
              }
              v22 = v15;
              v23 = (PSRWLOCK)L"CCallbackHelper::InvokeStrokesCollected";
              LODWORD(SRWLock) = v5;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v12,
                (unsigned int)word_18013780A,
                v13,
                v14,
                (__int64)&v23,
                (__int64)&SRWLock,
                (__int64)&v22);
            }
            else
            {
              v5 = -2147024882;
            }
LABEL_29:
            if ( v10 )
              (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v10 + 16LL))(v10);
          }
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
0x180095ce0  push    rbp
0x180095ce2  push    rbx
0x180095ce3  push    rsi
0x180095ce4  push    rdi
0x180095ce5  push    r12
0x180095ce7  push    r14
0x180095ce9  push    r15
0x180095ceb  mov     rbp, rsp
0x180095cee  sub     rsp, 60h
0x180095cf2  mov     r15, rdx
0x180095cf5  mov     rsi, rcx
0x180095cf8  mov     ebx, [rcx+10h]
0x180095cfb  call    cs:__imp_GetCurrentThreadId
0x180095d01  cmp     eax, ebx
0x180095d03  jnz     loc_180095EE4
0x180095d09  mov     rcx, rsi; this
0x180095d0c  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180095d11  mov     ebx, eax
0x180095d13  test    eax, eax
0x180095d15  js      loc_180095EE9
0x180095d1b  test    r15, r15
0x180095d1e  jnz     short loc_180095D2A
0x180095d20  mov     eax, 80004003h
0x180095d25  jmp     loc_180095EEB
0x180095d2a  mov     rcx, [rsi+18h]; this
0x180095d2e  test    rcx, rcx
0x180095d31  jz      short loc_180095D42
0x180095d33  call    ?DeliverInput@CAsyncInputMgr@@QEAAJXZ; CAsyncInputMgr::DeliverInput(void)
0x180095d38  mov     ebx, eax
0x180095d3a  test    eax, eax
0x180095d3c  js      loc_180095EE9
0x180095d42  lea     r14, [rsi+50h]
0x180095d46  cmp     qword ptr [r14], 0
0x180095d4a  jz      loc_180095EE9
0x180095d50  lea     rdx, [r14+8]
0x180095d54  lea     rcx, [rbp+SRWLock]
0x180095d58  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180095d5d  mov     rax, [r14]
0x180095d60  test    rax, rax
0x180095d63  jnz     short loc_180095D69
0x180095d65  xor     edi, edi
0x180095d67  jmp     short loc_180095D75
0x180095d69  mov     rdi, [rax+18h]
0x180095d6d  sub     rdi, [rax+10h]
0x180095d71  sar     rdi, 3
0x180095d75  mov     rcx, [rbp+SRWLock]; SRWLock
0x180095d79  test    rcx, rcx
0x180095d7c  jz      short loc_180095D84
0x180095d7e  call    cs:__imp_ReleaseSRWLockExclusive
0x180095d84  test    rdi, rdi
0x180095d87  jz      loc_180095EE9
0x180095d8d  lea     rcx, [rbp+arg_10]
0x180095d91  call    ??$Make@VCInkEventArgs@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkEventArgs@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkEventArgs,>(void)
0x180095d96  nop
0x180095d97  mov     rdi, [rbp+arg_10]
0x180095d9b  test    rdi, rdi
0x180095d9e  jnz     short loc_180095DAA
0x180095da0  mov     ebx, 8007000Eh
0x180095da5  jmp     loc_180095ECD
0x180095daa  mov     rax, [rdi]
0x180095dad  mov     rdx, r15
0x180095db0  mov     rcx, rdi
0x180095db3  mov     rax, [rax+40h]
0x180095db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095dbc  mov     ebx, eax
0x180095dbe  test    eax, eax
0x180095dc0  jns     short loc_180095DF6
0x180095dc2  mov     ecx, cs:dword_18015B128
0x180095dc8  cmp     ecx, 2
0x180095dcb  jbe     loc_180095ECD
0x180095dd1  mov     edx, 100h
0x180095dd6  lea     rcx, dword_18015B128
0x180095ddd  call    _tlgKeywordOn
0x180095de2  test    al, al
0x180095de4  jz      loc_180095ECD
0x180095dea  lea     rax, aSpinkeventargs; "spInkEventArgs->Initialize"
0x180095df1  jmp     loc_180095E93
0x180095df6  mov     [rbp+var_18], rdi
0x180095dfa  mov     rax, [rsi+20h]
0x180095dfe  mov     [rbp+var_20], rax
0x180095e02  xor     ebx, ebx
0x180095e04  mov     [rbp+SRWLock], rbx
0x180095e08  lea     rdx, [r14+8]
0x180095e0c  lea     rcx, [rbp+arg_18]
0x180095e10  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180095e15  mov     rdx, r14
0x180095e18  lea     rcx, [rbp+SRWLock]
0x180095e1c  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180095e21  mov     rcx, [rbp+arg_18]; SRWLock
0x180095e25  test    rcx, rcx
0x180095e28  jz      short loc_180095E30
0x180095e2a  call    cs:__imp_ReleaseSRWLockExclusive
0x180095e30  mov     rsi, [rbp+SRWLock]
0x180095e34  test    rsi, rsi
0x180095e37  jz      short loc_180095E68
0x180095e39  lea     rax, [rbp+var_20]
0x180095e3d  mov     [rbp+var_10], rax
0x180095e41  lea     rax, [rbp+var_18]
0x180095e45  mov     [rbp+var_8], rax
0x180095e49  mov     r8, r14
0x180095e4c  mov     rdx, rsi
0x180095e4f  lea     rcx, [rbp+var_10]
0x180095e53  call    ??$InvokeDelegates@V_lambda_9ad4557efc8539190f51ce7cff99b42a_@@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_9ad4557efc8539190f51ce7cff99b42a_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_9ad4557efc8539190f51ce7cff99b42a_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180095e58  mov     ebx, eax
0x180095e5a  test    rsi, rsi
0x180095e5d  jz      short loc_180095E68
0x180095e5f  mov     rcx, rsi
0x180095e62  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180095e67  nop
0x180095e68  test    ebx, ebx
0x180095e6a  jns     short loc_180095ECD
0x180095e6c  mov     eax, cs:dword_18015B128
0x180095e72  cmp     eax, 2
0x180095e75  jbe     short loc_180095ECD
0x180095e77  mov     edx, 100h
0x180095e7c  lea     rcx, dword_18015B128
0x180095e83  call    _tlgKeywordOn
0x180095e88  test    al, al
0x180095e8a  jz      short loc_180095ECD
0x180095e8c  lea     rax, aEvtstrokescoll; "_evtStrokesCollected.InvokeAll"
0x180095e93  mov     [rbp+arg_10], rax
0x180095e97  lea     rax, aCcallbackhelpe_2; "CCallbackHelper::InvokeStrokesCollected"
0x180095e9e  mov     [rbp+arg_18], rax
0x180095ea2  lea     rax, [rbp+arg_10]
0x180095ea6  mov     [rsp+60h+var_30], rax
0x180095eab  lea     rax, [rbp+SRWLock]
0x180095eaf  mov     [rsp+60h+var_38], rax
0x180095eb4  lea     rax, [rbp+arg_18]
0x180095eb8  mov     [rsp+60h+var_40], rax
0x180095ebd  mov     dword ptr [rbp+SRWLock], ebx
0x180095ec0  lea     rdx, word_18013780A
0x180095ec7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180095ecc  nop
0x180095ecd  test    rdi, rdi
0x180095ed0  jz      short loc_180095EE2
0x180095ed2  mov     rax, [rdi]
0x180095ed5  mov     rcx, rdi
0x180095ed8  mov     rax, [rax+10h]
0x180095edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ee1  nop
0x180095ee2  jmp     short loc_180095EE9
0x180095ee4  mov     ebx, 8001010Eh
0x180095ee9  mov     eax, ebx
0x180095eeb  add     rsp, 60h
0x180095eef  pop     r15
0x180095ef1  pop     r14
0x180095ef3  pop     r12
0x180095ef5  pop     rdi
0x180095ef6  pop     rsi
0x180095ef7  pop     rbx
0x180095ef8  pop     rbp
0x180095ef9  retn
```
