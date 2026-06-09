# LanguageOverlayTraceProvider::ServiceStartActivity::StopActivity(void)

- ea: `0x180010890`
- end: `0x180010b23`
- name: `?StopActivity@ServiceStartActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::ServiceStartActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010890`
- `0x180010dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800108ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800108ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanguageOverlayTraceProvider::ServiceStartActivity::StopActivity(
        LanguageOverlayTraceProvider::ServiceStartActivity *this)
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
        (__int64)&unk_180076550,
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
        (__int64)byte_1800764FB,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::ServiceStartActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010890  push    rbp
0x180010892  push    rbx
0x180010893  push    rdi
0x180010894  lea     rbp, [rsp-47h]
0x180010899  sub     rsp, 100h
0x1800108a0  mov     rbx, rcx
0x1800108a3  mov     rdi, [rcx+110h]
0x1800108aa  mov     eax, [rdi+48h]
0x1800108ad  test    eax, eax
0x1800108af  jns     loc_180010A60
0x1800108b5  add     rdi, 50h ; 'P'
0x1800108b9  cmp     eax, [rdi+8]
0x1800108bc  jnz     loc_180010A60
0x1800108c2  test    rdi, rdi
0x1800108c5  jz      loc_180010A60
0x1800108cb  lea     rdx, [rbp+57h+SRWLock]
0x1800108cf  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800108d4  mov     rax, [rbx+110h]
0x1800108db  mov     dword ptr [rax], 2
0x1800108e1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800108e5  test    rcx, rcx
0x1800108e8  jz      short loc_1800108F0
0x1800108ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800108f0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800108f5  mov     r9, [rax+8]
0x1800108f9  mov     eax, [r9]
0x1800108fc  cmp     eax, 5
0x1800108ff  jbe     loc_180010B05
0x180010905  mov     rdx, [r9+18h]
0x180010909  mov     rax, [r9+10h]
0x18001090d  mov     rcx, 200000000000h
0x180010917  test    rcx, rax
0x18001091a  jz      loc_180010B05
0x180010920  mov     rax, rdx
0x180010923  and     rax, rcx
0x180010926  cmp     rax, rdx
0x180010929  jnz     loc_180010B05
0x18001092f  mov     rax, [rdi+78h]
0x180010933  mov     [rbp+57h+var_68], rax
0x180010937  mov     rax, [rdi+70h]
0x18001093b  mov     [rbp+57h+var_60], rax
0x18001093f  mov     eax, [rdi+68h]
0x180010942  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010945  mov     rax, [rdi+60h]
0x180010949  mov     [rbp+57h+var_58], rax
0x18001094d  mov     rax, [rdi+58h]
0x180010951  mov     [rbp+57h+var_50], rax
0x180010955  mov     eax, [rdi+50h]
0x180010958  mov     [rbp+57h+arg_8], eax
0x18001095b  mov     rax, [rdi+48h]
0x18001095f  mov     [rbp+57h+var_48], rax
0x180010963  mov     eax, [rdi+20h]
0x180010966  mov     dword ptr [rbp+57h+arg_10], eax
0x180010969  mov     rax, [rdi+18h]
0x18001096d  mov     [rbp+57h+var_40], rax
0x180010971  mov     eax, [rdi]
0x180010973  mov     [rbp+57h+arg_18], eax
0x180010976  mov     rax, [rdi+80h]
0x18001097d  mov     [rbp+57h+var_38], rax
0x180010981  mov     eax, [rdi+40h]
0x180010984  mov     [rbp+57h+var_70], eax
0x180010987  mov     rax, [rdi+38h]
0x18001098b  mov     [rbp+57h+var_30], rax
0x18001098f  mov     eax, [rdi+8]
0x180010992  mov     [rbp+57h+var_6C], eax
0x180010995  mov     [rbp+57h+var_28], 1000000h
0x18001099d  mov     [rbp+57h+var_20], 0
0x1800109a5  mov     r8, [rbx+110h]
0x1800109ac  add     r8, 8
0x1800109b0  lea     rax, [rbp+57h+var_68]
0x1800109b4  mov     [rsp+110h+var_78], rax
0x1800109bc  lea     rax, [rbp+57h+var_60]
0x1800109c0  mov     [rsp+110h+var_80], rax
0x1800109c8  lea     rax, [rbp+57h+SRWLock]
0x1800109cc  mov     [rsp+110h+var_88], rax
0x1800109d4  lea     rax, [rbp+57h+var_58]
0x1800109d8  mov     [rsp+110h+var_90], rax
0x1800109e0  lea     rax, [rbp+57h+var_50]
0x1800109e4  mov     [rsp+110h+var_98], rax
0x1800109e9  lea     rax, [rbp+57h+arg_8]
0x1800109ed  mov     [rsp+110h+var_A0], rax
0x1800109f2  lea     rax, [rbp+57h+var_48]
0x1800109f6  mov     [rsp+110h+var_A8], rax
0x1800109fb  lea     rax, [rbp+57h+arg_10]
0x1800109ff  mov     [rsp+110h+var_B0], rax
0x180010a04  lea     rax, [rbp+57h+var_40]
0x180010a08  mov     [rsp+110h+var_B8], rax
0x180010a0d  lea     rax, [rbp+57h+arg_18]
0x180010a11  mov     [rsp+110h+var_C0], rax
0x180010a16  lea     rax, [rbp+57h+var_38]
0x180010a1a  mov     [rsp+110h+var_C8], rax
0x180010a1f  lea     rax, [rbp+57h+var_70]
0x180010a23  mov     [rsp+110h+var_D0], rax
0x180010a28  lea     rax, [rbp+57h+var_30]
0x180010a2c  mov     [rsp+110h+var_D8], rax
0x180010a31  lea     rax, [rbp+57h+var_6C]
0x180010a35  mov     [rsp+110h+var_E0], rax
0x180010a3a  lea     rax, [rbp+57h+var_28]
0x180010a3e  mov     [rsp+110h+var_E8], rax
0x180010a43  lea     rax, [rbp+57h+var_20]
0x180010a47  mov     [rsp+110h+var_F0], rax
0x180010a4c  lea     rdx, unk_180076550
0x180010a53  mov     rcx, r9
0x180010a56  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010a5b  jmp     loc_180010B05
0x180010a60  lea     rdx, [rbp+57h+SRWLock]
0x180010a64  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010a69  mov     rax, [rbx+110h]
0x180010a70  mov     dword ptr [rax], 2
0x180010a76  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180010a7a  test    rcx, rcx
0x180010a7d  jz      short loc_180010A85
0x180010a7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180010a85  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180010a8a  mov     rdi, [rax+8]
0x180010a8e  mov     eax, [rdi]
0x180010a90  cmp     eax, 5
0x180010a93  jbe     short loc_180010B05
0x180010a95  mov     rdx, [rdi+18h]
0x180010a99  mov     rax, [rdi+10h]
0x180010a9d  mov     rcx, 200000000000h
0x180010aa7  test    rcx, rax
0x180010aaa  jz      short loc_180010B05
0x180010aac  mov     rax, rdx
0x180010aaf  and     rax, rcx
0x180010ab2  cmp     rax, rdx
0x180010ab5  jnz     short loc_180010B05
0x180010ab7  call    cs:__imp_GetCurrentThreadId
0x180010abd  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010ac0  mov     r8, [rbx+110h]
0x180010ac7  mov     eax, [r8+48h]
0x180010acb  mov     [rbp+57h+arg_8], eax
0x180010ace  mov     [rbp+57h+arg_10], 0
0x180010ad6  add     r8, 8
0x180010ada  lea     rax, [rbp+57h+SRWLock]
0x180010ade  mov     [rsp+110h+var_E0], rax
0x180010ae3  lea     rax, [rbp+57h+arg_8]
0x180010ae7  mov     [rsp+110h+var_E8], rax
0x180010aec  lea     rax, [rbp+57h+arg_10]
0x180010af0  mov     [rsp+110h+var_F0], rax
0x180010af5  lea     rdx, byte_1800764FB
0x180010afc  mov     rcx, rdi
0x180010aff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010b04  nop
0x180010b05  lea     rcx, [rbx+120h]; this
0x180010b0c  cmp     dword ptr [rcx+18h], 0
0x180010b10  jz      short loc_180010B18
0x180010b12  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010b17  nop
0x180010b18  add     rsp, 100h
0x180010b1f  pop     rdi
0x180010b20  pop     rbx
0x180010b21  pop     rbp
0x180010b22  retn
```
