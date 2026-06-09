# SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StopActivity(void)

- ea: `0x18000c860`
- end: `0x18000cae3`
- name: `?StopActivity@MarkTroublePageDisplayed@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000c860`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c8ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ca5f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c8ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ca5f`
- `KERNEL32!GetCurrentThreadId` at `0x18000ca7b`
- `KERNEL32!GetCurrentThreadId` at `0x18000ca7b`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed *this)
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
        (unsigned int)word_180014EFA,
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
        (unsigned int)byte_18001504D,
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
0x18000c860  push    rbp
0x18000c862  push    rbx
0x18000c863  push    rdi
0x18000c864  lea     rbp, [rsp+10h]
0x18000c869  sub     rsp, 130h
0x18000c870  mov     rbx, rcx
0x18000c873  mov     rdi, [rcx+110h]
0x18000c87a  mov     eax, [rdi+48h]
0x18000c87d  test    eax, eax
0x18000c87f  jns     loc_18000CA40
0x18000c885  add     rdi, 50h ; 'P'
0x18000c889  cmp     eax, [rdi+8]
0x18000c88c  jnz     loc_18000CA40
0x18000c892  test    rdi, rdi
0x18000c895  jz      loc_18000CA40
0x18000c89b  lea     rdx, [rbp+SRWLock]
0x18000c89f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c8a4  mov     rax, [rbx+110h]
0x18000c8ab  mov     dword ptr [rax], 2
0x18000c8b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c8b5  test    rcx, rcx
0x18000c8b8  jz      short loc_18000C8C6
0x18000c8ba  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8c1  nop     dword ptr [rax+rax+00h]
0x18000c8c6  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c8cb  mov     rcx, [rax+8]
0x18000c8cf  mov     eax, [rcx]
0x18000c8d1  cmp     eax, 5
0x18000c8d4  jbe     loc_18000CAD1
0x18000c8da  mov     rax, [rdi+30h]
0x18000c8de  mov     [rbp+var_70], rax
0x18000c8e2  mov     eax, [rdi+44h]
0x18000c8e5  mov     dword ptr [rbp+SRWLock], eax
0x18000c8e8  mov     eax, [rdi+10h]
0x18000c8eb  mov     [rbp+arg_8], eax
0x18000c8ee  mov     rax, [rdi+78h]
0x18000c8f2  mov     [rbp+var_68], rax
0x18000c8f6  mov     rax, [rdi+70h]
0x18000c8fa  mov     [rbp+var_60], rax
0x18000c8fe  mov     eax, [rdi+68h]
0x18000c901  mov     dword ptr [rbp+arg_10], eax
0x18000c904  mov     rax, [rdi+60h]
0x18000c908  mov     [rbp+var_58], rax
0x18000c90c  mov     rax, [rdi+58h]
0x18000c910  mov     [rbp+var_50], rax
0x18000c914  mov     eax, [rdi+50h]
0x18000c917  mov     [rbp+arg_18], eax
0x18000c91a  mov     rax, [rdi+48h]
0x18000c91e  mov     [rbp+var_48], rax
0x18000c922  mov     eax, [rdi+20h]
0x18000c925  mov     [rbp+var_80], eax
0x18000c928  mov     rax, [rdi+18h]
0x18000c92c  mov     [rbp+var_40], rax
0x18000c930  mov     eax, [rdi]
0x18000c932  mov     [rbp+var_7C], eax
0x18000c935  mov     rax, [rdi+80h]
0x18000c93c  mov     [rbp+var_38], rax
0x18000c940  mov     eax, [rdi+40h]
0x18000c943  mov     [rbp+var_78], eax
0x18000c946  mov     rax, [rdi+38h]
0x18000c94a  mov     [rbp+var_30], rax
0x18000c94e  mov     eax, [rdi+8]
0x18000c951  mov     [rbp+var_74], eax
0x18000c954  mov     [rbp+var_28], 1000000h
0x18000c95c  mov     [rbp+var_20], 0
0x18000c964  mov     r8, [rbx+110h]
0x18000c96b  add     r8, 8
0x18000c96f  lea     rax, [rbp+var_70]
0x18000c973  mov     [rsp+140h+var_90], rax
0x18000c97b  lea     rax, [rbp+SRWLock]
0x18000c97f  mov     [rsp+140h+var_98], rax
0x18000c987  lea     rax, [rbp+arg_8]
0x18000c98b  mov     [rsp+140h+var_A0], rax
0x18000c993  lea     rax, [rbp+var_68]
0x18000c997  mov     [rsp+140h+var_A8], rax
0x18000c99f  lea     rax, [rbp+var_60]
0x18000c9a3  mov     [rsp+140h+var_B0], rax
0x18000c9ab  lea     rax, [rbp+arg_10]
0x18000c9af  mov     [rsp+140h+var_B8], rax
0x18000c9b7  lea     rax, [rbp+var_58]
0x18000c9bb  mov     [rsp+140h+var_C0], rax
0x18000c9c3  lea     rax, [rbp+var_50]
0x18000c9c7  mov     [rsp+140h+var_C8], rax
0x18000c9cc  lea     rax, [rbp+arg_18]
0x18000c9d0  mov     [rsp+140h+var_D0], rax
0x18000c9d5  lea     rax, [rbp+var_48]
0x18000c9d9  mov     [rsp+140h+var_D8], rax
0x18000c9de  lea     rax, [rbp+var_80]
0x18000c9e2  mov     [rsp+140h+var_E0], rax
0x18000c9e7  lea     rax, [rbp+var_40]
0x18000c9eb  mov     [rsp+140h+var_E8], rax
0x18000c9f0  lea     rax, [rbp+var_7C]
0x18000c9f4  mov     [rsp+140h+var_F0], rax
0x18000c9f9  lea     rax, [rbp+var_38]
0x18000c9fd  mov     [rsp+140h+var_F8], rax
0x18000ca02  lea     rax, [rbp+var_78]
0x18000ca06  mov     [rsp+140h+var_100], rax
0x18000ca0b  lea     rax, [rbp+var_30]
0x18000ca0f  mov     [rsp+140h+var_108], rax
0x18000ca14  lea     rax, [rbp+var_74]
0x18000ca18  mov     [rsp+140h+var_110], rax
0x18000ca1d  lea     rax, [rbp+var_28]
0x18000ca21  mov     [rsp+140h+var_118], rax
0x18000ca26  lea     rax, [rbp+var_20]
0x18000ca2a  mov     [rsp+140h+var_120], rax
0x18000ca2f  lea     rdx, word_180014EFA
0x18000ca36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ca3b  jmp     loc_18000CAD1
0x18000ca40  lea     rdx, [rbp+SRWLock]
0x18000ca44  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ca49  mov     rax, [rbx+110h]
0x18000ca50  mov     dword ptr [rax], 2
0x18000ca56  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000ca5a  test    rcx, rcx
0x18000ca5d  jz      short loc_18000CA6B
0x18000ca5f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca66  nop     dword ptr [rax+rax+00h]
0x18000ca6b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000ca70  mov     rdi, [rax+8]
0x18000ca74  mov     eax, [rdi]
0x18000ca76  cmp     eax, 5
0x18000ca79  jbe     short loc_18000CAD1
0x18000ca7b  call    cs:__imp_GetCurrentThreadId
0x18000ca82  nop     dword ptr [rax+rax+00h]
0x18000ca87  mov     dword ptr [rbp+SRWLock], eax
0x18000ca8a  mov     r8, [rbx+110h]
0x18000ca91  mov     eax, [r8+48h]
0x18000ca95  mov     [rbp+arg_8], eax
0x18000ca98  mov     [rbp+arg_10], 0
0x18000caa0  add     r8, 8
0x18000caa4  lea     rax, [rbp+SRWLock]
0x18000caa8  mov     [rsp+140h+var_110], rax
0x18000caad  lea     rax, [rbp+arg_8]
0x18000cab1  mov     [rsp+140h+var_118], rax
0x18000cab6  lea     rax, [rbp+arg_10]
0x18000caba  mov     [rsp+140h+var_120], rax
0x18000cabf  xor     r9d, r9d
0x18000cac2  lea     rdx, byte_18001504D
0x18000cac9  mov     rcx, rdi
0x18000cacc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cad1  mov     rcx, rbx
0x18000cad4  add     rsp, 130h
0x18000cadb  pop     rdi
0x18000cadc  pop     rbx
0x18000cadd  pop     rbp
0x18000cade  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
