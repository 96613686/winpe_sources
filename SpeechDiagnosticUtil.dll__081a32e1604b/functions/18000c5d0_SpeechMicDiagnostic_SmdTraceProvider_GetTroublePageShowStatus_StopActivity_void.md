# SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StopActivity(void)

- ea: `0x18000c5d0`
- end: `0x18000c853`
- name: `?StopActivity@GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000c5d0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c62a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c7cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c62a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c7cf`
- `KERNEL32!GetCurrentThreadId` at `0x18000c7eb`
- `KERNEL32!GetCurrentThreadId` at `0x18000c7eb`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *this)
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
        (unsigned int)&word_1800155EE,
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
        (unsigned int)byte_180015741,
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
0x18000c5d0  push    rbp
0x18000c5d2  push    rbx
0x18000c5d3  push    rdi
0x18000c5d4  lea     rbp, [rsp+10h]
0x18000c5d9  sub     rsp, 130h
0x18000c5e0  mov     rbx, rcx
0x18000c5e3  mov     rdi, [rcx+110h]
0x18000c5ea  mov     eax, [rdi+48h]
0x18000c5ed  test    eax, eax
0x18000c5ef  jns     loc_18000C7B0
0x18000c5f5  add     rdi, 50h ; 'P'
0x18000c5f9  cmp     eax, [rdi+8]
0x18000c5fc  jnz     loc_18000C7B0
0x18000c602  test    rdi, rdi
0x18000c605  jz      loc_18000C7B0
0x18000c60b  lea     rdx, [rbp+SRWLock]
0x18000c60f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c614  mov     rax, [rbx+110h]
0x18000c61b  mov     dword ptr [rax], 2
0x18000c621  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c625  test    rcx, rcx
0x18000c628  jz      short loc_18000C636
0x18000c62a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c631  nop     dword ptr [rax+rax+00h]
0x18000c636  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c63b  mov     rcx, [rax+8]
0x18000c63f  mov     eax, [rcx]
0x18000c641  cmp     eax, 5
0x18000c644  jbe     loc_18000C841
0x18000c64a  mov     rax, [rdi+30h]
0x18000c64e  mov     [rbp+var_70], rax
0x18000c652  mov     eax, [rdi+44h]
0x18000c655  mov     dword ptr [rbp+SRWLock], eax
0x18000c658  mov     eax, [rdi+10h]
0x18000c65b  mov     [rbp+arg_8], eax
0x18000c65e  mov     rax, [rdi+78h]
0x18000c662  mov     [rbp+var_68], rax
0x18000c666  mov     rax, [rdi+70h]
0x18000c66a  mov     [rbp+var_60], rax
0x18000c66e  mov     eax, [rdi+68h]
0x18000c671  mov     dword ptr [rbp+arg_10], eax
0x18000c674  mov     rax, [rdi+60h]
0x18000c678  mov     [rbp+var_58], rax
0x18000c67c  mov     rax, [rdi+58h]
0x18000c680  mov     [rbp+var_50], rax
0x18000c684  mov     eax, [rdi+50h]
0x18000c687  mov     [rbp+arg_18], eax
0x18000c68a  mov     rax, [rdi+48h]
0x18000c68e  mov     [rbp+var_48], rax
0x18000c692  mov     eax, [rdi+20h]
0x18000c695  mov     [rbp+var_80], eax
0x18000c698  mov     rax, [rdi+18h]
0x18000c69c  mov     [rbp+var_40], rax
0x18000c6a0  mov     eax, [rdi]
0x18000c6a2  mov     [rbp+var_7C], eax
0x18000c6a5  mov     rax, [rdi+80h]
0x18000c6ac  mov     [rbp+var_38], rax
0x18000c6b0  mov     eax, [rdi+40h]
0x18000c6b3  mov     [rbp+var_78], eax
0x18000c6b6  mov     rax, [rdi+38h]
0x18000c6ba  mov     [rbp+var_30], rax
0x18000c6be  mov     eax, [rdi+8]
0x18000c6c1  mov     [rbp+var_74], eax
0x18000c6c4  mov     [rbp+var_28], 1000000h
0x18000c6cc  mov     [rbp+var_20], 0
0x18000c6d4  mov     r8, [rbx+110h]
0x18000c6db  add     r8, 8
0x18000c6df  lea     rax, [rbp+var_70]
0x18000c6e3  mov     [rsp+140h+var_90], rax
0x18000c6eb  lea     rax, [rbp+SRWLock]
0x18000c6ef  mov     [rsp+140h+var_98], rax
0x18000c6f7  lea     rax, [rbp+arg_8]
0x18000c6fb  mov     [rsp+140h+var_A0], rax
0x18000c703  lea     rax, [rbp+var_68]
0x18000c707  mov     [rsp+140h+var_A8], rax
0x18000c70f  lea     rax, [rbp+var_60]
0x18000c713  mov     [rsp+140h+var_B0], rax
0x18000c71b  lea     rax, [rbp+arg_10]
0x18000c71f  mov     [rsp+140h+var_B8], rax
0x18000c727  lea     rax, [rbp+var_58]
0x18000c72b  mov     [rsp+140h+var_C0], rax
0x18000c733  lea     rax, [rbp+var_50]
0x18000c737  mov     [rsp+140h+var_C8], rax
0x18000c73c  lea     rax, [rbp+arg_18]
0x18000c740  mov     [rsp+140h+var_D0], rax
0x18000c745  lea     rax, [rbp+var_48]
0x18000c749  mov     [rsp+140h+var_D8], rax
0x18000c74e  lea     rax, [rbp+var_80]
0x18000c752  mov     [rsp+140h+var_E0], rax
0x18000c757  lea     rax, [rbp+var_40]
0x18000c75b  mov     [rsp+140h+var_E8], rax
0x18000c760  lea     rax, [rbp+var_7C]
0x18000c764  mov     [rsp+140h+var_F0], rax
0x18000c769  lea     rax, [rbp+var_38]
0x18000c76d  mov     [rsp+140h+var_F8], rax
0x18000c772  lea     rax, [rbp+var_78]
0x18000c776  mov     [rsp+140h+var_100], rax
0x18000c77b  lea     rax, [rbp+var_30]
0x18000c77f  mov     [rsp+140h+var_108], rax
0x18000c784  lea     rax, [rbp+var_74]
0x18000c788  mov     [rsp+140h+var_110], rax
0x18000c78d  lea     rax, [rbp+var_28]
0x18000c791  mov     [rsp+140h+var_118], rax
0x18000c796  lea     rax, [rbp+var_20]
0x18000c79a  mov     [rsp+140h+var_120], rax
0x18000c79f  lea     rdx, word_1800155EE
0x18000c7a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c7ab  jmp     loc_18000C841
0x18000c7b0  lea     rdx, [rbp+SRWLock]
0x18000c7b4  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c7b9  mov     rax, [rbx+110h]
0x18000c7c0  mov     dword ptr [rax], 2
0x18000c7c6  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000c7ca  test    rcx, rcx
0x18000c7cd  jz      short loc_18000C7DB
0x18000c7cf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c7d6  nop     dword ptr [rax+rax+00h]
0x18000c7db  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000c7e0  mov     rdi, [rax+8]
0x18000c7e4  mov     eax, [rdi]
0x18000c7e6  cmp     eax, 5
0x18000c7e9  jbe     short loc_18000C841
0x18000c7eb  call    cs:__imp_GetCurrentThreadId
0x18000c7f2  nop     dword ptr [rax+rax+00h]
0x18000c7f7  mov     dword ptr [rbp+SRWLock], eax
0x18000c7fa  mov     r8, [rbx+110h]
0x18000c801  mov     eax, [r8+48h]
0x18000c805  mov     [rbp+arg_8], eax
0x18000c808  mov     [rbp+arg_10], 0
0x18000c810  add     r8, 8
0x18000c814  lea     rax, [rbp+SRWLock]
0x18000c818  mov     [rsp+140h+var_110], rax
0x18000c81d  lea     rax, [rbp+arg_8]
0x18000c821  mov     [rsp+140h+var_118], rax
0x18000c826  lea     rax, [rbp+arg_10]
0x18000c82a  mov     [rsp+140h+var_120], rax
0x18000c82f  xor     r9d, r9d
0x18000c832  lea     rdx, byte_180015741
0x18000c839  mov     rcx, rdi
0x18000c83c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c841  mov     rcx, rbx
0x18000c844  add     rsp, 130h
0x18000c84b  pop     rdi
0x18000c84c  pop     rbx
0x18000c84d  pop     rbp
0x18000c84e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
