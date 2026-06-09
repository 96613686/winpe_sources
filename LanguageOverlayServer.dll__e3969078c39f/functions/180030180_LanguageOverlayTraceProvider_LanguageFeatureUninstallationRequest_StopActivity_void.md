# LanguageOverlayTraceProvider::LanguageFeatureUninstallationRequest::StopActivity(void)

- ea: `0x180030180`
- end: `0x180030413`
- name: `?StopActivity@LanguageFeatureUninstallationRequest@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::LanguageFeatureUninstallationRequest *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180030180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800301da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003036f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800301da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003036f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800303a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800303a7`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::LanguageFeatureUninstallationRequest::StopActivity(
        LanguageOverlayTraceProvider::LanguageFeatureUninstallationRequest *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+A0h] [rbp-19h] BYREF
  int v10; // [rsp+A4h] [rbp-15h] BYREF
  const int *v11; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-9h] BYREF
  const int *v13; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+Fh] BYREF
  const int *v16; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v17; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v11 = (const int *)*((_QWORD *)v4 + 15);
      v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v13 = (const int *)*((_QWORD *)v4 + 12);
      v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = (const int *)*((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)&dword_180077584,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v10,
        &v18,
        (__int64)&v9,
        &v17,
        (__int64)&v24,
        &v16,
        (__int64)&v23,
        &v15,
        (__int64)&v22,
        &v14,
        &v13,
        (__int64)&SRWLock,
        &v12,
        &v11);
    }
  }
  else
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&byte_18007751F,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::LanguageFeatureUninstallationRequest *)((char *)this + 288));
}

