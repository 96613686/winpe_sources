# BioIsoProvider::EngineDeactivate::StopActivity(void)

- ea: `0x140049f70`
- end: `0x14004a1a1`
- name: `?StopActivity@EngineDeactivate@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::EngineDeactivate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x140049f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004a13c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004a13c`

## pseudocode

```c
void __fastcall BioIsoProvider::EngineDeactivate::StopActivity(BioIsoProvider::EngineDeactivate *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  _DWORD *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  _DWORD *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp-70h] BYREF
  int *v17; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp-60h] BYREF
  int *v19; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v20; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+F8h] [rbp-48h] BYREF
  int *v22; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v23; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v26[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v27; // [rsp+150h] [rbp+10h] BYREF
  int v28; // [rsp+158h] [rbp+18h] BYREF
  __int64 v29; // [rsp+160h] [rbp+20h] BYREF
  int v30; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v5 > 5u )
    {
      v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v27 = v4[17];
      v28 = v4[4];
      v17 = (int *)*((_QWORD *)v4 + 15);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v29) = v4[26];
      v19 = (int *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v30 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = (int *)*((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)byte_14009DF15,
        v7 + 8,
        v6,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v30,
        &v20,
        &v19,
        (__int64)&v29,
        &v18,
        &v17,
        (__int64)&v28,
        (__int64)&v27,
        &v16);
    }
  }
  else
  {
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
    if ( *v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v10 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)qword_14009E060,
        (const GUID *)(v10 + 8),
        v11,
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
0x140049f70  push    rbp
0x140049f72  push    rbx
0x140049f73  push    rdi
0x140049f74  lea     rbp, [rsp+10h]
0x140049f79  sub     rsp, 130h
0x140049f80  mov     rdi, [rcx+110h]
0x140049f87  mov     rbx, rcx
0x140049f8a  mov     eax, [rdi+48h]
0x140049f8d  test    eax, eax
0x140049f8f  jns     loc_14004A127
0x140049f95  add     rdi, 50h ; 'P'
0x140049f99  cmp     eax, [rdi+8]
0x140049f9c  jnz     loc_14004A127
0x140049fa2  test    rdi, rdi
0x140049fa5  jz      loc_14004A127
0x140049fab  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140049fb0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140049fb5  mov     rcx, [rax+8]
0x140049fb9  mov     eax, [rcx]
0x140049fbb  cmp     eax, 5
0x140049fbe  jbe     loc_14004A18F
0x140049fc4  mov     rax, [rdi+30h]
0x140049fc8  lea     rdx, byte_14009DF15
0x140049fcf  mov     [rbp+var_70], rax
0x140049fd3  mov     eax, [rdi+44h]
0x140049fd6  mov     [rbp+arg_0], eax
0x140049fd9  mov     eax, [rdi+10h]
0x140049fdc  mov     [rbp+arg_8], eax
0x140049fdf  mov     rax, [rdi+78h]
0x140049fe3  mov     [rbp+var_68], rax
0x140049fe7  mov     rax, [rdi+70h]
0x140049feb  mov     [rbp+var_60], rax
0x140049fef  mov     eax, [rdi+68h]
0x140049ff2  mov     r8, [rbx+110h]
0x140049ff9  mov     dword ptr [rbp+arg_10], eax
0x140049ffc  add     r8, 8
0x14004a000  mov     rax, [rdi+60h]
0x14004a004  mov     [rbp+var_58], rax
0x14004a008  mov     rax, [rdi+58h]
0x14004a00c  mov     [rbp+var_50], rax
0x14004a010  mov     eax, [rdi+50h]
0x14004a013  mov     [rbp+arg_18], eax
0x14004a016  mov     rax, [rdi+48h]
0x14004a01a  mov     [rbp+var_48], rax
0x14004a01e  mov     eax, [rdi+20h]
0x14004a021  mov     [rbp+var_80], eax
0x14004a024  mov     rax, [rdi+18h]
0x14004a028  mov     [rbp+var_40], rax
0x14004a02c  mov     eax, [rdi]
0x14004a02e  mov     [rbp+var_7C], eax
0x14004a031  mov     rax, [rdi+80h]
0x14004a038  mov     [rbp+var_38], rax
0x14004a03c  mov     eax, [rdi+40h]
0x14004a03f  mov     [rbp+var_78], eax
0x14004a042  mov     rax, [rdi+38h]
0x14004a046  mov     [rbp+var_30], rax
0x14004a04a  mov     eax, [rdi+8]
0x14004a04d  mov     [rbp+var_74], eax
0x14004a050  lea     rax, [rbp+var_70]
0x14004a054  mov     [rsp+140h+var_90], rax
0x14004a05c  lea     rax, [rbp+arg_0]
0x14004a060  mov     [rsp+140h+var_98], rax
0x14004a068  lea     rax, [rbp+arg_8]
0x14004a06c  mov     [rsp+140h+var_A0], rax
0x14004a074  lea     rax, [rbp+var_68]
0x14004a078  mov     [rsp+140h+var_A8], rax
0x14004a080  lea     rax, [rbp+var_60]
0x14004a084  mov     [rsp+140h+var_B0], rax
0x14004a08c  lea     rax, [rbp+arg_10]
0x14004a090  mov     [rsp+140h+var_B8], rax
0x14004a098  lea     rax, [rbp+var_58]
0x14004a09c  mov     [rsp+140h+var_C0], rax
0x14004a0a4  lea     rax, [rbp+var_50]
0x14004a0a8  mov     [rsp+140h+var_C8], rax
0x14004a0ad  lea     rax, [rbp+arg_18]
0x14004a0b1  mov     [rsp+140h+var_D0], rax
0x14004a0b6  lea     rax, [rbp+var_48]
0x14004a0ba  mov     [rsp+140h+var_D8], rax
0x14004a0bf  lea     rax, [rbp+var_80]
0x14004a0c3  mov     [rsp+140h+var_E0], rax
0x14004a0c8  lea     rax, [rbp+var_40]
0x14004a0cc  mov     [rsp+140h+var_E8], rax
0x14004a0d1  lea     rax, [rbp+var_7C]
0x14004a0d5  mov     [rsp+140h+var_F0], rax
0x14004a0da  lea     rax, [rbp+var_38]
0x14004a0de  mov     [rsp+140h+var_F8], rax
0x14004a0e3  lea     rax, [rbp+var_78]
0x14004a0e7  mov     [rsp+140h+var_100], rax
0x14004a0ec  lea     rax, [rbp+var_30]
0x14004a0f0  mov     [rsp+140h+var_108], rax
0x14004a0f5  lea     rax, [rbp+var_74]
0x14004a0f9  mov     [rsp+140h+var_110], rax
0x14004a0fe  lea     rax, [rbp+var_28]
0x14004a102  mov     [rsp+140h+var_118], rax
0x14004a107  lea     rax, [rbp+var_20]
0x14004a10b  mov     [rsp+140h+var_120], rax
0x14004a110  mov     [rbp+var_28], 1000000h
0x14004a118  mov     [rbp+var_20], 0
0x14004a120  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004a125  jmp     short loc_14004A18F
0x14004a127  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004a12c  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004a131  mov     rdi, [rax+8]
0x14004a135  mov     eax, [rdi]
0x14004a137  cmp     eax, 5
0x14004a13a  jbe     short loc_14004A18F
0x14004a13c  call    cs:__imp_GetCurrentThreadId
0x14004a143  nop     dword ptr [rax+rax+00h]
0x14004a148  mov     r8, [rbx+110h]
0x14004a14f  lea     rdx, qword_14009E060
0x14004a156  mov     [rbp+arg_0], eax
0x14004a159  mov     rcx, rdi
0x14004a15c  mov     eax, [r8+48h]
0x14004a160  add     r8, 8
0x14004a164  mov     [rbp+arg_8], eax
0x14004a167  lea     rax, [rbp+arg_0]
0x14004a16b  mov     [rsp+140h+var_110], rax
0x14004a170  lea     rax, [rbp+arg_8]
0x14004a174  mov     [rsp+140h+var_118], rax
0x14004a179  lea     rax, [rbp+arg_10]
0x14004a17d  mov     [rsp+140h+var_120], rax
0x14004a182  mov     [rbp+arg_10], 0
0x14004a18a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004a18f  mov     rcx, rbx
0x14004a192  add     rsp, 130h
0x14004a199  pop     rdi
0x14004a19a  pop     rbx
0x14004a19b  pop     rbp
0x14004a19c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
