# LanguageOverlayTraceProvider::LanguagePackInstallationRequest::StopActivity(void)

- ea: `0x180030420`
- end: `0x1800306b3`
- name: `?StopActivity@LanguagePackInstallationRequest@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::LanguagePackInstallationRequest *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180030420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003047a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003060f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003047a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003060f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030647`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::LanguagePackInstallationRequest::StopActivity(
        LanguageOverlayTraceProvider::LanguagePackInstallationRequest *this)
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
        (__int64)byte_1800779F9,
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
        (__int64)byte_180077999,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::LanguagePackInstallationRequest *)((char *)this + 288));
}

```

## disassembly

```asm
0x180030420  push    rbp
0x180030422  push    rbx
0x180030423  push    rdi
0x180030424  lea     rbp, [rsp-47h]
0x180030429  sub     rsp, 100h
0x180030430  mov     rbx, rcx
0x180030433  mov     rdi, [rcx+110h]
0x18003043a  mov     eax, [rdi+48h]
0x18003043d  test    eax, eax
0x18003043f  jns     loc_1800305F0
0x180030445  add     rdi, 50h ; 'P'
0x180030449  cmp     eax, [rdi+8]
0x18003044c  jnz     loc_1800305F0
0x180030452  test    rdi, rdi
0x180030455  jz      loc_1800305F0
0x18003045b  lea     rdx, [rbp+57h+SRWLock]
0x18003045f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180030464  mov     rax, [rbx+110h]
0x18003046b  mov     dword ptr [rax], 2
0x180030471  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180030475  test    rcx, rcx
0x180030478  jz      short loc_180030480
0x18003047a  call    cs:__imp_ReleaseSRWLockExclusive
0x180030480  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180030485  mov     r9, [rax+8]
0x180030489  mov     eax, [r9]
0x18003048c  cmp     eax, 5
0x18003048f  jbe     loc_180030695
0x180030495  mov     rdx, [r9+18h]
0x180030499  mov     rax, [r9+10h]
0x18003049d  mov     rcx, 400000000000h
0x1800304a7  test    rcx, rax
0x1800304aa  jz      loc_180030695
0x1800304b0  mov     rax, rdx
0x1800304b3  and     rax, rcx
0x1800304b6  cmp     rax, rdx
0x1800304b9  jnz     loc_180030695
0x1800304bf  mov     rax, [rdi+78h]
0x1800304c3  mov     [rbp+57h+var_68], rax
0x1800304c7  mov     rax, [rdi+70h]
0x1800304cb  mov     [rbp+57h+var_60], rax
0x1800304cf  mov     eax, [rdi+68h]
0x1800304d2  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800304d5  mov     rax, [rdi+60h]
0x1800304d9  mov     [rbp+57h+var_58], rax
0x1800304dd  mov     rax, [rdi+58h]
0x1800304e1  mov     [rbp+57h+var_50], rax
0x1800304e5  mov     eax, [rdi+50h]
0x1800304e8  mov     [rbp+57h+arg_8], eax
0x1800304eb  mov     rax, [rdi+48h]
0x1800304ef  mov     [rbp+57h+var_48], rax
0x1800304f3  mov     eax, [rdi+20h]
0x1800304f6  mov     dword ptr [rbp+57h+arg_10], eax
0x1800304f9  mov     rax, [rdi+18h]
0x1800304fd  mov     [rbp+57h+var_40], rax
0x180030501  mov     eax, [rdi]
0x180030503  mov     [rbp+57h+arg_18], eax
0x180030506  mov     rax, [rdi+80h]
0x18003050d  mov     [rbp+57h+var_38], rax
0x180030511  mov     eax, [rdi+40h]
0x180030514  mov     [rbp+57h+var_70], eax
0x180030517  mov     rax, [rdi+38h]
0x18003051b  mov     [rbp+57h+var_30], rax
0x18003051f  mov     eax, [rdi+8]
0x180030522  mov     [rbp+57h+var_6C], eax
0x180030525  mov     [rbp+57h+var_28], 1000000h
0x18003052d  mov     [rbp+57h+var_20], 3000000h
0x180030535  mov     r8, [rbx+110h]
0x18003053c  add     r8, 8
0x180030540  lea     rax, [rbp+57h+var_68]
0x180030544  mov     [rsp+110h+var_78], rax
0x18003054c  lea     rax, [rbp+57h+var_60]
0x180030550  mov     [rsp+110h+var_80], rax
0x180030558  lea     rax, [rbp+57h+SRWLock]
0x18003055c  mov     [rsp+110h+var_88], rax
0x180030564  lea     rax, [rbp+57h+var_58]
0x180030568  mov     [rsp+110h+var_90], rax
0x180030570  lea     rax, [rbp+57h+var_50]
0x180030574  mov     [rsp+110h+var_98], rax
0x180030579  lea     rax, [rbp+57h+arg_8]
0x18003057d  mov     [rsp+110h+var_A0], rax
0x180030582  lea     rax, [rbp+57h+var_48]
0x180030586  mov     [rsp+110h+var_A8], rax
0x18003058b  lea     rax, [rbp+57h+arg_10]
0x18003058f  mov     [rsp+110h+var_B0], rax
0x180030594  lea     rax, [rbp+57h+var_40]
0x180030598  mov     [rsp+110h+var_B8], rax
0x18003059d  lea     rax, [rbp+57h+arg_18]
0x1800305a1  mov     [rsp+110h+var_C0], rax
0x1800305a6  lea     rax, [rbp+57h+var_38]
0x1800305aa  mov     [rsp+110h+var_C8], rax
0x1800305af  lea     rax, [rbp+57h+var_70]
0x1800305b3  mov     [rsp+110h+var_D0], rax
0x1800305b8  lea     rax, [rbp+57h+var_30]
0x1800305bc  mov     [rsp+110h+var_D8], rax
0x1800305c1  lea     rax, [rbp+57h+var_6C]
0x1800305c5  mov     [rsp+110h+var_E0], rax
0x1800305ca  lea     rax, [rbp+57h+var_28]
0x1800305ce  mov     [rsp+110h+var_E8], rax
0x1800305d3  lea     rax, [rbp+57h+var_20]
0x1800305d7  mov     [rsp+110h+var_F0], rax
0x1800305dc  lea     rdx, byte_1800779F9
0x1800305e3  mov     rcx, r9
0x1800305e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800305eb  jmp     loc_180030695
0x1800305f0  lea     rdx, [rbp+57h+SRWLock]
0x1800305f4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800305f9  mov     rax, [rbx+110h]
0x180030600  mov     dword ptr [rax], 2
0x180030606  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003060a  test    rcx, rcx
0x18003060d  jz      short loc_180030615
0x18003060f  call    cs:__imp_ReleaseSRWLockExclusive
0x180030615  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003061a  mov     rdi, [rax+8]
0x18003061e  mov     eax, [rdi]
0x180030620  cmp     eax, 5
0x180030623  jbe     short loc_180030695
0x180030625  mov     rdx, [rdi+18h]
0x180030629  mov     rax, [rdi+10h]
0x18003062d  mov     rcx, 400000000000h
0x180030637  test    rcx, rax
0x18003063a  jz      short loc_180030695
0x18003063c  mov     rax, rdx
0x18003063f  and     rax, rcx
0x180030642  cmp     rax, rdx
0x180030645  jnz     short loc_180030695
0x180030647  call    cs:__imp_GetCurrentThreadId
0x18003064d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180030650  mov     r8, [rbx+110h]
0x180030657  mov     eax, [r8+48h]
0x18003065b  mov     [rbp+57h+arg_8], eax
0x18003065e  mov     [rbp+57h+arg_10], 3000000h
0x180030666  add     r8, 8
0x18003066a  lea     rax, [rbp+57h+SRWLock]
0x18003066e  mov     [rsp+110h+var_E0], rax
0x180030673  lea     rax, [rbp+57h+arg_8]
0x180030677  mov     [rsp+110h+var_E8], rax
0x18003067c  lea     rax, [rbp+57h+arg_10]
0x180030680  mov     [rsp+110h+var_F0], rax
0x180030685  lea     rdx, byte_180077999
0x18003068c  mov     rcx, rdi
0x18003068f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030694  nop
0x180030695  lea     rcx, [rbx+120h]; this
0x18003069c  cmp     dword ptr [rcx+18h], 0
0x1800306a0  jz      short loc_1800306A8
0x1800306a2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800306a7  nop
0x1800306a8  add     rsp, 100h
0x1800306af  pop     rdi
0x1800306b0  pop     rbx
0x1800306b1  pop     rbp
0x1800306b2  retn
```
