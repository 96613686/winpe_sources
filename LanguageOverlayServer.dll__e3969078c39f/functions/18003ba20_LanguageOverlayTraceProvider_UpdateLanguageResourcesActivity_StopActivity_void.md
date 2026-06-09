# LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity::StopActivity(void)

- ea: `0x18003ba20`
- end: `0x18003bcb3`
- name: `?StopActivity@UpdateLanguageResourcesActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18003ba20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ba7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003bc0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ba7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003bc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bc47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bc47`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity::StopActivity(
        LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *this)
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
        (__int64)byte_1800780E3,
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
        (__int64)byte_180078083,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003ba20  push    rbp
0x18003ba22  push    rbx
0x18003ba23  push    rdi
0x18003ba24  lea     rbp, [rsp-47h]
0x18003ba29  sub     rsp, 100h
0x18003ba30  mov     rbx, rcx
0x18003ba33  mov     rdi, [rcx+110h]
0x18003ba3a  mov     eax, [rdi+48h]
0x18003ba3d  test    eax, eax
0x18003ba3f  jns     loc_18003BBF0
0x18003ba45  add     rdi, 50h ; 'P'
0x18003ba49  cmp     eax, [rdi+8]
0x18003ba4c  jnz     loc_18003BBF0
0x18003ba52  test    rdi, rdi
0x18003ba55  jz      loc_18003BBF0
0x18003ba5b  lea     rdx, [rbp+57h+SRWLock]
0x18003ba5f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ba64  mov     rax, [rbx+110h]
0x18003ba6b  mov     dword ptr [rax], 2
0x18003ba71  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003ba75  test    rcx, rcx
0x18003ba78  jz      short loc_18003BA80
0x18003ba7a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ba80  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003ba85  mov     r9, [rax+8]
0x18003ba89  mov     eax, [r9]
0x18003ba8c  cmp     eax, 5
0x18003ba8f  jbe     loc_18003BC95
0x18003ba95  mov     rdx, [r9+18h]
0x18003ba99  mov     rax, [r9+10h]
0x18003ba9d  mov     rcx, 200000000000h
0x18003baa7  test    rcx, rax
0x18003baaa  jz      loc_18003BC95
0x18003bab0  mov     rax, rdx
0x18003bab3  and     rax, rcx
0x18003bab6  cmp     rax, rdx
0x18003bab9  jnz     loc_18003BC95
0x18003babf  mov     rax, [rdi+78h]
0x18003bac3  mov     [rbp+57h+var_68], rax
0x18003bac7  mov     rax, [rdi+70h]
0x18003bacb  mov     [rbp+57h+var_60], rax
0x18003bacf  mov     eax, [rdi+68h]
0x18003bad2  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003bad5  mov     rax, [rdi+60h]
0x18003bad9  mov     [rbp+57h+var_58], rax
0x18003badd  mov     rax, [rdi+58h]
0x18003bae1  mov     [rbp+57h+var_50], rax
0x18003bae5  mov     eax, [rdi+50h]
0x18003bae8  mov     [rbp+57h+arg_8], eax
0x18003baeb  mov     rax, [rdi+48h]
0x18003baef  mov     [rbp+57h+var_48], rax
0x18003baf3  mov     eax, [rdi+20h]
0x18003baf6  mov     dword ptr [rbp+57h+arg_10], eax
0x18003baf9  mov     rax, [rdi+18h]
0x18003bafd  mov     [rbp+57h+var_40], rax
0x18003bb01  mov     eax, [rdi]
0x18003bb03  mov     [rbp+57h+arg_18], eax
0x18003bb06  mov     rax, [rdi+80h]
0x18003bb0d  mov     [rbp+57h+var_38], rax
0x18003bb11  mov     eax, [rdi+40h]
0x18003bb14  mov     [rbp+57h+var_70], eax
0x18003bb17  mov     rax, [rdi+38h]
0x18003bb1b  mov     [rbp+57h+var_30], rax
0x18003bb1f  mov     eax, [rdi+8]
0x18003bb22  mov     [rbp+57h+var_6C], eax
0x18003bb25  mov     [rbp+57h+var_28], 1000000h
0x18003bb2d  mov     [rbp+57h+var_20], 0
0x18003bb35  mov     r8, [rbx+110h]
0x18003bb3c  add     r8, 8
0x18003bb40  lea     rax, [rbp+57h+var_68]
0x18003bb44  mov     [rsp+110h+var_78], rax
0x18003bb4c  lea     rax, [rbp+57h+var_60]
0x18003bb50  mov     [rsp+110h+var_80], rax
0x18003bb58  lea     rax, [rbp+57h+SRWLock]
0x18003bb5c  mov     [rsp+110h+var_88], rax
0x18003bb64  lea     rax, [rbp+57h+var_58]
0x18003bb68  mov     [rsp+110h+var_90], rax
0x18003bb70  lea     rax, [rbp+57h+var_50]
0x18003bb74  mov     [rsp+110h+var_98], rax
0x18003bb79  lea     rax, [rbp+57h+arg_8]
0x18003bb7d  mov     [rsp+110h+var_A0], rax
0x18003bb82  lea     rax, [rbp+57h+var_48]
0x18003bb86  mov     [rsp+110h+var_A8], rax
0x18003bb8b  lea     rax, [rbp+57h+arg_10]
0x18003bb8f  mov     [rsp+110h+var_B0], rax
0x18003bb94  lea     rax, [rbp+57h+var_40]
0x18003bb98  mov     [rsp+110h+var_B8], rax
0x18003bb9d  lea     rax, [rbp+57h+arg_18]
0x18003bba1  mov     [rsp+110h+var_C0], rax
0x18003bba6  lea     rax, [rbp+57h+var_38]
0x18003bbaa  mov     [rsp+110h+var_C8], rax
0x18003bbaf  lea     rax, [rbp+57h+var_70]
0x18003bbb3  mov     [rsp+110h+var_D0], rax
0x18003bbb8  lea     rax, [rbp+57h+var_30]
0x18003bbbc  mov     [rsp+110h+var_D8], rax
0x18003bbc1  lea     rax, [rbp+57h+var_6C]
0x18003bbc5  mov     [rsp+110h+var_E0], rax
0x18003bbca  lea     rax, [rbp+57h+var_28]
0x18003bbce  mov     [rsp+110h+var_E8], rax
0x18003bbd3  lea     rax, [rbp+57h+var_20]
0x18003bbd7  mov     [rsp+110h+var_F0], rax
0x18003bbdc  lea     rdx, byte_1800780E3
0x18003bbe3  mov     rcx, r9
0x18003bbe6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003bbeb  jmp     loc_18003BC95
0x18003bbf0  lea     rdx, [rbp+57h+SRWLock]
0x18003bbf4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003bbf9  mov     rax, [rbx+110h]
0x18003bc00  mov     dword ptr [rax], 2
0x18003bc06  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003bc0a  test    rcx, rcx
0x18003bc0d  jz      short loc_18003BC15
0x18003bc0f  call    cs:__imp_ReleaseSRWLockExclusive
0x18003bc15  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003bc1a  mov     rdi, [rax+8]
0x18003bc1e  mov     eax, [rdi]
0x18003bc20  cmp     eax, 5
0x18003bc23  jbe     short loc_18003BC95
0x18003bc25  mov     rdx, [rdi+18h]
0x18003bc29  mov     rax, [rdi+10h]
0x18003bc2d  mov     rcx, 200000000000h
0x18003bc37  test    rcx, rax
0x18003bc3a  jz      short loc_18003BC95
0x18003bc3c  mov     rax, rdx
0x18003bc3f  and     rax, rcx
0x18003bc42  cmp     rax, rdx
0x18003bc45  jnz     short loc_18003BC95
0x18003bc47  call    cs:__imp_GetCurrentThreadId
0x18003bc4d  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003bc50  mov     r8, [rbx+110h]
0x18003bc57  mov     eax, [r8+48h]
0x18003bc5b  mov     [rbp+57h+arg_8], eax
0x18003bc5e  mov     [rbp+57h+arg_10], 0
0x18003bc66  add     r8, 8
0x18003bc6a  lea     rax, [rbp+57h+SRWLock]
0x18003bc6e  mov     [rsp+110h+var_E0], rax
0x18003bc73  lea     rax, [rbp+57h+arg_8]
0x18003bc77  mov     [rsp+110h+var_E8], rax
0x18003bc7c  lea     rax, [rbp+57h+arg_10]
0x18003bc80  mov     [rsp+110h+var_F0], rax
0x18003bc85  lea     rdx, byte_180078083
0x18003bc8c  mov     rcx, rdi
0x18003bc8f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003bc94  nop
0x18003bc95  lea     rcx, [rbx+120h]; this
0x18003bc9c  cmp     dword ptr [rcx+18h], 0
0x18003bca0  jz      short loc_18003BCA8
0x18003bca2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003bca7  nop
0x18003bca8  add     rsp, 100h
0x18003bcaf  pop     rdi
0x18003bcb0  pop     rbx
0x18003bcb1  pop     rbp
0x18003bcb2  retn
```
