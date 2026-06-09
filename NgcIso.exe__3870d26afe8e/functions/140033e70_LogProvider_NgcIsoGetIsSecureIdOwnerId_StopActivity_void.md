# LogProvider::NgcIsoGetIsSecureIdOwnerId::StopActivity(void)

- ea: `0x140033e70`
- end: `0x140034095`
- name: `?StopActivity@NgcIsoGetIsSecureIdOwnerId@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::NgcIsoGetIsSecureIdOwnerId *__hidden this)`
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
- `0x140033e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034032`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034032`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetIsSecureIdOwnerId::StopActivity(LogProvider::NgcIsoGetIsSecureIdOwnerId *this)
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
        (unsigned __int8 *)&dword_140087DAC,
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
        (unsigned int)&word_140087EDE,
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
0x140033e70  push    rbp
0x140033e72  push    rbx
0x140033e73  push    rdi
0x140033e74  lea     rbp, [rsp-47h]
0x140033e79  sub     rsp, 100h
0x140033e80  mov     rdi, [rcx+110h]
0x140033e87  mov     rbx, rcx
0x140033e8a  mov     eax, [rdi+48h]
0x140033e8d  test    eax, eax
0x140033e8f  jns     loc_140034008
0x140033e95  add     rdi, 50h ; 'P'
0x140033e99  cmp     eax, [rdi+8]
0x140033e9c  jnz     loc_140034008
0x140033ea2  test    rdi, rdi
0x140033ea5  jz      loc_140034008
0x140033eab  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140033eb0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033eb5  mov     r9, rax
0x140033eb8  mov     ecx, [rax]
0x140033eba  cmp     ecx, 4
0x140033ebd  jbe     loc_140034083
0x140033ec3  mov     rdx, 400000000000h
0x140033ecd  mov     rcx, rax
0x140033ed0  call    _tlgKeywordOn
0x140033ed5  test    al, al
0x140033ed7  jz      loc_140034083
0x140033edd  mov     rax, [rdi+70h]
0x140033ee1  lea     rdx, dword_140087DAC
0x140033ee8  mov     rcx, [rdi+78h]
0x140033eec  mov     r8, [rbx+110h]
0x140033ef3  mov     [rbp+57h+var_60], rax
0x140033ef7  add     r8, 8
0x140033efb  mov     eax, [rdi+68h]
0x140033efe  mov     [rbp+57h+arg_0], eax
0x140033f01  mov     rax, [rdi+60h]
0x140033f05  mov     [rbp+57h+var_58], rax
0x140033f09  mov     rax, [rdi+58h]
0x140033f0d  mov     [rbp+57h+var_50], rax
0x140033f11  mov     eax, [rdi+50h]
0x140033f14  mov     [rbp+57h+arg_8], eax
0x140033f17  mov     rax, [rdi+48h]
0x140033f1b  mov     [rbp+57h+var_48], rax
0x140033f1f  mov     eax, [rdi+20h]
0x140033f22  mov     dword ptr [rbp+57h+arg_10], eax
0x140033f25  mov     rax, [rdi+18h]
0x140033f29  mov     [rbp+57h+var_40], rax
0x140033f2d  mov     eax, [rdi]
0x140033f2f  mov     [rbp+57h+arg_18], eax
0x140033f32  mov     rax, [rdi+80h]
0x140033f39  mov     [rbp+57h+var_38], rax
0x140033f3d  mov     eax, [rdi+40h]
0x140033f40  mov     [rbp+57h+var_70], eax
0x140033f43  mov     rax, [rdi+38h]
0x140033f47  mov     [rbp+57h+var_30], rax
0x140033f4b  mov     eax, [rdi+8]
0x140033f4e  mov     [rbp+57h+var_6C], eax
0x140033f51  mov     eax, 1000000h
0x140033f56  mov     [rbp+57h+var_28], rax
0x140033f5a  mov     [rbp+57h+var_20], rax
0x140033f5e  lea     rax, [rbp+57h+var_68]
0x140033f62  mov     [rsp+110h+var_78], rax
0x140033f6a  lea     rax, [rbp+57h+var_60]
0x140033f6e  mov     [rsp+110h+var_80], rax
0x140033f76  lea     rax, [rbp+57h+arg_0]
0x140033f7a  mov     [rsp+110h+var_88], rax
0x140033f82  lea     rax, [rbp+57h+var_58]
0x140033f86  mov     [rsp+110h+var_90], rax
0x140033f8e  lea     rax, [rbp+57h+var_50]
0x140033f92  mov     [rsp+110h+var_98], rax
0x140033f97  lea     rax, [rbp+57h+arg_8]
0x140033f9b  mov     [rsp+110h+var_A0], rax
0x140033fa0  lea     rax, [rbp+57h+var_48]
0x140033fa4  mov     [rsp+110h+var_A8], rax
0x140033fa9  lea     rax, [rbp+57h+arg_10]
0x140033fad  mov     [rsp+110h+var_B0], rax
0x140033fb2  lea     rax, [rbp+57h+var_40]
0x140033fb6  mov     [rsp+110h+var_B8], rax
0x140033fbb  lea     rax, [rbp+57h+arg_18]
0x140033fbf  mov     [rsp+110h+var_C0], rax
0x140033fc4  lea     rax, [rbp+57h+var_38]
0x140033fc8  mov     [rsp+110h+var_C8], rax
0x140033fcd  lea     rax, [rbp+57h+var_70]
0x140033fd1  mov     [rsp+110h+var_D0], rax
0x140033fd6  lea     rax, [rbp+57h+var_30]
0x140033fda  mov     [rsp+110h+var_D8], rax
0x140033fdf  lea     rax, [rbp+57h+var_6C]
0x140033fe3  mov     [rsp+110h+var_E0], rax
0x140033fe8  lea     rax, [rbp+57h+var_28]
0x140033fec  mov     [rsp+110h+var_E8], rax
0x140033ff1  lea     rax, [rbp+57h+var_20]
0x140033ff5  mov     [rbp+57h+var_68], rcx
0x140033ff9  mov     rcx, r9
0x140033ffc  mov     [rsp+110h+var_F0], rax
0x140034001  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140034006  jmp     short loc_140034083
0x140034008  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14003400d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140034012  mov     rdi, rax
0x140034015  mov     ecx, [rax]
0x140034017  cmp     ecx, 4
0x14003401a  jbe     short loc_140034083
0x14003401c  mov     rdx, 400000000000h
0x140034026  mov     rcx, rax
0x140034029  call    _tlgKeywordOn
0x14003402e  test    al, al
0x140034030  jz      short loc_140034083
0x140034032  call    cs:__imp_GetCurrentThreadId
0x140034038  mov     r8, [rbx+110h]
0x14003403f  lea     rdx, word_140087EDE
0x140034046  mov     [rbp+57h+arg_0], eax
0x140034049  xor     r9d, r9d
0x14003404c  mov     rcx, rdi
0x14003404f  mov     eax, [r8+48h]
0x140034053  add     r8, 8
0x140034057  mov     [rbp+57h+arg_8], eax
0x14003405a  mov     eax, 1000000h
0x14003405f  mov     [rbp+57h+arg_10], rax
0x140034063  lea     rax, [rbp+57h+arg_0]
0x140034067  mov     [rsp+110h+var_E0], rax
0x14003406c  lea     rax, [rbp+57h+arg_8]
0x140034070  mov     [rsp+110h+var_E8], rax
0x140034075  lea     rax, [rbp+57h+arg_10]
0x140034079  mov     [rsp+110h+var_F0], rax
0x14003407e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140034083  mov     rcx, rbx
0x140034086  add     rsp, 100h
0x14003408d  pop     rdi
0x14003408e  pop     rbx
0x14003408f  pop     rbp
0x140034090  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
