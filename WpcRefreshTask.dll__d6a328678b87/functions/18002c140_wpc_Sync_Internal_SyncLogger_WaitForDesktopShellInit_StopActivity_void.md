# wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit::StopActivity(void)

- ea: `0x18002c140`
- end: `0x18002c3ba`
- name: `?StopActivity@WaitForDesktopShellInit@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c140`
- `0x18002c3c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c34d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c34d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c19a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c338`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c19a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c338`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit::StopActivity(
        wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = wpc::Sync::Internal::SyncLogger::Provider();
    if ( *(_DWORD *)v5 > 4u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&unk_1800D4DD0,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = wpc::Sync::Internal::SyncLogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&unk_1800D4D78,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002c140  push    rbp
0x18002c142  push    rbx
0x18002c143  push    rdi
0x18002c144  lea     rbp, [rsp+10h]
0x18002c149  sub     rsp, 130h
0x18002c150  mov     rbx, rcx
0x18002c153  mov     rdi, [rcx+110h]
0x18002c15a  mov     eax, [rdi+48h]
0x18002c15d  test    eax, eax
0x18002c15f  jns     loc_18002C319
0x18002c165  add     rdi, 50h ; 'P'
0x18002c169  cmp     eax, [rdi+8]
0x18002c16c  jnz     loc_18002C319
0x18002c172  test    rdi, rdi
0x18002c175  jz      loc_18002C319
0x18002c17b  lea     rdx, [rbp+SRWLock]
0x18002c17f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c184  mov     rax, [rbx+110h]
0x18002c18b  mov     dword ptr [rax], 2
0x18002c191  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c195  test    rcx, rcx
0x18002c198  jz      short loc_18002C1A0
0x18002c19a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c1a0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x18002c1a5  mov     r9, rax
0x18002c1a8  mov     ecx, [rax]
0x18002c1aa  cmp     ecx, 4
0x18002c1ad  jbe     loc_18002C39C
0x18002c1b3  mov     rcx, [rdi+30h]
0x18002c1b7  mov     [rbp+var_70], rcx
0x18002c1bb  mov     ecx, [rdi+44h]
0x18002c1be  mov     dword ptr [rbp+SRWLock], ecx
0x18002c1c1  mov     ecx, [rdi+10h]
0x18002c1c4  mov     [rbp+arg_8], ecx
0x18002c1c7  mov     rcx, [rdi+78h]
0x18002c1cb  mov     [rbp+var_68], rcx
0x18002c1cf  mov     rax, [rdi+70h]
0x18002c1d3  mov     [rbp+var_60], rax
0x18002c1d7  mov     eax, [rdi+68h]
0x18002c1da  mov     dword ptr [rbp+arg_10], eax
0x18002c1dd  mov     rax, [rdi+60h]
0x18002c1e1  mov     [rbp+var_58], rax
0x18002c1e5  mov     rax, [rdi+58h]
0x18002c1e9  mov     [rbp+var_50], rax
0x18002c1ed  mov     eax, [rdi+50h]
0x18002c1f0  mov     [rbp+arg_18], eax
0x18002c1f3  mov     rax, [rdi+48h]
0x18002c1f7  mov     [rbp+var_48], rax
0x18002c1fb  mov     eax, [rdi+20h]
0x18002c1fe  mov     [rbp+var_80], eax
0x18002c201  mov     rax, [rdi+18h]
0x18002c205  mov     [rbp+var_40], rax
0x18002c209  mov     eax, [rdi]
0x18002c20b  mov     [rbp+var_7C], eax
0x18002c20e  mov     rax, [rdi+80h]
0x18002c215  mov     [rbp+var_38], rax
0x18002c219  mov     eax, [rdi+40h]
0x18002c21c  mov     [rbp+var_78], eax
0x18002c21f  mov     rax, [rdi+38h]
0x18002c223  mov     [rbp+var_30], rax
0x18002c227  mov     eax, [rdi+8]
0x18002c22a  mov     [rbp+var_74], eax
0x18002c22d  mov     eax, 1000000h
0x18002c232  mov     [rbp+var_28], rax
0x18002c236  mov     [rbp+var_20], rax
0x18002c23a  mov     r8, [rbx+110h]
0x18002c241  add     r8, 8
0x18002c245  lea     rax, [rbp+var_70]
0x18002c249  mov     [rsp+140h+var_90], rax
0x18002c251  lea     rax, [rbp+SRWLock]
0x18002c255  mov     [rsp+140h+var_98], rax
0x18002c25d  lea     rax, [rbp+arg_8]
0x18002c261  mov     [rsp+140h+var_A0], rax
0x18002c269  lea     rax, [rbp+var_68]
0x18002c26d  mov     [rsp+140h+var_A8], rax
0x18002c275  lea     rax, [rbp+var_60]
0x18002c279  mov     [rsp+140h+var_B0], rax
0x18002c281  lea     rax, [rbp+arg_10]
0x18002c285  mov     [rsp+140h+var_B8], rax
0x18002c28d  lea     rax, [rbp+var_58]
0x18002c291  mov     [rsp+140h+var_C0], rax
0x18002c299  lea     rax, [rbp+var_50]
0x18002c29d  mov     [rsp+140h+var_C8], rax
0x18002c2a2  lea     rax, [rbp+arg_18]
0x18002c2a6  mov     [rsp+140h+var_D0], rax
0x18002c2ab  lea     rax, [rbp+var_48]
0x18002c2af  mov     [rsp+140h+var_D8], rax
0x18002c2b4  lea     rax, [rbp+var_80]
0x18002c2b8  mov     [rsp+140h+var_E0], rax
0x18002c2bd  lea     rax, [rbp+var_40]
0x18002c2c1  mov     [rsp+140h+var_E8], rax
0x18002c2c6  lea     rax, [rbp+var_7C]
0x18002c2ca  mov     [rsp+140h+var_F0], rax
0x18002c2cf  lea     rax, [rbp+var_38]
0x18002c2d3  mov     [rsp+140h+var_F8], rax
0x18002c2d8  lea     rax, [rbp+var_78]
0x18002c2dc  mov     [rsp+140h+var_100], rax
0x18002c2e1  lea     rax, [rbp+var_30]
0x18002c2e5  mov     [rsp+140h+var_108], rax
0x18002c2ea  lea     rax, [rbp+var_74]
0x18002c2ee  mov     [rsp+140h+var_110], rax
0x18002c2f3  lea     rax, [rbp+var_28]
0x18002c2f7  mov     [rsp+140h+var_118], rax
0x18002c2fc  lea     rax, [rbp+var_20]
0x18002c300  mov     [rsp+140h+var_120], rax
0x18002c305  lea     rdx, unk_1800D4DD0
0x18002c30c  mov     rcx, r9
0x18002c30f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002c314  jmp     loc_18002C39C
0x18002c319  lea     rdx, [rbp+SRWLock]
0x18002c31d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c322  mov     rax, [rbx+110h]
0x18002c329  mov     dword ptr [rax], 2
0x18002c32f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c333  test    rcx, rcx
0x18002c336  jz      short loc_18002C33E
0x18002c338  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c33e  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x18002c343  mov     rdi, rax
0x18002c346  mov     ecx, [rax]
0x18002c348  cmp     ecx, 4
0x18002c34b  jbe     short loc_18002C39C
0x18002c34d  call    cs:__imp_GetCurrentThreadId
0x18002c353  mov     dword ptr [rbp+SRWLock], eax
0x18002c356  mov     r8, [rbx+110h]
0x18002c35d  mov     ecx, [r8+48h]
0x18002c361  mov     [rbp+arg_8], ecx
0x18002c364  mov     eax, 1000000h
0x18002c369  mov     [rbp+arg_10], rax
0x18002c36d  add     r8, 8
0x18002c371  lea     rax, [rbp+SRWLock]
0x18002c375  mov     [rsp+140h+var_110], rax
0x18002c37a  lea     rax, [rbp+arg_8]
0x18002c37e  mov     [rsp+140h+var_118], rax
0x18002c383  lea     rax, [rbp+arg_10]
0x18002c387  mov     [rsp+140h+var_120], rax
0x18002c38c  lea     rdx, unk_1800D4D78
0x18002c393  mov     rcx, rdi
0x18002c396  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c39b  nop
0x18002c39c  lea     rcx, [rbx+120h]; this
0x18002c3a3  cmp     dword ptr [rcx+18h], 0
0x18002c3a7  jz      short loc_18002C3AF
0x18002c3a9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002c3ae  nop
0x18002c3af  add     rsp, 130h
0x18002c3b6  pop     rdi
0x18002c3b7  pop     rbx
0x18002c3b8  pop     rbp
0x18002c3b9  retn
```
