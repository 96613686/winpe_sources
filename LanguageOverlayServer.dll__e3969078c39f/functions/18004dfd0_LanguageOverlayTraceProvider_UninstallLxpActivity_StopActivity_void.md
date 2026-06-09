# LanguageOverlayTraceProvider::UninstallLxpActivity::StopActivity(void)

- ea: `0x18004dfd0`
- end: `0x18004e263`
- name: `?StopActivity@UninstallLxpActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::UninstallLxpActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18004dfd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e02a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e1bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e02a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e1f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e1f7`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::UninstallLxpActivity::StopActivity(
        LanguageOverlayTraceProvider::UninstallLxpActivity *this)
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
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)&unk_180079370,
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
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&byte_1800792C7,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::UninstallLxpActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004dfd0  push    rbp
0x18004dfd2  push    rbx
0x18004dfd3  push    rdi
0x18004dfd4  lea     rbp, [rsp-47h]
0x18004dfd9  sub     rsp, 100h
0x18004dfe0  mov     rbx, rcx
0x18004dfe3  mov     rdi, [rcx+110h]
0x18004dfea  mov     eax, [rdi+48h]
0x18004dfed  test    eax, eax
0x18004dfef  jns     loc_18004E1A0
0x18004dff5  add     rdi, 50h ; 'P'
0x18004dff9  cmp     eax, [rdi+8]
0x18004dffc  jnz     loc_18004E1A0
0x18004e002  test    rdi, rdi
0x18004e005  jz      loc_18004E1A0
0x18004e00b  lea     rdx, [rbp+57h+SRWLock]
0x18004e00f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e014  mov     rax, [rbx+110h]
0x18004e01b  mov     dword ptr [rax], 2
0x18004e021  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004e025  test    rcx, rcx
0x18004e028  jz      short loc_18004E030
0x18004e02a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e030  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18004e035  mov     r9, [rax+8]
0x18004e039  mov     eax, [r9]
0x18004e03c  cmp     eax, 5
0x18004e03f  jbe     loc_18004E245
0x18004e045  mov     rdx, [r9+18h]
0x18004e049  mov     rax, [r9+10h]
0x18004e04d  mov     rcx, 400000000000h
0x18004e057  test    rcx, rax
0x18004e05a  jz      loc_18004E245
0x18004e060  mov     rax, rdx
0x18004e063  and     rax, rcx
0x18004e066  cmp     rax, rdx
0x18004e069  jnz     loc_18004E245
0x18004e06f  mov     rax, [rdi+78h]
0x18004e073  mov     [rbp+57h+var_68], rax
0x18004e077  mov     rax, [rdi+70h]
0x18004e07b  mov     [rbp+57h+var_60], rax
0x18004e07f  mov     eax, [rdi+68h]
0x18004e082  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004e085  mov     rax, [rdi+60h]
0x18004e089  mov     [rbp+57h+var_58], rax
0x18004e08d  mov     rax, [rdi+58h]
0x18004e091  mov     [rbp+57h+var_50], rax
0x18004e095  mov     eax, [rdi+50h]
0x18004e098  mov     [rbp+57h+arg_8], eax
0x18004e09b  mov     rax, [rdi+48h]
0x18004e09f  mov     [rbp+57h+var_48], rax
0x18004e0a3  mov     eax, [rdi+20h]
0x18004e0a6  mov     dword ptr [rbp+57h+arg_10], eax
0x18004e0a9  mov     rax, [rdi+18h]
0x18004e0ad  mov     [rbp+57h+var_40], rax
0x18004e0b1  mov     eax, [rdi]
0x18004e0b3  mov     [rbp+57h+arg_18], eax
0x18004e0b6  mov     rax, [rdi+80h]
0x18004e0bd  mov     [rbp+57h+var_38], rax
0x18004e0c1  mov     eax, [rdi+40h]
0x18004e0c4  mov     [rbp+57h+var_70], eax
0x18004e0c7  mov     rax, [rdi+38h]
0x18004e0cb  mov     [rbp+57h+var_30], rax
0x18004e0cf  mov     eax, [rdi+8]
0x18004e0d2  mov     [rbp+57h+var_6C], eax
0x18004e0d5  mov     [rbp+57h+var_28], 1000000h
0x18004e0dd  mov     [rbp+57h+var_20], 0
0x18004e0e5  mov     r8, [rbx+110h]
0x18004e0ec  add     r8, 8
0x18004e0f0  lea     rax, [rbp+57h+var_68]
0x18004e0f4  mov     [rsp+110h+var_78], rax
0x18004e0fc  lea     rax, [rbp+57h+var_60]
0x18004e100  mov     [rsp+110h+var_80], rax
0x18004e108  lea     rax, [rbp+57h+SRWLock]
0x18004e10c  mov     [rsp+110h+var_88], rax
0x18004e114  lea     rax, [rbp+57h+var_58]
0x18004e118  mov     [rsp+110h+var_90], rax
0x18004e120  lea     rax, [rbp+57h+var_50]
0x18004e124  mov     [rsp+110h+var_98], rax
0x18004e129  lea     rax, [rbp+57h+arg_8]
0x18004e12d  mov     [rsp+110h+var_A0], rax
0x18004e132  lea     rax, [rbp+57h+var_48]
0x18004e136  mov     [rsp+110h+var_A8], rax
0x18004e13b  lea     rax, [rbp+57h+arg_10]
0x18004e13f  mov     [rsp+110h+var_B0], rax
0x18004e144  lea     rax, [rbp+57h+var_40]
0x18004e148  mov     [rsp+110h+var_B8], rax
0x18004e14d  lea     rax, [rbp+57h+arg_18]
0x18004e151  mov     [rsp+110h+var_C0], rax
0x18004e156  lea     rax, [rbp+57h+var_38]
0x18004e15a  mov     [rsp+110h+var_C8], rax
0x18004e15f  lea     rax, [rbp+57h+var_70]
0x18004e163  mov     [rsp+110h+var_D0], rax
0x18004e168  lea     rax, [rbp+57h+var_30]
0x18004e16c  mov     [rsp+110h+var_D8], rax
0x18004e171  lea     rax, [rbp+57h+var_6C]
0x18004e175  mov     [rsp+110h+var_E0], rax
0x18004e17a  lea     rax, [rbp+57h+var_28]
0x18004e17e  mov     [rsp+110h+var_E8], rax
0x18004e183  lea     rax, [rbp+57h+var_20]
0x18004e187  mov     [rsp+110h+var_F0], rax
0x18004e18c  lea     rdx, unk_180079370
0x18004e193  mov     rcx, r9
0x18004e196  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004e19b  jmp     loc_18004E245
0x18004e1a0  lea     rdx, [rbp+57h+SRWLock]
0x18004e1a4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e1a9  mov     rax, [rbx+110h]
0x18004e1b0  mov     dword ptr [rax], 2
0x18004e1b6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004e1ba  test    rcx, rcx
0x18004e1bd  jz      short loc_18004E1C5
0x18004e1bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e1c5  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18004e1ca  mov     rdi, [rax+8]
0x18004e1ce  mov     eax, [rdi]
0x18004e1d0  cmp     eax, 5
0x18004e1d3  jbe     short loc_18004E245
0x18004e1d5  mov     rdx, [rdi+18h]
0x18004e1d9  mov     rax, [rdi+10h]
0x18004e1dd  mov     rcx, 400000000000h
0x18004e1e7  test    rcx, rax
0x18004e1ea  jz      short loc_18004E245
0x18004e1ec  mov     rax, rdx
0x18004e1ef  and     rax, rcx
0x18004e1f2  cmp     rax, rdx
0x18004e1f5  jnz     short loc_18004E245
0x18004e1f7  call    cs:__imp_GetCurrentThreadId
0x18004e1fd  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004e200  mov     r8, [rbx+110h]
0x18004e207  mov     eax, [r8+48h]
0x18004e20b  mov     [rbp+57h+arg_8], eax
0x18004e20e  mov     [rbp+57h+arg_10], 0
0x18004e216  add     r8, 8
0x18004e21a  lea     rax, [rbp+57h+SRWLock]
0x18004e21e  mov     [rsp+110h+var_E0], rax
0x18004e223  lea     rax, [rbp+57h+arg_8]
0x18004e227  mov     [rsp+110h+var_E8], rax
0x18004e22c  lea     rax, [rbp+57h+arg_10]
0x18004e230  mov     [rsp+110h+var_F0], rax
0x18004e235  lea     rdx, byte_1800792C7
0x18004e23c  mov     rcx, rdi
0x18004e23f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004e244  nop
0x18004e245  lea     rcx, [rbx+120h]; this
0x18004e24c  cmp     dword ptr [rcx+18h], 0
0x18004e250  jz      short loc_18004E258
0x18004e252  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004e257  nop
0x18004e258  add     rsp, 100h
0x18004e25f  pop     rdi
0x18004e260  pop     rbx
0x18004e261  pop     rbp
0x18004e262  retn
```
