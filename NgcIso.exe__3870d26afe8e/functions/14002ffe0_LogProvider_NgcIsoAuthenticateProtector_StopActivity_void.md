# LogProvider::NgcIsoAuthenticateProtector::StopActivity(void)

- ea: `0x14002ffe0`
- end: `0x140030205`
- name: `?StopActivity@NgcIsoAuthenticateProtector@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::NgcIsoAuthenticateProtector *__hidden this)`
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
- `0x14002ffe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400301a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400301a2`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoAuthenticateProtector::StopActivity(LogProvider::NgcIsoAuthenticateProtector *this)
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
        (unsigned __int8 *)&unk_14008A018,
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
        (unsigned int)byte_14008A14B,
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
0x14002ffe0  push    rbp
0x14002ffe2  push    rbx
0x14002ffe3  push    rdi
0x14002ffe4  lea     rbp, [rsp-47h]
0x14002ffe9  sub     rsp, 100h
0x14002fff0  mov     rdi, [rcx+110h]
0x14002fff7  mov     rbx, rcx
0x14002fffa  mov     eax, [rdi+48h]
0x14002fffd  test    eax, eax
0x14002ffff  jns     loc_140030178
0x140030005  add     rdi, 50h ; 'P'
0x140030009  cmp     eax, [rdi+8]
0x14003000c  jnz     loc_140030178
0x140030012  test    rdi, rdi
0x140030015  jz      loc_140030178
0x14003001b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140030020  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140030025  mov     r9, rax
0x140030028  mov     ecx, [rax]
0x14003002a  cmp     ecx, 4
0x14003002d  jbe     loc_1400301F3
0x140030033  mov     rdx, 400000000000h
0x14003003d  mov     rcx, rax
0x140030040  call    _tlgKeywordOn
0x140030045  test    al, al
0x140030047  jz      loc_1400301F3
0x14003004d  mov     rax, [rdi+70h]
0x140030051  lea     rdx, unk_14008A018
0x140030058  mov     rcx, [rdi+78h]
0x14003005c  mov     r8, [rbx+110h]
0x140030063  mov     [rbp+57h+var_60], rax
0x140030067  add     r8, 8
0x14003006b  mov     eax, [rdi+68h]
0x14003006e  mov     [rbp+57h+arg_0], eax
0x140030071  mov     rax, [rdi+60h]
0x140030075  mov     [rbp+57h+var_58], rax
0x140030079  mov     rax, [rdi+58h]
0x14003007d  mov     [rbp+57h+var_50], rax
0x140030081  mov     eax, [rdi+50h]
0x140030084  mov     [rbp+57h+arg_8], eax
0x140030087  mov     rax, [rdi+48h]
0x14003008b  mov     [rbp+57h+var_48], rax
0x14003008f  mov     eax, [rdi+20h]
0x140030092  mov     dword ptr [rbp+57h+arg_10], eax
0x140030095  mov     rax, [rdi+18h]
0x140030099  mov     [rbp+57h+var_40], rax
0x14003009d  mov     eax, [rdi]
0x14003009f  mov     [rbp+57h+arg_18], eax
0x1400300a2  mov     rax, [rdi+80h]
0x1400300a9  mov     [rbp+57h+var_38], rax
0x1400300ad  mov     eax, [rdi+40h]
0x1400300b0  mov     [rbp+57h+var_70], eax
0x1400300b3  mov     rax, [rdi+38h]
0x1400300b7  mov     [rbp+57h+var_30], rax
0x1400300bb  mov     eax, [rdi+8]
0x1400300be  mov     [rbp+57h+var_6C], eax
0x1400300c1  mov     eax, 1000000h
0x1400300c6  mov     [rbp+57h+var_28], rax
0x1400300ca  mov     [rbp+57h+var_20], rax
0x1400300ce  lea     rax, [rbp+57h+var_68]
0x1400300d2  mov     [rsp+110h+var_78], rax
0x1400300da  lea     rax, [rbp+57h+var_60]
0x1400300de  mov     [rsp+110h+var_80], rax
0x1400300e6  lea     rax, [rbp+57h+arg_0]
0x1400300ea  mov     [rsp+110h+var_88], rax
0x1400300f2  lea     rax, [rbp+57h+var_58]
0x1400300f6  mov     [rsp+110h+var_90], rax
0x1400300fe  lea     rax, [rbp+57h+var_50]
0x140030102  mov     [rsp+110h+var_98], rax
0x140030107  lea     rax, [rbp+57h+arg_8]
0x14003010b  mov     [rsp+110h+var_A0], rax
0x140030110  lea     rax, [rbp+57h+var_48]
0x140030114  mov     [rsp+110h+var_A8], rax
0x140030119  lea     rax, [rbp+57h+arg_10]
0x14003011d  mov     [rsp+110h+var_B0], rax
0x140030122  lea     rax, [rbp+57h+var_40]
0x140030126  mov     [rsp+110h+var_B8], rax
0x14003012b  lea     rax, [rbp+57h+arg_18]
0x14003012f  mov     [rsp+110h+var_C0], rax
0x140030134  lea     rax, [rbp+57h+var_38]
0x140030138  mov     [rsp+110h+var_C8], rax
0x14003013d  lea     rax, [rbp+57h+var_70]
0x140030141  mov     [rsp+110h+var_D0], rax
0x140030146  lea     rax, [rbp+57h+var_30]
0x14003014a  mov     [rsp+110h+var_D8], rax
0x14003014f  lea     rax, [rbp+57h+var_6C]
0x140030153  mov     [rsp+110h+var_E0], rax
0x140030158  lea     rax, [rbp+57h+var_28]
0x14003015c  mov     [rsp+110h+var_E8], rax
0x140030161  lea     rax, [rbp+57h+var_20]
0x140030165  mov     [rbp+57h+var_68], rcx
0x140030169  mov     rcx, r9
0x14003016c  mov     [rsp+110h+var_F0], rax
0x140030171  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140030176  jmp     short loc_1400301F3
0x140030178  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14003017d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140030182  mov     rdi, rax
0x140030185  mov     ecx, [rax]
0x140030187  cmp     ecx, 4
0x14003018a  jbe     short loc_1400301F3
0x14003018c  mov     rdx, 400000000000h
0x140030196  mov     rcx, rax
0x140030199  call    _tlgKeywordOn
0x14003019e  test    al, al
0x1400301a0  jz      short loc_1400301F3
0x1400301a2  call    cs:__imp_GetCurrentThreadId
0x1400301a8  mov     r8, [rbx+110h]
0x1400301af  lea     rdx, byte_14008A14B
0x1400301b6  mov     [rbp+57h+arg_0], eax
0x1400301b9  xor     r9d, r9d
0x1400301bc  mov     rcx, rdi
0x1400301bf  mov     eax, [r8+48h]
0x1400301c3  add     r8, 8
0x1400301c7  mov     [rbp+57h+arg_8], eax
0x1400301ca  mov     eax, 1000000h
0x1400301cf  mov     [rbp+57h+arg_10], rax
0x1400301d3  lea     rax, [rbp+57h+arg_0]
0x1400301d7  mov     [rsp+110h+var_E0], rax
0x1400301dc  lea     rax, [rbp+57h+arg_8]
0x1400301e0  mov     [rsp+110h+var_E8], rax
0x1400301e5  lea     rax, [rbp+57h+arg_10]
0x1400301e9  mov     [rsp+110h+var_F0], rax
0x1400301ee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400301f3  mov     rcx, rbx
0x1400301f6  add     rsp, 100h
0x1400301fd  pop     rdi
0x1400301fe  pop     rbx
0x1400301ff  pop     rbp
0x140030200  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
