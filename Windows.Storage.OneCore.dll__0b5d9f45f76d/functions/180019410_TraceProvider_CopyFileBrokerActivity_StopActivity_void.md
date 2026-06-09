# TraceProvider::CopyFileBrokerActivity::StopActivity(void)

- ea: `0x180019410`
- end: `0x18001963c`
- name: `?StopActivity@CopyFileBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::CopyFileBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180019410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800195dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800195dd`

## pseudocode

```c
void __fastcall TraceProvider::CopyFileBrokerActivity::StopActivity(TraceProvider::CopyFileBrokerActivity *this)
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
        (__int64)&unk_18002B838,
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
        (__int64)byte_18002B989,
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
0x180019410  push    rbp
0x180019412  push    rbx
0x180019413  push    rdi
0x180019414  lea     rbp, [rsp+10h]
0x180019419  sub     rsp, 130h
0x180019420  mov     rdi, [rcx+110h]
0x180019427  mov     rbx, rcx
0x18001942a  mov     eax, [rdi+48h]
0x18001942d  test    eax, eax
0x18001942f  jns     loc_1800195C9
0x180019435  add     rdi, 50h ; 'P'
0x180019439  cmp     eax, [rdi+8]
0x18001943c  jnz     loc_1800195C9
0x180019442  test    rdi, rdi
0x180019445  jz      loc_1800195C9
0x18001944b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019450  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019455  mov     r9, rax
0x180019458  mov     ecx, [rax]
0x18001945a  cmp     ecx, 5
0x18001945d  jbe     loc_18001962A
0x180019463  mov     rax, [rdi+70h]
0x180019467  lea     rdx, unk_18002B838
0x18001946e  mov     rcx, [rdi+30h]
0x180019472  mov     [rbp+var_60], rax
0x180019476  mov     eax, [rdi+68h]
0x180019479  mov     r8, [rbx+110h]
0x180019480  mov     dword ptr [rbp+arg_10], eax
0x180019483  add     r8, 8
0x180019487  mov     rax, [rdi+60h]
0x18001948b  mov     [rbp+var_58], rax
0x18001948f  mov     rax, [rdi+58h]
0x180019493  mov     [rbp+var_50], rax
0x180019497  mov     eax, [rdi+50h]
0x18001949a  mov     [rbp+arg_18], eax
0x18001949d  mov     rax, [rdi+48h]
0x1800194a1  mov     [rbp+var_48], rax
0x1800194a5  mov     eax, [rdi+20h]
0x1800194a8  mov     [rbp+var_80], eax
0x1800194ab  mov     rax, [rdi+18h]
0x1800194af  mov     [rbp+var_40], rax
0x1800194b3  mov     eax, [rdi]
0x1800194b5  mov     [rbp+var_7C], eax
0x1800194b8  mov     rax, [rdi+80h]
0x1800194bf  mov     [rbp+var_38], rax
0x1800194c3  mov     eax, [rdi+40h]
0x1800194c6  mov     [rbp+var_78], eax
0x1800194c9  mov     rax, [rdi+38h]
0x1800194cd  mov     [rbp+var_30], rax
0x1800194d1  mov     eax, [rdi+8]
0x1800194d4  mov     [rbp+var_74], eax
0x1800194d7  lea     rax, [rbp+var_70]
0x1800194db  mov     [rsp+140h+var_90], rax
0x1800194e3  lea     rax, [rbp+arg_0]
0x1800194e7  mov     [rsp+140h+var_98], rax
0x1800194ef  lea     rax, [rbp+arg_8]
0x1800194f3  mov     [rsp+140h+var_A0], rax
0x1800194fb  lea     rax, [rbp+var_68]
0x1800194ff  mov     [rsp+140h+var_A8], rax
0x180019507  lea     rax, [rbp+var_60]
0x18001950b  mov     [rsp+140h+var_B0], rax
0x180019513  lea     rax, [rbp+arg_10]
0x180019517  mov     [rsp+140h+var_B8], rax
0x18001951f  lea     rax, [rbp+var_58]
0x180019523  mov     [rsp+140h+var_C0], rax
0x18001952b  lea     rax, [rbp+var_50]
0x18001952f  mov     [rsp+140h+var_C8], rax
0x180019534  lea     rax, [rbp+arg_18]
0x180019538  mov     [rsp+140h+var_D0], rax
0x18001953d  lea     rax, [rbp+var_48]
0x180019541  mov     [rsp+140h+var_D8], rax
0x180019546  lea     rax, [rbp+var_80]
0x18001954a  mov     [rsp+140h+var_E0], rax
0x18001954f  lea     rax, [rbp+var_40]
0x180019553  mov     [rsp+140h+var_E8], rax
0x180019558  lea     rax, [rbp+var_7C]
0x18001955c  mov     [rsp+140h+var_F0], rax
0x180019561  lea     rax, [rbp+var_38]
0x180019565  mov     [rsp+140h+var_F8], rax
0x18001956a  lea     rax, [rbp+var_78]
0x18001956e  mov     [rsp+140h+var_100], rax
0x180019573  lea     rax, [rbp+var_30]
0x180019577  mov     [rsp+140h+var_108], rax
0x18001957c  lea     rax, [rbp+var_74]
0x180019580  mov     [rbp+var_70], rcx
0x180019584  mov     ecx, [rdi+44h]
0x180019587  mov     [rsp+140h+var_110], rax
0x18001958c  lea     rax, [rbp+var_28]
0x180019590  mov     [rbp+arg_0], ecx
0x180019593  mov     ecx, [rdi+10h]
0x180019596  mov     [rbp+arg_8], ecx
0x180019599  mov     rcx, [rdi+78h]
0x18001959d  mov     [rsp+140h+var_118], rax
0x1800195a2  lea     rax, [rbp+var_20]
0x1800195a6  mov     [rbp+var_68], rcx
0x1800195aa  mov     rcx, r9
0x1800195ad  mov     [rsp+140h+var_120], rax
0x1800195b2  mov     [rbp+var_28], 1000000h
0x1800195ba  mov     [rbp+var_20], 0
0x1800195c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800195c7  jmp     short loc_18001962A
0x1800195c9  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800195ce  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x1800195d3  mov     rdi, rax
0x1800195d6  mov     ecx, [rax]
0x1800195d8  cmp     ecx, 5
0x1800195db  jbe     short loc_18001962A
0x1800195dd  call    cs:__imp_GetCurrentThreadId
0x1800195e3  mov     r8, [rbx+110h]
0x1800195ea  lea     rdx, byte_18002B989
0x1800195f1  mov     [rbp+arg_0], eax
0x1800195f4  lea     rax, [rbp+arg_0]
0x1800195f8  mov     [rsp+140h+var_110], rax
0x1800195fd  lea     rax, [rbp+arg_8]
0x180019601  mov     [rsp+140h+var_118], rax
0x180019606  lea     rax, [rbp+arg_10]
0x18001960a  mov     ecx, [r8+48h]
0x18001960e  add     r8, 8
0x180019612  mov     [rbp+arg_8], ecx
0x180019615  mov     rcx, rdi
0x180019618  mov     [rsp+140h+var_120], rax
0x18001961d  mov     [rbp+arg_10], 0
0x180019625  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001962a  mov     rcx, rbx
0x18001962d  add     rsp, 130h
0x180019634  pop     rdi
0x180019635  pop     rbx
0x180019636  pop     rbp
0x180019637  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
