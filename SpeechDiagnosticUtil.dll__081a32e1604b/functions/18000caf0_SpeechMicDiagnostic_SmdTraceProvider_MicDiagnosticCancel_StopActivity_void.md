# SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel::StopActivity(void)

- ea: `0x18000caf0`
- end: `0x18000cd73`
- name: `?StopActivity@MicDiagnosticCancel@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000caf0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cb4a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ccef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cb4a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ccef`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd0b`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd0b`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // r9d
  _DWORD *v7; // rdi
  __int64 v8; // r8
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v13; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v14; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v5 > 5u )
    {
      v13 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = *((_QWORD *)v4 + 15);
      v15 = *((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = *((_QWORD *)v4 + 12);
      v17 = *((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = *((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = *((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = *((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = *((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&word_1800146B6,
        *((_QWORD *)this + 34) + 8,
        v6,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v11,
        (__int64)&v20,
        (__int64)&v10,
        (__int64)&v19,
        (__int64)&v9,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        (__int64)&v13);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v7 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v8 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)&dword_180014804,
        v8 + 8,
        0,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000caf0  push    rbp
0x18000caf2  push    rbx
0x18000caf3  push    rdi
0x18000caf4  lea     rbp, [rsp+10h]
0x18000caf9  sub     rsp, 130h
0x18000cb00  mov     rbx, rcx
0x18000cb03  mov     rdi, [rcx+110h]
0x18000cb0a  mov     eax, [rdi+48h]
0x18000cb0d  test    eax, eax
0x18000cb0f  jns     loc_18000CCD0
0x18000cb15  add     rdi, 50h ; 'P'
0x18000cb19  cmp     eax, [rdi+8]
0x18000cb1c  jnz     loc_18000CCD0
0x18000cb22  test    rdi, rdi
0x18000cb25  jz      loc_18000CCD0
0x18000cb2b  lea     rdx, [rbp+SRWLock]
0x18000cb2f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cb34  mov     rax, [rbx+110h]
0x18000cb3b  mov     dword ptr [rax], 2
0x18000cb41  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000cb45  test    rcx, rcx
0x18000cb48  jz      short loc_18000CB56
0x18000cb4a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb51  nop     dword ptr [rax+rax+00h]
0x18000cb56  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000cb5b  mov     rcx, [rax+8]
0x18000cb5f  mov     eax, [rcx]
0x18000cb61  cmp     eax, 5
0x18000cb64  jbe     loc_18000CD61
0x18000cb6a  mov     rax, [rdi+30h]
0x18000cb6e  mov     [rbp+var_70], rax
0x18000cb72  mov     eax, [rdi+44h]
0x18000cb75  mov     dword ptr [rbp+SRWLock], eax
0x18000cb78  mov     eax, [rdi+10h]
0x18000cb7b  mov     [rbp+arg_8], eax
0x18000cb7e  mov     rax, [rdi+78h]
0x18000cb82  mov     [rbp+var_68], rax
0x18000cb86  mov     rax, [rdi+70h]
0x18000cb8a  mov     [rbp+var_60], rax
0x18000cb8e  mov     eax, [rdi+68h]
0x18000cb91  mov     dword ptr [rbp+arg_10], eax
0x18000cb94  mov     rax, [rdi+60h]
0x18000cb98  mov     [rbp+var_58], rax
0x18000cb9c  mov     rax, [rdi+58h]
0x18000cba0  mov     [rbp+var_50], rax
0x18000cba4  mov     eax, [rdi+50h]
0x18000cba7  mov     [rbp+arg_18], eax
0x18000cbaa  mov     rax, [rdi+48h]
0x18000cbae  mov     [rbp+var_48], rax
0x18000cbb2  mov     eax, [rdi+20h]
0x18000cbb5  mov     [rbp+var_80], eax
0x18000cbb8  mov     rax, [rdi+18h]
0x18000cbbc  mov     [rbp+var_40], rax
0x18000cbc0  mov     eax, [rdi]
0x18000cbc2  mov     [rbp+var_7C], eax
0x18000cbc5  mov     rax, [rdi+80h]
0x18000cbcc  mov     [rbp+var_38], rax
0x18000cbd0  mov     eax, [rdi+40h]
0x18000cbd3  mov     [rbp+var_78], eax
0x18000cbd6  mov     rax, [rdi+38h]
0x18000cbda  mov     [rbp+var_30], rax
0x18000cbde  mov     eax, [rdi+8]
0x18000cbe1  mov     [rbp+var_74], eax
0x18000cbe4  mov     [rbp+var_28], 1000000h
0x18000cbec  mov     [rbp+var_20], 0
0x18000cbf4  mov     r8, [rbx+110h]
0x18000cbfb  add     r8, 8
0x18000cbff  lea     rax, [rbp+var_70]
0x18000cc03  mov     [rsp+140h+var_90], rax
0x18000cc0b  lea     rax, [rbp+SRWLock]
0x18000cc0f  mov     [rsp+140h+var_98], rax
0x18000cc17  lea     rax, [rbp+arg_8]
0x18000cc1b  mov     [rsp+140h+var_A0], rax
0x18000cc23  lea     rax, [rbp+var_68]
0x18000cc27  mov     [rsp+140h+var_A8], rax
0x18000cc2f  lea     rax, [rbp+var_60]
0x18000cc33  mov     [rsp+140h+var_B0], rax
0x18000cc3b  lea     rax, [rbp+arg_10]
0x18000cc3f  mov     [rsp+140h+var_B8], rax
0x18000cc47  lea     rax, [rbp+var_58]
0x18000cc4b  mov     [rsp+140h+var_C0], rax
0x18000cc53  lea     rax, [rbp+var_50]
0x18000cc57  mov     [rsp+140h+var_C8], rax
0x18000cc5c  lea     rax, [rbp+arg_18]
0x18000cc60  mov     [rsp+140h+var_D0], rax
0x18000cc65  lea     rax, [rbp+var_48]
0x18000cc69  mov     [rsp+140h+var_D8], rax
0x18000cc6e  lea     rax, [rbp+var_80]
0x18000cc72  mov     [rsp+140h+var_E0], rax
0x18000cc77  lea     rax, [rbp+var_40]
0x18000cc7b  mov     [rsp+140h+var_E8], rax
0x18000cc80  lea     rax, [rbp+var_7C]
0x18000cc84  mov     [rsp+140h+var_F0], rax
0x18000cc89  lea     rax, [rbp+var_38]
0x18000cc8d  mov     [rsp+140h+var_F8], rax
0x18000cc92  lea     rax, [rbp+var_78]
0x18000cc96  mov     [rsp+140h+var_100], rax
0x18000cc9b  lea     rax, [rbp+var_30]
0x18000cc9f  mov     [rsp+140h+var_108], rax
0x18000cca4  lea     rax, [rbp+var_74]
0x18000cca8  mov     [rsp+140h+var_110], rax
0x18000ccad  lea     rax, [rbp+var_28]
0x18000ccb1  mov     [rsp+140h+var_118], rax
0x18000ccb6  lea     rax, [rbp+var_20]
0x18000ccba  mov     [rsp+140h+var_120], rax
0x18000ccbf  lea     rdx, word_1800146B6
0x18000ccc6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000cccb  jmp     loc_18000CD61
0x18000ccd0  lea     rdx, [rbp+SRWLock]
0x18000ccd4  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ccd9  mov     rax, [rbx+110h]
0x18000cce0  mov     dword ptr [rax], 2
0x18000cce6  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000ccea  test    rcx, rcx
0x18000cced  jz      short loc_18000CCFB
0x18000ccef  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ccf6  nop     dword ptr [rax+rax+00h]
0x18000ccfb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000cd00  mov     rdi, [rax+8]
0x18000cd04  mov     eax, [rdi]
0x18000cd06  cmp     eax, 5
0x18000cd09  jbe     short loc_18000CD61
0x18000cd0b  call    cs:__imp_GetCurrentThreadId
0x18000cd12  nop     dword ptr [rax+rax+00h]
0x18000cd17  mov     dword ptr [rbp+SRWLock], eax
0x18000cd1a  mov     r8, [rbx+110h]
0x18000cd21  mov     eax, [r8+48h]
0x18000cd25  mov     [rbp+arg_8], eax
0x18000cd28  mov     [rbp+arg_10], 0
0x18000cd30  add     r8, 8
0x18000cd34  lea     rax, [rbp+SRWLock]
0x18000cd38  mov     [rsp+140h+var_110], rax
0x18000cd3d  lea     rax, [rbp+arg_8]
0x18000cd41  mov     [rsp+140h+var_118], rax
0x18000cd46  lea     rax, [rbp+arg_10]
0x18000cd4a  mov     [rsp+140h+var_120], rax
0x18000cd4f  xor     r9d, r9d
0x18000cd52  lea     rdx, dword_180014804
0x18000cd59  mov     rcx, rdi
0x18000cd5c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cd61  mov     rcx, rbx
0x18000cd64  add     rsp, 130h
0x18000cd6b  pop     rdi
0x18000cd6c  pop     rbx
0x18000cd6d  pop     rbp
0x18000cd6e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
