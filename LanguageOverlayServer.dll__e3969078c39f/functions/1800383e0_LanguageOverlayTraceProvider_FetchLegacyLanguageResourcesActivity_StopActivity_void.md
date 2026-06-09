# LanguageOverlayTraceProvider::FetchLegacyLanguageResourcesActivity::StopActivity(void)

- ea: `0x1800383e0`
- end: `0x180038673`
- name: `?StopActivity@FetchLegacyLanguageResourcesActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::FetchLegacyLanguageResourcesActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x1800383e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003843a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800385cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003843a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800385cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038607`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::FetchLegacyLanguageResourcesActivity::StopActivity(
        LanguageOverlayTraceProvider::FetchLegacyLanguageResourcesActivity *this)
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
  _QWORD v20[4]; // [rsp+F0h] [rbp+37h] BYREF
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
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_180077D19,
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
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&dword_180077CB4,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::FetchLegacyLanguageResourcesActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800383e0  push    rbp
0x1800383e2  push    rbx
0x1800383e3  push    rdi
0x1800383e4  lea     rbp, [rsp-47h]
0x1800383e9  sub     rsp, 100h
0x1800383f0  mov     rbx, rcx
0x1800383f3  mov     rdi, [rcx+110h]
0x1800383fa  mov     eax, [rdi+48h]
0x1800383fd  test    eax, eax
0x1800383ff  jns     loc_1800385B0
0x180038405  add     rdi, 50h ; 'P'
0x180038409  cmp     eax, [rdi+8]
0x18003840c  jnz     loc_1800385B0
0x180038412  test    rdi, rdi
0x180038415  jz      loc_1800385B0
0x18003841b  lea     rdx, [rbp+57h+SRWLock]
0x18003841f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180038424  mov     rax, [rbx+110h]
0x18003842b  mov     dword ptr [rax], 2
0x180038431  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180038435  test    rcx, rcx
0x180038438  jz      short loc_180038440
0x18003843a  call    cs:__imp_ReleaseSRWLockExclusive
0x180038440  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180038445  mov     r9, [rax+8]
0x180038449  mov     eax, [r9]
0x18003844c  cmp     eax, 5
0x18003844f  jbe     loc_180038655
0x180038455  mov     rdx, [r9+18h]
0x180038459  mov     rax, [r9+10h]
0x18003845d  mov     rcx, 200000000000h
0x180038467  test    rcx, rax
0x18003846a  jz      loc_180038655
0x180038470  mov     rax, rdx
0x180038473  and     rax, rcx
0x180038476  cmp     rax, rdx
0x180038479  jnz     loc_180038655
0x18003847f  mov     rax, [rdi+78h]
0x180038483  mov     [rbp+57h+var_68], rax
0x180038487  mov     rax, [rdi+70h]
0x18003848b  mov     [rbp+57h+var_60], rax
0x18003848f  mov     eax, [rdi+68h]
0x180038492  mov     dword ptr [rbp+57h+SRWLock], eax
0x180038495  mov     rax, [rdi+60h]
0x180038499  mov     [rbp+57h+var_58], rax
0x18003849d  mov     rax, [rdi+58h]
0x1800384a1  mov     [rbp+57h+var_50], rax
0x1800384a5  mov     eax, [rdi+50h]
0x1800384a8  mov     [rbp+57h+arg_8], eax
0x1800384ab  mov     rax, [rdi+48h]
0x1800384af  mov     [rbp+57h+var_48], rax
0x1800384b3  mov     eax, [rdi+20h]
0x1800384b6  mov     dword ptr [rbp+57h+arg_10], eax
0x1800384b9  mov     rax, [rdi+18h]
0x1800384bd  mov     [rbp+57h+var_40], rax
0x1800384c1  mov     eax, [rdi]
0x1800384c3  mov     [rbp+57h+arg_18], eax
0x1800384c6  mov     rax, [rdi+80h]
0x1800384cd  mov     [rbp+57h+var_38], rax
0x1800384d1  mov     eax, [rdi+40h]
0x1800384d4  mov     [rbp+57h+var_70], eax
0x1800384d7  mov     rax, [rdi+38h]
0x1800384db  mov     [rbp+57h+var_30], rax
0x1800384df  mov     eax, [rdi+8]
0x1800384e2  mov     [rbp+57h+var_6C], eax
0x1800384e5  mov     [rbp+57h+var_28], 1000000h
0x1800384ed  mov     [rbp+57h+var_20], 0
0x1800384f5  mov     r8, [rbx+110h]
0x1800384fc  add     r8, 8
0x180038500  lea     rax, [rbp+57h+var_68]
0x180038504  mov     [rsp+110h+var_78], rax
0x18003850c  lea     rax, [rbp+57h+var_60]
0x180038510  mov     [rsp+110h+var_80], rax
0x180038518  lea     rax, [rbp+57h+SRWLock]
0x18003851c  mov     [rsp+110h+var_88], rax
0x180038524  lea     rax, [rbp+57h+var_58]
0x180038528  mov     [rsp+110h+var_90], rax
0x180038530  lea     rax, [rbp+57h+var_50]
0x180038534  mov     [rsp+110h+var_98], rax
0x180038539  lea     rax, [rbp+57h+arg_8]
0x18003853d  mov     [rsp+110h+var_A0], rax
0x180038542  lea     rax, [rbp+57h+var_48]
0x180038546  mov     [rsp+110h+var_A8], rax
0x18003854b  lea     rax, [rbp+57h+arg_10]
0x18003854f  mov     [rsp+110h+var_B0], rax
0x180038554  lea     rax, [rbp+57h+var_40]
0x180038558  mov     [rsp+110h+var_B8], rax
0x18003855d  lea     rax, [rbp+57h+arg_18]
0x180038561  mov     [rsp+110h+var_C0], rax
0x180038566  lea     rax, [rbp+57h+var_38]
0x18003856a  mov     [rsp+110h+var_C8], rax
0x18003856f  lea     rax, [rbp+57h+var_70]
0x180038573  mov     [rsp+110h+var_D0], rax
0x180038578  lea     rax, [rbp+57h+var_30]
0x18003857c  mov     [rsp+110h+var_D8], rax
0x180038581  lea     rax, [rbp+57h+var_6C]
0x180038585  mov     [rsp+110h+var_E0], rax
0x18003858a  lea     rax, [rbp+57h+var_28]
0x18003858e  mov     [rsp+110h+var_E8], rax
0x180038593  lea     rax, [rbp+57h+var_20]
0x180038597  mov     [rsp+110h+var_F0], rax
0x18003859c  lea     rdx, byte_180077D19
0x1800385a3  mov     rcx, r9
0x1800385a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800385ab  jmp     loc_180038655
0x1800385b0  lea     rdx, [rbp+57h+SRWLock]
0x1800385b4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800385b9  mov     rax, [rbx+110h]
0x1800385c0  mov     dword ptr [rax], 2
0x1800385c6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800385ca  test    rcx, rcx
0x1800385cd  jz      short loc_1800385D5
0x1800385cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800385d5  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800385da  mov     rdi, [rax+8]
0x1800385de  mov     eax, [rdi]
0x1800385e0  cmp     eax, 5
0x1800385e3  jbe     short loc_180038655
0x1800385e5  mov     rdx, [rdi+18h]
0x1800385e9  mov     rax, [rdi+10h]
0x1800385ed  mov     rcx, 200000000000h
0x1800385f7  test    rcx, rax
0x1800385fa  jz      short loc_180038655
0x1800385fc  mov     rax, rdx
0x1800385ff  and     rax, rcx
0x180038602  cmp     rax, rdx
0x180038605  jnz     short loc_180038655
0x180038607  call    cs:__imp_GetCurrentThreadId
0x18003860d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180038610  mov     r8, [rbx+110h]
0x180038617  mov     eax, [r8+48h]
0x18003861b  mov     [rbp+57h+arg_8], eax
0x18003861e  mov     [rbp+57h+arg_10], 0
0x180038626  add     r8, 8
0x18003862a  lea     rax, [rbp+57h+SRWLock]
0x18003862e  mov     [rsp+110h+var_E0], rax
0x180038633  lea     rax, [rbp+57h+arg_8]
0x180038637  mov     [rsp+110h+var_E8], rax
0x18003863c  lea     rax, [rbp+57h+arg_10]
0x180038640  mov     [rsp+110h+var_F0], rax
0x180038645  lea     rdx, dword_180077CB4
0x18003864c  mov     rcx, rdi
0x18003864f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038654  nop
0x180038655  lea     rcx, [rbx+120h]; this
0x18003865c  cmp     dword ptr [rcx+18h], 0
0x180038660  jz      short loc_180038668
0x180038662  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180038667  nop
0x180038668  add     rsp, 100h
0x18003866f  pop     rdi
0x180038670  pop     rbx
0x180038671  pop     rbp
0x180038672  retn
```
