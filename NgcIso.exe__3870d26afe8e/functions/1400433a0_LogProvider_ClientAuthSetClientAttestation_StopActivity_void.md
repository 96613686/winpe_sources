# LogProvider::ClientAuthSetClientAttestation::StopActivity(void)

- ea: `0x1400433a0`
- end: `0x1400435c5`
- name: `?StopActivity@ClientAuthSetClientAttestation@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::ClientAuthSetClientAttestation *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x1400433a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043562`

## pseudocode

```c
void __fastcall LogProvider::ClientAuthSetClientAttestation::StopActivity(
        LogProvider::ClientAuthSetClientAttestation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LogProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (unsigned __int8 *)byte_14008DA31,
        (const GUID *)(v10 + 8),
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&byte_14008DB67,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1400433a0  push    rbp
0x1400433a2  push    rbx
0x1400433a3  push    rdi
0x1400433a4  lea     rbp, [rsp-47h]
0x1400433a9  sub     rsp, 100h
0x1400433b0  mov     rdi, [rcx+110h]
0x1400433b7  mov     rbx, rcx
0x1400433ba  mov     eax, [rdi+48h]
0x1400433bd  test    eax, eax
0x1400433bf  jns     loc_140043538
0x1400433c5  add     rdi, 50h ; 'P'
0x1400433c9  cmp     eax, [rdi+8]
0x1400433cc  jnz     loc_140043538
0x1400433d2  test    rdi, rdi
0x1400433d5  jz      loc_140043538
0x1400433db  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400433e0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400433e5  mov     r9, rax
0x1400433e8  mov     ecx, [rax]
0x1400433ea  cmp     ecx, 4
0x1400433ed  jbe     loc_1400435B3
0x1400433f3  mov     rdx, 400000000000h
0x1400433fd  mov     rcx, rax
0x140043400  call    _tlgKeywordOn
0x140043405  test    al, al
0x140043407  jz      loc_1400435B3
0x14004340d  mov     rax, [rdi+70h]
0x140043411  lea     rdx, byte_14008DA31
0x140043418  mov     rcx, [rdi+78h]
0x14004341c  mov     r8, [rbx+110h]
0x140043423  mov     [rbp+57h+var_60], rax
0x140043427  add     r8, 8
0x14004342b  mov     eax, [rdi+68h]
0x14004342e  mov     [rbp+57h+arg_0], eax
0x140043431  mov     rax, [rdi+60h]
0x140043435  mov     [rbp+57h+var_58], rax
0x140043439  mov     rax, [rdi+58h]
0x14004343d  mov     [rbp+57h+var_50], rax
0x140043441  mov     eax, [rdi+50h]
0x140043444  mov     [rbp+57h+arg_8], eax
0x140043447  mov     rax, [rdi+48h]
0x14004344b  mov     [rbp+57h+var_48], rax
0x14004344f  mov     eax, [rdi+20h]
0x140043452  mov     dword ptr [rbp+57h+arg_10], eax
0x140043455  mov     rax, [rdi+18h]
0x140043459  mov     [rbp+57h+var_40], rax
0x14004345d  mov     eax, [rdi]
0x14004345f  mov     [rbp+57h+arg_18], eax
0x140043462  mov     rax, [rdi+80h]
0x140043469  mov     [rbp+57h+var_38], rax
0x14004346d  mov     eax, [rdi+40h]
0x140043470  mov     [rbp+57h+var_70], eax
0x140043473  mov     rax, [rdi+38h]
0x140043477  mov     [rbp+57h+var_30], rax
0x14004347b  mov     eax, [rdi+8]
0x14004347e  mov     [rbp+57h+var_6C], eax
0x140043481  mov     eax, 1000000h
0x140043486  mov     [rbp+57h+var_28], rax
0x14004348a  mov     [rbp+57h+var_20], rax
0x14004348e  lea     rax, [rbp+57h+var_68]
0x140043492  mov     [rsp+110h+var_78], rax
0x14004349a  lea     rax, [rbp+57h+var_60]
0x14004349e  mov     [rsp+110h+var_80], rax
0x1400434a6  lea     rax, [rbp+57h+arg_0]
0x1400434aa  mov     [rsp+110h+var_88], rax
0x1400434b2  lea     rax, [rbp+57h+var_58]
0x1400434b6  mov     [rsp+110h+var_90], rax
0x1400434be  lea     rax, [rbp+57h+var_50]
0x1400434c2  mov     [rsp+110h+var_98], rax
0x1400434c7  lea     rax, [rbp+57h+arg_8]
0x1400434cb  mov     [rsp+110h+var_A0], rax
0x1400434d0  lea     rax, [rbp+57h+var_48]
0x1400434d4  mov     [rsp+110h+var_A8], rax
0x1400434d9  lea     rax, [rbp+57h+arg_10]
0x1400434dd  mov     [rsp+110h+var_B0], rax
0x1400434e2  lea     rax, [rbp+57h+var_40]
0x1400434e6  mov     [rsp+110h+var_B8], rax
0x1400434eb  lea     rax, [rbp+57h+arg_18]
0x1400434ef  mov     [rsp+110h+var_C0], rax
0x1400434f4  lea     rax, [rbp+57h+var_38]
0x1400434f8  mov     [rsp+110h+var_C8], rax
0x1400434fd  lea     rax, [rbp+57h+var_70]
0x140043501  mov     [rsp+110h+var_D0], rax
0x140043506  lea     rax, [rbp+57h+var_30]
0x14004350a  mov     [rsp+110h+var_D8], rax
0x14004350f  lea     rax, [rbp+57h+var_6C]
0x140043513  mov     [rsp+110h+var_E0], rax
0x140043518  lea     rax, [rbp+57h+var_28]
0x14004351c  mov     [rsp+110h+var_E8], rax
0x140043521  lea     rax, [rbp+57h+var_20]
0x140043525  mov     [rbp+57h+var_68], rcx
0x140043529  mov     rcx, r9
0x14004352c  mov     [rsp+110h+var_F0], rax
0x140043531  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140043536  jmp     short loc_1400435B3
0x140043538  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004353d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140043542  mov     rdi, rax
0x140043545  mov     ecx, [rax]
0x140043547  cmp     ecx, 4
0x14004354a  jbe     short loc_1400435B3
0x14004354c  mov     rdx, 400000000000h
0x140043556  mov     rcx, rax
0x140043559  call    _tlgKeywordOn
0x14004355e  test    al, al
0x140043560  jz      short loc_1400435B3
0x140043562  call    cs:__imp_GetCurrentThreadId
0x140043568  mov     r8, [rbx+110h]
0x14004356f  lea     rdx, byte_14008DB67
0x140043576  mov     [rbp+57h+arg_0], eax
0x140043579  xor     r9d, r9d
0x14004357c  mov     rcx, rdi
0x14004357f  mov     eax, [r8+48h]
0x140043583  add     r8, 8
0x140043587  mov     [rbp+57h+arg_8], eax
0x14004358a  mov     eax, 1000000h
0x14004358f  mov     [rbp+57h+arg_10], rax
0x140043593  lea     rax, [rbp+57h+arg_0]
0x140043597  mov     [rsp+110h+var_E0], rax
0x14004359c  lea     rax, [rbp+57h+arg_8]
0x1400435a0  mov     [rsp+110h+var_E8], rax
0x1400435a5  lea     rax, [rbp+57h+arg_10]
0x1400435a9  mov     [rsp+110h+var_F0], rax
0x1400435ae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400435b3  mov     rcx, rbx
0x1400435b6  add     rsp, 100h
0x1400435bd  pop     rdi
0x1400435be  pop     rbx
0x1400435bf  pop     rbp
0x1400435c0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
