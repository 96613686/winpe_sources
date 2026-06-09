# WnsCPLog::ConnectActivity::StopActivity(void)

- ea: `0x18001c050`
- end: `0x18001c275`
- name: `?StopActivity@ConnectActivity@WnsCPLog@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(WnsCPLog::ConnectActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001e64`
- `0x18000d830`
- `0x18000f2f0`
- `0x180015080`
- `0x180017c30`
- `0x180018430`
- `0x18001c050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c212`

## pseudocode

```c
void __fastcall WnsCPLog::ConnectActivity::StopActivity(WnsCPLog::ConnectActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v17; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v19; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = *((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = *((_QWORD *)v4 + 12);
      v20 = *((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = *((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = *((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&word_18004125E,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = WnsCPTracelogger::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned __int8 *)&word_18004120E,
        (const GUID *)(v14 + 8),
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18001c050  push    rbp
0x18001c052  push    rbx
0x18001c053  push    rdi
0x18001c054  lea     rbp, [rsp-47h]
0x18001c059  sub     rsp, 100h
0x18001c060  mov     rdi, [rcx+110h]
0x18001c067  mov     rbx, rcx
0x18001c06a  mov     eax, [rdi+48h]
0x18001c06d  test    eax, eax
0x18001c06f  jns     loc_18001C1E8
0x18001c075  add     rdi, 50h ; 'P'
0x18001c079  cmp     eax, [rdi+8]
0x18001c07c  jnz     loc_18001C1E8
0x18001c082  test    rdi, rdi
0x18001c085  jz      loc_18001C1E8
0x18001c08b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001c090  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001c095  mov     r9, rax
0x18001c098  mov     ecx, [rax]
0x18001c09a  cmp     ecx, 5
0x18001c09d  jbe     loc_18001C263
0x18001c0a3  mov     rdx, 400000000000h
0x18001c0ad  mov     rcx, rax
0x18001c0b0  call    _tlgKeywordOn
0x18001c0b5  test    al, al
0x18001c0b7  jz      loc_18001C263
0x18001c0bd  mov     rax, [rdi+70h]
0x18001c0c1  lea     rdx, word_18004125E
0x18001c0c8  mov     rcx, [rdi+78h]
0x18001c0cc  mov     r8, [rbx+110h]
0x18001c0d3  mov     [rbp+57h+var_60], rax
0x18001c0d7  add     r8, 8
0x18001c0db  mov     eax, [rdi+68h]
0x18001c0de  mov     [rbp+57h+arg_0], eax
0x18001c0e1  mov     rax, [rdi+60h]
0x18001c0e5  mov     [rbp+57h+var_58], rax
0x18001c0e9  mov     rax, [rdi+58h]
0x18001c0ed  mov     [rbp+57h+var_50], rax
0x18001c0f1  mov     eax, [rdi+50h]
0x18001c0f4  mov     [rbp+57h+arg_8], eax
0x18001c0f7  mov     rax, [rdi+48h]
0x18001c0fb  mov     [rbp+57h+var_48], rax
0x18001c0ff  mov     eax, [rdi+20h]
0x18001c102  mov     dword ptr [rbp+57h+arg_10], eax
0x18001c105  mov     rax, [rdi+18h]
0x18001c109  mov     [rbp+57h+var_40], rax
0x18001c10d  mov     eax, [rdi]
0x18001c10f  mov     [rbp+57h+arg_18], eax
0x18001c112  mov     rax, [rdi+80h]
0x18001c119  mov     [rbp+57h+var_38], rax
0x18001c11d  mov     eax, [rdi+40h]
0x18001c120  mov     [rbp+57h+var_70], eax
0x18001c123  mov     rax, [rdi+38h]
0x18001c127  mov     [rbp+57h+var_30], rax
0x18001c12b  mov     eax, [rdi+8]
0x18001c12e  mov     [rbp+57h+var_6C], eax
0x18001c131  mov     eax, 1000000h
0x18001c136  mov     [rbp+57h+var_28], rax
0x18001c13a  mov     [rbp+57h+var_20], rax
0x18001c13e  lea     rax, [rbp+57h+var_68]
0x18001c142  mov     [rsp+110h+var_78], rax
0x18001c14a  lea     rax, [rbp+57h+var_60]
0x18001c14e  mov     [rsp+110h+var_80], rax
0x18001c156  lea     rax, [rbp+57h+arg_0]
0x18001c15a  mov     [rsp+110h+var_88], rax
0x18001c162  lea     rax, [rbp+57h+var_58]
0x18001c166  mov     [rsp+110h+var_90], rax
0x18001c16e  lea     rax, [rbp+57h+var_50]
0x18001c172  mov     [rsp+110h+var_98], rax
0x18001c177  lea     rax, [rbp+57h+arg_8]
0x18001c17b  mov     [rsp+110h+var_A0], rax
0x18001c180  lea     rax, [rbp+57h+var_48]
0x18001c184  mov     [rsp+110h+var_A8], rax
0x18001c189  lea     rax, [rbp+57h+arg_10]
0x18001c18d  mov     [rsp+110h+var_B0], rax
0x18001c192  lea     rax, [rbp+57h+var_40]
0x18001c196  mov     [rsp+110h+var_B8], rax
0x18001c19b  lea     rax, [rbp+57h+arg_18]
0x18001c19f  mov     [rsp+110h+var_C0], rax
0x18001c1a4  lea     rax, [rbp+57h+var_38]
0x18001c1a8  mov     [rsp+110h+var_C8], rax
0x18001c1ad  lea     rax, [rbp+57h+var_70]
0x18001c1b1  mov     [rsp+110h+var_D0], rax
0x18001c1b6  lea     rax, [rbp+57h+var_30]
0x18001c1ba  mov     [rsp+110h+var_D8], rax
0x18001c1bf  lea     rax, [rbp+57h+var_6C]
0x18001c1c3  mov     [rsp+110h+var_E0], rax
0x18001c1c8  lea     rax, [rbp+57h+var_28]
0x18001c1cc  mov     [rsp+110h+var_E8], rax
0x18001c1d1  lea     rax, [rbp+57h+var_20]
0x18001c1d5  mov     [rbp+57h+var_68], rcx
0x18001c1d9  mov     rcx, r9
0x18001c1dc  mov     [rsp+110h+var_F0], rax
0x18001c1e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001c1e6  jmp     short loc_18001C263
0x18001c1e8  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001c1ed  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001c1f2  mov     rdi, rax
0x18001c1f5  mov     ecx, [rax]
0x18001c1f7  cmp     ecx, 5
0x18001c1fa  jbe     short loc_18001C263
0x18001c1fc  mov     rdx, 400000000000h
0x18001c206  mov     rcx, rax
0x18001c209  call    _tlgKeywordOn
0x18001c20e  test    al, al
0x18001c210  jz      short loc_18001C263
0x18001c212  call    cs:__imp_GetCurrentThreadId
0x18001c218  mov     r8, [rbx+110h]
0x18001c21f  lea     rdx, word_18004120E
0x18001c226  mov     [rbp+57h+arg_0], eax
0x18001c229  xor     r9d, r9d
0x18001c22c  mov     rcx, rdi
0x18001c22f  mov     eax, [r8+48h]
0x18001c233  add     r8, 8
0x18001c237  mov     [rbp+57h+arg_8], eax
0x18001c23a  mov     eax, 1000000h
0x18001c23f  mov     [rbp+57h+arg_10], rax
0x18001c243  lea     rax, [rbp+57h+arg_0]
0x18001c247  mov     [rsp+110h+var_E0], rax
0x18001c24c  lea     rax, [rbp+57h+arg_8]
0x18001c250  mov     [rsp+110h+var_E8], rax
0x18001c255  lea     rax, [rbp+57h+arg_10]
0x18001c259  mov     [rsp+110h+var_F0], rax
0x18001c25e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c263  mov     rcx, rbx
0x18001c266  add     rsp, 100h
0x18001c26d  pop     rdi
0x18001c26e  pop     rbx
0x18001c26f  pop     rbp
0x18001c270  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
