# StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StopActivity(void)

- ea: `0x18002bf10`
- end: `0x18002c19b`
- name: `?StopActivity@FixReserveAreaUntaggedParent@SRProvider@Internal@StorageReserveTelemetry@@MEAAXXZ`
- size: `651`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800018ec`
- `0x1800029d8`
- `0x180028494`
- `0x180028738`
- `0x18002939c`
- `0x18002bf10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bf72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c103`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bf72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c13b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c13b`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StopActivity(
        StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *this)
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
          (int)&byte_180044E03,
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
          (int)&word_180044DA6,
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
0x18002bf10  push    rbp
0x18002bf12  push    rbx
0x18002bf13  push    rdi
0x18002bf14  lea     rbp, [rsp-47h]
0x18002bf19  sub     rsp, 100h
0x18002bf20  mov     [rbp+57h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002bf28  mov     rbx, rcx
0x18002bf2b  mov     rdi, [rcx+110h]
0x18002bf32  mov     eax, [rdi+48h]
0x18002bf35  test    eax, eax
0x18002bf37  jns     loc_18002C0E4
0x18002bf3d  add     rdi, 50h ; 'P'
0x18002bf41  cmp     eax, [rdi+8]
0x18002bf44  jnz     loc_18002C0E4
0x18002bf4a  test    rdi, rdi
0x18002bf4d  jz      loc_18002C0E4
0x18002bf53  lea     rdx, [rbp+57h+SRWLock]
0x18002bf57  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bf5c  mov     rax, [rbx+110h]
0x18002bf63  mov     dword ptr [rax], 2
0x18002bf69  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002bf6d  test    rcx, rcx
0x18002bf70  jz      short loc_18002BF79
0x18002bf72  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bf78  nop
0x18002bf79  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002bf7e  mov     r9, rax
0x18002bf81  mov     ecx, [rax]
0x18002bf83  cmp     ecx, 5
0x18002bf86  jbe     loc_18002C189
0x18002bf8c  mov     rax, [rax+18h]
0x18002bf90  mov     rcx, [r9+10h]
0x18002bf94  mov     rdx, 400000000000h
0x18002bf9e  test    rdx, rcx
0x18002bfa1  jz      loc_18002C189
0x18002bfa7  mov     rcx, rax
0x18002bfaa  and     rcx, rdx
0x18002bfad  cmp     rcx, rax
0x18002bfb0  jnz     loc_18002C189
0x18002bfb6  mov     rax, [rdi+78h]
0x18002bfba  mov     [rbp+57h+var_68], rax
0x18002bfbe  mov     rax, [rdi+70h]
0x18002bfc2  mov     [rbp+57h+var_60], rax
0x18002bfc6  mov     eax, [rdi+68h]
0x18002bfc9  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002bfcc  mov     rax, [rdi+60h]
0x18002bfd0  mov     [rbp+57h+var_58], rax
0x18002bfd4  mov     rax, [rdi+58h]
0x18002bfd8  mov     [rbp+57h+var_50], rax
0x18002bfdc  mov     eax, [rdi+50h]
0x18002bfdf  mov     dword ptr [rbp+57h+arg_8], eax
0x18002bfe2  mov     rax, [rdi+48h]
0x18002bfe6  mov     [rbp+57h+var_48], rax
0x18002bfea  mov     eax, [rdi+20h]
0x18002bfed  mov     dword ptr [rbp+57h+arg_10], eax
0x18002bff0  mov     rax, [rdi+18h]
0x18002bff4  mov     [rbp+57h+var_40], rax
0x18002bff8  mov     eax, [rdi]
0x18002bffa  mov     dword ptr [rbp+57h+arg_18], eax
0x18002bffd  mov     rax, [rdi+80h]
0x18002c004  mov     [rbp+57h+var_38], rax
0x18002c008  mov     eax, [rdi+40h]
0x18002c00b  mov     dword ptr [rbp+57h+var_70], eax
0x18002c00e  mov     rax, [rdi+38h]
0x18002c012  mov     [rbp+57h+var_30], rax
0x18002c016  mov     eax, [rdi+8]
0x18002c019  mov     dword ptr [rbp+57h+var_70+4], eax
0x18002c01c  mov     eax, 1000000h
0x18002c021  mov     [rbp+57h+var_28], rax
0x18002c025  mov     [rbp+57h+var_20], rax
0x18002c029  mov     r8, [rbx+110h]
0x18002c030  add     r8, 8; int
0x18002c034  lea     rax, [rbp+57h+var_68]
0x18002c038  mov     [rsp+110h+var_78], rax; __int64
0x18002c040  lea     rax, [rbp+57h+var_60]
0x18002c044  mov     [rsp+110h+var_80], rax; __int64
0x18002c04c  lea     rax, [rbp+57h+SRWLock]
0x18002c050  mov     [rsp+110h+var_88], rax; __int64
0x18002c058  lea     rax, [rbp+57h+var_58]
0x18002c05c  mov     [rsp+110h+var_90], rax; __int64
0x18002c064  lea     rax, [rbp+57h+var_50]
0x18002c068  mov     [rsp+110h+var_98], rax; __int64
0x18002c06d  lea     rax, [rbp+57h+arg_8]
0x18002c071  mov     [rsp+110h+var_A0], rax; __int64
0x18002c076  lea     rax, [rbp+57h+var_48]
0x18002c07a  mov     [rsp+110h+var_A8], rax; __int64
0x18002c07f  lea     rax, [rbp+57h+arg_10]
0x18002c083  mov     [rsp+110h+var_B0], rax; __int64
0x18002c088  lea     rax, [rbp+57h+var_40]
0x18002c08c  mov     [rsp+110h+var_B8], rax; __int64
0x18002c091  lea     rax, [rbp+57h+arg_18]
0x18002c095  mov     [rsp+110h+var_C0], rax; __int64
0x18002c09a  lea     rax, [rbp+57h+var_38]
0x18002c09e  mov     [rsp+110h+var_C8], rax; __int64
0x18002c0a3  lea     rax, [rbp+57h+var_70]
0x18002c0a7  mov     [rsp+110h+var_D0], rax; __int64
0x18002c0ac  lea     rax, [rbp+57h+var_30]
0x18002c0b0  mov     [rsp+110h+var_D8], rax; __int64
0x18002c0b5  lea     rax, [rbp+57h+var_70+4]
0x18002c0b9  mov     [rsp+110h+var_E0], rax; __int64
0x18002c0be  lea     rax, [rbp+57h+var_28]
0x18002c0c2  mov     [rsp+110h+var_E8], rax; __int64
0x18002c0c7  lea     rax, [rbp+57h+var_20]
0x18002c0cb  mov     [rsp+110h+var_F0], rax; __int64
0x18002c0d0  lea     rdx, byte_180044E03; int
0x18002c0d7  mov     rcx, r9; int
0x18002c0da  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002c0df  jmp     loc_18002C189
0x18002c0e4  lea     rdx, [rbp+57h+SRWLock]
0x18002c0e8  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c0ed  mov     rax, [rbx+110h]
0x18002c0f4  mov     dword ptr [rax], 2
0x18002c0fa  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002c0fe  test    rcx, rcx
0x18002c101  jz      short loc_18002C10A
0x18002c103  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c109  nop
0x18002c10a  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002c10f  mov     rdi, rax
0x18002c112  mov     ecx, [rax]
0x18002c114  cmp     ecx, 5
0x18002c117  jbe     short loc_18002C189
0x18002c119  mov     rax, [rax+18h]
0x18002c11d  mov     rcx, [rdi+10h]
0x18002c121  mov     rdx, 400000000000h
0x18002c12b  test    rdx, rcx
0x18002c12e  jz      short loc_18002C189
0x18002c130  mov     rcx, rax
0x18002c133  and     rcx, rdx
0x18002c136  cmp     rcx, rax
0x18002c139  jnz     short loc_18002C189
0x18002c13b  call    cs:__imp_GetCurrentThreadId
0x18002c141  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002c144  mov     r8, [rbx+110h]
0x18002c14b  mov     eax, [r8+48h]
0x18002c14f  mov     dword ptr [rbp+57h+arg_8], eax
0x18002c152  mov     eax, 1000000h
0x18002c157  mov     [rbp+57h+arg_10], rax
0x18002c15b  add     r8, 8
0x18002c15f  lea     rax, [rbp+57h+SRWLock]
0x18002c163  mov     [rsp+110h+var_E0], rax
0x18002c168  lea     rax, [rbp+57h+arg_8]
0x18002c16c  mov     [rsp+110h+var_E8], rax
0x18002c171  lea     rax, [rbp+57h+arg_10]
0x18002c175  mov     [rsp+110h+var_F0], rax
0x18002c17a  lea     rdx, word_180044DA6
0x18002c181  mov     rcx, rdi
0x18002c184  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c189  mov     rcx, rbx
0x18002c18c  add     rsp, 100h
0x18002c193  pop     rdi
0x18002c194  pop     rbx
0x18002c195  pop     rbp
0x18002c196  jmp     ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
