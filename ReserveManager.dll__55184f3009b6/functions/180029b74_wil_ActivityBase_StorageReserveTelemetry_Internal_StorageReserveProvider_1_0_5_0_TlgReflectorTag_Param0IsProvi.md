# wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180029b74`
- end: `0x180029dd5`
- name: `?ReportStopActivity@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180026084`
- `0x18002aa80`

## callees

- `0x180002a68`
- `0x180002c44`
- `0x18002939c`
- `0x180029b74`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d60`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v23; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v24; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v27; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v28; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v30; // [rsp+120h] [rbp+67h] BYREF
  __int64 v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  __int64 v33; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
      v8 = (__int64)v7;
      if ( *(_DWORD *)v7 > 2u )
      {
        v9 = *((_QWORD *)v7 + 3);
        if ( (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
        {
          v10 = a1[34];
          v22 = *(_QWORD *)(v6 + 120);
          v23 = *(_QWORD *)(v6 + 112);
          LODWORD(v31) = *(_DWORD *)(v6 + 104);
          v24 = *(_QWORD *)(v6 + 96);
          v25 = *(_QWORD *)(v6 + 88);
          LODWORD(v30) = *(_DWORD *)(v6 + 80);
          v26 = *(_QWORD *)(v6 + 72);
          LODWORD(v32) = *(_DWORD *)(v6 + 32);
          v27 = *(_QWORD *)(v6 + 24);
          LODWORD(v33) = *(_DWORD *)v6;
          v28 = *(_QWORD *)(v6 + 128);
          v19 = *(_DWORD *)(v6 + 64);
          v29 = *(_QWORD *)(v6 + 56);
          v20 = *(_DWORD *)(v6 + 8);
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v8,
            (int)&qword_1800431E8,
            v10 + 8,
            v8,
            (__int64)&v21,
            (__int64)&v20,
            (const wchar_t **)&v29,
            (__int64)&v19,
            (const wchar_t **)&v28,
            (__int64)&v33,
            (const unsigned __int16 **)&v27,
            (__int64)&v32,
            (const wchar_t **)&v26,
            (__int64)&v30,
            (const wchar_t **)&v25,
            (const unsigned __int16 **)&v24,
            (__int64)&v31,
            (const wchar_t **)&v23,
            (const unsigned __int16 **)&v22);
        }
      }
    }
    else
    {
      v11 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
      v12 = v11;
      if ( *(_DWORD *)v11 > 2u )
      {
        v13 = *((_QWORD *)v11 + 3);
        if ( (*((_QWORD *)v12 + 2) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
        {
          v14 = a1[34];
          v32 = *(_QWORD *)(v14 + 56);
          v33 = *(_QWORD *)(v14 + 48);
          CurrentThreadId = GetCurrentThreadId();
          v16 = a1[34];
          LODWORD(v31) = CurrentThreadId;
          LODWORD(v30) = a2;
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (int)v12,
            (int)&byte_1800432FF,
            v16 + 8,
            v17,
            (__int64)&v21,
            (__int64)&v30,
            (__int64)&v31,
            (const wchar_t **)&v33,
            (const unsigned __int16 **)&v32);
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x180029b74  push    rbp
0x180029b76  push    rbx
0x180029b77  push    rsi
0x180029b78  push    rdi
0x180029b79  lea     rbp, [rsp-3Fh]
0x180029b7e  sub     rsp, 0F8h
0x180029b85  mov     esi, edx
0x180029b87  mov     rbx, rcx
0x180029b8a  test    edx, edx
0x180029b8c  jns     loc_180029DBB
0x180029b92  mov     rdi, [rcx+110h]
0x180029b99  mov     eax, [rdi+48h]
0x180029b9c  test    eax, eax
0x180029b9e  jns     loc_180029D14
0x180029ba4  add     rdi, 50h ; 'P'
0x180029ba8  cmp     eax, [rdi+8]
0x180029bab  jnz     loc_180029D14
0x180029bb1  test    rdi, rdi
0x180029bb4  jz      loc_180029D14
0x180029bba  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x180029bbf  mov     r9, rax
0x180029bc2  mov     ecx, [rax]
0x180029bc4  cmp     ecx, 2
0x180029bc7  jbe     loc_180029DBB
0x180029bcd  mov     rax, [rax+18h]
0x180029bd1  mov     rdx, 200000000000h
0x180029bdb  mov     rcx, [r9+10h]
0x180029bdf  test    rdx, rcx
0x180029be2  jz      loc_180029DBB
0x180029be8  mov     rcx, rax
0x180029beb  and     rcx, rdx
0x180029bee  cmp     rcx, rax
0x180029bf1  jnz     loc_180029DBB
0x180029bf7  mov     rax, [rdi+78h]
0x180029bfb  lea     rdx, qword_1800431E8; int
0x180029c02  mov     r8, [rbx+110h]
0x180029c09  mov     rcx, r9; int
0x180029c0c  mov     [rbp+57h+var_60], rax
0x180029c10  add     r8, 8; int
0x180029c14  mov     rax, [rdi+70h]
0x180029c18  mov     [rbp+57h+var_58], rax
0x180029c1c  mov     eax, [rdi+68h]
0x180029c1f  mov     dword ptr [rbp+57h+arg_8], eax
0x180029c22  mov     rax, [rdi+60h]
0x180029c26  mov     [rbp+57h+var_50], rax
0x180029c2a  mov     rax, [rdi+58h]
0x180029c2e  mov     [rbp+57h+var_48], rax
0x180029c32  mov     eax, [rdi+50h]
0x180029c35  mov     dword ptr [rbp+57h+arg_0], eax
0x180029c38  mov     rax, [rdi+48h]
0x180029c3c  mov     [rbp+57h+var_40], rax
0x180029c40  mov     eax, [rdi+20h]
0x180029c43  mov     dword ptr [rbp+57h+arg_10], eax
0x180029c46  mov     rax, [rdi+18h]
0x180029c4a  mov     [rbp+57h+var_38], rax
0x180029c4e  mov     eax, [rdi]
0x180029c50  mov     dword ptr [rbp+57h+arg_18], eax
0x180029c53  mov     rax, [rdi+80h]
0x180029c5a  mov     [rbp+57h+var_30], rax
0x180029c5e  mov     eax, [rdi+40h]
0x180029c61  mov     dword ptr [rbp+57h+var_70], eax
0x180029c64  mov     rax, [rdi+38h]
0x180029c68  mov     [rbp+57h+var_28], rax
0x180029c6c  mov     eax, [rdi+8]
0x180029c6f  mov     dword ptr [rbp+57h+var_70+4], eax
0x180029c72  lea     rax, [rbp+57h+var_60]
0x180029c76  mov     [rsp+110h+var_80], rax; __int64
0x180029c7e  lea     rax, [rbp+57h+var_58]
0x180029c82  mov     [rsp+110h+var_88], rax; __int64
0x180029c8a  lea     rax, [rbp+57h+arg_8]
0x180029c8e  mov     [rsp+110h+var_90], rax; __int64
0x180029c96  lea     rax, [rbp+57h+var_50]
0x180029c9a  mov     [rsp+110h+var_98], rax; __int64
0x180029c9f  lea     rax, [rbp+57h+var_48]
0x180029ca3  mov     [rsp+110h+var_A0], rax; __int64
0x180029ca8  lea     rax, [rbp+57h+arg_0]
0x180029cac  mov     [rsp+110h+var_A8], rax; __int64
0x180029cb1  lea     rax, [rbp+57h+var_40]
0x180029cb5  mov     [rsp+110h+var_B0], rax; __int64
0x180029cba  lea     rax, [rbp+57h+arg_10]
0x180029cbe  mov     [rsp+110h+var_B8], rax; __int64
0x180029cc3  lea     rax, [rbp+57h+var_38]
0x180029cc7  mov     [rsp+110h+var_C0], rax; __int64
0x180029ccc  lea     rax, [rbp+57h+arg_18]
0x180029cd0  mov     [rsp+110h+var_C8], rax; __int64
0x180029cd5  lea     rax, [rbp+57h+var_30]
0x180029cd9  mov     [rsp+110h+var_D0], rax; __int64
0x180029cde  lea     rax, [rbp+57h+var_70]
0x180029ce2  mov     [rsp+110h+var_D8], rax; __int64
0x180029ce7  lea     rax, [rbp+57h+var_28]
0x180029ceb  mov     [rsp+110h+var_E0], rax; __int64
0x180029cf0  lea     rax, [rbp+57h+var_70+4]
0x180029cf4  mov     [rsp+110h+var_E8], rax; __int64
0x180029cf9  lea     rax, [rbp+57h+var_68]
0x180029cfd  mov     [rsp+110h+var_F0], rax; __int64
0x180029d02  mov     [rbp+57h+var_68], 1000000h
0x180029d0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180029d0f  jmp     loc_180029DBB
0x180029d14  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x180029d19  mov     rdi, rax
0x180029d1c  mov     ecx, [rax]
0x180029d1e  cmp     ecx, 2
0x180029d21  jbe     loc_180029DBB
0x180029d27  mov     rax, [rax+18h]
0x180029d2b  mov     rdx, 200000000000h
0x180029d35  mov     rcx, [rdi+10h]
0x180029d39  test    rdx, rcx
0x180029d3c  jz      short loc_180029DBB
0x180029d3e  mov     rcx, rax
0x180029d41  and     rcx, rdx
0x180029d44  cmp     rcx, rax
0x180029d47  jnz     short loc_180029DBB
0x180029d49  mov     rcx, [rbx+110h]
0x180029d50  mov     rax, [rcx+38h]
0x180029d54  mov     [rbp+57h+arg_10], rax
0x180029d58  mov     rax, [rcx+30h]
0x180029d5c  mov     [rbp+57h+arg_18], rax
0x180029d60  call    cs:__imp_GetCurrentThreadId
0x180029d66  mov     r8, [rbx+110h]
0x180029d6d  lea     rdx, byte_1800432FF; int
0x180029d74  mov     dword ptr [rbp+57h+arg_8], eax
0x180029d77  add     r8, 8
0x180029d7b  lea     rax, [rbp+57h+arg_10]
0x180029d7f  mov     dword ptr [rbp+57h+arg_0], esi
0x180029d82  mov     [rsp+110h+var_D0], rax; __int64
0x180029d87  mov     rcx, rdi; int
0x180029d8a  lea     rax, [rbp+57h+arg_18]
0x180029d8e  mov     [rbp+57h+var_68], 1000000h
0x180029d96  mov     [rsp+110h+var_D8], rax; __int64
0x180029d9b  lea     rax, [rbp+57h+arg_8]
0x180029d9f  mov     [rsp+110h+var_E0], rax; __int64
0x180029da4  lea     rax, [rbp+57h+arg_0]
0x180029da8  mov     [rsp+110h+var_E8], rax; __int64
0x180029dad  lea     rax, [rbp+57h+var_68]
0x180029db1  mov     [rsp+110h+var_F0], rax; __int64
0x180029db6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180029dbb  mov     rax, [rbx]
0x180029dbe  mov     rcx, rbx
0x180029dc1  mov     rax, [rax+8]
0x180029dc5  add     rsp, 0F8h
0x180029dcc  pop     rdi
0x180029dcd  pop     rsi
0x180029dce  pop     rbx
0x180029dcf  pop     rbp
0x180029dd0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
