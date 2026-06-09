# SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StopActivity(void)

- ea: `0x18000d010`
- end: `0x18000d293`
- name: `?StopActivity@UpdateRegistryValues@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d06a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d20f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d06a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d20f`
- `KERNEL32!GetCurrentThreadId` at `0x18000d22b`
- `KERNEL32!GetCurrentThreadId` at `0x18000d22b`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues *this)
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
        (unsigned int)&dword_1800141C4,
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
        (unsigned int)byte_180014313,
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
0x18000d010  push    rbp
0x18000d012  push    rbx
0x18000d013  push    rdi
0x18000d014  lea     rbp, [rsp+10h]
0x18000d019  sub     rsp, 130h
0x18000d020  mov     rbx, rcx
0x18000d023  mov     rdi, [rcx+110h]
0x18000d02a  mov     eax, [rdi+48h]
0x18000d02d  test    eax, eax
0x18000d02f  jns     loc_18000D1F0
0x18000d035  add     rdi, 50h ; 'P'
0x18000d039  cmp     eax, [rdi+8]
0x18000d03c  jnz     loc_18000D1F0
0x18000d042  test    rdi, rdi
0x18000d045  jz      loc_18000D1F0
0x18000d04b  lea     rdx, [rbp+SRWLock]
0x18000d04f  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d054  mov     rax, [rbx+110h]
0x18000d05b  mov     dword ptr [rax], 2
0x18000d061  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000d065  test    rcx, rcx
0x18000d068  jz      short loc_18000D076
0x18000d06a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d071  nop     dword ptr [rax+rax+00h]
0x18000d076  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000d07b  mov     rcx, [rax+8]
0x18000d07f  mov     eax, [rcx]
0x18000d081  cmp     eax, 5
0x18000d084  jbe     loc_18000D281
0x18000d08a  mov     rax, [rdi+30h]
0x18000d08e  mov     [rbp+var_70], rax
0x18000d092  mov     eax, [rdi+44h]
0x18000d095  mov     dword ptr [rbp+SRWLock], eax
0x18000d098  mov     eax, [rdi+10h]
0x18000d09b  mov     [rbp+arg_8], eax
0x18000d09e  mov     rax, [rdi+78h]
0x18000d0a2  mov     [rbp+var_68], rax
0x18000d0a6  mov     rax, [rdi+70h]
0x18000d0aa  mov     [rbp+var_60], rax
0x18000d0ae  mov     eax, [rdi+68h]
0x18000d0b1  mov     dword ptr [rbp+arg_10], eax
0x18000d0b4  mov     rax, [rdi+60h]
0x18000d0b8  mov     [rbp+var_58], rax
0x18000d0bc  mov     rax, [rdi+58h]
0x18000d0c0  mov     [rbp+var_50], rax
0x18000d0c4  mov     eax, [rdi+50h]
0x18000d0c7  mov     [rbp+arg_18], eax
0x18000d0ca  mov     rax, [rdi+48h]
0x18000d0ce  mov     [rbp+var_48], rax
0x18000d0d2  mov     eax, [rdi+20h]
0x18000d0d5  mov     [rbp+var_80], eax
0x18000d0d8  mov     rax, [rdi+18h]
0x18000d0dc  mov     [rbp+var_40], rax
0x18000d0e0  mov     eax, [rdi]
0x18000d0e2  mov     [rbp+var_7C], eax
0x18000d0e5  mov     rax, [rdi+80h]
0x18000d0ec  mov     [rbp+var_38], rax
0x18000d0f0  mov     eax, [rdi+40h]
0x18000d0f3  mov     [rbp+var_78], eax
0x18000d0f6  mov     rax, [rdi+38h]
0x18000d0fa  mov     [rbp+var_30], rax
0x18000d0fe  mov     eax, [rdi+8]
0x18000d101  mov     [rbp+var_74], eax
0x18000d104  mov     [rbp+var_28], 1000000h
0x18000d10c  mov     [rbp+var_20], 0
0x18000d114  mov     r8, [rbx+110h]
0x18000d11b  add     r8, 8
0x18000d11f  lea     rax, [rbp+var_70]
0x18000d123  mov     [rsp+140h+var_90], rax
0x18000d12b  lea     rax, [rbp+SRWLock]
0x18000d12f  mov     [rsp+140h+var_98], rax
0x18000d137  lea     rax, [rbp+arg_8]
0x18000d13b  mov     [rsp+140h+var_A0], rax
0x18000d143  lea     rax, [rbp+var_68]
0x18000d147  mov     [rsp+140h+var_A8], rax
0x18000d14f  lea     rax, [rbp+var_60]
0x18000d153  mov     [rsp+140h+var_B0], rax
0x18000d15b  lea     rax, [rbp+arg_10]
0x18000d15f  mov     [rsp+140h+var_B8], rax
0x18000d167  lea     rax, [rbp+var_58]
0x18000d16b  mov     [rsp+140h+var_C0], rax
0x18000d173  lea     rax, [rbp+var_50]
0x18000d177  mov     [rsp+140h+var_C8], rax
0x18000d17c  lea     rax, [rbp+arg_18]
0x18000d180  mov     [rsp+140h+var_D0], rax
0x18000d185  lea     rax, [rbp+var_48]
0x18000d189  mov     [rsp+140h+var_D8], rax
0x18000d18e  lea     rax, [rbp+var_80]
0x18000d192  mov     [rsp+140h+var_E0], rax
0x18000d197  lea     rax, [rbp+var_40]
0x18000d19b  mov     [rsp+140h+var_E8], rax
0x18000d1a0  lea     rax, [rbp+var_7C]
0x18000d1a4  mov     [rsp+140h+var_F0], rax
0x18000d1a9  lea     rax, [rbp+var_38]
0x18000d1ad  mov     [rsp+140h+var_F8], rax
0x18000d1b2  lea     rax, [rbp+var_78]
0x18000d1b6  mov     [rsp+140h+var_100], rax
0x18000d1bb  lea     rax, [rbp+var_30]
0x18000d1bf  mov     [rsp+140h+var_108], rax
0x18000d1c4  lea     rax, [rbp+var_74]
0x18000d1c8  mov     [rsp+140h+var_110], rax
0x18000d1cd  lea     rax, [rbp+var_28]
0x18000d1d1  mov     [rsp+140h+var_118], rax
0x18000d1d6  lea     rax, [rbp+var_20]
0x18000d1da  mov     [rsp+140h+var_120], rax
0x18000d1df  lea     rdx, dword_1800141C4
0x18000d1e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d1eb  jmp     loc_18000D281
0x18000d1f0  lea     rdx, [rbp+SRWLock]
0x18000d1f4  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d1f9  mov     rax, [rbx+110h]
0x18000d200  mov     dword ptr [rax], 2
0x18000d206  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000d20a  test    rcx, rcx
0x18000d20d  jz      short loc_18000D21B
0x18000d20f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d216  nop     dword ptr [rax+rax+00h]
0x18000d21b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000d220  mov     rdi, [rax+8]
0x18000d224  mov     eax, [rdi]
0x18000d226  cmp     eax, 5
0x18000d229  jbe     short loc_18000D281
0x18000d22b  call    cs:__imp_GetCurrentThreadId
0x18000d232  nop     dword ptr [rax+rax+00h]
0x18000d237  mov     dword ptr [rbp+SRWLock], eax
0x18000d23a  mov     r8, [rbx+110h]
0x18000d241  mov     eax, [r8+48h]
0x18000d245  mov     [rbp+arg_8], eax
0x18000d248  mov     [rbp+arg_10], 0
0x18000d250  add     r8, 8
0x18000d254  lea     rax, [rbp+SRWLock]
0x18000d258  mov     [rsp+140h+var_110], rax
0x18000d25d  lea     rax, [rbp+arg_8]
0x18000d261  mov     [rsp+140h+var_118], rax
0x18000d266  lea     rax, [rbp+arg_10]
0x18000d26a  mov     [rsp+140h+var_120], rax
0x18000d26f  xor     r9d, r9d
0x18000d272  lea     rdx, byte_180014313
0x18000d279  mov     rcx, rdi
0x18000d27c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d281  mov     rcx, rbx
0x18000d284  add     rsp, 130h
0x18000d28b  pop     rdi
0x18000d28c  pop     rbx
0x18000d28d  pop     rbp
0x18000d28e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
