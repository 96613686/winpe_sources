# LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity::StopActivity(void)

- ea: `0x180046a90`
- end: `0x180046d23`
- name: `?StopActivity@InstallSystemLanguagePackActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180046a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046c7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046cb7`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity::StopActivity(
        LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *this)
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
        (__int64)byte_1800790B5,
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
        (__int64)byte_180079053,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::InstallSystemLanguagePackActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180046a90  push    rbp
0x180046a92  push    rbx
0x180046a93  push    rdi
0x180046a94  lea     rbp, [rsp-47h]
0x180046a99  sub     rsp, 100h
0x180046aa0  mov     rbx, rcx
0x180046aa3  mov     rdi, [rcx+110h]
0x180046aaa  mov     eax, [rdi+48h]
0x180046aad  test    eax, eax
0x180046aaf  jns     loc_180046C60
0x180046ab5  add     rdi, 50h ; 'P'
0x180046ab9  cmp     eax, [rdi+8]
0x180046abc  jnz     loc_180046C60
0x180046ac2  test    rdi, rdi
0x180046ac5  jz      loc_180046C60
0x180046acb  lea     rdx, [rbp+57h+SRWLock]
0x180046acf  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046ad4  mov     rax, [rbx+110h]
0x180046adb  mov     dword ptr [rax], 2
0x180046ae1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180046ae5  test    rcx, rcx
0x180046ae8  jz      short loc_180046AF0
0x180046aea  call    cs:__imp_ReleaseSRWLockExclusive
0x180046af0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180046af5  mov     r9, [rax+8]
0x180046af9  mov     eax, [r9]
0x180046afc  cmp     eax, 5
0x180046aff  jbe     loc_180046D05
0x180046b05  mov     rdx, [r9+18h]
0x180046b09  mov     rax, [r9+10h]
0x180046b0d  mov     rcx, 400000000000h
0x180046b17  test    rcx, rax
0x180046b1a  jz      loc_180046D05
0x180046b20  mov     rax, rdx
0x180046b23  and     rax, rcx
0x180046b26  cmp     rax, rdx
0x180046b29  jnz     loc_180046D05
0x180046b2f  mov     rax, [rdi+78h]
0x180046b33  mov     [rbp+57h+var_68], rax
0x180046b37  mov     rax, [rdi+70h]
0x180046b3b  mov     [rbp+57h+var_60], rax
0x180046b3f  mov     eax, [rdi+68h]
0x180046b42  mov     dword ptr [rbp+57h+SRWLock], eax
0x180046b45  mov     rax, [rdi+60h]
0x180046b49  mov     [rbp+57h+var_58], rax
0x180046b4d  mov     rax, [rdi+58h]
0x180046b51  mov     [rbp+57h+var_50], rax
0x180046b55  mov     eax, [rdi+50h]
0x180046b58  mov     [rbp+57h+arg_8], eax
0x180046b5b  mov     rax, [rdi+48h]
0x180046b5f  mov     [rbp+57h+var_48], rax
0x180046b63  mov     eax, [rdi+20h]
0x180046b66  mov     dword ptr [rbp+57h+arg_10], eax
0x180046b69  mov     rax, [rdi+18h]
0x180046b6d  mov     [rbp+57h+var_40], rax
0x180046b71  mov     eax, [rdi]
0x180046b73  mov     [rbp+57h+arg_18], eax
0x180046b76  mov     rax, [rdi+80h]
0x180046b7d  mov     [rbp+57h+var_38], rax
0x180046b81  mov     eax, [rdi+40h]
0x180046b84  mov     [rbp+57h+var_70], eax
0x180046b87  mov     rax, [rdi+38h]
0x180046b8b  mov     [rbp+57h+var_30], rax
0x180046b8f  mov     eax, [rdi+8]
0x180046b92  mov     [rbp+57h+var_6C], eax
0x180046b95  mov     [rbp+57h+var_28], 1000000h
0x180046b9d  mov     [rbp+57h+var_20], 3000000h
0x180046ba5  mov     r8, [rbx+110h]
0x180046bac  add     r8, 8
0x180046bb0  lea     rax, [rbp+57h+var_68]
0x180046bb4  mov     [rsp+110h+var_78], rax
0x180046bbc  lea     rax, [rbp+57h+var_60]
0x180046bc0  mov     [rsp+110h+var_80], rax
0x180046bc8  lea     rax, [rbp+57h+SRWLock]
0x180046bcc  mov     [rsp+110h+var_88], rax
0x180046bd4  lea     rax, [rbp+57h+var_58]
0x180046bd8  mov     [rsp+110h+var_90], rax
0x180046be0  lea     rax, [rbp+57h+var_50]
0x180046be4  mov     [rsp+110h+var_98], rax
0x180046be9  lea     rax, [rbp+57h+arg_8]
0x180046bed  mov     [rsp+110h+var_A0], rax
0x180046bf2  lea     rax, [rbp+57h+var_48]
0x180046bf6  mov     [rsp+110h+var_A8], rax
0x180046bfb  lea     rax, [rbp+57h+arg_10]
0x180046bff  mov     [rsp+110h+var_B0], rax
0x180046c04  lea     rax, [rbp+57h+var_40]
0x180046c08  mov     [rsp+110h+var_B8], rax
0x180046c0d  lea     rax, [rbp+57h+arg_18]
0x180046c11  mov     [rsp+110h+var_C0], rax
0x180046c16  lea     rax, [rbp+57h+var_38]
0x180046c1a  mov     [rsp+110h+var_C8], rax
0x180046c1f  lea     rax, [rbp+57h+var_70]
0x180046c23  mov     [rsp+110h+var_D0], rax
0x180046c28  lea     rax, [rbp+57h+var_30]
0x180046c2c  mov     [rsp+110h+var_D8], rax
0x180046c31  lea     rax, [rbp+57h+var_6C]
0x180046c35  mov     [rsp+110h+var_E0], rax
0x180046c3a  lea     rax, [rbp+57h+var_28]
0x180046c3e  mov     [rsp+110h+var_E8], rax
0x180046c43  lea     rax, [rbp+57h+var_20]
0x180046c47  mov     [rsp+110h+var_F0], rax
0x180046c4c  lea     rdx, byte_1800790B5
0x180046c53  mov     rcx, r9
0x180046c56  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180046c5b  jmp     loc_180046D05
0x180046c60  lea     rdx, [rbp+57h+SRWLock]
0x180046c64  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046c69  mov     rax, [rbx+110h]
0x180046c70  mov     dword ptr [rax], 2
0x180046c76  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180046c7a  test    rcx, rcx
0x180046c7d  jz      short loc_180046C85
0x180046c7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180046c85  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180046c8a  mov     rdi, [rax+8]
0x180046c8e  mov     eax, [rdi]
0x180046c90  cmp     eax, 5
0x180046c93  jbe     short loc_180046D05
0x180046c95  mov     rdx, [rdi+18h]
0x180046c99  mov     rax, [rdi+10h]
0x180046c9d  mov     rcx, 400000000000h
0x180046ca7  test    rcx, rax
0x180046caa  jz      short loc_180046D05
0x180046cac  mov     rax, rdx
0x180046caf  and     rax, rcx
0x180046cb2  cmp     rax, rdx
0x180046cb5  jnz     short loc_180046D05
0x180046cb7  call    cs:__imp_GetCurrentThreadId
0x180046cbd  mov     dword ptr [rbp+57h+SRWLock], eax
0x180046cc0  mov     r8, [rbx+110h]
0x180046cc7  mov     eax, [r8+48h]
0x180046ccb  mov     [rbp+57h+arg_8], eax
0x180046cce  mov     [rbp+57h+arg_10], 3000000h
0x180046cd6  add     r8, 8
0x180046cda  lea     rax, [rbp+57h+SRWLock]
0x180046cde  mov     [rsp+110h+var_E0], rax
0x180046ce3  lea     rax, [rbp+57h+arg_8]
0x180046ce7  mov     [rsp+110h+var_E8], rax
0x180046cec  lea     rax, [rbp+57h+arg_10]
0x180046cf0  mov     [rsp+110h+var_F0], rax
0x180046cf5  lea     rdx, byte_180079053
0x180046cfc  mov     rcx, rdi
0x180046cff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046d04  nop
0x180046d05  lea     rcx, [rbx+120h]; this
0x180046d0c  cmp     dword ptr [rcx+18h], 0
0x180046d10  jz      short loc_180046D18
0x180046d12  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046d17  nop
0x180046d18  add     rsp, 100h
0x180046d1f  pop     rdi
0x180046d20  pop     rbx
0x180046d21  pop     rbp
0x180046d22  retn
```
