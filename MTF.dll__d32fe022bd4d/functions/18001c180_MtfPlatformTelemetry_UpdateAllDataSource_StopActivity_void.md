# MtfPlatformTelemetry::UpdateAllDataSource::StopActivity(void)

- ea: `0x18001c180`
- end: `0x18001c3ee`
- name: `?StopActivity@UpdateAllDataSource@MtfPlatformTelemetry@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateAllDataSource *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800016dc`
- `0x1800019f0`
- `0x1800053cc`
- `0x180018c84`
- `0x180018d00`
- `0x18001c180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c1da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c1da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c379`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c38f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c38f`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateAllDataSource::StopActivity(
        MtfPlatformTelemetry::UpdateAllDataSource *this)
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
        (unsigned int)&word_18003684E,
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
        (unsigned int)word_1800363B2,
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
0x18001c180  push    rbp
0x18001c182  push    rbx
0x18001c183  push    rdi
0x18001c184  lea     rbp, [rsp+10h]
0x18001c189  sub     rsp, 130h
0x18001c190  mov     rdi, [rcx+110h]
0x18001c197  mov     rbx, rcx
0x18001c19a  mov     eax, [rdi+48h]
0x18001c19d  test    eax, eax
0x18001c19f  jns     loc_18001C35A
0x18001c1a5  add     rdi, 50h ; 'P'
0x18001c1a9  cmp     eax, [rdi+8]
0x18001c1ac  jnz     loc_18001C35A
0x18001c1b2  test    rdi, rdi
0x18001c1b5  jz      loc_18001C35A
0x18001c1bb  lea     rdx, [rbp+SRWLock]
0x18001c1bf  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c1c4  mov     rax, [rbx+110h]
0x18001c1cb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001c1cf  mov     dword ptr [rax], 2
0x18001c1d5  test    rcx, rcx
0x18001c1d8  jz      short loc_18001C1E0
0x18001c1da  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c1e0  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001c1e5  mov     rcx, [rax+8]
0x18001c1e9  mov     eax, [rcx]
0x18001c1eb  cmp     eax, 5
0x18001c1ee  jbe     loc_18001C3DC
0x18001c1f4  mov     rax, [rdi+30h]
0x18001c1f8  lea     rdx, word_18003684E
0x18001c1ff  mov     [rbp+var_70], rax
0x18001c203  mov     eax, [rdi+44h]
0x18001c206  mov     dword ptr [rbp+SRWLock], eax
0x18001c209  mov     eax, [rdi+10h]
0x18001c20c  mov     [rbp+arg_8], eax
0x18001c20f  mov     rax, [rdi+78h]
0x18001c213  mov     [rbp+var_68], rax
0x18001c217  mov     rax, [rdi+70h]
0x18001c21b  mov     [rbp+var_60], rax
0x18001c21f  mov     eax, [rdi+68h]
0x18001c222  mov     r8, [rbx+110h]
0x18001c229  mov     dword ptr [rbp+arg_10], eax
0x18001c22c  add     r8, 8
0x18001c230  mov     rax, [rdi+60h]
0x18001c234  mov     [rbp+var_58], rax
0x18001c238  mov     rax, [rdi+58h]
0x18001c23c  mov     [rbp+var_50], rax
0x18001c240  mov     eax, [rdi+50h]
0x18001c243  mov     [rbp+arg_18], eax
0x18001c246  mov     rax, [rdi+48h]
0x18001c24a  mov     [rbp+var_48], rax
0x18001c24e  mov     eax, [rdi+20h]
0x18001c251  mov     [rbp+var_80], eax
0x18001c254  mov     rax, [rdi+18h]
0x18001c258  mov     [rbp+var_40], rax
0x18001c25c  mov     eax, [rdi]
0x18001c25e  mov     [rbp+var_7C], eax
0x18001c261  mov     rax, [rdi+80h]
0x18001c268  mov     [rbp+var_38], rax
0x18001c26c  mov     eax, [rdi+40h]
0x18001c26f  mov     [rbp+var_78], eax
0x18001c272  mov     rax, [rdi+38h]
0x18001c276  mov     [rbp+var_30], rax
0x18001c27a  mov     eax, [rdi+8]
0x18001c27d  mov     [rbp+var_74], eax
0x18001c280  lea     rax, [rbp+var_70]
0x18001c284  mov     [rsp+140h+var_90], rax
0x18001c28c  lea     rax, [rbp+SRWLock]
0x18001c290  mov     [rsp+140h+var_98], rax
0x18001c298  lea     rax, [rbp+arg_8]
0x18001c29c  mov     [rsp+140h+var_A0], rax
0x18001c2a4  lea     rax, [rbp+var_68]
0x18001c2a8  mov     [rsp+140h+var_A8], rax
0x18001c2b0  lea     rax, [rbp+var_60]
0x18001c2b4  mov     [rsp+140h+var_B0], rax
0x18001c2bc  lea     rax, [rbp+arg_10]
0x18001c2c0  mov     [rsp+140h+var_B8], rax
0x18001c2c8  lea     rax, [rbp+var_58]
0x18001c2cc  mov     [rsp+140h+var_C0], rax
0x18001c2d4  lea     rax, [rbp+var_50]
0x18001c2d8  mov     [rsp+140h+var_C8], rax
0x18001c2dd  lea     rax, [rbp+arg_18]
0x18001c2e1  mov     [rsp+140h+var_D0], rax
0x18001c2e6  lea     rax, [rbp+var_48]
0x18001c2ea  mov     [rsp+140h+var_D8], rax
0x18001c2ef  lea     rax, [rbp+var_80]
0x18001c2f3  mov     [rsp+140h+var_E0], rax
0x18001c2f8  lea     rax, [rbp+var_40]
0x18001c2fc  mov     [rsp+140h+var_E8], rax
0x18001c301  lea     rax, [rbp+var_7C]
0x18001c305  mov     [rsp+140h+var_F0], rax
0x18001c30a  lea     rax, [rbp+var_38]
0x18001c30e  mov     [rsp+140h+var_F8], rax
0x18001c313  lea     rax, [rbp+var_78]
0x18001c317  mov     [rsp+140h+var_100], rax
0x18001c31c  lea     rax, [rbp+var_30]
0x18001c320  mov     [rsp+140h+var_108], rax
0x18001c325  lea     rax, [rbp+var_74]
0x18001c329  mov     [rsp+140h+var_110], rax
0x18001c32e  lea     rax, [rbp+var_28]
0x18001c332  mov     [rsp+140h+var_118], rax
0x18001c337  lea     rax, [rbp+var_20]
0x18001c33b  mov     [rsp+140h+var_120], rax
0x18001c340  mov     [rbp+var_28], 1000000h
0x18001c348  mov     [rbp+var_20], 0
0x18001c350  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001c355  jmp     loc_18001C3DC
0x18001c35a  lea     rdx, [rbp+SRWLock]
0x18001c35e  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c363  mov     rax, [rbx+110h]
0x18001c36a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001c36e  mov     dword ptr [rax], 2
0x18001c374  test    rcx, rcx
0x18001c377  jz      short loc_18001C37F
0x18001c379  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c37f  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001c384  mov     rdi, [rax+8]
0x18001c388  mov     eax, [rdi]
0x18001c38a  cmp     eax, 5
0x18001c38d  jbe     short loc_18001C3DC
0x18001c38f  call    cs:__imp_GetCurrentThreadId
0x18001c395  mov     r8, [rbx+110h]
0x18001c39c  lea     rdx, word_1800363B2
0x18001c3a3  mov     dword ptr [rbp+SRWLock], eax
0x18001c3a6  mov     rcx, rdi
0x18001c3a9  mov     eax, [r8+48h]
0x18001c3ad  add     r8, 8
0x18001c3b1  mov     [rbp+arg_8], eax
0x18001c3b4  lea     rax, [rbp+SRWLock]
0x18001c3b8  mov     [rsp+140h+var_110], rax
0x18001c3bd  lea     rax, [rbp+arg_8]
0x18001c3c1  mov     [rsp+140h+var_118], rax
0x18001c3c6  lea     rax, [rbp+arg_10]
0x18001c3ca  mov     [rsp+140h+var_120], rax
0x18001c3cf  mov     [rbp+arg_10], 0
0x18001c3d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c3dc  mov     rcx, rbx
0x18001c3df  add     rsp, 130h
0x18001c3e6  pop     rdi
0x18001c3e7  pop     rbx
0x18001c3e8  pop     rbp
0x18001c3e9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
