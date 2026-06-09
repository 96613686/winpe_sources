# MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(void)

- ea: `0x140016c90`
- end: `0x140016ebc`
- name: `?StopActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001010`
- `0x140001698`
- `0x140015d70`
- `0x1400163d8`
- `0x140016c90`
- `0x140017568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016e5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016e5d`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = MDMPushProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v7;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)&dword_14001F524,
        v8 + 8,
        (__int64)v6,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&v29,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MDMPushProvider::Provider(v9);
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)word_14001F46A,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140016c90  push    rbp
0x140016c92  push    rbx
0x140016c93  push    rdi
0x140016c94  lea     rbp, [rsp+10h]
0x140016c99  sub     rsp, 130h
0x140016ca0  mov     rdi, [rcx+110h]
0x140016ca7  mov     rbx, rcx
0x140016caa  mov     eax, [rdi+48h]
0x140016cad  test    eax, eax
0x140016caf  jns     loc_140016E49
0x140016cb5  add     rdi, 50h ; 'P'
0x140016cb9  cmp     eax, [rdi+8]
0x140016cbc  jnz     loc_140016E49
0x140016cc2  test    rdi, rdi
0x140016cc5  jz      loc_140016E49
0x140016ccb  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140016cd0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016cd5  mov     r9, rax
0x140016cd8  mov     ecx, [rax]
0x140016cda  cmp     ecx, 5
0x140016cdd  jbe     loc_140016EAA
0x140016ce3  mov     rax, [rdi+70h]
0x140016ce7  lea     rdx, dword_14001F524
0x140016cee  mov     rcx, [rdi+30h]
0x140016cf2  mov     [rbp+var_60], rax
0x140016cf6  mov     eax, [rdi+68h]
0x140016cf9  mov     r8, [rbx+110h]
0x140016d00  mov     dword ptr [rbp+arg_10], eax
0x140016d03  add     r8, 8
0x140016d07  mov     rax, [rdi+60h]
0x140016d0b  mov     [rbp+var_58], rax
0x140016d0f  mov     rax, [rdi+58h]
0x140016d13  mov     [rbp+var_50], rax
0x140016d17  mov     eax, [rdi+50h]
0x140016d1a  mov     [rbp+arg_18], eax
0x140016d1d  mov     rax, [rdi+48h]
0x140016d21  mov     [rbp+var_48], rax
0x140016d25  mov     eax, [rdi+20h]
0x140016d28  mov     [rbp+var_80], eax
0x140016d2b  mov     rax, [rdi+18h]
0x140016d2f  mov     [rbp+var_40], rax
0x140016d33  mov     eax, [rdi]
0x140016d35  mov     [rbp+var_7C], eax
0x140016d38  mov     rax, [rdi+80h]
0x140016d3f  mov     [rbp+var_38], rax
0x140016d43  mov     eax, [rdi+40h]
0x140016d46  mov     [rbp+var_78], eax
0x140016d49  mov     rax, [rdi+38h]
0x140016d4d  mov     [rbp+var_30], rax
0x140016d51  mov     eax, [rdi+8]
0x140016d54  mov     [rbp+var_74], eax
0x140016d57  lea     rax, [rbp+var_70]
0x140016d5b  mov     [rsp+140h+var_90], rax
0x140016d63  lea     rax, [rbp+arg_0]
0x140016d67  mov     [rsp+140h+var_98], rax
0x140016d6f  lea     rax, [rbp+arg_8]
0x140016d73  mov     [rsp+140h+var_A0], rax
0x140016d7b  lea     rax, [rbp+var_68]
0x140016d7f  mov     [rsp+140h+var_A8], rax
0x140016d87  lea     rax, [rbp+var_60]
0x140016d8b  mov     [rsp+140h+var_B0], rax
0x140016d93  lea     rax, [rbp+arg_10]
0x140016d97  mov     [rsp+140h+var_B8], rax
0x140016d9f  lea     rax, [rbp+var_58]
0x140016da3  mov     [rsp+140h+var_C0], rax
0x140016dab  lea     rax, [rbp+var_50]
0x140016daf  mov     [rsp+140h+var_C8], rax
0x140016db4  lea     rax, [rbp+arg_18]
0x140016db8  mov     [rsp+140h+var_D0], rax
0x140016dbd  lea     rax, [rbp+var_48]
0x140016dc1  mov     [rsp+140h+var_D8], rax
0x140016dc6  lea     rax, [rbp+var_80]
0x140016dca  mov     [rsp+140h+var_E0], rax
0x140016dcf  lea     rax, [rbp+var_40]
0x140016dd3  mov     [rsp+140h+var_E8], rax
0x140016dd8  lea     rax, [rbp+var_7C]
0x140016ddc  mov     [rsp+140h+var_F0], rax
0x140016de1  lea     rax, [rbp+var_38]
0x140016de5  mov     [rsp+140h+var_F8], rax
0x140016dea  lea     rax, [rbp+var_78]
0x140016dee  mov     [rsp+140h+var_100], rax
0x140016df3  lea     rax, [rbp+var_30]
0x140016df7  mov     [rsp+140h+var_108], rax
0x140016dfc  lea     rax, [rbp+var_74]
0x140016e00  mov     [rbp+var_70], rcx
0x140016e04  mov     ecx, [rdi+44h]
0x140016e07  mov     [rsp+140h+var_110], rax
0x140016e0c  lea     rax, [rbp+var_28]
0x140016e10  mov     [rbp+arg_0], ecx
0x140016e13  mov     ecx, [rdi+10h]
0x140016e16  mov     [rbp+arg_8], ecx
0x140016e19  mov     rcx, [rdi+78h]
0x140016e1d  mov     [rsp+140h+var_118], rax
0x140016e22  lea     rax, [rbp+var_20]
0x140016e26  mov     [rbp+var_68], rcx
0x140016e2a  mov     rcx, r9
0x140016e2d  mov     [rsp+140h+var_120], rax
0x140016e32  mov     [rbp+var_28], 1000000h
0x140016e3a  mov     [rbp+var_20], 0
0x140016e42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140016e47  jmp     short loc_140016EAA
0x140016e49  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140016e4e  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016e53  mov     rdi, rax
0x140016e56  mov     ecx, [rax]
0x140016e58  cmp     ecx, 5
0x140016e5b  jbe     short loc_140016EAA
0x140016e5d  call    cs:__imp_GetCurrentThreadId
0x140016e63  mov     r8, [rbx+110h]
0x140016e6a  lea     rdx, word_14001F46A
0x140016e71  mov     [rbp+arg_0], eax
0x140016e74  lea     rax, [rbp+arg_0]
0x140016e78  mov     [rsp+140h+var_110], rax
0x140016e7d  lea     rax, [rbp+arg_8]
0x140016e81  mov     [rsp+140h+var_118], rax
0x140016e86  lea     rax, [rbp+arg_10]
0x140016e8a  mov     ecx, [r8+48h]
0x140016e8e  add     r8, 8
0x140016e92  mov     [rbp+arg_8], ecx
0x140016e95  mov     rcx, rdi
0x140016e98  mov     [rsp+140h+var_120], rax
0x140016e9d  mov     [rbp+arg_10], 0
0x140016ea5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140016eaa  mov     rcx, rbx
0x140016ead  add     rsp, 130h
0x140016eb4  pop     rdi
0x140016eb5  pop     rbx
0x140016eb6  pop     rbp
0x140016eb7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
