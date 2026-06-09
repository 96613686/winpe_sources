# LogProvider::CounterStoreQueryCounter::StopActivity(void)

- ea: `0x14005fe00`
- end: `0x140060025`
- name: `?StopActivity@CounterStoreQueryCounter@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::CounterStoreQueryCounter *__hidden this)`
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
- `0x14005fe00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ffc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ffc2`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreQueryCounter::StopActivity(LogProvider::CounterStoreQueryCounter *this)
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
        (unsigned __int8 *)byte_14008E5AB,
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
        (unsigned int)word_14008E552,
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
0x14005fe00  push    rbp
0x14005fe02  push    rbx
0x14005fe03  push    rdi
0x14005fe04  lea     rbp, [rsp-47h]
0x14005fe09  sub     rsp, 100h
0x14005fe10  mov     rdi, [rcx+110h]
0x14005fe17  mov     rbx, rcx
0x14005fe1a  mov     eax, [rdi+48h]
0x14005fe1d  test    eax, eax
0x14005fe1f  jns     loc_14005FF98
0x14005fe25  add     rdi, 50h ; 'P'
0x14005fe29  cmp     eax, [rdi+8]
0x14005fe2c  jnz     loc_14005FF98
0x14005fe32  test    rdi, rdi
0x14005fe35  jz      loc_14005FF98
0x14005fe3b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005fe40  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005fe45  mov     r9, rax
0x14005fe48  mov     ecx, [rax]
0x14005fe4a  cmp     ecx, 4
0x14005fe4d  jbe     loc_140060013
0x14005fe53  mov     rdx, 400000000000h
0x14005fe5d  mov     rcx, rax
0x14005fe60  call    _tlgKeywordOn
0x14005fe65  test    al, al
0x14005fe67  jz      loc_140060013
0x14005fe6d  mov     rax, [rdi+70h]
0x14005fe71  lea     rdx, byte_14008E5AB
0x14005fe78  mov     rcx, [rdi+78h]
0x14005fe7c  mov     r8, [rbx+110h]
0x14005fe83  mov     [rbp+57h+var_60], rax
0x14005fe87  add     r8, 8
0x14005fe8b  mov     eax, [rdi+68h]
0x14005fe8e  mov     [rbp+57h+arg_0], eax
0x14005fe91  mov     rax, [rdi+60h]
0x14005fe95  mov     [rbp+57h+var_58], rax
0x14005fe99  mov     rax, [rdi+58h]
0x14005fe9d  mov     [rbp+57h+var_50], rax
0x14005fea1  mov     eax, [rdi+50h]
0x14005fea4  mov     [rbp+57h+arg_8], eax
0x14005fea7  mov     rax, [rdi+48h]
0x14005feab  mov     [rbp+57h+var_48], rax
0x14005feaf  mov     eax, [rdi+20h]
0x14005feb2  mov     dword ptr [rbp+57h+arg_10], eax
0x14005feb5  mov     rax, [rdi+18h]
0x14005feb9  mov     [rbp+57h+var_40], rax
0x14005febd  mov     eax, [rdi]
0x14005febf  mov     [rbp+57h+arg_18], eax
0x14005fec2  mov     rax, [rdi+80h]
0x14005fec9  mov     [rbp+57h+var_38], rax
0x14005fecd  mov     eax, [rdi+40h]
0x14005fed0  mov     [rbp+57h+var_70], eax
0x14005fed3  mov     rax, [rdi+38h]
0x14005fed7  mov     [rbp+57h+var_30], rax
0x14005fedb  mov     eax, [rdi+8]
0x14005fede  mov     [rbp+57h+var_6C], eax
0x14005fee1  mov     eax, 1000000h
0x14005fee6  mov     [rbp+57h+var_28], rax
0x14005feea  mov     [rbp+57h+var_20], rax
0x14005feee  lea     rax, [rbp+57h+var_68]
0x14005fef2  mov     [rsp+110h+var_78], rax
0x14005fefa  lea     rax, [rbp+57h+var_60]
0x14005fefe  mov     [rsp+110h+var_80], rax
0x14005ff06  lea     rax, [rbp+57h+arg_0]
0x14005ff0a  mov     [rsp+110h+var_88], rax
0x14005ff12  lea     rax, [rbp+57h+var_58]
0x14005ff16  mov     [rsp+110h+var_90], rax
0x14005ff1e  lea     rax, [rbp+57h+var_50]
0x14005ff22  mov     [rsp+110h+var_98], rax
0x14005ff27  lea     rax, [rbp+57h+arg_8]
0x14005ff2b  mov     [rsp+110h+var_A0], rax
0x14005ff30  lea     rax, [rbp+57h+var_48]
0x14005ff34  mov     [rsp+110h+var_A8], rax
0x14005ff39  lea     rax, [rbp+57h+arg_10]
0x14005ff3d  mov     [rsp+110h+var_B0], rax
0x14005ff42  lea     rax, [rbp+57h+var_40]
0x14005ff46  mov     [rsp+110h+var_B8], rax
0x14005ff4b  lea     rax, [rbp+57h+arg_18]
0x14005ff4f  mov     [rsp+110h+var_C0], rax
0x14005ff54  lea     rax, [rbp+57h+var_38]
0x14005ff58  mov     [rsp+110h+var_C8], rax
0x14005ff5d  lea     rax, [rbp+57h+var_70]
0x14005ff61  mov     [rsp+110h+var_D0], rax
0x14005ff66  lea     rax, [rbp+57h+var_30]
0x14005ff6a  mov     [rsp+110h+var_D8], rax
0x14005ff6f  lea     rax, [rbp+57h+var_6C]
0x14005ff73  mov     [rsp+110h+var_E0], rax
0x14005ff78  lea     rax, [rbp+57h+var_28]
0x14005ff7c  mov     [rsp+110h+var_E8], rax
0x14005ff81  lea     rax, [rbp+57h+var_20]
0x14005ff85  mov     [rbp+57h+var_68], rcx
0x14005ff89  mov     rcx, r9
0x14005ff8c  mov     [rsp+110h+var_F0], rax
0x14005ff91  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14005ff96  jmp     short loc_140060013
0x14005ff98  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005ff9d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005ffa2  mov     rdi, rax
0x14005ffa5  mov     ecx, [rax]
0x14005ffa7  cmp     ecx, 4
0x14005ffaa  jbe     short loc_140060013
0x14005ffac  mov     rdx, 400000000000h
0x14005ffb6  mov     rcx, rax
0x14005ffb9  call    _tlgKeywordOn
0x14005ffbe  test    al, al
0x14005ffc0  jz      short loc_140060013
0x14005ffc2  call    cs:__imp_GetCurrentThreadId
0x14005ffc8  mov     r8, [rbx+110h]
0x14005ffcf  lea     rdx, word_14008E552
0x14005ffd6  mov     [rbp+57h+arg_0], eax
0x14005ffd9  xor     r9d, r9d
0x14005ffdc  mov     rcx, rdi
0x14005ffdf  mov     eax, [r8+48h]
0x14005ffe3  add     r8, 8
0x14005ffe7  mov     [rbp+57h+arg_8], eax
0x14005ffea  mov     eax, 1000000h
0x14005ffef  mov     [rbp+57h+arg_10], rax
0x14005fff3  lea     rax, [rbp+57h+arg_0]
0x14005fff7  mov     [rsp+110h+var_E0], rax
0x14005fffc  lea     rax, [rbp+57h+arg_8]
0x140060000  mov     [rsp+110h+var_E8], rax
0x140060005  lea     rax, [rbp+57h+arg_10]
0x140060009  mov     [rsp+110h+var_F0], rax
0x14006000e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140060013  mov     rcx, rbx
0x140060016  add     rsp, 100h
0x14006001d  pop     rdi
0x14006001e  pop     rbx
0x14006001f  pop     rbp
0x140060020  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