```

## disassembly

```asm
0x180030180  push    rbp
0x180030182  push    rbx
0x180030183  push    rdi
0x180030184  lea     rbp, [rsp-47h]
0x180030189  sub     rsp, 100h
0x180030190  mov     rbx, rcx
0x180030193  mov     rdi, [rcx+110h]
0x18003019a  mov     eax, [rdi+48h]
0x18003019d  test    eax, eax
0x18003019f  jns     loc_180030350
0x1800301a5  add     rdi, 50h ; 'P'
0x1800301a9  cmp     eax, [rdi+8]
0x1800301ac  jnz     loc_180030350
0x1800301b2  test    rdi, rdi
0x1800301b5  jz      loc_180030350
0x1800301bb  lea     rdx, [rbp+57h+SRWLock]
0x1800301bf  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800301c4  mov     rax, [rbx+110h]
0x1800301cb  mov     dword ptr [rax], 2
0x1800301d1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800301d5  test    rcx, rcx
0x1800301d8  jz      short loc_1800301E0
0x1800301da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800301e0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800301e5  mov     r9, [rax+8]
0x1800301e9  mov     eax, [r9]
0x1800301ec  cmp     eax, 5
0x1800301ef  jbe     loc_1800303F5
0x1800301f5  mov     rdx, [r9+18h]
0x1800301f9  mov     rax, [r9+10h]
0x1800301fd  mov     rcx, 400000000000h
0x180030207  test    rcx, rax
0x18003020a  jz      loc_1800303F5
0x180030210  mov     rax, rdx
0x180030213  and     rax, rcx
0x180030216  cmp     rax, rdx
0x180030219  jnz     loc_1800303F5
0x18003021f  mov     rax, [rdi+78h]
0x180030223  mov     [rbp+57h+var_68], rax
0x180030227  mov     rax, [rdi+70h]
0x18003022b  mov     [rbp+57h+var_60], rax
0x18003022f  mov     eax, [rdi+68h]
0x180030232  mov     dword ptr [rbp+57h+SRWLock], eax
0x180030235  mov     rax, [rdi+60h]
0x180030239  mov     [rbp+57h+var_58], rax
0x18003023d  mov     rax, [rdi+58h]
0x180030241  mov     [rbp+57h+var_50], rax
0x180030245  mov     eax, [rdi+50h]
0x180030248  mov     [rbp+57h+arg_8], eax
0x18003024b  mov     rax, [rdi+48h]
0x18003024f  mov     [rbp+57h+var_48], rax
0x180030253  mov     eax, [rdi+20h]
0x180030256  mov     dword ptr [rbp+57h+arg_10], eax
0x180030259  mov     rax, [rdi+18h]
0x18003025d  mov     [rbp+57h+var_40], rax
0x180030261  mov     eax, [rdi]
0x180030263  mov     [rbp+57h+arg_18], eax
0x180030266  mov     rax, [rdi+80h]
0x18003026d  mov     [rbp+57h+var_38], rax
0x180030271  mov     eax, [rdi+40h]
0x180030274  mov     [rbp+57h+var_70], eax
0x180030277  mov     rax, [rdi+38h]
0x18003027b  mov     [rbp+57h+var_30], rax
0x18003027f  mov     eax, [rdi+8]
0x180030282  mov     [rbp+57h+var_6C], eax
0x180030285  mov     [rbp+57h+var_28], 1000000h
0x18003028d  mov     [rbp+57h+var_20], 3000000h
0x180030295  mov     r8, [rbx+110h]
0x18003029c  add     r8, 8
0x1800302a0  lea     rax, [rbp+57h+var_68]
0x1800302a4  mov     [rsp+110h+var_78], rax
0x1800302ac  lea     rax, [rbp+57h+var_60]
0x1800302b0  mov     [rsp+110h+var_80], rax
0x1800302b8  lea     rax, [rbp+57h+SRWLock]
0x1800302bc  mov     [rsp+110h+var_88], rax
0x1800302c4  lea     rax, [rbp+57h+var_58]
0x1800302c8  mov     [rsp+110h+var_90], rax
0x1800302d0  lea     rax, [rbp+57h+var_50]
0x1800302d4  mov     [rsp+110h+var_98], rax
0x1800302d9  lea     rax, [rbp+57h+arg_8]
0x1800302dd  mov     [rsp+110h+var_A0], rax
0x1800302e2  lea     rax, [rbp+57h+var_48]
0x1800302e6  mov     [rsp+110h+var_A8], rax
0x1800302eb  lea     rax, [rbp+57h+arg_10]
0x1800302ef  mov     [rsp+110h+var_B0], rax
0x1800302f4  lea     rax, [rbp+57h+var_40]
0x1800302f8  mov     [rsp+110h+var_B8], rax
0x1800302fd  lea     rax, [rbp+57h+arg_18]
0x180030301  mov     [rsp+110h+var_C0], rax
0x180030306  lea     rax, [rbp+57h+var_38]
0x18003030a  mov     [rsp+110h+var_C8], rax
0x18003030f  lea     rax, [rbp+57h+var_70]
0x180030313  mov     [rsp+110h+var_D0], rax
0x180030318  lea     rax, [rbp+57h+var_30]
0x18003031c  mov     [rsp+110h+var_D8], rax
0x180030321  lea     rax, [rbp+57h+var_6C]
0x180030325  mov     [rsp+110h+var_E0], rax
0x18003032a  lea     rax, [rbp+57h+var_28]
0x18003032e  mov     [rsp+110h+var_E8], rax
0x180030333  lea     rax, [rbp+57h+var_20]
0x180030337  mov     [rsp+110h+var_F0], rax
0x18003033c  lea     rdx, dword_180077584
0x180030343  mov     rcx, r9
0x180030346  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003034b  jmp     loc_1800303F5
0x180030350  lea     rdx, [rbp+57h+SRWLock]
0x180030354  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180030359  mov     rax, [rbx+110h]
0x180030360  mov     dword ptr [rax], 2
0x180030366  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003036a  test    rcx, rcx
0x18003036d  jz      short loc_180030375
0x18003036f  call    cs:__imp_ReleaseSRWLockExclusive
0x180030375  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003037a  mov     rdi, [rax+8]
0x18003037e  mov     eax, [rdi]
0x180030380  cmp     eax, 5
0x180030383  jbe     short loc_1800303F5
0x180030385  mov     rdx, [rdi+18h]
0x180030389  mov     rax, [rdi+10h]
0x18003038d  mov     rcx, 400000000000h
0x180030397  test    rcx, rax
0x18003039a  jz      short loc_1800303F5
0x18003039c  mov     rax, rdx
0x18003039f  and     rax, rcx
0x1800303a2  cmp     rax, rdx
0x1800303a5  jnz     short loc_1800303F5
0x1800303a7  call    cs:__imp_GetCurrentThreadId
0x1800303ad  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800303b0  mov     r8, [rbx+110h]
0x1800303b7  mov     eax, [r8+48h]
0x1800303bb  mov     [rbp+57h+arg_8], eax
0x1800303be  mov     [rbp+57h+arg_10], 3000000h
0x1800303c6  add     r8, 8
0x1800303ca  lea     rax, [rbp+57h+SRWLock]
0x1800303ce  mov     [rsp+110h+var_E0], rax
0x1800303d3  lea     rax, [rbp+57h+arg_8]
0x1800303d7  mov     [rsp+110h+var_E8], rax
0x1800303dc  lea     rax, [rbp+57h+arg_10]
0x1800303e0  mov     [rsp+110h+var_F0], rax
0x1800303e5  lea     rdx, byte_18007751F
0x1800303ec  mov     rcx, rdi
0x1800303ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800303f4  nop
0x1800303f5  lea     rcx, [rbx+120h]; this
0x1800303fc  cmp     dword ptr [rcx+18h], 0
0x180030400  jz      short loc_180030408
0x180030402  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180030407  nop
0x180030408  add     rsp, 100h
0x18003040f  pop     rdi
0x180030410  pop     rbx
0x180030411  pop     rbp
0x180030412  retn
```
