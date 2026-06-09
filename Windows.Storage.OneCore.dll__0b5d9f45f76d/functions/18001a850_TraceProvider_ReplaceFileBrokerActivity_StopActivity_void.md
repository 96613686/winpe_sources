# TraceProvider::ReplaceFileBrokerActivity::StopActivity(void)

- ea: `0x18001a850`
- end: `0x18001aa7c`
- name: `?StopActivity@ReplaceFileBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::ReplaceFileBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x18001a850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa1d`

## pseudocode

```c
void __fastcall TraceProvider::ReplaceFileBrokerActivity::StopActivity(TraceProvider::ReplaceFileBrokerActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-40h] BYREF
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
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = TraceProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v7,
        (__int64)word_18002AC5A,
        v9 + 8,
        (__int64)v7,
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
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = TraceProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&word_18002ADAE,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this, v5, v6, v7);
}

```

## disassembly

```asm
0x18001a850  push    rbp
0x18001a852  push    rbx
0x18001a853  push    rdi
0x18001a854  lea     rbp, [rsp+10h]
0x18001a859  sub     rsp, 130h
0x18001a860  mov     rdi, [rcx+110h]
0x18001a867  mov     rbx, rcx
0x18001a86a  mov     eax, [rdi+48h]
0x18001a86d  test    eax, eax
0x18001a86f  jns     loc_18001AA09
0x18001a875  add     rdi, 50h ; 'P'
0x18001a879  cmp     eax, [rdi+8]
0x18001a87c  jnz     loc_18001AA09
0x18001a882  test    rdi, rdi
0x18001a885  jz      loc_18001AA09
0x18001a88b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a890  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a895  mov     r9, rax
0x18001a898  mov     ecx, [rax]
0x18001a89a  cmp     ecx, 5
0x18001a89d  jbe     loc_18001AA6A
0x18001a8a3  mov     rax, [rdi+70h]
0x18001a8a7  lea     rdx, word_18002AC5A
0x18001a8ae  mov     rcx, [rdi+30h]
0x18001a8b2  mov     [rbp+var_60], rax
0x18001a8b6  mov     eax, [rdi+68h]
0x18001a8b9  mov     r8, [rbx+110h]
0x18001a8c0  mov     dword ptr [rbp+arg_10], eax
0x18001a8c3  add     r8, 8
0x18001a8c7  mov     rax, [rdi+60h]
0x18001a8cb  mov     [rbp+var_58], rax
0x18001a8cf  mov     rax, [rdi+58h]
0x18001a8d3  mov     [rbp+var_50], rax
0x18001a8d7  mov     eax, [rdi+50h]
0x18001a8da  mov     [rbp+arg_18], eax
0x18001a8dd  mov     rax, [rdi+48h]
0x18001a8e1  mov     [rbp+var_48], rax
0x18001a8e5  mov     eax, [rdi+20h]
0x18001a8e8  mov     [rbp+var_80], eax
0x18001a8eb  mov     rax, [rdi+18h]
0x18001a8ef  mov     [rbp+var_40], rax
0x18001a8f3  mov     eax, [rdi]
0x18001a8f5  mov     [rbp+var_7C], eax
0x18001a8f8  mov     rax, [rdi+80h]
0x18001a8ff  mov     [rbp+var_38], rax
0x18001a903  mov     eax, [rdi+40h]
0x18001a906  mov     [rbp+var_78], eax
0x18001a909  mov     rax, [rdi+38h]
0x18001a90d  mov     [rbp+var_30], rax
0x18001a911  mov     eax, [rdi+8]
0x18001a914  mov     [rbp+var_74], eax
0x18001a917  lea     rax, [rbp+var_70]
0x18001a91b  mov     [rsp+140h+var_90], rax
0x18001a923  lea     rax, [rbp+arg_0]
0x18001a927  mov     [rsp+140h+var_98], rax
0x18001a92f  lea     rax, [rbp+arg_8]
0x18001a933  mov     [rsp+140h+var_A0], rax
0x18001a93b  lea     rax, [rbp+var_68]
0x18001a93f  mov     [rsp+140h+var_A8], rax
0x18001a947  lea     rax, [rbp+var_60]
0x18001a94b  mov     [rsp+140h+var_B0], rax
0x18001a953  lea     rax, [rbp+arg_10]
0x18001a957  mov     [rsp+140h+var_B8], rax
0x18001a95f  lea     rax, [rbp+var_58]
0x18001a963  mov     [rsp+140h+var_C0], rax
0x18001a96b  lea     rax, [rbp+var_50]
0x18001a96f  mov     [rsp+140h+var_C8], rax
0x18001a974  lea     rax, [rbp+arg_18]
0x18001a978  mov     [rsp+140h+var_D0], rax
0x18001a97d  lea     rax, [rbp+var_48]
0x18001a981  mov     [rsp+140h+var_D8], rax
0x18001a986  lea     rax, [rbp+var_80]
0x18001a98a  mov     [rsp+140h+var_E0], rax
0x18001a98f  lea     rax, [rbp+var_40]
0x18001a993  mov     [rsp+140h+var_E8], rax
0x18001a998  lea     rax, [rbp+var_7C]
0x18001a99c  mov     [rsp+140h+var_F0], rax
0x18001a9a1  lea     rax, [rbp+var_38]
0x18001a9a5  mov     [rsp+140h+var_F8], rax
0x18001a9aa  lea     rax, [rbp+var_78]
0x18001a9ae  mov     [rsp+140h+var_100], rax
0x18001a9b3  lea     rax, [rbp+var_30]
0x18001a9b7  mov     [rsp+140h+var_108], rax
0x18001a9bc  lea     rax, [rbp+var_74]
0x18001a9c0  mov     [rbp+var_70], rcx
0x18001a9c4  mov     ecx, [rdi+44h]
0x18001a9c7  mov     [rsp+140h+var_110], rax
0x18001a9cc  lea     rax, [rbp+var_28]
0x18001a9d0  mov     [rbp+arg_0], ecx
0x18001a9d3  mov     ecx, [rdi+10h]
0x18001a9d6  mov     [rbp+arg_8], ecx
0x18001a9d9  mov     rcx, [rdi+78h]
0x18001a9dd  mov     [rsp+140h+var_118], rax
0x18001a9e2  lea     rax, [rbp+var_20]
0x18001a9e6  mov     [rbp+var_68], rcx
0x18001a9ea  mov     rcx, r9
0x18001a9ed  mov     [rsp+140h+var_120], rax
0x18001a9f2  mov     [rbp+var_28], 1000000h
0x18001a9fa  mov     [rbp+var_20], 0
0x18001aa02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001aa07  jmp     short loc_18001AA6A
0x18001aa09  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aa0e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001aa13  mov     rdi, rax
0x18001aa16  mov     ecx, [rax]
0x18001aa18  cmp     ecx, 5
0x18001aa1b  jbe     short loc_18001AA6A
0x18001aa1d  call    cs:__imp_GetCurrentThreadId
0x18001aa23  mov     r8, [rbx+110h]
0x18001aa2a  lea     rdx, word_18002ADAE
0x18001aa31  mov     [rbp+arg_0], eax
0x18001aa34  lea     rax, [rbp+arg_0]
0x18001aa38  mov     [rsp+140h+var_110], rax
0x18001aa3d  lea     rax, [rbp+arg_8]
0x18001aa41  mov     [rsp+140h+var_118], rax
0x18001aa46  lea     rax, [rbp+arg_10]
0x18001aa4a  mov     ecx, [r8+48h]
0x18001aa4e  add     r8, 8
0x18001aa52  mov     [rbp+arg_8], ecx
0x18001aa55  mov     rcx, rdi
0x18001aa58  mov     [rsp+140h+var_120], rax
0x18001aa5d  mov     [rbp+arg_10], 0
0x18001aa65  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001aa6a  mov     rcx, rbx
0x18001aa6d  add     rsp, 130h
0x18001aa74  pop     rdi
0x18001aa75  pop     rbx
0x18001aa76  pop     rbp
0x18001aa77  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
