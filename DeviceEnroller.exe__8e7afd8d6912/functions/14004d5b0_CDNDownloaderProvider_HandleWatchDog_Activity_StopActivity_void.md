# CDNDownloaderProvider::HandleWatchDog_Activity::StopActivity(void)

- ea: `0x14004d5b0`
- end: `0x14004d840`
- name: `?StopActivity@HandleWatchDog_Activity@CDNDownloaderProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(CDNDownloaderProvider::HandleWatchDog_Activity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14004bf84`
- `0x14004d5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004d60a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004d79d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004d60a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004d79d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004d7d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004d7d4`

## pseudocode

```c
void __fastcall CDNDownloaderProvider::HandleWatchDog_Activity::StopActivity(
        CDNDownloaderProvider::HandleWatchDog_Activity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const OLECHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v16; // [rsp+B0h] [rbp-9h] BYREF
  const OLECHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v18; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const OLECHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = CDNDownloaderProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v15 = (const OLECHAR *)*((_QWORD *)v4 + 15);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = (const OLECHAR *)*((_QWORD *)v4 + 12);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = (const OLECHAR *)*((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&byte_1400712DF,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v28,
          &v20,
          (__int64)&v27,
          &v19,
          (__int64)&v26,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v16,
          &v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = CDNDownloaderProvider::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)&byte_140071287,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CDNDownloaderProvider::HandleWatchDog_Activity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14004d5b0  push    rbp
0x14004d5b2  push    rbx
0x14004d5b3  push    rdi
0x14004d5b4  lea     rbp, [rsp-47h]
0x14004d5b9  sub     rsp, 100h
0x14004d5c0  mov     rbx, rcx
0x14004d5c3  mov     rdi, [rcx+110h]
0x14004d5ca  mov     eax, [rdi+48h]
0x14004d5cd  test    eax, eax
0x14004d5cf  jns     loc_14004D77E
0x14004d5d5  add     rdi, 50h ; 'P'
0x14004d5d9  cmp     eax, [rdi+8]
0x14004d5dc  jnz     loc_14004D77E
0x14004d5e2  test    rdi, rdi
0x14004d5e5  jz      loc_14004D77E
0x14004d5eb  lea     rdx, [rbp+57h+SRWLock]
0x14004d5ef  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004d5f4  mov     rax, [rbx+110h]
0x14004d5fb  mov     dword ptr [rax], 2
0x14004d601  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004d605  test    rcx, rcx
0x14004d608  jz      short loc_14004D610
0x14004d60a  call    cs:__imp_ReleaseSRWLockExclusive
0x14004d610  call    ?Provider@CDNDownloaderProvider@@SAPEBU_tlgProvider_t@@XZ; CDNDownloaderProvider::Provider(void)
0x14004d615  mov     r9, rax
0x14004d618  mov     ecx, [rax]
0x14004d61a  cmp     ecx, 5
0x14004d61d  jbe     loc_14004D822
0x14004d623  mov     rax, [rax+18h]
0x14004d627  mov     rcx, [r9+10h]
0x14004d62b  mov     rdx, 400000000000h
0x14004d635  test    rdx, rcx
0x14004d638  jz      loc_14004D822
0x14004d63e  mov     rcx, rax
0x14004d641  and     rcx, rdx
0x14004d644  cmp     rcx, rax
0x14004d647  jnz     loc_14004D822
0x14004d64d  mov     rax, [rdi+78h]
0x14004d651  mov     [rbp+57h+var_68], rax
0x14004d655  mov     rax, [rdi+70h]
0x14004d659  mov     [rbp+57h+var_60], rax
0x14004d65d  mov     eax, [rdi+68h]
0x14004d660  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004d663  mov     rax, [rdi+60h]
0x14004d667  mov     [rbp+57h+var_58], rax
0x14004d66b  mov     rax, [rdi+58h]
0x14004d66f  mov     [rbp+57h+var_50], rax
0x14004d673  mov     eax, [rdi+50h]
0x14004d676  mov     [rbp+57h+arg_8], eax
0x14004d679  mov     rax, [rdi+48h]
0x14004d67d  mov     [rbp+57h+var_48], rax
0x14004d681  mov     eax, [rdi+20h]
0x14004d684  mov     dword ptr [rbp+57h+arg_10], eax
0x14004d687  mov     rax, [rdi+18h]
0x14004d68b  mov     [rbp+57h+var_40], rax
0x14004d68f  mov     eax, [rdi]
0x14004d691  mov     [rbp+57h+arg_18], eax
0x14004d694  mov     rax, [rdi+80h]
0x14004d69b  mov     [rbp+57h+var_38], rax
0x14004d69f  mov     eax, [rdi+40h]
0x14004d6a2  mov     [rbp+57h+var_70], eax
0x14004d6a5  mov     rax, [rdi+38h]
0x14004d6a9  mov     [rbp+57h+var_30], rax
0x14004d6ad  mov     eax, [rdi+8]
0x14004d6b0  mov     [rbp+57h+var_6C], eax
0x14004d6b3  mov     [rbp+57h+var_28], 1000000h
0x14004d6bb  mov     [rbp+57h+var_20], 0
0x14004d6c3  mov     r8, [rbx+110h]
0x14004d6ca  add     r8, 8
0x14004d6ce  lea     rax, [rbp+57h+var_68]
0x14004d6d2  mov     [rsp+110h+var_78], rax
0x14004d6da  lea     rax, [rbp+57h+var_60]
0x14004d6de  mov     [rsp+110h+var_80], rax
0x14004d6e6  lea     rax, [rbp+57h+SRWLock]
0x14004d6ea  mov     [rsp+110h+var_88], rax
0x14004d6f2  lea     rax, [rbp+57h+var_58]
0x14004d6f6  mov     [rsp+110h+var_90], rax
0x14004d6fe  lea     rax, [rbp+57h+var_50]
0x14004d702  mov     [rsp+110h+var_98], rax
0x14004d707  lea     rax, [rbp+57h+arg_8]
0x14004d70b  mov     [rsp+110h+var_A0], rax
0x14004d710  lea     rax, [rbp+57h+var_48]
0x14004d714  mov     [rsp+110h+var_A8], rax
0x14004d719  lea     rax, [rbp+57h+arg_10]
0x14004d71d  mov     [rsp+110h+var_B0], rax
0x14004d722  lea     rax, [rbp+57h+var_40]
0x14004d726  mov     [rsp+110h+var_B8], rax
0x14004d72b  lea     rax, [rbp+57h+arg_18]
0x14004d72f  mov     [rsp+110h+var_C0], rax
0x14004d734  lea     rax, [rbp+57h+var_38]
0x14004d738  mov     [rsp+110h+var_C8], rax
0x14004d73d  lea     rax, [rbp+57h+var_70]
0x14004d741  mov     [rsp+110h+var_D0], rax
0x14004d746  lea     rax, [rbp+57h+var_30]
0x14004d74a  mov     [rsp+110h+var_D8], rax
0x14004d74f  lea     rax, [rbp+57h+var_6C]
0x14004d753  mov     [rsp+110h+var_E0], rax
0x14004d758  lea     rax, [rbp+57h+var_28]
0x14004d75c  mov     [rsp+110h+var_E8], rax
0x14004d761  lea     rax, [rbp+57h+var_20]
0x14004d765  mov     [rsp+110h+var_F0], rax
0x14004d76a  lea     rdx, byte_1400712DF
0x14004d771  mov     rcx, r9
0x14004d774  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14004d779  jmp     loc_14004D822
0x14004d77e  lea     rdx, [rbp+57h+SRWLock]
0x14004d782  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004d787  mov     rax, [rbx+110h]
0x14004d78e  mov     dword ptr [rax], 2
0x14004d794  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004d798  test    rcx, rcx
0x14004d79b  jz      short loc_14004D7A3
0x14004d79d  call    cs:__imp_ReleaseSRWLockExclusive
0x14004d7a3  call    ?Provider@CDNDownloaderProvider@@SAPEBU_tlgProvider_t@@XZ; CDNDownloaderProvider::Provider(void)
0x14004d7a8  mov     rdi, rax
0x14004d7ab  mov     ecx, [rax]
0x14004d7ad  cmp     ecx, 5
0x14004d7b0  jbe     short loc_14004D822
0x14004d7b2  mov     rax, [rax+18h]
0x14004d7b6  mov     rcx, [rdi+10h]
0x14004d7ba  mov     rdx, 400000000000h
0x14004d7c4  test    rdx, rcx
0x14004d7c7  jz      short loc_14004D822
0x14004d7c9  mov     rcx, rax
0x14004d7cc  and     rcx, rdx
0x14004d7cf  cmp     rcx, rax
0x14004d7d2  jnz     short loc_14004D822
0x14004d7d4  call    cs:__imp_GetCurrentThreadId
0x14004d7da  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004d7dd  mov     r8, [rbx+110h]
0x14004d7e4  mov     eax, [r8+48h]
0x14004d7e8  mov     [rbp+57h+arg_8], eax
0x14004d7eb  mov     [rbp+57h+arg_10], 0
0x14004d7f3  add     r8, 8
0x14004d7f7  lea     rax, [rbp+57h+SRWLock]
0x14004d7fb  mov     [rsp+110h+var_E0], rax
0x14004d800  lea     rax, [rbp+57h+arg_8]
0x14004d804  mov     [rsp+110h+var_E8], rax
0x14004d809  lea     rax, [rbp+57h+arg_10]
0x14004d80d  mov     [rsp+110h+var_F0], rax
0x14004d812  lea     rdx, byte_140071287
0x14004d819  mov     rcx, rdi
0x14004d81c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004d821  nop
0x14004d822  lea     rcx, [rbx+120h]; this
0x14004d829  cmp     dword ptr [rcx+18h], 0
0x14004d82d  jz      short loc_14004D835
0x14004d82f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14004d834  nop
0x14004d835  add     rsp, 100h
0x14004d83c  pop     rdi
0x14004d83d  pop     rbx
0x14004d83e  pop     rbp
0x14004d83f  retn
```
