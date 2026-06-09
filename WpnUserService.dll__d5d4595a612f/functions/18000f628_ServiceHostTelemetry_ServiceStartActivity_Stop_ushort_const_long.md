# ServiceHostTelemetry::ServiceStartActivity::Stop(ushort const *,long)

- ea: `0x18000f628`
- end: `0x18000f902`
- name: `?Stop@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z`
- size: `730`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000e9e8`

## callees

- `0x180001e50`
- `0x18000214c`
- `0x18000a648`
- `0x18000e400`
- `0x18000e47c`
- `0x18000f628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f692`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f841`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f692`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f883`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f883`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::Stop(
        ServiceHostTelemetry::ServiceStartActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r8
  RTL_SRWLOCK *v14; // rcx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rax
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // [rsp+B0h] [rbp-80h] BYREF
  int v22; // [rsp+B4h] [rbp-7Ch] BYREF
  int v23; // [rsp+B8h] [rbp-78h] BYREF
  int v24; // [rsp+BCh] [rbp-74h] BYREF
  int v25; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-60h] BYREF
  __int64 *v28; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v29; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v31; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v32; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v33; // [rsp+100h] [rbp-30h] BYREF
  __int64 *v34; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v35; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v36; // [rsp+118h] [rbp-18h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  DWORD v38; // [rsp+158h] [rbp+28h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = ServiceHostLogging::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      v12 = *((_QWORD *)v10 + 3);
      if ( (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
      {
        v29 = (__int64 *)*((_QWORD *)v8 + 15);
        v30 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
        v13 = *((_QWORD *)this + 34);
        v38 = v8[26];
        v31 = (__int64 *)*((_QWORD *)v8 + 12);
        v32 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
        v22 = v8[20];
        v33 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
        v23 = v8[8];
        v34 = (__int64 *)*((_QWORD *)v8 + 3);
        v24 = *v8;
        v35 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
        v25 = v8[16];
        v36 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
        v21 = v8[2];
        v26 = 0x1000000;
        v27 = 0x1000000;
        LODWORD(SRWLock) = a3;
        v28 = (__int64 *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v11,
          (__int64)&byte_18001592F,
          v13 + 8,
          v11,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v21,
          &v36,
          (__int64)&v25,
          &v35,
          (__int64)&v24,
          &v34,
          (__int64)&v23,
          &v33,
          (__int64)&v22,
          &v32,
          &v31,
          (__int64)&v38,
          &v30,
          &v29,
          &v28,
          (__int64)&SRWLock);
      }
    }
  }
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v14 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    v15 = ServiceHostLogging::Provider();
    v16 = (__int64)v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *((_QWORD *)v15 + 3);
      if ( (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        LODWORD(SRWLock) = a3;
        v27 = (__int64)a2;
        CurrentThreadId = GetCurrentThreadId();
        v19 = *((_QWORD *)this + 34);
        v38 = CurrentThreadId;
        v21 = *(_DWORD *)(v19 + 72);
        v26 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v16,
          (__int64)byte_1800158C9,
          v19 + 8,
          v20,
          (__int64)&v26,
          (__int64)&v21,
          (__int64)&v38,
          (__int64 **)&v27,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000f628  mov     [rsp-8+arg_8], rbx
0x18000f62d  mov     [rsp-8+arg_10], rsi
0x18000f632  push    rbp
0x18000f633  push    rdi
0x18000f634  push    r14
0x18000f636  lea     rbp, [rsp+10h]
0x18000f63b  sub     rsp, 120h
0x18000f642  mov     rdi, [rcx+110h]
0x18000f649  mov     esi, r8d
0x18000f64c  mov     r14, rdx
0x18000f64f  mov     rbx, rcx
0x18000f652  mov     eax, [rdi+48h]
0x18000f655  test    eax, eax
0x18000f657  jns     loc_18000F822
0x18000f65d  add     rdi, 50h ; 'P'
0x18000f661  cmp     eax, [rdi+8]
0x18000f664  jnz     loc_18000F822
0x18000f66a  test    rdi, rdi
0x18000f66d  jz      loc_18000F822
0x18000f673  lea     rdx, [rbp+SRWLock]
0x18000f677  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f67c  mov     rax, [rbx+110h]
0x18000f683  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000f687  mov     dword ptr [rax], 2
0x18000f68d  test    rcx, rcx
0x18000f690  jz      short loc_18000F698
0x18000f692  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f698  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f69d  mov     r9, rax
0x18000f6a0  mov     ecx, [rax]
0x18000f6a2  cmp     ecx, 5
0x18000f6a5  jbe     loc_18000F8E3
0x18000f6ab  mov     rax, [rax+18h]
0x18000f6af  mov     rdx, 400000000000h
0x18000f6b9  mov     rcx, [r9+10h]
0x18000f6bd  test    rdx, rcx
0x18000f6c0  jz      loc_18000F8E3
0x18000f6c6  mov     rcx, rax
0x18000f6c9  and     rcx, rdx
0x18000f6cc  cmp     rcx, rax
0x18000f6cf  jnz     loc_18000F8E3
0x18000f6d5  mov     rax, [rdi+78h]
0x18000f6d9  lea     rdx, byte_18001592F
0x18000f6e0  mov     [rbp+var_50], rax
0x18000f6e4  mov     rcx, r9
0x18000f6e7  mov     rax, [rdi+70h]
0x18000f6eb  mov     [rbp+var_48], rax
0x18000f6ef  mov     eax, [rdi+68h]
0x18000f6f2  mov     r8, [rbx+110h]
0x18000f6f9  mov     [rbp+arg_18], eax
0x18000f6fc  add     r8, 8
0x18000f700  mov     rax, [rdi+60h]
0x18000f704  mov     [rbp+var_40], rax
0x18000f708  mov     rax, [rdi+58h]
0x18000f70c  mov     [rbp+var_38], rax
0x18000f710  mov     eax, [rdi+50h]
0x18000f713  mov     [rbp+var_7C], eax
0x18000f716  mov     rax, [rdi+48h]
0x18000f71a  mov     [rbp+var_30], rax
0x18000f71e  mov     eax, [rdi+20h]
0x18000f721  mov     [rbp+var_78], eax
0x18000f724  mov     rax, [rdi+18h]
0x18000f728  mov     [rbp+var_28], rax
0x18000f72c  mov     eax, [rdi]
0x18000f72e  mov     [rbp+var_74], eax
0x18000f731  mov     rax, [rdi+80h]
0x18000f738  mov     [rbp+var_20], rax
0x18000f73c  mov     eax, [rdi+40h]
0x18000f73f  mov     [rbp+var_70], eax
0x18000f742  mov     rax, [rdi+38h]
0x18000f746  mov     [rbp+var_18], rax
0x18000f74a  mov     eax, [rdi+8]
0x18000f74d  mov     [rbp+var_80], eax
0x18000f750  mov     eax, 1000000h
0x18000f755  mov     [rbp+var_68], rax
0x18000f759  mov     [rbp+var_60], rax
0x18000f75d  lea     rax, [rbp+SRWLock]
0x18000f761  mov     [rsp+130h+var_88], rax
0x18000f769  lea     rax, [rbp+var_58]
0x18000f76d  mov     [rsp+130h+var_90], rax
0x18000f775  lea     rax, [rbp+var_50]
0x18000f779  mov     [rsp+130h+var_98], rax
0x18000f781  lea     rax, [rbp+var_48]
0x18000f785  mov     [rsp+130h+var_A0], rax
0x18000f78d  lea     rax, [rbp+arg_18]
0x18000f791  mov     [rsp+130h+var_A8], rax
0x18000f799  lea     rax, [rbp+var_40]
0x18000f79d  mov     [rsp+130h+var_B0], rax
0x18000f7a5  lea     rax, [rbp+var_38]
0x18000f7a9  mov     [rsp+130h+var_B8], rax
0x18000f7ae  lea     rax, [rbp+var_7C]
0x18000f7b2  mov     [rsp+130h+var_C0], rax
0x18000f7b7  lea     rax, [rbp+var_30]
0x18000f7bb  mov     [rsp+130h+var_C8], rax
0x18000f7c0  lea     rax, [rbp+var_78]
0x18000f7c4  mov     [rsp+130h+var_D0], rax
0x18000f7c9  lea     rax, [rbp+var_28]
0x18000f7cd  mov     [rsp+130h+var_D8], rax
0x18000f7d2  lea     rax, [rbp+var_74]
0x18000f7d6  mov     [rsp+130h+var_E0], rax
0x18000f7db  lea     rax, [rbp+var_20]
0x18000f7df  mov     [rsp+130h+var_E8], rax
0x18000f7e4  lea     rax, [rbp+var_70]
0x18000f7e8  mov     [rsp+130h+var_F0], rax
0x18000f7ed  lea     rax, [rbp+var_18]
0x18000f7f1  mov     [rsp+130h+var_F8], rax
0x18000f7f6  lea     rax, [rbp+var_80]
0x18000f7fa  mov     [rsp+130h+var_100], rax
0x18000f7ff  lea     rax, [rbp+var_68]
0x18000f803  mov     [rsp+130h+var_108], rax
0x18000f808  lea     rax, [rbp+var_60]
0x18000f80c  mov     [rsp+130h+var_110], rax
0x18000f811  mov     dword ptr [rbp+SRWLock], esi
0x18000f814  mov     [rbp+var_58], r14
0x18000f818  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f81d  jmp     loc_18000F8E3
0x18000f822  lea     rdx, [rbp+SRWLock]
0x18000f826  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f82b  mov     rax, [rbx+110h]
0x18000f832  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000f836  mov     dword ptr [rax], 2
0x18000f83c  test    rcx, rcx
0x18000f83f  jz      short loc_18000F847
0x18000f841  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f847  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f84c  mov     rdi, rax
0x18000f84f  mov     ecx, [rax]
0x18000f851  cmp     ecx, 5
0x18000f854  jbe     loc_18000F8E3
0x18000f85a  mov     rax, [rax+18h]
0x18000f85e  mov     rdx, 400000000000h
0x18000f868  mov     rcx, [rdi+10h]
0x18000f86c  test    rdx, rcx
0x18000f86f  jz      short loc_18000F8E3
0x18000f871  mov     rcx, rax
0x18000f874  and     rcx, rdx
0x18000f877  cmp     rcx, rax
0x18000f87a  jnz     short loc_18000F8E3
0x18000f87c  mov     dword ptr [rbp+SRWLock], esi
0x18000f87f  mov     [rbp+var_60], r14
0x18000f883  call    cs:__imp_GetCurrentThreadId
0x18000f889  mov     r8, [rbx+110h]
0x18000f890  lea     rdx, byte_1800158C9
0x18000f897  mov     [rbp+arg_18], eax
0x18000f89a  mov     rcx, rdi
0x18000f89d  mov     eax, [r8+48h]
0x18000f8a1  add     r8, 8
0x18000f8a5  mov     [rbp+var_80], eax
0x18000f8a8  mov     eax, 1000000h
0x18000f8ad  mov     [rbp+var_68], rax
0x18000f8b1  lea     rax, [rbp+SRWLock]
0x18000f8b5  mov     [rsp+130h+var_F0], rax
0x18000f8ba  lea     rax, [rbp+var_60]
0x18000f8be  mov     [rsp+130h+var_F8], rax
0x18000f8c3  lea     rax, [rbp+arg_18]
0x18000f8c7  mov     [rsp+130h+var_100], rax
0x18000f8cc  lea     rax, [rbp+var_80]
0x18000f8d0  mov     [rsp+130h+var_108], rax
0x18000f8d5  lea     rax, [rbp+var_68]
0x18000f8d9  mov     [rsp+130h+var_110], rax
0x18000f8de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f8e3  mov     rcx, rbx
0x18000f8e6  lea     r11, [rsp+130h+var_10]
0x18000f8ee  mov     rbx, [r11+28h]
0x18000f8f2  mov     rsi, [r11+30h]
0x18000f8f6  mov     rsp, r11
0x18000f8f9  pop     r14
0x18000f8fb  pop     rdi
0x18000f8fc  pop     rbp
0x18000f8fd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
