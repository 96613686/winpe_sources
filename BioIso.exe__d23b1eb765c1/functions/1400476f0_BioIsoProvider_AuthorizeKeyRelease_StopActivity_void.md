# BioIsoProvider::AuthorizeKeyRelease::StopActivity(void)

- ea: `0x1400476f0`
- end: `0x140047921`
- name: `?StopActivity@AuthorizeKeyRelease@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::AuthorizeKeyRelease *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x1400476f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400478bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400478bc`

## pseudocode

```c
void __fastcall BioIsoProvider::AuthorizeKeyRelease::StopActivity(BioIsoProvider::AuthorizeKeyRelease *this)
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
        (__int64)&word_140098C96,
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
        (unsigned __int8 *)&dword_140098DE4,
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
0x1400476f0  push    rbp
0x1400476f2  push    rbx
0x1400476f3  push    rdi
0x1400476f4  lea     rbp, [rsp+10h]
0x1400476f9  sub     rsp, 130h
0x140047700  mov     rdi, [rcx+110h]
0x140047707  mov     rbx, rcx
0x14004770a  mov     eax, [rdi+48h]
0x14004770d  test    eax, eax
0x14004770f  jns     loc_1400478A7
0x140047715  add     rdi, 50h ; 'P'
0x140047719  cmp     eax, [rdi+8]
0x14004771c  jnz     loc_1400478A7
0x140047722  test    rdi, rdi
0x140047725  jz      loc_1400478A7
0x14004772b  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140047730  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140047735  mov     rcx, [rax+8]
0x140047739  mov     eax, [rcx]
0x14004773b  cmp     eax, 5
0x14004773e  jbe     loc_14004790F
0x140047744  mov     rax, [rdi+30h]
0x140047748  lea     rdx, word_140098C96
0x14004774f  mov     [rbp+var_70], rax
0x140047753  mov     eax, [rdi+44h]
0x140047756  mov     [rbp+arg_0], eax
0x140047759  mov     eax, [rdi+10h]
0x14004775c  mov     [rbp+arg_8], eax
0x14004775f  mov     rax, [rdi+78h]
0x140047763  mov     [rbp+var_68], rax
0x140047767  mov     rax, [rdi+70h]
0x14004776b  mov     [rbp+var_60], rax
0x14004776f  mov     eax, [rdi+68h]
0x140047772  mov     r8, [rbx+110h]
0x140047779  mov     dword ptr [rbp+arg_10], eax
0x14004777c  add     r8, 8
0x140047780  mov     rax, [rdi+60h]
0x140047784  mov     [rbp+var_58], rax
0x140047788  mov     rax, [rdi+58h]
0x14004778c  mov     [rbp+var_50], rax
0x140047790  mov     eax, [rdi+50h]
0x140047793  mov     [rbp+arg_18], eax
0x140047796  mov     rax, [rdi+48h]
0x14004779a  mov     [rbp+var_48], rax
0x14004779e  mov     eax, [rdi+20h]
0x1400477a1  mov     [rbp+var_80], eax
0x1400477a4  mov     rax, [rdi+18h]
0x1400477a8  mov     [rbp+var_40], rax
0x1400477ac  mov     eax, [rdi]
0x1400477ae  mov     [rbp+var_7C], eax
0x1400477b1  mov     rax, [rdi+80h]
0x1400477b8  mov     [rbp+var_38], rax
0x1400477bc  mov     eax, [rdi+40h]
0x1400477bf  mov     [rbp+var_78], eax
0x1400477c2  mov     rax, [rdi+38h]
0x1400477c6  mov     [rbp+var_30], rax
0x1400477ca  mov     eax, [rdi+8]
0x1400477cd  mov     [rbp+var_74], eax
0x1400477d0  lea     rax, [rbp+var_70]
0x1400477d4  mov     [rsp+140h+var_90], rax
0x1400477dc  lea     rax, [rbp+arg_0]
0x1400477e0  mov     [rsp+140h+var_98], rax
0x1400477e8  lea     rax, [rbp+arg_8]
0x1400477ec  mov     [rsp+140h+var_A0], rax
0x1400477f4  lea     rax, [rbp+var_68]
0x1400477f8  mov     [rsp+140h+var_A8], rax
0x140047800  lea     rax, [rbp+var_60]
0x140047804  mov     [rsp+140h+var_B0], rax
0x14004780c  lea     rax, [rbp+arg_10]
0x140047810  mov     [rsp+140h+var_B8], rax
0x140047818  lea     rax, [rbp+var_58]
0x14004781c  mov     [rsp+140h+var_C0], rax
0x140047824  lea     rax, [rbp+var_50]
0x140047828  mov     [rsp+140h+var_C8], rax
0x14004782d  lea     rax, [rbp+arg_18]
0x140047831  mov     [rsp+140h+var_D0], rax
0x140047836  lea     rax, [rbp+var_48]
0x14004783a  mov     [rsp+140h+var_D8], rax
0x14004783f  lea     rax, [rbp+var_80]
0x140047843  mov     [rsp+140h+var_E0], rax
0x140047848  lea     rax, [rbp+var_40]
0x14004784c  mov     [rsp+140h+var_E8], rax
0x140047851  lea     rax, [rbp+var_7C]
0x140047855  mov     [rsp+140h+var_F0], rax
0x14004785a  lea     rax, [rbp+var_38]
0x14004785e  mov     [rsp+140h+var_F8], rax
0x140047863  lea     rax, [rbp+var_78]
0x140047867  mov     [rsp+140h+var_100], rax
0x14004786c  lea     rax, [rbp+var_30]
0x140047870  mov     [rsp+140h+var_108], rax
0x140047875  lea     rax, [rbp+var_74]
0x140047879  mov     [rsp+140h+var_110], rax
0x14004787e  lea     rax, [rbp+var_28]
0x140047882  mov     [rsp+140h+var_118], rax
0x140047887  lea     rax, [rbp+var_20]
0x14004788b  mov     [rsp+140h+var_120], rax
0x140047890  mov     [rbp+var_28], 1000000h
0x140047898  mov     [rbp+var_20], 0
0x1400478a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400478a5  jmp     short loc_14004790F
0x1400478a7  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400478ac  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400478b1  mov     rdi, [rax+8]
0x1400478b5  mov     eax, [rdi]
0x1400478b7  cmp     eax, 5
0x1400478ba  jbe     short loc_14004790F
0x1400478bc  call    cs:__imp_GetCurrentThreadId
0x1400478c3  nop     dword ptr [rax+rax+00h]
0x1400478c8  mov     r8, [rbx+110h]
0x1400478cf  lea     rdx, dword_140098DE4
0x1400478d6  mov     [rbp+arg_0], eax
0x1400478d9  mov     rcx, rdi
0x1400478dc  mov     eax, [r8+48h]
0x1400478e0  add     r8, 8
0x1400478e4  mov     [rbp+arg_8], eax
0x1400478e7  lea     rax, [rbp+arg_0]
0x1400478eb  mov     [rsp+140h+var_110], rax
0x1400478f0  lea     rax, [rbp+arg_8]
0x1400478f4  mov     [rsp+140h+var_118], rax
0x1400478f9  lea     rax, [rbp+arg_10]
0x1400478fd  mov     [rsp+140h+var_120], rax
0x140047902  mov     [rbp+arg_10], 0
0x14004790a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004790f  mov     rcx, rbx
0x140047912  add     rsp, 130h
0x140047919  pop     rdi
0x14004791a  pop     rbx
0x14004791b  pop     rbp
0x14004791c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
