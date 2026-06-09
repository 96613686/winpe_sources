# wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18000ead4`
- end: `0x18000ed19`
- name: `?ReportStopActivity@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000def4`
- `0x18000f224`

## callees

- `0x1800016e0`
- `0x1800017dc`
- `0x180001ecc`
- `0x18000e964`
- `0x18000ead4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eca4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eca4`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
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
      v7 = TraceProvider::Provider();
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
          (__int64)&byte_180029D6F,
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
      v11 = TraceProvider::Provider();
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
          (__int64)&word_180029E86,
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
0x18000ead4  push    rbp
0x18000ead6  push    rbx
0x18000ead7  push    rsi
0x18000ead8  push    rdi
0x18000ead9  lea     rbp, [rsp-3Fh]
0x18000eade  sub     rsp, 0F8h
0x18000eae5  mov     esi, edx
0x18000eae7  mov     rbx, rcx
0x18000eaea  test    edx, edx
0x18000eaec  jns     loc_18000ECFF
0x18000eaf2  mov     rdi, [rcx+110h]
0x18000eaf9  mov     eax, [rdi+48h]
0x18000eafc  test    eax, eax
0x18000eafe  jns     loc_18000EC64
0x18000eb04  add     rdi, 50h ; 'P'
0x18000eb08  cmp     eax, [rdi+8]
0x18000eb0b  jnz     loc_18000EC64
0x18000eb11  test    rdi, rdi
0x18000eb14  jz      loc_18000EC64
0x18000eb1a  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18000eb1f  mov     r9, rax
0x18000eb22  mov     ecx, [rax]
0x18000eb24  cmp     ecx, 2
0x18000eb27  jbe     loc_18000ECFF
0x18000eb2d  mov     rdx, 200000000000h
0x18000eb37  mov     rcx, rax
0x18000eb3a  call    _tlgKeywordOn
0x18000eb3f  test    al, al
0x18000eb41  jz      loc_18000ECFF
0x18000eb47  mov     rax, [rdi+70h]
0x18000eb4b  lea     rdx, byte_180029D6F
0x18000eb52  mov     rcx, [rdi+78h]
0x18000eb56  mov     r8, [rbx+110h]
0x18000eb5d  mov     [rbp+57h+var_58], rax
0x18000eb61  add     r8, 8
0x18000eb65  mov     eax, [rdi+68h]
0x18000eb68  mov     [rbp+57h+arg_8], eax
0x18000eb6b  mov     rax, [rdi+60h]
0x18000eb6f  mov     [rbp+57h+var_50], rax
0x18000eb73  mov     rax, [rdi+58h]
0x18000eb77  mov     [rbp+57h+var_48], rax
0x18000eb7b  mov     eax, [rdi+50h]
0x18000eb7e  mov     [rbp+57h+arg_0], eax
0x18000eb81  mov     rax, [rdi+48h]
0x18000eb85  mov     [rbp+57h+var_40], rax
0x18000eb89  mov     eax, [rdi+20h]
0x18000eb8c  mov     dword ptr [rbp+57h+arg_10], eax
0x18000eb8f  mov     rax, [rdi+18h]
0x18000eb93  mov     [rbp+57h+var_38], rax
0x18000eb97  mov     eax, [rdi]
0x18000eb99  mov     dword ptr [rbp+57h+arg_18], eax
0x18000eb9c  mov     rax, [rdi+80h]
0x18000eba3  mov     [rbp+57h+var_30], rax
0x18000eba7  mov     eax, [rdi+40h]
0x18000ebaa  mov     [rbp+57h+var_70], eax
0x18000ebad  mov     rax, [rdi+38h]
0x18000ebb1  mov     [rbp+57h+var_28], rax
0x18000ebb5  mov     eax, [rdi+8]
0x18000ebb8  mov     [rbp+57h+var_6C], eax
0x18000ebbb  lea     rax, [rbp+57h+var_60]
0x18000ebbf  mov     [rsp+110h+var_80], rax
0x18000ebc7  lea     rax, [rbp+57h+var_58]
0x18000ebcb  mov     [rsp+110h+var_88], rax
0x18000ebd3  lea     rax, [rbp+57h+arg_8]
0x18000ebd7  mov     [rsp+110h+var_90], rax
0x18000ebdf  lea     rax, [rbp+57h+var_50]
0x18000ebe3  mov     [rsp+110h+var_98], rax
0x18000ebe8  lea     rax, [rbp+57h+var_48]
0x18000ebec  mov     [rsp+110h+var_A0], rax
0x18000ebf1  lea     rax, [rbp+57h+arg_0]
0x18000ebf5  mov     [rsp+110h+var_A8], rax
0x18000ebfa  lea     rax, [rbp+57h+var_40]
0x18000ebfe  mov     [rsp+110h+var_B0], rax
0x18000ec03  lea     rax, [rbp+57h+arg_10]
0x18000ec07  mov     [rsp+110h+var_B8], rax
0x18000ec0c  lea     rax, [rbp+57h+var_38]
0x18000ec10  mov     [rsp+110h+var_C0], rax
0x18000ec15  lea     rax, [rbp+57h+arg_18]
0x18000ec19  mov     [rsp+110h+var_C8], rax
0x18000ec1e  lea     rax, [rbp+57h+var_30]
0x18000ec22  mov     [rsp+110h+var_D0], rax
0x18000ec27  lea     rax, [rbp+57h+var_70]
0x18000ec2b  mov     [rsp+110h+var_D8], rax
0x18000ec30  lea     rax, [rbp+57h+var_28]
0x18000ec34  mov     [rsp+110h+var_E0], rax
0x18000ec39  lea     rax, [rbp+57h+var_6C]
0x18000ec3d  mov     [rsp+110h+var_E8], rax
0x18000ec42  lea     rax, [rbp+57h+var_68]
0x18000ec46  mov     [rbp+57h+var_60], rcx
0x18000ec4a  mov     rcx, r9
0x18000ec4d  mov     [rsp+110h+var_F0], rax
0x18000ec52  mov     [rbp+57h+var_68], 1000000h
0x18000ec5a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000ec5f  jmp     loc_18000ECFF
0x18000ec64  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18000ec69  mov     rdi, rax
0x18000ec6c  mov     ecx, [rax]
0x18000ec6e  cmp     ecx, 2
0x18000ec71  jbe     loc_18000ECFF
0x18000ec77  mov     rdx, 200000000000h
0x18000ec81  mov     rcx, rax
0x18000ec84  call    _tlgKeywordOn
0x18000ec89  test    al, al
0x18000ec8b  jz      short loc_18000ECFF
0x18000ec8d  mov     rcx, [rbx+110h]
0x18000ec94  mov     rax, [rcx+38h]
0x18000ec98  mov     [rbp+57h+arg_10], rax
0x18000ec9c  mov     rax, [rcx+30h]
0x18000eca0  mov     [rbp+57h+arg_18], rax
0x18000eca4  call    cs:__imp_GetCurrentThreadId
0x18000ecaa  mov     r8, [rbx+110h]
0x18000ecb1  lea     rdx, word_180029E86
0x18000ecb8  mov     [rbp+57h+arg_8], eax
0x18000ecbb  add     r8, 8
0x18000ecbf  lea     rax, [rbp+57h+arg_10]
0x18000ecc3  mov     [rbp+57h+arg_0], esi
0x18000ecc6  mov     [rsp+110h+var_D0], rax
0x18000eccb  mov     rcx, rdi
0x18000ecce  lea     rax, [rbp+57h+arg_18]
0x18000ecd2  mov     [rbp+57h+var_68], 1000000h
0x18000ecda  mov     [rsp+110h+var_D8], rax
0x18000ecdf  lea     rax, [rbp+57h+arg_8]
0x18000ece3  mov     [rsp+110h+var_E0], rax
0x18000ece8  lea     rax, [rbp+57h+arg_0]
0x18000ecec  mov     [rsp+110h+var_E8], rax
0x18000ecf1  lea     rax, [rbp+57h+var_68]
0x18000ecf5  mov     [rsp+110h+var_F0], rax
0x18000ecfa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000ecff  mov     rax, [rbx]
0x18000ed02  mov     rcx, rbx
0x18000ed05  mov     rax, [rax+8]
0x18000ed09  add     rsp, 0F8h
0x18000ed10  pop     rdi
0x18000ed11  pop     rsi
0x18000ed12  pop     rbx
0x18000ed13  pop     rbp
0x18000ed14  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
