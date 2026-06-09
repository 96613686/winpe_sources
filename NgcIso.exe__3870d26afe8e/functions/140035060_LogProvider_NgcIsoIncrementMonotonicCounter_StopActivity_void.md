# LogProvider::NgcIsoIncrementMonotonicCounter::StopActivity(void)

- ea: `0x140035060`
- end: `0x140035285`
- name: `?StopActivity@NgcIsoIncrementMonotonicCounter@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::NgcIsoIncrementMonotonicCounter *__hidden this)`
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
- `0x140035060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035222`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoIncrementMonotonicCounter::StopActivity(
        LogProvider::NgcIsoIncrementMonotonicCounter *this)
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
        (unsigned __int8 *)byte_14008557F,
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
        (unsigned int)&word_1400856B6,
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
0x140035060  push    rbp
0x140035062  push    rbx
0x140035063  push    rdi
0x140035064  lea     rbp, [rsp-47h]
0x140035069  sub     rsp, 100h
0x140035070  mov     rdi, [rcx+110h]
0x140035077  mov     rbx, rcx
0x14003507a  mov     eax, [rdi+48h]
0x14003507d  test    eax, eax
0x14003507f  jns     loc_1400351F8
0x140035085  add     rdi, 50h ; 'P'
0x140035089  cmp     eax, [rdi+8]
0x14003508c  jnz     loc_1400351F8
0x140035092  test    rdi, rdi
0x140035095  jz      loc_1400351F8
0x14003509b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400350a0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400350a5  mov     r9, rax
0x1400350a8  mov     ecx, [rax]
0x1400350aa  cmp     ecx, 4
0x1400350ad  jbe     loc_140035273
0x1400350b3  mov     rdx, 400000000000h
0x1400350bd  mov     rcx, rax
0x1400350c0  call    _tlgKeywordOn
0x1400350c5  test    al, al
0x1400350c7  jz      loc_140035273
0x1400350cd  mov     rax, [rdi+70h]
0x1400350d1  lea     rdx, byte_14008557F
0x1400350d8  mov     rcx, [rdi+78h]
0x1400350dc  mov     r8, [rbx+110h]
0x1400350e3  mov     [rbp+57h+var_60], rax
0x1400350e7  add     r8, 8
0x1400350eb  mov     eax, [rdi+68h]
0x1400350ee  mov     [rbp+57h+arg_0], eax
0x1400350f1  mov     rax, [rdi+60h]
0x1400350f5  mov     [rbp+57h+var_58], rax
0x1400350f9  mov     rax, [rdi+58h]
0x1400350fd  mov     [rbp+57h+var_50], rax
0x140035101  mov     eax, [rdi+50h]
0x140035104  mov     [rbp+57h+arg_8], eax
0x140035107  mov     rax, [rdi+48h]
0x14003510b  mov     [rbp+57h+var_48], rax
0x14003510f  mov     eax, [rdi+20h]
0x140035112  mov     dword ptr [rbp+57h+arg_10], eax
0x140035115  mov     rax, [rdi+18h]
0x140035119  mov     [rbp+57h+var_40], rax
0x14003511d  mov     eax, [rdi]
0x14003511f  mov     [rbp+57h+arg_18], eax
0x140035122  mov     rax, [rdi+80h]
0x140035129  mov     [rbp+57h+var_38], rax
0x14003512d  mov     eax, [rdi+40h]
0x140035130  mov     [rbp+57h+var_70], eax
0x140035133  mov     rax, [rdi+38h]
0x140035137  mov     [rbp+57h+var_30], rax
0x14003513b  mov     eax, [rdi+8]
0x14003513e  mov     [rbp+57h+var_6C], eax
0x140035141  mov     eax, 1000000h
0x140035146  mov     [rbp+57h+var_28], rax
0x14003514a  mov     [rbp+57h+var_20], rax
0x14003514e  lea     rax, [rbp+57h+var_68]
0x140035152  mov     [rsp+110h+var_78], rax
0x14003515a  lea     rax, [rbp+57h+var_60]
0x14003515e  mov     [rsp+110h+var_80], rax
0x140035166  lea     rax, [rbp+57h+arg_0]
0x14003516a  mov     [rsp+110h+var_88], rax
0x140035172  lea     rax, [rbp+57h+var_58]
0x140035176  mov     [rsp+110h+var_90], rax
0x14003517e  lea     rax, [rbp+57h+var_50]
0x140035182  mov     [rsp+110h+var_98], rax
0x140035187  lea     rax, [rbp+57h+arg_8]
0x14003518b  mov     [rsp+110h+var_A0], rax
0x140035190  lea     rax, [rbp+57h+var_48]
0x140035194  mov     [rsp+110h+var_A8], rax
0x140035199  lea     rax, [rbp+57h+arg_10]
0x14003519d  mov     [rsp+110h+var_B0], rax
0x1400351a2  lea     rax, [rbp+57h+var_40]
0x1400351a6  mov     [rsp+110h+var_B8], rax
0x1400351ab  lea     rax, [rbp+57h+arg_18]
0x1400351af  mov     [rsp+110h+var_C0], rax
0x1400351b4  lea     rax, [rbp+57h+var_38]
0x1400351b8  mov     [rsp+110h+var_C8], rax
0x1400351bd  lea     rax, [rbp+57h+var_70]
0x1400351c1  mov     [rsp+110h+var_D0], rax
0x1400351c6  lea     rax, [rbp+57h+var_30]
0x1400351ca  mov     [rsp+110h+var_D8], rax
0x1400351cf  lea     rax, [rbp+57h+var_6C]
0x1400351d3  mov     [rsp+110h+var_E0], rax
0x1400351d8  lea     rax, [rbp+57h+var_28]
0x1400351dc  mov     [rsp+110h+var_E8], rax
0x1400351e1  lea     rax, [rbp+57h+var_20]
0x1400351e5  mov     [rbp+57h+var_68], rcx
0x1400351e9  mov     rcx, r9
0x1400351ec  mov     [rsp+110h+var_F0], rax
0x1400351f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400351f6  jmp     short loc_140035273
0x1400351f8  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400351fd  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140035202  mov     rdi, rax
0x140035205  mov     ecx, [rax]
0x140035207  cmp     ecx, 4
0x14003520a  jbe     short loc_140035273
0x14003520c  mov     rdx, 400000000000h
0x140035216  mov     rcx, rax
0x140035219  call    _tlgKeywordOn
0x14003521e  test    al, al
0x140035220  jz      short loc_140035273
0x140035222  call    cs:__imp_GetCurrentThreadId
0x140035228  mov     r8, [rbx+110h]
0x14003522f  lea     rdx, word_1400856B6
0x140035236  mov     [rbp+57h+arg_0], eax
0x140035239  xor     r9d, r9d
0x14003523c  mov     rcx, rdi
0x14003523f  mov     eax, [r8+48h]
0x140035243  add     r8, 8
0x140035247  mov     [rbp+57h+arg_8], eax
0x14003524a  mov     eax, 1000000h
0x14003524f  mov     [rbp+57h+arg_10], rax
0x140035253  lea     rax, [rbp+57h+arg_0]
0x140035257  mov     [rsp+110h+var_E0], rax
0x14003525c  lea     rax, [rbp+57h+arg_8]
0x140035260  mov     [rsp+110h+var_E8], rax
0x140035265  lea     rax, [rbp+57h+arg_10]
0x140035269  mov     [rsp+110h+var_F0], rax
0x14003526e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140035273  mov     rcx, rbx
0x140035276  add     rsp, 100h
0x14003527d  pop     rdi
0x14003527e  pop     rbx
0x14003527f  pop     rbp
0x140035280  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
