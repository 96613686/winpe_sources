# LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::StopActivity(void)

- ea: `0x180046d30`
- end: `0x180046fc3`
- name: `?StopActivity@UninstallSystemLanguagePackActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180046d30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046f1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046f57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046f57`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::StopActivity(
        LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity *this)
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
        (__int64)&word_180078D56,
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
        (__int64)byte_180078C7D,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180046d30  push    rbp
0x180046d32  push    rbx
0x180046d33  push    rdi
0x180046d34  lea     rbp, [rsp-47h]
0x180046d39  sub     rsp, 100h
0x180046d40  mov     rbx, rcx
0x180046d43  mov     rdi, [rcx+110h]
0x180046d4a  mov     eax, [rdi+48h]
0x180046d4d  test    eax, eax
0x180046d4f  jns     loc_180046F00
0x180046d55  add     rdi, 50h ; 'P'
0x180046d59  cmp     eax, [rdi+8]
0x180046d5c  jnz     loc_180046F00
0x180046d62  test    rdi, rdi
0x180046d65  jz      loc_180046F00
0x180046d6b  lea     rdx, [rbp+57h+SRWLock]
0x180046d6f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046d74  mov     rax, [rbx+110h]
0x180046d7b  mov     dword ptr [rax], 2
0x180046d81  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180046d85  test    rcx, rcx
0x180046d88  jz      short loc_180046D90
0x180046d8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180046d90  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180046d95  mov     r9, [rax+8]
0x180046d99  mov     eax, [r9]
0x180046d9c  cmp     eax, 5
0x180046d9f  jbe     loc_180046FA5
0x180046da5  mov     rdx, [r9+18h]
0x180046da9  mov     rax, [r9+10h]
0x180046dad  mov     rcx, 400000000000h
0x180046db7  test    rcx, rax
0x180046dba  jz      loc_180046FA5
0x180046dc0  mov     rax, rdx
0x180046dc3  and     rax, rcx
0x180046dc6  cmp     rax, rdx
0x180046dc9  jnz     loc_180046FA5
0x180046dcf  mov     rax, [rdi+78h]
0x180046dd3  mov     [rbp+57h+var_68], rax
0x180046dd7  mov     rax, [rdi+70h]
0x180046ddb  mov     [rbp+57h+var_60], rax
0x180046ddf  mov     eax, [rdi+68h]
0x180046de2  mov     dword ptr [rbp+57h+SRWLock], eax
0x180046de5  mov     rax, [rdi+60h]
0x180046de9  mov     [rbp+57h+var_58], rax
0x180046ded  mov     rax, [rdi+58h]
0x180046df1  mov     [rbp+57h+var_50], rax
0x180046df5  mov     eax, [rdi+50h]
0x180046df8  mov     [rbp+57h+arg_8], eax
0x180046dfb  mov     rax, [rdi+48h]
0x180046dff  mov     [rbp+57h+var_48], rax
0x180046e03  mov     eax, [rdi+20h]
0x180046e06  mov     dword ptr [rbp+57h+arg_10], eax
0x180046e09  mov     rax, [rdi+18h]
0x180046e0d  mov     [rbp+57h+var_40], rax
0x180046e11  mov     eax, [rdi]
0x180046e13  mov     [rbp+57h+arg_18], eax
0x180046e16  mov     rax, [rdi+80h]
0x180046e1d  mov     [rbp+57h+var_38], rax
0x180046e21  mov     eax, [rdi+40h]
0x180046e24  mov     [rbp+57h+var_70], eax
0x180046e27  mov     rax, [rdi+38h]
0x180046e2b  mov     [rbp+57h+var_30], rax
0x180046e2f  mov     eax, [rdi+8]
0x180046e32  mov     [rbp+57h+var_6C], eax
0x180046e35  mov     [rbp+57h+var_28], 1000000h
0x180046e3d  mov     [rbp+57h+var_20], 3000000h
0x180046e45  mov     r8, [rbx+110h]
0x180046e4c  add     r8, 8
0x180046e50  lea     rax, [rbp+57h+var_68]
0x180046e54  mov     [rsp+110h+var_78], rax
0x180046e5c  lea     rax, [rbp+57h+var_60]
0x180046e60  mov     [rsp+110h+var_80], rax
0x180046e68  lea     rax, [rbp+57h+SRWLock]
0x180046e6c  mov     [rsp+110h+var_88], rax
0x180046e74  lea     rax, [rbp+57h+var_58]
0x180046e78  mov     [rsp+110h+var_90], rax
0x180046e80  lea     rax, [rbp+57h+var_50]
0x180046e84  mov     [rsp+110h+var_98], rax
0x180046e89  lea     rax, [rbp+57h+arg_8]
0x180046e8d  mov     [rsp+110h+var_A0], rax
0x180046e92  lea     rax, [rbp+57h+var_48]
0x180046e96  mov     [rsp+110h+var_A8], rax
0x180046e9b  lea     rax, [rbp+57h+arg_10]
0x180046e9f  mov     [rsp+110h+var_B0], rax
0x180046ea4  lea     rax, [rbp+57h+var_40]
0x180046ea8  mov     [rsp+110h+var_B8], rax
0x180046ead  lea     rax, [rbp+57h+arg_18]
0x180046eb1  mov     [rsp+110h+var_C0], rax
0x180046eb6  lea     rax, [rbp+57h+var_38]
0x180046eba  mov     [rsp+110h+var_C8], rax
0x180046ebf  lea     rax, [rbp+57h+var_70]
0x180046ec3  mov     [rsp+110h+var_D0], rax
0x180046ec8  lea     rax, [rbp+57h+var_30]
0x180046ecc  mov     [rsp+110h+var_D8], rax
0x180046ed1  lea     rax, [rbp+57h+var_6C]
0x180046ed5  mov     [rsp+110h+var_E0], rax
0x180046eda  lea     rax, [rbp+57h+var_28]
0x180046ede  mov     [rsp+110h+var_E8], rax
0x180046ee3  lea     rax, [rbp+57h+var_20]
0x180046ee7  mov     [rsp+110h+var_F0], rax
0x180046eec  lea     rdx, word_180078D56
0x180046ef3  mov     rcx, r9
0x180046ef6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180046efb  jmp     loc_180046FA5
0x180046f00  lea     rdx, [rbp+57h+SRWLock]
0x180046f04  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046f09  mov     rax, [rbx+110h]
0x180046f10  mov     dword ptr [rax], 2
0x180046f16  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180046f1a  test    rcx, rcx
0x180046f1d  jz      short loc_180046F25
0x180046f1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180046f25  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180046f2a  mov     rdi, [rax+8]
0x180046f2e  mov     eax, [rdi]
0x180046f30  cmp     eax, 5
0x180046f33  jbe     short loc_180046FA5
0x180046f35  mov     rdx, [rdi+18h]
0x180046f39  mov     rax, [rdi+10h]
0x180046f3d  mov     rcx, 400000000000h
0x180046f47  test    rcx, rax
0x180046f4a  jz      short loc_180046FA5
0x180046f4c  mov     rax, rdx
0x180046f4f  and     rax, rcx
0x180046f52  cmp     rax, rdx
0x180046f55  jnz     short loc_180046FA5
0x180046f57  call    cs:__imp_GetCurrentThreadId
0x180046f5d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180046f60  mov     r8, [rbx+110h]
0x180046f67  mov     eax, [r8+48h]
0x180046f6b  mov     [rbp+57h+arg_8], eax
0x180046f6e  mov     [rbp+57h+arg_10], 3000000h
0x180046f76  add     r8, 8
0x180046f7a  lea     rax, [rbp+57h+SRWLock]
0x180046f7e  mov     [rsp+110h+var_E0], rax
0x180046f83  lea     rax, [rbp+57h+arg_8]
0x180046f87  mov     [rsp+110h+var_E8], rax
0x180046f8c  lea     rax, [rbp+57h+arg_10]
0x180046f90  mov     [rsp+110h+var_F0], rax
0x180046f95  lea     rdx, byte_180078C7D
0x180046f9c  mov     rcx, rdi
0x180046f9f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046fa4  nop
0x180046fa5  lea     rcx, [rbx+120h]; this
0x180046fac  cmp     dword ptr [rcx+18h], 0
0x180046fb0  jz      short loc_180046FB8
0x180046fb2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046fb7  nop
0x180046fb8  add     rsp, 100h
0x180046fbf  pop     rdi
0x180046fc0  pop     rbx
0x180046fc1  pop     rbp
0x180046fc2  retn
```
