# TraceProvider::CreateFile2BrokerActivity::StopActivity(void)

- ea: `0x180019890`
- end: `0x180019abc`
- name: `?StopActivity@CreateFile2BrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::CreateFile2BrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180019890`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a5d`

## pseudocode

```c
void __fastcall TraceProvider::CreateFile2BrokerActivity::StopActivity(TraceProvider::CreateFile2BrokerActivity *this)
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
        (__int64)word_18002B68A,
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
        (__int64)&word_18002B7DE,
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
0x180019890  push    rbp
0x180019892  push    rbx
0x180019893  push    rdi
0x180019894  lea     rbp, [rsp+10h]
0x180019899  sub     rsp, 130h
0x1800198a0  mov     rdi, [rcx+110h]
0x1800198a7  mov     rbx, rcx
0x1800198aa  mov     eax, [rdi+48h]
0x1800198ad  test    eax, eax
0x1800198af  jns     loc_180019A49
0x1800198b5  add     rdi, 50h ; 'P'
0x1800198b9  cmp     eax, [rdi+8]
0x1800198bc  jnz     loc_180019A49
0x1800198c2  test    rdi, rdi
0x1800198c5  jz      loc_180019A49
0x1800198cb  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800198d0  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x1800198d5  mov     r9, rax
0x1800198d8  mov     ecx, [rax]
0x1800198da  cmp     ecx, 5
0x1800198dd  jbe     loc_180019AAA
0x1800198e3  mov     rax, [rdi+70h]
0x1800198e7  lea     rdx, word_18002B68A
0x1800198ee  mov     rcx, [rdi+30h]
0x1800198f2  mov     [rbp+var_60], rax
0x1800198f6  mov     eax, [rdi+68h]
0x1800198f9  mov     r8, [rbx+110h]
0x180019900  mov     dword ptr [rbp+arg_10], eax
0x180019903  add     r8, 8
0x180019907  mov     rax, [rdi+60h]
0x18001990b  mov     [rbp+var_58], rax
0x18001990f  mov     rax, [rdi+58h]
0x180019913  mov     [rbp+var_50], rax
0x180019917  mov     eax, [rdi+50h]
0x18001991a  mov     [rbp+arg_18], eax
0x18001991d  mov     rax, [rdi+48h]
0x180019921  mov     [rbp+var_48], rax
0x180019925  mov     eax, [rdi+20h]
0x180019928  mov     [rbp+var_80], eax
0x18001992b  mov     rax, [rdi+18h]
0x18001992f  mov     [rbp+var_40], rax
0x180019933  mov     eax, [rdi]
0x180019935  mov     [rbp+var_7C], eax
0x180019938  mov     rax, [rdi+80h]
0x18001993f  mov     [rbp+var_38], rax
0x180019943  mov     eax, [rdi+40h]
0x180019946  mov     [rbp+var_78], eax
0x180019949  mov     rax, [rdi+38h]
0x18001994d  mov     [rbp+var_30], rax
0x180019951  mov     eax, [rdi+8]
0x180019954  mov     [rbp+var_74], eax
0x180019957  lea     rax, [rbp+var_70]
0x18001995b  mov     [rsp+140h+var_90], rax
0x180019963  lea     rax, [rbp+arg_0]
0x180019967  mov     [rsp+140h+var_98], rax
0x18001996f  lea     rax, [rbp+arg_8]
0x180019973  mov     [rsp+140h+var_A0], rax
0x18001997b  lea     rax, [rbp+var_68]
0x18001997f  mov     [rsp+140h+var_A8], rax
0x180019987  lea     rax, [rbp+var_60]
0x18001998b  mov     [rsp+140h+var_B0], rax
0x180019993  lea     rax, [rbp+arg_10]
0x180019997  mov     [rsp+140h+var_B8], rax
0x18001999f  lea     rax, [rbp+var_58]
0x1800199a3  mov     [rsp+140h+var_C0], rax
0x1800199ab  lea     rax, [rbp+var_50]
0x1800199af  mov     [rsp+140h+var_C8], rax
0x1800199b4  lea     rax, [rbp+arg_18]
0x1800199b8  mov     [rsp+140h+var_D0], rax
0x1800199bd  lea     rax, [rbp+var_48]
0x1800199c1  mov     [rsp+140h+var_D8], rax
0x1800199c6  lea     rax, [rbp+var_80]
0x1800199ca  mov     [rsp+140h+var_E0], rax
0x1800199cf  lea     rax, [rbp+var_40]
0x1800199d3  mov     [rsp+140h+var_E8], rax
0x1800199d8  lea     rax, [rbp+var_7C]
0x1800199dc  mov     [rsp+140h+var_F0], rax
0x1800199e1  lea     rax, [rbp+var_38]
0x1800199e5  mov     [rsp+140h+var_F8], rax
0x1800199ea  lea     rax, [rbp+var_78]
0x1800199ee  mov     [rsp+140h+var_100], rax
0x1800199f3  lea     rax, [rbp+var_30]
0x1800199f7  mov     [rsp+140h+var_108], rax
0x1800199fc  lea     rax, [rbp+var_74]
0x180019a00  mov     [rbp+var_70], rcx
0x180019a04  mov     ecx, [rdi+44h]
0x180019a07  mov     [rsp+140h+var_110], rax
0x180019a0c  lea     rax, [rbp+var_28]
0x180019a10  mov     [rbp+arg_0], ecx
0x180019a13  mov     ecx, [rdi+10h]
0x180019a16  mov     [rbp+arg_8], ecx
0x180019a19  mov     rcx, [rdi+78h]
0x180019a1d  mov     [rsp+140h+var_118], rax
0x180019a22  lea     rax, [rbp+var_20]
0x180019a26  mov     [rbp+var_68], rcx
0x180019a2a  mov     rcx, r9
0x180019a2d  mov     [rsp+140h+var_120], rax
0x180019a32  mov     [rbp+var_28], 1000000h
0x180019a3a  mov     [rbp+var_20], 0
0x180019a42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019a47  jmp     short loc_180019AAA
0x180019a49  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019a4e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019a53  mov     rdi, rax
0x180019a56  mov     ecx, [rax]
0x180019a58  cmp     ecx, 5
0x180019a5b  jbe     short loc_180019AAA
0x180019a5d  call    cs:__imp_GetCurrentThreadId
0x180019a63  mov     r8, [rbx+110h]
0x180019a6a  lea     rdx, word_18002B7DE
0x180019a71  mov     [rbp+arg_0], eax
0x180019a74  lea     rax, [rbp+arg_0]
0x180019a78  mov     [rsp+140h+var_110], rax
0x180019a7d  lea     rax, [rbp+arg_8]
0x180019a81  mov     [rsp+140h+var_118], rax
0x180019a86  lea     rax, [rbp+arg_10]
0x180019a8a  mov     ecx, [r8+48h]
0x180019a8e  add     r8, 8
0x180019a92  mov     [rbp+arg_8], ecx
0x180019a95  mov     rcx, rdi
0x180019a98  mov     [rsp+140h+var_120], rax
0x180019a9d  mov     [rbp+arg_10], 0
0x180019aa5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019aaa  mov     rcx, rbx
0x180019aad  add     rsp, 130h
0x180019ab4  pop     rdi
0x180019ab5  pop     rbx
0x180019ab6  pop     rbp
0x180019ab7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
