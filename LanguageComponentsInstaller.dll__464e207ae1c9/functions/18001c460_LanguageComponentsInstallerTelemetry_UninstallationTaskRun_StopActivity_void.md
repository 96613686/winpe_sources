# LanguageComponentsInstallerTelemetry::UninstallationTaskRun::StopActivity(void)

- ea: `0x18001c460`
- end: `0x18001c6e3`
- name: `?StopActivity@UninstallationTaskRun@LanguageComponentsInstallerTelemetry@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::UninstallationTaskRun *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800013a4`
- `0x18000196c`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x18001c460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c4ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c64d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c4ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c64d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c684`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c684`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationTaskRun::StopActivity(
        LanguageComponentsInstallerTelemetry::UninstallationTaskRun *this)
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
          (int)&dword_18002F64C,
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
          (int)word_18002F9AA,
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
0x18001c460  push    rbp
0x18001c462  push    rbx
0x18001c463  push    rdi
0x18001c464  lea     rbp, [rsp-47h]
0x18001c469  sub     rsp, 100h
0x18001c470  mov     rdi, [rcx+110h]
0x18001c477  mov     rbx, rcx
0x18001c47a  mov     eax, [rdi+48h]
0x18001c47d  test    eax, eax
0x18001c47f  jns     loc_18001C62E
0x18001c485  add     rdi, 50h ; 'P'
0x18001c489  cmp     eax, [rdi+8]
0x18001c48c  jnz     loc_18001C62E
0x18001c492  test    rdi, rdi
0x18001c495  jz      loc_18001C62E
0x18001c49b  lea     rdx, [rbp+57h+SRWLock]
0x18001c49f  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c4a4  mov     rax, [rbx+110h]
0x18001c4ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c4af  mov     dword ptr [rax], 2
0x18001c4b5  test    rcx, rcx
0x18001c4b8  jz      short loc_18001C4C0
0x18001c4ba  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c4c0  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001c4c5  mov     r9, rax
0x18001c4c8  mov     ecx, [rax]
0x18001c4ca  cmp     ecx, 5
0x18001c4cd  jbe     loc_18001C6D1
0x18001c4d3  mov     rax, [rax+18h]
0x18001c4d7  mov     rdx, 400000000000h
0x18001c4e1  mov     rcx, [r9+10h]
0x18001c4e5  test    rdx, rcx
0x18001c4e8  jz      loc_18001C6D1
0x18001c4ee  mov     rcx, rax
0x18001c4f1  and     rcx, rdx
0x18001c4f4  cmp     rcx, rax
0x18001c4f7  jnz     loc_18001C6D1
0x18001c4fd  mov     rax, [rdi+78h]
0x18001c501  lea     rdx, dword_18002F64C; int
0x18001c508  mov     r8, [rbx+110h]
0x18001c50f  mov     rcx, r9; int
0x18001c512  mov     [rbp+57h+var_68], rax
0x18001c516  add     r8, 8; int
0x18001c51a  mov     rax, [rdi+70h]
0x18001c51e  mov     [rbp+57h+var_60], rax
0x18001c522  mov     eax, [rdi+68h]
0x18001c525  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001c528  mov     rax, [rdi+60h]
0x18001c52c  mov     [rbp+57h+var_58], rax
0x18001c530  mov     rax, [rdi+58h]
0x18001c534  mov     [rbp+57h+var_50], rax
0x18001c538  mov     eax, [rdi+50h]
0x18001c53b  mov     dword ptr [rbp+57h+arg_8], eax
0x18001c53e  mov     rax, [rdi+48h]
0x18001c542  mov     [rbp+57h+var_48], rax
0x18001c546  mov     eax, [rdi+20h]
0x18001c549  mov     dword ptr [rbp+57h+arg_10], eax
0x18001c54c  mov     rax, [rdi+18h]
0x18001c550  mov     [rbp+57h+var_40], rax
0x18001c554  mov     eax, [rdi]
0x18001c556  mov     dword ptr [rbp+57h+arg_18], eax
0x18001c559  mov     rax, [rdi+80h]
0x18001c560  mov     [rbp+57h+var_38], rax
0x18001c564  mov     eax, [rdi+40h]
0x18001c567  mov     dword ptr [rbp+57h+var_70], eax
0x18001c56a  mov     rax, [rdi+38h]
0x18001c56e  mov     [rbp+57h+var_30], rax
0x18001c572  mov     eax, [rdi+8]
0x18001c575  mov     dword ptr [rbp+57h+var_70+4], eax
0x18001c578  lea     rax, [rbp+57h+var_68]
0x18001c57c  mov     [rsp+110h+var_78], rax; __int64
0x18001c584  lea     rax, [rbp+57h+var_60]
0x18001c588  mov     [rsp+110h+var_80], rax; __int64
0x18001c590  lea     rax, [rbp+57h+SRWLock]
0x18001c594  mov     [rsp+110h+var_88], rax; __int64
0x18001c59c  lea     rax, [rbp+57h+var_58]
0x18001c5a0  mov     [rsp+110h+var_90], rax; __int64
0x18001c5a8  lea     rax, [rbp+57h+var_50]
0x18001c5ac  mov     [rsp+110h+var_98], rax; __int64
0x18001c5b1  lea     rax, [rbp+57h+arg_8]
0x18001c5b5  mov     [rsp+110h+var_A0], rax; __int64
0x18001c5ba  lea     rax, [rbp+57h+var_48]
0x18001c5be  mov     [rsp+110h+var_A8], rax; __int64
0x18001c5c3  lea     rax, [rbp+57h+arg_10]
0x18001c5c7  mov     [rsp+110h+var_B0], rax; __int64
0x18001c5cc  lea     rax, [rbp+57h+var_40]
0x18001c5d0  mov     [rsp+110h+var_B8], rax; __int64
0x18001c5d5  lea     rax, [rbp+57h+arg_18]
0x18001c5d9  mov     [rsp+110h+var_C0], rax; __int64
0x18001c5de  lea     rax, [rbp+57h+var_38]
0x18001c5e2  mov     [rsp+110h+var_C8], rax; __int64
0x18001c5e7  lea     rax, [rbp+57h+var_70]
0x18001c5eb  mov     [rsp+110h+var_D0], rax; __int64
0x18001c5f0  lea     rax, [rbp+57h+var_30]
0x18001c5f4  mov     [rsp+110h+var_D8], rax; __int64
0x18001c5f9  lea     rax, [rbp+57h+var_70+4]
0x18001c5fd  mov     [rsp+110h+var_E0], rax; __int64
0x18001c602  lea     rax, [rbp+57h+var_28]
0x18001c606  mov     [rsp+110h+var_E8], rax; __int64
0x18001c60b  lea     rax, [rbp+57h+var_20]
0x18001c60f  mov     [rsp+110h+var_F0], rax; __int64
0x18001c614  mov     [rbp+57h+var_28], 1000000h
0x18001c61c  mov     [rbp+57h+var_20], 3000000h
0x18001c624  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001c629  jmp     loc_18001C6D1
0x18001c62e  lea     rdx, [rbp+57h+SRWLock]
0x18001c632  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c637  mov     rax, [rbx+110h]
0x18001c63e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c642  mov     dword ptr [rax], 2
0x18001c648  test    rcx, rcx
0x18001c64b  jz      short loc_18001C653
0x18001c64d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c653  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001c658  mov     rdi, rax
0x18001c65b  mov     ecx, [rax]
0x18001c65d  cmp     ecx, 5
0x18001c660  jbe     short loc_18001C6D1
0x18001c662  mov     rax, [rax+18h]
0x18001c666  mov     rdx, 400000000000h
0x18001c670  mov     rcx, [rdi+10h]
0x18001c674  test    rdx, rcx
0x18001c677  jz      short loc_18001C6D1
0x18001c679  mov     rcx, rax
0x18001c67c  and     rcx, rdx
0x18001c67f  cmp     rcx, rax
0x18001c682  jnz     short loc_18001C6D1
0x18001c684  call    cs:__imp_GetCurrentThreadId
0x18001c68a  mov     r8, [rbx+110h]
0x18001c691  lea     rdx, word_18002F9AA
0x18001c698  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001c69b  mov     rcx, rdi
0x18001c69e  mov     eax, [r8+48h]
0x18001c6a2  add     r8, 8
0x18001c6a6  mov     dword ptr [rbp+57h+arg_8], eax
0x18001c6a9  lea     rax, [rbp+57h+SRWLock]
0x18001c6ad  mov     [rsp+110h+var_E0], rax
0x18001c6b2  lea     rax, [rbp+57h+arg_8]
0x18001c6b6  mov     [rsp+110h+var_E8], rax
0x18001c6bb  lea     rax, [rbp+57h+arg_10]
0x18001c6bf  mov     [rsp+110h+var_F0], rax
0x18001c6c4  mov     [rbp+57h+arg_10], 3000000h
0x18001c6cc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c6d1  mov     rcx, rbx
0x18001c6d4  add     rsp, 100h
0x18001c6db  pop     rdi
0x18001c6dc  pop     rbx
0x18001c6dd  pop     rbp
0x18001c6de  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
