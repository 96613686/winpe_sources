# WnsCPLog::WnsCMChannelRequestExpired::StopActivity(void)

- ea: `0x180030620`
- end: `0x180030847`
- name: `?StopActivity@WnsCMChannelRequestExpired@WnsCPLog@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(WnsCPLog::WnsCMChannelRequestExpired *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001e64`
- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180013130`
- `0x180018430`
- `0x180030620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800307e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800307e5`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMChannelRequestExpired::StopActivity(WnsCPLog::WnsCMChannelRequestExpired *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
    {
      v8 = *((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&byte_1800402D7,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = WnsCPTracelogger::Provider();
    v13 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v15 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)&dword_18004027C,
        (const GUID *)(v15 + 8),
        0,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180030620  push    rbp
0x180030622  push    rbx
0x180030623  push    rdi
0x180030624  lea     rbp, [rsp-47h]
0x180030629  sub     rsp, 100h
0x180030630  mov     rdi, [rcx+110h]
0x180030637  mov     rbx, rcx
0x18003063a  mov     eax, [rdi+48h]
0x18003063d  test    eax, eax
0x18003063f  jns     loc_1800307BB
0x180030645  add     rdi, 50h ; 'P'
0x180030649  cmp     eax, [rdi+8]
0x18003064c  jnz     loc_1800307BB
0x180030652  test    rdi, rdi
0x180030655  jz      loc_1800307BB
0x18003065b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180030660  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180030665  mov     r9, rax
0x180030668  mov     ecx, [rax]
0x18003066a  cmp     ecx, 5
0x18003066d  jbe     loc_180030835
0x180030673  mov     rdx, 200000000000h
0x18003067d  mov     rcx, rax
0x180030680  call    _tlgKeywordOn
0x180030685  test    al, al
0x180030687  jz      loc_180030835
0x18003068d  mov     rax, [rdi+70h]
0x180030691  lea     rdx, byte_1800402D7
0x180030698  mov     rcx, [rdi+78h]
0x18003069c  mov     r8, [rbx+110h]
0x1800306a3  mov     [rbp+57h+var_60], rax
0x1800306a7  add     r8, 8
0x1800306ab  mov     eax, [rdi+68h]
0x1800306ae  mov     [rbp+57h+arg_0], eax
0x1800306b1  mov     rax, [rdi+60h]
0x1800306b5  mov     [rbp+57h+var_58], rax
0x1800306b9  mov     rax, [rdi+58h]
0x1800306bd  mov     [rbp+57h+var_50], rax
0x1800306c1  mov     eax, [rdi+50h]
0x1800306c4  mov     [rbp+57h+arg_8], eax
0x1800306c7  mov     rax, [rdi+48h]
0x1800306cb  mov     [rbp+57h+var_48], rax
0x1800306cf  mov     eax, [rdi+20h]
0x1800306d2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800306d5  mov     rax, [rdi+18h]
0x1800306d9  mov     [rbp+57h+var_40], rax
0x1800306dd  mov     eax, [rdi]
0x1800306df  mov     [rbp+57h+arg_18], eax
0x1800306e2  mov     rax, [rdi+80h]
0x1800306e9  mov     [rbp+57h+var_38], rax
0x1800306ed  mov     eax, [rdi+40h]
0x1800306f0  mov     [rbp+57h+var_70], eax
0x1800306f3  mov     rax, [rdi+38h]
0x1800306f7  mov     [rbp+57h+var_30], rax
0x1800306fb  mov     eax, [rdi+8]
0x1800306fe  mov     [rbp+57h+var_6C], eax
0x180030701  lea     rax, [rbp+57h+var_68]
0x180030705  mov     [rsp+110h+var_78], rax
0x18003070d  lea     rax, [rbp+57h+var_60]
0x180030711  mov     [rsp+110h+var_80], rax
0x180030719  lea     rax, [rbp+57h+arg_0]
0x18003071d  mov     [rsp+110h+var_88], rax
0x180030725  lea     rax, [rbp+57h+var_58]
0x180030729  mov     [rsp+110h+var_90], rax
0x180030731  lea     rax, [rbp+57h+var_50]
0x180030735  mov     [rsp+110h+var_98], rax
0x18003073a  lea     rax, [rbp+57h+arg_8]
0x18003073e  mov     [rsp+110h+var_A0], rax
0x180030743  lea     rax, [rbp+57h+var_48]
0x180030747  mov     [rsp+110h+var_A8], rax
0x18003074c  lea     rax, [rbp+57h+arg_10]
0x180030750  mov     [rsp+110h+var_B0], rax
0x180030755  lea     rax, [rbp+57h+var_40]
0x180030759  mov     [rsp+110h+var_B8], rax
0x18003075e  lea     rax, [rbp+57h+arg_18]
0x180030762  mov     [rsp+110h+var_C0], rax
0x180030767  lea     rax, [rbp+57h+var_38]
0x18003076b  mov     [rsp+110h+var_C8], rax
0x180030770  lea     rax, [rbp+57h+var_70]
0x180030774  mov     [rsp+110h+var_D0], rax
0x180030779  lea     rax, [rbp+57h+var_30]
0x18003077d  mov     [rsp+110h+var_D8], rax
0x180030782  lea     rax, [rbp+57h+var_6C]
0x180030786  mov     [rsp+110h+var_E0], rax
0x18003078b  lea     rax, [rbp+57h+var_28]
0x18003078f  mov     [rsp+110h+var_E8], rax
0x180030794  lea     rax, [rbp+57h+var_20]
0x180030798  mov     [rbp+57h+var_68], rcx
0x18003079c  mov     rcx, r9
0x18003079f  mov     [rsp+110h+var_F0], rax
0x1800307a4  mov     [rbp+57h+var_28], 1000000h
0x1800307ac  mov     [rbp+57h+var_20], 0
0x1800307b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800307b9  jmp     short loc_180030835
0x1800307bb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800307c0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800307c5  mov     rdi, rax
0x1800307c8  mov     ecx, [rax]
0x1800307ca  cmp     ecx, 5
0x1800307cd  jbe     short loc_180030835
0x1800307cf  mov     rdx, 200000000000h
0x1800307d9  mov     rcx, rax
0x1800307dc  call    _tlgKeywordOn
0x1800307e1  test    al, al
0x1800307e3  jz      short loc_180030835
0x1800307e5  call    cs:__imp_GetCurrentThreadId
0x1800307eb  mov     r8, [rbx+110h]
0x1800307f2  lea     rdx, dword_18004027C
0x1800307f9  mov     [rbp+57h+arg_0], eax
0x1800307fc  xor     r9d, r9d
0x1800307ff  mov     rcx, rdi
0x180030802  mov     eax, [r8+48h]
0x180030806  add     r8, 8
0x18003080a  mov     [rbp+57h+arg_8], eax
0x18003080d  lea     rax, [rbp+57h+arg_0]
0x180030811  mov     [rsp+110h+var_E0], rax
0x180030816  lea     rax, [rbp+57h+arg_8]
0x18003081a  mov     [rsp+110h+var_E8], rax
0x18003081f  lea     rax, [rbp+57h+arg_10]
0x180030823  mov     [rsp+110h+var_F0], rax
0x180030828  mov     [rbp+57h+arg_10], 0
0x180030830  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030835  mov     rcx, rbx
0x180030838  add     rsp, 100h
0x18003083f  pop     rdi
0x180030840  pop     rbx
0x180030841  pop     rbp
0x180030842  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
