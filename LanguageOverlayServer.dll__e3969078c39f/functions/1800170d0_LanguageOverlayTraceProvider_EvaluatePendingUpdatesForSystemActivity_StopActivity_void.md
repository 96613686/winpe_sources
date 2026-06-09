# LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity::StopActivity(void)

- ea: `0x1800170d0`
- end: `0x180017363`
- name: `?StopActivity@EvaluatePendingUpdatesForSystemActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x1800170d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001712a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001712a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172f7`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity::StopActivity(
        LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *this)
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
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
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
        (__int64)word_18007716A,
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
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)word_180077102,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800170d0  push    rbp
0x1800170d2  push    rbx
0x1800170d3  push    rdi
0x1800170d4  lea     rbp, [rsp-47h]
0x1800170d9  sub     rsp, 100h
0x1800170e0  mov     rbx, rcx
0x1800170e3  mov     rdi, [rcx+110h]
0x1800170ea  mov     eax, [rdi+48h]
0x1800170ed  test    eax, eax
0x1800170ef  jns     loc_1800172A0
0x1800170f5  add     rdi, 50h ; 'P'
0x1800170f9  cmp     eax, [rdi+8]
0x1800170fc  jnz     loc_1800172A0
0x180017102  test    rdi, rdi
0x180017105  jz      loc_1800172A0
0x18001710b  lea     rdx, [rbp+57h+SRWLock]
0x18001710f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017114  mov     rax, [rbx+110h]
0x18001711b  mov     dword ptr [rax], 2
0x180017121  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180017125  test    rcx, rcx
0x180017128  jz      short loc_180017130
0x18001712a  call    cs:__imp_ReleaseSRWLockExclusive
0x180017130  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180017135  mov     r9, [rax+8]
0x180017139  mov     eax, [r9]
0x18001713c  cmp     eax, 5
0x18001713f  jbe     loc_180017345
0x180017145  mov     rdx, [r9+18h]
0x180017149  mov     rax, [r9+10h]
0x18001714d  mov     rcx, 200000000000h
0x180017157  test    rcx, rax
0x18001715a  jz      loc_180017345
0x180017160  mov     rax, rdx
0x180017163  and     rax, rcx
0x180017166  cmp     rax, rdx
0x180017169  jnz     loc_180017345
0x18001716f  mov     rax, [rdi+78h]
0x180017173  mov     [rbp+57h+var_68], rax
0x180017177  mov     rax, [rdi+70h]
0x18001717b  mov     [rbp+57h+var_60], rax
0x18001717f  mov     eax, [rdi+68h]
0x180017182  mov     dword ptr [rbp+57h+SRWLock], eax
0x180017185  mov     rax, [rdi+60h]
0x180017189  mov     [rbp+57h+var_58], rax
0x18001718d  mov     rax, [rdi+58h]
0x180017191  mov     [rbp+57h+var_50], rax
0x180017195  mov     eax, [rdi+50h]
0x180017198  mov     [rbp+57h+arg_8], eax
0x18001719b  mov     rax, [rdi+48h]
0x18001719f  mov     [rbp+57h+var_48], rax
0x1800171a3  mov     eax, [rdi+20h]
0x1800171a6  mov     dword ptr [rbp+57h+arg_10], eax
0x1800171a9  mov     rax, [rdi+18h]
0x1800171ad  mov     [rbp+57h+var_40], rax
0x1800171b1  mov     eax, [rdi]
0x1800171b3  mov     [rbp+57h+arg_18], eax
0x1800171b6  mov     rax, [rdi+80h]
0x1800171bd  mov     [rbp+57h+var_38], rax
0x1800171c1  mov     eax, [rdi+40h]
0x1800171c4  mov     [rbp+57h+var_70], eax
0x1800171c7  mov     rax, [rdi+38h]
0x1800171cb  mov     [rbp+57h+var_30], rax
0x1800171cf  mov     eax, [rdi+8]
0x1800171d2  mov     [rbp+57h+var_6C], eax
0x1800171d5  mov     [rbp+57h+var_28], 1000000h
0x1800171dd  mov     [rbp+57h+var_20], 3000000h
0x1800171e5  mov     r8, [rbx+110h]
0x1800171ec  add     r8, 8
0x1800171f0  lea     rax, [rbp+57h+var_68]
0x1800171f4  mov     [rsp+110h+var_78], rax
0x1800171fc  lea     rax, [rbp+57h+var_60]
0x180017200  mov     [rsp+110h+var_80], rax
0x180017208  lea     rax, [rbp+57h+SRWLock]
0x18001720c  mov     [rsp+110h+var_88], rax
0x180017214  lea     rax, [rbp+57h+var_58]
0x180017218  mov     [rsp+110h+var_90], rax
0x180017220  lea     rax, [rbp+57h+var_50]
0x180017224  mov     [rsp+110h+var_98], rax
0x180017229  lea     rax, [rbp+57h+arg_8]
0x18001722d  mov     [rsp+110h+var_A0], rax
0x180017232  lea     rax, [rbp+57h+var_48]
0x180017236  mov     [rsp+110h+var_A8], rax
0x18001723b  lea     rax, [rbp+57h+arg_10]
0x18001723f  mov     [rsp+110h+var_B0], rax
0x180017244  lea     rax, [rbp+57h+var_40]
0x180017248  mov     [rsp+110h+var_B8], rax
0x18001724d  lea     rax, [rbp+57h+arg_18]
0x180017251  mov     [rsp+110h+var_C0], rax
0x180017256  lea     rax, [rbp+57h+var_38]
0x18001725a  mov     [rsp+110h+var_C8], rax
0x18001725f  lea     rax, [rbp+57h+var_70]
0x180017263  mov     [rsp+110h+var_D0], rax
0x180017268  lea     rax, [rbp+57h+var_30]
0x18001726c  mov     [rsp+110h+var_D8], rax
0x180017271  lea     rax, [rbp+57h+var_6C]
0x180017275  mov     [rsp+110h+var_E0], rax
0x18001727a  lea     rax, [rbp+57h+var_28]
0x18001727e  mov     [rsp+110h+var_E8], rax
0x180017283  lea     rax, [rbp+57h+var_20]
0x180017287  mov     [rsp+110h+var_F0], rax
0x18001728c  lea     rdx, word_18007716A
0x180017293  mov     rcx, r9
0x180017296  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001729b  jmp     loc_180017345
0x1800172a0  lea     rdx, [rbp+57h+SRWLock]
0x1800172a4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800172a9  mov     rax, [rbx+110h]
0x1800172b0  mov     dword ptr [rax], 2
0x1800172b6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800172ba  test    rcx, rcx
0x1800172bd  jz      short loc_1800172C5
0x1800172bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800172c5  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800172ca  mov     rdi, [rax+8]
0x1800172ce  mov     eax, [rdi]
0x1800172d0  cmp     eax, 5
0x1800172d3  jbe     short loc_180017345
0x1800172d5  mov     rdx, [rdi+18h]
0x1800172d9  mov     rax, [rdi+10h]
0x1800172dd  mov     rcx, 200000000000h
0x1800172e7  test    rcx, rax
0x1800172ea  jz      short loc_180017345
0x1800172ec  mov     rax, rdx
0x1800172ef  and     rax, rcx
0x1800172f2  cmp     rax, rdx
0x1800172f5  jnz     short loc_180017345
0x1800172f7  call    cs:__imp_GetCurrentThreadId
0x1800172fd  mov     dword ptr [rbp+57h+SRWLock], eax
0x180017300  mov     r8, [rbx+110h]
0x180017307  mov     eax, [r8+48h]
0x18001730b  mov     [rbp+57h+arg_8], eax
0x18001730e  mov     [rbp+57h+arg_10], 3000000h
0x180017316  add     r8, 8
0x18001731a  lea     rax, [rbp+57h+SRWLock]
0x18001731e  mov     [rsp+110h+var_E0], rax
0x180017323  lea     rax, [rbp+57h+arg_8]
0x180017327  mov     [rsp+110h+var_E8], rax
0x18001732c  lea     rax, [rbp+57h+arg_10]
0x180017330  mov     [rsp+110h+var_F0], rax
0x180017335  lea     rdx, word_180077102
0x18001733c  mov     rcx, rdi
0x18001733f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017344  nop
0x180017345  lea     rcx, [rbx+120h]; this
0x18001734c  cmp     dword ptr [rcx+18h], 0
0x180017350  jz      short loc_180017358
0x180017352  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180017357  nop
0x180017358  add     rsp, 100h
0x18001735f  pop     rdi
0x180017360  pop     rbx
0x180017361  pop     rbp
0x180017362  retn
```
