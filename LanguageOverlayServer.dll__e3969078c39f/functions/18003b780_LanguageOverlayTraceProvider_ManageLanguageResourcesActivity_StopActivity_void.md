# LanguageOverlayTraceProvider::ManageLanguageResourcesActivity::StopActivity(void)

- ea: `0x18003b780`
- end: `0x18003ba13`
- name: `?StopActivity@ManageLanguageResourcesActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::ManageLanguageResourcesActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18003b780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b9a7`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::ManageLanguageResourcesActivity::StopActivity(
        LanguageOverlayTraceProvider::ManageLanguageResourcesActivity *this)
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
        (__int64)&dword_1800782DC,
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
        (__int64)&dword_18007827C,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::ManageLanguageResourcesActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003b780  push    rbp
0x18003b782  push    rbx
0x18003b783  push    rdi
0x18003b784  lea     rbp, [rsp-47h]
0x18003b789  sub     rsp, 100h
0x18003b790  mov     rbx, rcx
0x18003b793  mov     rdi, [rcx+110h]
0x18003b79a  mov     eax, [rdi+48h]
0x18003b79d  test    eax, eax
0x18003b79f  jns     loc_18003B950
0x18003b7a5  add     rdi, 50h ; 'P'
0x18003b7a9  cmp     eax, [rdi+8]
0x18003b7ac  jnz     loc_18003B950
0x18003b7b2  test    rdi, rdi
0x18003b7b5  jz      loc_18003B950
0x18003b7bb  lea     rdx, [rbp+57h+SRWLock]
0x18003b7bf  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b7c4  mov     rax, [rbx+110h]
0x18003b7cb  mov     dword ptr [rax], 2
0x18003b7d1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b7d5  test    rcx, rcx
0x18003b7d8  jz      short loc_18003B7E0
0x18003b7da  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b7e0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003b7e5  mov     r9, [rax+8]
0x18003b7e9  mov     eax, [r9]
0x18003b7ec  cmp     eax, 5
0x18003b7ef  jbe     loc_18003B9F5
0x18003b7f5  mov     rdx, [r9+18h]
0x18003b7f9  mov     rax, [r9+10h]
0x18003b7fd  mov     rcx, 200000000000h
0x18003b807  test    rcx, rax
0x18003b80a  jz      loc_18003B9F5
0x18003b810  mov     rax, rdx
0x18003b813  and     rax, rcx
0x18003b816  cmp     rax, rdx
0x18003b819  jnz     loc_18003B9F5
0x18003b81f  mov     rax, [rdi+78h]
0x18003b823  mov     [rbp+57h+var_68], rax
0x18003b827  mov     rax, [rdi+70h]
0x18003b82b  mov     [rbp+57h+var_60], rax
0x18003b82f  mov     eax, [rdi+68h]
0x18003b832  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b835  mov     rax, [rdi+60h]
0x18003b839  mov     [rbp+57h+var_58], rax
0x18003b83d  mov     rax, [rdi+58h]
0x18003b841  mov     [rbp+57h+var_50], rax
0x18003b845  mov     eax, [rdi+50h]
0x18003b848  mov     [rbp+57h+arg_8], eax
0x18003b84b  mov     rax, [rdi+48h]
0x18003b84f  mov     [rbp+57h+var_48], rax
0x18003b853  mov     eax, [rdi+20h]
0x18003b856  mov     dword ptr [rbp+57h+arg_10], eax
0x18003b859  mov     rax, [rdi+18h]
0x18003b85d  mov     [rbp+57h+var_40], rax
0x18003b861  mov     eax, [rdi]
0x18003b863  mov     [rbp+57h+arg_18], eax
0x18003b866  mov     rax, [rdi+80h]
0x18003b86d  mov     [rbp+57h+var_38], rax
0x18003b871  mov     eax, [rdi+40h]
0x18003b874  mov     [rbp+57h+var_70], eax
0x18003b877  mov     rax, [rdi+38h]
0x18003b87b  mov     [rbp+57h+var_30], rax
0x18003b87f  mov     eax, [rdi+8]
0x18003b882  mov     [rbp+57h+var_6C], eax
0x18003b885  mov     [rbp+57h+var_28], 1000000h
0x18003b88d  mov     [rbp+57h+var_20], 0
0x18003b895  mov     r8, [rbx+110h]
0x18003b89c  add     r8, 8
0x18003b8a0  lea     rax, [rbp+57h+var_68]
0x18003b8a4  mov     [rsp+110h+var_78], rax
0x18003b8ac  lea     rax, [rbp+57h+var_60]
0x18003b8b0  mov     [rsp+110h+var_80], rax
0x18003b8b8  lea     rax, [rbp+57h+SRWLock]
0x18003b8bc  mov     [rsp+110h+var_88], rax
0x18003b8c4  lea     rax, [rbp+57h+var_58]
0x18003b8c8  mov     [rsp+110h+var_90], rax
0x18003b8d0  lea     rax, [rbp+57h+var_50]
0x18003b8d4  mov     [rsp+110h+var_98], rax
0x18003b8d9  lea     rax, [rbp+57h+arg_8]
0x18003b8dd  mov     [rsp+110h+var_A0], rax
0x18003b8e2  lea     rax, [rbp+57h+var_48]
0x18003b8e6  mov     [rsp+110h+var_A8], rax
0x18003b8eb  lea     rax, [rbp+57h+arg_10]
0x18003b8ef  mov     [rsp+110h+var_B0], rax
0x18003b8f4  lea     rax, [rbp+57h+var_40]
0x18003b8f8  mov     [rsp+110h+var_B8], rax
0x18003b8fd  lea     rax, [rbp+57h+arg_18]
0x18003b901  mov     [rsp+110h+var_C0], rax
0x18003b906  lea     rax, [rbp+57h+var_38]
0x18003b90a  mov     [rsp+110h+var_C8], rax
0x18003b90f  lea     rax, [rbp+57h+var_70]
0x18003b913  mov     [rsp+110h+var_D0], rax
0x18003b918  lea     rax, [rbp+57h+var_30]
0x18003b91c  mov     [rsp+110h+var_D8], rax
0x18003b921  lea     rax, [rbp+57h+var_6C]
0x18003b925  mov     [rsp+110h+var_E0], rax
0x18003b92a  lea     rax, [rbp+57h+var_28]
0x18003b92e  mov     [rsp+110h+var_E8], rax
0x18003b933  lea     rax, [rbp+57h+var_20]
0x18003b937  mov     [rsp+110h+var_F0], rax
0x18003b93c  lea     rdx, dword_1800782DC
0x18003b943  mov     rcx, r9
0x18003b946  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003b94b  jmp     loc_18003B9F5
0x18003b950  lea     rdx, [rbp+57h+SRWLock]
0x18003b954  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b959  mov     rax, [rbx+110h]
0x18003b960  mov     dword ptr [rax], 2
0x18003b966  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b96a  test    rcx, rcx
0x18003b96d  jz      short loc_18003B975
0x18003b96f  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b975  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003b97a  mov     rdi, [rax+8]
0x18003b97e  mov     eax, [rdi]
0x18003b980  cmp     eax, 5
0x18003b983  jbe     short loc_18003B9F5
0x18003b985  mov     rdx, [rdi+18h]
0x18003b989  mov     rax, [rdi+10h]
0x18003b98d  mov     rcx, 200000000000h
0x18003b997  test    rcx, rax
0x18003b99a  jz      short loc_18003B9F5
0x18003b99c  mov     rax, rdx
0x18003b99f  and     rax, rcx
0x18003b9a2  cmp     rax, rdx
0x18003b9a5  jnz     short loc_18003B9F5
0x18003b9a7  call    cs:__imp_GetCurrentThreadId
0x18003b9ad  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b9b0  mov     r8, [rbx+110h]
0x18003b9b7  mov     eax, [r8+48h]
0x18003b9bb  mov     [rbp+57h+arg_8], eax
0x18003b9be  mov     [rbp+57h+arg_10], 0
0x18003b9c6  add     r8, 8
0x18003b9ca  lea     rax, [rbp+57h+SRWLock]
0x18003b9ce  mov     [rsp+110h+var_E0], rax
0x18003b9d3  lea     rax, [rbp+57h+arg_8]
0x18003b9d7  mov     [rsp+110h+var_E8], rax
0x18003b9dc  lea     rax, [rbp+57h+arg_10]
0x18003b9e0  mov     [rsp+110h+var_F0], rax
0x18003b9e5  lea     rdx, dword_18007827C
0x18003b9ec  mov     rcx, rdi
0x18003b9ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b9f4  nop
0x18003b9f5  lea     rcx, [rbx+120h]; this
0x18003b9fc  cmp     dword ptr [rcx+18h], 0
0x18003ba00  jz      short loc_18003BA08
0x18003ba02  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003ba07  nop
0x18003ba08  add     rsp, 100h
0x18003ba0f  pop     rdi
0x18003ba10  pop     rbx
0x18003ba11  pop     rbp
0x18003ba12  retn
```
