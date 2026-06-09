# StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StopActivity(void)

- ea: `0x18002c450`
- end: `0x18002c729`
- name: `?StopActivity@QueryStorageReserve@SRProvider@Internal@StorageReserveTelemetry@@MEAAXXZ`
- size: `729`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001ba0`
- `0x1800029d8`
- `0x180028738`
- `0x18002939c`
- `0x18002c450`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c4b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c654`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c4b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c66a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c66a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6c7`

## string_xrefs

- `0x18002c6e2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StopActivity(
        StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27[4]; // [rsp+120h] [rbp-20h] BYREF
  void *retaddr; // [rsp+148h] [rbp+8h]
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  __int64 v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  __int64 v32; // [rsp+168h] [rbp+28h] BYREF

  v27[1] = -2;
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v17 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      LODWORD(v30) = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      LODWORD(v31) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      LODWORD(v32) = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v5,
        (int)&byte_180044865,
        *((_QWORD *)this + 34) + 8,
        (__int64)v5,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        (const wchar_t **)&v25,
        (__int64)&v15,
        (const wchar_t **)&v24,
        (__int64)&v14,
        (const unsigned __int16 **)&v23,
        (__int64)&v13,
        (const wchar_t **)&v22,
        (__int64)&v32,
        (const wchar_t **)&v21,
        (const unsigned __int16 **)&v20,
        (__int64)&v31,
        (const wchar_t **)&v19,
        (const unsigned __int16 **)&v18,
        (__int64)&v30,
        (__int64)&SRWLock,
        (const wchar_t **)&v17);
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      LODWORD(v30) = *(_DWORD *)(v8 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (int)byte_180044811,
        v8 + 8,
        v9,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( *((_DWORD *)v10 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v10 + 6) = 0;
    v11 = *(__int64 **)v10;
    while ( 1 )
    {
      v12 = *v11;
      if ( !*v11 )
        break;
      if ( (char *)v12 == v10 )
      {
        *v11 = *((_QWORD *)v10 + 2);
        break;
      }
      v11 = (__int64 *)(v12 + 16);
      *(_QWORD *)v10 = v12 + 16;
    }
    *(_QWORD *)v10 = 0;
  }
}

