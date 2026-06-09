# TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels::StopActivity(void)

- ea: `0x1800697d0`
- end: `0x180069a54`
- name: `?StopActivity@UpdateModelCacheOnDriverUpdateCacheModels@TelemetryLogger@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x1800697d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006982a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800699bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006982a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800699bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800699f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800699f4`

## pseudocode

```c
void __fastcall TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels::StopActivity(
        TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels *this)
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
        (__int64)&word_18009C7A6,
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
        (__int64)word_18009C6BA,
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
0x1800697d0  push    rbp
0x1800697d2  push    rbx
0x1800697d3  push    rdi
0x1800697d4  lea     rbp, [rsp-47h]
0x1800697d9  sub     rsp, 100h
0x1800697e0  mov     rdi, [rcx+110h]
0x1800697e7  mov     rbx, rcx
0x1800697ea  mov     eax, [rdi+48h]
0x1800697ed  test    eax, eax
0x1800697ef  jns     loc_18006999D
0x1800697f5  add     rdi, 50h ; 'P'
0x1800697f9  cmp     eax, [rdi+8]
0x1800697fc  jnz     loc_18006999D
0x180069802  test    rdi, rdi
0x180069805  jz      loc_18006999D
0x18006980b  lea     rdx, [rbp+57h+SRWLock]
0x18006980f  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069814  mov     rax, [rbx+110h]
0x18006981b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006981f  mov     dword ptr [rax], 2
0x180069825  test    rcx, rcx
0x180069828  jz      short loc_180069830
0x18006982a  call    cs:__imp_ReleaseSRWLockExclusive
0x180069830  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069835  mov     r9, [rax+8]
0x180069839  mov     eax, [r9]
0x18006983c  cmp     eax, 5
0x18006983f  jbe     loc_180069A42
0x180069845  mov     rdx, [r9+18h]
0x180069849  mov     rcx, 400000000000h
0x180069853  mov     rax, [r9+10h]
0x180069857  test    rcx, rax
0x18006985a  jz      loc_180069A42
0x180069860  mov     rax, rdx
0x180069863  and     rax, rcx
0x180069866  cmp     rax, rdx
0x180069869  jnz     loc_180069A42
0x18006986f  mov     rax, [rdi+78h]
0x180069873  lea     rdx, word_18009C7A6
0x18006987a  mov     r8, [rbx+110h]
0x180069881  mov     rcx, r9
0x180069884  mov     [rbp+57h+var_68], rax
0x180069888  add     r8, 8
0x18006988c  mov     rax, [rdi+70h]
0x180069890  mov     [rbp+57h+var_60], rax
0x180069894  mov     eax, [rdi+68h]
0x180069897  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006989a  mov     rax, [rdi+60h]
0x18006989e  mov     [rbp+57h+var_58], rax
0x1800698a2  mov     rax, [rdi+58h]
0x1800698a6  mov     [rbp+57h+var_50], rax
0x1800698aa  mov     eax, [rdi+50h]
0x1800698ad  mov     [rbp+57h+arg_8], eax
0x1800698b0  mov     rax, [rdi+48h]
0x1800698b4  mov     [rbp+57h+var_48], rax
0x1800698b8  mov     eax, [rdi+20h]
0x1800698bb  mov     dword ptr [rbp+57h+arg_10], eax
0x1800698be  mov     rax, [rdi+18h]
0x1800698c2  mov     [rbp+57h+var_40], rax
0x1800698c6  mov     eax, [rdi]
0x1800698c8  mov     [rbp+57h+arg_18], eax
0x1800698cb  mov     rax, [rdi+80h]
0x1800698d2  mov     [rbp+57h+var_38], rax
0x1800698d6  mov     eax, [rdi+40h]
0x1800698d9  mov     [rbp+57h+var_70], eax
0x1800698dc  mov     rax, [rdi+38h]
0x1800698e0  mov     [rbp+57h+var_30], rax
0x1800698e4  mov     eax, [rdi+8]
0x1800698e7  mov     [rbp+57h+var_6C], eax
0x1800698ea  mov     eax, 1000000h
0x1800698ef  mov     [rbp+57h+var_28], rax
0x1800698f3  mov     [rbp+57h+var_20], rax
0x1800698f7  lea     rax, [rbp+57h+var_68]
0x1800698fb  mov     [rsp+110h+var_78], rax
0x180069903  lea     rax, [rbp+57h+var_60]
0x180069907  mov     [rsp+110h+var_80], rax
0x18006990f  lea     rax, [rbp+57h+SRWLock]
0x180069913  mov     [rsp+110h+var_88], rax
0x18006991b  lea     rax, [rbp+57h+var_58]
0x18006991f  mov     [rsp+110h+var_90], rax
0x180069927  lea     rax, [rbp+57h+var_50]
0x18006992b  mov     [rsp+110h+var_98], rax
0x180069930  lea     rax, [rbp+57h+arg_8]
0x180069934  mov     [rsp+110h+var_A0], rax
0x180069939  lea     rax, [rbp+57h+var_48]
0x18006993d  mov     [rsp+110h+var_A8], rax
0x180069942  lea     rax, [rbp+57h+arg_10]
0x180069946  mov     [rsp+110h+var_B0], rax
0x18006994b  lea     rax, [rbp+57h+var_40]
0x18006994f  mov     [rsp+110h+var_B8], rax
0x180069954  lea     rax, [rbp+57h+arg_18]
0x180069958  mov     [rsp+110h+var_C0], rax
0x18006995d  lea     rax, [rbp+57h+var_38]
0x180069961  mov     [rsp+110h+var_C8], rax
0x180069966  lea     rax, [rbp+57h+var_70]
0x18006996a  mov     [rsp+110h+var_D0], rax
0x18006996f  lea     rax, [rbp+57h+var_30]
0x180069973  mov     [rsp+110h+var_D8], rax
0x180069978  lea     rax, [rbp+57h+var_6C]
0x18006997c  mov     [rsp+110h+var_E0], rax
0x180069981  lea     rax, [rbp+57h+var_28]
0x180069985  mov     [rsp+110h+var_E8], rax
0x18006998a  lea     rax, [rbp+57h+var_20]
0x18006998e  mov     [rsp+110h+var_F0], rax
0x180069993  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180069998  jmp     loc_180069A42
0x18006999d  lea     rdx, [rbp+57h+SRWLock]
0x1800699a1  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800699a6  mov     rax, [rbx+110h]
0x1800699ad  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800699b1  mov     dword ptr [rax], 2
0x1800699b7  test    rcx, rcx
0x1800699ba  jz      short loc_1800699C2
0x1800699bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800699c2  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800699c7  mov     rdi, [rax+8]
0x1800699cb  mov     eax, [rdi]
0x1800699cd  cmp     eax, 5
0x1800699d0  jbe     short loc_180069A42
0x1800699d2  mov     rdx, [rdi+18h]
0x1800699d6  mov     rcx, 400000000000h
0x1800699e0  mov     rax, [rdi+10h]
0x1800699e4  test    rcx, rax
0x1800699e7  jz      short loc_180069A42
0x1800699e9  mov     rax, rdx
0x1800699ec  and     rax, rcx
0x1800699ef  cmp     rax, rdx
0x1800699f2  jnz     short loc_180069A42
0x1800699f4  call    cs:__imp_GetCurrentThreadId
0x1800699fa  mov     r8, [rbx+110h]
0x180069a01  lea     rdx, word_18009C6BA
0x180069a08  mov     dword ptr [rbp+57h+SRWLock], eax
0x180069a0b  mov     rcx, rdi
0x180069a0e  mov     eax, [r8+48h]
0x180069a12  add     r8, 8
0x180069a16  mov     [rbp+57h+arg_8], eax
0x180069a19  mov     eax, 1000000h
0x180069a1e  mov     [rbp+57h+arg_10], rax
0x180069a22  lea     rax, [rbp+57h+SRWLock]
0x180069a26  mov     [rsp+110h+var_E0], rax
0x180069a2b  lea     rax, [rbp+57h+arg_8]
0x180069a2f  mov     [rsp+110h+var_E8], rax
0x180069a34  lea     rax, [rbp+57h+arg_10]
0x180069a38  mov     [rsp+110h+var_F0], rax
0x180069a3d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069a42  mov     rcx, rbx
0x180069a45  add     rsp, 100h
0x180069a4c  pop     rdi
0x180069a4d  pop     rbx
0x180069a4e  pop     rbp
0x180069a4f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
