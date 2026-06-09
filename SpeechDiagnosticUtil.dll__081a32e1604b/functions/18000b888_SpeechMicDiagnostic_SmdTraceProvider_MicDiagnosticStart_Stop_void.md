# SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart::Stop(void *)

- ea: `0x18000b888`
- end: `0x18000bb7d`
- name: `?Stop@MicDiagnosticStart@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `757`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x180001640`
- `0x1800019f8`
- `0x180002910`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000b888`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b8f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000baac`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b8f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000baac`
- `KERNEL32!GetCurrentThreadId` at `0x18000bad0`
- `KERNEL32!GetCurrentThreadId` at `0x18000bad0`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart::Stop(
        SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart *this,
        RTL_SRWLOCK *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  _DWORD *v8; // rcx
  int v9; // r9d
  __int64 v10; // r8
  RTL_SRWLOCK *v11; // rcx
  _DWORD *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+D0h] [rbp-70h] BYREF
  int v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  int v20; // [rsp+E0h] [rbp-60h] BYREF
  int v21; // [rsp+E4h] [rbp-5Ch] BYREF
  int v22; // [rsp+E8h] [rbp-58h] BYREF
  int v23; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+128h] [rbp-18h] BYREF
  __int64 v32; // [rsp+130h] [rbp-10h] BYREF
  __int64 v33; // [rsp+138h] [rbp-8h] BYREF
  __int64 v34; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v36; // [rsp+170h] [rbp+30h]
  __int64 v37; // [rsp+178h] [rbp+38h]
  int *v38; // [rsp+180h] [rbp+40h]
  __int64 v39; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v41; // [rsp+198h] [rbp+58h]
  PSRWLOCK *v42; // [rsp+1A0h] [rbp+60h]
  __int64 v43; // [rsp+1A8h] [rbp+68h]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v7 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v8 > 5u )
    {
      v26 = *((_QWORD *)v6 + 6);
      v18 = v6[17];
      v19 = v6[4];
      v27 = *((_QWORD *)v6 + 15);
      v28 = *((_QWORD *)v6 + 14);
      v20 = v6[26];
      v10 = *((_QWORD *)this + 34);
      v29 = *((_QWORD *)v6 + 12);
      v30 = *((_QWORD *)v6 + 11);
      v21 = v6[20];
      v31 = *((_QWORD *)v6 + 9);
      v22 = v6[8];
      v32 = *((_QWORD *)v6 + 3);
      v23 = *v6;
      v33 = *((_QWORD *)v6 + 16);
      v15 = v6[16];
      v34 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v25 = a2;
      v24 = 0x1000000;
      v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v8,
        (unsigned int)&unk_180014858,
        v10 + 8,
        v9,
        (__int64)&v17,
        (__int64)&v24,
        (__int64)&SRWLock,
        (__int64)&v34,
        (__int64)&v15,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v25);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    v11 = v17;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v12 > 5u )
    {
      v17 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v43 = 8;
      v41 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      v42 = &v17;
      p_SRWLock = &SRWLock;
      v38 = &v15;
      v36 = &v24;
      v24 = 0;
      v39 = 4;
      v37 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v12,
        (unsigned __int8 *)&dword_1800149AC,
        (const GUID *)(v14 + 8),
        0,
        6u,
        &v35);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000b888  push    rbp
0x18000b88a  push    rbx
0x18000b88b  push    rsi
0x18000b88c  push    rdi
0x18000b88d  lea     rbp, [rsp-88h]
0x18000b895  sub     rsp, 1C8h
0x18000b89c  mov     rax, cs:__security_cookie
0x18000b8a3  xor     rax, rsp
0x18000b8a6  mov     [rbp+0A0h+var_30], rax
0x18000b8aa  mov     rdi, [rcx+110h]
0x18000b8b1  mov     rsi, rdx
0x18000b8b4  mov     rbx, rcx
0x18000b8b7  mov     eax, [rdi+48h]
0x18000b8ba  test    eax, eax
0x18000b8bc  jns     loc_18000BA8D
0x18000b8c2  add     rdi, 50h ; 'P'
0x18000b8c6  cmp     eax, [rdi+8]
0x18000b8c9  jnz     loc_18000BA8D
0x18000b8cf  test    rdi, rdi
0x18000b8d2  jz      loc_18000BA8D
0x18000b8d8  lea     rdx, [rbp+0A0h+SRWLock]
0x18000b8dc  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b8e1  mov     rax, [rbx+110h]
0x18000b8e8  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x18000b8ec  mov     dword ptr [rax], 2
0x18000b8f2  test    rcx, rcx
0x18000b8f5  jz      short loc_18000B903
0x18000b8f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8fe  nop     dword ptr [rax+rax+00h]
0x18000b903  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000b908  mov     rcx, [rax+8]
0x18000b90c  mov     eax, [rcx]
0x18000b90e  cmp     eax, 5
0x18000b911  jbe     loc_18000BB5C
0x18000b917  mov     rax, [rdi+30h]
0x18000b91b  lea     rdx, unk_180014858
0x18000b922  mov     [rbp+0A0h+var_E0], rax
0x18000b926  mov     eax, [rdi+44h]
0x18000b929  mov     [rbp+0A0h+var_108], eax
0x18000b92c  mov     eax, [rdi+10h]
0x18000b92f  mov     [rbp+0A0h+var_104], eax
0x18000b932  mov     rax, [rdi+78h]
0x18000b936  mov     [rbp+0A0h+var_D8], rax
0x18000b93a  mov     rax, [rdi+70h]
0x18000b93e  mov     [rbp+0A0h+var_D0], rax
0x18000b942  mov     eax, [rdi+68h]
0x18000b945  mov     [rbp+0A0h+var_100], eax
0x18000b948  mov     rax, [rdi+60h]
0x18000b94c  mov     r8, [rbx+110h]
0x18000b953  mov     [rbp+0A0h+var_C8], rax
0x18000b957  add     r8, 8
0x18000b95b  mov     rax, [rdi+58h]
0x18000b95f  mov     [rbp+0A0h+var_C0], rax
0x18000b963  mov     eax, [rdi+50h]
0x18000b966  mov     [rbp+0A0h+var_FC], eax
0x18000b969  mov     rax, [rdi+48h]
0x18000b96d  mov     [rbp+0A0h+var_B8], rax
0x18000b971  mov     eax, [rdi+20h]
0x18000b974  mov     [rbp+0A0h+var_F8], eax
0x18000b977  mov     rax, [rdi+18h]
0x18000b97b  mov     [rbp+0A0h+var_B0], rax
0x18000b97f  mov     eax, [rdi]
0x18000b981  mov     [rbp+0A0h+var_F4], eax
0x18000b984  mov     rax, [rdi+80h]
0x18000b98b  mov     [rbp+0A0h+var_A8], rax
0x18000b98f  mov     eax, [rdi+40h]
0x18000b992  mov     [rbp+0A0h+var_120], eax
0x18000b995  mov     rax, [rdi+38h]
0x18000b999  mov     [rbp+0A0h+var_A0], rax
0x18000b99d  mov     eax, [rdi+8]
0x18000b9a0  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x18000b9a3  lea     rax, [rbp+0A0h+var_E8]
0x18000b9a7  mov     [rsp+1E0h+var_128], rax
0x18000b9af  lea     rax, [rbp+0A0h+var_E0]
0x18000b9b3  mov     [rsp+1E0h+var_130], rax
0x18000b9bb  lea     rax, [rbp+0A0h+var_108]
0x18000b9bf  mov     [rsp+1E0h+var_138], rax
0x18000b9c7  lea     rax, [rbp+0A0h+var_104]
0x18000b9cb  mov     [rsp+1E0h+var_140], rax
0x18000b9d3  lea     rax, [rbp+0A0h+var_D8]
0x18000b9d7  mov     [rsp+1E0h+var_148], rax
0x18000b9df  lea     rax, [rbp+0A0h+var_D0]
0x18000b9e3  mov     [rsp+1E0h+var_150], rax
0x18000b9eb  lea     rax, [rbp+0A0h+var_100]
0x18000b9ef  mov     [rsp+1E0h+var_158], rax
0x18000b9f7  lea     rax, [rbp+0A0h+var_C8]
0x18000b9fb  mov     [rsp+1E0h+var_160], rax
0x18000ba03  lea     rax, [rbp+0A0h+var_C0]
0x18000ba07  mov     [rsp+1E0h+var_168], rax
0x18000ba0c  lea     rax, [rbp+0A0h+var_FC]
0x18000ba10  mov     [rsp+1E0h+var_170], rax
0x18000ba15  lea     rax, [rbp+0A0h+var_B8]
0x18000ba19  mov     [rsp+1E0h+var_178], rax
0x18000ba1e  lea     rax, [rbp+0A0h+var_F8]
0x18000ba22  mov     [rsp+1E0h+var_180], rax
0x18000ba27  lea     rax, [rbp+0A0h+var_B0]
0x18000ba2b  mov     [rsp+1E0h+var_188], rax
0x18000ba30  lea     rax, [rbp+0A0h+var_F4]
0x18000ba34  mov     [rsp+1E0h+var_190], rax
0x18000ba39  lea     rax, [rbp+0A0h+var_A8]
0x18000ba3d  mov     [rsp+1E0h+var_198], rax
0x18000ba42  lea     rax, [rbp+0A0h+var_120]
0x18000ba46  mov     [rsp+1E0h+var_1A0], rax
0x18000ba4b  lea     rax, [rbp+0A0h+var_A0]
0x18000ba4f  mov     [rsp+1E0h+var_1A8], rax
0x18000ba54  lea     rax, [rbp+0A0h+SRWLock]
0x18000ba58  mov     [rsp+1E0h+var_1B0], rax
0x18000ba5d  lea     rax, [rbp+0A0h+var_F0]
0x18000ba61  mov     [rsp+1E0h+var_1B8], rax
0x18000ba66  lea     rax, [rbp+0A0h+var_110]
0x18000ba6a  mov     [rsp+1E0h+var_1C0], rax
0x18000ba6f  mov     [rbp+0A0h+var_E8], rsi
0x18000ba73  mov     [rbp+0A0h+var_F0], 1000000h
0x18000ba7b  mov     [rbp+0A0h+var_110], 0
0x18000ba83  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564453@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ba88  jmp     loc_18000BB5C
0x18000ba8d  lea     rdx, [rbp+0A0h+var_110]
0x18000ba91  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ba96  mov     rax, [rbx+110h]
0x18000ba9d  mov     rcx, [rbp+0A0h+var_110]; SRWLock
0x18000baa1  mov     dword ptr [rax], 2
0x18000baa7  test    rcx, rcx
0x18000baaa  jz      short loc_18000BAB8
0x18000baac  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bab3  nop     dword ptr [rax+rax+00h]
0x18000bab8  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000babd  mov     rdi, [rax+8]
0x18000bac1  mov     eax, [rdi]
0x18000bac3  cmp     eax, 5
0x18000bac6  jbe     loc_18000BB5C
0x18000bacc  mov     [rbp+0A0h+var_110], rsi
0x18000bad0  call    cs:__imp_GetCurrentThreadId
0x18000bad7  nop     dword ptr [rax+rax+00h]
0x18000badc  mov     r8, [rbx+110h]
0x18000bae3  lea     rdx, dword_1800149AC
0x18000baea  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x18000baed  xor     r9d, r9d
0x18000baf0  mov     rcx, rdi
0x18000baf3  mov     [rbp+0A0h+var_38], 8
0x18000bafb  mov     [rbp+0A0h+var_48], 4
0x18000bb03  mov     eax, [r8+48h]
0x18000bb07  add     r8, 8
0x18000bb0b  mov     [rbp+0A0h+var_120], eax
0x18000bb0e  lea     rax, [rbp+0A0h+var_110]
0x18000bb12  mov     [rbp+0A0h+var_40], rax
0x18000bb16  lea     rax, [rbp+0A0h+SRWLock]
0x18000bb1a  mov     [rbp+0A0h+var_50], rax
0x18000bb1e  lea     rax, [rbp+0A0h+var_120]
0x18000bb22  mov     [rbp+0A0h+var_60], rax
0x18000bb26  lea     rax, [rbp+0A0h+var_F0]
0x18000bb2a  mov     [rbp+0A0h+var_70], rax
0x18000bb2e  lea     rax, [rbp+0A0h+var_90]
0x18000bb32  mov     [rsp+1E0h+var_1B8], rax
0x18000bb37  mov     dword ptr [rsp+1E0h+var_1C0], 6
0x18000bb3f  mov     [rbp+0A0h+var_F0], 0
0x18000bb47  mov     [rbp+0A0h+var_58], 4
0x18000bb4f  mov     [rbp+0A0h+var_68], 8
0x18000bb57  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bb5c  mov     rcx, rbx
0x18000bb5f  call    ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000bb64  mov     rcx, [rbp+0A0h+var_30]
0x18000bb68  xor     rcx, rsp; StackCookie
0x18000bb6b  call    __security_check_cookie
0x18000bb70  add     rsp, 1C8h
0x18000bb77  pop     rdi
0x18000bb78  pop     rsi
0x18000bb79  pop     rbx
0x18000bb7a  pop     rbp
0x18000bb7b  retn
```
