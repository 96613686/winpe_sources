# LogProvider::CounterStoreIncrementCounter::Stop(unsigned __int64)

- ea: `0x14005ec30`
- end: `0x14005ee81`
- name: `?Stop@CounterStoreIncrementCounter@LogProvider@@QEAAX_K@Z`
- size: `593`
- prototype: `void __fastcall(LogProvider::CounterStoreIncrementCounter *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005e060`

## callees

- `0x140001fc0`
- `0x14000330c`
- `0x1400036d4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14005ec30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ee10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ee10`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreIncrementCounter::Stop(
        LogProvider::CounterStoreIncrementCounter *this,
        __int64 a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  int v19; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+100h] [rbp-30h] BYREF
  __int64 v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  __int64 v33; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LogProvider::Provider();
    v10 = v7;
    if ( *(_DWORD *)v7 > 4u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v22 = *((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 14);
      v31 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v32 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      LODWORD(v33) = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v30[0] = 0x1000000;
      v20 = 0x1000000;
      v21 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (_DWORD)v10,
        (unsigned int)&byte_14008E797,
        v11 + 8,
        (_DWORD)v10,
        (__int64)&v20,
        (__int64)v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v33,
        (__int64)&v26,
        (__int64)&v32,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v33 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v15 + 72);
      v20 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v13,
        (unsigned int)byte_14008E6DB,
        v15 + 8,
        v16,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v33);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x14005ec30  mov     [rsp-8+arg_8], rbx
