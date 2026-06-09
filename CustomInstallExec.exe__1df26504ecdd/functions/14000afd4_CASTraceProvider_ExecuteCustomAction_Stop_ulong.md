# CASTraceProvider::ExecuteCustomAction::Stop(ulong)

- ea: `0x14000afd4`
- end: `0x14000b2d0`
- name: `?Stop@ExecuteCustomAction@CASTraceProvider@@QEAAXK@Z`
- size: `764`
- prototype: `void __fastcall(CASTraceProvider::ExecuteCustomAction *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140008bc4`

## callees

- `0x1400017e8`
- `0x140001d50`
- `0x14000258c`
- `0x140009730`
- `0x14000a594`
- `0x14000afd4`
- `0x14000babc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b23b`

## pseudocode

```c
void __fastcall CASTraceProvider::ExecuteCustomAction::Stop(CASTraceProvider::ExecuteCustomAction *this, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rcx
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+D0h] [rbp-80h] BYREF
  int v21; // [rsp+D4h] [rbp-7Ch] BYREF
  int v22; // [rsp+D8h] [rbp-78h] BYREF
  int v23; // [rsp+DCh] [rbp-74h] BYREF
  int v24; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-68h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+100h] [rbp-50h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+110h] [rbp-40h] BYREF
  __int64 v31; // [rsp+118h] [rbp-38h] BYREF
  const unsigned __int16 *v32; // [rsp+120h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+128h] [rbp-28h] BYREF
  const unsigned __int16 *v34; // [rsp+130h] [rbp-20h] BYREF
  const unsigned __int16 *v35; // [rsp+138h] [rbp-18h] BYREF
  const unsigned __int16 *v36; // [rsp+140h] [rbp-10h] BYREF
  const unsigned __int16 *v37; // [rsp+148h] [rbp-8h] BYREF
  int v38; // [rsp+170h] [rbp+20h] BYREF
  int v39; // [rsp+180h] [rbp+30h] BYREF
  DWORD v40; // [rsp+188h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = CASTraceProvider::Provider(v7);
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v9, v8) )
    {
      v39 = *((_DWORD *)this + 92);
      v29 = (const unsigned __int16 *)*((_QWORD *)this + 45);
      v30 = (const unsigned __int16 *)*((_QWORD *)this + 44);
      v31 = (__int64)this + 336;
      v32 = (const unsigned __int16 *)*((_QWORD *)v6 + 15);
      v33 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v40 = v6[26];
      v34 = (const unsigned __int16 *)*((_QWORD *)v6 + 12);
      v11 = *((_QWORD *)this + 34);
      v35 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v21 = v6[20];
      v36 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v22 = v6[8];
      v37 = (const unsigned __int16 *)*((_QWORD *)v6 + 3);
      v23 = *v6;
      v25 = *((_QWORD *)v6 + 16);
      v24 = v6[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v20 = v6[2];
      v27 = 0x1000000;
      v28 = 0x1000000;
      v38 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)byte_140012109,
        v11 + 8,
        v10,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v20,
        &v26,
        (__int64)&v24,
        (const unsigned __int16 **)&v25,
        (__int64)&v23,
        &v37,
        (__int64)&v22,
        &v36,
        (__int64)&v21,
        &v35,
        &v34,
        (__int64)&v40,
        &v33,
        &v32,
        &v31,
        &v30,
        &v29,
        (__int64)&v39,
        (__int64)&v38);
    }
  }
  else
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = CASTraceProvider::Provider(v12);
    v16 = (__int64)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL, v14, v15) )
    {
      v39 = *((_DWORD *)this + 92);
      v28 = *((_QWORD *)this + 45);
      v27 = *((_QWORD *)this + 44);
      v26 = (const unsigned __int16 *)((char *)this + 336);
      v38 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v18 = *((_QWORD *)this + 34);
      v40 = CurrentThreadId;
      v20 = *(_DWORD *)(v18 + 72);
      v25 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (__int64)&byte_140012267,
        v18 + 8,
        v19,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v40,
        (__int64 *)&v26,
        (const unsigned __int16 **)&v27,
        (const unsigned __int16 **)&v28,
        (__int64)&v39,
        (__int64)&v38);
    }
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000afd4  mov     [rsp-18h+arg_8], rbx
0x14000afd9  push    rbp
0x14000afda  push    rsi
0x14000afdb  push    rdi
0x14000afdc  mov     rbp, rsp
0x14000afdf  sub     rsp, 150h
0x14000afe6  mov     rdi, [rcx+110h]
0x14000afed  mov     esi, edx
0x14000afef  mov     rbx, rcx
0x14000aff2  mov     eax, [rdi+48h]
0x14000aff5  test    eax, eax
0x14000aff7  jns     loc_14000B1DC
0x14000affd  add     rdi, 50h ; 'P'
0x14000b001  cmp     eax, [rdi+8]
0x14000b004  jnz     loc_14000B1DC
0x14000b00a  test    rdi, rdi
0x14000b00d  jz      loc_14000B1DC
0x14000b013  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b018  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b01d  mov     r9, rax
0x14000b020  mov     ecx, [rax]
0x14000b022  cmp     ecx, 5
0x14000b025  jbe     loc_14000B2B6
0x14000b02b  mov     rdx, 400000000000h
0x14000b035  mov     rcx, rax
0x14000b038  call    _tlgKeywordOn
0x14000b03d  test    al, al
0x14000b03f  jz      loc_14000B2B6
0x14000b045  mov     eax, [rbx+170h]
0x14000b04b  mov     [rbp+arg_10], eax
0x14000b04e  mov     rax, [rbx+168h]
0x14000b055  mov     [rbp+var_48], rax
0x14000b059  mov     rax, [rbx+160h]
0x14000b060  mov     [rbp+var_40], rax
0x14000b064  lea     rax, [rbx+150h]
0x14000b06b  mov     [rbp+var_38], rax
0x14000b06f  mov     rax, [rdi+78h]
0x14000b073  mov     [rbp+var_30], rax
0x14000b077  mov     rax, [rdi+70h]
0x14000b07b  mov     [rbp+var_28], rax
0x14000b07f  mov     eax, [rdi+68h]
0x14000b082  mov     [rbp+arg_18], eax
0x14000b085  mov     rax, [rdi+60h]
0x14000b089  mov     [rbp+var_20], rax
0x14000b08d  mov     rax, [rdi+58h]
0x14000b091  mov     r8, [rbx+110h]
0x14000b098  mov     [rbp+var_18], rax
0x14000b09c  add     r8, 8
0x14000b0a0  mov     eax, [rdi+50h]
0x14000b0a3  mov     [rbp+var_7C], eax
0x14000b0a6  mov     rax, [rdi+48h]
0x14000b0aa  mov     [rbp+var_10], rax
0x14000b0ae  mov     eax, [rdi+20h]
0x14000b0b1  mov     [rbp+var_78], eax
0x14000b0b4  mov     rax, [rdi+18h]
0x14000b0b8  mov     [rbp+var_8], rax
0x14000b0bc  mov     eax, [rdi]
0x14000b0be  mov     [rbp+var_74], eax
0x14000b0c1  mov     rax, [rdi+80h]
0x14000b0c8  mov     [rbp+var_68], rax
0x14000b0cc  mov     eax, [rdi+40h]
0x14000b0cf  mov     [rbp+var_70], eax
0x14000b0d2  mov     rax, [rdi+38h]
0x14000b0d6  mov     [rbp+var_60], rax
0x14000b0da  mov     eax, [rdi+8]
0x14000b0dd  mov     [rbp+var_80], eax
0x14000b0e0  mov     eax, 1000000h
0x14000b0e5  mov     [rbp+var_58], rax
0x14000b0e9  mov     [rbp+var_50], rax
0x14000b0ed  lea     rax, [rbp+arg_0]
0x14000b0f1  mov     [rsp+150h+var_90], rax
0x14000b0f9  lea     rax, [rbp+arg_10]
0x14000b0fd  mov     [rsp+150h+var_98], rax
0x14000b105  lea     rax, [rbp+var_48]
0x14000b109  mov     [rsp+150h+var_A0], rax
0x14000b111  lea     rax, [rbp+var_40]
0x14000b115  mov     [rsp+150h+var_A8], rax
0x14000b11d  lea     rax, [rbp+var_38]
0x14000b121  mov     [rsp+150h+var_B0], rax
0x14000b129  lea     rax, [rbp+var_30]
0x14000b12d  mov     [rsp+150h+var_B8], rax
0x14000b135  lea     rax, [rbp+var_28]
0x14000b139  mov     [rsp+150h+var_C0], rax
0x14000b141  lea     rax, [rbp+arg_18]
0x14000b145  mov     [rsp+150h+var_C8], rax
0x14000b14d  lea     rax, [rbp+var_20]
0x14000b151  mov     [rsp+150h+var_D0], rax
0x14000b159  lea     rax, [rbp+var_18]
0x14000b15d  mov     [rsp+150h+var_D8], rax
0x14000b162  lea     rax, [rbp+var_7C]
0x14000b166  mov     [rsp+150h+var_E0], rax
0x14000b16b  lea     rax, [rbp+var_10]
0x14000b16f  mov     [rsp+150h+var_E8], rax
0x14000b174  lea     rax, [rbp+var_78]
0x14000b178  mov     [rsp+150h+var_F0], rax
0x14000b17d  lea     rax, [rbp+var_8]
0x14000b181  mov     [rsp+150h+var_F8], rax
0x14000b186  lea     rax, [rbp+var_74]
0x14000b18a  mov     [rsp+150h+var_100], rax
0x14000b18f  lea     rax, [rbp+var_68]
0x14000b193  mov     [rsp+150h+var_108], rax
0x14000b198  lea     rax, [rbp+var_70]
0x14000b19c  mov     [rsp+150h+var_110], rax
0x14000b1a1  lea     rax, [rbp+var_60]
0x14000b1a5  mov     [rsp+150h+var_118], rax
0x14000b1aa  lea     rax, [rbp+var_80]
0x14000b1ae  mov     [rsp+150h+var_120], rax
0x14000b1b3  lea     rax, [rbp+var_58]
0x14000b1b7  mov     [rbp+arg_0], esi
0x14000b1ba  mov     [rsp+150h+var_128], rax
0x14000b1bf  lea     rdx, byte_140012109
0x14000b1c6  lea     rax, [rbp+var_50]
0x14000b1ca  mov     rcx, r9
0x14000b1cd  mov     [rsp+150h+var_130], rax
0x14000b1d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByRef@$0BA@@@6644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000b1d7  jmp     loc_14000B2B6
0x14000b1dc  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b1e1  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b1e6  mov     rdi, rax
0x14000b1e9  mov     ecx, [rax]
0x14000b1eb  cmp     ecx, 5
0x14000b1ee  jbe     loc_14000B2B6
0x14000b1f4  mov     rdx, 400000000000h
0x14000b1fe  mov     rcx, rax
0x14000b201  call    _tlgKeywordOn
0x14000b206  test    al, al
0x14000b208  jz      loc_14000B2B6
0x14000b20e  mov     eax, [rbx+170h]
0x14000b214  mov     [rbp+arg_10], eax
0x14000b217  mov     rax, [rbx+168h]
0x14000b21e  mov     [rbp+var_50], rax
0x14000b222  mov     rax, [rbx+160h]
0x14000b229  mov     [rbp+var_58], rax
0x14000b22d  lea     rax, [rbx+150h]
0x14000b234  mov     [rbp+var_60], rax
0x14000b238  mov     [rbp+arg_0], esi
0x14000b23b  call    cs:__imp_GetCurrentThreadId
0x14000b241  mov     r8, [rbx+110h]
0x14000b248  lea     rdx, byte_140012267
0x14000b24f  mov     [rbp+arg_18], eax
0x14000b252  mov     rcx, rdi
0x14000b255  mov     eax, [r8+48h]
0x14000b259  add     r8, 8
0x14000b25d  mov     [rbp+var_80], eax
0x14000b260  mov     eax, 1000000h
0x14000b265  mov     [rbp+var_68], rax
0x14000b269  lea     rax, [rbp+arg_0]
0x14000b26d  mov     [rsp+150h+var_F8], rax
0x14000b272  lea     rax, [rbp+arg_10]
0x14000b276  mov     [rsp+150h+var_100], rax
0x14000b27b  lea     rax, [rbp+var_50]
0x14000b27f  mov     [rsp+150h+var_108], rax
0x14000b284  lea     rax, [rbp+var_58]
0x14000b288  mov     [rsp+150h+var_110], rax
0x14000b28d  lea     rax, [rbp+var_60]
0x14000b291  mov     [rsp+150h+var_118], rax
0x14000b296  lea     rax, [rbp+arg_18]
0x14000b29a  mov     [rsp+150h+var_120], rax
0x14000b29f  lea     rax, [rbp+var_80]
0x14000b2a3  mov     [rsp+150h+var_128], rax
0x14000b2a8  lea     rax, [rbp+var_68]
0x14000b2ac  mov     [rsp+150h+var_130], rax
0x14000b2b1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000b2b6  mov     rcx, rbx
0x14000b2b9  mov     rbx, [rsp+150h+arg_8]
0x14000b2c1  add     rsp, 150h
0x14000b2c8  pop     rdi
0x14000b2c9  pop     rsi
0x14000b2ca  pop     rbp
0x14000b2cb  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
