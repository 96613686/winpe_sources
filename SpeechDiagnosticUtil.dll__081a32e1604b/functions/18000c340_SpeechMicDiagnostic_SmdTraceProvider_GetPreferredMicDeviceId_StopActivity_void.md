# SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::StopActivity(void)

- ea: `0x18000c340`
- end: `0x18000c5c3`
- name: `?StopActivity@GetPreferredMicDeviceId@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000c340`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c39a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c53f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c39a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c53f`
- `KERNEL32!GetCurrentThreadId` at `0x18000c55b`
- `KERNEL32!GetCurrentThreadId` at `0x18000c55b`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *this)
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
        (unsigned int)&dword_180015264,
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
        (unsigned int)&word_1800153B6,
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
0x18000c340  push    rbp
0x18000c342  push    rbx
0x18000c343  push    rdi
0x18000c344  lea     rbp, [rsp+10h]
0x18000c349  sub     rsp, 130h
0x18000c350  mov     rbx, rcx
0x18000c353  mov     rdi, [rcx+110h]
0x18000c35a  mov     eax, [rdi+48h]
0x18000c35d  test    eax, eax
0x18000c35f  jns     loc_18000C520
0x18000c365  add     rdi, 50h ; 'P'
0x18000c369  cmp     eax, [rdi+8]
0x18000c36c  jnz     loc_18000C520
0x18000c372  test    rdi, rdi
0x18000c375  jz      loc_18000C520
0x18000c37b  lea     rdx, [rbp+SRWLock]
0x18000c37f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c384  mov     rax, [rbx+110h]
0x18000c38b  mov     dword ptr [rax], 2
0x18000c391  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c395  test    rcx, rcx
0x18000c398  jz      short loc_18000C3A6
0x18000c39a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c3a1  nop     dword ptr [rax+rax+00h]
0x18000c3a6  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c3ab  mov     rcx, [rax+8]
0x18000c3af  mov     eax, [rcx]
0x18000c3b1  cmp     eax, 5
0x18000c3b4  jbe     loc_18000C5B1
0x18000c3ba  mov     rax, [rdi+30h]
0x18000c3be  mov     [rbp+var_70], rax
0x18000c3c2  mov     eax, [rdi+44h]
0x18000c3c5  mov     dword ptr [rbp+SRWLock], eax
0x18000c3c8  mov     eax, [rdi+10h]
0x18000c3cb  mov     [rbp+arg_8], eax
0x18000c3ce  mov     rax, [rdi+78h]
0x18000c3d2  mov     [rbp+var_68], rax
0x18000c3d6  mov     rax, [rdi+70h]
0x18000c3da  mov     [rbp+var_60], rax
0x18000c3de  mov     eax, [rdi+68h]
0x18000c3e1  mov     dword ptr [rbp+arg_10], eax
0x18000c3e4  mov     rax, [rdi+60h]
0x18000c3e8  mov     [rbp+var_58], rax
0x18000c3ec  mov     rax, [rdi+58h]
0x18000c3f0  mov     [rbp+var_50], rax
0x18000c3f4  mov     eax, [rdi+50h]
0x18000c3f7  mov     [rbp+arg_18], eax
0x18000c3fa  mov     rax, [rdi+48h]
0x18000c3fe  mov     [rbp+var_48], rax
0x18000c402  mov     eax, [rdi+20h]
0x18000c405  mov     [rbp+var_80], eax
0x18000c408  mov     rax, [rdi+18h]
0x18000c40c  mov     [rbp+var_40], rax
0x18000c410  mov     eax, [rdi]
0x18000c412  mov     [rbp+var_7C], eax
0x18000c415  mov     rax, [rdi+80h]
0x18000c41c  mov     [rbp+var_38], rax
0x18000c420  mov     eax, [rdi+40h]
0x18000c423  mov     [rbp+var_78], eax
0x18000c426  mov     rax, [rdi+38h]
0x18000c42a  mov     [rbp+var_30], rax
0x18000c42e  mov     eax, [rdi+8]
0x18000c431  mov     [rbp+var_74], eax
0x18000c434  mov     [rbp+var_28], 1000000h
0x18000c43c  mov     [rbp+var_20], 0
0x18000c444  mov     r8, [rbx+110h]
0x18000c44b  add     r8, 8
0x18000c44f  lea     rax, [rbp+var_70]
0x18000c453  mov     [rsp+140h+var_90], rax
0x18000c45b  lea     rax, [rbp+SRWLock]
0x18000c45f  mov     [rsp+140h+var_98], rax
0x18000c467  lea     rax, [rbp+arg_8]
0x18000c46b  mov     [rsp+140h+var_A0], rax
0x18000c473  lea     rax, [rbp+var_68]
0x18000c477  mov     [rsp+140h+var_A8], rax
0x18000c47f  lea     rax, [rbp+var_60]
0x18000c483  mov     [rsp+140h+var_B0], rax
0x18000c48b  lea     rax, [rbp+arg_10]
0x18000c48f  mov     [rsp+140h+var_B8], rax
0x18000c497  lea     rax, [rbp+var_58]
0x18000c49b  mov     [rsp+140h+var_C0], rax
0x18000c4a3  lea     rax, [rbp+var_50]
0x18000c4a7  mov     [rsp+140h+var_C8], rax
0x18000c4ac  lea     rax, [rbp+arg_18]
0x18000c4b0  mov     [rsp+140h+var_D0], rax
0x18000c4b5  lea     rax, [rbp+var_48]
0x18000c4b9  mov     [rsp+140h+var_D8], rax
0x18000c4be  lea     rax, [rbp+var_80]
0x18000c4c2  mov     [rsp+140h+var_E0], rax
0x18000c4c7  lea     rax, [rbp+var_40]
0x18000c4cb  mov     [rsp+140h+var_E8], rax
0x18000c4d0  lea     rax, [rbp+var_7C]
0x18000c4d4  mov     [rsp+140h+var_F0], rax
0x18000c4d9  lea     rax, [rbp+var_38]
0x18000c4dd  mov     [rsp+140h+var_F8], rax
0x18000c4e2  lea     rax, [rbp+var_78]
0x18000c4e6  mov     [rsp+140h+var_100], rax
0x18000c4eb  lea     rax, [rbp+var_30]
0x18000c4ef  mov     [rsp+140h+var_108], rax
0x18000c4f4  lea     rax, [rbp+var_74]
0x18000c4f8  mov     [rsp+140h+var_110], rax
0x18000c4fd  lea     rax, [rbp+var_28]
0x18000c501  mov     [rsp+140h+var_118], rax
0x18000c506  lea     rax, [rbp+var_20]
0x18000c50a  mov     [rsp+140h+var_120], rax
0x18000c50f  lea     rdx, dword_180015264
0x18000c516  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c51b  jmp     loc_18000C5B1
0x18000c520  lea     rdx, [rbp+SRWLock]
0x18000c524  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c529  mov     rax, [rbx+110h]
0x18000c530  mov     dword ptr [rax], 2
0x18000c536  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c53a  test    rcx, rcx
0x18000c53d  jz      short loc_18000C54B
0x18000c53f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c546  nop     dword ptr [rax+rax+00h]
0x18000c54b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c550  mov     rdi, [rax+8]
0x18000c554  mov     eax, [rdi]
0x18000c556  cmp     eax, 5
0x18000c559  jbe     short loc_18000C5B1
0x18000c55b  call    cs:__imp_GetCurrentThreadId
0x18000c562  nop     dword ptr [rax+rax+00h]
0x18000c567  mov     dword ptr [rbp+SRWLock], eax
0x18000c56a  mov     r8, [rbx+110h]
0x18000c571  mov     eax, [r8+48h]
0x18000c575  mov     [rbp+arg_8], eax
0x18000c578  mov     [rbp+arg_10], 0
0x18000c580  add     r8, 8
0x18000c584  lea     rax, [rbp+SRWLock]
0x18000c588  mov     [rsp+140h+var_110], rax
0x18000c58d  lea     rax, [rbp+arg_8]
0x18000c591  mov     [rsp+140h+var_118], rax
0x18000c596  lea     rax, [rbp+arg_10]
0x18000c59a  mov     [rsp+140h+var_120], rax
0x18000c59f  xor     r9d, r9d
0x18000c5a2  lea     rdx, word_1800153B6
0x18000c5a9  mov     rcx, rdi
0x18000c5ac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c5b1  mov     rcx, rbx
0x18000c5b4  add     rsp, 130h
0x18000c5bb  pop     rdi
0x18000c5bc  pop     rbx
0x18000c5bd  pop     rbp
0x18000c5be  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
