# CASTraceProvider::ExecuteCustomAction::StopActivity(void)

- ea: `0x14000b510`
- end: `0x14000b732`
- name: `?StopActivity@ExecuteCustomAction@CASTraceProvider@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CASTraceProvider::ExecuteCustomAction *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001010`
- `0x140001bcc`
- `0x14000258c`
- `0x140009730`
- `0x14000a594`
- `0x14000b510`
- `0x14000babc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b6d2`

## pseudocode

```c
void __fastcall CASTraceProvider::ExecuteCustomAction::StopActivity(CASTraceProvider::ExecuteCustomAction *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v21; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v22; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v23; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v24; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v26; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v30[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v31; // [rsp+120h] [rbp+67h] BYREF
  int v32; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v33; // [rsp+130h] [rbp+77h] BYREF
  int v34; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = CASTraceProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v6) )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v31 = v4[26];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v33) = v4[8];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v34 = *v4;
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v19 = v4[16];
      v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v20 = v4[2];
      v29 = 0x1000000;
      v30[0] = 0x1000000;
      v21 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&word_1400125A6,
        v10 + 8,
        v8,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v20,
        &v28,
        (__int64)&v19,
        &v27,
        (__int64)&v34,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        &v23,
        (__int64)&v31,
        &v22,
        &v21);
    }
  }
  else
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = CASTraceProvider::Provider(v11);
    v15 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13, v14) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v17 + 72);
      v33 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)byte_1400126D1,
        v17 + 8,
        v18,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000b510  push    rbp
0x14000b512  push    rbx
0x14000b513  push    rdi
0x14000b514  lea     rbp, [rsp-47h]
0x14000b519  sub     rsp, 100h
0x14000b520  mov     rdi, [rcx+110h]
0x14000b527  mov     rbx, rcx
0x14000b52a  mov     eax, [rdi+48h]
0x14000b52d  test    eax, eax
0x14000b52f  jns     loc_14000B6A8
0x14000b535  add     rdi, 50h ; 'P'
0x14000b539  cmp     eax, [rdi+8]
0x14000b53c  jnz     loc_14000B6A8
0x14000b542  test    rdi, rdi
0x14000b545  jz      loc_14000B6A8
0x14000b54b  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b550  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b555  mov     r9, rax
0x14000b558  mov     ecx, [rax]
0x14000b55a  cmp     ecx, 5
0x14000b55d  jbe     loc_14000B720
0x14000b563  mov     rdx, 400000000000h
0x14000b56d  mov     rcx, rax
0x14000b570  call    _tlgKeywordOn
0x14000b575  test    al, al
0x14000b577  jz      loc_14000B720
0x14000b57d  mov     rax, [rdi+70h]
0x14000b581  lea     rdx, word_1400125A6
0x14000b588  mov     rcx, [rdi+78h]
0x14000b58c  mov     r8, [rbx+110h]
0x14000b593  mov     [rbp+57h+var_60], rax
0x14000b597  add     r8, 8
0x14000b59b  mov     eax, [rdi+68h]
0x14000b59e  mov     [rbp+57h+arg_0], eax
0x14000b5a1  mov     rax, [rdi+60h]
0x14000b5a5  mov     [rbp+57h+var_58], rax
0x14000b5a9  mov     rax, [rdi+58h]
0x14000b5ad  mov     [rbp+57h+var_50], rax
0x14000b5b1  mov     eax, [rdi+50h]
0x14000b5b4  mov     [rbp+57h+arg_8], eax
0x14000b5b7  mov     rax, [rdi+48h]
0x14000b5bb  mov     [rbp+57h+var_48], rax
0x14000b5bf  mov     eax, [rdi+20h]
0x14000b5c2  mov     dword ptr [rbp+57h+arg_10], eax
0x14000b5c5  mov     rax, [rdi+18h]
0x14000b5c9  mov     [rbp+57h+var_40], rax
0x14000b5cd  mov     eax, [rdi]
0x14000b5cf  mov     [rbp+57h+arg_18], eax
0x14000b5d2  mov     rax, [rdi+80h]
0x14000b5d9  mov     [rbp+57h+var_38], rax
0x14000b5dd  mov     eax, [rdi+40h]
0x14000b5e0  mov     [rbp+57h+var_70], eax
0x14000b5e3  mov     rax, [rdi+38h]
0x14000b5e7  mov     [rbp+57h+var_30], rax
0x14000b5eb  mov     eax, [rdi+8]
0x14000b5ee  mov     [rbp+57h+var_6C], eax
0x14000b5f1  mov     eax, 1000000h
0x14000b5f6  mov     [rbp+57h+var_28], rax
0x14000b5fa  mov     [rbp+57h+var_20], rax
0x14000b5fe  lea     rax, [rbp+57h+var_68]
0x14000b602  mov     [rsp+110h+var_78], rax
0x14000b60a  lea     rax, [rbp+57h+var_60]
0x14000b60e  mov     [rsp+110h+var_80], rax
0x14000b616  lea     rax, [rbp+57h+arg_0]
0x14000b61a  mov     [rsp+110h+var_88], rax
0x14000b622  lea     rax, [rbp+57h+var_58]
0x14000b626  mov     [rsp+110h+var_90], rax
0x14000b62e  lea     rax, [rbp+57h+var_50]
0x14000b632  mov     [rsp+110h+var_98], rax
0x14000b637  lea     rax, [rbp+57h+arg_8]
0x14000b63b  mov     [rsp+110h+var_A0], rax
0x14000b640  lea     rax, [rbp+57h+var_48]
0x14000b644  mov     [rsp+110h+var_A8], rax
0x14000b649  lea     rax, [rbp+57h+arg_10]
0x14000b64d  mov     [rsp+110h+var_B0], rax
0x14000b652  lea     rax, [rbp+57h+var_40]
0x14000b656  mov     [rsp+110h+var_B8], rax
0x14000b65b  lea     rax, [rbp+57h+arg_18]
0x14000b65f  mov     [rsp+110h+var_C0], rax
0x14000b664  lea     rax, [rbp+57h+var_38]
0x14000b668  mov     [rsp+110h+var_C8], rax
0x14000b66d  lea     rax, [rbp+57h+var_70]
0x14000b671  mov     [rsp+110h+var_D0], rax
0x14000b676  lea     rax, [rbp+57h+var_30]
0x14000b67a  mov     [rsp+110h+var_D8], rax
0x14000b67f  lea     rax, [rbp+57h+var_6C]
0x14000b683  mov     [rsp+110h+var_E0], rax
0x14000b688  lea     rax, [rbp+57h+var_28]
0x14000b68c  mov     [rsp+110h+var_E8], rax
0x14000b691  lea     rax, [rbp+57h+var_20]
0x14000b695  mov     [rbp+57h+var_68], rcx
0x14000b699  mov     rcx, r9
0x14000b69c  mov     [rsp+110h+var_F0], rax
0x14000b6a1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b6a6  jmp     short loc_14000B720
0x14000b6a8  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b6ad  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b6b2  mov     rdi, rax
0x14000b6b5  mov     ecx, [rax]
0x14000b6b7  cmp     ecx, 5
0x14000b6ba  jbe     short loc_14000B720
0x14000b6bc  mov     rdx, 400000000000h
0x14000b6c6  mov     rcx, rax
0x14000b6c9  call    _tlgKeywordOn
0x14000b6ce  test    al, al
0x14000b6d0  jz      short loc_14000B720
0x14000b6d2  call    cs:__imp_GetCurrentThreadId
0x14000b6d8  mov     r8, [rbx+110h]
0x14000b6df  lea     rdx, byte_1400126D1
0x14000b6e6  mov     [rbp+57h+arg_0], eax
0x14000b6e9  mov     rcx, rdi
0x14000b6ec  mov     eax, [r8+48h]
0x14000b6f0  add     r8, 8
0x14000b6f4  mov     [rbp+57h+arg_8], eax
0x14000b6f7  mov     eax, 1000000h
0x14000b6fc  mov     [rbp+57h+arg_10], rax
0x14000b700  lea     rax, [rbp+57h+arg_0]
0x14000b704  mov     [rsp+110h+var_E0], rax
0x14000b709  lea     rax, [rbp+57h+arg_8]
0x14000b70d  mov     [rsp+110h+var_E8], rax
0x14000b712  lea     rax, [rbp+57h+arg_10]
0x14000b716  mov     [rsp+110h+var_F0], rax
0x14000b71b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000b720  mov     rcx, rbx
0x14000b723  add     rsp, 100h
0x14000b72a  pop     rdi
0x14000b72b  pop     rbx
0x14000b72c  pop     rbp
0x14000b72d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
