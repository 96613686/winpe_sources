# HostNameVerifierProvider::VerifyFromWeb::StopActivity(void)

- ea: `0x14000e890`
- end: `0x14000eab2`
- name: `?StopActivity@VerifyFromWeb@HostNameVerifierProvider@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyFromWeb *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001010`
- `0x1400012cc`
- `0x140001b4c`
- `0x14000d438`
- `0x14000da38`
- `0x14000e890`
- `0x140010cf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ea52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ea52`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyFromWeb::StopActivity(HostNameVerifierProvider::VerifyFromWeb *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  int *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  int *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  int *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = HostNameVerifierProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (int *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (int *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (int *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_140015E73,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = HostNameVerifierProvider::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)byte_140015E25,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000e890  push    rbp
0x14000e892  push    rbx
0x14000e893  push    rdi
0x14000e894  lea     rbp, [rsp-47h]
0x14000e899  sub     rsp, 100h
0x14000e8a0  mov     rdi, [rcx+110h]
0x14000e8a7  mov     rbx, rcx
0x14000e8aa  mov     eax, [rdi+48h]
0x14000e8ad  test    eax, eax
0x14000e8af  jns     loc_14000EA28
0x14000e8b5  add     rdi, 50h ; 'P'
0x14000e8b9  cmp     eax, [rdi+8]
0x14000e8bc  jnz     loc_14000EA28
0x14000e8c2  test    rdi, rdi
0x14000e8c5  jz      loc_14000EA28
0x14000e8cb  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000e8d0  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e8d5  mov     r9, rax
0x14000e8d8  mov     ecx, [rax]
0x14000e8da  cmp     ecx, 5
0x14000e8dd  jbe     loc_14000EAA0
0x14000e8e3  mov     rdx, 400000000000h
0x14000e8ed  mov     rcx, rax
0x14000e8f0  call    _tlgKeywordOn
0x14000e8f5  test    al, al
0x14000e8f7  jz      loc_14000EAA0
0x14000e8fd  mov     rax, [rdi+70h]
0x14000e901  lea     rdx, byte_140015E73
0x14000e908  mov     rcx, [rdi+78h]
0x14000e90c  mov     r8, [rbx+110h]
0x14000e913  mov     [rbp+57h+var_60], rax
0x14000e917  add     r8, 8
0x14000e91b  mov     eax, [rdi+68h]
0x14000e91e  mov     [rbp+57h+arg_0], eax
0x14000e921  mov     rax, [rdi+60h]
0x14000e925  mov     [rbp+57h+var_58], rax
0x14000e929  mov     rax, [rdi+58h]
0x14000e92d  mov     [rbp+57h+var_50], rax
0x14000e931  mov     eax, [rdi+50h]
0x14000e934  mov     [rbp+57h+arg_8], eax
0x14000e937  mov     rax, [rdi+48h]
0x14000e93b  mov     [rbp+57h+var_48], rax
0x14000e93f  mov     eax, [rdi+20h]
0x14000e942  mov     dword ptr [rbp+57h+arg_10], eax
0x14000e945  mov     rax, [rdi+18h]
0x14000e949  mov     [rbp+57h+var_40], rax
0x14000e94d  mov     eax, [rdi]
0x14000e94f  mov     [rbp+57h+arg_18], eax
0x14000e952  mov     rax, [rdi+80h]
0x14000e959  mov     [rbp+57h+var_38], rax
0x14000e95d  mov     eax, [rdi+40h]
0x14000e960  mov     [rbp+57h+var_70], eax
0x14000e963  mov     rax, [rdi+38h]
0x14000e967  mov     [rbp+57h+var_30], rax
0x14000e96b  mov     eax, [rdi+8]
0x14000e96e  mov     [rbp+57h+var_6C], eax
0x14000e971  mov     eax, 1000000h
0x14000e976  mov     [rbp+57h+var_28], rax
0x14000e97a  mov     [rbp+57h+var_20], rax
0x14000e97e  lea     rax, [rbp+57h+var_68]
0x14000e982  mov     [rsp+110h+var_78], rax
0x14000e98a  lea     rax, [rbp+57h+var_60]
0x14000e98e  mov     [rsp+110h+var_80], rax
0x14000e996  lea     rax, [rbp+57h+arg_0]
0x14000e99a  mov     [rsp+110h+var_88], rax
0x14000e9a2  lea     rax, [rbp+57h+var_58]
0x14000e9a6  mov     [rsp+110h+var_90], rax
0x14000e9ae  lea     rax, [rbp+57h+var_50]
0x14000e9b2  mov     [rsp+110h+var_98], rax
0x14000e9b7  lea     rax, [rbp+57h+arg_8]
0x14000e9bb  mov     [rsp+110h+var_A0], rax
0x14000e9c0  lea     rax, [rbp+57h+var_48]
0x14000e9c4  mov     [rsp+110h+var_A8], rax
0x14000e9c9  lea     rax, [rbp+57h+arg_10]
0x14000e9cd  mov     [rsp+110h+var_B0], rax
0x14000e9d2  lea     rax, [rbp+57h+var_40]
0x14000e9d6  mov     [rsp+110h+var_B8], rax
0x14000e9db  lea     rax, [rbp+57h+arg_18]
0x14000e9df  mov     [rsp+110h+var_C0], rax
0x14000e9e4  lea     rax, [rbp+57h+var_38]
0x14000e9e8  mov     [rsp+110h+var_C8], rax
0x14000e9ed  lea     rax, [rbp+57h+var_70]
0x14000e9f1  mov     [rsp+110h+var_D0], rax
0x14000e9f6  lea     rax, [rbp+57h+var_30]
0x14000e9fa  mov     [rsp+110h+var_D8], rax
0x14000e9ff  lea     rax, [rbp+57h+var_6C]
0x14000ea03  mov     [rsp+110h+var_E0], rax
0x14000ea08  lea     rax, [rbp+57h+var_28]
0x14000ea0c  mov     [rsp+110h+var_E8], rax
0x14000ea11  lea     rax, [rbp+57h+var_20]
0x14000ea15  mov     [rbp+57h+var_68], rcx
0x14000ea19  mov     rcx, r9
0x14000ea1c  mov     [rsp+110h+var_F0], rax
0x14000ea21  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000ea26  jmp     short loc_14000EAA0
0x14000ea28  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000ea2d  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000ea32  mov     rdi, rax
0x14000ea35  mov     ecx, [rax]
0x14000ea37  cmp     ecx, 5
0x14000ea3a  jbe     short loc_14000EAA0
0x14000ea3c  mov     rdx, 400000000000h
0x14000ea46  mov     rcx, rax
0x14000ea49  call    _tlgKeywordOn
0x14000ea4e  test    al, al
0x14000ea50  jz      short loc_14000EAA0
0x14000ea52  call    cs:__imp_GetCurrentThreadId
0x14000ea58  mov     r8, [rbx+110h]
0x14000ea5f  lea     rdx, byte_140015E25
0x14000ea66  mov     [rbp+57h+arg_0], eax
0x14000ea69  mov     rcx, rdi
0x14000ea6c  mov     eax, [r8+48h]
0x14000ea70  add     r8, 8
0x14000ea74  mov     [rbp+57h+arg_8], eax
0x14000ea77  mov     eax, 1000000h
0x14000ea7c  mov     [rbp+57h+arg_10], rax
0x14000ea80  lea     rax, [rbp+57h+arg_0]
0x14000ea84  mov     [rsp+110h+var_E0], rax
0x14000ea89  lea     rax, [rbp+57h+arg_8]
0x14000ea8d  mov     [rsp+110h+var_E8], rax
0x14000ea92  lea     rax, [rbp+57h+arg_10]
0x14000ea96  mov     [rsp+110h+var_F0], rax
0x14000ea9b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000eaa0  mov     rcx, rbx
0x14000eaa3  add     rsp, 100h
0x14000eaaa  pop     rdi
0x14000eaab  pop     rbx
0x14000eaac  pop     rbp
0x14000eaad  jmp     ?IgnoreCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
