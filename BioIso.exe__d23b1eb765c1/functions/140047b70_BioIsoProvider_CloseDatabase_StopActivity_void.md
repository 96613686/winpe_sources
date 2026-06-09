# BioIsoProvider::CloseDatabase::StopActivity(void)

- ea: `0x140047b70`
- end: `0x140047d9d`
- name: `?StopActivity@CloseDatabase@BioIsoProvider@@MEAAXXZ`
- size: `557`
- prototype: `void __fastcall(BioIsoProvider::CloseDatabase *__hidden this)`
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
- `0x140047b70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047d38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047d38`

## pseudocode

```c
void __fastcall BioIsoProvider::CloseDatabase::StopActivity(BioIsoProvider::CloseDatabase *this)
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
        (unsigned __int8 *)&unk_14009C1C8,
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
        (unsigned __int8 *)byte_14009C2ED,
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
0x140047b70  push    rbp
0x140047b72  push    rbx
0x140047b73  push    rdi
0x140047b74  lea     rbp, [rsp-47h]
0x140047b79  sub     rsp, 100h
0x140047b80  mov     rdi, [rcx+110h]
0x140047b87  mov     rbx, rcx
0x140047b8a  mov     eax, [rdi+48h]
0x140047b8d  test    eax, eax
0x140047b8f  jns     loc_140047D0D
0x140047b95  add     rdi, 50h ; 'P'
0x140047b99  cmp     eax, [rdi+8]
0x140047b9c  jnz     loc_140047D0D
0x140047ba2  test    rdi, rdi
0x140047ba5  jz      loc_140047D0D
0x140047bab  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140047bb0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140047bb5  mov     r9, [rax+8]
0x140047bb9  mov     eax, [r9]
0x140047bbc  cmp     eax, 5
0x140047bbf  jbe     loc_140047D8B
0x140047bc5  mov     rdx, 400000000000h
0x140047bcf  mov     rcx, r9
0x140047bd2  call    _tlgKeywordOn
0x140047bd7  test    al, al
0x140047bd9  jz      loc_140047D8B
0x140047bdf  mov     rax, [rdi+78h]
0x140047be3  lea     rdx, unk_14009C1C8
0x140047bea  mov     r8, [rbx+110h]
0x140047bf1  mov     rcx, r9
0x140047bf4  mov     [rbp+57h+var_68], rax
0x140047bf8  add     r8, 8
0x140047bfc  mov     rax, [rdi+70h]
0x140047c00  mov     [rbp+57h+var_60], rax
0x140047c04  mov     eax, [rdi+68h]
0x140047c07  mov     [rbp+57h+arg_0], eax
0x140047c0a  mov     rax, [rdi+60h]
0x140047c0e  mov     [rbp+57h+var_58], rax
0x140047c12  mov     rax, [rdi+58h]
0x140047c16  mov     [rbp+57h+var_50], rax
0x140047c1a  mov     eax, [rdi+50h]
0x140047c1d  mov     [rbp+57h+arg_8], eax
0x140047c20  mov     rax, [rdi+48h]
0x140047c24  mov     [rbp+57h+var_48], rax
0x140047c28  mov     eax, [rdi+20h]
0x140047c2b  mov     dword ptr [rbp+57h+arg_10], eax
0x140047c2e  mov     rax, [rdi+18h]
0x140047c32  mov     [rbp+57h+var_40], rax
0x140047c36  mov     eax, [rdi]
0x140047c38  mov     [rbp+57h+arg_18], eax
0x140047c3b  mov     rax, [rdi+80h]
0x140047c42  mov     [rbp+57h+var_38], rax
0x140047c46  mov     eax, [rdi+40h]
0x140047c49  mov     [rbp+57h+var_70], eax
0x140047c4c  mov     rax, [rdi+38h]
0x140047c50  mov     [rbp+57h+var_30], rax
0x140047c54  mov     eax, [rdi+8]
0x140047c57  mov     [rbp+57h+var_6C], eax
0x140047c5a  lea     rax, [rbp+57h+var_68]
0x140047c5e  mov     [rsp+110h+var_78], rax
0x140047c66  lea     rax, [rbp+57h+var_60]
0x140047c6a  mov     [rsp+110h+var_80], rax
0x140047c72  lea     rax, [rbp+57h+arg_0]
0x140047c76  mov     [rsp+110h+var_88], rax
0x140047c7e  lea     rax, [rbp+57h+var_58]
0x140047c82  mov     [rsp+110h+var_90], rax
0x140047c8a  lea     rax, [rbp+57h+var_50]
0x140047c8e  mov     [rsp+110h+var_98], rax
0x140047c93  lea     rax, [rbp+57h+arg_8]
0x140047c97  mov     [rsp+110h+var_A0], rax
0x140047c9c  lea     rax, [rbp+57h+var_48]
0x140047ca0  mov     [rsp+110h+var_A8], rax
0x140047ca5  lea     rax, [rbp+57h+arg_10]
0x140047ca9  mov     [rsp+110h+var_B0], rax
0x140047cae  lea     rax, [rbp+57h+var_40]
0x140047cb2  mov     [rsp+110h+var_B8], rax
0x140047cb7  lea     rax, [rbp+57h+arg_18]
0x140047cbb  mov     [rsp+110h+var_C0], rax
0x140047cc0  lea     rax, [rbp+57h+var_38]
0x140047cc4  mov     [rsp+110h+var_C8], rax
0x140047cc9  lea     rax, [rbp+57h+var_70]
0x140047ccd  mov     [rsp+110h+var_D0], rax
0x140047cd2  lea     rax, [rbp+57h+var_30]
0x140047cd6  mov     [rsp+110h+var_D8], rax
0x140047cdb  lea     rax, [rbp+57h+var_6C]
0x140047cdf  mov     [rsp+110h+var_E0], rax
0x140047ce4  lea     rax, [rbp+57h+var_28]
0x140047ce8  mov     [rsp+110h+var_E8], rax
0x140047ced  lea     rax, [rbp+57h+var_20]
0x140047cf1  mov     [rsp+110h+var_F0], rax
0x140047cf6  mov     [rbp+57h+var_28], 1000000h
0x140047cfe  mov     [rbp+57h+var_20], 0
0x140047d06  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140047d0b  jmp     short loc_140047D8B
0x140047d0d  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140047d12  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140047d17  mov     rdi, [rax+8]
0x140047d1b  mov     eax, [rdi]
0x140047d1d  cmp     eax, 5
0x140047d20  jbe     short loc_140047D8B
0x140047d22  mov     rdx, 400000000000h
0x140047d2c  mov     rcx, rdi
0x140047d2f  call    _tlgKeywordOn
0x140047d34  test    al, al
0x140047d36  jz      short loc_140047D8B
0x140047d38  call    cs:__imp_GetCurrentThreadId
0x140047d3f  nop     dword ptr [rax+rax+00h]
0x140047d44  mov     r8, [rbx+110h]
0x140047d4b  lea     rdx, byte_14009C2ED
0x140047d52  mov     [rbp+57h+arg_0], eax
0x140047d55  mov     rcx, rdi
0x140047d58  mov     eax, [r8+48h]
0x140047d5c  add     r8, 8
0x140047d60  mov     [rbp+57h+arg_8], eax
0x140047d63  lea     rax, [rbp+57h+arg_0]
0x140047d67  mov     [rsp+110h+var_E0], rax
0x140047d6c  lea     rax, [rbp+57h+arg_8]
0x140047d70  mov     [rsp+110h+var_E8], rax
0x140047d75  lea     rax, [rbp+57h+arg_10]
0x140047d79  mov     [rsp+110h+var_F0], rax
0x140047d7e  mov     [rbp+57h+arg_10], 0
0x140047d86  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140047d8b  mov     rcx, rbx
0x140047d8e  add     rsp, 100h
0x140047d95  pop     rdi
0x140047d96  pop     rbx
0x140047d97  pop     rbp
0x140047d98  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