```

## disassembly

```asm
0x18002c450  push    rbp
0x18002c452  push    rbx
0x18002c453  push    rdi
0x18002c454  lea     rbp, [rsp+10h]
0x18002c459  sub     rsp, 130h
0x18002c460  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18002c468  mov     rbx, rcx
0x18002c46b  mov     rdi, [rcx+110h]
0x18002c472  mov     eax, [rdi+48h]
0x18002c475  test    eax, eax
0x18002c477  jns     loc_18002C635
0x18002c47d  add     rdi, 50h ; 'P'
0x18002c481  cmp     eax, [rdi+8]
0x18002c484  jnz     loc_18002C635
0x18002c48a  test    rdi, rdi
0x18002c48d  jz      loc_18002C635
0x18002c493  lea     rdx, [rbp+SRWLock]
0x18002c497  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c49c  mov     rax, [rbx+110h]
0x18002c4a3  mov     dword ptr [rax], 2
0x18002c4a9  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c4ad  test    rcx, rcx
0x18002c4b0  jz      short loc_18002C4B9
0x18002c4b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c4b8  nop
0x18002c4b9  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002c4be  mov     r9, rax
0x18002c4c1  mov     ecx, [rax]
0x18002c4c3  cmp     ecx, 5
0x18002c4c6  jbe     loc_18002C6B7
0x18002c4cc  mov     rcx, [rdi+30h]
0x18002c4d0  mov     [rbp+var_70], rcx
0x18002c4d4  mov     ecx, [rdi+44h]
0x18002c4d7  mov     dword ptr [rbp+SRWLock], ecx
0x18002c4da  mov     ecx, [rdi+10h]
0x18002c4dd  mov     dword ptr [rbp+arg_8], ecx
0x18002c4e0  mov     rcx, [rdi+78h]
0x18002c4e4  mov     [rbp+var_68], rcx
0x18002c4e8  mov     rax, [rdi+70h]
0x18002c4ec  mov     [rbp+var_60], rax
0x18002c4f0  mov     eax, [rdi+68h]
0x18002c4f3  mov     dword ptr [rbp+arg_10], eax
0x18002c4f6  mov     rax, [rdi+60h]
0x18002c4fa  mov     [rbp+var_58], rax
0x18002c4fe  mov     rax, [rdi+58h]
0x18002c502  mov     [rbp+var_50], rax
0x18002c506  mov     eax, [rdi+50h]
0x18002c509  mov     dword ptr [rbp+arg_18], eax
0x18002c50c  mov     rax, [rdi+48h]
0x18002c510  mov     [rbp+var_48], rax
0x18002c514  mov     eax, [rdi+20h]
0x18002c517  mov     dword ptr [rbp+var_80], eax
0x18002c51a  mov     rax, [rdi+18h]
0x18002c51e  mov     [rbp+var_40], rax
0x18002c522  mov     eax, [rdi]
0x18002c524  mov     dword ptr [rbp+var_80+4], eax
0x18002c527  mov     rax, [rdi+80h]
0x18002c52e  mov     [rbp+var_38], rax
0x18002c532  mov     eax, [rdi+40h]
0x18002c535  mov     dword ptr [rbp+var_78], eax
0x18002c538  mov     rax, [rdi+38h]
0x18002c53c  mov     [rbp+var_30], rax
0x18002c540  mov     eax, [rdi+8]
0x18002c543  mov     dword ptr [rbp+var_78+4], eax
0x18002c546  mov     [rbp+var_28], 1000000h
0x18002c54e  mov     [rbp+var_20], 0
0x18002c556  mov     r8, [rbx+110h]
0x18002c55d  add     r8, 8; int
0x18002c561  lea     rax, [rbp+var_70]
0x18002c565  mov     [rsp+140h+var_90], rax; __int64
0x18002c56d  lea     rax, [rbp+SRWLock]
0x18002c571  mov     [rsp+140h+var_98], rax; __int64
0x18002c579  lea     rax, [rbp+arg_8]
0x18002c57d  mov     [rsp+140h+var_A0], rax; __int64
0x18002c585  lea     rax, [rbp+var_68]
0x18002c589  mov     [rsp+140h+var_A8], rax; __int64
0x18002c591  lea     rax, [rbp+var_60]
0x18002c595  mov     [rsp+140h+var_B0], rax; __int64
0x18002c59d  lea     rax, [rbp+arg_10]
0x18002c5a1  mov     [rsp+140h+var_B8], rax; __int64
0x18002c5a9  lea     rax, [rbp+var_58]
0x18002c5ad  mov     [rsp+140h+var_C0], rax; __int64
0x18002c5b5  lea     rax, [rbp+var_50]
0x18002c5b9  mov     [rsp+140h+var_C8], rax; __int64
0x18002c5be  lea     rax, [rbp+arg_18]
0x18002c5c2  mov     [rsp+140h+var_D0], rax; __int64
0x18002c5c7  lea     rax, [rbp+var_48]
0x18002c5cb  mov     [rsp+140h+var_D8], rax; __int64
0x18002c5d0  lea     rax, [rbp+var_80]
0x18002c5d4  mov     [rsp+140h+var_E0], rax; __int64
0x18002c5d9  lea     rax, [rbp+var_40]
0x18002c5dd  mov     [rsp+140h+var_E8], rax; __int64
0x18002c5e2  lea     rax, [rbp+var_80+4]
0x18002c5e6  mov     [rsp+140h+var_F0], rax; __int64
0x18002c5eb  lea     rax, [rbp+var_38]
0x18002c5ef  mov     [rsp+140h+var_F8], rax; __int64
0x18002c5f4  lea     rax, [rbp+var_78]
0x18002c5f8  mov     [rsp+140h+var_100], rax; __int64
0x18002c5fd  lea     rax, [rbp+var_30]
0x18002c601  mov     [rsp+140h+var_108], rax; __int64
0x18002c606  lea     rax, [rbp+var_78+4]
0x18002c60a  mov     [rsp+140h+var_110], rax; __int64
0x18002c60f  lea     rax, [rbp+var_28]
0x18002c613  mov     [rsp+140h+var_118], rax; __int64
0x18002c618  lea     rax, [rbp+var_20]
0x18002c61c  mov     [rsp+140h+var_120], rax; __int64
0x18002c621  lea     rdx, byte_180044865; int
0x18002c628  mov     rcx, r9; int
0x18002c62b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002c630  jmp     loc_18002C6B7
0x18002c635  lea     rdx, [rbp+SRWLock]
0x18002c639  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c63e  mov     rax, [rbx+110h]
0x18002c645  mov     dword ptr [rax], 2
0x18002c64b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c64f  test    rcx, rcx
0x18002c652  jz      short loc_18002C65B
0x18002c654  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c65a  nop
0x18002c65b  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002c660  mov     rdi, rax
0x18002c663  mov     ecx, [rax]
0x18002c665  cmp     ecx, 5
0x18002c668  jbe     short loc_18002C6B7
0x18002c66a  call    cs:__imp_GetCurrentThreadId
0x18002c670  mov     dword ptr [rbp+SRWLock], eax
0x18002c673  mov     r8, [rbx+110h]
0x18002c67a  mov     ecx, [r8+48h]
0x18002c67e  mov     dword ptr [rbp+arg_8], ecx
0x18002c681  mov     [rbp+arg_10], 0
0x18002c689  add     r8, 8
0x18002c68d  lea     rax, [rbp+SRWLock]
0x18002c691  mov     [rsp+140h+var_110], rax
0x18002c696  lea     rax, [rbp+arg_8]
0x18002c69a  mov     [rsp+140h+var_118], rax
0x18002c69f  lea     rax, [rbp+arg_10]
0x18002c6a3  mov     [rsp+140h+var_120], rax
0x18002c6a8  lea     rdx, byte_180044811
0x18002c6af  mov     rcx, rdi
0x18002c6b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c6b7  cmp     dword ptr [rbx+138h], 0
0x18002c6be  jz      short loc_18002C71E
0x18002c6c0  add     rbx, 120h
0x18002c6c7  call    cs:__imp_GetCurrentThreadId
0x18002c6cd  cmp     [rbx+18h], eax
0x18002c6d0  jz      short loc_18002C6EE
0x18002c6d2  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002c6d9  test    rax, rax
0x18002c6dc  jz      short loc_18002C6EE
0x18002c6de  mov     rdx, [rbp+8]
0x18002c6e2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002c6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6ee  mov     dword ptr [rbx+18h], 0
0x18002c6f5  mov     rcx, [rbx]
0x18002c6f8  jmp     short loc_18002C706
0x18002c6fa  cmp     rax, rbx
0x18002c6fd  jz      short loc_18002C710
0x18002c6ff  lea     rcx, [rax+10h]
0x18002c703  mov     [rbx], rcx
0x18002c706  mov     rax, [rcx]
0x18002c709  test    rax, rax
0x18002c70c  jnz     short loc_18002C6FA
0x18002c70e  jmp     short loc_18002C717
0x18002c710  mov     rax, [rbx+10h]
0x18002c714  mov     [rcx], rax
0x18002c717  mov     qword ptr [rbx], 0
0x18002c71e  add     rsp, 130h
0x18002c725  pop     rdi
0x18002c726  pop     rbx
0x18002c727  pop     rbp
0x18002c728  retn
```
