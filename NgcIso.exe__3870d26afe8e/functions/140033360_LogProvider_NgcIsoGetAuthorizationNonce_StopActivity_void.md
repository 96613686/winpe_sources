# LogProvider::NgcIsoGetAuthorizationNonce::StopActivity(void)

- ea: `0x140033360`
- end: `0x14003358f`
- name: `?StopActivity@NgcIsoGetAuthorizationNonce@LogProvider@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(LogProvider::NgcIsoGetAuthorizationNonce *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140001008`
- `0x140003124`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140033360`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003352d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003352d`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetAuthorizationNonce::StopActivity(LogProvider::NgcIsoGetAuthorizationNonce *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
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
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LogProvider::Provider();
    if ( *(_DWORD *)v7 > 4u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)byte_140086283,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = LogProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_1400863D9,
        v13 + 8,
        0,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x140033360  push    rbp
0x140033362  push    rbx
0x140033363  push    rdi
0x140033364  lea     rbp, [rsp+10h]
0x140033369  sub     rsp, 130h
0x140033370  mov     rdi, [rcx+110h]
0x140033377  mov     rbx, rcx
0x14003337a  mov     eax, [rdi+48h]
0x14003337d  test    eax, eax
0x14003337f  jns     loc_140033519
0x140033385  add     rdi, 50h ; 'P'
0x140033389  cmp     eax, [rdi+8]
0x14003338c  jnz     loc_140033519
0x140033392  test    rdi, rdi
0x140033395  jz      loc_140033519
0x14003339b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400333a0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400333a5  mov     r9, rax
0x1400333a8  mov     ecx, [rax]
0x1400333aa  cmp     ecx, 4
0x1400333ad  jbe     loc_14003357D
0x1400333b3  mov     rax, [rdi+70h]
0x1400333b7  lea     rdx, byte_140086283
0x1400333be  mov     rcx, [rdi+30h]
0x1400333c2  mov     [rbp+var_60], rax
0x1400333c6  mov     eax, [rdi+68h]
0x1400333c9  mov     r8, [rbx+110h]
0x1400333d0  mov     dword ptr [rbp+arg_10], eax
0x1400333d3  add     r8, 8
0x1400333d7  mov     rax, [rdi+60h]
0x1400333db  mov     [rbp+var_58], rax
0x1400333df  mov     rax, [rdi+58h]
0x1400333e3  mov     [rbp+var_50], rax
0x1400333e7  mov     eax, [rdi+50h]
0x1400333ea  mov     [rbp+arg_18], eax
0x1400333ed  mov     rax, [rdi+48h]
0x1400333f1  mov     [rbp+var_48], rax
0x1400333f5  mov     eax, [rdi+20h]
0x1400333f8  mov     [rbp+var_80], eax
0x1400333fb  mov     rax, [rdi+18h]
0x1400333ff  mov     [rbp+var_40], rax
0x140033403  mov     eax, [rdi]
0x140033405  mov     [rbp+var_7C], eax
0x140033408  mov     rax, [rdi+80h]
0x14003340f  mov     [rbp+var_38], rax
0x140033413  mov     eax, [rdi+40h]
0x140033416  mov     [rbp+var_78], eax
0x140033419  mov     rax, [rdi+38h]
0x14003341d  mov     [rbp+var_30], rax
0x140033421  mov     eax, [rdi+8]
0x140033424  mov     [rbp+var_74], eax
0x140033427  lea     rax, [rbp+var_70]
0x14003342b  mov     [rsp+140h+var_90], rax
0x140033433  lea     rax, [rbp+arg_0]
0x140033437  mov     [rsp+140h+var_98], rax
0x14003343f  lea     rax, [rbp+arg_8]
0x140033443  mov     [rsp+140h+var_A0], rax
0x14003344b  lea     rax, [rbp+var_68]
0x14003344f  mov     [rsp+140h+var_A8], rax
0x140033457  lea     rax, [rbp+var_60]
0x14003345b  mov     [rsp+140h+var_B0], rax
0x140033463  lea     rax, [rbp+arg_10]
0x140033467  mov     [rsp+140h+var_B8], rax
0x14003346f  lea     rax, [rbp+var_58]
0x140033473  mov     [rsp+140h+var_C0], rax
0x14003347b  lea     rax, [rbp+var_50]
0x14003347f  mov     [rsp+140h+var_C8], rax
0x140033484  lea     rax, [rbp+arg_18]
0x140033488  mov     [rsp+140h+var_D0], rax
0x14003348d  lea     rax, [rbp+var_48]
0x140033491  mov     [rsp+140h+var_D8], rax
0x140033496  lea     rax, [rbp+var_80]
0x14003349a  mov     [rsp+140h+var_E0], rax
0x14003349f  lea     rax, [rbp+var_40]
0x1400334a3  mov     [rsp+140h+var_E8], rax
0x1400334a8  lea     rax, [rbp+var_7C]
0x1400334ac  mov     [rsp+140h+var_F0], rax
0x1400334b1  lea     rax, [rbp+var_38]
0x1400334b5  mov     [rsp+140h+var_F8], rax
0x1400334ba  lea     rax, [rbp+var_78]
0x1400334be  mov     [rsp+140h+var_100], rax
0x1400334c3  lea     rax, [rbp+var_30]
0x1400334c7  mov     [rsp+140h+var_108], rax
0x1400334cc  lea     rax, [rbp+var_74]
0x1400334d0  mov     [rbp+var_70], rcx
0x1400334d4  mov     ecx, [rdi+44h]
0x1400334d7  mov     [rsp+140h+var_110], rax
0x1400334dc  lea     rax, [rbp+var_28]
0x1400334e0  mov     [rbp+arg_0], ecx
0x1400334e3  mov     ecx, [rdi+10h]
0x1400334e6  mov     [rbp+arg_8], ecx
0x1400334e9  mov     rcx, [rdi+78h]
0x1400334ed  mov     [rsp+140h+var_118], rax
0x1400334f2  lea     rax, [rbp+var_20]
0x1400334f6  mov     [rbp+var_68], rcx
0x1400334fa  mov     rcx, r9
0x1400334fd  mov     [rsp+140h+var_120], rax
0x140033502  mov     [rbp+var_28], 1000000h
0x14003350a  mov     [rbp+var_20], 0
0x140033512  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140033517  jmp     short loc_14003357D
0x140033519  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14003351e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033523  mov     rdi, rax
0x140033526  mov     ecx, [rax]
0x140033528  cmp     ecx, 4
0x14003352b  jbe     short loc_14003357D
0x14003352d  call    cs:__imp_GetCurrentThreadId
0x140033533  mov     r8, [rbx+110h]
0x14003353a  lea     rdx, byte_1400863D9
0x140033541  mov     [rbp+arg_0], eax
0x140033544  xor     r9d, r9d
0x140033547  lea     rax, [rbp+arg_0]
0x14003354b  mov     [rsp+140h+var_110], rax
0x140033550  lea     rax, [rbp+arg_8]
0x140033554  mov     ecx, [r8+48h]
0x140033558  add     r8, 8
0x14003355c  mov     [rsp+140h+var_118], rax
0x140033561  lea     rax, [rbp+arg_10]
0x140033565  mov     [rbp+arg_8], ecx
0x140033568  mov     rcx, rdi
0x14003356b  mov     [rsp+140h+var_120], rax
0x140033570  mov     [rbp+arg_10], 0
0x140033578  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003357d  mov     rcx, rbx
0x140033580  add     rsp, 130h
0x140033587  pop     rdi
0x140033588  pop     rbx
0x140033589  pop     rbp
0x14003358a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
