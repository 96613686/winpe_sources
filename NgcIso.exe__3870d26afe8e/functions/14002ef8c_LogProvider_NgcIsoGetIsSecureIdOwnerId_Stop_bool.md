# LogProvider::NgcIsoGetIsSecureIdOwnerId::Stop(bool)

- ea: `0x14002ef8c`
- end: `0x14002f1dd`
- name: `?Stop@NgcIsoGetIsSecureIdOwnerId@LogProvider@@QEAAX_N@Z`
- size: `593`
- prototype: `void __fastcall(LogProvider::NgcIsoGetIsSecureIdOwnerId *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140027100`

## callees

- `0x140002284`
- `0x14000330c`
- `0x140003484`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002ef8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f16c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f16c`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetIsSecureIdOwnerId::Stop(LogProvider::NgcIsoGetIsSecureIdOwnerId *this, char a2)
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
  int v20; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30[3]; // [rsp+108h] [rbp-28h] BYREF
  char v31; // [rsp+130h] [rbp+0h] BYREF
  DWORD v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF

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
      v32 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v33 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      v17 = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v18 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v19 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      v20 = v6[2];
      v30[0] = 0x1000000;
      v21 = 0x1000000;
      v31 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        (_DWORD)v10,
        (unsigned int)byte_140087C0B,
        v11 + 8,
        (_DWORD)v10,
        (__int64)&v21,
        (__int64)v30,
        (__int64)&v20,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v33,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v32,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v31);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v32 = CurrentThreadId;
      v33 = *(_DWORD *)(v15 + 72);
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v13,
        (unsigned int)&byte_140087D47,
        v15 + 8,
        v16,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
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
0x14002ef8c  mov     [rsp-8+arg_8], rbx
0x14002ef91  push    rbp
0x14002ef92  push    rsi
0x14002ef93  push    rdi
0x14002ef94  lea     rbp, [rsp+20h]
0x14002ef99  sub     rsp, 110h
0x14002efa0  mov     rdi, [rcx+110h]
0x14002efa7  mov     sil, dl
0x14002efaa  mov     rbx, rcx
0x14002efad  mov     eax, [rdi+48h]
0x14002efb0  test    eax, eax
0x14002efb2  jns     loc_14002F13E
0x14002efb8  add     rdi, 50h ; 'P'
0x14002efbc  cmp     eax, [rdi+8]
0x14002efbf  jnz     loc_14002F13E
0x14002efc5  test    rdi, rdi
0x14002efc8  jz      loc_14002F13E
0x14002efce  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002efd3  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002efd8  mov     r9, rax
0x14002efdb  mov     ecx, [rax]
0x14002efdd  cmp     ecx, 4
0x14002efe0  jbe     loc_14002F1C3
0x14002efe6  mov     rdx, 400000000000h
0x14002eff0  mov     rcx, rax
0x14002eff3  call    _tlgKeywordOn
0x14002eff8  test    al, al
0x14002effa  jz      loc_14002F1C3
0x14002f000  mov     rax, [rdi+78h]
0x14002f004  lea     rdx, byte_140087C0B
0x14002f00b  mov     [rbp-10h+var_58], rax
0x14002f00f  mov     rcx, r9
0x14002f012  mov     rax, [rdi+70h]
0x14002f016  mov     r8, [rbx+110h]
0x14002f01d  mov     [rbp-10h+var_50], rax
0x14002f021  add     r8, 8
0x14002f025  mov     eax, [rdi+68h]
0x14002f028  mov     [rbp-10h+arg_10], eax
0x14002f02b  mov     rax, [rdi+60h]
0x14002f02f  mov     [rbp-10h+var_48], rax
0x14002f033  mov     rax, [rdi+58h]
0x14002f037  mov     [rbp-10h+var_40], rax
0x14002f03b  mov     eax, [rdi+50h]
0x14002f03e  mov     [rbp-10h+arg_18], eax
0x14002f041  mov     rax, [rdi+48h]
0x14002f045  mov     [rbp-10h+var_38], rax
0x14002f049  mov     eax, [rdi+20h]
0x14002f04c  mov     [rbp-10h+var_70], eax
0x14002f04f  mov     rax, [rdi+18h]
0x14002f053  mov     [rbp-10h+var_30], rax
0x14002f057  mov     eax, [rdi]
0x14002f059  mov     [rbp-10h+var_6C], eax
0x14002f05c  mov     rax, [rdi+80h]
0x14002f063  mov     [rbp-10h+var_28], rax
0x14002f067  mov     eax, [rdi+40h]
0x14002f06a  mov     [rbp-10h+var_68], eax
0x14002f06d  mov     rax, [rdi+38h]
0x14002f071  mov     [rbp-10h+var_20], rax
0x14002f075  mov     eax, [rdi+8]
0x14002f078  mov     [rbp-10h+var_64], eax
0x14002f07b  mov     eax, 1000000h
0x14002f080  mov     [rbp-10h+var_18], rax
0x14002f084  mov     [rbp-10h+var_60], rax
0x14002f088  lea     rax, [rbp-10h+arg_0]
0x14002f08c  mov     [rsp+120h+var_80], rax
0x14002f094  lea     rax, [rbp-10h+var_58]
0x14002f098  mov     [rsp+120h+var_88], rax
0x14002f0a0  lea     rax, [rbp-10h+var_50]
0x14002f0a4  mov     [rsp+120h+var_90], rax
0x14002f0ac  lea     rax, [rbp-10h+arg_10]
0x14002f0b0  mov     [rsp+120h+var_98], rax
0x14002f0b8  lea     rax, [rbp-10h+var_48]
0x14002f0bc  mov     [rsp+120h+var_A0], rax
0x14002f0c4  lea     rax, [rbp-10h+var_40]
0x14002f0c8  mov     [rsp+120h+var_A8], rax
0x14002f0cd  lea     rax, [rbp-10h+arg_18]
0x14002f0d1  mov     [rsp+120h+var_B0], rax
0x14002f0d6  lea     rax, [rbp-10h+var_38]
0x14002f0da  mov     [rsp+120h+var_B8], rax
0x14002f0df  lea     rax, [rbp-10h+var_70]
0x14002f0e3  mov     [rsp+120h+var_C0], rax
0x14002f0e8  lea     rax, [rbp-10h+var_30]
0x14002f0ec  mov     [rsp+120h+var_C8], rax
0x14002f0f1  lea     rax, [rbp-10h+var_6C]
0x14002f0f5  mov     [rsp+120h+var_D0], rax
0x14002f0fa  lea     rax, [rbp-10h+var_28]
0x14002f0fe  mov     [rsp+120h+var_D8], rax
0x14002f103  lea     rax, [rbp-10h+var_68]
0x14002f107  mov     [rsp+120h+var_E0], rax
0x14002f10c  lea     rax, [rbp-10h+var_20]
0x14002f110  mov     [rsp+120h+var_E8], rax
0x14002f115  lea     rax, [rbp-10h+var_64]
0x14002f119  mov     [rsp+120h+var_F0], rax
0x14002f11e  lea     rax, [rbp-10h+var_18]
0x14002f122  mov     [rsp+120h+var_F8], rax
0x14002f127  lea     rax, [rbp-10h+var_60]
0x14002f12b  mov     [rsp+120h+var_100], rax
0x14002f130  mov     [rbp-10h+arg_0], sil
0x14002f134  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x14002f139  jmp     loc_14002F1C3
0x14002f13e  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f143  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f148  mov     rdi, rax
0x14002f14b  mov     ecx, [rax]
0x14002f14d  cmp     ecx, 4
0x14002f150  jbe     short loc_14002F1C3
0x14002f152  mov     rdx, 400000000000h
0x14002f15c  mov     rcx, rax
0x14002f15f  call    _tlgKeywordOn
0x14002f164  test    al, al
0x14002f166  jz      short loc_14002F1C3
0x14002f168  mov     [rbp-10h+arg_0], sil
0x14002f16c  call    cs:__imp_GetCurrentThreadId
0x14002f172  mov     r8, [rbx+110h]
0x14002f179  lea     rdx, byte_140087D47
0x14002f180  mov     [rbp-10h+arg_10], eax
0x14002f183  mov     rcx, rdi
0x14002f186  mov     eax, [r8+48h]
0x14002f18a  add     r8, 8
0x14002f18e  mov     [rbp-10h+arg_18], eax
0x14002f191  mov     eax, 1000000h
0x14002f196  mov     [rbp-10h+var_60], rax
0x14002f19a  lea     rax, [rbp-10h+arg_0]
0x14002f19e  mov     [rsp+120h+var_E8], rax
0x14002f1a3  lea     rax, [rbp-10h+arg_10]
0x14002f1a7  mov     [rsp+120h+var_F0], rax
0x14002f1ac  lea     rax, [rbp-10h+arg_18]
0x14002f1b0  mov     [rsp+120h+var_F8], rax
0x14002f1b5  lea     rax, [rbp-10h+var_60]
0x14002f1b9  mov     [rsp+120h+var_100], rax
0x14002f1be  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002f1c3  mov     rcx, rbx
0x14002f1c6  mov     rbx, [rsp+120h+arg_8]
0x14002f1ce  add     rsp, 110h
0x14002f1d5  pop     rdi
0x14002f1d6  pop     rsi
0x14002f1d7  pop     rbp
0x14002f1d8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
