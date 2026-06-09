# BioIsoProvider::SensorPushDataToEngine::StopActivity(void)

- ea: `0x140050270`
- end: `0x1400504a1`
- name: `?StopActivity@SensorPushDataToEngine@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::SensorPushDataToEngine *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x140050270`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005043c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005043c`

## pseudocode

```c
void __fastcall BioIsoProvider::SensorPushDataToEngine::StopActivity(BioIsoProvider::SensorPushDataToEngine *this)
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
        (__int64)&byte_1400A0EBF,
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
        (unsigned __int8 *)&unk_1400A1010,
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
0x140050270  push    rbp
0x140050272  push    rbx
0x140050273  push    rdi
0x140050274  lea     rbp, [rsp+10h]
0x140050279  sub     rsp, 130h
0x140050280  mov     rdi, [rcx+110h]
0x140050287  mov     rbx, rcx
0x14005028a  mov     eax, [rdi+48h]
0x14005028d  test    eax, eax
0x14005028f  jns     loc_140050427
0x140050295  add     rdi, 50h ; 'P'
0x140050299  cmp     eax, [rdi+8]
0x14005029c  jnz     loc_140050427
0x1400502a2  test    rdi, rdi
0x1400502a5  jz      loc_140050427
0x1400502ab  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400502b0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400502b5  mov     rcx, [rax+8]
0x1400502b9  mov     eax, [rcx]
0x1400502bb  cmp     eax, 5
0x1400502be  jbe     loc_14005048F
0x1400502c4  mov     rax, [rdi+30h]
0x1400502c8  lea     rdx, byte_1400A0EBF
0x1400502cf  mov     [rbp+var_70], rax
0x1400502d3  mov     eax, [rdi+44h]
0x1400502d6  mov     [rbp+arg_0], eax
0x1400502d9  mov     eax, [rdi+10h]
0x1400502dc  mov     [rbp+arg_8], eax
0x1400502df  mov     rax, [rdi+78h]
0x1400502e3  mov     [rbp+var_68], rax
0x1400502e7  mov     rax, [rdi+70h]
0x1400502eb  mov     [rbp+var_60], rax
0x1400502ef  mov     eax, [rdi+68h]
0x1400502f2  mov     r8, [rbx+110h]
0x1400502f9  mov     dword ptr [rbp+arg_10], eax
0x1400502fc  add     r8, 8
0x140050300  mov     rax, [rdi+60h]
0x140050304  mov     [rbp+var_58], rax
0x140050308  mov     rax, [rdi+58h]
0x14005030c  mov     [rbp+var_50], rax
0x140050310  mov     eax, [rdi+50h]
0x140050313  mov     [rbp+arg_18], eax
0x140050316  mov     rax, [rdi+48h]
0x14005031a  mov     [rbp+var_48], rax
0x14005031e  mov     eax, [rdi+20h]
0x140050321  mov     [rbp+var_80], eax
0x140050324  mov     rax, [rdi+18h]
0x140050328  mov     [rbp+var_40], rax
0x14005032c  mov     eax, [rdi]
0x14005032e  mov     [rbp+var_7C], eax
0x140050331  mov     rax, [rdi+80h]
0x140050338  mov     [rbp+var_38], rax
0x14005033c  mov     eax, [rdi+40h]
0x14005033f  mov     [rbp+var_78], eax
0x140050342  mov     rax, [rdi+38h]
0x140050346  mov     [rbp+var_30], rax
0x14005034a  mov     eax, [rdi+8]
0x14005034d  mov     [rbp+var_74], eax
0x140050350  lea     rax, [rbp+var_70]
0x140050354  mov     [rsp+140h+var_90], rax
0x14005035c  lea     rax, [rbp+arg_0]
0x140050360  mov     [rsp+140h+var_98], rax
0x140050368  lea     rax, [rbp+arg_8]
0x14005036c  mov     [rsp+140h+var_A0], rax
0x140050374  lea     rax, [rbp+var_68]
0x140050378  mov     [rsp+140h+var_A8], rax
0x140050380  lea     rax, [rbp+var_60]
0x140050384  mov     [rsp+140h+var_B0], rax
0x14005038c  lea     rax, [rbp+arg_10]
0x140050390  mov     [rsp+140h+var_B8], rax
0x140050398  lea     rax, [rbp+var_58]
0x14005039c  mov     [rsp+140h+var_C0], rax
0x1400503a4  lea     rax, [rbp+var_50]
0x1400503a8  mov     [rsp+140h+var_C8], rax
0x1400503ad  lea     rax, [rbp+arg_18]
0x1400503b1  mov     [rsp+140h+var_D0], rax
0x1400503b6  lea     rax, [rbp+var_48]
0x1400503ba  mov     [rsp+140h+var_D8], rax
0x1400503bf  lea     rax, [rbp+var_80]
0x1400503c3  mov     [rsp+140h+var_E0], rax
0x1400503c8  lea     rax, [rbp+var_40]
0x1400503cc  mov     [rsp+140h+var_E8], rax
0x1400503d1  lea     rax, [rbp+var_7C]
0x1400503d5  mov     [rsp+140h+var_F0], rax
0x1400503da  lea     rax, [rbp+var_38]
0x1400503de  mov     [rsp+140h+var_F8], rax
0x1400503e3  lea     rax, [rbp+var_78]
0x1400503e7  mov     [rsp+140h+var_100], rax
0x1400503ec  lea     rax, [rbp+var_30]
0x1400503f0  mov     [rsp+140h+var_108], rax
0x1400503f5  lea     rax, [rbp+var_74]
0x1400503f9  mov     [rsp+140h+var_110], rax
0x1400503fe  lea     rax, [rbp+var_28]
0x140050402  mov     [rsp+140h+var_118], rax
0x140050407  lea     rax, [rbp+var_20]
0x14005040b  mov     [rsp+140h+var_120], rax
0x140050410  mov     [rbp+var_28], 1000000h
0x140050418  mov     [rbp+var_20], 0
0x140050420  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140050425  jmp     short loc_14005048F
0x140050427  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005042c  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140050431  mov     rdi, [rax+8]
0x140050435  mov     eax, [rdi]
0x140050437  cmp     eax, 5
0x14005043a  jbe     short loc_14005048F
0x14005043c  call    cs:__imp_GetCurrentThreadId
0x140050443  nop     dword ptr [rax+rax+00h]
0x140050448  mov     r8, [rbx+110h]
0x14005044f  lea     rdx, unk_1400A1010
0x140050456  mov     [rbp+arg_0], eax
0x140050459  mov     rcx, rdi
0x14005045c  mov     eax, [r8+48h]
0x140050460  add     r8, 8
0x140050464  mov     [rbp+arg_8], eax
0x140050467  lea     rax, [rbp+arg_0]
0x14005046b  mov     [rsp+140h+var_110], rax
0x140050470  lea     rax, [rbp+arg_8]
0x140050474  mov     [rsp+140h+var_118], rax
0x140050479  lea     rax, [rbp+arg_10]
0x14005047d  mov     [rsp+140h+var_120], rax
0x140050482  mov     [rbp+arg_10], 0
0x14005048a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005048f  mov     rcx, rbx
0x140050492  add     rsp, 130h
0x140050499  pop     rdi
0x14005049a  pop     rbx
0x14005049b  pop     rbp
0x14005049c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
