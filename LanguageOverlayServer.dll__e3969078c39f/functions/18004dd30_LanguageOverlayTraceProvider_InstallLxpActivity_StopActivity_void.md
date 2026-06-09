# LanguageOverlayTraceProvider::InstallLxpActivity::StopActivity(void)

- ea: `0x18004dd30`
- end: `0x18004dfc3`
- name: `?StopActivity@InstallLxpActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::InstallLxpActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18004dd30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dd8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004df1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dd8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004df1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004df57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004df57`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::InstallLxpActivity::StopActivity(
        LanguageOverlayTraceProvider::InstallLxpActivity *this)
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
        (__int64)&byte_1800794EF,
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
        (__int64)&dword_18007949C,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::InstallLxpActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004dd30  push    rbp
0x18004dd32  push    rbx
0x18004dd33  push    rdi
0x18004dd34  lea     rbp, [rsp-47h]
0x18004dd39  sub     rsp, 100h
0x18004dd40  mov     rbx, rcx
0x18004dd43  mov     rdi, [rcx+110h]
0x18004dd4a  mov     eax, [rdi+48h]
0x18004dd4d  test    eax, eax
0x18004dd4f  jns     loc_18004DF00
0x18004dd55  add     rdi, 50h ; 'P'
0x18004dd59  cmp     eax, [rdi+8]
0x18004dd5c  jnz     loc_18004DF00
0x18004dd62  test    rdi, rdi
0x18004dd65  jz      loc_18004DF00
0x18004dd6b  lea     rdx, [rbp+57h+SRWLock]
0x18004dd6f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004dd74  mov     rax, [rbx+110h]
0x18004dd7b  mov     dword ptr [rax], 2
0x18004dd81  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004dd85  test    rcx, rcx
0x18004dd88  jz      short loc_18004DD90
0x18004dd8a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004dd90  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18004dd95  mov     r9, [rax+8]
0x18004dd99  mov     eax, [r9]
0x18004dd9c  cmp     eax, 5
0x18004dd9f  jbe     loc_18004DFA5
0x18004dda5  mov     rdx, [r9+18h]
0x18004dda9  mov     rax, [r9+10h]
0x18004ddad  mov     rcx, 400000000000h
0x18004ddb7  test    rcx, rax
0x18004ddba  jz      loc_18004DFA5
0x18004ddc0  mov     rax, rdx
0x18004ddc3  and     rax, rcx
0x18004ddc6  cmp     rax, rdx
0x18004ddc9  jnz     loc_18004DFA5
0x18004ddcf  mov     rax, [rdi+78h]
0x18004ddd3  mov     [rbp+57h+var_68], rax
0x18004ddd7  mov     rax, [rdi+70h]
0x18004dddb  mov     [rbp+57h+var_60], rax
0x18004dddf  mov     eax, [rdi+68h]
0x18004dde2  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004dde5  mov     rax, [rdi+60h]
0x18004dde9  mov     [rbp+57h+var_58], rax
0x18004dded  mov     rax, [rdi+58h]
0x18004ddf1  mov     [rbp+57h+var_50], rax
0x18004ddf5  mov     eax, [rdi+50h]
0x18004ddf8  mov     [rbp+57h+arg_8], eax
0x18004ddfb  mov     rax, [rdi+48h]
0x18004ddff  mov     [rbp+57h+var_48], rax
0x18004de03  mov     eax, [rdi+20h]
0x18004de06  mov     dword ptr [rbp+57h+arg_10], eax
0x18004de09  mov     rax, [rdi+18h]
0x18004de0d  mov     [rbp+57h+var_40], rax
0x18004de11  mov     eax, [rdi]
0x18004de13  mov     [rbp+57h+arg_18], eax
0x18004de16  mov     rax, [rdi+80h]
0x18004de1d  mov     [rbp+57h+var_38], rax
0x18004de21  mov     eax, [rdi+40h]
0x18004de24  mov     [rbp+57h+var_70], eax
0x18004de27  mov     rax, [rdi+38h]
0x18004de2b  mov     [rbp+57h+var_30], rax
0x18004de2f  mov     eax, [rdi+8]
0x18004de32  mov     [rbp+57h+var_6C], eax
0x18004de35  mov     [rbp+57h+var_28], 1000000h
0x18004de3d  mov     [rbp+57h+var_20], 0
0x18004de45  mov     r8, [rbx+110h]
0x18004de4c  add     r8, 8
0x18004de50  lea     rax, [rbp+57h+var_68]
0x18004de54  mov     [rsp+110h+var_78], rax
0x18004de5c  lea     rax, [rbp+57h+var_60]
0x18004de60  mov     [rsp+110h+var_80], rax
0x18004de68  lea     rax, [rbp+57h+SRWLock]
0x18004de6c  mov     [rsp+110h+var_88], rax
0x18004de74  lea     rax, [rbp+57h+var_58]
0x18004de78  mov     [rsp+110h+var_90], rax
0x18004de80  lea     rax, [rbp+57h+var_50]
0x18004de84  mov     [rsp+110h+var_98], rax
0x18004de89  lea     rax, [rbp+57h+arg_8]
0x18004de8d  mov     [rsp+110h+var_A0], rax
0x18004de92  lea     rax, [rbp+57h+var_48]
0x18004de96  mov     [rsp+110h+var_A8], rax
0x18004de9b  lea     rax, [rbp+57h+arg_10]
0x18004de9f  mov     [rsp+110h+var_B0], rax
0x18004dea4  lea     rax, [rbp+57h+var_40]
0x18004dea8  mov     [rsp+110h+var_B8], rax
0x18004dead  lea     rax, [rbp+57h+arg_18]
0x18004deb1  mov     [rsp+110h+var_C0], rax
0x18004deb6  lea     rax, [rbp+57h+var_38]
0x18004deba  mov     [rsp+110h+var_C8], rax
0x18004debf  lea     rax, [rbp+57h+var_70]
0x18004dec3  mov     [rsp+110h+var_D0], rax
0x18004dec8  lea     rax, [rbp+57h+var_30]
0x18004decc  mov     [rsp+110h+var_D8], rax
0x18004ded1  lea     rax, [rbp+57h+var_6C]
0x18004ded5  mov     [rsp+110h+var_E0], rax
0x18004deda  lea     rax, [rbp+57h+var_28]
0x18004dede  mov     [rsp+110h+var_E8], rax
0x18004dee3  lea     rax, [rbp+57h+var_20]
0x18004dee7  mov     [rsp+110h+var_F0], rax
0x18004deec  lea     rdx, byte_1800794EF
0x18004def3  mov     rcx, r9
0x18004def6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004defb  jmp     loc_18004DFA5
0x18004df00  lea     rdx, [rbp+57h+SRWLock]
0x18004df04  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004df09  mov     rax, [rbx+110h]
0x18004df10  mov     dword ptr [rax], 2
0x18004df16  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004df1a  test    rcx, rcx
0x18004df1d  jz      short loc_18004DF25
0x18004df1f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004df25  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18004df2a  mov     rdi, [rax+8]
0x18004df2e  mov     eax, [rdi]
0x18004df30  cmp     eax, 5
0x18004df33  jbe     short loc_18004DFA5
0x18004df35  mov     rdx, [rdi+18h]
0x18004df39  mov     rax, [rdi+10h]
0x18004df3d  mov     rcx, 400000000000h
0x18004df47  test    rcx, rax
0x18004df4a  jz      short loc_18004DFA5
0x18004df4c  mov     rax, rdx
0x18004df4f  and     rax, rcx
0x18004df52  cmp     rax, rdx
0x18004df55  jnz     short loc_18004DFA5
0x18004df57  call    cs:__imp_GetCurrentThreadId
0x18004df5d  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004df60  mov     r8, [rbx+110h]
0x18004df67  mov     eax, [r8+48h]
0x18004df6b  mov     [rbp+57h+arg_8], eax
0x18004df6e  mov     [rbp+57h+arg_10], 0
0x18004df76  add     r8, 8
0x18004df7a  lea     rax, [rbp+57h+SRWLock]
0x18004df7e  mov     [rsp+110h+var_E0], rax
0x18004df83  lea     rax, [rbp+57h+arg_8]
0x18004df87  mov     [rsp+110h+var_E8], rax
0x18004df8c  lea     rax, [rbp+57h+arg_10]
0x18004df90  mov     [rsp+110h+var_F0], rax
0x18004df95  lea     rdx, dword_18007949C
0x18004df9c  mov     rcx, rdi
0x18004df9f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004dfa4  nop
0x18004dfa5  lea     rcx, [rbx+120h]; this
0x18004dfac  cmp     dword ptr [rcx+18h], 0
0x18004dfb0  jz      short loc_18004DFB8
0x18004dfb2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004dfb7  nop
0x18004dfb8  add     rsp, 100h
0x18004dfbf  pop     rdi
0x18004dfc0  pop     rbx
0x18004dfc1  pop     rbp
0x18004dfc2  retn
```
