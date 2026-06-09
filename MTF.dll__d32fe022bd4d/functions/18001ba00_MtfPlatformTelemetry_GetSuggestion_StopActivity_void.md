# MtfPlatformTelemetry::GetSuggestion::StopActivity(void)

- ea: `0x18001ba00`
- end: `0x18001bc6e`
- name: `?StopActivity@GetSuggestion@MtfPlatformTelemetry@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(MtfPlatformTelemetry::GetSuggestion *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800016dc`
- `0x1800019f0`
- `0x1800053cc`
- `0x180018c84`
- `0x180018d00`
- `0x18001ba00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bbf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bbf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bc0f`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::GetSuggestion::StopActivity(MtfPlatformTelemetry::GetSuggestion *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  _DWORD *v6; // rcx
  int v7; // r9d
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v6 > 5u )
    {
      v18 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)word_18003626A,
        v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&dword_18003644C,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001ba00  push    rbp
0x18001ba02  push    rbx
0x18001ba03  push    rdi
0x18001ba04  lea     rbp, [rsp+10h]
0x18001ba09  sub     rsp, 130h
0x18001ba10  mov     rdi, [rcx+110h]
0x18001ba17  mov     rbx, rcx
0x18001ba1a  mov     eax, [rdi+48h]
0x18001ba1d  test    eax, eax
0x18001ba1f  jns     loc_18001BBDA
0x18001ba25  add     rdi, 50h ; 'P'
0x18001ba29  cmp     eax, [rdi+8]
0x18001ba2c  jnz     loc_18001BBDA
0x18001ba32  test    rdi, rdi
0x18001ba35  jz      loc_18001BBDA
0x18001ba3b  lea     rdx, [rbp+SRWLock]
0x18001ba3f  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ba44  mov     rax, [rbx+110h]
0x18001ba4b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001ba4f  mov     dword ptr [rax], 2
0x18001ba55  test    rcx, rcx
0x18001ba58  jz      short loc_18001BA60
0x18001ba5a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ba60  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001ba65  mov     rcx, [rax+8]
0x18001ba69  mov     eax, [rcx]
0x18001ba6b  cmp     eax, 5
0x18001ba6e  jbe     loc_18001BC5C
0x18001ba74  mov     rax, [rdi+30h]
0x18001ba78  lea     rdx, word_18003626A
0x18001ba7f  mov     [rbp+var_70], rax
0x18001ba83  mov     eax, [rdi+44h]
0x18001ba86  mov     dword ptr [rbp+SRWLock], eax
0x18001ba89  mov     eax, [rdi+10h]
0x18001ba8c  mov     [rbp+arg_8], eax
0x18001ba8f  mov     rax, [rdi+78h]
0x18001ba93  mov     [rbp+var_68], rax
0x18001ba97  mov     rax, [rdi+70h]
0x18001ba9b  mov     [rbp+var_60], rax
0x18001ba9f  mov     eax, [rdi+68h]
0x18001baa2  mov     r8, [rbx+110h]
0x18001baa9  mov     dword ptr [rbp+arg_10], eax
0x18001baac  add     r8, 8
0x18001bab0  mov     rax, [rdi+60h]
0x18001bab4  mov     [rbp+var_58], rax
0x18001bab8  mov     rax, [rdi+58h]
0x18001babc  mov     [rbp+var_50], rax
0x18001bac0  mov     eax, [rdi+50h]
0x18001bac3  mov     [rbp+arg_18], eax
0x18001bac6  mov     rax, [rdi+48h]
0x18001baca  mov     [rbp+var_48], rax
0x18001bace  mov     eax, [rdi+20h]
0x18001bad1  mov     [rbp+var_80], eax
0x18001bad4  mov     rax, [rdi+18h]
0x18001bad8  mov     [rbp+var_40], rax
0x18001badc  mov     eax, [rdi]
0x18001bade  mov     [rbp+var_7C], eax
0x18001bae1  mov     rax, [rdi+80h]
0x18001bae8  mov     [rbp+var_38], rax
0x18001baec  mov     eax, [rdi+40h]
0x18001baef  mov     [rbp+var_78], eax
0x18001baf2  mov     rax, [rdi+38h]
0x18001baf6  mov     [rbp+var_30], rax
0x18001bafa  mov     eax, [rdi+8]
0x18001bafd  mov     [rbp+var_74], eax
0x18001bb00  lea     rax, [rbp+var_70]
0x18001bb04  mov     [rsp+140h+var_90], rax
0x18001bb0c  lea     rax, [rbp+SRWLock]
0x18001bb10  mov     [rsp+140h+var_98], rax
0x18001bb18  lea     rax, [rbp+arg_8]
0x18001bb1c  mov     [rsp+140h+var_A0], rax
0x18001bb24  lea     rax, [rbp+var_68]
0x18001bb28  mov     [rsp+140h+var_A8], rax
0x18001bb30  lea     rax, [rbp+var_60]
0x18001bb34  mov     [rsp+140h+var_B0], rax
0x18001bb3c  lea     rax, [rbp+arg_10]
0x18001bb40  mov     [rsp+140h+var_B8], rax
0x18001bb48  lea     rax, [rbp+var_58]
0x18001bb4c  mov     [rsp+140h+var_C0], rax
0x18001bb54  lea     rax, [rbp+var_50]
0x18001bb58  mov     [rsp+140h+var_C8], rax
0x18001bb5d  lea     rax, [rbp+arg_18]
0x18001bb61  mov     [rsp+140h+var_D0], rax
0x18001bb66  lea     rax, [rbp+var_48]
0x18001bb6a  mov     [rsp+140h+var_D8], rax
0x18001bb6f  lea     rax, [rbp+var_80]
0x18001bb73  mov     [rsp+140h+var_E0], rax
0x18001bb78  lea     rax, [rbp+var_40]
0x18001bb7c  mov     [rsp+140h+var_E8], rax
0x18001bb81  lea     rax, [rbp+var_7C]
0x18001bb85  mov     [rsp+140h+var_F0], rax
0x18001bb8a  lea     rax, [rbp+var_38]
0x18001bb8e  mov     [rsp+140h+var_F8], rax
0x18001bb93  lea     rax, [rbp+var_78]
0x18001bb97  mov     [rsp+140h+var_100], rax
0x18001bb9c  lea     rax, [rbp+var_30]
0x18001bba0  mov     [rsp+140h+var_108], rax
0x18001bba5  lea     rax, [rbp+var_74]
0x18001bba9  mov     [rsp+140h+var_110], rax
0x18001bbae  lea     rax, [rbp+var_28]
0x18001bbb2  mov     [rsp+140h+var_118], rax
0x18001bbb7  lea     rax, [rbp+var_20]
0x18001bbbb  mov     [rsp+140h+var_120], rax
0x18001bbc0  mov     [rbp+var_28], 1000000h
0x18001bbc8  mov     [rbp+var_20], 0
0x18001bbd0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001bbd5  jmp     loc_18001BC5C
0x18001bbda  lea     rdx, [rbp+SRWLock]
0x18001bbde  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001bbe3  mov     rax, [rbx+110h]
0x18001bbea  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001bbee  mov     dword ptr [rax], 2
0x18001bbf4  test    rcx, rcx
0x18001bbf7  jz      short loc_18001BBFF
0x18001bbf9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bbff  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001bc04  mov     rdi, [rax+8]
0x18001bc08  mov     eax, [rdi]
0x18001bc0a  cmp     eax, 5
0x18001bc0d  jbe     short loc_18001BC5C
0x18001bc0f  call    cs:__imp_GetCurrentThreadId
0x18001bc15  mov     r8, [rbx+110h]
0x18001bc1c  lea     rdx, dword_18003644C
0x18001bc23  mov     dword ptr [rbp+SRWLock], eax
0x18001bc26  mov     rcx, rdi
0x18001bc29  mov     eax, [r8+48h]
0x18001bc2d  add     r8, 8
0x18001bc31  mov     [rbp+arg_8], eax
0x18001bc34  lea     rax, [rbp+SRWLock]
0x18001bc38  mov     [rsp+140h+var_110], rax
0x18001bc3d  lea     rax, [rbp+arg_8]
0x18001bc41  mov     [rsp+140h+var_118], rax
0x18001bc46  lea     rax, [rbp+arg_10]
0x18001bc4a  mov     [rsp+140h+var_120], rax
0x18001bc4f  mov     [rbp+arg_10], 0
0x18001bc57  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001bc5c  mov     rcx, rbx
0x18001bc5f  add     rsp, 130h
0x18001bc66  pop     rdi
0x18001bc67  pop     rbx
0x18001bc68  pop     rbp
0x18001bc69  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
