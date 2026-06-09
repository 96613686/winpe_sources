# LogProvider::CounterStoreExport::StopActivity(void)

- ea: `0x14005f540`
- end: `0x14005f765`
- name: `?StopActivity@CounterStoreExport@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::CounterStoreExport *__hidden this)`
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
- `0x14005f540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f702`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreExport::StopActivity(LogProvider::CounterStoreExport *this)
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
        (unsigned __int8 *)byte_14008EEB7,
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
        (unsigned int)&dword_14008EE64,
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
0x14005f540  push    rbp
0x14005f542  push    rbx
0x14005f543  push    rdi
0x14005f544  lea     rbp, [rsp-47h]
0x14005f549  sub     rsp, 100h
0x14005f550  mov     rdi, [rcx+110h]
0x14005f557  mov     rbx, rcx
0x14005f55a  mov     eax, [rdi+48h]
0x14005f55d  test    eax, eax
0x14005f55f  jns     loc_14005F6D8
0x14005f565  add     rdi, 50h ; 'P'
0x14005f569  cmp     eax, [rdi+8]
0x14005f56c  jnz     loc_14005F6D8
0x14005f572  test    rdi, rdi
0x14005f575  jz      loc_14005F6D8
0x14005f57b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005f580  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005f585  mov     r9, rax
0x14005f588  mov     ecx, [rax]
0x14005f58a  cmp     ecx, 4
0x14005f58d  jbe     loc_14005F753
0x14005f593  mov     rdx, 400000000000h
0x14005f59d  mov     rcx, rax
0x14005f5a0  call    _tlgKeywordOn
0x14005f5a5  test    al, al
0x14005f5a7  jz      loc_14005F753
0x14005f5ad  mov     rax, [rdi+70h]
0x14005f5b1  lea     rdx, byte_14008EEB7
0x14005f5b8  mov     rcx, [rdi+78h]
0x14005f5bc  mov     r8, [rbx+110h]
0x14005f5c3  mov     [rbp+57h+var_60], rax
0x14005f5c7  add     r8, 8
0x14005f5cb  mov     eax, [rdi+68h]
0x14005f5ce  mov     [rbp+57h+arg_0], eax
0x14005f5d1  mov     rax, [rdi+60h]
0x14005f5d5  mov     [rbp+57h+var_58], rax
0x14005f5d9  mov     rax, [rdi+58h]
0x14005f5dd  mov     [rbp+57h+var_50], rax
0x14005f5e1  mov     eax, [rdi+50h]
0x14005f5e4  mov     [rbp+57h+arg_8], eax
0x14005f5e7  mov     rax, [rdi+48h]
0x14005f5eb  mov     [rbp+57h+var_48], rax
0x14005f5ef  mov     eax, [rdi+20h]
0x14005f5f2  mov     dword ptr [rbp+57h+arg_10], eax
0x14005f5f5  mov     rax, [rdi+18h]
0x14005f5f9  mov     [rbp+57h+var_40], rax
0x14005f5fd  mov     eax, [rdi]
0x14005f5ff  mov     [rbp+57h+arg_18], eax
0x14005f602  mov     rax, [rdi+80h]
0x14005f609  mov     [rbp+57h+var_38], rax
0x14005f60d  mov     eax, [rdi+40h]
0x14005f610  mov     [rbp+57h+var_70], eax
0x14005f613  mov     rax, [rdi+38h]
0x14005f617  mov     [rbp+57h+var_30], rax
0x14005f61b  mov     eax, [rdi+8]
0x14005f61e  mov     [rbp+57h+var_6C], eax
0x14005f621  mov     eax, 1000000h
0x14005f626  mov     [rbp+57h+var_28], rax
0x14005f62a  mov     [rbp+57h+var_20], rax
0x14005f62e  lea     rax, [rbp+57h+var_68]
0x14005f632  mov     [rsp+110h+var_78], rax
0x14005f63a  lea     rax, [rbp+57h+var_60]
0x14005f63e  mov     [rsp+110h+var_80], rax
0x14005f646  lea     rax, [rbp+57h+arg_0]
0x14005f64a  mov     [rsp+110h+var_88], rax
0x14005f652  lea     rax, [rbp+57h+var_58]
0x14005f656  mov     [rsp+110h+var_90], rax
0x14005f65e  lea     rax, [rbp+57h+var_50]
0x14005f662  mov     [rsp+110h+var_98], rax
0x14005f667  lea     rax, [rbp+57h+arg_8]
0x14005f66b  mov     [rsp+110h+var_A0], rax
0x14005f670  lea     rax, [rbp+57h+var_48]
0x14005f674  mov     [rsp+110h+var_A8], rax
0x14005f679  lea     rax, [rbp+57h+arg_10]
0x14005f67d  mov     [rsp+110h+var_B0], rax
0x14005f682  lea     rax, [rbp+57h+var_40]
0x14005f686  mov     [rsp+110h+var_B8], rax
0x14005f68b  lea     rax, [rbp+57h+arg_18]
0x14005f68f  mov     [rsp+110h+var_C0], rax
0x14005f694  lea     rax, [rbp+57h+var_38]
0x14005f698  mov     [rsp+110h+var_C8], rax
0x14005f69d  lea     rax, [rbp+57h+var_70]
0x14005f6a1  mov     [rsp+110h+var_D0], rax
0x14005f6a6  lea     rax, [rbp+57h+var_30]
0x14005f6aa  mov     [rsp+110h+var_D8], rax
0x14005f6af  lea     rax, [rbp+57h+var_6C]
0x14005f6b3  mov     [rsp+110h+var_E0], rax
0x14005f6b8  lea     rax, [rbp+57h+var_28]
0x14005f6bc  mov     [rsp+110h+var_E8], rax
0x14005f6c1  lea     rax, [rbp+57h+var_20]
0x14005f6c5  mov     [rbp+57h+var_68], rcx
0x14005f6c9  mov     rcx, r9
0x14005f6cc  mov     [rsp+110h+var_F0], rax
0x14005f6d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14005f6d6  jmp     short loc_14005F753
0x14005f6d8  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005f6dd  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005f6e2  mov     rdi, rax
0x14005f6e5  mov     ecx, [rax]
0x14005f6e7  cmp     ecx, 4
0x14005f6ea  jbe     short loc_14005F753
0x14005f6ec  mov     rdx, 400000000000h
0x14005f6f6  mov     rcx, rax
0x14005f6f9  call    _tlgKeywordOn
0x14005f6fe  test    al, al
0x14005f700  jz      short loc_14005F753
0x14005f702  call    cs:__imp_GetCurrentThreadId
0x14005f708  mov     r8, [rbx+110h]
0x14005f70f  lea     rdx, dword_14008EE64
0x14005f716  mov     [rbp+57h+arg_0], eax
0x14005f719  xor     r9d, r9d
0x14005f71c  mov     rcx, rdi
0x14005f71f  mov     eax, [r8+48h]
0x14005f723  add     r8, 8
0x14005f727  mov     [rbp+57h+arg_8], eax
0x14005f72a  mov     eax, 1000000h
0x14005f72f  mov     [rbp+57h+arg_10], rax
0x14005f733  lea     rax, [rbp+57h+arg_0]
0x14005f737  mov     [rsp+110h+var_E0], rax
0x14005f73c  lea     rax, [rbp+57h+arg_8]
0x14005f740  mov     [rsp+110h+var_E8], rax
0x14005f745  lea     rax, [rbp+57h+arg_10]
0x14005f749  mov     [rsp+110h+var_F0], rax
0x14005f74e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005f753  mov     rcx, rbx
0x14005f756  add     rsp, 100h
0x14005f75d  pop     rdi
0x14005f75e  pop     rbx
0x14005f75f  pop     rbp
0x14005f760  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
