# LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::StopActivity(void)

- ea: `0x18002fee0`
- end: `0x180030173`
- name: `?StopActivity@LanguageFeatureInstallationRequest@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18002fee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ff3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800300cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ff3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800300cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030107`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::StopActivity(
        LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest *this)
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
        (__int64)byte_1800777D5,
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
        (__int64)&byte_180077727,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002fee0  push    rbp
0x18002fee2  push    rbx
0x18002fee3  push    rdi
0x18002fee4  lea     rbp, [rsp-47h]
0x18002fee9  sub     rsp, 100h
0x18002fef0  mov     rbx, rcx
0x18002fef3  mov     rdi, [rcx+110h]
0x18002fefa  mov     eax, [rdi+48h]
0x18002fefd  test    eax, eax
0x18002feff  jns     loc_1800300B0
0x18002ff05  add     rdi, 50h ; 'P'
0x18002ff09  cmp     eax, [rdi+8]
0x18002ff0c  jnz     loc_1800300B0
0x18002ff12  test    rdi, rdi
0x18002ff15  jz      loc_1800300B0
0x18002ff1b  lea     rdx, [rbp+57h+SRWLock]
0x18002ff1f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002ff24  mov     rax, [rbx+110h]
0x18002ff2b  mov     dword ptr [rax], 2
0x18002ff31  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002ff35  test    rcx, rcx
0x18002ff38  jz      short loc_18002FF40
0x18002ff3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ff40  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18002ff45  mov     r9, [rax+8]
0x18002ff49  mov     eax, [r9]
0x18002ff4c  cmp     eax, 5
0x18002ff4f  jbe     loc_180030155
0x18002ff55  mov     rdx, [r9+18h]
0x18002ff59  mov     rax, [r9+10h]
0x18002ff5d  mov     rcx, 400000000000h
0x18002ff67  test    rcx, rax
0x18002ff6a  jz      loc_180030155
0x18002ff70  mov     rax, rdx
0x18002ff73  and     rax, rcx
0x18002ff76  cmp     rax, rdx
0x18002ff79  jnz     loc_180030155
0x18002ff7f  mov     rax, [rdi+78h]
0x18002ff83  mov     [rbp+57h+var_68], rax
0x18002ff87  mov     rax, [rdi+70h]
0x18002ff8b  mov     [rbp+57h+var_60], rax
0x18002ff8f  mov     eax, [rdi+68h]
0x18002ff92  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002ff95  mov     rax, [rdi+60h]
0x18002ff99  mov     [rbp+57h+var_58], rax
0x18002ff9d  mov     rax, [rdi+58h]
0x18002ffa1  mov     [rbp+57h+var_50], rax
0x18002ffa5  mov     eax, [rdi+50h]
0x18002ffa8  mov     [rbp+57h+arg_8], eax
0x18002ffab  mov     rax, [rdi+48h]
0x18002ffaf  mov     [rbp+57h+var_48], rax
0x18002ffb3  mov     eax, [rdi+20h]
0x18002ffb6  mov     dword ptr [rbp+57h+arg_10], eax
0x18002ffb9  mov     rax, [rdi+18h]
0x18002ffbd  mov     [rbp+57h+var_40], rax
0x18002ffc1  mov     eax, [rdi]
0x18002ffc3  mov     [rbp+57h+arg_18], eax
0x18002ffc6  mov     rax, [rdi+80h]
0x18002ffcd  mov     [rbp+57h+var_38], rax
0x18002ffd1  mov     eax, [rdi+40h]
0x18002ffd4  mov     [rbp+57h+var_70], eax
0x18002ffd7  mov     rax, [rdi+38h]
0x18002ffdb  mov     [rbp+57h+var_30], rax
0x18002ffdf  mov     eax, [rdi+8]
0x18002ffe2  mov     [rbp+57h+var_6C], eax
0x18002ffe5  mov     [rbp+57h+var_28], 1000000h
0x18002ffed  mov     [rbp+57h+var_20], 3000000h
0x18002fff5  mov     r8, [rbx+110h]
0x18002fffc  add     r8, 8
0x180030000  lea     rax, [rbp+57h+var_68]
0x180030004  mov     [rsp+110h+var_78], rax
0x18003000c  lea     rax, [rbp+57h+var_60]
0x180030010  mov     [rsp+110h+var_80], rax
0x180030018  lea     rax, [rbp+57h+SRWLock]
0x18003001c  mov     [rsp+110h+var_88], rax
0x180030024  lea     rax, [rbp+57h+var_58]
0x180030028  mov     [rsp+110h+var_90], rax
0x180030030  lea     rax, [rbp+57h+var_50]
0x180030034  mov     [rsp+110h+var_98], rax
0x180030039  lea     rax, [rbp+57h+arg_8]
0x18003003d  mov     [rsp+110h+var_A0], rax
0x180030042  lea     rax, [rbp+57h+var_48]
0x180030046  mov     [rsp+110h+var_A8], rax
0x18003004b  lea     rax, [rbp+57h+arg_10]
0x18003004f  mov     [rsp+110h+var_B0], rax
0x180030054  lea     rax, [rbp+57h+var_40]
0x180030058  mov     [rsp+110h+var_B8], rax
0x18003005d  lea     rax, [rbp+57h+arg_18]
0x180030061  mov     [rsp+110h+var_C0], rax
0x180030066  lea     rax, [rbp+57h+var_38]
0x18003006a  mov     [rsp+110h+var_C8], rax
0x18003006f  lea     rax, [rbp+57h+var_70]
0x180030073  mov     [rsp+110h+var_D0], rax
0x180030078  lea     rax, [rbp+57h+var_30]
0x18003007c  mov     [rsp+110h+var_D8], rax
0x180030081  lea     rax, [rbp+57h+var_6C]
0x180030085  mov     [rsp+110h+var_E0], rax
0x18003008a  lea     rax, [rbp+57h+var_28]
0x18003008e  mov     [rsp+110h+var_E8], rax
0x180030093  lea     rax, [rbp+57h+var_20]
0x180030097  mov     [rsp+110h+var_F0], rax
0x18003009c  lea     rdx, byte_1800777D5
0x1800300a3  mov     rcx, r9
0x1800300a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800300ab  jmp     loc_180030155
0x1800300b0  lea     rdx, [rbp+57h+SRWLock]
0x1800300b4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800300b9  mov     rax, [rbx+110h]
0x1800300c0  mov     dword ptr [rax], 2
0x1800300c6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800300ca  test    rcx, rcx
0x1800300cd  jz      short loc_1800300D5
0x1800300cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800300d5  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800300da  mov     rdi, [rax+8]
0x1800300de  mov     eax, [rdi]
0x1800300e0  cmp     eax, 5
0x1800300e3  jbe     short loc_180030155
0x1800300e5  mov     rdx, [rdi+18h]
0x1800300e9  mov     rax, [rdi+10h]
0x1800300ed  mov     rcx, 400000000000h
0x1800300f7  test    rcx, rax
0x1800300fa  jz      short loc_180030155
0x1800300fc  mov     rax, rdx
0x1800300ff  and     rax, rcx
0x180030102  cmp     rax, rdx
0x180030105  jnz     short loc_180030155
0x180030107  call    cs:__imp_GetCurrentThreadId
0x18003010d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180030110  mov     r8, [rbx+110h]
0x180030117  mov     eax, [r8+48h]
0x18003011b  mov     [rbp+57h+arg_8], eax
0x18003011e  mov     [rbp+57h+arg_10], 3000000h
0x180030126  add     r8, 8
0x18003012a  lea     rax, [rbp+57h+SRWLock]
0x18003012e  mov     [rsp+110h+var_E0], rax
0x180030133  lea     rax, [rbp+57h+arg_8]
0x180030137  mov     [rsp+110h+var_E8], rax
0x18003013c  lea     rax, [rbp+57h+arg_10]
0x180030140  mov     [rsp+110h+var_F0], rax
0x180030145  lea     rdx, byte_180077727
0x18003014c  mov     rcx, rdi
0x18003014f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030154  nop
0x180030155  lea     rcx, [rbx+120h]; this
0x18003015c  cmp     dword ptr [rcx+18h], 0
0x180030160  jz      short loc_180030168
0x180030162  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180030167  nop
0x180030168  add     rsp, 100h
0x18003016f  pop     rdi
0x180030170  pop     rbx
0x180030171  pop     rbp
0x180030172  retn
```
