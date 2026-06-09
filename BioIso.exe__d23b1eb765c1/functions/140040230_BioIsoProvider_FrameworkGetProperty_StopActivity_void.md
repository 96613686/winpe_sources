# BioIsoProvider::FrameworkGetProperty::StopActivity(void)

- ea: `0x140040230`
- end: `0x140040461`
- name: `?StopActivity@FrameworkGetProperty@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::FrameworkGetProperty *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x140040230`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400403fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400403fc`

## pseudocode

```c
void __fastcall BioIsoProvider::FrameworkGetProperty::StopActivity(BioIsoProvider::FrameworkGetProperty *this)
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
        (__int64)byte_140095F65,
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
        (unsigned __int8 *)&dword_1400960B4,
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
0x140040230  push    rbp
0x140040232  push    rbx
0x140040233  push    rdi
0x140040234  lea     rbp, [rsp+10h]
0x140040239  sub     rsp, 130h
0x140040240  mov     rdi, [rcx+110h]
0x140040247  mov     rbx, rcx
0x14004024a  mov     eax, [rdi+48h]
0x14004024d  test    eax, eax
0x14004024f  jns     loc_1400403E7
0x140040255  add     rdi, 50h ; 'P'
0x140040259  cmp     eax, [rdi+8]
0x14004025c  jnz     loc_1400403E7
0x140040262  test    rdi, rdi
0x140040265  jz      loc_1400403E7
0x14004026b  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140040270  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140040275  mov     rcx, [rax+8]
0x140040279  mov     eax, [rcx]
0x14004027b  cmp     eax, 5
0x14004027e  jbe     loc_14004044F
0x140040284  mov     rax, [rdi+30h]
0x140040288  lea     rdx, byte_140095F65
0x14004028f  mov     [rbp+var_70], rax
0x140040293  mov     eax, [rdi+44h]
0x140040296  mov     [rbp+arg_0], eax
0x140040299  mov     eax, [rdi+10h]
0x14004029c  mov     [rbp+arg_8], eax
0x14004029f  mov     rax, [rdi+78h]
0x1400402a3  mov     [rbp+var_68], rax
0x1400402a7  mov     rax, [rdi+70h]
0x1400402ab  mov     [rbp+var_60], rax
0x1400402af  mov     eax, [rdi+68h]
0x1400402b2  mov     r8, [rbx+110h]
0x1400402b9  mov     dword ptr [rbp+arg_10], eax
0x1400402bc  add     r8, 8
0x1400402c0  mov     rax, [rdi+60h]
0x1400402c4  mov     [rbp+var_58], rax
0x1400402c8  mov     rax, [rdi+58h]
0x1400402cc  mov     [rbp+var_50], rax
0x1400402d0  mov     eax, [rdi+50h]
0x1400402d3  mov     [rbp+arg_18], eax
0x1400402d6  mov     rax, [rdi+48h]
0x1400402da  mov     [rbp+var_48], rax
0x1400402de  mov     eax, [rdi+20h]
0x1400402e1  mov     [rbp+var_80], eax
0x1400402e4  mov     rax, [rdi+18h]
0x1400402e8  mov     [rbp+var_40], rax
0x1400402ec  mov     eax, [rdi]
0x1400402ee  mov     [rbp+var_7C], eax
0x1400402f1  mov     rax, [rdi+80h]
0x1400402f8  mov     [rbp+var_38], rax
0x1400402fc  mov     eax, [rdi+40h]
0x1400402ff  mov     [rbp+var_78], eax
0x140040302  mov     rax, [rdi+38h]
0x140040306  mov     [rbp+var_30], rax
0x14004030a  mov     eax, [rdi+8]
0x14004030d  mov     [rbp+var_74], eax
0x140040310  lea     rax, [rbp+var_70]
0x140040314  mov     [rsp+140h+var_90], rax
0x14004031c  lea     rax, [rbp+arg_0]
0x140040320  mov     [rsp+140h+var_98], rax
0x140040328  lea     rax, [rbp+arg_8]
0x14004032c  mov     [rsp+140h+var_A0], rax
0x140040334  lea     rax, [rbp+var_68]
0x140040338  mov     [rsp+140h+var_A8], rax
0x140040340  lea     rax, [rbp+var_60]
0x140040344  mov     [rsp+140h+var_B0], rax
0x14004034c  lea     rax, [rbp+arg_10]
0x140040350  mov     [rsp+140h+var_B8], rax
0x140040358  lea     rax, [rbp+var_58]
0x14004035c  mov     [rsp+140h+var_C0], rax
0x140040364  lea     rax, [rbp+var_50]
0x140040368  mov     [rsp+140h+var_C8], rax
0x14004036d  lea     rax, [rbp+arg_18]
0x140040371  mov     [rsp+140h+var_D0], rax
0x140040376  lea     rax, [rbp+var_48]
0x14004037a  mov     [rsp+140h+var_D8], rax
0x14004037f  lea     rax, [rbp+var_80]
0x140040383  mov     [rsp+140h+var_E0], rax
0x140040388  lea     rax, [rbp+var_40]
0x14004038c  mov     [rsp+140h+var_E8], rax
0x140040391  lea     rax, [rbp+var_7C]
0x140040395  mov     [rsp+140h+var_F0], rax
0x14004039a  lea     rax, [rbp+var_38]
0x14004039e  mov     [rsp+140h+var_F8], rax
0x1400403a3  lea     rax, [rbp+var_78]
0x1400403a7  mov     [rsp+140h+var_100], rax
0x1400403ac  lea     rax, [rbp+var_30]
0x1400403b0  mov     [rsp+140h+var_108], rax
0x1400403b5  lea     rax, [rbp+var_74]
0x1400403b9  mov     [rsp+140h+var_110], rax
0x1400403be  lea     rax, [rbp+var_28]
0x1400403c2  mov     [rsp+140h+var_118], rax
0x1400403c7  lea     rax, [rbp+var_20]
0x1400403cb  mov     [rsp+140h+var_120], rax
0x1400403d0  mov     [rbp+var_28], 1000000h
0x1400403d8  mov     [rbp+var_20], 0
0x1400403e0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400403e5  jmp     short loc_14004044F
0x1400403e7  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400403ec  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400403f1  mov     rdi, [rax+8]
0x1400403f5  mov     eax, [rdi]
0x1400403f7  cmp     eax, 5
0x1400403fa  jbe     short loc_14004044F
0x1400403fc  call    cs:__imp_GetCurrentThreadId
0x140040403  nop     dword ptr [rax+rax+00h]
0x140040408  mov     r8, [rbx+110h]
0x14004040f  lea     rdx, dword_1400960B4
0x140040416  mov     [rbp+arg_0], eax
0x140040419  mov     rcx, rdi
0x14004041c  mov     eax, [r8+48h]
0x140040420  add     r8, 8
0x140040424  mov     [rbp+arg_8], eax
0x140040427  lea     rax, [rbp+arg_0]
0x14004042b  mov     [rsp+140h+var_110], rax
0x140040430  lea     rax, [rbp+arg_8]
0x140040434  mov     [rsp+140h+var_118], rax
0x140040439  lea     rax, [rbp+arg_10]
0x14004043d  mov     [rsp+140h+var_120], rax
0x140040442  mov     [rbp+arg_10], 0
0x14004044a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004044f  mov     rcx, rbx
0x140040452  add     rsp, 130h
0x140040459  pop     rdi
0x14004045a  pop     rbx
0x14004045b  pop     rbp
0x14004045c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
