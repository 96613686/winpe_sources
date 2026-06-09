# BioIsoProvider::CreateSecureBiometricUnit::StopActivity(void)

- ea: `0x1400486b0`
- end: `0x1400488e1`
- name: `?StopActivity@CreateSecureBiometricUnit@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::CreateSecureBiometricUnit *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x1400486b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004887c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004887c`

## pseudocode

```c
void __fastcall BioIsoProvider::CreateSecureBiometricUnit::StopActivity(
        BioIsoProvider::CreateSecureBiometricUnit *this)
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
        (__int64)byte_1400A20D3,
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
        (unsigned __int8 *)byte_1400A2227,
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
0x1400486b0  push    rbp
0x1400486b2  push    rbx
0x1400486b3  push    rdi
0x1400486b4  lea     rbp, [rsp+10h]
0x1400486b9  sub     rsp, 130h
0x1400486c0  mov     rdi, [rcx+110h]
0x1400486c7  mov     rbx, rcx
0x1400486ca  mov     eax, [rdi+48h]
0x1400486cd  test    eax, eax
0x1400486cf  jns     loc_140048867
0x1400486d5  add     rdi, 50h ; 'P'
0x1400486d9  cmp     eax, [rdi+8]
0x1400486dc  jnz     loc_140048867
0x1400486e2  test    rdi, rdi
0x1400486e5  jz      loc_140048867
0x1400486eb  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400486f0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400486f5  mov     rcx, [rax+8]
0x1400486f9  mov     eax, [rcx]
0x1400486fb  cmp     eax, 5
0x1400486fe  jbe     loc_1400488CF
0x140048704  mov     rax, [rdi+30h]
0x140048708  lea     rdx, byte_1400A20D3
0x14004870f  mov     [rbp+var_70], rax
0x140048713  mov     eax, [rdi+44h]
0x140048716  mov     [rbp+arg_0], eax
0x140048719  mov     eax, [rdi+10h]
0x14004871c  mov     [rbp+arg_8], eax
0x14004871f  mov     rax, [rdi+78h]
0x140048723  mov     [rbp+var_68], rax
0x140048727  mov     rax, [rdi+70h]
0x14004872b  mov     [rbp+var_60], rax
0x14004872f  mov     eax, [rdi+68h]
0x140048732  mov     r8, [rbx+110h]
0x140048739  mov     dword ptr [rbp+arg_10], eax
0x14004873c  add     r8, 8
0x140048740  mov     rax, [rdi+60h]
0x140048744  mov     [rbp+var_58], rax
0x140048748  mov     rax, [rdi+58h]
0x14004874c  mov     [rbp+var_50], rax
0x140048750  mov     eax, [rdi+50h]
0x140048753  mov     [rbp+arg_18], eax
0x140048756  mov     rax, [rdi+48h]
0x14004875a  mov     [rbp+var_48], rax
0x14004875e  mov     eax, [rdi+20h]
0x140048761  mov     [rbp+var_80], eax
0x140048764  mov     rax, [rdi+18h]
0x140048768  mov     [rbp+var_40], rax
0x14004876c  mov     eax, [rdi]
0x14004876e  mov     [rbp+var_7C], eax
0x140048771  mov     rax, [rdi+80h]
0x140048778  mov     [rbp+var_38], rax
0x14004877c  mov     eax, [rdi+40h]
0x14004877f  mov     [rbp+var_78], eax
0x140048782  mov     rax, [rdi+38h]
0x140048786  mov     [rbp+var_30], rax
0x14004878a  mov     eax, [rdi+8]
0x14004878d  mov     [rbp+var_74], eax
0x140048790  lea     rax, [rbp+var_70]
0x140048794  mov     [rsp+140h+var_90], rax
0x14004879c  lea     rax, [rbp+arg_0]
0x1400487a0  mov     [rsp+140h+var_98], rax
0x1400487a8  lea     rax, [rbp+arg_8]
0x1400487ac  mov     [rsp+140h+var_A0], rax
0x1400487b4  lea     rax, [rbp+var_68]
0x1400487b8  mov     [rsp+140h+var_A8], rax
0x1400487c0  lea     rax, [rbp+var_60]
0x1400487c4  mov     [rsp+140h+var_B0], rax
0x1400487cc  lea     rax, [rbp+arg_10]
0x1400487d0  mov     [rsp+140h+var_B8], rax
0x1400487d8  lea     rax, [rbp+var_58]
0x1400487dc  mov     [rsp+140h+var_C0], rax
0x1400487e4  lea     rax, [rbp+var_50]
0x1400487e8  mov     [rsp+140h+var_C8], rax
0x1400487ed  lea     rax, [rbp+arg_18]
0x1400487f1  mov     [rsp+140h+var_D0], rax
0x1400487f6  lea     rax, [rbp+var_48]
0x1400487fa  mov     [rsp+140h+var_D8], rax
0x1400487ff  lea     rax, [rbp+var_80]
0x140048803  mov     [rsp+140h+var_E0], rax
0x140048808  lea     rax, [rbp+var_40]
0x14004880c  mov     [rsp+140h+var_E8], rax
0x140048811  lea     rax, [rbp+var_7C]
0x140048815  mov     [rsp+140h+var_F0], rax
0x14004881a  lea     rax, [rbp+var_38]
0x14004881e  mov     [rsp+140h+var_F8], rax
0x140048823  lea     rax, [rbp+var_78]
0x140048827  mov     [rsp+140h+var_100], rax
0x14004882c  lea     rax, [rbp+var_30]
0x140048830  mov     [rsp+140h+var_108], rax
0x140048835  lea     rax, [rbp+var_74]
0x140048839  mov     [rsp+140h+var_110], rax
0x14004883e  lea     rax, [rbp+var_28]
0x140048842  mov     [rsp+140h+var_118], rax
0x140048847  lea     rax, [rbp+var_20]
0x14004884b  mov     [rsp+140h+var_120], rax
0x140048850  mov     [rbp+var_28], 1000000h
0x140048858  mov     [rbp+var_20], 0
0x140048860  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140048865  jmp     short loc_1400488CF
0x140048867  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004886c  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140048871  mov     rdi, [rax+8]
0x140048875  mov     eax, [rdi]
0x140048877  cmp     eax, 5
0x14004887a  jbe     short loc_1400488CF
0x14004887c  call    cs:__imp_GetCurrentThreadId
0x140048883  nop     dword ptr [rax+rax+00h]
0x140048888  mov     r8, [rbx+110h]
0x14004888f  lea     rdx, byte_1400A2227
0x140048896  mov     [rbp+arg_0], eax
0x140048899  mov     rcx, rdi
0x14004889c  mov     eax, [r8+48h]
0x1400488a0  add     r8, 8
0x1400488a4  mov     [rbp+arg_8], eax
0x1400488a7  lea     rax, [rbp+arg_0]
0x1400488ab  mov     [rsp+140h+var_110], rax
0x1400488b0  lea     rax, [rbp+arg_8]
0x1400488b4  mov     [rsp+140h+var_118], rax
0x1400488b9  lea     rax, [rbp+arg_10]
0x1400488bd  mov     [rsp+140h+var_120], rax
0x1400488c2  mov     [rbp+arg_10], 0
0x1400488ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400488cf  mov     rcx, rbx
0x1400488d2  add     rsp, 130h
0x1400488d9  pop     rdi
0x1400488da  pop     rbx
0x1400488db  pop     rbp
0x1400488dc  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
