# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x14000fdf0`
- end: `0x140010136`
- name: `?NotifyFailure@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x1400026f4`
- `0x140002998`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x14000fdf0`
- `0x140011aa0`
- `0x140014120`
- `0x14001f010`

## pseudocode

```c
char __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rax
  int v15; // edx
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v19; // [rsp+B8h] [rbp-78h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+148h] [rbp+18h] BYREF
  int v33; // [rsp+150h] [rbp+20h] BYREF
  int v34; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v9 > 2u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL, v10, v9) )
      {
        LODWORD(v31) = a2[17];
        v32 = a2[4];
        v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v13 = a1[34];
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v33 = a2[26];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v34 = a2[20];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v18 = a2[8];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v17 = *a2;
        v28 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v19) = a2[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v20) = a2[2];
        v27 = (__int64)v12;
        v30[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (__int64)byte_140025F49,
          v13 + 8,
          v11,
          (__int64)v30,
          (__int64)&v20,
          &v29,
          (__int64)&v19,
          &v28,
          (__int64)&v17,
          &v21,
          (__int64)&v18,
          &v22,
          (__int64)&v34,
          &v23,
          &v24,
          (__int64)&v33,
          &v25,
          &v26,
          (__int64)&v32,
          (__int64)&v31,
          (const unsigned __int16 **)&v27);
      }
    }
    else
    {
      v4 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5, v4) )
      {
        v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v8 = a1[34];
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v31) = a2[26];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v32 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v33 = a2[8];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v34 = *a2;
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v17 = a2[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        v18 = a2[2];
        v20 = v7;
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&byte_140024E17,
          v8 + 8,
          v6,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v34,
          &v24,
          (__int64)&v33,
          &v23,
          (__int64)&v32,
          &v22,
          &v21,
          (__int64)&v31,
          &v19,
          &v20);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v31);
  v14 = (_DWORD *)a1[34];
  v15 = a2[2];
  if ( v15 != v14[22] && (v15 != v14[18] || (int)v14[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v14 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v31);
  return 1;
}

```

## disassembly

```asm
0x14000fdf0  push    rbp
0x14000fdf2  push    rbx
0x14000fdf3  push    rdi
0x14000fdf4  lea     rbp, [rsp+10h]
0x14000fdf9  sub     rsp, 120h
0x14000fe00  test    byte ptr [rdx+4], 2
0x14000fe04  mov     rbx, rdx
0x14000fe07  mov     rdi, rcx
0x14000fe0a  jnz     loc_1400100EE
0x14000fe10  mov     rax, [rcx]
0x14000fe13  mov     edx, [rdx+10h]
0x14000fe16  mov     rax, [rax+10h]
0x14000fe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe1f  test    al, al
0x14000fe21  jnz     loc_14000FF71
0x14000fe27  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14000fe2c  mov     r9, rax
0x14000fe2f  mov     ecx, [rax]
0x14000fe31  cmp     ecx, 2
0x14000fe34  jbe     loc_1400100EE
0x14000fe3a  mov     rdx, 200000000000h
0x14000fe44  mov     rcx, rax
0x14000fe47  call    _tlgKeywordOn
0x14000fe4c  test    al, al
0x14000fe4e  jz      loc_1400100EE
0x14000fe54  mov     rax, [rbx+70h]
0x14000fe58  lea     rdx, byte_140024E17
0x14000fe5f  mov     rcx, [rbx+78h]
0x14000fe63  mov     r8, [rdi+110h]
0x14000fe6a  mov     [rbp+var_78], rax
0x14000fe6e  add     r8, 8
0x14000fe72  mov     eax, [rbx+68h]
0x14000fe75  mov     dword ptr [rbp+arg_0], eax
0x14000fe78  mov     rax, [rbx+60h]
0x14000fe7c  mov     [rbp+var_68], rax
0x14000fe80  mov     rax, [rbx+58h]
0x14000fe84  mov     [rbp+var_60], rax
0x14000fe88  mov     eax, [rbx+50h]
0x14000fe8b  mov     [rbp+arg_8], eax
0x14000fe8e  mov     rax, [rbx+48h]
0x14000fe92  mov     [rbp+var_58], rax
0x14000fe96  mov     eax, [rbx+20h]
0x14000fe99  mov     [rbp+arg_10], eax
0x14000fe9c  mov     rax, [rbx+18h]
0x14000fea0  mov     [rbp+var_50], rax
0x14000fea4  mov     eax, [rbx]
0x14000fea6  mov     [rbp+arg_18], eax
0x14000fea9  mov     rax, [rbx+80h]
0x14000feb0  mov     [rbp+var_48], rax
0x14000feb4  mov     eax, [rbx+40h]
0x14000feb7  mov     [rbp+var_80], eax
0x14000feba  mov     rax, [rbx+38h]
0x14000febe  mov     [rbp+var_40], rax
0x14000fec2  mov     eax, [rbx+8]
0x14000fec5  mov     [rbp+var_7C], eax
0x14000fec8  lea     rax, [rbp+var_70]
0x14000fecc  mov     [rsp+130h+var_A0], rax
0x14000fed4  lea     rax, [rbp+var_78]
0x14000fed8  mov     [rsp+130h+var_A8], rax
0x14000fee0  lea     rax, [rbp+arg_0]
0x14000fee4  mov     [rsp+130h+var_B0], rax
0x14000feec  lea     rax, [rbp+var_68]
0x14000fef0  mov     [rsp+130h+var_B8], rax
0x14000fef5  lea     rax, [rbp+var_60]
0x14000fef9  mov     [rsp+130h+var_C0], rax
0x14000fefe  lea     rax, [rbp+arg_8]
0x14000ff02  mov     [rsp+130h+var_C8], rax
0x14000ff07  lea     rax, [rbp+var_58]
0x14000ff0b  mov     [rsp+130h+var_D0], rax
0x14000ff10  lea     rax, [rbp+arg_10]
0x14000ff14  mov     [rsp+130h+var_D8], rax
0x14000ff19  lea     rax, [rbp+var_50]
0x14000ff1d  mov     [rsp+130h+var_E0], rax
0x14000ff22  lea     rax, [rbp+arg_18]
0x14000ff26  mov     [rsp+130h+var_E8], rax
0x14000ff2b  lea     rax, [rbp+var_48]
0x14000ff2f  mov     [rsp+130h+var_F0], rax
0x14000ff34  lea     rax, [rbp+var_80]
0x14000ff38  mov     [rsp+130h+var_F8], rax
0x14000ff3d  lea     rax, [rbp+var_40]
0x14000ff41  mov     [rsp+130h+var_100], rax
0x14000ff46  lea     rax, [rbp+var_7C]
0x14000ff4a  mov     [rsp+130h+var_108], rax
0x14000ff4f  lea     rax, [rbp+var_38]
0x14000ff53  mov     [rbp+var_70], rcx
0x14000ff57  mov     rcx, r9
0x14000ff5a  mov     [rsp+130h+var_110], rax
0x14000ff5f  mov     [rbp+var_38], 1000000h
0x14000ff67  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000ff6c  jmp     loc_1400100EE
0x14000ff71  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14000ff76  mov     r9, rax
0x14000ff79  mov     ecx, [rax]
0x14000ff7b  cmp     ecx, 2
0x14000ff7e  jbe     loc_1400100EE
0x14000ff84  mov     rdx, 200000000000h
0x14000ff8e  mov     rcx, rax
0x14000ff91  call    _tlgKeywordOn
0x14000ff96  test    al, al
0x14000ff98  jz      loc_1400100EE
0x14000ff9e  mov     eax, [rbx+44h]
0x14000ffa1  lea     rdx, byte_140025F49
0x14000ffa8  mov     dword ptr [rbp+arg_0], eax
0x14000ffab  mov     eax, [rbx+10h]
0x14000ffae  mov     [rbp+arg_8], eax
0x14000ffb1  mov     rax, [rbx+78h]
0x14000ffb5  mov     rcx, [rbx+30h]
0x14000ffb9  mov     [rbp+var_40], rax
0x14000ffbd  mov     rax, [rbx+70h]
0x14000ffc1  mov     r8, [rdi+110h]
0x14000ffc8  mov     [rbp+var_48], rax
0x14000ffcc  add     r8, 8
0x14000ffd0  mov     eax, [rbx+68h]
0x14000ffd3  mov     [rbp+arg_10], eax
0x14000ffd6  mov     rax, [rbx+60h]
0x14000ffda  mov     [rbp+var_50], rax
0x14000ffde  mov     rax, [rbx+58h]
0x14000ffe2  mov     [rbp+var_58], rax
0x14000ffe6  mov     eax, [rbx+50h]
0x14000ffe9  mov     [rbp+arg_18], eax
0x14000ffec  mov     rax, [rbx+48h]
0x14000fff0  mov     [rbp+var_60], rax
0x14000fff4  mov     eax, [rbx+20h]
0x14000fff7  mov     [rbp+var_7C], eax
0x14000fffa  mov     rax, [rbx+18h]
0x14000fffe  mov     [rbp+var_68], rax
0x140010002  mov     eax, [rbx]
0x140010004  mov     [rbp+var_80], eax
0x140010007  mov     rax, [rbx+80h]
0x14001000e  mov     [rbp+var_30], rax
0x140010012  mov     eax, [rbx+40h]
0x140010015  mov     dword ptr [rbp+var_78], eax
0x140010018  mov     rax, [rbx+38h]
0x14001001c  mov     [rbp+var_28], rax
0x140010020  mov     eax, [rbx+8]
0x140010023  mov     dword ptr [rbp+var_70], eax
0x140010026  lea     rax, [rbp+var_38]
0x14001002a  mov     [rsp+130h+var_88], rax
0x140010032  lea     rax, [rbp+arg_0]
0x140010036  mov     [rsp+130h+var_90], rax
0x14001003e  lea     rax, [rbp+arg_8]
0x140010042  mov     [rsp+130h+var_98], rax
0x14001004a  lea     rax, [rbp+var_40]
0x14001004e  mov     [rsp+130h+var_A0], rax
0x140010056  lea     rax, [rbp+var_48]
0x14001005a  mov     [rsp+130h+var_A8], rax
0x140010062  lea     rax, [rbp+arg_10]
0x140010066  mov     [rsp+130h+var_B0], rax
0x14001006e  lea     rax, [rbp+var_50]
0x140010072  mov     [rsp+130h+var_B8], rax
0x140010077  lea     rax, [rbp+var_58]
0x14001007b  mov     [rsp+130h+var_C0], rax
0x140010080  lea     rax, [rbp+arg_18]
0x140010084  mov     [rsp+130h+var_C8], rax
0x140010089  lea     rax, [rbp+var_60]
0x14001008d  mov     [rsp+130h+var_D0], rax
0x140010092  lea     rax, [rbp+var_7C]
0x140010096  mov     [rsp+130h+var_D8], rax
0x14001009b  lea     rax, [rbp+var_68]
0x14001009f  mov     [rsp+130h+var_E0], rax
0x1400100a4  lea     rax, [rbp+var_80]
0x1400100a8  mov     [rsp+130h+var_E8], rax
0x1400100ad  lea     rax, [rbp+var_30]
0x1400100b1  mov     [rsp+130h+var_F0], rax
0x1400100b6  lea     rax, [rbp+var_78]
0x1400100ba  mov     [rsp+130h+var_F8], rax
0x1400100bf  lea     rax, [rbp+var_28]
0x1400100c3  mov     [rsp+130h+var_100], rax
0x1400100c8  lea     rax, [rbp+var_70]
0x1400100cc  mov     [rsp+130h+var_108], rax
0x1400100d1  lea     rax, [rbp+var_20]
0x1400100d5  mov     [rbp+var_38], rcx
0x1400100d9  mov     rcx, r9
0x1400100dc  mov     [rsp+130h+var_110], rax
0x1400100e1  mov     [rbp+var_20], 1000000h
0x1400100e9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400100ee  lea     rdx, [rbp+arg_0]
0x1400100f2  mov     rcx, rdi
0x1400100f5  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400100fa  mov     rax, [rdi+110h]
0x140010101  mov     edx, [rbx+8]
0x140010104  lea     rcx, [rax+50h]; this
0x140010108  cmp     edx, [rcx+8]
0x14001010b  jz      short loc_140010120
0x14001010d  cmp     edx, [rax+48h]
0x140010110  jnz     short loc_140010118
0x140010112  cmp     dword ptr [rax+48h], 0
0x140010116  jl      short loc_140010120
0x140010118  mov     rdx, rbx; struct wil::FailureInfo *
0x14001011b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x140010120  lea     rcx, [rbp+arg_0]
0x140010124  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140010129  mov     al, 1
0x14001012b  add     rsp, 120h
0x140010132  pop     rdi
0x140010133  pop     rbx
0x140010134  pop     rbp
0x140010135  retn
```
