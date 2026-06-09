# TraceProvider::CreateDirectoryBrokerActivity::StopActivity(void)

- ea: `0x180019650`
- end: `0x18001987c`
- name: `?StopActivity@CreateDirectoryBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::CreateDirectoryBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180019650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001981d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001981d`

## pseudocode

```c
void __fastcall TraceProvider::CreateDirectoryBrokerActivity::StopActivity(
        TraceProvider::CreateDirectoryBrokerActivity *this)
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
        (__int64)word_18002A8EA,
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
        (__int64)word_18002AA42,
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
0x180019650  push    rbp
0x180019652  push    rbx
0x180019653  push    rdi
0x180019654  lea     rbp, [rsp+10h]
0x180019659  sub     rsp, 130h
0x180019660  mov     rdi, [rcx+110h]
0x180019667  mov     rbx, rcx
0x18001966a  mov     eax, [rdi+48h]
0x18001966d  test    eax, eax
0x18001966f  jns     loc_180019809
0x180019675  add     rdi, 50h ; 'P'
0x180019679  cmp     eax, [rdi+8]
0x18001967c  jnz     loc_180019809
0x180019682  test    rdi, rdi
0x180019685  jz      loc_180019809
0x18001968b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019690  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019695  mov     r9, rax
0x180019698  mov     ecx, [rax]
0x18001969a  cmp     ecx, 5
0x18001969d  jbe     loc_18001986A
0x1800196a3  mov     rax, [rdi+70h]
0x1800196a7  lea     rdx, word_18002A8EA
0x1800196ae  mov     rcx, [rdi+30h]
0x1800196b2  mov     [rbp+var_60], rax
0x1800196b6  mov     eax, [rdi+68h]
0x1800196b9  mov     r8, [rbx+110h]
0x1800196c0  mov     dword ptr [rbp+arg_10], eax
0x1800196c3  add     r8, 8
0x1800196c7  mov     rax, [rdi+60h]
0x1800196cb  mov     [rbp+var_58], rax
0x1800196cf  mov     rax, [rdi+58h]
0x1800196d3  mov     [rbp+var_50], rax
0x1800196d7  mov     eax, [rdi+50h]
0x1800196da  mov     [rbp+arg_18], eax
0x1800196dd  mov     rax, [rdi+48h]
0x1800196e1  mov     [rbp+var_48], rax
0x1800196e5  mov     eax, [rdi+20h]
0x1800196e8  mov     [rbp+var_80], eax
0x1800196eb  mov     rax, [rdi+18h]
0x1800196ef  mov     [rbp+var_40], rax
0x1800196f3  mov     eax, [rdi]
0x1800196f5  mov     [rbp+var_7C], eax
0x1800196f8  mov     rax, [rdi+80h]
0x1800196ff  mov     [rbp+var_38], rax
0x180019703  mov     eax, [rdi+40h]
0x180019706  mov     [rbp+var_78], eax
0x180019709  mov     rax, [rdi+38h]
0x18001970d  mov     [rbp+var_30], rax
0x180019711  mov     eax, [rdi+8]
0x180019714  mov     [rbp+var_74], eax
0x180019717  lea     rax, [rbp+var_70]
0x18001971b  mov     [rsp+140h+var_90], rax
0x180019723  lea     rax, [rbp+arg_0]
0x180019727  mov     [rsp+140h+var_98], rax
0x18001972f  lea     rax, [rbp+arg_8]
0x180019733  mov     [rsp+140h+var_A0], rax
0x18001973b  lea     rax, [rbp+var_68]
0x18001973f  mov     [rsp+140h+var_A8], rax
0x180019747  lea     rax, [rbp+var_60]
0x18001974b  mov     [rsp+140h+var_B0], rax
0x180019753  lea     rax, [rbp+arg_10]
0x180019757  mov     [rsp+140h+var_B8], rax
0x18001975f  lea     rax, [rbp+var_58]
0x180019763  mov     [rsp+140h+var_C0], rax
0x18001976b  lea     rax, [rbp+var_50]
0x18001976f  mov     [rsp+140h+var_C8], rax
0x180019774  lea     rax, [rbp+arg_18]
0x180019778  mov     [rsp+140h+var_D0], rax
0x18001977d  lea     rax, [rbp+var_48]
0x180019781  mov     [rsp+140h+var_D8], rax
0x180019786  lea     rax, [rbp+var_80]
0x18001978a  mov     [rsp+140h+var_E0], rax
0x18001978f  lea     rax, [rbp+var_40]
0x180019793  mov     [rsp+140h+var_E8], rax
0x180019798  lea     rax, [rbp+var_7C]
0x18001979c  mov     [rsp+140h+var_F0], rax
0x1800197a1  lea     rax, [rbp+var_38]
0x1800197a5  mov     [rsp+140h+var_F8], rax
0x1800197aa  lea     rax, [rbp+var_78]
0x1800197ae  mov     [rsp+140h+var_100], rax
0x1800197b3  lea     rax, [rbp+var_30]
0x1800197b7  mov     [rsp+140h+var_108], rax
0x1800197bc  lea     rax, [rbp+var_74]
0x1800197c0  mov     [rbp+var_70], rcx
0x1800197c4  mov     ecx, [rdi+44h]
0x1800197c7  mov     [rsp+140h+var_110], rax
0x1800197cc  lea     rax, [rbp+var_28]
0x1800197d0  mov     [rbp+arg_0], ecx
0x1800197d3  mov     ecx, [rdi+10h]
0x1800197d6  mov     [rbp+arg_8], ecx
0x1800197d9  mov     rcx, [rdi+78h]
0x1800197dd  mov     [rsp+140h+var_118], rax
0x1800197e2  lea     rax, [rbp+var_20]
0x1800197e6  mov     [rbp+var_68], rcx
0x1800197ea  mov     rcx, r9
0x1800197ed  mov     [rsp+140h+var_120], rax
0x1800197f2  mov     [rbp+var_28], 1000000h
0x1800197fa  mov     [rbp+var_20], 0
0x180019802  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019807  jmp     short loc_18001986A
0x180019809  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001980e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019813  mov     rdi, rax
0x180019816  mov     ecx, [rax]
0x180019818  cmp     ecx, 5
0x18001981b  jbe     short loc_18001986A
0x18001981d  call    cs:__imp_GetCurrentThreadId
0x180019823  mov     r8, [rbx+110h]
0x18001982a  lea     rdx, word_18002AA42
0x180019831  mov     [rbp+arg_0], eax
0x180019834  lea     rax, [rbp+arg_0]
0x180019838  mov     [rsp+140h+var_110], rax
0x18001983d  lea     rax, [rbp+arg_8]
0x180019841  mov     [rsp+140h+var_118], rax
0x180019846  lea     rax, [rbp+arg_10]
0x18001984a  mov     ecx, [r8+48h]
0x18001984e  add     r8, 8
0x180019852  mov     [rbp+arg_8], ecx
0x180019855  mov     rcx, rdi
0x180019858  mov     [rsp+140h+var_120], rax
0x18001985d  mov     [rbp+arg_10], 0
0x180019865  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001986a  mov     rcx, rbx
0x18001986d  add     rsp, 130h
0x180019874  pop     rdi
0x180019875  pop     rbx
0x180019876  pop     rbp
0x180019877  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
