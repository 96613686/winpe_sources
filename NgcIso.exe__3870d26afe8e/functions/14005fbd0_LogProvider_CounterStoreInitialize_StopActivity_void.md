# LogProvider::CounterStoreInitialize::StopActivity(void)

- ea: `0x14005fbd0`
- end: `0x14005fdf5`
- name: `?StopActivity@CounterStoreInitialize@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::CounterStoreInitialize *__hidden this)`
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
- `0x14005fbd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fd92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fd92`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreInitialize::StopActivity(LogProvider::CounterStoreInitialize *this)
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
        (unsigned __int8 *)byte_14008F3ED,
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
        (unsigned int)&word_14008F396,
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
0x14005fbd0  push    rbp
0x14005fbd2  push    rbx
0x14005fbd3  push    rdi
0x14005fbd4  lea     rbp, [rsp-47h]
0x14005fbd9  sub     rsp, 100h
0x14005fbe0  mov     rdi, [rcx+110h]
0x14005fbe7  mov     rbx, rcx
0x14005fbea  mov     eax, [rdi+48h]
0x14005fbed  test    eax, eax
0x14005fbef  jns     loc_14005FD68
0x14005fbf5  add     rdi, 50h ; 'P'
0x14005fbf9  cmp     eax, [rdi+8]
0x14005fbfc  jnz     loc_14005FD68
0x14005fc02  test    rdi, rdi
0x14005fc05  jz      loc_14005FD68
0x14005fc0b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005fc10  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005fc15  mov     r9, rax
0x14005fc18  mov     ecx, [rax]
0x14005fc1a  cmp     ecx, 4
0x14005fc1d  jbe     loc_14005FDE3
0x14005fc23  mov     rdx, 400000000000h
0x14005fc2d  mov     rcx, rax
0x14005fc30  call    _tlgKeywordOn
0x14005fc35  test    al, al
0x14005fc37  jz      loc_14005FDE3
0x14005fc3d  mov     rax, [rdi+70h]
0x14005fc41  lea     rdx, byte_14008F3ED
0x14005fc48  mov     rcx, [rdi+78h]
0x14005fc4c  mov     r8, [rbx+110h]
0x14005fc53  mov     [rbp+57h+var_60], rax
0x14005fc57  add     r8, 8
0x14005fc5b  mov     eax, [rdi+68h]
0x14005fc5e  mov     [rbp+57h+arg_0], eax
0x14005fc61  mov     rax, [rdi+60h]
0x14005fc65  mov     [rbp+57h+var_58], rax
0x14005fc69  mov     rax, [rdi+58h]
0x14005fc6d  mov     [rbp+57h+var_50], rax
0x14005fc71  mov     eax, [rdi+50h]
0x14005fc74  mov     [rbp+57h+arg_8], eax
0x14005fc77  mov     rax, [rdi+48h]
0x14005fc7b  mov     [rbp+57h+var_48], rax
0x14005fc7f  mov     eax, [rdi+20h]
0x14005fc82  mov     dword ptr [rbp+57h+arg_10], eax
0x14005fc85  mov     rax, [rdi+18h]
0x14005fc89  mov     [rbp+57h+var_40], rax
0x14005fc8d  mov     eax, [rdi]
0x14005fc8f  mov     [rbp+57h+arg_18], eax
0x14005fc92  mov     rax, [rdi+80h]
0x14005fc99  mov     [rbp+57h+var_38], rax
0x14005fc9d  mov     eax, [rdi+40h]
0x14005fca0  mov     [rbp+57h+var_70], eax
0x14005fca3  mov     rax, [rdi+38h]
0x14005fca7  mov     [rbp+57h+var_30], rax
0x14005fcab  mov     eax, [rdi+8]
0x14005fcae  mov     [rbp+57h+var_6C], eax
0x14005fcb1  mov     eax, 1000000h
0x14005fcb6  mov     [rbp+57h+var_28], rax
0x14005fcba  mov     [rbp+57h+var_20], rax
0x14005fcbe  lea     rax, [rbp+57h+var_68]
0x14005fcc2  mov     [rsp+110h+var_78], rax
0x14005fcca  lea     rax, [rbp+57h+var_60]
0x14005fcce  mov     [rsp+110h+var_80], rax
0x14005fcd6  lea     rax, [rbp+57h+arg_0]
0x14005fcda  mov     [rsp+110h+var_88], rax
0x14005fce2  lea     rax, [rbp+57h+var_58]
0x14005fce6  mov     [rsp+110h+var_90], rax
0x14005fcee  lea     rax, [rbp+57h+var_50]
0x14005fcf2  mov     [rsp+110h+var_98], rax
0x14005fcf7  lea     rax, [rbp+57h+arg_8]
0x14005fcfb  mov     [rsp+110h+var_A0], rax
0x14005fd00  lea     rax, [rbp+57h+var_48]
0x14005fd04  mov     [rsp+110h+var_A8], rax
0x14005fd09  lea     rax, [rbp+57h+arg_10]
0x14005fd0d  mov     [rsp+110h+var_B0], rax
0x14005fd12  lea     rax, [rbp+57h+var_40]
0x14005fd16  mov     [rsp+110h+var_B8], rax
0x14005fd1b  lea     rax, [rbp+57h+arg_18]
0x14005fd1f  mov     [rsp+110h+var_C0], rax
0x14005fd24  lea     rax, [rbp+57h+var_38]
0x14005fd28  mov     [rsp+110h+var_C8], rax
0x14005fd2d  lea     rax, [rbp+57h+var_70]
0x14005fd31  mov     [rsp+110h+var_D0], rax
0x14005fd36  lea     rax, [rbp+57h+var_30]
0x14005fd3a  mov     [rsp+110h+var_D8], rax
0x14005fd3f  lea     rax, [rbp+57h+var_6C]
0x14005fd43  mov     [rsp+110h+var_E0], rax
0x14005fd48  lea     rax, [rbp+57h+var_28]
0x14005fd4c  mov     [rsp+110h+var_E8], rax
0x14005fd51  lea     rax, [rbp+57h+var_20]
0x14005fd55  mov     [rbp+57h+var_68], rcx
0x14005fd59  mov     rcx, r9
0x14005fd5c  mov     [rsp+110h+var_F0], rax
0x14005fd61  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14005fd66  jmp     short loc_14005FDE3
0x14005fd68  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005fd6d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005fd72  mov     rdi, rax
0x14005fd75  mov     ecx, [rax]
0x14005fd77  cmp     ecx, 4
0x14005fd7a  jbe     short loc_14005FDE3
0x14005fd7c  mov     rdx, 400000000000h
0x14005fd86  mov     rcx, rax
0x14005fd89  call    _tlgKeywordOn
0x14005fd8e  test    al, al
0x14005fd90  jz      short loc_14005FDE3
0x14005fd92  call    cs:__imp_GetCurrentThreadId
0x14005fd98  mov     r8, [rbx+110h]
0x14005fd9f  lea     rdx, word_14008F396
0x14005fda6  mov     [rbp+57h+arg_0], eax
0x14005fda9  xor     r9d, r9d
0x14005fdac  mov     rcx, rdi
0x14005fdaf  mov     eax, [r8+48h]
0x14005fdb3  add     r8, 8
0x14005fdb7  mov     [rbp+57h+arg_8], eax
0x14005fdba  mov     eax, 1000000h
0x14005fdbf  mov     [rbp+57h+arg_10], rax
0x14005fdc3  lea     rax, [rbp+57h+arg_0]
0x14005fdc7  mov     [rsp+110h+var_E0], rax
0x14005fdcc  lea     rax, [rbp+57h+arg_8]
0x14005fdd0  mov     [rsp+110h+var_E8], rax
0x14005fdd5  lea     rax, [rbp+57h+arg_10]
0x14005fdd9  mov     [rsp+110h+var_F0], rax
0x14005fdde  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005fde3  mov     rcx, rbx
0x14005fde6  add     rsp, 100h
0x14005fded  pop     rdi
0x14005fdee  pop     rbx
0x14005fdef  pop     rbp
0x14005fdf0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
