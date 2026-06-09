# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StopActivity(void)

- ea: `0x1800138c0`
- end: `0x180013b2d`
- name: `?StopActivity@WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@MEAAXXZ`
- size: `621`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x180010794`
- `0x180010810`
- `0x180010d90`
- `0x1800138c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001391a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001391a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ab8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013acd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013acd`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StopActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v19; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v20; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v22; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v24; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v25; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v32) = v4[26];
      v8 = *((_QWORD *)this + 34);
      v22 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v18 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v19 = v7;
      LODWORD(SRWLock) = v4[17];
      v31 = v4[4];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)byte_18003CEDD,
        v8 + 8,
        (__int64)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v33,
        &v23,
        &v22,
        (__int64)&v32,
        &v21,
        &v20,
        (__int64)&v31,
        (__int64)&SRWLock,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v13 = *(_DWORD *)(v12 + 72);
      v32 = 0x1000000;
      v31 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&dword_18003CBCC,
        v12 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800138c0  push    rbp
0x1800138c2  push    rbx
0x1800138c3  push    rdi
0x1800138c4  lea     rbp, [rsp+10h]
0x1800138c9  sub     rsp, 130h
0x1800138d0  mov     rdi, [rcx+110h]
0x1800138d7  mov     rbx, rcx
0x1800138da  mov     eax, [rdi+48h]
0x1800138dd  test    eax, eax
0x1800138df  jns     loc_180013A99
0x1800138e5  add     rdi, 50h ; 'P'
0x1800138e9  cmp     eax, [rdi+8]
0x1800138ec  jnz     loc_180013A99
0x1800138f2  test    rdi, rdi
0x1800138f5  jz      loc_180013A99
0x1800138fb  lea     rdx, [rbp+SRWLock]
0x1800138ff  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013904  mov     rax, [rbx+110h]
0x18001390b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001390f  mov     dword ptr [rax], 2
0x180013915  test    rcx, rcx
0x180013918  jz      short loc_180013920
0x18001391a  call    cs:__imp_ReleaseSRWLockExclusive
0x180013920  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180013925  mov     r9, rax
0x180013928  mov     ecx, [rax]
0x18001392a  cmp     ecx, 4
0x18001392d  jbe     loc_180013B1B
0x180013933  mov     rax, [rdi+70h]
0x180013937  lea     rdx, byte_18003CEDD
0x18001393e  mov     rcx, [rdi+30h]
0x180013942  mov     [rbp+var_60], rax
0x180013946  mov     eax, [rdi+68h]
0x180013949  mov     dword ptr [rbp+arg_10], eax
0x18001394c  mov     rax, [rdi+60h]
0x180013950  mov     r8, [rbx+110h]
0x180013957  mov     [rbp+var_58], rax
0x18001395b  add     r8, 8
0x18001395f  mov     rax, [rdi+58h]
0x180013963  mov     [rbp+var_50], rax
0x180013967  mov     eax, [rdi+50h]
0x18001396a  mov     [rbp+arg_18], eax
0x18001396d  mov     rax, [rdi+48h]
0x180013971  mov     [rbp+var_48], rax
0x180013975  mov     eax, [rdi+20h]
0x180013978  mov     [rbp+var_80], eax
0x18001397b  mov     rax, [rdi+18h]
0x18001397f  mov     [rbp+var_40], rax
0x180013983  mov     eax, [rdi]
0x180013985  mov     [rbp+var_7C], eax
0x180013988  mov     rax, [rdi+80h]
0x18001398f  mov     [rbp+var_38], rax
0x180013993  mov     eax, [rdi+40h]
0x180013996  mov     [rbp+var_78], eax
0x180013999  mov     rax, [rdi+38h]
0x18001399d  mov     [rbp+var_30], rax
0x1800139a1  mov     eax, [rdi+8]
0x1800139a4  mov     [rbp+var_74], eax
0x1800139a7  mov     eax, 1000000h
0x1800139ac  mov     [rbp+var_28], rax
0x1800139b0  mov     [rbp+var_20], rax
0x1800139b4  lea     rax, [rbp+var_70]
0x1800139b8  mov     [rsp+140h+var_90], rax
0x1800139c0  lea     rax, [rbp+SRWLock]
0x1800139c4  mov     [rsp+140h+var_98], rax
0x1800139cc  lea     rax, [rbp+arg_8]
0x1800139d0  mov     [rsp+140h+var_A0], rax
0x1800139d8  lea     rax, [rbp+var_68]
0x1800139dc  mov     [rsp+140h+var_A8], rax
0x1800139e4  lea     rax, [rbp+var_60]
0x1800139e8  mov     [rsp+140h+var_B0], rax
0x1800139f0  lea     rax, [rbp+arg_10]
0x1800139f4  mov     [rsp+140h+var_B8], rax
0x1800139fc  lea     rax, [rbp+var_58]
0x180013a00  mov     [rsp+140h+var_C0], rax
0x180013a08  lea     rax, [rbp+var_50]
0x180013a0c  mov     [rsp+140h+var_C8], rax
0x180013a11  lea     rax, [rbp+arg_18]
0x180013a15  mov     [rsp+140h+var_D0], rax
0x180013a1a  lea     rax, [rbp+var_48]
0x180013a1e  mov     [rsp+140h+var_D8], rax
0x180013a23  lea     rax, [rbp+var_80]
0x180013a27  mov     [rsp+140h+var_E0], rax
0x180013a2c  lea     rax, [rbp+var_40]
0x180013a30  mov     [rsp+140h+var_E8], rax
0x180013a35  lea     rax, [rbp+var_7C]
0x180013a39  mov     [rsp+140h+var_F0], rax
0x180013a3e  lea     rax, [rbp+var_38]
0x180013a42  mov     [rsp+140h+var_F8], rax
0x180013a47  lea     rax, [rbp+var_78]
0x180013a4b  mov     [rsp+140h+var_100], rax
0x180013a50  lea     rax, [rbp+var_30]
0x180013a54  mov     [rsp+140h+var_108], rax
0x180013a59  lea     rax, [rbp+var_74]
0x180013a5d  mov     [rbp+var_70], rcx
0x180013a61  mov     ecx, [rdi+44h]
0x180013a64  mov     [rsp+140h+var_110], rax
0x180013a69  lea     rax, [rbp+var_28]
0x180013a6d  mov     dword ptr [rbp+SRWLock], ecx
0x180013a70  mov     ecx, [rdi+10h]
0x180013a73  mov     [rbp+arg_8], ecx
0x180013a76  mov     rcx, [rdi+78h]
0x180013a7a  mov     [rsp+140h+var_118], rax
0x180013a7f  lea     rax, [rbp+var_20]
0x180013a83  mov     [rbp+var_68], rcx
0x180013a87  mov     rcx, r9
0x180013a8a  mov     [rsp+140h+var_120], rax
0x180013a8f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180013a94  jmp     loc_180013B1B
0x180013a99  lea     rdx, [rbp+SRWLock]
0x180013a9d  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013aa2  mov     rax, [rbx+110h]
0x180013aa9  mov     rcx, [rbp+SRWLock]; SRWLock
0x180013aad  mov     dword ptr [rax], 2
0x180013ab3  test    rcx, rcx
0x180013ab6  jz      short loc_180013ABE
0x180013ab8  call    cs:__imp_ReleaseSRWLockExclusive
0x180013abe  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180013ac3  mov     rdi, rax
0x180013ac6  mov     ecx, [rax]
0x180013ac8  cmp     ecx, 4
0x180013acb  jbe     short loc_180013B1B
0x180013acd  call    cs:__imp_GetCurrentThreadId
0x180013ad3  mov     r8, [rbx+110h]
0x180013ada  lea     rdx, dword_18003CBCC
0x180013ae1  mov     dword ptr [rbp+SRWLock], eax
0x180013ae4  mov     eax, 1000000h
0x180013ae9  mov     ecx, [r8+48h]
0x180013aed  add     r8, 8
0x180013af1  mov     [rbp+arg_10], rax
0x180013af5  lea     rax, [rbp+SRWLock]
0x180013af9  mov     [rsp+140h+var_110], rax
0x180013afe  lea     rax, [rbp+arg_8]
0x180013b02  mov     [rsp+140h+var_118], rax
0x180013b07  lea     rax, [rbp+arg_10]
0x180013b0b  mov     [rbp+arg_8], ecx
0x180013b0e  mov     rcx, rdi
0x180013b11  mov     [rsp+140h+var_120], rax
0x180013b16  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013b1b  mov     rcx, rbx
0x180013b1e  add     rsp, 130h
0x180013b25  pop     rdi
0x180013b26  pop     rbx
0x180013b27  pop     rbp
0x180013b28  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
