# StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StopActivity(void)

- ea: `0x18002bc70`
- end: `0x18002befb`
- name: `?StopActivity@DeleteReserveAreaContent@SRProvider@Internal@StorageReserveTelemetry@@MEAAXXZ`
- size: `651`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800018ec`
- `0x1800029d8`
- `0x180028494`
- `0x180028738`
- `0x18002939c`
- `0x18002bc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bcd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bcd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be9b`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StopActivity(
        StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *this)
{
  __int64 v2; // rdi
  int v3; // eax
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  __int64 v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v24[1] = -2;
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = v2 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v15 = *(_QWORD *)(v4 + 120);
        v16 = *(_QWORD *)(v4 + 112);
        LODWORD(SRWLock) = *(_DWORD *)(v4 + 104);
        v17 = *(_QWORD *)(v4 + 96);
        v18 = *(_QWORD *)(v4 + 88);
        LODWORD(v26) = *(_DWORD *)(v4 + 80);
        v19 = *(_QWORD *)(v4 + 72);
        LODWORD(v27) = *(_DWORD *)(v4 + 32);
        v20 = *(_QWORD *)(v4 + 24);
        LODWORD(v28) = *(_DWORD *)v4;
        v21 = *(_QWORD *)(v4 + 128);
        v13 = *(_DWORD *)(v4 + 64);
        v22 = *(_QWORD *)(v4 + 56);
        v14 = *(_DWORD *)(v4 + 8);
        v23 = 0x1000000;
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (int)&dword_180044304,
          *((_QWORD *)this + 34) + 8,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          (const wchar_t **)&v22,
          (__int64)&v13,
          (const wchar_t **)&v21,
          (__int64)&v28,
          (const unsigned __int16 **)&v20,
          (__int64)&v27,
          (const wchar_t **)&v19,
          (__int64)&v26,
          (const wchar_t **)&v18,
          (const unsigned __int16 **)&v17,
          (__int64)&SRWLock,
          (const wchar_t **)&v16,
          (const unsigned __int16 **)&v15);
      }
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
    v8 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        LODWORD(v26) = *(_DWORD *)(v11 + 72);
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v9,
          (int)byte_1800442AB,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002bc70  push    rbp
0x18002bc72  push    rbx
0x18002bc73  push    rdi
0x18002bc74  lea     rbp, [rsp-47h]
0x18002bc79  sub     rsp, 100h
0x18002bc80  mov     [rbp+57h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002bc88  mov     rbx, rcx
0x18002bc8b  mov     rdi, [rcx+110h]
0x18002bc92  mov     eax, [rdi+48h]
0x18002bc95  test    eax, eax
0x18002bc97  jns     loc_18002BE44
0x18002bc9d  add     rdi, 50h ; 'P'
0x18002bca1  cmp     eax, [rdi+8]
0x18002bca4  jnz     loc_18002BE44
0x18002bcaa  test    rdi, rdi
0x18002bcad  jz      loc_18002BE44
0x18002bcb3  lea     rdx, [rbp+57h+SRWLock]
0x18002bcb7  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bcbc  mov     rax, [rbx+110h]
0x18002bcc3  mov     dword ptr [rax], 2
0x18002bcc9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002bccd  test    rcx, rcx
0x18002bcd0  jz      short loc_18002BCD9
0x18002bcd2  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bcd8  nop
0x18002bcd9  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002bcde  mov     r9, rax
0x18002bce1  mov     ecx, [rax]
0x18002bce3  cmp     ecx, 5
0x18002bce6  jbe     loc_18002BEE9
0x18002bcec  mov     rax, [rax+18h]
0x18002bcf0  mov     rcx, [r9+10h]
0x18002bcf4  mov     rdx, 400000000000h
0x18002bcfe  test    rdx, rcx
0x18002bd01  jz      loc_18002BEE9
0x18002bd07  mov     rcx, rax
0x18002bd0a  and     rcx, rdx
0x18002bd0d  cmp     rcx, rax
0x18002bd10  jnz     loc_18002BEE9
0x18002bd16  mov     rax, [rdi+78h]
0x18002bd1a  mov     [rbp+57h+var_68], rax
0x18002bd1e  mov     rax, [rdi+70h]
0x18002bd22  mov     [rbp+57h+var_60], rax
0x18002bd26  mov     eax, [rdi+68h]
0x18002bd29  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002bd2c  mov     rax, [rdi+60h]
0x18002bd30  mov     [rbp+57h+var_58], rax
0x18002bd34  mov     rax, [rdi+58h]
0x18002bd38  mov     [rbp+57h+var_50], rax
0x18002bd3c  mov     eax, [rdi+50h]
0x18002bd3f  mov     dword ptr [rbp+57h+arg_8], eax
0x18002bd42  mov     rax, [rdi+48h]
0x18002bd46  mov     [rbp+57h+var_48], rax
0x18002bd4a  mov     eax, [rdi+20h]
0x18002bd4d  mov     dword ptr [rbp+57h+arg_10], eax
0x18002bd50  mov     rax, [rdi+18h]
0x18002bd54  mov     [rbp+57h+var_40], rax
0x18002bd58  mov     eax, [rdi]
0x18002bd5a  mov     dword ptr [rbp+57h+arg_18], eax
0x18002bd5d  mov     rax, [rdi+80h]
0x18002bd64  mov     [rbp+57h+var_38], rax
0x18002bd68  mov     eax, [rdi+40h]
0x18002bd6b  mov     dword ptr [rbp+57h+var_70], eax
0x18002bd6e  mov     rax, [rdi+38h]
0x18002bd72  mov     [rbp+57h+var_30], rax
0x18002bd76  mov     eax, [rdi+8]
0x18002bd79  mov     dword ptr [rbp+57h+var_70+4], eax
0x18002bd7c  mov     eax, 1000000h
0x18002bd81  mov     [rbp+57h+var_28], rax
0x18002bd85  mov     [rbp+57h+var_20], rax
0x18002bd89  mov     r8, [rbx+110h]
0x18002bd90  add     r8, 8; int
0x18002bd94  lea     rax, [rbp+57h+var_68]
0x18002bd98  mov     [rsp+110h+var_78], rax; __int64
0x18002bda0  lea     rax, [rbp+57h+var_60]
0x18002bda4  mov     [rsp+110h+var_80], rax; __int64
0x18002bdac  lea     rax, [rbp+57h+SRWLock]
0x18002bdb0  mov     [rsp+110h+var_88], rax; __int64
0x18002bdb8  lea     rax, [rbp+57h+var_58]
0x18002bdbc  mov     [rsp+110h+var_90], rax; __int64
0x18002bdc4  lea     rax, [rbp+57h+var_50]
0x18002bdc8  mov     [rsp+110h+var_98], rax; __int64
0x18002bdcd  lea     rax, [rbp+57h+arg_8]
0x18002bdd1  mov     [rsp+110h+var_A0], rax; __int64
0x18002bdd6  lea     rax, [rbp+57h+var_48]
0x18002bdda  mov     [rsp+110h+var_A8], rax; __int64
0x18002bddf  lea     rax, [rbp+57h+arg_10]
0x18002bde3  mov     [rsp+110h+var_B0], rax; __int64
0x18002bde8  lea     rax, [rbp+57h+var_40]
0x18002bdec  mov     [rsp+110h+var_B8], rax; __int64
0x18002bdf1  lea     rax, [rbp+57h+arg_18]
0x18002bdf5  mov     [rsp+110h+var_C0], rax; __int64
0x18002bdfa  lea     rax, [rbp+57h+var_38]
0x18002bdfe  mov     [rsp+110h+var_C8], rax; __int64
0x18002be03  lea     rax, [rbp+57h+var_70]
0x18002be07  mov     [rsp+110h+var_D0], rax; __int64
0x18002be0c  lea     rax, [rbp+57h+var_30]
0x18002be10  mov     [rsp+110h+var_D8], rax; __int64
0x18002be15  lea     rax, [rbp+57h+var_70+4]
0x18002be19  mov     [rsp+110h+var_E0], rax; __int64
0x18002be1e  lea     rax, [rbp+57h+var_28]
0x18002be22  mov     [rsp+110h+var_E8], rax; __int64
0x18002be27  lea     rax, [rbp+57h+var_20]
0x18002be2b  mov     [rsp+110h+var_F0], rax; __int64
0x18002be30  lea     rdx, dword_180044304; int
0x18002be37  mov     rcx, r9; int
0x18002be3a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002be3f  jmp     loc_18002BEE9
0x18002be44  lea     rdx, [rbp+57h+SRWLock]
0x18002be48  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002be4d  mov     rax, [rbx+110h]
0x18002be54  mov     dword ptr [rax], 2
0x18002be5a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002be5e  test    rcx, rcx
0x18002be61  jz      short loc_18002BE6A
0x18002be63  call    cs:__imp_ReleaseSRWLockExclusive
0x18002be69  nop
0x18002be6a  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002be6f  mov     rdi, rax
0x18002be72  mov     ecx, [rax]
0x18002be74  cmp     ecx, 5
0x18002be77  jbe     short loc_18002BEE9
0x18002be79  mov     rax, [rax+18h]
0x18002be7d  mov     rcx, [rdi+10h]
0x18002be81  mov     rdx, 400000000000h
0x18002be8b  test    rdx, rcx
0x18002be8e  jz      short loc_18002BEE9
0x18002be90  mov     rcx, rax
0x18002be93  and     rcx, rdx
0x18002be96  cmp     rcx, rax
0x18002be99  jnz     short loc_18002BEE9
0x18002be9b  call    cs:__imp_GetCurrentThreadId
0x18002bea1  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002bea4  mov     r8, [rbx+110h]
0x18002beab  mov     eax, [r8+48h]
0x18002beaf  mov     dword ptr [rbp+57h+arg_8], eax
0x18002beb2  mov     eax, 1000000h
0x18002beb7  mov     [rbp+57h+arg_10], rax
0x18002bebb  add     r8, 8
0x18002bebf  lea     rax, [rbp+57h+SRWLock]
0x18002bec3  mov     [rsp+110h+var_E0], rax
0x18002bec8  lea     rax, [rbp+57h+arg_8]
0x18002becc  mov     [rsp+110h+var_E8], rax
0x18002bed1  lea     rax, [rbp+57h+arg_10]
0x18002bed5  mov     [rsp+110h+var_F0], rax
0x18002beda  lea     rdx, byte_1800442AB
0x18002bee1  mov     rcx, rdi
0x18002bee4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002bee9  mov     rcx, rbx
0x18002beec  add     rsp, 100h
0x18002bef3  pop     rdi
0x18002bef4  pop     rbx
0x18002bef5  pop     rbp
0x18002bef6  jmp     ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
