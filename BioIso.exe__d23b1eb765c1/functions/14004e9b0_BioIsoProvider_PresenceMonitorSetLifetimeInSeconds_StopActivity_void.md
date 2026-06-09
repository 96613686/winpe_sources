# BioIsoProvider::PresenceMonitorSetLifetimeInSeconds::StopActivity(void)

- ea: `0x14004e9b0`
- end: `0x14004ebe1`
- name: `?StopActivity@PresenceMonitorSetLifetimeInSeconds@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::PresenceMonitorSetLifetimeInSeconds *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x14004e9b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004eb7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004eb7c`

## pseudocode

```c
void __fastcall BioIsoProvider::PresenceMonitorSetLifetimeInSeconds::StopActivity(
        BioIsoProvider::PresenceMonitorSetLifetimeInSeconds *this)
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
        (__int64)word_14009984A,
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
        (unsigned __int8 *)&unk_1400999A8,
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
0x14004e9b0  push    rbp
0x14004e9b2  push    rbx
0x14004e9b3  push    rdi
0x14004e9b4  lea     rbp, [rsp+10h]
0x14004e9b9  sub     rsp, 130h
0x14004e9c0  mov     rdi, [rcx+110h]
0x14004e9c7  mov     rbx, rcx
0x14004e9ca  mov     eax, [rdi+48h]
0x14004e9cd  test    eax, eax
0x14004e9cf  jns     loc_14004EB67
0x14004e9d5  add     rdi, 50h ; 'P'
0x14004e9d9  cmp     eax, [rdi+8]
0x14004e9dc  jnz     loc_14004EB67
0x14004e9e2  test    rdi, rdi
0x14004e9e5  jz      loc_14004EB67
0x14004e9eb  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004e9f0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004e9f5  mov     rcx, [rax+8]
0x14004e9f9  mov     eax, [rcx]
0x14004e9fb  cmp     eax, 5
0x14004e9fe  jbe     loc_14004EBCF
0x14004ea04  mov     rax, [rdi+30h]
0x14004ea08  lea     rdx, word_14009984A
0x14004ea0f  mov     [rbp+var_70], rax
0x14004ea13  mov     eax, [rdi+44h]
0x14004ea16  mov     [rbp+arg_0], eax
0x14004ea19  mov     eax, [rdi+10h]
0x14004ea1c  mov     [rbp+arg_8], eax
0x14004ea1f  mov     rax, [rdi+78h]
0x14004ea23  mov     [rbp+var_68], rax
0x14004ea27  mov     rax, [rdi+70h]
0x14004ea2b  mov     [rbp+var_60], rax
0x14004ea2f  mov     eax, [rdi+68h]
0x14004ea32  mov     r8, [rbx+110h]
0x14004ea39  mov     dword ptr [rbp+arg_10], eax
0x14004ea3c  add     r8, 8
0x14004ea40  mov     rax, [rdi+60h]
0x14004ea44  mov     [rbp+var_58], rax
0x14004ea48  mov     rax, [rdi+58h]
0x14004ea4c  mov     [rbp+var_50], rax
0x14004ea50  mov     eax, [rdi+50h]
0x14004ea53  mov     [rbp+arg_18], eax
0x14004ea56  mov     rax, [rdi+48h]
0x14004ea5a  mov     [rbp+var_48], rax
0x14004ea5e  mov     eax, [rdi+20h]
0x14004ea61  mov     [rbp+var_80], eax
0x14004ea64  mov     rax, [rdi+18h]
0x14004ea68  mov     [rbp+var_40], rax
0x14004ea6c  mov     eax, [rdi]
0x14004ea6e  mov     [rbp+var_7C], eax
0x14004ea71  mov     rax, [rdi+80h]
0x14004ea78  mov     [rbp+var_38], rax
0x14004ea7c  mov     eax, [rdi+40h]
0x14004ea7f  mov     [rbp+var_78], eax
0x14004ea82  mov     rax, [rdi+38h]
0x14004ea86  mov     [rbp+var_30], rax
0x14004ea8a  mov     eax, [rdi+8]
0x14004ea8d  mov     [rbp+var_74], eax
0x14004ea90  lea     rax, [rbp+var_70]
0x14004ea94  mov     [rsp+140h+var_90], rax
0x14004ea9c  lea     rax, [rbp+arg_0]
0x14004eaa0  mov     [rsp+140h+var_98], rax
0x14004eaa8  lea     rax, [rbp+arg_8]
0x14004eaac  mov     [rsp+140h+var_A0], rax
0x14004eab4  lea     rax, [rbp+var_68]
0x14004eab8  mov     [rsp+140h+var_A8], rax
0x14004eac0  lea     rax, [rbp+var_60]
0x14004eac4  mov     [rsp+140h+var_B0], rax
0x14004eacc  lea     rax, [rbp+arg_10]
0x14004ead0  mov     [rsp+140h+var_B8], rax
0x14004ead8  lea     rax, [rbp+var_58]
0x14004eadc  mov     [rsp+140h+var_C0], rax
0x14004eae4  lea     rax, [rbp+var_50]
0x14004eae8  mov     [rsp+140h+var_C8], rax
0x14004eaed  lea     rax, [rbp+arg_18]
0x14004eaf1  mov     [rsp+140h+var_D0], rax
0x14004eaf6  lea     rax, [rbp+var_48]
0x14004eafa  mov     [rsp+140h+var_D8], rax
0x14004eaff  lea     rax, [rbp+var_80]
0x14004eb03  mov     [rsp+140h+var_E0], rax
0x14004eb08  lea     rax, [rbp+var_40]
0x14004eb0c  mov     [rsp+140h+var_E8], rax
0x14004eb11  lea     rax, [rbp+var_7C]
0x14004eb15  mov     [rsp+140h+var_F0], rax
0x14004eb1a  lea     rax, [rbp+var_38]
0x14004eb1e  mov     [rsp+140h+var_F8], rax
0x14004eb23  lea     rax, [rbp+var_78]
0x14004eb27  mov     [rsp+140h+var_100], rax
0x14004eb2c  lea     rax, [rbp+var_30]
0x14004eb30  mov     [rsp+140h+var_108], rax
0x14004eb35  lea     rax, [rbp+var_74]
0x14004eb39  mov     [rsp+140h+var_110], rax
0x14004eb3e  lea     rax, [rbp+var_28]
0x14004eb42  mov     [rsp+140h+var_118], rax
0x14004eb47  lea     rax, [rbp+var_20]
0x14004eb4b  mov     [rsp+140h+var_120], rax
0x14004eb50  mov     [rbp+var_28], 1000000h
0x14004eb58  mov     [rbp+var_20], 0
0x14004eb60  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004eb65  jmp     short loc_14004EBCF
0x14004eb67  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004eb6c  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004eb71  mov     rdi, [rax+8]
0x14004eb75  mov     eax, [rdi]
0x14004eb77  cmp     eax, 5
0x14004eb7a  jbe     short loc_14004EBCF
0x14004eb7c  call    cs:__imp_GetCurrentThreadId
0x14004eb83  nop     dword ptr [rax+rax+00h]
0x14004eb88  mov     r8, [rbx+110h]
0x14004eb8f  lea     rdx, unk_1400999A8
0x14004eb96  mov     [rbp+arg_0], eax
0x14004eb99  mov     rcx, rdi
0x14004eb9c  mov     eax, [r8+48h]
0x14004eba0  add     r8, 8
0x14004eba4  mov     [rbp+arg_8], eax
0x14004eba7  lea     rax, [rbp+arg_0]
0x14004ebab  mov     [rsp+140h+var_110], rax
0x14004ebb0  lea     rax, [rbp+arg_8]
0x14004ebb4  mov     [rsp+140h+var_118], rax
0x14004ebb9  lea     rax, [rbp+arg_10]
0x14004ebbd  mov     [rsp+140h+var_120], rax
0x14004ebc2  mov     [rbp+arg_10], 0
0x14004ebca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004ebcf  mov     rcx, rbx
0x14004ebd2  add     rsp, 130h
0x14004ebd9  pop     rdi
0x14004ebda  pop     rbx
0x14004ebdb  pop     rbp
0x14004ebdc  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
