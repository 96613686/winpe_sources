# BioIsoProvider::PresenceMonitorUpdate::StopActivity(void)

- ea: `0x14004ebf0`
- end: `0x14004ee21`
- name: `?StopActivity@PresenceMonitorUpdate@BioIsoProvider@@MEAAXXZ`
- size: `561`
- prototype: `void __fastcall(BioIsoProvider::PresenceMonitorUpdate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140001008`
- `0x140001bc4`
- `0x14000b4e0`
- `0x14000d990`
- `0x140013728`
- `0x14004ebf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004edbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004edbc`

## pseudocode

```c
void __fastcall BioIsoProvider::PresenceMonitorUpdate::StopActivity(BioIsoProvider::PresenceMonitorUpdate *this)
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
        (__int64)&unk_140099F10,
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
        (unsigned __int8 *)&unk_14009A060,
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
0x14004ebf0  push    rbp
0x14004ebf2  push    rbx
0x14004ebf3  push    rdi
0x14004ebf4  lea     rbp, [rsp+10h]
0x14004ebf9  sub     rsp, 130h
0x14004ec00  mov     rdi, [rcx+110h]
0x14004ec07  mov     rbx, rcx
0x14004ec0a  mov     eax, [rdi+48h]
0x14004ec0d  test    eax, eax
0x14004ec0f  jns     loc_14004EDA7
0x14004ec15  add     rdi, 50h ; 'P'
0x14004ec19  cmp     eax, [rdi+8]
0x14004ec1c  jnz     loc_14004EDA7
0x14004ec22  test    rdi, rdi
0x14004ec25  jz      loc_14004EDA7
0x14004ec2b  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004ec30  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004ec35  mov     rcx, [rax+8]
0x14004ec39  mov     eax, [rcx]
0x14004ec3b  cmp     eax, 5
0x14004ec3e  jbe     loc_14004EE0F
0x14004ec44  mov     rax, [rdi+30h]
0x14004ec48  lea     rdx, unk_140099F10
0x14004ec4f  mov     [rbp+var_70], rax
0x14004ec53  mov     eax, [rdi+44h]
0x14004ec56  mov     [rbp+arg_0], eax
0x14004ec59  mov     eax, [rdi+10h]
0x14004ec5c  mov     [rbp+arg_8], eax
0x14004ec5f  mov     rax, [rdi+78h]
0x14004ec63  mov     [rbp+var_68], rax
0x14004ec67  mov     rax, [rdi+70h]
0x14004ec6b  mov     [rbp+var_60], rax
0x14004ec6f  mov     eax, [rdi+68h]
0x14004ec72  mov     r8, [rbx+110h]
0x14004ec79  mov     dword ptr [rbp+arg_10], eax
0x14004ec7c  add     r8, 8
0x14004ec80  mov     rax, [rdi+60h]
0x14004ec84  mov     [rbp+var_58], rax
0x14004ec88  mov     rax, [rdi+58h]
0x14004ec8c  mov     [rbp+var_50], rax
0x14004ec90  mov     eax, [rdi+50h]
0x14004ec93  mov     [rbp+arg_18], eax
0x14004ec96  mov     rax, [rdi+48h]
0x14004ec9a  mov     [rbp+var_48], rax
0x14004ec9e  mov     eax, [rdi+20h]
0x14004eca1  mov     [rbp+var_80], eax
0x14004eca4  mov     rax, [rdi+18h]
0x14004eca8  mov     [rbp+var_40], rax
0x14004ecac  mov     eax, [rdi]
0x14004ecae  mov     [rbp+var_7C], eax
0x14004ecb1  mov     rax, [rdi+80h]
0x14004ecb8  mov     [rbp+var_38], rax
0x14004ecbc  mov     eax, [rdi+40h]
0x14004ecbf  mov     [rbp+var_78], eax
0x14004ecc2  mov     rax, [rdi+38h]
0x14004ecc6  mov     [rbp+var_30], rax
0x14004ecca  mov     eax, [rdi+8]
0x14004eccd  mov     [rbp+var_74], eax
0x14004ecd0  lea     rax, [rbp+var_70]
0x14004ecd4  mov     [rsp+140h+var_90], rax
0x14004ecdc  lea     rax, [rbp+arg_0]
0x14004ece0  mov     [rsp+140h+var_98], rax
0x14004ece8  lea     rax, [rbp+arg_8]
0x14004ecec  mov     [rsp+140h+var_A0], rax
0x14004ecf4  lea     rax, [rbp+var_68]
0x14004ecf8  mov     [rsp+140h+var_A8], rax
0x14004ed00  lea     rax, [rbp+var_60]
0x14004ed04  mov     [rsp+140h+var_B0], rax
0x14004ed0c  lea     rax, [rbp+arg_10]
0x14004ed10  mov     [rsp+140h+var_B8], rax
0x14004ed18  lea     rax, [rbp+var_58]
0x14004ed1c  mov     [rsp+140h+var_C0], rax
0x14004ed24  lea     rax, [rbp+var_50]
0x14004ed28  mov     [rsp+140h+var_C8], rax
0x14004ed2d  lea     rax, [rbp+arg_18]
0x14004ed31  mov     [rsp+140h+var_D0], rax
0x14004ed36  lea     rax, [rbp+var_48]
0x14004ed3a  mov     [rsp+140h+var_D8], rax
0x14004ed3f  lea     rax, [rbp+var_80]
0x14004ed43  mov     [rsp+140h+var_E0], rax
0x14004ed48  lea     rax, [rbp+var_40]
0x14004ed4c  mov     [rsp+140h+var_E8], rax
0x14004ed51  lea     rax, [rbp+var_7C]
0x14004ed55  mov     [rsp+140h+var_F0], rax
0x14004ed5a  lea     rax, [rbp+var_38]
0x14004ed5e  mov     [rsp+140h+var_F8], rax
0x14004ed63  lea     rax, [rbp+var_78]
0x14004ed67  mov     [rsp+140h+var_100], rax
0x14004ed6c  lea     rax, [rbp+var_30]
0x14004ed70  mov     [rsp+140h+var_108], rax
0x14004ed75  lea     rax, [rbp+var_74]
0x14004ed79  mov     [rsp+140h+var_110], rax
0x14004ed7e  lea     rax, [rbp+var_28]
0x14004ed82  mov     [rsp+140h+var_118], rax
0x14004ed87  lea     rax, [rbp+var_20]
0x14004ed8b  mov     [rsp+140h+var_120], rax
0x14004ed90  mov     [rbp+var_28], 1000000h
0x14004ed98  mov     [rbp+var_20], 0
0x14004eda0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004eda5  jmp     short loc_14004EE0F
0x14004eda7  call    ?zInternalStop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004edac  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14004edb1  mov     rdi, [rax+8]
0x14004edb5  mov     eax, [rdi]
0x14004edb7  cmp     eax, 5
0x14004edba  jbe     short loc_14004EE0F
0x14004edbc  call    cs:__imp_GetCurrentThreadId
0x14004edc3  nop     dword ptr [rax+rax+00h]
0x14004edc8  mov     r8, [rbx+110h]
0x14004edcf  lea     rdx, unk_14009A060
0x14004edd6  mov     [rbp+arg_0], eax
0x14004edd9  mov     rcx, rdi
0x14004eddc  mov     eax, [r8+48h]
0x14004ede0  add     r8, 8
0x14004ede4  mov     [rbp+arg_8], eax
0x14004ede7  lea     rax, [rbp+arg_0]
0x14004edeb  mov     [rsp+140h+var_110], rax
0x14004edf0  lea     rax, [rbp+arg_8]
0x14004edf4  mov     [rsp+140h+var_118], rax
0x14004edf9  lea     rax, [rbp+arg_10]
0x14004edfd  mov     [rsp+140h+var_120], rax
0x14004ee02  mov     [rbp+arg_10], 0
0x14004ee0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004ee0f  mov     rcx, rbx
0x14004ee12  add     rsp, 130h
0x14004ee19  pop     rdi
0x14004ee1a  pop     rbx
0x14004ee1b  pop     rbp
0x14004ee1c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