0x14005ec35  push    rbp
0x14005ec36  push    rsi
0x14005ec37  push    rdi
0x14005ec38  lea     rbp, [rsp+10h]
0x14005ec3d  sub     rsp, 120h
0x14005ec44  mov     rdi, [rcx+110h]
0x14005ec4b  mov     rsi, rdx
0x14005ec4e  mov     rbx, rcx
0x14005ec51  mov     eax, [rdi+48h]
0x14005ec54  test    eax, eax
0x14005ec56  jns     loc_14005EDE2
0x14005ec5c  add     rdi, 50h ; 'P'
0x14005ec60  cmp     eax, [rdi+8]
0x14005ec63  jnz     loc_14005EDE2
0x14005ec69  test    rdi, rdi
0x14005ec6c  jz      loc_14005EDE2
0x14005ec72  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005ec77  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005ec7c  mov     r9, rax
0x14005ec7f  mov     ecx, [rax]
0x14005ec81  cmp     ecx, 4
0x14005ec84  jbe     loc_14005EE67
0x14005ec8a  mov     rdx, 400000000000h
0x14005ec94  mov     rcx, rax
0x14005ec97  call    _tlgKeywordOn
0x14005ec9c  test    al, al
0x14005ec9e  jz      loc_14005EE67
0x14005eca4  mov     rax, [rdi+78h]
0x14005eca8  lea     rdx, byte_14008E797
0x14005ecaf  mov     [rbp+var_60], rax
0x14005ecb3  mov     rcx, r9
0x14005ecb6  mov     rax, [rdi+70h]
0x14005ecba  mov     r8, [rbx+110h]
0x14005ecc1  mov     [rbp+var_58], rax
0x14005ecc5  add     r8, 8
0x14005ecc9  mov     eax, [rdi+68h]
0x14005eccc  mov     [rbp+arg_0], eax
0x14005eccf  mov     rax, [rdi+60h]
0x14005ecd3  mov     [rbp+var_50], rax
0x14005ecd7  mov     rax, [rdi+58h]
0x14005ecdb  mov     [rbp+var_48], rax
0x14005ecdf  mov     eax, [rdi+50h]
0x14005ece2  mov     [rbp+arg_10], eax
0x14005ece5  mov     rax, [rdi+48h]
0x14005ece9  mov     [rbp+var_40], rax
0x14005eced  mov     eax, [rdi+20h]
0x14005ecf0  mov     dword ptr [rbp+arg_18], eax
0x14005ecf3  mov     rax, [rdi+18h]
0x14005ecf7  mov     [rbp+var_38], rax
0x14005ecfb  mov     eax, [rdi]
0x14005ecfd  mov     [rbp+var_80], eax
0x14005ed00  mov     rax, [rdi+80h]
0x14005ed07  mov     [rbp+var_30], rax
0x14005ed0b  mov     eax, [rdi+40h]
0x14005ed0e  mov     [rbp+var_7C], eax
0x14005ed11  mov     rax, [rdi+38h]
0x14005ed15  mov     [rbp+var_28], rax
0x14005ed19  mov     eax, [rdi+8]
0x14005ed1c  mov     [rbp+var_78], eax
0x14005ed1f  mov     eax, 1000000h
0x14005ed24  mov     [rbp+var_20], rax
0x14005ed28  mov     [rbp+var_70], rax
0x14005ed2c  lea     rax, [rbp+var_68]
0x14005ed30  mov     [rsp+130h+var_90], rax
0x14005ed38  lea     rax, [rbp+var_60]
0x14005ed3c  mov     [rsp+130h+var_98], rax
0x14005ed44  lea     rax, [rbp+var_58]
0x14005ed48  mov     [rsp+130h+var_A0], rax
0x14005ed50  lea     rax, [rbp+arg_0]
0x14005ed54  mov     [rsp+130h+var_A8], rax
0x14005ed5c  lea     rax, [rbp+var_50]
0x14005ed60  mov     [rsp+130h+var_B0], rax
0x14005ed68  lea     rax, [rbp+var_48]
0x14005ed6c  mov     [rsp+130h+var_B8], rax
0x14005ed71  lea     rax, [rbp+arg_10]
0x14005ed75  mov     [rsp+130h+var_C0], rax
0x14005ed7a  lea     rax, [rbp+var_40]
0x14005ed7e  mov     [rsp+130h+var_C8], rax
0x14005ed83  lea     rax, [rbp+arg_18]
0x14005ed87  mov     [rsp+130h+var_D0], rax
0x14005ed8c  lea     rax, [rbp+var_38]
0x14005ed90  mov     [rsp+130h+var_D8], rax
0x14005ed95  lea     rax, [rbp+var_80]
0x14005ed99  mov     [rsp+130h+var_E0], rax
0x14005ed9e  lea     rax, [rbp+var_30]
0x14005eda2  mov     [rsp+130h+var_E8], rax
0x14005eda7  lea     rax, [rbp+var_7C]
0x14005edab  mov     [rsp+130h+var_F0], rax
0x14005edb0  lea     rax, [rbp+var_28]
0x14005edb4  mov     [rsp+130h+var_F8], rax
0x14005edb9  lea     rax, [rbp+var_78]
0x14005edbd  mov     [rsp+130h+var_100], rax
0x14005edc2  lea     rax, [rbp+var_20]
0x14005edc6  mov     [rsp+130h+var_108], rax
0x14005edcb  lea     rax, [rbp+var_70]
0x14005edcf  mov     [rsp+130h+var_110], rax
0x14005edd4  mov     [rbp+var_68], rsi
0x14005edd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14005eddd  jmp     loc_14005EE67
0x14005ede2  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005ede7  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005edec  mov     rdi, rax
0x14005edef  mov     ecx, [rax]
0x14005edf1  cmp     ecx, 4
0x14005edf4  jbe     short loc_14005EE67
0x14005edf6  mov     rdx, 400000000000h
0x14005ee00  mov     rcx, rax
0x14005ee03  call    _tlgKeywordOn
0x14005ee08  test    al, al
0x14005ee0a  jz      short loc_14005EE67
0x14005ee0c  mov     [rbp+arg_18], rsi
0x14005ee10  call    cs:__imp_GetCurrentThreadId
0x14005ee16  mov     r8, [rbx+110h]
0x14005ee1d  lea     rdx, byte_14008E6DB
0x14005ee24  mov     [rbp+arg_0], eax
0x14005ee27  mov     rcx, rdi
0x14005ee2a  mov     eax, [r8+48h]
0x14005ee2e  add     r8, 8
0x14005ee32  mov     [rbp+arg_10], eax
0x14005ee35  mov     eax, 1000000h
0x14005ee3a  mov     [rbp+var_70], rax
0x14005ee3e  lea     rax, [rbp+arg_18]
0x14005ee42  mov     [rsp+130h+var_F8], rax
0x14005ee47  lea     rax, [rbp+arg_0]
0x14005ee4b  mov     [rsp+130h+var_100], rax
0x14005ee50  lea     rax, [rbp+arg_10]
0x14005ee54  mov     [rsp+130h+var_108], rax
0x14005ee59  lea     rax, [rbp+var_70]
0x14005ee5d  mov     [rsp+130h+var_110], rax
0x14005ee62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14005ee67  mov     rcx, rbx
0x14005ee6a  mov     rbx, [rsp+130h+arg_8]
0x14005ee72  add     rsp, 120h
0x14005ee79  pop     rdi
0x14005ee7a  pop     rsi
0x14005ee7b  pop     rbp
0x14005ee7c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
