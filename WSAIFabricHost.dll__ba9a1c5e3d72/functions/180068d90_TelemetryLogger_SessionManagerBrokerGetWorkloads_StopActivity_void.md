# TelemetryLogger::SessionManagerBrokerGetWorkloads::StopActivity(void)

- ea: `0x180068d90`
- end: `0x180069014`
- name: `?StopActivity@SessionManagerBrokerGetWorkloads@TelemetryLogger@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerGetWorkloads *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180068d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068dea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068f7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068dea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068f7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068fb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068fb4`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerGetWorkloads::StopActivity(
        TelemetryLogger::SessionManagerBrokerGetWorkloads *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v15; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v18; // [rsp+C0h] [rbp+7h] BYREF
  const wchar_t *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v20; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const wchar_t *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v16 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v6,
        (__int64)&byte_18009CD1F,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        &v22,
        (__int64)&v13,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        (__int64)&v26,
        &v18,
        &v17,
        (__int64)&SRWLock,
        &v16,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&word_18009CCBE,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180068d90  push    rbp
0x180068d92  push    rbx
0x180068d93  push    rdi
0x180068d94  lea     rbp, [rsp-47h]
0x180068d99  sub     rsp, 100h
0x180068da0  mov     rdi, [rcx+110h]
0x180068da7  mov     rbx, rcx
0x180068daa  mov     eax, [rdi+48h]
0x180068dad  test    eax, eax
0x180068daf  jns     loc_180068F5D
0x180068db5  add     rdi, 50h ; 'P'
0x180068db9  cmp     eax, [rdi+8]
0x180068dbc  jnz     loc_180068F5D
0x180068dc2  test    rdi, rdi
0x180068dc5  jz      loc_180068F5D
0x180068dcb  lea     rdx, [rbp+57h+SRWLock]
0x180068dcf  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068dd4  mov     rax, [rbx+110h]
0x180068ddb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180068ddf  mov     dword ptr [rax], 2
0x180068de5  test    rcx, rcx
0x180068de8  jz      short loc_180068DF0
0x180068dea  call    cs:__imp_ReleaseSRWLockExclusive
0x180068df0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068df5  mov     r9, [rax+8]
0x180068df9  mov     eax, [r9]
0x180068dfc  cmp     eax, 5
0x180068dff  jbe     loc_180069002
0x180068e05  mov     rdx, [r9+18h]
0x180068e09  mov     rcx, 400000000000h
0x180068e13  mov     rax, [r9+10h]
0x180068e17  test    rcx, rax
0x180068e1a  jz      loc_180069002
0x180068e20  mov     rax, rdx
0x180068e23  and     rax, rcx
0x180068e26  cmp     rax, rdx
0x180068e29  jnz     loc_180069002
0x180068e2f  mov     rax, [rdi+78h]
0x180068e33  lea     rdx, byte_18009CD1F
0x180068e3a  mov     r8, [rbx+110h]
0x180068e41  mov     rcx, r9
0x180068e44  mov     [rbp+57h+var_68], rax
0x180068e48  add     r8, 8
0x180068e4c  mov     rax, [rdi+70h]
0x180068e50  mov     [rbp+57h+var_60], rax
0x180068e54  mov     eax, [rdi+68h]
0x180068e57  mov     dword ptr [rbp+57h+SRWLock], eax
0x180068e5a  mov     rax, [rdi+60h]
0x180068e5e  mov     [rbp+57h+var_58], rax
0x180068e62  mov     rax, [rdi+58h]
0x180068e66  mov     [rbp+57h+var_50], rax
0x180068e6a  mov     eax, [rdi+50h]
0x180068e6d  mov     [rbp+57h+arg_8], eax
0x180068e70  mov     rax, [rdi+48h]
0x180068e74  mov     [rbp+57h+var_48], rax
0x180068e78  mov     eax, [rdi+20h]
0x180068e7b  mov     dword ptr [rbp+57h+arg_10], eax
0x180068e7e  mov     rax, [rdi+18h]
0x180068e82  mov     [rbp+57h+var_40], rax
0x180068e86  mov     eax, [rdi]
0x180068e88  mov     [rbp+57h+arg_18], eax
0x180068e8b  mov     rax, [rdi+80h]
0x180068e92  mov     [rbp+57h+var_38], rax
0x180068e96  mov     eax, [rdi+40h]
0x180068e99  mov     [rbp+57h+var_70], eax
0x180068e9c  mov     rax, [rdi+38h]
0x180068ea0  mov     [rbp+57h+var_30], rax
0x180068ea4  mov     eax, [rdi+8]
0x180068ea7  mov     [rbp+57h+var_6C], eax
0x180068eaa  mov     eax, 1000000h
0x180068eaf  mov     [rbp+57h+var_28], rax
0x180068eb3  mov     [rbp+57h+var_20], rax
0x180068eb7  lea     rax, [rbp+57h+var_68]
0x180068ebb  mov     [rsp+110h+var_78], rax
0x180068ec3  lea     rax, [rbp+57h+var_60]
0x180068ec7  mov     [rsp+110h+var_80], rax
0x180068ecf  lea     rax, [rbp+57h+SRWLock]
0x180068ed3  mov     [rsp+110h+var_88], rax
0x180068edb  lea     rax, [rbp+57h+var_58]
0x180068edf  mov     [rsp+110h+var_90], rax
0x180068ee7  lea     rax, [rbp+57h+var_50]
0x180068eeb  mov     [rsp+110h+var_98], rax
0x180068ef0  lea     rax, [rbp+57h+arg_8]
0x180068ef4  mov     [rsp+110h+var_A0], rax
0x180068ef9  lea     rax, [rbp+57h+var_48]
0x180068efd  mov     [rsp+110h+var_A8], rax
0x180068f02  lea     rax, [rbp+57h+arg_10]
0x180068f06  mov     [rsp+110h+var_B0], rax
0x180068f0b  lea     rax, [rbp+57h+var_40]
0x180068f0f  mov     [rsp+110h+var_B8], rax
0x180068f14  lea     rax, [rbp+57h+arg_18]
0x180068f18  mov     [rsp+110h+var_C0], rax
0x180068f1d  lea     rax, [rbp+57h+var_38]
0x180068f21  mov     [rsp+110h+var_C8], rax
0x180068f26  lea     rax, [rbp+57h+var_70]
0x180068f2a  mov     [rsp+110h+var_D0], rax
0x180068f2f  lea     rax, [rbp+57h+var_30]
0x180068f33  mov     [rsp+110h+var_D8], rax
0x180068f38  lea     rax, [rbp+57h+var_6C]
0x180068f3c  mov     [rsp+110h+var_E0], rax
0x180068f41  lea     rax, [rbp+57h+var_28]
0x180068f45  mov     [rsp+110h+var_E8], rax
0x180068f4a  lea     rax, [rbp+57h+var_20]
0x180068f4e  mov     [rsp+110h+var_F0], rax
0x180068f53  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180068f58  jmp     loc_180069002
0x180068f5d  lea     rdx, [rbp+57h+SRWLock]
0x180068f61  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068f66  mov     rax, [rbx+110h]
0x180068f6d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180068f71  mov     dword ptr [rax], 2
0x180068f77  test    rcx, rcx
0x180068f7a  jz      short loc_180068F82
0x180068f7c  call    cs:__imp_ReleaseSRWLockExclusive
0x180068f82  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068f87  mov     rdi, [rax+8]
0x180068f8b  mov     eax, [rdi]
0x180068f8d  cmp     eax, 5
0x180068f90  jbe     short loc_180069002
0x180068f92  mov     rdx, [rdi+18h]
0x180068f96  mov     rcx, 400000000000h
0x180068fa0  mov     rax, [rdi+10h]
0x180068fa4  test    rcx, rax
0x180068fa7  jz      short loc_180069002
0x180068fa9  mov     rax, rdx
0x180068fac  and     rax, rcx
0x180068faf  cmp     rax, rdx
0x180068fb2  jnz     short loc_180069002
0x180068fb4  call    cs:__imp_GetCurrentThreadId
0x180068fba  mov     r8, [rbx+110h]
0x180068fc1  lea     rdx, word_18009CCBE
0x180068fc8  mov     dword ptr [rbp+57h+SRWLock], eax
0x180068fcb  mov     rcx, rdi
0x180068fce  mov     eax, [r8+48h]
0x180068fd2  add     r8, 8
0x180068fd6  mov     [rbp+57h+arg_8], eax
0x180068fd9  mov     eax, 1000000h
0x180068fde  mov     [rbp+57h+arg_10], rax
0x180068fe2  lea     rax, [rbp+57h+SRWLock]
0x180068fe6  mov     [rsp+110h+var_E0], rax
0x180068feb  lea     rax, [rbp+57h+arg_8]
0x180068fef  mov     [rsp+110h+var_E8], rax
0x180068ff4  lea     rax, [rbp+57h+arg_10]
0x180068ff8  mov     [rsp+110h+var_F0], rax
0x180068ffd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069002  mov     rcx, rbx
0x180069005  add     rsp, 100h
0x18006900c  pop     rdi
0x18006900d  pop     rbx
0x18006900e  pop     rbp
0x18006900f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
