# CCallbackHelper::InvokeHighContrastAdjustmentChanged(Windows::UI::Input::Inking::InkHighContrastAdjustment *)

- ea: `0x1800954f4`
- end: `0x1800956f9`
- name: `?InvokeHighContrastAdjustmentChanged@CCallbackHelper@@QEAAJPEAW4InkHighContrastAdjustment@Inking@Input@UI@Windows@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(CCallbackHelper *__hidden this, enum Windows::UI::Input::Inking::InkHighContrastAdjustment *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008fb50`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x18001043c`
- `0x1800207b0`
- `0x18002455c`
- `0x180032920`
- `0x18008b1e4`
- `0x180094490`
- `0x1800954f4`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009557d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095629`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009557d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095629`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009550f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009550f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCallbackHelper::InvokeHighContrastAdjustmentChanged(
        CCallbackHelper *this,
        enum Windows::UI::Input::Inking::InkHighContrastAdjustment *a2)
{
  int v4; // ebx
  int v5; // ebx
  char *v6; // r14
  __int64 v7; // rdi
  const wchar_t *v8; // rdi
  __int64 v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const wchar_t *v13; // rax
  __int64 v14; // r8
  PSRWLOCK v15; // rsi
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v18; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v21; // [rsp+B0h] [rbp+50h] BYREF
  PSRWLOCK v22; // [rsp+B8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() != v4 )
    return (unsigned int)-2147417842;
  v5 = CObjLifetime::CheckAlive(this);
  if ( v5 >= 0 )
  {
    if ( !a2 )
      return (unsigned int)-2147467261;
    v6 = (char *)this + 128;
    if ( *((_QWORD *)this + 16) )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 136);
      if ( *(_QWORD *)v6 )
        v7 = (__int64)(*(_QWORD *)(*(_QWORD *)v6 + 24LL) - *(_QWORD *)(*(_QWORD *)v6 + 16LL)) >> 3;
      else
        v7 = 0;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v7 )
      {
        Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::Internal::CHighContrastAdjustmentEventArgs,>(&v21);
        v8 = v21;
        if ( !v21 )
        {
          v5 = -2147024882;
          goto LABEL_27;
        }
        v5 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD))(*(_QWORD *)v21 + 64LL))(v21, *(unsigned int *)a2);
        if ( v5 >= 0 )
        {
          v18 = v8;
          v17 = *((_QWORD *)this + 4);
          v5 = 0;
          SRWLock = 0;
          Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v22, (char *)this + 136);
          Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&SRWLock, (char *)this + 128);
          if ( v22 )
            ReleaseSRWLockExclusive(v22);
          v15 = SRWLock;
          if ( SRWLock )
          {
            v19[0] = &v17;
            v19[1] = &v18;
            v5 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
                   v19,
                   SRWLock,
                   v6);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v15);
          }
          if ( v5 >= 0
            || (unsigned int)dword_18015B128 <= 2
            || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v14) )
          {
            goto LABEL_27;
          }
          v13 = L"spHighContrastAdjustmentEventArgs.InvokeAll";
        }
        else
        {
          if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v9) )
          {
LABEL_27:
            if ( v8 )
              (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v8 + 16LL))(v8);
            return (unsigned int)v5;
          }
          v13 = L"spHighContrastAdjustmentEventArgs->Initialize";
        }
        v21 = v13;
        v22 = (PSRWLOCK)L"CCallbackHelper::InvokeHighContrastAdjustmentChanged";
        LODWORD(SRWLock) = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)word_18013780A,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&SRWLock,
          (__int64)&v21);
        goto LABEL_27;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800954f4  push    rbp
0x1800954f6  push    rbx
0x1800954f7  push    rsi
0x1800954f8  push    rdi
0x1800954f9  push    r12
0x1800954fb  push    r14
0x1800954fd  push    r15
0x1800954ff  mov     rbp, rsp
0x180095502  sub     rsp, 60h
0x180095506  mov     r15, rdx
0x180095509  mov     rsi, rcx
0x18009550c  mov     ebx, [rcx+10h]
0x18009550f  call    cs:__imp_GetCurrentThreadId
0x180095515  cmp     eax, ebx
0x180095517  jnz     loc_1800956E3
0x18009551d  mov     rcx, rsi; this
0x180095520  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180095525  mov     ebx, eax
0x180095527  test    eax, eax
0x180095529  js      loc_1800956E8
0x18009552f  test    r15, r15
0x180095532  jnz     short loc_18009553E
0x180095534  mov     ebx, 80004003h
0x180095539  jmp     loc_1800956E8
0x18009553e  lea     r14, [rsi+80h]
0x180095545  cmp     qword ptr [r14], 0
0x180095549  jz      loc_1800956E8
0x18009554f  lea     rdx, [r14+8]
0x180095553  lea     rcx, [rbp+SRWLock]
0x180095557  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18009555c  mov     rax, [r14]
0x18009555f  test    rax, rax
0x180095562  jnz     short loc_180095568
0x180095564  xor     edi, edi
0x180095566  jmp     short loc_180095574
0x180095568  mov     rdi, [rax+18h]
0x18009556c  sub     rdi, [rax+10h]
0x180095570  sar     rdi, 3
0x180095574  mov     rcx, [rbp+SRWLock]; SRWLock
0x180095578  test    rcx, rcx
0x18009557b  jz      short loc_180095583
0x18009557d  call    cs:__imp_ReleaseSRWLockExclusive
0x180095583  test    rdi, rdi
0x180095586  jz      loc_1800956E8
0x18009558c  lea     rcx, [rbp+arg_10]
0x180095590  call    ??$Make@VCHighContrastAdjustmentEventArgs@Internal@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCHighContrastAdjustmentEventArgs@Internal@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::Internal::CHighContrastAdjustmentEventArgs,>(void)
0x180095595  nop
0x180095596  mov     rdi, [rbp+arg_10]
0x18009559a  test    rdi, rdi
0x18009559d  jnz     short loc_1800955A9
0x18009559f  mov     ebx, 8007000Eh
0x1800955a4  jmp     loc_1800956CC
0x1800955a9  mov     rax, [rdi]
0x1800955ac  mov     edx, [r15]
0x1800955af  mov     rcx, rdi
0x1800955b2  mov     rax, [rax+40h]
0x1800955b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955bb  mov     ebx, eax
0x1800955bd  test    eax, eax
0x1800955bf  jns     short loc_1800955F5
0x1800955c1  mov     ecx, cs:dword_18015B128
0x1800955c7  cmp     ecx, 2
0x1800955ca  jbe     loc_1800956CC
0x1800955d0  mov     edx, 100h
0x1800955d5  lea     rcx, dword_18015B128
0x1800955dc  call    _tlgKeywordOn
0x1800955e1  test    al, al
0x1800955e3  jz      loc_1800956CC
0x1800955e9  lea     rax, aSphighcontrast; "spHighContrastAdjustmentEventArgs->Init"...
0x1800955f0  jmp     loc_180095692
0x1800955f5  mov     [rbp+var_18], rdi
0x1800955f9  mov     rax, [rsi+20h]
0x1800955fd  mov     [rbp+var_20], rax
0x180095601  xor     ebx, ebx
0x180095603  mov     [rbp+SRWLock], rbx
0x180095607  lea     rdx, [r14+8]
0x18009560b  lea     rcx, [rbp+arg_18]
0x18009560f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180095614  mov     rdx, r14
0x180095617  lea     rcx, [rbp+SRWLock]
0x18009561b  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180095620  mov     rcx, [rbp+arg_18]; SRWLock
0x180095624  test    rcx, rcx
0x180095627  jz      short loc_18009562F
0x180095629  call    cs:__imp_ReleaseSRWLockExclusive
0x18009562f  mov     rsi, [rbp+SRWLock]
0x180095633  test    rsi, rsi
0x180095636  jz      short loc_180095667
0x180095638  lea     rax, [rbp+var_20]
0x18009563c  mov     [rbp+var_10], rax
0x180095640  lea     rax, [rbp+var_18]
0x180095644  mov     [rbp+var_8], rax
0x180095648  mov     r8, r14
0x18009564b  mov     rdx, rsi
0x18009564e  lea     rcx, [rbp+var_10]
0x180095652  call    ??$InvokeDelegates@V_lambda_9ad4557efc8539190f51ce7cff99b42a_@@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_9ad4557efc8539190f51ce7cff99b42a_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVInkPresenter@Inking@Input@UI@Windows@@PEAVInkStrokesCollectedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9ad4557efc8539190f51ce7cff99b42a_,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_9ad4557efc8539190f51ce7cff99b42a_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::InkPresenter *,Windows::UI::Input::Inking::InkStrokesCollectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180095657  mov     ebx, eax
0x180095659  test    rsi, rsi
0x18009565c  jz      short loc_180095667
0x18009565e  mov     rcx, rsi
0x180095661  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180095666  nop
0x180095667  test    ebx, ebx
0x180095669  jns     short loc_1800956CC
0x18009566b  mov     eax, cs:dword_18015B128
0x180095671  cmp     eax, 2
0x180095674  jbe     short loc_1800956CC
0x180095676  mov     edx, 100h
0x18009567b  lea     rcx, dword_18015B128
0x180095682  call    _tlgKeywordOn
0x180095687  test    al, al
0x180095689  jz      short loc_1800956CC
0x18009568b  lea     rax, aSphighcontrast_0; "spHighContrastAdjustmentEventArgs.Invok"...
0x180095692  mov     [rbp+arg_10], rax
0x180095696  lea     rax, aCcallbackhelpe_9; "CCallbackHelper::InvokeHighContrastAdju"...
0x18009569d  mov     [rbp+arg_18], rax
0x1800956a1  lea     rax, [rbp+arg_10]
0x1800956a5  mov     [rsp+60h+var_30], rax
0x1800956aa  lea     rax, [rbp+SRWLock]
0x1800956ae  mov     [rsp+60h+var_38], rax
0x1800956b3  lea     rax, [rbp+arg_18]
0x1800956b7  mov     [rsp+60h+var_40], rax
0x1800956bc  mov     dword ptr [rbp+SRWLock], ebx
0x1800956bf  lea     rdx, word_18013780A
0x1800956c6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800956cb  nop
0x1800956cc  test    rdi, rdi
0x1800956cf  jz      short loc_1800956E1
0x1800956d1  mov     rax, [rdi]
0x1800956d4  mov     rcx, rdi
0x1800956d7  mov     rax, [rax+10h]
0x1800956db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800956e0  nop
0x1800956e1  jmp     short loc_1800956E8
0x1800956e3  mov     ebx, 8001010Eh
0x1800956e8  mov     eax, ebx
0x1800956ea  add     rsp, 60h
0x1800956ee  pop     r15
0x1800956f0  pop     r14
0x1800956f2  pop     r12
0x1800956f4  pop     rdi
0x1800956f5  pop     rsi
0x1800956f6  pop     rbx
0x1800956f7  pop     rbp
0x1800956f8  retn
```
