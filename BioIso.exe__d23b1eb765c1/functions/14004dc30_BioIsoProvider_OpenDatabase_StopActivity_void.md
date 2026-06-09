# BioIsoProvider::OpenDatabase::StopActivity(void)

- ea: `0x14004dc30`
- end: `0x14004de5d`
- name: `?StopActivity@OpenDatabase@BioIsoProvider@@MEAAXXZ`
- size: `557`
- prototype: `void __fastcall(BioIsoProvider::OpenDatabase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001bc4`
- `0x140001d7c`
- `0x1400022c0`
- `0x14000d990`
- `0x1400126a4`
- `0x140013728`
- `0x14004dc30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004ddf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004ddf8`

## pseudocode

```c
void __fastcall BioIsoProvider::OpenDatabase::StopActivity(BioIsoProvider::OpenDatabase *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r8
  _DWORD *v6; // r9
  __int64 v7; // r9
  __int64 v8; // r8
  _DWORD *v9; // rdi
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  int *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  int *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  int *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v5, v6) )
    {
      v8 = *((_QWORD *)this + 34);
      v17 = (int *)*((_QWORD *)v4 + 15);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (int *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (int *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned __int8 *)&unk_14009C610,
        (const GUID *)(v8 + 8),
        v7,
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
    wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v13 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v9,
        (unsigned __int8 *)&dword_14009C734,
        (const GUID *)(v13 + 8),
        v14,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14004dc30  push    rbp
0x14004dc32  push    rbx
0x14004dc33  push    rdi
0x14004dc34  lea     rbp, [rsp-47h]
0x14004dc39  sub     rsp, 100h
0x14004dc40  mov     rdi, [rcx+110h]
0x14004dc47  mov     rbx, rcx
0x14004dc4a  mov     eax, [rdi+48h]
0x14004dc4d  test    eax, eax
0x14004dc4f  jns     loc_14004DDCD
0x14004dc55  add     rdi, 50h ; 'P'
0x14004dc59  cmp     eax, [rdi+8]
0x14004dc5c  jnz     loc_14004DDCD
0x14004dc62  test    rdi, rdi
0x14004dc65  jz      loc_14004DDCD
0x14004dc6b  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004dc70  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004dc75  mov     r9, [rax+8]
0x14004dc79  mov     eax, [r9]
0x14004dc7c  cmp     eax, 5
0x14004dc7f  jbe     loc_14004DE4B
0x14004dc85  mov     rdx, 400000000000h
0x14004dc8f  mov     rcx, r9
0x14004dc92  call    _tlgKeywordOn
0x14004dc97  test    al, al
0x14004dc99  jz      loc_14004DE4B
0x14004dc9f  mov     rax, [rdi+78h]
0x14004dca3  lea     rdx, unk_14009C610
0x14004dcaa  mov     r8, [rbx+110h]
0x14004dcb1  mov     rcx, r9
0x14004dcb4  mov     [rbp+57h+var_68], rax
0x14004dcb8  add     r8, 8
0x14004dcbc  mov     rax, [rdi+70h]
0x14004dcc0  mov     [rbp+57h+var_60], rax
0x14004dcc4  mov     eax, [rdi+68h]
0x14004dcc7  mov     [rbp+57h+arg_0], eax
0x14004dcca  mov     rax, [rdi+60h]
0x14004dcce  mov     [rbp+57h+var_58], rax
0x14004dcd2  mov     rax, [rdi+58h]
0x14004dcd6  mov     [rbp+57h+var_50], rax
0x14004dcda  mov     eax, [rdi+50h]
0x14004dcdd  mov     [rbp+57h+arg_8], eax
0x14004dce0  mov     rax, [rdi+48h]
0x14004dce4  mov     [rbp+57h+var_48], rax
0x14004dce8  mov     eax, [rdi+20h]
0x14004dceb  mov     dword ptr [rbp+57h+arg_10], eax
0x14004dcee  mov     rax, [rdi+18h]
0x14004dcf2  mov     [rbp+57h+var_40], rax
0x14004dcf6  mov     eax, [rdi]
0x14004dcf8  mov     [rbp+57h+arg_18], eax
0x14004dcfb  mov     rax, [rdi+80h]
0x14004dd02  mov     [rbp+57h+var_38], rax
0x14004dd06  mov     eax, [rdi+40h]
0x14004dd09  mov     [rbp+57h+var_70], eax
0x14004dd0c  mov     rax, [rdi+38h]
0x14004dd10  mov     [rbp+57h+var_30], rax
0x14004dd14  mov     eax, [rdi+8]
0x14004dd17  mov     [rbp+57h+var_6C], eax
0x14004dd1a  lea     rax, [rbp+57h+var_68]
0x14004dd1e  mov     [rsp+110h+var_78], rax
0x14004dd26  lea     rax, [rbp+57h+var_60]
0x14004dd2a  mov     [rsp+110h+var_80], rax
0x14004dd32  lea     rax, [rbp+57h+arg_0]
0x14004dd36  mov     [rsp+110h+var_88], rax
0x14004dd3e  lea     rax, [rbp+57h+var_58]
0x14004dd42  mov     [rsp+110h+var_90], rax
0x14004dd4a  lea     rax, [rbp+57h+var_50]
0x14004dd4e  mov     [rsp+110h+var_98], rax
0x14004dd53  lea     rax, [rbp+57h+arg_8]
0x14004dd57  mov     [rsp+110h+var_A0], rax
0x14004dd5c  lea     rax, [rbp+57h+var_48]
0x14004dd60  mov     [rsp+110h+var_A8], rax
0x14004dd65  lea     rax, [rbp+57h+arg_10]
0x14004dd69  mov     [rsp+110h+var_B0], rax
0x14004dd6e  lea     rax, [rbp+57h+var_40]
0x14004dd72  mov     [rsp+110h+var_B8], rax
0x14004dd77  lea     rax, [rbp+57h+arg_18]
0x14004dd7b  mov     [rsp+110h+var_C0], rax
0x14004dd80  lea     rax, [rbp+57h+var_38]
0x14004dd84  mov     [rsp+110h+var_C8], rax
0x14004dd89  lea     rax, [rbp+57h+var_70]
0x14004dd8d  mov     [rsp+110h+var_D0], rax
0x14004dd92  lea     rax, [rbp+57h+var_30]
0x14004dd96  mov     [rsp+110h+var_D8], rax
0x14004dd9b  lea     rax, [rbp+57h+var_6C]
0x14004dd9f  mov     [rsp+110h+var_E0], rax
0x14004dda4  lea     rax, [rbp+57h+var_28]
0x14004dda8  mov     [rsp+110h+var_E8], rax
0x14004ddad  lea     rax, [rbp+57h+var_20]
0x14004ddb1  mov     [rsp+110h+var_F0], rax
0x14004ddb6  mov     [rbp+57h+var_28], 1000000h
0x14004ddbe  mov     [rbp+57h+var_20], 0
0x14004ddc6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14004ddcb  jmp     short loc_14004DE4B
0x14004ddcd  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004ddd2  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004ddd7  mov     rdi, [rax+8]
0x14004dddb  mov     eax, [rdi]
0x14004dddd  cmp     eax, 5
0x14004dde0  jbe     short loc_14004DE4B
0x14004dde2  mov     rdx, 400000000000h
0x14004ddec  mov     rcx, rdi
0x14004ddef  call    _tlgKeywordOn
0x14004ddf4  test    al, al
0x14004ddf6  jz      short loc_14004DE4B
0x14004ddf8  call    cs:__imp_GetCurrentThreadId
0x14004ddff  nop     dword ptr [rax+rax+00h]
0x14004de04  mov     r8, [rbx+110h]
0x14004de0b  lea     rdx, dword_14009C734
0x14004de12  mov     [rbp+57h+arg_0], eax
0x14004de15  mov     rcx, rdi
0x14004de18  mov     eax, [r8+48h]
0x14004de1c  add     r8, 8
0x14004de20  mov     [rbp+57h+arg_8], eax
0x14004de23  lea     rax, [rbp+57h+arg_0]
0x14004de27  mov     [rsp+110h+var_E0], rax
0x14004de2c  lea     rax, [rbp+57h+arg_8]
0x14004de30  mov     [rsp+110h+var_E8], rax
0x14004de35  lea     rax, [rbp+57h+arg_10]
0x14004de39  mov     [rsp+110h+var_F0], rax
0x14004de3e  mov     [rbp+57h+arg_10], 0
0x14004de46  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004de4b  mov     rcx, rbx
0x14004de4e  add     rsp, 100h
0x14004de55  pop     rdi
0x14004de56  pop     rbx
0x14004de57  pop     rbp
0x14004de58  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
