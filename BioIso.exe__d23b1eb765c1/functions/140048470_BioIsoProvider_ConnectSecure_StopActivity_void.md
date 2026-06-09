# BioIsoProvider::ConnectSecure::StopActivity(void)

- ea: `0x140048470`
- end: `0x1400486a1`
- name: `?StopActivity@ConnectSecure@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::ConnectSecure *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x140048470`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004863c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004863c`

## pseudocode

```c
void __fastcall BioIsoProvider::ConnectSecure::StopActivity(BioIsoProvider::ConnectSecure *this)
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
        (__int64)&word_14009879E,
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
        (unsigned __int8 *)&word_1400988E6,
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
0x140048470  push    rbp
0x140048472  push    rbx
0x140048473  push    rdi
0x140048474  lea     rbp, [rsp+10h]
0x140048479  sub     rsp, 130h
0x140048480  mov     rdi, [rcx+110h]
0x140048487  mov     rbx, rcx
0x14004848a  mov     eax, [rdi+48h]
0x14004848d  test    eax, eax
0x14004848f  jns     loc_140048627
0x140048495  add     rdi, 50h ; 'P'
0x140048499  cmp     eax, [rdi+8]
0x14004849c  jnz     loc_140048627
0x1400484a2  test    rdi, rdi
0x1400484a5  jz      loc_140048627
0x1400484ab  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400484b0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400484b5  mov     rcx, [rax+8]
0x1400484b9  mov     eax, [rcx]
0x1400484bb  cmp     eax, 5
0x1400484be  jbe     loc_14004868F
0x1400484c4  mov     rax, [rdi+30h]
0x1400484c8  lea     rdx, word_14009879E
0x1400484cf  mov     [rbp+var_70], rax
0x1400484d3  mov     eax, [rdi+44h]
0x1400484d6  mov     [rbp+arg_0], eax
0x1400484d9  mov     eax, [rdi+10h]
0x1400484dc  mov     [rbp+arg_8], eax
0x1400484df  mov     rax, [rdi+78h]
0x1400484e3  mov     [rbp+var_68], rax
0x1400484e7  mov     rax, [rdi+70h]
0x1400484eb  mov     [rbp+var_60], rax
0x1400484ef  mov     eax, [rdi+68h]
0x1400484f2  mov     r8, [rbx+110h]
0x1400484f9  mov     dword ptr [rbp+arg_10], eax
0x1400484fc  add     r8, 8
0x140048500  mov     rax, [rdi+60h]
0x140048504  mov     [rbp+var_58], rax
0x140048508  mov     rax, [rdi+58h]
0x14004850c  mov     [rbp+var_50], rax
0x140048510  mov     eax, [rdi+50h]
0x140048513  mov     [rbp+arg_18], eax
0x140048516  mov     rax, [rdi+48h]
0x14004851a  mov     [rbp+var_48], rax
0x14004851e  mov     eax, [rdi+20h]
0x140048521  mov     [rbp+var_80], eax
0x140048524  mov     rax, [rdi+18h]
0x140048528  mov     [rbp+var_40], rax
0x14004852c  mov     eax, [rdi]
0x14004852e  mov     [rbp+var_7C], eax
0x140048531  mov     rax, [rdi+80h]
0x140048538  mov     [rbp+var_38], rax
0x14004853c  mov     eax, [rdi+40h]
0x14004853f  mov     [rbp+var_78], eax
0x140048542  mov     rax, [rdi+38h]
0x140048546  mov     [rbp+var_30], rax
0x14004854a  mov     eax, [rdi+8]
0x14004854d  mov     [rbp+var_74], eax
0x140048550  lea     rax, [rbp+var_70]
0x140048554  mov     [rsp+140h+var_90], rax
0x14004855c  lea     rax, [rbp+arg_0]
0x140048560  mov     [rsp+140h+var_98], rax
0x140048568  lea     rax, [rbp+arg_8]
0x14004856c  mov     [rsp+140h+var_A0], rax
0x140048574  lea     rax, [rbp+var_68]
0x140048578  mov     [rsp+140h+var_A8], rax
0x140048580  lea     rax, [rbp+var_60]
0x140048584  mov     [rsp+140h+var_B0], rax
0x14004858c  lea     rax, [rbp+arg_10]
0x140048590  mov     [rsp+140h+var_B8], rax
0x140048598  lea     rax, [rbp+var_58]
0x14004859c  mov     [rsp+140h+var_C0], rax
0x1400485a4  lea     rax, [rbp+var_50]
0x1400485a8  mov     [rsp+140h+var_C8], rax
0x1400485ad  lea     rax, [rbp+arg_18]
0x1400485b1  mov     [rsp+140h+var_D0], rax
0x1400485b6  lea     rax, [rbp+var_48]
0x1400485ba  mov     [rsp+140h+var_D8], rax
0x1400485bf  lea     rax, [rbp+var_80]
0x1400485c3  mov     [rsp+140h+var_E0], rax
0x1400485c8  lea     rax, [rbp+var_40]
0x1400485cc  mov     [rsp+140h+var_E8], rax
0x1400485d1  lea     rax, [rbp+var_7C]
0x1400485d5  mov     [rsp+140h+var_F0], rax
0x1400485da  lea     rax, [rbp+var_38]
0x1400485de  mov     [rsp+140h+var_F8], rax
0x1400485e3  lea     rax, [rbp+var_78]
0x1400485e7  mov     [rsp+140h+var_100], rax
0x1400485ec  lea     rax, [rbp+var_30]
0x1400485f0  mov     [rsp+140h+var_108], rax
0x1400485f5  lea     rax, [rbp+var_74]
0x1400485f9  mov     [rsp+140h+var_110], rax
0x1400485fe  lea     rax, [rbp+var_28]
0x140048602  mov     [rsp+140h+var_118], rax
0x140048607  lea     rax, [rbp+var_20]
0x14004860b  mov     [rsp+140h+var_120], rax
0x140048610  mov     [rbp+var_28], 1000000h
0x140048618  mov     [rbp+var_20], 0
0x140048620  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140048625  jmp     short loc_14004868F
0x140048627  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004862c  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140048631  mov     rdi, [rax+8]
0x140048635  mov     eax, [rdi]
0x140048637  cmp     eax, 5
0x14004863a  jbe     short loc_14004868F
0x14004863c  call    cs:__imp_GetCurrentThreadId
0x140048643  nop     dword ptr [rax+rax+00h]
0x140048648  mov     r8, [rbx+110h]
0x14004864f  lea     rdx, word_1400988E6
0x140048656  mov     [rbp+arg_0], eax
0x140048659  mov     rcx, rdi
0x14004865c  mov     eax, [r8+48h]
0x140048660  add     r8, 8
0x140048664  mov     [rbp+arg_8], eax
0x140048667  lea     rax, [rbp+arg_0]
0x14004866b  mov     [rsp+140h+var_110], rax
0x140048670  lea     rax, [rbp+arg_8]
0x140048674  mov     [rsp+140h+var_118], rax
0x140048679  lea     rax, [rbp+arg_10]
0x14004867d  mov     [rsp+140h+var_120], rax
0x140048682  mov     [rbp+arg_10], 0
0x14004868a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004868f  mov     rcx, rbx
0x140048692  add     rsp, 130h
0x140048699  pop     rdi
0x14004869a  pop     rbx
0x14004869b  pop     rbp
0x14004869c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
