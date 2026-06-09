# WnsCPLog::WnsMuxMakeCM::StopActivity(void)

- ea: `0x180018fa0`
- end: `0x1800191cf`
- name: `?StopActivity@WnsMuxMakeCM@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsMuxMakeCM *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x180018fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001916d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001916d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsMuxMakeCM::StopActivity(WnsCPLog::WnsMuxMakeCM *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // [rsp+C0h] [rbp-80h] BYREF
  int v12; // [rsp+C4h] [rbp-7Ch] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v15; // [rsp+D0h] [rbp-70h] BYREF
  int *v16; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+E0h] [rbp-60h] BYREF
  int *v18; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v20; // [rsp+F8h] [rbp-48h] BYREF
  int *v21; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v23; // [rsp+110h] [rbp-30h] BYREF
  __int64 v24; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v25[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v26; // [rsp+150h] [rbp+10h] BYREF
  int v27; // [rsp+158h] [rbp+18h] BYREF
  __int64 v28; // [rsp+160h] [rbp+20h] BYREF
  int v29; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v28) = v4[26];
      v18 = (int *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v11 = v4[8];
      v21 = (int *)*((_QWORD *)v4 + 3);
      v12 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v15 = v6;
      v26 = v4[17];
      v27 = v4[4];
      v16 = (int *)*((_QWORD *)v4 + 15);
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (unsigned __int8 *)&word_18003DCCE,
        (const GUID *)(v7 + 8),
        (__int64)v5,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v29,
        &v19,
        &v18,
        (__int64)&v28,
        &v17,
        &v16,
        (__int64)&v27,
        (__int64)&v26,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v10 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)byte_18003DC81,
        (const GUID *)(v10 + 8),
        0,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180018fa0  push    rbp
0x180018fa2  push    rbx
0x180018fa3  push    rdi
0x180018fa4  lea     rbp, [rsp+10h]
0x180018fa9  sub     rsp, 130h
0x180018fb0  mov     rdi, [rcx+110h]
0x180018fb7  mov     rbx, rcx
0x180018fba  mov     eax, [rdi+48h]
0x180018fbd  test    eax, eax
0x180018fbf  jns     loc_180019159
0x180018fc5  add     rdi, 50h ; 'P'
0x180018fc9  cmp     eax, [rdi+8]
0x180018fcc  jnz     loc_180019159
0x180018fd2  test    rdi, rdi
0x180018fd5  jz      loc_180019159
0x180018fdb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018fe0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180018fe5  mov     r9, rax
0x180018fe8  mov     ecx, [rax]
0x180018fea  cmp     ecx, 5
0x180018fed  jbe     loc_1800191BD
0x180018ff3  mov     rax, [rdi+70h]
0x180018ff7  lea     rdx, word_18003DCCE
0x180018ffe  mov     rcx, [rdi+30h]
0x180019002  mov     [rbp+var_60], rax
0x180019006  mov     eax, [rdi+68h]
0x180019009  mov     r8, [rbx+110h]
0x180019010  mov     dword ptr [rbp+arg_10], eax
0x180019013  add     r8, 8
0x180019017  mov     rax, [rdi+60h]
0x18001901b  mov     [rbp+var_58], rax
0x18001901f  mov     rax, [rdi+58h]
0x180019023  mov     [rbp+var_50], rax
0x180019027  mov     eax, [rdi+50h]
0x18001902a  mov     [rbp+arg_18], eax
0x18001902d  mov     rax, [rdi+48h]
0x180019031  mov     [rbp+var_48], rax
0x180019035  mov     eax, [rdi+20h]
0x180019038  mov     [rbp+var_80], eax
0x18001903b  mov     rax, [rdi+18h]
0x18001903f  mov     [rbp+var_40], rax
0x180019043  mov     eax, [rdi]
0x180019045  mov     [rbp+var_7C], eax
0x180019048  mov     rax, [rdi+80h]
0x18001904f  mov     [rbp+var_38], rax
0x180019053  mov     eax, [rdi+40h]
0x180019056  mov     [rbp+var_78], eax
0x180019059  mov     rax, [rdi+38h]
0x18001905d  mov     [rbp+var_30], rax
0x180019061  mov     eax, [rdi+8]
0x180019064  mov     [rbp+var_74], eax
0x180019067  lea     rax, [rbp+var_70]
0x18001906b  mov     [rsp+140h+var_90], rax
0x180019073  lea     rax, [rbp+arg_0]
0x180019077  mov     [rsp+140h+var_98], rax
0x18001907f  lea     rax, [rbp+arg_8]
0x180019083  mov     [rsp+140h+var_A0], rax
0x18001908b  lea     rax, [rbp+var_68]
0x18001908f  mov     [rsp+140h+var_A8], rax
0x180019097  lea     rax, [rbp+var_60]
0x18001909b  mov     [rsp+140h+var_B0], rax
0x1800190a3  lea     rax, [rbp+arg_10]
0x1800190a7  mov     [rsp+140h+var_B8], rax
0x1800190af  lea     rax, [rbp+var_58]
0x1800190b3  mov     [rsp+140h+var_C0], rax
0x1800190bb  lea     rax, [rbp+var_50]
0x1800190bf  mov     [rsp+140h+var_C8], rax
0x1800190c4  lea     rax, [rbp+arg_18]
0x1800190c8  mov     [rsp+140h+var_D0], rax
0x1800190cd  lea     rax, [rbp+var_48]
0x1800190d1  mov     [rsp+140h+var_D8], rax
0x1800190d6  lea     rax, [rbp+var_80]
0x1800190da  mov     [rsp+140h+var_E0], rax
0x1800190df  lea     rax, [rbp+var_40]
0x1800190e3  mov     [rsp+140h+var_E8], rax
0x1800190e8  lea     rax, [rbp+var_7C]
0x1800190ec  mov     [rsp+140h+var_F0], rax
0x1800190f1  lea     rax, [rbp+var_38]
0x1800190f5  mov     [rsp+140h+var_F8], rax
0x1800190fa  lea     rax, [rbp+var_78]
0x1800190fe  mov     [rsp+140h+var_100], rax
0x180019103  lea     rax, [rbp+var_30]
0x180019107  mov     [rsp+140h+var_108], rax
0x18001910c  lea     rax, [rbp+var_74]
0x180019110  mov     [rbp+var_70], rcx
0x180019114  mov     ecx, [rdi+44h]
0x180019117  mov     [rsp+140h+var_110], rax
0x18001911c  lea     rax, [rbp+var_28]
0x180019120  mov     [rbp+arg_0], ecx
0x180019123  mov     ecx, [rdi+10h]
0x180019126  mov     [rbp+arg_8], ecx
0x180019129  mov     rcx, [rdi+78h]
0x18001912d  mov     [rsp+140h+var_118], rax
0x180019132  lea     rax, [rbp+var_20]
0x180019136  mov     [rbp+var_68], rcx
0x18001913a  mov     rcx, r9
0x18001913d  mov     [rsp+140h+var_120], rax
0x180019142  mov     [rbp+var_28], 1000000h
0x18001914a  mov     [rbp+var_20], 0
0x180019152  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019157  jmp     short loc_1800191BD
0x180019159  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001915e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180019163  mov     rdi, rax
0x180019166  mov     ecx, [rax]
0x180019168  cmp     ecx, 5
0x18001916b  jbe     short loc_1800191BD
0x18001916d  call    cs:__imp_GetCurrentThreadId
0x180019173  mov     r8, [rbx+110h]
0x18001917a  lea     rdx, byte_18003DC81
0x180019181  mov     [rbp+arg_0], eax
0x180019184  xor     r9d, r9d
0x180019187  lea     rax, [rbp+arg_0]
0x18001918b  mov     [rsp+140h+var_110], rax
0x180019190  lea     rax, [rbp+arg_8]
0x180019194  mov     ecx, [r8+48h]
0x180019198  add     r8, 8
0x18001919c  mov     [rsp+140h+var_118], rax
0x1800191a1  lea     rax, [rbp+arg_10]
0x1800191a5  mov     [rbp+arg_8], ecx
0x1800191a8  mov     rcx, rdi
0x1800191ab  mov     [rsp+140h+var_120], rax
0x1800191b0  mov     [rbp+arg_10], 0
0x1800191b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800191bd  mov     rcx, rbx
0x1800191c0  add     rsp, 130h
0x1800191c7  pop     rdi
0x1800191c8  pop     rbx
0x1800191c9  pop     rbp
0x1800191ca  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
