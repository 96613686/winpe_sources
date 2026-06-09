# SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::StopActivity(void)

- ea: `0x18000be20`
- end: `0x18000c0a3`
- name: `?StopActivity@GetDiagnosticResult@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000be20`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000be7a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c01f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000be7a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c01f`
- `KERNEL32!GetCurrentThreadId` at `0x18000c03b`
- `KERNEL32!GetCurrentThreadId` at `0x18000c03b`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *this)
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
        (unsigned int)&unk_180014D58,
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
        (unsigned int)&word_180014EA6,
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
0x18000be20  push    rbp
0x18000be22  push    rbx
0x18000be23  push    rdi
0x18000be24  lea     rbp, [rsp+10h]
0x18000be29  sub     rsp, 130h
0x18000be30  mov     rbx, rcx
0x18000be33  mov     rdi, [rcx+110h]
0x18000be3a  mov     eax, [rdi+48h]
0x18000be3d  test    eax, eax
0x18000be3f  jns     loc_18000C000
0x18000be45  add     rdi, 50h ; 'P'
0x18000be49  cmp     eax, [rdi+8]
0x18000be4c  jnz     loc_18000C000
0x18000be52  test    rdi, rdi
0x18000be55  jz      loc_18000C000
0x18000be5b  lea     rdx, [rbp+SRWLock]
0x18000be5f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000be64  mov     rax, [rbx+110h]
0x18000be6b  mov     dword ptr [rax], 2
0x18000be71  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000be75  test    rcx, rcx
0x18000be78  jz      short loc_18000BE86
0x18000be7a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be81  nop     dword ptr [rax+rax+00h]
0x18000be86  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000be8b  mov     rcx, [rax+8]
0x18000be8f  mov     eax, [rcx]
0x18000be91  cmp     eax, 5
0x18000be94  jbe     loc_18000C091
0x18000be9a  mov     rax, [rdi+30h]
0x18000be9e  mov     [rbp+var_70], rax
0x18000bea2  mov     eax, [rdi+44h]
0x18000bea5  mov     dword ptr [rbp+SRWLock], eax
0x18000bea8  mov     eax, [rdi+10h]
0x18000beab  mov     [rbp+arg_8], eax
0x18000beae  mov     rax, [rdi+78h]
0x18000beb2  mov     [rbp+var_68], rax
0x18000beb6  mov     rax, [rdi+70h]
0x18000beba  mov     [rbp+var_60], rax
0x18000bebe  mov     eax, [rdi+68h]
0x18000bec1  mov     dword ptr [rbp+arg_10], eax
0x18000bec4  mov     rax, [rdi+60h]
0x18000bec8  mov     [rbp+var_58], rax
0x18000becc  mov     rax, [rdi+58h]
0x18000bed0  mov     [rbp+var_50], rax
0x18000bed4  mov     eax, [rdi+50h]
0x18000bed7  mov     [rbp+arg_18], eax
0x18000beda  mov     rax, [rdi+48h]
0x18000bede  mov     [rbp+var_48], rax
0x18000bee2  mov     eax, [rdi+20h]
0x18000bee5  mov     [rbp+var_80], eax
0x18000bee8  mov     rax, [rdi+18h]
0x18000beec  mov     [rbp+var_40], rax
0x18000bef0  mov     eax, [rdi]
0x18000bef2  mov     [rbp+var_7C], eax
0x18000bef5  mov     rax, [rdi+80h]
0x18000befc  mov     [rbp+var_38], rax
0x18000bf00  mov     eax, [rdi+40h]
0x18000bf03  mov     [rbp+var_78], eax
0x18000bf06  mov     rax, [rdi+38h]
0x18000bf0a  mov     [rbp+var_30], rax
0x18000bf0e  mov     eax, [rdi+8]
0x18000bf11  mov     [rbp+var_74], eax
0x18000bf14  mov     [rbp+var_28], 1000000h
0x18000bf1c  mov     [rbp+var_20], 0
0x18000bf24  mov     r8, [rbx+110h]
0x18000bf2b  add     r8, 8
0x18000bf2f  lea     rax, [rbp+var_70]
0x18000bf33  mov     [rsp+140h+var_90], rax
0x18000bf3b  lea     rax, [rbp+SRWLock]
0x18000bf3f  mov     [rsp+140h+var_98], rax
0x18000bf47  lea     rax, [rbp+arg_8]
0x18000bf4b  mov     [rsp+140h+var_A0], rax
0x18000bf53  lea     rax, [rbp+var_68]
0x18000bf57  mov     [rsp+140h+var_A8], rax
0x18000bf5f  lea     rax, [rbp+var_60]
0x18000bf63  mov     [rsp+140h+var_B0], rax
0x18000bf6b  lea     rax, [rbp+arg_10]
0x18000bf6f  mov     [rsp+140h+var_B8], rax
0x18000bf77  lea     rax, [rbp+var_58]
0x18000bf7b  mov     [rsp+140h+var_C0], rax
0x18000bf83  lea     rax, [rbp+var_50]
0x18000bf87  mov     [rsp+140h+var_C8], rax
0x18000bf8c  lea     rax, [rbp+arg_18]
0x18000bf90  mov     [rsp+140h+var_D0], rax
0x18000bf95  lea     rax, [rbp+var_48]
0x18000bf99  mov     [rsp+140h+var_D8], rax
0x18000bf9e  lea     rax, [rbp+var_80]
0x18000bfa2  mov     [rsp+140h+var_E0], rax
0x18000bfa7  lea     rax, [rbp+var_40]
0x18000bfab  mov     [rsp+140h+var_E8], rax
0x18000bfb0  lea     rax, [rbp+var_7C]
0x18000bfb4  mov     [rsp+140h+var_F0], rax
0x18000bfb9  lea     rax, [rbp+var_38]
0x18000bfbd  mov     [rsp+140h+var_F8], rax
0x18000bfc2  lea     rax, [rbp+var_78]
0x18000bfc6  mov     [rsp+140h+var_100], rax
0x18000bfcb  lea     rax, [rbp+var_30]
0x18000bfcf  mov     [rsp+140h+var_108], rax
0x18000bfd4  lea     rax, [rbp+var_74]
0x18000bfd8  mov     [rsp+140h+var_110], rax
0x18000bfdd  lea     rax, [rbp+var_28]
0x18000bfe1  mov     [rsp+140h+var_118], rax
0x18000bfe6  lea     rax, [rbp+var_20]
0x18000bfea  mov     [rsp+140h+var_120], rax
0x18000bfef  lea     rdx, unk_180014D58
0x18000bff6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000bffb  jmp     loc_18000C091
0x18000c000  lea     rdx, [rbp+SRWLock]
0x18000c004  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c009  mov     rax, [rbx+110h]
0x18000c010  mov     dword ptr [rax], 2
0x18000c016  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c01a  test    rcx, rcx
0x18000c01d  jz      short loc_18000C02B
0x18000c01f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c026  nop     dword ptr [rax+rax+00h]
0x18000c02b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c030  mov     rdi, [rax+8]
0x18000c034  mov     eax, [rdi]
0x18000c036  cmp     eax, 5
0x18000c039  jbe     short loc_18000C091
0x18000c03b  call    cs:__imp_GetCurrentThreadId
0x18000c042  nop     dword ptr [rax+rax+00h]
0x18000c047  mov     dword ptr [rbp+SRWLock], eax
0x18000c04a  mov     r8, [rbx+110h]
0x18000c051  mov     eax, [r8+48h]
0x18000c055  mov     [rbp+arg_8], eax
0x18000c058  mov     [rbp+arg_10], 0
0x18000c060  add     r8, 8
0x18000c064  lea     rax, [rbp+SRWLock]
0x18000c068  mov     [rsp+140h+var_110], rax
0x18000c06d  lea     rax, [rbp+arg_8]
0x18000c071  mov     [rsp+140h+var_118], rax
0x18000c076  lea     rax, [rbp+arg_10]
0x18000c07a  mov     [rsp+140h+var_120], rax
0x18000c07f  xor     r9d, r9d
0x18000c082  lea     rdx, word_180014EA6
0x18000c089  mov     rcx, rdi
0x18000c08c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c091  mov     rcx, rbx
0x18000c094  add     rsp, 130h
0x18000c09b  pop     rdi
0x18000c09c  pop     rbx
0x18000c09d  pop     rbp
0x18000c09e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
