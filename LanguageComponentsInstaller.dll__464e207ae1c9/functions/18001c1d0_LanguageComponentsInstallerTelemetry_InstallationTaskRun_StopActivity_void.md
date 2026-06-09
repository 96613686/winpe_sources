# LanguageComponentsInstallerTelemetry::InstallationTaskRun::StopActivity(void)

- ea: `0x18001c1d0`
- end: `0x18001c453`
- name: `?StopActivity@InstallationTaskRun@LanguageComponentsInstallerTelemetry@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::InstallationTaskRun *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800013a4`
- `0x18000196c`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x18001c1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c22a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c3bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c22a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c3bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c3f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c3f4`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationTaskRun::StopActivity(
        LanguageComponentsInstallerTelemetry::InstallationTaskRun *this)
{
  __int64 v1; // rdi
  int v3; // eax
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  __int64 v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  __int64 v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = v1 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = *(_QWORD *)(v4 + 120);
        v20 = *(_QWORD *)(v4 + 112);
        LODWORD(SRWLock) = *(_DWORD *)(v4 + 104);
        v21 = *(_QWORD *)(v4 + 96);
        v22 = *(_QWORD *)(v4 + 88);
        LODWORD(v30) = *(_DWORD *)(v4 + 80);
        v23 = *(_QWORD *)(v4 + 72);
        LODWORD(v31) = *(_DWORD *)(v4 + 32);
        v24 = *(_QWORD *)(v4 + 24);
        LODWORD(v32) = *(_DWORD *)v4;
        v25 = *(_QWORD *)(v4 + 128);
        v17 = *(_DWORD *)(v4 + 64);
        v26 = *(_QWORD *)(v4 + 56);
        v18 = *(_DWORD *)(v4 + 8);
        v27 = 0x1000000;
        v28[0] = 50331648;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (int)&byte_18002F521,
          v9 + 8,
          v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          (const unsigned __int16 **)&v26,
          (__int64)&v17,
          (const unsigned __int16 **)&v25,
          (__int64)&v32,
          (__int64 **)&v24,
          (__int64)&v31,
          (const unsigned __int16 **)&v23,
          (__int64)&v30,
          (const unsigned __int16 **)&v22,
          (__int64 **)&v21,
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v20,
          (__int64 **)&v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        LODWORD(v30) = *(_DWORD *)(v15 + 72);
        v31 = 50331648;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v12,
          (int)&word_18002F956,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001c1d0  push    rbp
0x18001c1d2  push    rbx
0x18001c1d3  push    rdi
0x18001c1d4  lea     rbp, [rsp-47h]
0x18001c1d9  sub     rsp, 100h
0x18001c1e0  mov     rdi, [rcx+110h]
0x18001c1e7  mov     rbx, rcx
0x18001c1ea  mov     eax, [rdi+48h]
0x18001c1ed  test    eax, eax
0x18001c1ef  jns     loc_18001C39E
0x18001c1f5  add     rdi, 50h ; 'P'
0x18001c1f9  cmp     eax, [rdi+8]
0x18001c1fc  jnz     loc_18001C39E
0x18001c202  test    rdi, rdi
0x18001c205  jz      loc_18001C39E
0x18001c20b  lea     rdx, [rbp+57h+SRWLock]
0x18001c20f  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c214  mov     rax, [rbx+110h]
0x18001c21b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c21f  mov     dword ptr [rax], 2
0x18001c225  test    rcx, rcx
0x18001c228  jz      short loc_18001C230
0x18001c22a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c230  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001c235  mov     r9, rax
0x18001c238  mov     ecx, [rax]
0x18001c23a  cmp     ecx, 5
0x18001c23d  jbe     loc_18001C441
0x18001c243  mov     rax, [rax+18h]
0x18001c247  mov     rdx, 400000000000h
0x18001c251  mov     rcx, [r9+10h]
0x18001c255  test    rdx, rcx
0x18001c258  jz      loc_18001C441
0x18001c25e  mov     rcx, rax
0x18001c261  and     rcx, rdx
0x18001c264  cmp     rcx, rax
0x18001c267  jnz     loc_18001C441
0x18001c26d  mov     rax, [rdi+78h]
0x18001c271  lea     rdx, byte_18002F521; int
0x18001c278  mov     r8, [rbx+110h]
0x18001c27f  mov     rcx, r9; int
0x18001c282  mov     [rbp+57h+var_68], rax
0x18001c286  add     r8, 8; int
0x18001c28a  mov     rax, [rdi+70h]
0x18001c28e  mov     [rbp+57h+var_60], rax
0x18001c292  mov     eax, [rdi+68h]
0x18001c295  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001c298  mov     rax, [rdi+60h]
0x18001c29c  mov     [rbp+57h+var_58], rax
0x18001c2a0  mov     rax, [rdi+58h]
0x18001c2a4  mov     [rbp+57h+var_50], rax
0x18001c2a8  mov     eax, [rdi+50h]
0x18001c2ab  mov     dword ptr [rbp+57h+arg_8], eax
0x18001c2ae  mov     rax, [rdi+48h]
0x18001c2b2  mov     [rbp+57h+var_48], rax
0x18001c2b6  mov     eax, [rdi+20h]
0x18001c2b9  mov     dword ptr [rbp+57h+arg_10], eax
0x18001c2bc  mov     rax, [rdi+18h]
0x18001c2c0  mov     [rbp+57h+var_40], rax
0x18001c2c4  mov     eax, [rdi]
0x18001c2c6  mov     dword ptr [rbp+57h+arg_18], eax
0x18001c2c9  mov     rax, [rdi+80h]
0x18001c2d0  mov     [rbp+57h+var_38], rax
0x18001c2d4  mov     eax, [rdi+40h]
0x18001c2d7  mov     dword ptr [rbp+57h+var_70], eax
0x18001c2da  mov     rax, [rdi+38h]
0x18001c2de  mov     [rbp+57h+var_30], rax
0x18001c2e2  mov     eax, [rdi+8]
0x18001c2e5  mov     dword ptr [rbp+57h+var_70+4], eax
0x18001c2e8  lea     rax, [rbp+57h+var_68]
0x18001c2ec  mov     [rsp+110h+var_78], rax; __int64
0x18001c2f4  lea     rax, [rbp+57h+var_60]
0x18001c2f8  mov     [rsp+110h+var_80], rax; __int64
0x18001c300  lea     rax, [rbp+57h+SRWLock]
0x18001c304  mov     [rsp+110h+var_88], rax; __int64
0x18001c30c  lea     rax, [rbp+57h+var_58]
0x18001c310  mov     [rsp+110h+var_90], rax; __int64
0x18001c318  lea     rax, [rbp+57h+var_50]
0x18001c31c  mov     [rsp+110h+var_98], rax; __int64
0x18001c321  lea     rax, [rbp+57h+arg_8]
0x18001c325  mov     [rsp+110h+var_A0], rax; __int64
0x18001c32a  lea     rax, [rbp+57h+var_48]
0x18001c32e  mov     [rsp+110h+var_A8], rax; __int64
0x18001c333  lea     rax, [rbp+57h+arg_10]
0x18001c337  mov     [rsp+110h+var_B0], rax; __int64
0x18001c33c  lea     rax, [rbp+57h+var_40]
0x18001c340  mov     [rsp+110h+var_B8], rax; __int64
0x18001c345  lea     rax, [rbp+57h+arg_18]
0x18001c349  mov     [rsp+110h+var_C0], rax; __int64
0x18001c34e  lea     rax, [rbp+57h+var_38]
0x18001c352  mov     [rsp+110h+var_C8], rax; __int64
0x18001c357  lea     rax, [rbp+57h+var_70]
0x18001c35b  mov     [rsp+110h+var_D0], rax; __int64
0x18001c360  lea     rax, [rbp+57h+var_30]
0x18001c364  mov     [rsp+110h+var_D8], rax; __int64
0x18001c369  lea     rax, [rbp+57h+var_70+4]
0x18001c36d  mov     [rsp+110h+var_E0], rax; __int64
0x18001c372  lea     rax, [rbp+57h+var_28]
0x18001c376  mov     [rsp+110h+var_E8], rax; __int64
0x18001c37b  lea     rax, [rbp+57h+var_20]
0x18001c37f  mov     [rsp+110h+var_F0], rax; __int64
0x18001c384  mov     [rbp+57h+var_28], 1000000h
0x18001c38c  mov     [rbp+57h+var_20], 3000000h
0x18001c394  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001c399  jmp     loc_18001C441
0x18001c39e  lea     rdx, [rbp+57h+SRWLock]
0x18001c3a2  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c3a7  mov     rax, [rbx+110h]
0x18001c3ae  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c3b2  mov     dword ptr [rax], 2
0x18001c3b8  test    rcx, rcx
0x18001c3bb  jz      short loc_18001C3C3
0x18001c3bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c3c3  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001c3c8  mov     rdi, rax
0x18001c3cb  mov     ecx, [rax]
0x18001c3cd  cmp     ecx, 5
0x18001c3d0  jbe     short loc_18001C441
0x18001c3d2  mov     rax, [rax+18h]
0x18001c3d6  mov     rdx, 400000000000h
0x18001c3e0  mov     rcx, [rdi+10h]
0x18001c3e4  test    rdx, rcx
0x18001c3e7  jz      short loc_18001C441
0x18001c3e9  mov     rcx, rax
0x18001c3ec  and     rcx, rdx
0x18001c3ef  cmp     rcx, rax
0x18001c3f2  jnz     short loc_18001C441
0x18001c3f4  call    cs:__imp_GetCurrentThreadId
0x18001c3fa  mov     r8, [rbx+110h]
0x18001c401  lea     rdx, word_18002F956
0x18001c408  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001c40b  mov     rcx, rdi
0x18001c40e  mov     eax, [r8+48h]
0x18001c412  add     r8, 8
0x18001c416  mov     dword ptr [rbp+57h+arg_8], eax
0x18001c419  lea     rax, [rbp+57h+SRWLock]
0x18001c41d  mov     [rsp+110h+var_E0], rax
0x18001c422  lea     rax, [rbp+57h+arg_8]
0x18001c426  mov     [rsp+110h+var_E8], rax
0x18001c42b  lea     rax, [rbp+57h+arg_10]
0x18001c42f  mov     [rsp+110h+var_F0], rax
0x18001c434  mov     [rbp+57h+arg_10], 3000000h
0x18001c43c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c441  mov     rcx, rbx
0x18001c444  add     rsp, 100h
0x18001c44b  pop     rdi
0x18001c44c  pop     rbx
0x18001c44d  pop     rbp
0x18001c44e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
