# LogProvider::NgcIsoImportData::Stop(ulong)

- ea: `0x14002f1e4`
- end: `0x14002f439`
- name: `?Stop@NgcIsoImportData@LogProvider@@QEAAXK@Z`
- size: `597`
- prototype: `void __fastcall(LogProvider::NgcIsoImportData *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400280f0`

## callees

- `0x140001c98`
- `0x1400033f4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002f1e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f3c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f3c9`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoImportData::Stop(LogProvider::NgcIsoImportData *this, int a2)
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
    if ( *(_DWORD *)v9 > 5u )
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
        (unsigned int)word_14008AF22,
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
    if ( *(_DWORD *)v12 > 5u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_14008B081,
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
0x14002f1e4  mov     [rsp-8+arg_8], rbx
0x14002f1e9  push    rbp
0x14002f1ea  push    rsi
0x14002f1eb  push    rdi
0x14002f1ec  lea     rbp, [rsp+10h]
0x14002f1f1  sub     rsp, 130h
0x14002f1f8  mov     rdi, [rcx+110h]
0x14002f1ff  mov     esi, edx
0x14002f201  mov     rbx, rcx
0x14002f204  mov     eax, [rdi+48h]
0x14002f207  test    eax, eax
0x14002f209  jns     loc_14002F3B2
0x14002f20f  add     rdi, 50h ; 'P'
0x14002f213  cmp     eax, [rdi+8]
0x14002f216  jnz     loc_14002F3B2
0x14002f21c  test    rdi, rdi
0x14002f21f  jz      loc_14002F3B2
0x14002f225  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f22a  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f22f  mov     r9, rax
0x14002f232  mov     ecx, [rax]
0x14002f234  cmp     ecx, 5
0x14002f237  jbe     loc_14002F41F
0x14002f23d  mov     rax, [rdi+70h]
0x14002f241  lea     rdx, word_14008AF22
0x14002f248  mov     rcx, [rdi+30h]
0x14002f24c  mov     [rbp+var_50], rax
0x14002f250  mov     eax, [rdi+68h]
0x14002f253  mov     [rbp+var_80], eax
0x14002f256  mov     rax, [rdi+60h]
0x14002f25a  mov     r8, [rbx+110h]
0x14002f261  mov     [rbp+var_48], rax
0x14002f265  add     r8, 8
0x14002f269  mov     rax, [rdi+58h]
0x14002f26d  mov     [rbp+var_40], rax
0x14002f271  mov     eax, [rdi+50h]
0x14002f274  mov     [rbp+var_7C], eax
0x14002f277  mov     rax, [rdi+48h]
0x14002f27b  mov     [rbp+var_38], rax
0x14002f27f  mov     eax, [rdi+20h]
0x14002f282  mov     [rbp+var_78], eax
0x14002f285  mov     rax, [rdi+18h]
0x14002f289  mov     [rbp+var_30], rax
0x14002f28d  mov     eax, [rdi]
0x14002f28f  mov     [rbp+var_74], eax
0x14002f292  mov     rax, [rdi+80h]
0x14002f299  mov     [rbp+var_28], rax
0x14002f29d  mov     eax, [rdi+40h]
0x14002f2a0  mov     [rbp+var_70], eax
0x14002f2a3  mov     rax, [rdi+38h]
0x14002f2a7  mov     [rbp+var_20], rax
0x14002f2ab  mov     eax, [rdi+8]
0x14002f2ae  mov     [rbp+var_6C], eax
0x14002f2b1  lea     rax, [rbp+arg_0]
0x14002f2b5  mov     [rsp+140h+var_88], rax
0x14002f2bd  lea     rax, [rbp+var_60]
0x14002f2c1  mov     [rsp+140h+var_90], rax
0x14002f2c9  lea     rax, [rbp+arg_10]
0x14002f2cd  mov     [rsp+140h+var_98], rax
0x14002f2d5  lea     rax, [rbp+arg_18]
0x14002f2d9  mov     [rsp+140h+var_A0], rax
0x14002f2e1  lea     rax, [rbp+var_58]
0x14002f2e5  mov     [rsp+140h+var_A8], rax
0x14002f2ed  lea     rax, [rbp+var_50]
0x14002f2f1  mov     [rsp+140h+var_B0], rax
0x14002f2f9  lea     rax, [rbp+var_80]
0x14002f2fd  mov     [rsp+140h+var_B8], rax
0x14002f305  lea     rax, [rbp+var_48]
0x14002f309  mov     [rsp+140h+var_C0], rax
0x14002f311  lea     rax, [rbp+var_40]
0x14002f315  mov     [rsp+140h+var_C8], rax
0x14002f31a  lea     rax, [rbp+var_7C]
0x14002f31e  mov     [rsp+140h+var_D0], rax
0x14002f323  lea     rax, [rbp+var_38]
0x14002f327  mov     [rsp+140h+var_D8], rax
0x14002f32c  lea     rax, [rbp+var_78]
0x14002f330  mov     [rsp+140h+var_E0], rax
0x14002f335  lea     rax, [rbp+var_30]
0x14002f339  mov     [rsp+140h+var_E8], rax
0x14002f33e  lea     rax, [rbp+var_74]
0x14002f342  mov     [rsp+140h+var_F0], rax
0x14002f347  lea     rax, [rbp+var_28]
0x14002f34b  mov     [rsp+140h+var_F8], rax
0x14002f350  lea     rax, [rbp+var_70]
0x14002f354  mov     [rsp+140h+var_100], rax
0x14002f359  lea     rax, [rbp+var_20]
0x14002f35d  mov     [rsp+140h+var_108], rax
0x14002f362  lea     rax, [rbp+var_6C]
0x14002f366  mov     [rbp+var_60], rcx
0x14002f36a  mov     ecx, [rdi+44h]
0x14002f36d  mov     [rsp+140h+var_110], rax
0x14002f372  lea     rax, [rbp+var_18]
0x14002f376  mov     [rbp+arg_10], ecx
0x14002f379  mov     ecx, [rdi+10h]
0x14002f37c  mov     [rbp+arg_18], ecx
0x14002f37f  mov     rcx, [rdi+78h]
0x14002f383  mov     [rsp+140h+var_118], rax
0x14002f388  lea     rax, [rbp+var_68]
0x14002f38c  mov     [rbp+var_58], rcx
0x14002f390  mov     rcx, r9
0x14002f393  mov     [rsp+140h+var_120], rax
0x14002f398  mov     [rbp+arg_0], esi
0x14002f39b  mov     [rbp+var_18], 1000000h
0x14002f3a3  mov     [rbp+var_68], 0
0x14002f3ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14002f3b0  jmp     short loc_14002F41F
0x14002f3b2  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f3b7  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f3bc  mov     rdi, rax
0x14002f3bf  mov     ecx, [rax]
0x14002f3c1  cmp     ecx, 5
0x14002f3c4  jbe     short loc_14002F41F
0x14002f3c6  mov     [rbp+arg_0], esi
0x14002f3c9  call    cs:__imp_GetCurrentThreadId
0x14002f3cf  mov     r8, [rbx+110h]
0x14002f3d6  lea     rdx, byte_14008B081
0x14002f3dd  mov     [rbp+arg_10], eax
0x14002f3e0  lea     rax, [rbp+arg_0]
0x14002f3e4  mov     [rsp+140h+var_108], rax
0x14002f3e9  lea     rax, [rbp+arg_10]
0x14002f3ed  mov     [rsp+140h+var_110], rax
0x14002f3f2  lea     rax, [rbp+arg_18]
0x14002f3f6  mov     ecx, [r8+48h]
0x14002f3fa  add     r8, 8
0x14002f3fe  mov     [rsp+140h+var_118], rax
0x14002f403  lea     rax, [rbp+var_68]
0x14002f407  mov     [rbp+arg_18], ecx
0x14002f40a  mov     rcx, rdi
0x14002f40d  mov     [rsp+140h+var_120], rax
0x14002f412  mov     [rbp+var_68], 0
0x14002f41a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002f41f  mov     rcx, rbx
0x14002f422  mov     rbx, [rsp+140h+arg_8]
0x14002f42a  add     rsp, 130h
0x14002f431  pop     rdi
0x14002f432  pop     rsi
0x14002f433  pop     rbp
0x14002f434  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
