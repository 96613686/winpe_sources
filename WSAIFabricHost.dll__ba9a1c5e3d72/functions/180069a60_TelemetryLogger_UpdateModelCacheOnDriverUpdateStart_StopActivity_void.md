# TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::StopActivity(void)

- ea: `0x180069a60`
- end: `0x180069ce4`
- name: `?StopActivity@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180069a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069c4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069c4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069c84`

## pseudocode

```c
void __fastcall TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::StopActivity(
        TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *this)
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
        (__int64)byte_18009CB2B,
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
        (__int64)&byte_18009CAC7,
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
0x180069a60  push    rbp
0x180069a62  push    rbx
0x180069a63  push    rdi
0x180069a64  lea     rbp, [rsp-47h]
0x180069a69  sub     rsp, 100h
0x180069a70  mov     rdi, [rcx+110h]
0x180069a77  mov     rbx, rcx
0x180069a7a  mov     eax, [rdi+48h]
0x180069a7d  test    eax, eax
0x180069a7f  jns     loc_180069C2D
0x180069a85  add     rdi, 50h ; 'P'
0x180069a89  cmp     eax, [rdi+8]
0x180069a8c  jnz     loc_180069C2D
0x180069a92  test    rdi, rdi
0x180069a95  jz      loc_180069C2D
0x180069a9b  lea     rdx, [rbp+57h+SRWLock]
0x180069a9f  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069aa4  mov     rax, [rbx+110h]
0x180069aab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180069aaf  mov     dword ptr [rax], 2
0x180069ab5  test    rcx, rcx
0x180069ab8  jz      short loc_180069AC0
0x180069aba  call    cs:__imp_ReleaseSRWLockExclusive
0x180069ac0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069ac5  mov     r9, [rax+8]
0x180069ac9  mov     eax, [r9]
0x180069acc  cmp     eax, 5
0x180069acf  jbe     loc_180069CD2
0x180069ad5  mov     rdx, [r9+18h]
0x180069ad9  mov     rcx, 400000000000h
0x180069ae3  mov     rax, [r9+10h]
0x180069ae7  test    rcx, rax
0x180069aea  jz      loc_180069CD2
0x180069af0  mov     rax, rdx
0x180069af3  and     rax, rcx
0x180069af6  cmp     rax, rdx
0x180069af9  jnz     loc_180069CD2
0x180069aff  mov     rax, [rdi+78h]
0x180069b03  lea     rdx, byte_18009CB2B
0x180069b0a  mov     r8, [rbx+110h]
0x180069b11  mov     rcx, r9
0x180069b14  mov     [rbp+57h+var_68], rax
0x180069b18  add     r8, 8
0x180069b1c  mov     rax, [rdi+70h]
0x180069b20  mov     [rbp+57h+var_60], rax
0x180069b24  mov     eax, [rdi+68h]
0x180069b27  mov     dword ptr [rbp+57h+SRWLock], eax
0x180069b2a  mov     rax, [rdi+60h]
0x180069b2e  mov     [rbp+57h+var_58], rax
0x180069b32  mov     rax, [rdi+58h]
0x180069b36  mov     [rbp+57h+var_50], rax
0x180069b3a  mov     eax, [rdi+50h]
0x180069b3d  mov     [rbp+57h+arg_8], eax
0x180069b40  mov     rax, [rdi+48h]
0x180069b44  mov     [rbp+57h+var_48], rax
0x180069b48  mov     eax, [rdi+20h]
0x180069b4b  mov     dword ptr [rbp+57h+arg_10], eax
0x180069b4e  mov     rax, [rdi+18h]
0x180069b52  mov     [rbp+57h+var_40], rax
0x180069b56  mov     eax, [rdi]
0x180069b58  mov     [rbp+57h+arg_18], eax
0x180069b5b  mov     rax, [rdi+80h]
0x180069b62  mov     [rbp+57h+var_38], rax
0x180069b66  mov     eax, [rdi+40h]
0x180069b69  mov     [rbp+57h+var_70], eax
0x180069b6c  mov     rax, [rdi+38h]
0x180069b70  mov     [rbp+57h+var_30], rax
0x180069b74  mov     eax, [rdi+8]
0x180069b77  mov     [rbp+57h+var_6C], eax
0x180069b7a  mov     eax, 1000000h
0x180069b7f  mov     [rbp+57h+var_28], rax
0x180069b83  mov     [rbp+57h+var_20], rax
0x180069b87  lea     rax, [rbp+57h+var_68]
0x180069b8b  mov     [rsp+110h+var_78], rax
0x180069b93  lea     rax, [rbp+57h+var_60]
0x180069b97  mov     [rsp+110h+var_80], rax
0x180069b9f  lea     rax, [rbp+57h+SRWLock]
0x180069ba3  mov     [rsp+110h+var_88], rax
0x180069bab  lea     rax, [rbp+57h+var_58]
0x180069baf  mov     [rsp+110h+var_90], rax
0x180069bb7  lea     rax, [rbp+57h+var_50]
0x180069bbb  mov     [rsp+110h+var_98], rax
0x180069bc0  lea     rax, [rbp+57h+arg_8]
0x180069bc4  mov     [rsp+110h+var_A0], rax
0x180069bc9  lea     rax, [rbp+57h+var_48]
0x180069bcd  mov     [rsp+110h+var_A8], rax
0x180069bd2  lea     rax, [rbp+57h+arg_10]
0x180069bd6  mov     [rsp+110h+var_B0], rax
0x180069bdb  lea     rax, [rbp+57h+var_40]
0x180069bdf  mov     [rsp+110h+var_B8], rax
0x180069be4  lea     rax, [rbp+57h+arg_18]
0x180069be8  mov     [rsp+110h+var_C0], rax
0x180069bed  lea     rax, [rbp+57h+var_38]
0x180069bf1  mov     [rsp+110h+var_C8], rax
0x180069bf6  lea     rax, [rbp+57h+var_70]
0x180069bfa  mov     [rsp+110h+var_D0], rax
0x180069bff  lea     rax, [rbp+57h+var_30]
0x180069c03  mov     [rsp+110h+var_D8], rax
0x180069c08  lea     rax, [rbp+57h+var_6C]
0x180069c0c  mov     [rsp+110h+var_E0], rax
0x180069c11  lea     rax, [rbp+57h+var_28]
0x180069c15  mov     [rsp+110h+var_E8], rax
0x180069c1a  lea     rax, [rbp+57h+var_20]
0x180069c1e  mov     [rsp+110h+var_F0], rax
0x180069c23  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180069c28  jmp     loc_180069CD2
0x180069c2d  lea     rdx, [rbp+57h+SRWLock]
0x180069c31  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069c36  mov     rax, [rbx+110h]
0x180069c3d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180069c41  mov     dword ptr [rax], 2
0x180069c47  test    rcx, rcx
0x180069c4a  jz      short loc_180069C52
0x180069c4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180069c52  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069c57  mov     rdi, [rax+8]
0x180069c5b  mov     eax, [rdi]
0x180069c5d  cmp     eax, 5
0x180069c60  jbe     short loc_180069CD2
0x180069c62  mov     rdx, [rdi+18h]
0x180069c66  mov     rcx, 400000000000h
0x180069c70  mov     rax, [rdi+10h]
0x180069c74  test    rcx, rax
0x180069c77  jz      short loc_180069CD2
0x180069c79  mov     rax, rdx
0x180069c7c  and     rax, rcx
0x180069c7f  cmp     rax, rdx
0x180069c82  jnz     short loc_180069CD2
0x180069c84  call    cs:__imp_GetCurrentThreadId
0x180069c8a  mov     r8, [rbx+110h]
0x180069c91  lea     rdx, byte_18009CAC7
0x180069c98  mov     dword ptr [rbp+57h+SRWLock], eax
0x180069c9b  mov     rcx, rdi
0x180069c9e  mov     eax, [r8+48h]
0x180069ca2  add     r8, 8
0x180069ca6  mov     [rbp+57h+arg_8], eax
0x180069ca9  mov     eax, 1000000h
0x180069cae  mov     [rbp+57h+arg_10], rax
0x180069cb2  lea     rax, [rbp+57h+SRWLock]
0x180069cb6  mov     [rsp+110h+var_E0], rax
0x180069cbb  lea     rax, [rbp+57h+arg_8]
0x180069cbf  mov     [rsp+110h+var_E8], rax
0x180069cc4  lea     rax, [rbp+57h+arg_10]
0x180069cc8  mov     [rsp+110h+var_F0], rax
0x180069ccd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069cd2  mov     rcx, rbx
0x180069cd5  add     rsp, 100h
0x180069cdc  pop     rdi
0x180069cdd  pop     rbx
0x180069cde  pop     rbp
0x180069cdf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
