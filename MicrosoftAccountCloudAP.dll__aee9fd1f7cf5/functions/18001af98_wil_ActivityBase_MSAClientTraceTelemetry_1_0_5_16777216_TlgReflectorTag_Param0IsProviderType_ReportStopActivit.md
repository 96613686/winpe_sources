# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18001af98`
- end: `0x18001b1dd`
- name: `?ReportStopActivity@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001a7d8`
- `0x18001b688`

## callees

- `0x1800011fc`
- `0x180002300`
- `0x1800023fc`
- `0x18001acec`
- `0x18001af98`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b168`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v28; // [rsp+E8h] [rbp+2Fh] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  const unsigned __int16 *v31; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v32; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = MSAClientTraceTelemetry::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
      {
        v9 = *(const unsigned __int16 **)(v6 + 120);
        v10 = a1[34];
        v22 = *(const unsigned __int16 **)(v6 + 112);
        v30 = *(_DWORD *)(v6 + 104);
        v23 = *(const unsigned __int16 **)(v6 + 96);
        v24 = *(const unsigned __int16 **)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v25 = *(const unsigned __int16 **)(v6 + 72);
        LODWORD(v31) = *(_DWORD *)(v6 + 32);
        v26 = *(const unsigned __int16 **)(v6 + 24);
        LODWORD(v32) = *(_DWORD *)v6;
        v27 = *(const unsigned __int16 **)(v6 + 128);
        v18 = *(_DWORD *)(v6 + 64);
        v28 = *(const unsigned __int16 **)(v6 + 56);
        v19 = *(_DWORD *)(v6 + 8);
        v21 = v9;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v8,
          (__int64)&dword_180044CEC,
          v10 + 8,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          &v28,
          (__int64)&v18,
          &v27,
          (__int64)&v32,
          &v26,
          (__int64)&v31,
          &v25,
          (__int64)&v29,
          &v24,
          &v23,
          (__int64)&v30,
          &v22,
          &v21);
      }
    }
    else
    {
      v11 = MSAClientTraceTelemetry::Provider();
      v12 = (__int64)v11;
      if ( *(_DWORD *)v11 > 2u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
      {
        v13 = a1[34];
        v31 = *(const unsigned __int16 **)(v13 + 56);
        v32 = *(const unsigned __int16 **)(v13 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v15 = a1[34];
        v30 = CurrentThreadId;
        v29 = a2;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (__int64)byte_180044B81,
          v15 + 8,
          v16,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v30,
          &v32,
          &v31);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18001af98  push    rbp
0x18001af9a  push    rbx
0x18001af9b  push    rsi
0x18001af9c  push    rdi
0x18001af9d  lea     rbp, [rsp-3Fh]
0x18001afa2  sub     rsp, 0F8h
0x18001afa9  mov     esi, edx
0x18001afab  mov     rbx, rcx
0x18001afae  test    edx, edx
0x18001afb0  jns     loc_18001B1C3
0x18001afb6  mov     rdi, [rcx+110h]
0x18001afbd  mov     eax, [rdi+48h]
0x18001afc0  test    eax, eax
0x18001afc2  jns     loc_18001B128
0x18001afc8  add     rdi, 50h ; 'P'
0x18001afcc  cmp     eax, [rdi+8]
0x18001afcf  jnz     loc_18001B128
0x18001afd5  test    rdi, rdi
0x18001afd8  jz      loc_18001B128
0x18001afde  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001afe3  mov     r9, rax
0x18001afe6  mov     ecx, [rax]
0x18001afe8  cmp     ecx, 2
0x18001afeb  jbe     loc_18001B1C3
0x18001aff1  mov     rdx, 200000000000h
0x18001affb  mov     rcx, rax
0x18001affe  call    _tlgKeywordOn
0x18001b003  test    al, al
0x18001b005  jz      loc_18001B1C3
0x18001b00b  mov     rax, [rdi+70h]
0x18001b00f  lea     rdx, dword_180044CEC
0x18001b016  mov     rcx, [rdi+78h]
0x18001b01a  mov     r8, [rbx+110h]
0x18001b021  mov     [rbp+57h+var_58], rax
0x18001b025  add     r8, 8
0x18001b029  mov     eax, [rdi+68h]
0x18001b02c  mov     [rbp+57h+arg_8], eax
0x18001b02f  mov     rax, [rdi+60h]
0x18001b033  mov     [rbp+57h+var_50], rax
0x18001b037  mov     rax, [rdi+58h]
0x18001b03b  mov     [rbp+57h+var_48], rax
0x18001b03f  mov     eax, [rdi+50h]
0x18001b042  mov     [rbp+57h+arg_0], eax
0x18001b045  mov     rax, [rdi+48h]
0x18001b049  mov     [rbp+57h+var_40], rax
0x18001b04d  mov     eax, [rdi+20h]
0x18001b050  mov     dword ptr [rbp+57h+arg_10], eax
0x18001b053  mov     rax, [rdi+18h]
0x18001b057  mov     [rbp+57h+var_38], rax
0x18001b05b  mov     eax, [rdi]
0x18001b05d  mov     dword ptr [rbp+57h+arg_18], eax
0x18001b060  mov     rax, [rdi+80h]
0x18001b067  mov     [rbp+57h+var_30], rax
0x18001b06b  mov     eax, [rdi+40h]
0x18001b06e  mov     [rbp+57h+var_70], eax
0x18001b071  mov     rax, [rdi+38h]
0x18001b075  mov     [rbp+57h+var_28], rax
0x18001b079  mov     eax, [rdi+8]
0x18001b07c  mov     [rbp+57h+var_6C], eax
0x18001b07f  lea     rax, [rbp+57h+var_60]
0x18001b083  mov     [rsp+110h+var_80], rax
0x18001b08b  lea     rax, [rbp+57h+var_58]
0x18001b08f  mov     [rsp+110h+var_88], rax
0x18001b097  lea     rax, [rbp+57h+arg_8]
0x18001b09b  mov     [rsp+110h+var_90], rax
0x18001b0a3  lea     rax, [rbp+57h+var_50]
0x18001b0a7  mov     [rsp+110h+var_98], rax
0x18001b0ac  lea     rax, [rbp+57h+var_48]
0x18001b0b0  mov     [rsp+110h+var_A0], rax
0x18001b0b5  lea     rax, [rbp+57h+arg_0]
0x18001b0b9  mov     [rsp+110h+var_A8], rax
0x18001b0be  lea     rax, [rbp+57h+var_40]
0x18001b0c2  mov     [rsp+110h+var_B0], rax
0x18001b0c7  lea     rax, [rbp+57h+arg_10]
0x18001b0cb  mov     [rsp+110h+var_B8], rax
0x18001b0d0  lea     rax, [rbp+57h+var_38]
0x18001b0d4  mov     [rsp+110h+var_C0], rax
0x18001b0d9  lea     rax, [rbp+57h+arg_18]
0x18001b0dd  mov     [rsp+110h+var_C8], rax
0x18001b0e2  lea     rax, [rbp+57h+var_30]
0x18001b0e6  mov     [rsp+110h+var_D0], rax
0x18001b0eb  lea     rax, [rbp+57h+var_70]
0x18001b0ef  mov     [rsp+110h+var_D8], rax
0x18001b0f4  lea     rax, [rbp+57h+var_28]
0x18001b0f8  mov     [rsp+110h+var_E0], rax
0x18001b0fd  lea     rax, [rbp+57h+var_6C]
0x18001b101  mov     [rsp+110h+var_E8], rax
0x18001b106  lea     rax, [rbp+57h+var_68]
0x18001b10a  mov     [rbp+57h+var_60], rcx
0x18001b10e  mov     rcx, r9
0x18001b111  mov     [rsp+110h+var_F0], rax
0x18001b116  mov     [rbp+57h+var_68], 1000000h
0x18001b11e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b123  jmp     loc_18001B1C3
0x18001b128  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b12d  mov     rdi, rax
0x18001b130  mov     ecx, [rax]
0x18001b132  cmp     ecx, 2
0x18001b135  jbe     loc_18001B1C3
0x18001b13b  mov     rdx, 200000000000h
0x18001b145  mov     rcx, rax
0x18001b148  call    _tlgKeywordOn
0x18001b14d  test    al, al
0x18001b14f  jz      short loc_18001B1C3
0x18001b151  mov     rcx, [rbx+110h]
0x18001b158  mov     rax, [rcx+38h]
0x18001b15c  mov     [rbp+57h+arg_10], rax
0x18001b160  mov     rax, [rcx+30h]
0x18001b164  mov     [rbp+57h+arg_18], rax
0x18001b168  call    cs:__imp_GetCurrentThreadId
0x18001b16e  mov     r8, [rbx+110h]
0x18001b175  lea     rdx, byte_180044B81
0x18001b17c  mov     [rbp+57h+arg_8], eax
0x18001b17f  add     r8, 8
0x18001b183  lea     rax, [rbp+57h+arg_10]
0x18001b187  mov     [rbp+57h+arg_0], esi
0x18001b18a  mov     [rsp+110h+var_D0], rax
0x18001b18f  mov     rcx, rdi
0x18001b192  lea     rax, [rbp+57h+arg_18]
0x18001b196  mov     [rbp+57h+var_68], 1000000h
0x18001b19e  mov     [rsp+110h+var_D8], rax
0x18001b1a3  lea     rax, [rbp+57h+arg_8]
0x18001b1a7  mov     [rsp+110h+var_E0], rax
0x18001b1ac  lea     rax, [rbp+57h+arg_0]
0x18001b1b0  mov     [rsp+110h+var_E8], rax
0x18001b1b5  lea     rax, [rbp+57h+var_68]
0x18001b1b9  mov     [rsp+110h+var_F0], rax
0x18001b1be  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b1c3  mov     rax, [rbx]
0x18001b1c6  mov     rcx, rbx
0x18001b1c9  mov     rax, [rax+8]
0x18001b1cd  add     rsp, 0F8h
0x18001b1d4  pop     rdi
0x18001b1d5  pop     rsi
0x18001b1d6  pop     rbx
0x18001b1d7  pop     rbp
0x18001b1d8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
