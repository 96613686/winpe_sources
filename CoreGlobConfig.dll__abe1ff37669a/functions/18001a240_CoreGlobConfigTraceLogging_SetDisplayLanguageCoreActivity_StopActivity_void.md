# CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StopActivity(void)

- ea: `0x18001a240`
- end: `0x18001a464`
- name: `?StopActivity@SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180015bf0`
- `0x180016fcc`
- `0x18001a240`
- `0x18001f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a405`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a405`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StopActivity(
        CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CoreGlobConfigTraceLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      v8 = (__int64 *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (__int64 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (__int64 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_18002A8E3,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CoreGlobConfigTraceLogging::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002AA19,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001a240  push    rbp
0x18001a242  push    rbx
0x18001a243  push    rdi
0x18001a244  lea     rbp, [rsp-47h]
0x18001a249  sub     rsp, 100h
0x18001a250  mov     rdi, [rcx+110h]
0x18001a257  mov     rbx, rcx
0x18001a25a  mov     eax, [rdi+48h]
0x18001a25d  test    eax, eax
0x18001a25f  jns     loc_18001A3DB
0x18001a265  add     rdi, 50h ; 'P'
0x18001a269  cmp     eax, [rdi+8]
0x18001a26c  jnz     loc_18001A3DB
0x18001a272  test    rdi, rdi
0x18001a275  jz      loc_18001A3DB
0x18001a27b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a280  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a285  mov     r9, rax
0x18001a288  mov     ecx, [rax]
0x18001a28a  cmp     ecx, 5
0x18001a28d  jbe     loc_18001A452
0x18001a293  mov     rdx, 200000000000h
0x18001a29d  mov     rcx, rax
0x18001a2a0  call    _tlgKeywordOn
0x18001a2a5  test    al, al
0x18001a2a7  jz      loc_18001A452
0x18001a2ad  mov     rax, [rdi+70h]
0x18001a2b1  lea     rdx, byte_18002A8E3
0x18001a2b8  mov     rcx, [rdi+78h]
0x18001a2bc  mov     r8, [rbx+110h]
0x18001a2c3  mov     [rbp+57h+var_60], rax
0x18001a2c7  add     r8, 8
0x18001a2cb  mov     eax, [rdi+68h]
0x18001a2ce  mov     [rbp+57h+arg_0], eax
0x18001a2d1  mov     rax, [rdi+60h]
0x18001a2d5  mov     [rbp+57h+var_58], rax
0x18001a2d9  mov     rax, [rdi+58h]
0x18001a2dd  mov     [rbp+57h+var_50], rax
0x18001a2e1  mov     eax, [rdi+50h]
0x18001a2e4  mov     [rbp+57h+arg_8], eax
0x18001a2e7  mov     rax, [rdi+48h]
0x18001a2eb  mov     [rbp+57h+var_48], rax
0x18001a2ef  mov     eax, [rdi+20h]
0x18001a2f2  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a2f5  mov     rax, [rdi+18h]
0x18001a2f9  mov     [rbp+57h+var_40], rax
0x18001a2fd  mov     eax, [rdi]
0x18001a2ff  mov     [rbp+57h+arg_18], eax
0x18001a302  mov     rax, [rdi+80h]
0x18001a309  mov     [rbp+57h+var_38], rax
0x18001a30d  mov     eax, [rdi+40h]
0x18001a310  mov     [rbp+57h+var_70], eax
0x18001a313  mov     rax, [rdi+38h]
0x18001a317  mov     [rbp+57h+var_30], rax
0x18001a31b  mov     eax, [rdi+8]
0x18001a31e  mov     [rbp+57h+var_6C], eax
0x18001a321  lea     rax, [rbp+57h+var_68]
0x18001a325  mov     [rsp+110h+var_78], rax
0x18001a32d  lea     rax, [rbp+57h+var_60]
0x18001a331  mov     [rsp+110h+var_80], rax
0x18001a339  lea     rax, [rbp+57h+arg_0]
0x18001a33d  mov     [rsp+110h+var_88], rax
0x18001a345  lea     rax, [rbp+57h+var_58]
0x18001a349  mov     [rsp+110h+var_90], rax
0x18001a351  lea     rax, [rbp+57h+var_50]
0x18001a355  mov     [rsp+110h+var_98], rax
0x18001a35a  lea     rax, [rbp+57h+arg_8]
0x18001a35e  mov     [rsp+110h+var_A0], rax
0x18001a363  lea     rax, [rbp+57h+var_48]
0x18001a367  mov     [rsp+110h+var_A8], rax
0x18001a36c  lea     rax, [rbp+57h+arg_10]
0x18001a370  mov     [rsp+110h+var_B0], rax
0x18001a375  lea     rax, [rbp+57h+var_40]
0x18001a379  mov     [rsp+110h+var_B8], rax
0x18001a37e  lea     rax, [rbp+57h+arg_18]
0x18001a382  mov     [rsp+110h+var_C0], rax
0x18001a387  lea     rax, [rbp+57h+var_38]
0x18001a38b  mov     [rsp+110h+var_C8], rax
0x18001a390  lea     rax, [rbp+57h+var_70]
0x18001a394  mov     [rsp+110h+var_D0], rax
0x18001a399  lea     rax, [rbp+57h+var_30]
0x18001a39d  mov     [rsp+110h+var_D8], rax
0x18001a3a2  lea     rax, [rbp+57h+var_6C]
0x18001a3a6  mov     [rsp+110h+var_E0], rax
0x18001a3ab  lea     rax, [rbp+57h+var_28]
0x18001a3af  mov     [rsp+110h+var_E8], rax
0x18001a3b4  lea     rax, [rbp+57h+var_20]
0x18001a3b8  mov     [rbp+57h+var_68], rcx
0x18001a3bc  mov     rcx, r9
0x18001a3bf  mov     [rsp+110h+var_F0], rax
0x18001a3c4  mov     [rbp+57h+var_28], 1000000h
0x18001a3cc  mov     [rbp+57h+var_20], 1000800h
0x18001a3d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a3d9  jmp     short loc_18001A452
0x18001a3db  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a3e0  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a3e5  mov     rdi, rax
0x18001a3e8  mov     ecx, [rax]
0x18001a3ea  cmp     ecx, 5
0x18001a3ed  jbe     short loc_18001A452
0x18001a3ef  mov     rdx, 200000000000h
0x18001a3f9  mov     rcx, rax
0x18001a3fc  call    _tlgKeywordOn
0x18001a401  test    al, al
0x18001a403  jz      short loc_18001A452
0x18001a405  call    cs:__imp_GetCurrentThreadId
0x18001a40b  mov     r8, [rbx+110h]
0x18001a412  lea     rdx, byte_18002AA19
0x18001a419  mov     [rbp+57h+arg_0], eax
0x18001a41c  mov     rcx, rdi
0x18001a41f  mov     eax, [r8+48h]
0x18001a423  add     r8, 8
0x18001a427  mov     [rbp+57h+arg_8], eax
0x18001a42a  lea     rax, [rbp+57h+arg_0]
0x18001a42e  mov     [rsp+110h+var_E0], rax
0x18001a433  lea     rax, [rbp+57h+arg_8]
0x18001a437  mov     [rsp+110h+var_E8], rax
0x18001a43c  lea     rax, [rbp+57h+arg_10]
0x18001a440  mov     [rsp+110h+var_F0], rax
0x18001a445  mov     [rbp+57h+arg_10], 1000800h
0x18001a44d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a452  mov     rcx, rbx
0x18001a455  add     rsp, 100h
0x18001a45c  pop     rdi
0x18001a45d  pop     rbx
0x18001a45e  pop     rbp
0x18001a45f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
