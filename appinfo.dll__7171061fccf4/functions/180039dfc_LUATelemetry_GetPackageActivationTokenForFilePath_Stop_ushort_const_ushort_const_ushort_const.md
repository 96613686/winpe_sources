# LUATelemetry::GetPackageActivationTokenForFilePath::Stop(ushort const *,ushort const *,ushort const *)

- ea: `0x180039dfc`
- end: `0x18003a091`
- name: `?Stop@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXPEBG00@Z`
- size: `661`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002c480`

## callees

- `0x180002acc`
- `0x18000ef04`
- `0x18000f168`
- `0x180011fd0`
- `0x18001b03c`
- `0x18001b23c`
- `0x180039dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a012`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::Stop(
        LUATelemetry::GetPackageActivationTokenForFilePath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
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
  int v19; // [rsp+C0h] [rbp-80h] BYREF
  int v20; // [rsp+C4h] [rbp-7Ch] BYREF
  int v21; // [rsp+C8h] [rbp-78h] BYREF
  int v22; // [rsp+CCh] [rbp-74h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-58h] BYREF
  const wchar_t *v27; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v28; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v29; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v30; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v31; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v32; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v33; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v34; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v35; // [rsp+130h] [rbp-10h] BYREF
  const wchar_t *v36; // [rsp+138h] [rbp-8h] BYREF
  DWORD v37; // [rsp+180h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LUATelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      v31 = (const wchar_t *)*((_QWORD *)v10 + 15);
      v32 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
      v13 = *((_QWORD *)this + 34);
      v37 = v10[26];
      v33 = (const wchar_t *)*((_QWORD *)v10 + 12);
      v34 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
      v20 = v10[20];
      v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
      v21 = v10[8];
      v36 = (const wchar_t *)*((_QWORD *)v10 + 3);
      v22 = *v10;
      v24 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
      v23 = v10[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
      v19 = v10[2];
      v28 = a4;
      v29 = a3;
      v30 = a2;
      v26 = 0x1000000;
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v12,
        (__int64)&unk_1800569C0,
        v13 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v19,
        &v25,
        (__int64)&v23,
        &v24,
        (__int64)&v22,
        &v36,
        (__int64)&v21,
        &v35,
        (__int64)&v20,
        &v34,
        &v33,
        (__int64)&v37,
        &v32,
        &v31,
        &v30,
        &v29,
        &v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = LUATelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x200000000000LL) )
    {
      v27 = a4;
      v26 = (__int64)a3;
      v25 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v37 = CurrentThreadId;
      v19 = *(_DWORD *)(v17 + 72);
      v24 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned __int8 *)word_180056CEA,
        (const GUID *)(v17 + 8),
        v18,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v37,
        &v25,
        (const wchar_t **)&v26,
        &v27);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180039dfc  push    rbp
0x180039dfe  push    rbx
0x180039dff  push    rsi
0x180039e00  push    rdi
0x180039e01  push    r14
0x180039e03  push    r15
0x180039e05  lea     rbp, [rsp-8]
0x180039e0a  sub     rsp, 148h
0x180039e11  mov     rdi, [rcx+110h]
0x180039e18  mov     rsi, r9
0x180039e1b  mov     r14, r8
0x180039e1e  mov     r15, rdx
0x180039e21  mov     rbx, rcx
0x180039e24  mov     eax, [rdi+48h]
0x180039e27  test    eax, eax
0x180039e29  jns     loc_180039FD8
0x180039e2f  add     rdi, 50h ; 'P'
0x180039e33  cmp     eax, [rdi+8]
0x180039e36  jnz     loc_180039FD8
0x180039e3c  test    rdi, rdi
0x180039e3f  jz      loc_180039FD8
0x180039e45  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180039e4a  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180039e4f  mov     r9, rax
0x180039e52  mov     ecx, [rax]
0x180039e54  cmp     ecx, 5
0x180039e57  jbe     loc_18003A07A
0x180039e5d  mov     rdx, 200000000000h
0x180039e67  mov     rcx, rax
0x180039e6a  call    _tlgKeywordOn
0x180039e6f  test    al, al
0x180039e71  jz      loc_18003A07A
0x180039e77  mov     rax, [rdi+78h]
0x180039e7b  lea     rdx, unk_1800569C0
0x180039e82  mov     [rbp+30h+var_60], rax
0x180039e86  mov     rcx, r9
0x180039e89  mov     rax, [rdi+70h]
0x180039e8d  mov     [rbp+30h+var_58], rax
0x180039e91  mov     eax, [rdi+68h]
0x180039e94  mov     r8, [rbx+110h]
0x180039e9b  mov     [rbp+30h+arg_0], eax
0x180039e9e  add     r8, 8
0x180039ea2  mov     rax, [rdi+60h]
0x180039ea6  mov     [rbp+30h+var_50], rax
0x180039eaa  mov     rax, [rdi+58h]
0x180039eae  mov     [rbp+30h+var_48], rax
0x180039eb2  mov     eax, [rdi+50h]
0x180039eb5  mov     [rbp+30h+var_AC], eax
0x180039eb8  mov     rax, [rdi+48h]
0x180039ebc  mov     [rbp+30h+var_40], rax
0x180039ec0  mov     eax, [rdi+20h]
0x180039ec3  mov     [rbp+30h+var_A8], eax
0x180039ec6  mov     rax, [rdi+18h]
0x180039eca  mov     [rbp+30h+var_38], rax
0x180039ece  mov     eax, [rdi]
0x180039ed0  mov     [rbp+30h+var_A4], eax
0x180039ed3  mov     rax, [rdi+80h]
0x180039eda  mov     [rbp+30h+var_98], rax
0x180039ede  mov     eax, [rdi+40h]
0x180039ee1  mov     [rbp+30h+var_A0], eax
0x180039ee4  mov     rax, [rdi+38h]
0x180039ee8  mov     [rbp+30h+var_90], rax
0x180039eec  mov     eax, [rdi+8]
0x180039eef  mov     [rbp+30h+var_B0], eax
0x180039ef2  lea     rax, [rbp+30h+var_78]
0x180039ef6  mov     [rsp+170h+var_C0], rax
0x180039efe  lea     rax, [rbp+30h+var_70]
0x180039f02  mov     [rsp+170h+var_C8], rax
0x180039f0a  lea     rax, [rbp+30h+var_68]
0x180039f0e  mov     [rsp+170h+var_D0], rax
0x180039f16  lea     rax, [rbp+30h+var_60]
0x180039f1a  mov     [rsp+170h+var_D8], rax
0x180039f22  lea     rax, [rbp+30h+var_58]
0x180039f26  mov     [rsp+170h+var_E0], rax
0x180039f2e  lea     rax, [rbp+30h+arg_0]
0x180039f32  mov     [rsp+170h+var_E8], rax
0x180039f3a  lea     rax, [rbp+30h+var_50]
0x180039f3e  mov     [rsp+170h+var_F0], rax
0x180039f46  lea     rax, [rbp+30h+var_48]
0x180039f4a  mov     [rsp+170h+var_F8], rax
0x180039f4f  lea     rax, [rbp+30h+var_AC]
0x180039f53  mov     [rsp+170h+var_100], rax
0x180039f58  lea     rax, [rbp+30h+var_40]
0x180039f5c  mov     [rsp+170h+var_108], rax
0x180039f61  lea     rax, [rbp+30h+var_A8]
0x180039f65  mov     [rsp+170h+var_110], rax
0x180039f6a  lea     rax, [rbp+30h+var_38]
0x180039f6e  mov     [rsp+170h+var_118], rax
0x180039f73  lea     rax, [rbp+30h+var_A4]
0x180039f77  mov     [rsp+170h+var_120], rax
0x180039f7c  lea     rax, [rbp+30h+var_98]
0x180039f80  mov     [rsp+170h+var_128], rax
0x180039f85  lea     rax, [rbp+30h+var_A0]
0x180039f89  mov     [rsp+170h+var_130], rax
0x180039f8e  lea     rax, [rbp+30h+var_90]
0x180039f92  mov     [rsp+170h+var_138], rax
0x180039f97  lea     rax, [rbp+30h+var_B0]
0x180039f9b  mov     [rsp+170h+var_140], rax
0x180039fa0  lea     rax, [rbp+30h+var_88]
0x180039fa4  mov     [rsp+170h+var_148], rax
0x180039fa9  lea     rax, [rbp+30h+var_80]
0x180039fad  mov     [rsp+170h+var_150], rax
0x180039fb2  mov     [rbp+30h+var_78], rsi
0x180039fb6  mov     [rbp+30h+var_70], r14
0x180039fba  mov     [rbp+30h+var_68], r15
0x180039fbe  mov     [rbp+30h+var_88], 1000000h
0x180039fc6  mov     [rbp+30h+var_80], 0
0x180039fce  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180039fd3  jmp     loc_18003A07A
0x180039fd8  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180039fdd  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180039fe2  mov     rdi, rax
0x180039fe5  mov     ecx, [rax]
0x180039fe7  cmp     ecx, 5
0x180039fea  jbe     loc_18003A07A
0x180039ff0  mov     rdx, 200000000000h
0x180039ffa  mov     rcx, rax
0x180039ffd  call    _tlgKeywordOn
0x18003a002  test    al, al
0x18003a004  jz      short loc_18003A07A
0x18003a006  mov     [rbp+30h+var_80], rsi
0x18003a00a  mov     [rbp+30h+var_88], r14
0x18003a00e  mov     [rbp+30h+var_90], r15
0x18003a012  call    cs:__imp_GetCurrentThreadId
0x18003a018  mov     r8, [rbx+110h]
0x18003a01f  lea     rdx, word_180056CEA
0x18003a026  mov     [rbp+30h+arg_0], eax
0x18003a029  mov     rcx, rdi
0x18003a02c  mov     eax, [r8+48h]
0x18003a030  add     r8, 8
0x18003a034  mov     [rbp+30h+var_B0], eax
0x18003a037  lea     rax, [rbp+30h+var_80]
0x18003a03b  mov     [rsp+170h+var_128], rax
0x18003a040  lea     rax, [rbp+30h+var_88]
0x18003a044  mov     [rsp+170h+var_130], rax
0x18003a049  lea     rax, [rbp+30h+var_90]
0x18003a04d  mov     [rsp+170h+var_138], rax
0x18003a052  lea     rax, [rbp+30h+arg_0]
0x18003a056  mov     [rsp+170h+var_140], rax
0x18003a05b  lea     rax, [rbp+30h+var_B0]
0x18003a05f  mov     [rsp+170h+var_148], rax
0x18003a064  lea     rax, [rbp+30h+var_98]
0x18003a068  mov     [rsp+170h+var_150], rax
0x18003a06d  mov     [rbp+30h+var_98], 0
0x18003a075  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003a07a  mov     rcx, rbx
0x18003a07d  add     rsp, 148h
0x18003a084  pop     r15
0x18003a086  pop     r14
0x18003a088  pop     rdi
0x18003a089  pop     rsi
0x18003a08a  pop     rbx
0x18003a08b  pop     rbp
0x18003a08c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
