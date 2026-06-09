# LogProvider::CounterStoreImport::StopActivity(void)

- ea: `0x14005f770`
- end: `0x14005f995`
- name: `?StopActivity@CounterStoreImport@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::CounterStoreImport *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14005f770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f932`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreImport::StopActivity(LogProvider::CounterStoreImport *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
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
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LogProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (unsigned __int8 *)byte_14008F213,
        (const GUID *)(v10 + 8),
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
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&word_14008F176,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x14005f770  push    rbp
0x14005f772  push    rbx
0x14005f773  push    rdi
0x14005f774  lea     rbp, [rsp-47h]
0x14005f779  sub     rsp, 100h
0x14005f780  mov     rdi, [rcx+110h]
0x14005f787  mov     rbx, rcx
0x14005f78a  mov     eax, [rdi+48h]
0x14005f78d  test    eax, eax
0x14005f78f  jns     loc_14005F908
0x14005f795  add     rdi, 50h ; 'P'
0x14005f799  cmp     eax, [rdi+8]
0x14005f79c  jnz     loc_14005F908
0x14005f7a2  test    rdi, rdi
0x14005f7a5  jz      loc_14005F908
0x14005f7ab  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005f7b0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005f7b5  mov     r9, rax
0x14005f7b8  mov     ecx, [rax]
0x14005f7ba  cmp     ecx, 4
0x14005f7bd  jbe     loc_14005F983
0x14005f7c3  mov     rdx, 400000000000h
0x14005f7cd  mov     rcx, rax
0x14005f7d0  call    _tlgKeywordOn
0x14005f7d5  test    al, al
0x14005f7d7  jz      loc_14005F983
0x14005f7dd  mov     rax, [rdi+70h]
0x14005f7e1  lea     rdx, byte_14008F213
0x14005f7e8  mov     rcx, [rdi+78h]
0x14005f7ec  mov     r8, [rbx+110h]
0x14005f7f3  mov     [rbp+57h+var_60], rax
0x14005f7f7  add     r8, 8
0x14005f7fb  mov     eax, [rdi+68h]
0x14005f7fe  mov     [rbp+57h+arg_0], eax
0x14005f801  mov     rax, [rdi+60h]
0x14005f805  mov     [rbp+57h+var_58], rax
0x14005f809  mov     rax, [rdi+58h]
0x14005f80d  mov     [rbp+57h+var_50], rax
0x14005f811  mov     eax, [rdi+50h]
0x14005f814  mov     [rbp+57h+arg_8], eax
0x14005f817  mov     rax, [rdi+48h]
0x14005f81b  mov     [rbp+57h+var_48], rax
0x14005f81f  mov     eax, [rdi+20h]
0x14005f822  mov     dword ptr [rbp+57h+arg_10], eax
0x14005f825  mov     rax, [rdi+18h]
0x14005f829  mov     [rbp+57h+var_40], rax
0x14005f82d  mov     eax, [rdi]
0x14005f82f  mov     [rbp+57h+arg_18], eax
0x14005f832  mov     rax, [rdi+80h]
0x14005f839  mov     [rbp+57h+var_38], rax
0x14005f83d  mov     eax, [rdi+40h]
0x14005f840  mov     [rbp+57h+var_70], eax
0x14005f843  mov     rax, [rdi+38h]
0x14005f847  mov     [rbp+57h+var_30], rax
0x14005f84b  mov     eax, [rdi+8]
0x14005f84e  mov     [rbp+57h+var_6C], eax
0x14005f851  mov     eax, 1000000h
0x14005f856  mov     [rbp+57h+var_28], rax
0x14005f85a  mov     [rbp+57h+var_20], rax
0x14005f85e  lea     rax, [rbp+57h+var_68]
0x14005f862  mov     [rsp+110h+var_78], rax
0x14005f86a  lea     rax, [rbp+57h+var_60]
0x14005f86e  mov     [rsp+110h+var_80], rax
0x14005f876  lea     rax, [rbp+57h+arg_0]
0x14005f87a  mov     [rsp+110h+var_88], rax
0x14005f882  lea     rax, [rbp+57h+var_58]
0x14005f886  mov     [rsp+110h+var_90], rax
0x14005f88e  lea     rax, [rbp+57h+var_50]
0x14005f892  mov     [rsp+110h+var_98], rax
0x14005f897  lea     rax, [rbp+57h+arg_8]
0x14005f89b  mov     [rsp+110h+var_A0], rax
0x14005f8a0  lea     rax, [rbp+57h+var_48]
0x14005f8a4  mov     [rsp+110h+var_A8], rax
0x14005f8a9  lea     rax, [rbp+57h+arg_10]
0x14005f8ad  mov     [rsp+110h+var_B0], rax
0x14005f8b2  lea     rax, [rbp+57h+var_40]
0x14005f8b6  mov     [rsp+110h+var_B8], rax
0x14005f8bb  lea     rax, [rbp+57h+arg_18]
0x14005f8bf  mov     [rsp+110h+var_C0], rax
0x14005f8c4  lea     rax, [rbp+57h+var_38]
0x14005f8c8  mov     [rsp+110h+var_C8], rax
0x14005f8cd  lea     rax, [rbp+57h+var_70]
0x14005f8d1  mov     [rsp+110h+var_D0], rax
0x14005f8d6  lea     rax, [rbp+57h+var_30]
0x14005f8da  mov     [rsp+110h+var_D8], rax
0x14005f8df  lea     rax, [rbp+57h+var_6C]
0x14005f8e3  mov     [rsp+110h+var_E0], rax
0x14005f8e8  lea     rax, [rbp+57h+var_28]
0x14005f8ec  mov     [rsp+110h+var_E8], rax
0x14005f8f1  lea     rax, [rbp+57h+var_20]
0x14005f8f5  mov     [rbp+57h+var_68], rcx
0x14005f8f9  mov     rcx, r9
0x14005f8fc  mov     [rsp+110h+var_F0], rax
0x14005f901  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14005f906  jmp     short loc_14005F983
0x14005f908  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005f90d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005f912  mov     rdi, rax
0x14005f915  mov     ecx, [rax]
0x14005f917  cmp     ecx, 4
0x14005f91a  jbe     short loc_14005F983
0x14005f91c  mov     rdx, 400000000000h
0x14005f926  mov     rcx, rax
0x14005f929  call    _tlgKeywordOn
0x14005f92e  test    al, al
0x14005f930  jz      short loc_14005F983
0x14005f932  call    cs:__imp_GetCurrentThreadId
0x14005f938  mov     r8, [rbx+110h]
0x14005f93f  lea     rdx, word_14008F176
0x14005f946  mov     [rbp+57h+arg_0], eax
0x14005f949  xor     r9d, r9d
0x14005f94c  mov     rcx, rdi
0x14005f94f  mov     eax, [r8+48h]
0x14005f953  add     r8, 8
0x14005f957  mov     [rbp+57h+arg_8], eax
0x14005f95a  mov     eax, 1000000h
0x14005f95f  mov     [rbp+57h+arg_10], rax
0x14005f963  lea     rax, [rbp+57h+arg_0]
0x14005f967  mov     [rsp+110h+var_E0], rax
0x14005f96c  lea     rax, [rbp+57h+arg_8]
0x14005f970  mov     [rsp+110h+var_E8], rax
0x14005f975  lea     rax, [rbp+57h+arg_10]
0x14005f979  mov     [rsp+110h+var_F0], rax
0x14005f97e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005f983  mov     rcx, rbx
0x14005f986  add     rsp, 100h
0x14005f98d  pop     rdi
0x14005f98e  pop     rbx
0x14005f98f  pop     rbp
0x14005f990  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
