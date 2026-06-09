# LogProvider::NgcIsoGetContainerTrustLevel::Stop(ulong)

- ea: `0x14002ed30`
- end: `0x14002ef85`
- name: `?Stop@NgcIsoGetContainerTrustLevel@LogProvider@@QEAAXK@Z`
- size: `597`
- prototype: `void __fastcall(LogProvider::NgcIsoGetContainerTrustLevel *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140026c60`

## callees

- `0x140001c98`
- `0x1400033f4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002ed30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002ef15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002ef15`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetContainerTrustLevel::Stop(
        LogProvider::NgcIsoGetContainerTrustLevel *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33[3]; // [rsp+128h] [rbp-18h] BYREF
  int v34; // [rsp+150h] [rbp+10h] BYREF
  DWORD v35; // [rsp+160h] [rbp+20h] BYREF
  int v36; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LogProvider::Provider();
    if ( *(_DWORD *)v9 > 4u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v26 = *((_QWORD *)v6 + 14);
      v17 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v18 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v19 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v20 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v21 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v22 = v6[2];
      v24 = v10;
      v35 = v6[17];
      v36 = v6[4];
      v25 = *((_QWORD *)v6 + 15);
      v34 = a2;
      v33[0] = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)byte_14008B77B,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v23,
        (__int64)v33,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&word_14008B8DE,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x14002ed30  mov     [rsp-8+arg_8], rbx
0x14002ed35  push    rbp
0x14002ed36  push    rsi
0x14002ed37  push    rdi
0x14002ed38  lea     rbp, [rsp+10h]
0x14002ed3d  sub     rsp, 130h
0x14002ed44  mov     rdi, [rcx+110h]
0x14002ed4b  mov     esi, edx
0x14002ed4d  mov     rbx, rcx
0x14002ed50  mov     eax, [rdi+48h]
0x14002ed53  test    eax, eax
0x14002ed55  jns     loc_14002EEFE
0x14002ed5b  add     rdi, 50h ; 'P'
0x14002ed5f  cmp     eax, [rdi+8]
0x14002ed62  jnz     loc_14002EEFE
0x14002ed68  test    rdi, rdi
0x14002ed6b  jz      loc_14002EEFE
0x14002ed71  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002ed76  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002ed7b  mov     r9, rax
0x14002ed7e  mov     ecx, [rax]
0x14002ed80  cmp     ecx, 4
0x14002ed83  jbe     loc_14002EF6B
0x14002ed89  mov     rax, [rdi+70h]
0x14002ed8d  lea     rdx, byte_14008B77B
0x14002ed94  mov     rcx, [rdi+30h]
0x14002ed98  mov     [rbp+var_50], rax
0x14002ed9c  mov     eax, [rdi+68h]
0x14002ed9f  mov     [rbp+var_80], eax
0x14002eda2  mov     rax, [rdi+60h]
0x14002eda6  mov     r8, [rbx+110h]
0x14002edad  mov     [rbp+var_48], rax
0x14002edb1  add     r8, 8
0x14002edb5  mov     rax, [rdi+58h]
0x14002edb9  mov     [rbp+var_40], rax
0x14002edbd  mov     eax, [rdi+50h]
0x14002edc0  mov     [rbp+var_7C], eax
0x14002edc3  mov     rax, [rdi+48h]
0x14002edc7  mov     [rbp+var_38], rax
0x14002edcb  mov     eax, [rdi+20h]
0x14002edce  mov     [rbp+var_78], eax
0x14002edd1  mov     rax, [rdi+18h]
0x14002edd5  mov     [rbp+var_30], rax
0x14002edd9  mov     eax, [rdi]
0x14002eddb  mov     [rbp+var_74], eax
0x14002edde  mov     rax, [rdi+80h]
0x14002ede5  mov     [rbp+var_28], rax
0x14002ede9  mov     eax, [rdi+40h]
0x14002edec  mov     [rbp+var_70], eax
0x14002edef  mov     rax, [rdi+38h]
0x14002edf3  mov     [rbp+var_20], rax
0x14002edf7  mov     eax, [rdi+8]
0x14002edfa  mov     [rbp+var_6C], eax
0x14002edfd  lea     rax, [rbp+arg_0]
0x14002ee01  mov     [rsp+140h+var_88], rax
0x14002ee09  lea     rax, [rbp+var_60]
0x14002ee0d  mov     [rsp+140h+var_90], rax
0x14002ee15  lea     rax, [rbp+arg_10]
0x14002ee19  mov     [rsp+140h+var_98], rax
0x14002ee21  lea     rax, [rbp+arg_18]
0x14002ee25  mov     [rsp+140h+var_A0], rax
0x14002ee2d  lea     rax, [rbp+var_58]
0x14002ee31  mov     [rsp+140h+var_A8], rax
0x14002ee39  lea     rax, [rbp+var_50]
0x14002ee3d  mov     [rsp+140h+var_B0], rax
0x14002ee45  lea     rax, [rbp+var_80]
0x14002ee49  mov     [rsp+140h+var_B8], rax
0x14002ee51  lea     rax, [rbp+var_48]
0x14002ee55  mov     [rsp+140h+var_C0], rax
0x14002ee5d  lea     rax, [rbp+var_40]
0x14002ee61  mov     [rsp+140h+var_C8], rax
0x14002ee66  lea     rax, [rbp+var_7C]
0x14002ee6a  mov     [rsp+140h+var_D0], rax
0x14002ee6f  lea     rax, [rbp+var_38]
0x14002ee73  mov     [rsp+140h+var_D8], rax
0x14002ee78  lea     rax, [rbp+var_78]
0x14002ee7c  mov     [rsp+140h+var_E0], rax
0x14002ee81  lea     rax, [rbp+var_30]
0x14002ee85  mov     [rsp+140h+var_E8], rax
0x14002ee8a  lea     rax, [rbp+var_74]
0x14002ee8e  mov     [rsp+140h+var_F0], rax
0x14002ee93  lea     rax, [rbp+var_28]
0x14002ee97  mov     [rsp+140h+var_F8], rax
0x14002ee9c  lea     rax, [rbp+var_70]
0x14002eea0  mov     [rsp+140h+var_100], rax
0x14002eea5  lea     rax, [rbp+var_20]
0x14002eea9  mov     [rsp+140h+var_108], rax
0x14002eeae  lea     rax, [rbp+var_6C]
0x14002eeb2  mov     [rbp+var_60], rcx
0x14002eeb6  mov     ecx, [rdi+44h]
0x14002eeb9  mov     [rsp+140h+var_110], rax
0x14002eebe  lea     rax, [rbp+var_18]
0x14002eec2  mov     [rbp+arg_10], ecx
0x14002eec5  mov     ecx, [rdi+10h]
0x14002eec8  mov     [rbp+arg_18], ecx
0x14002eecb  mov     rcx, [rdi+78h]
0x14002eecf  mov     [rsp+140h+var_118], rax
0x14002eed4  lea     rax, [rbp+var_68]
0x14002eed8  mov     [rbp+var_58], rcx
0x14002eedc  mov     rcx, r9
0x14002eedf  mov     [rsp+140h+var_120], rax
0x14002eee4  mov     [rbp+arg_0], esi
0x14002eee7  mov     [rbp+var_18], 1000000h
0x14002eeef  mov     [rbp+var_68], 0
0x14002eef7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14002eefc  jmp     short loc_14002EF6B
0x14002eefe  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002ef03  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002ef08  mov     rdi, rax
0x14002ef0b  mov     ecx, [rax]
0x14002ef0d  cmp     ecx, 4
0x14002ef10  jbe     short loc_14002EF6B
0x14002ef12  mov     [rbp+arg_0], esi
0x14002ef15  call    cs:__imp_GetCurrentThreadId
0x14002ef1b  mov     r8, [rbx+110h]
0x14002ef22  lea     rdx, word_14008B8DE
0x14002ef29  mov     [rbp+arg_10], eax
0x14002ef2c  lea     rax, [rbp+arg_0]
0x14002ef30  mov     [rsp+140h+var_108], rax
0x14002ef35  lea     rax, [rbp+arg_10]
0x14002ef39  mov     [rsp+140h+var_110], rax
0x14002ef3e  lea     rax, [rbp+arg_18]
0x14002ef42  mov     ecx, [r8+48h]
0x14002ef46  add     r8, 8
0x14002ef4a  mov     [rsp+140h+var_118], rax
0x14002ef4f  lea     rax, [rbp+var_68]
0x14002ef53  mov     [rbp+arg_18], ecx
0x14002ef56  mov     rcx, rdi
0x14002ef59  mov     [rsp+140h+var_120], rax
0x14002ef5e  mov     [rbp+var_68], 0
0x14002ef66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002ef6b  mov     rcx, rbx
0x14002ef6e  mov     rbx, [rsp+140h+arg_8]
0x14002ef76  add     rsp, 130h
0x14002ef7d  pop     rdi
0x14002ef7e  pop     rsi
0x14002ef7f  pop     rbp
0x14002ef80  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
