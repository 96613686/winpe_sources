# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x18003a098`
- end: `0x18003a32d`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `661`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003b4c4`

## callees

- `0x180002e30`
- `0x180003204`
- `0x18000f168`
- `0x180011fd0`
- `0x18001b03c`
- `0x1800384dc`
- `0x18003a098`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a2ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a2ae`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  _BYTE v19[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v20; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v21; // [rsp+C8h] [rbp-78h] BYREF
  int v22; // [rsp+CCh] [rbp-74h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  int v24; // [rsp+D4h] [rbp-6Ch] BYREF
  int v25; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-60h] BYREF
  const wchar_t *v27; // [rsp+E8h] [rbp-58h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v29; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v32; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v34; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v35; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v36; // [rsp+130h] [rbp-10h] BYREF
  char v37; // [rsp+180h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v29 = (const wchar_t *)*((_QWORD *)v10 + 15);
      v30 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
      v13 = *((_QWORD *)this + 34);
      v22 = v10[26];
      v31 = (const wchar_t *)*((_QWORD *)v10 + 12);
      v32 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
      v23 = v10[20];
      v33 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
      v24 = v10[8];
      v34 = (const wchar_t *)*((_QWORD *)v10 + 3);
      v25 = *v10;
      v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
      v20 = v10[16];
      v36 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
      v21 = v10[2];
      v28 = a4;
      v37 = a3;
      v19[0] = a2;
      v26 = 0x1000000;
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v12,
        (__int64)byte_180056E25,
        v13 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v21,
        &v36,
        (__int64)&v20,
        &v35,
        (__int64)&v25,
        &v34,
        (__int64)&v24,
        &v33,
        (__int64)&v23,
        &v32,
        &v31,
        (__int64)&v22,
        &v30,
        &v29,
        (__int64)v19,
        (__int64)&v37,
        &v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
    {
      v27 = a4;
      v37 = a3;
      v19[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v21 = CurrentThreadId;
      v20 = *(_DWORD *)(v17 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v15,
        (__int64)word_180055D02,
        v17 + 8,
        v18,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v21,
        (__int64)v19,
        (__int64)&v37,
        &v27);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18003a098  push    rbp
0x18003a09a  push    rbx
0x18003a09b  push    rsi
0x18003a09c  push    rdi
0x18003a09d  push    r14
0x18003a09f  push    r15
0x18003a0a1  lea     rbp, [rsp-8]
0x18003a0a6  sub     rsp, 148h
0x18003a0ad  mov     rdi, [rcx+110h]
0x18003a0b4  mov     rsi, r9
0x18003a0b7  mov     r14b, r8b
0x18003a0ba  mov     r15b, dl
0x18003a0bd  mov     rbx, rcx
0x18003a0c0  mov     eax, [rdi+48h]
0x18003a0c3  test    eax, eax
0x18003a0c5  jns     loc_18003A274
0x18003a0cb  add     rdi, 50h ; 'P'
0x18003a0cf  cmp     eax, [rdi+8]
0x18003a0d2  jnz     loc_18003A274
0x18003a0d8  test    rdi, rdi
0x18003a0db  jz      loc_18003A274
0x18003a0e1  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a0e6  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003a0eb  mov     r9, rax
0x18003a0ee  mov     ecx, [rax]
0x18003a0f0  cmp     ecx, 5
0x18003a0f3  jbe     loc_18003A316
0x18003a0f9  mov     rdx, 400000000000h
0x18003a103  mov     rcx, rax
0x18003a106  call    _tlgKeywordOn
0x18003a10b  test    al, al
0x18003a10d  jz      loc_18003A316
0x18003a113  mov     rax, [rdi+78h]
0x18003a117  lea     rdx, byte_180056E25
0x18003a11e  mov     [rbp+30h+var_78], rax
0x18003a122  mov     rcx, r9
0x18003a125  mov     rax, [rdi+70h]
0x18003a129  mov     [rbp+30h+var_70], rax
0x18003a12d  mov     eax, [rdi+68h]
0x18003a130  mov     r8, [rbx+110h]
0x18003a137  mov     [rbp+30h+var_A4], eax
0x18003a13a  add     r8, 8
0x18003a13e  mov     rax, [rdi+60h]
0x18003a142  mov     [rbp+30h+var_68], rax
0x18003a146  mov     rax, [rdi+58h]
0x18003a14a  mov     [rbp+30h+var_60], rax
0x18003a14e  mov     eax, [rdi+50h]
0x18003a151  mov     [rbp+30h+var_A0], eax
0x18003a154  mov     rax, [rdi+48h]
0x18003a158  mov     [rbp+30h+var_58], rax
0x18003a15c  mov     eax, [rdi+20h]
0x18003a15f  mov     [rbp+30h+var_9C], eax
0x18003a162  mov     rax, [rdi+18h]
0x18003a166  mov     [rbp+30h+var_50], rax
0x18003a16a  mov     eax, [rdi]
0x18003a16c  mov     [rbp+30h+var_98], eax
0x18003a16f  mov     rax, [rdi+80h]
0x18003a176  mov     [rbp+30h+var_48], rax
0x18003a17a  mov     eax, [rdi+40h]
0x18003a17d  mov     [rbp+30h+var_AC], eax
0x18003a180  mov     rax, [rdi+38h]
0x18003a184  mov     [rbp+30h+var_40], rax
0x18003a188  mov     eax, [rdi+8]
0x18003a18b  mov     [rbp+30h+var_A8], eax
0x18003a18e  lea     rax, [rbp+30h+var_80]
0x18003a192  mov     [rsp+170h+var_C0], rax
0x18003a19a  lea     rax, [rbp+30h+arg_0]
0x18003a19e  mov     [rsp+170h+var_C8], rax
0x18003a1a6  lea     rax, [rbp+30h+var_B0]
0x18003a1aa  mov     [rsp+170h+var_D0], rax
0x18003a1b2  lea     rax, [rbp+30h+var_78]
0x18003a1b6  mov     [rsp+170h+var_D8], rax
0x18003a1be  lea     rax, [rbp+30h+var_70]
0x18003a1c2  mov     [rsp+170h+var_E0], rax
0x18003a1ca  lea     rax, [rbp+30h+var_A4]
0x18003a1ce  mov     [rsp+170h+var_E8], rax
0x18003a1d6  lea     rax, [rbp+30h+var_68]
0x18003a1da  mov     [rsp+170h+var_F0], rax
0x18003a1e2  lea     rax, [rbp+30h+var_60]
0x18003a1e6  mov     [rsp+170h+var_F8], rax
0x18003a1eb  lea     rax, [rbp+30h+var_A0]
0x18003a1ef  mov     [rsp+170h+var_100], rax
0x18003a1f4  lea     rax, [rbp+30h+var_58]
0x18003a1f8  mov     [rsp+170h+var_108], rax
0x18003a1fd  lea     rax, [rbp+30h+var_9C]
0x18003a201  mov     [rsp+170h+var_110], rax
0x18003a206  lea     rax, [rbp+30h+var_50]
0x18003a20a  mov     [rsp+170h+var_118], rax
0x18003a20f  lea     rax, [rbp+30h+var_98]
0x18003a213  mov     [rsp+170h+var_120], rax
0x18003a218  lea     rax, [rbp+30h+var_48]
0x18003a21c  mov     [rsp+170h+var_128], rax
0x18003a221  lea     rax, [rbp+30h+var_AC]
0x18003a225  mov     [rsp+170h+var_130], rax
0x18003a22a  lea     rax, [rbp+30h+var_40]
0x18003a22e  mov     [rsp+170h+var_138], rax
0x18003a233  lea     rax, [rbp+30h+var_A8]
0x18003a237  mov     [rsp+170h+var_140], rax
0x18003a23c  lea     rax, [rbp+30h+var_90]
0x18003a240  mov     [rsp+170h+var_148], rax
0x18003a245  lea     rax, [rbp+30h+var_88]
0x18003a249  mov     [rsp+170h+var_150], rax
0x18003a24e  mov     [rbp+30h+var_80], rsi
0x18003a252  mov     [rbp+30h+arg_0], r14b
0x18003a256  mov     [rbp+30h+var_B0], r15b
0x18003a25a  mov     [rbp+30h+var_90], 1000000h
0x18003a262  mov     [rbp+30h+var_88], 0
0x18003a26a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18003a26f  jmp     loc_18003A316
0x18003a274  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a279  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003a27e  mov     rdi, rax
0x18003a281  mov     ecx, [rax]
0x18003a283  cmp     ecx, 5
0x18003a286  jbe     loc_18003A316
0x18003a28c  mov     rdx, 400000000000h
0x18003a296  mov     rcx, rax
0x18003a299  call    _tlgKeywordOn
0x18003a29e  test    al, al
0x18003a2a0  jz      short loc_18003A316
0x18003a2a2  mov     [rbp+30h+var_88], rsi
0x18003a2a6  mov     [rbp+30h+arg_0], r14b
0x18003a2aa  mov     [rbp+30h+var_B0], r15b
0x18003a2ae  call    cs:__imp_GetCurrentThreadId
0x18003a2b4  mov     r8, [rbx+110h]
0x18003a2bb  lea     rdx, word_180055D02
0x18003a2c2  mov     [rbp+30h+var_A8], eax
0x18003a2c5  mov     rcx, rdi
0x18003a2c8  mov     eax, [r8+48h]
0x18003a2cc  add     r8, 8
0x18003a2d0  mov     [rbp+30h+var_AC], eax
0x18003a2d3  lea     rax, [rbp+30h+var_88]
0x18003a2d7  mov     [rsp+170h+var_128], rax
0x18003a2dc  lea     rax, [rbp+30h+arg_0]
0x18003a2e0  mov     [rsp+170h+var_130], rax
0x18003a2e5  lea     rax, [rbp+30h+var_B0]
0x18003a2e9  mov     [rsp+170h+var_138], rax
0x18003a2ee  lea     rax, [rbp+30h+var_A8]
0x18003a2f2  mov     [rsp+170h+var_140], rax
0x18003a2f7  lea     rax, [rbp+30h+var_AC]
0x18003a2fb  mov     [rsp+170h+var_148], rax
0x18003a300  lea     rax, [rbp+30h+var_90]
0x18003a304  mov     [rsp+170h+var_150], rax
0x18003a309  mov     [rbp+30h+var_90], 0
0x18003a311  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18003a316  mov     rcx, rbx
0x18003a319  add     rsp, 148h
0x18003a320  pop     r15
0x18003a322  pop     r14
0x18003a324  pop     rdi
0x18003a325  pop     rsi
0x18003a326  pop     rbx
0x18003a327  pop     rbp
0x18003a328  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
