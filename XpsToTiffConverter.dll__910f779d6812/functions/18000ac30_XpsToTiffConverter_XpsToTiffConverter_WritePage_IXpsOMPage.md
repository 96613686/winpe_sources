# XpsToTiffConverter::XpsToTiffConverter::WritePage(IXpsOMPage *)

- ea: `0x18000ac30`
- end: `0x18000b0a6`
- name: `?WritePage@XpsToTiffConverter@1@UEAAJPEAUIXpsOMPage@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(XpsToTiffConverter::XpsToTiffConverter *__hidden this, struct IXpsOMPage *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800016a0`
- `0x180009494`
- `0x180009d6c`
- `0x18000a1dc`
- `0x18000ac30`
- `0x18000b0ac`
- `0x18000b62c`
- `0x18000c238`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000adf5`
- `OLEAUT32!__imp_VariantInit` at `0x18000adf5`
- `OLEAUT32!__imp_VariantClear` at `0x18000af5d`
- `OLEAUT32!__imp_VariantClear` at `0x18000af5d`

## string_xrefs

- `0x18000adde`: `TiffCompressionMethod`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall XpsToTiffConverter::XpsToTiffConverter::WritePage(
        XpsToTiffConverter::XpsToTiffConverter *this,
        struct IXpsOMPage *a2)
{
  int v3; // ecx
  int v4; // ecx
  GUID v5; // xmm1
  unsigned int v6; // r12d
  unsigned int v7; // esi
  __int64 v8; // rbx
  __int64 v9; // r14
  int XpsBitmapProvider; // eax
  __int64 v11; // rbx
  unsigned int v12; // r14d
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const char *v23; // r9
  __int64 result; // rax
  const char *v25; // [rsp+20h] [rbp-118h]
  int v26; // [rsp+20h] [rbp-118h]
  __int64 v27; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v28; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-D0h] BYREF
  int v31[2]; // [rsp+70h] [rbp-C8h] BYREF
  int v32; // [rsp+78h] [rbp-C0h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v34[2]; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD v35[3]; // [rsp+B0h] [rbp-88h] BYREF
  __int128 v36; // [rsp+C8h] [rbp-70h]
  GUID v37; // [rsp+E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v3 = *((_DWORD *)this + 27);
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
            "Unexpected page output color",
            v25);
        v5 = GUID_WICPixelFormatBlackWhite;
      }
      else
      {
        v5 = GUID_WICPixelFormat8bppGray;
      }
    }
    else
    {
      v5 = GUID_WICPixelFormat32bppPBGRA;
    }
    v37 = v5;
    v6 = (int)(float)((float)*((int *)this + 22) * *((float *)this + 24));
    v7 = (int)(float)((float)*((int *)this + 23) * *((float *)this + 25));
    v29 = 0;
    v8 = *((_QWORD *)this + 5);
    v9 = *((_QWORD *)this + 4);
    v30 = (__int64)a2;
    if ( a2 )
    {
      ((void (__fastcall *)(struct IXpsOMPage *))a2->lpVtbl->AddRef)(a2);
      v5 = v37;
    }
    *(GUID *)v34 = v5;
    XpsBitmapProvider = PrintCore::CreateXpsBitmapProvider(
                          *((_DWORD *)this + 22),
                          *((_DWORD *)this + 23),
                          *((_DWORD *)this + 6),
                          (__int64)v34,
                          (__int64)&v30,
                          v9,
                          v8,
                          (__int64)&v29);
    if ( XpsBitmapProvider < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)XpsBitmapProvider,
        v26);
    v11 = v29;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 80LL))(v29);
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
    std::vector<unsigned char>::vector<unsigned char>(v31, v12 * v13);
    v28 = 0;
    v27 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *))(**((_QWORD **)this + 7) + 80LL))(
            *((_QWORD *)this + 7),
            &v27,
            &v28);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v14,
        v26);
    v35[0] = 0;
    v35[1] = 0;
    v36 = 0;
    v35[2] = L"TiffCompressionMethod";
    VariantInit(&pvarg);
    pvarg.vt = 17;
    pvarg.bVal = 4;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, VARIANTARG *))(*(_QWORD *)v28 + 32LL))(
            v28,
            1,
            v35,
            &pvarg);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v15,
        v26);
    v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 24LL))(v27, v28);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v16,
        v26);
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 32LL))(v27, v6, v7);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v17,
        v26);
    v18 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v27 + 48LL))(v27, &v37);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v18,
        v26);
    while ( v7 )
    {
      v19 = v12;
      if ( v7 < v12 )
        v19 = v7;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 24LL))(
              v11,
              v19,
              (unsigned int)(v32 - v31[0]));
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
          (const char *)(unsigned int)v20,
          v26);
      v26 = v31[0];
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 80LL))(
              v27,
              v19,
              v13,
              (unsigned int)(v32 - v31[0]));
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
          (const char *)(unsigned int)v21,
          v26);
      v7 -= v19;
    }
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 96LL))(v27);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v22,
        v26);
    VariantClear(&pvarg);
    if ( v27 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(&v27);
    if ( v28 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(&v28);
    std::vector<unsigned char>::~vector<unsigned char>(v31);
    if ( v11 )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(&v29);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x54,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpsto"
                                         "tiffconverter.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x18000ac30  push    rbx
0x18000ac32  push    rsi
0x18000ac33  push    rdi
0x18000ac34  push    r12
0x18000ac36  push    r14
0x18000ac38  push    r15
0x18000ac3a  sub     rsp, 108h
0x18000ac41  mov     rax, cs:__security_cookie
0x18000ac48  xor     rax, rsp
0x18000ac4b  mov     [rsp+138h+var_48], rax
0x18000ac53  mov     rdi, rcx
0x18000ac56  mov     ecx, [rcx+6Ch]
0x18000ac59  test    ecx, ecx
0x18000ac5b  jz      short loc_18000AC7D
0x18000ac5d  sub     ecx, 1
0x18000ac60  jz      short loc_18000AC74
0x18000ac62  cmp     ecx, 1
0x18000ac65  jnz     loc_18000AFCD
0x18000ac6b  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormatBlackWhite.Data1
0x18000ac72  jmp     short loc_18000AC84
0x18000ac74  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormat8bppGray.Data1
0x18000ac7b  jmp     short loc_18000AC84
0x18000ac7d  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x18000ac84  movaps  [rsp+138h+var_58], xmm1
0x18000ac8c  mov     eax, [rdi+58h]
0x18000ac8f  xorps   xmm0, xmm0
0x18000ac92  cvtsi2ss xmm0, rax
0x18000ac97  mulss   xmm0, dword ptr [rdi+60h]
0x18000ac9c  cvttss2si r12, xmm0
0x18000aca1  mov     eax, [rdi+5Ch]
0x18000aca4  xorps   xmm0, xmm0
0x18000aca7  cvtsi2ss xmm0, rax
0x18000acac  mulss   xmm0, dword ptr [rdi+64h]
0x18000acb1  cvttss2si rsi, xmm0
0x18000acb6  mov     [rsp+138h+var_D8], 0
0x18000acbf  mov     rbx, [rdi+28h]
0x18000acc3  mov     r14, [rdi+20h]
0x18000acc7  mov     [rsp+138h+var_D0], rdx
0x18000accc  test    rdx, rdx
0x18000accf  jz      short loc_18000ACE8
0x18000acd1  mov     rax, [rdx]
0x18000acd4  mov     rcx, rdx
0x18000acd7  mov     rax, [rax+8]
0x18000acdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace0  movaps  xmm1, [rsp+138h+var_58]
0x18000ace8  movdqa  xmmword ptr [rsp+138h+var_98], xmm1
0x18000acf1  lea     rax, [rsp+138h+var_D8]
0x18000acf6  mov     [rsp+138h+var_F0], rax; __int64
0x18000acfb  mov     [rsp+138h+var_F8], rbx; __int64
0x18000ad00  mov     [rsp+138h+var_100], r14; __int64
0x18000ad05  lea     rax, [rsp+138h+var_D0]
0x18000ad0a  mov     [rsp+138h+var_108], rax; __int64
0x18000ad0f  lea     rax, [rsp+138h+var_98]
0x18000ad17  mov     [rsp+138h+var_110], rax; __int64
0x18000ad1c  mov     eax, [rdi+18h]
0x18000ad1f  mov     [rsp+138h+var_118], eax; int
0x18000ad23  mov     r9d, esi
0x18000ad26  mov     r8d, r12d
0x18000ad29  mov     edx, [rdi+5Ch]; int
0x18000ad2c  mov     ecx, [rdi+58h]; int
0x18000ad2f  call    ?CreateXpsBitmapProvider@PrintCore@@YAJIIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEAPEAUIPageBitmapProvider@@@Z; PrintCore::CreateXpsBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,IPageBitmapProvider * *)
0x18000ad34  mov     rcx, [rsp+138h]; this
0x18000ad3c  test    eax, eax
0x18000ad3e  js      loc_18000AFEE
0x18000ad44  mov     rbx, [rsp+138h+var_D8]
0x18000ad49  mov     rax, [rbx]
0x18000ad4c  mov     rcx, rbx
0x18000ad4f  mov     rax, [rax+50h]
0x18000ad53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad58  mov     r14d, eax
0x18000ad5b  mov     rcx, [rbx]
0x18000ad5e  mov     rax, [rcx+48h]
0x18000ad62  mov     rcx, rbx
0x18000ad65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad6a  mov     r15d, eax
0x18000ad6d  mov     edx, eax
0x18000ad6f  imul    edx, r14d
0x18000ad73  lea     rcx, [rsp+138h+var_C8]
0x18000ad78  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000ad7d  nop
0x18000ad7e  mov     [rsp+138h+var_E0], 0
0x18000ad87  mov     [rsp+138h+var_E8], 0
0x18000ad90  mov     rcx, [rdi+38h]
0x18000ad94  mov     rax, [rcx]
0x18000ad97  lea     r8, [rsp+138h+var_E0]
0x18000ad9c  lea     rdx, [rsp+138h+var_E8]
0x18000ada1  mov     rax, [rax+50h]
0x18000ada5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adaa  mov     rcx, [rsp+138h]; this
0x18000adb2  test    eax, eax
0x18000adb4  js      loc_18000B003
0x18000adba  mov     [rsp+138h+var_88], 0
0x18000adc6  mov     [rsp+138h+var_80], 0
0x18000add2  xorps   xmm0, xmm0
0x18000add5  movdqu  [rsp+138h+var_70], xmm0
0x18000adde  lea     rax, aTiffcompressio; "TiffCompressionMethod"
0x18000ade5  mov     [rsp+138h+var_78], rax
0x18000aded  lea     rcx, [rsp+138h+pvarg]; pvarg
0x18000adf5  call    cs:__imp_VariantInit
0x18000adfb  nop
0x18000adfc  mov     eax, 11h
0x18000ae01  mov     word ptr [rsp+138h+pvarg], ax
0x18000ae09  mov     byte ptr [rsp+138h+pvarg+8], 4
0x18000ae11  mov     rcx, [rsp+138h+var_E0]
0x18000ae16  mov     rax, [rcx]
0x18000ae19  lea     r9, [rsp+138h+pvarg]
0x18000ae21  lea     r8, [rsp+138h+var_88]
0x18000ae29  mov     edx, 1
0x18000ae2e  mov     rax, [rax+20h]
0x18000ae32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae37  mov     rcx, [rsp+138h]; this
0x18000ae3f  test    eax, eax
0x18000ae41  js      loc_18000B018
0x18000ae47  mov     rcx, [rsp+138h+var_E8]
0x18000ae4c  mov     rax, [rcx]
0x18000ae4f  mov     rdx, [rsp+138h+var_E0]
0x18000ae54  mov     rax, [rax+18h]
0x18000ae58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5d  mov     rcx, [rsp+138h]; this
0x18000ae65  test    eax, eax
0x18000ae67  js      loc_18000B02C
0x18000ae6d  mov     rcx, [rsp+138h+var_E8]
0x18000ae72  mov     rax, [rcx]
0x18000ae75  mov     r8d, esi
0x18000ae78  mov     edx, r12d
0x18000ae7b  mov     rax, [rax+20h]
0x18000ae7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae84  mov     rcx, [rsp+138h]; this
0x18000ae8c  test    eax, eax
0x18000ae8e  js      loc_18000B040
0x18000ae94  mov     rcx, [rsp+138h+var_E8]
0x18000ae99  mov     rax, [rcx]
0x18000ae9c  lea     rdx, [rsp+138h+var_58]
0x18000aea4  mov     rax, [rax+30h]
0x18000aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aead  mov     rcx, [rsp+138h]; this
0x18000aeb5  test    eax, eax
0x18000aeb7  js      loc_18000B054
0x18000aebd  test    esi, esi
0x18000aebf  jz      short loc_18000AF34
0x18000aec1  mov     edi, r14d
0x18000aec4  cmp     esi, r14d
0x18000aec7  cmovb   edi, esi
0x18000aeca  mov     r9, qword ptr [rsp+138h+var_C8]
0x18000aecf  mov     rax, [rbx]
0x18000aed2  mov     r8d, [rsp+138h+var_C0]
0x18000aed7  sub     r8d, r9d
0x18000aeda  mov     edx, edi
0x18000aedc  mov     rcx, rbx
0x18000aedf  mov     rax, [rax+18h]
0x18000aee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee8  mov     rcx, [rsp+138h]; this
0x18000aef0  test    eax, eax
0x18000aef2  js      loc_18000B068
0x18000aef8  mov     rcx, [rsp+138h+var_E8]
0x18000aefd  mov     rdx, qword ptr [rsp+138h+var_C8]
0x18000af02  mov     rax, [rcx]
0x18000af05  mov     r9d, [rsp+138h+var_C0]
0x18000af0a  sub     r9d, edx
0x18000af0d  mov     qword ptr [rsp+138h+var_118], rdx; int
0x18000af12  mov     r8d, r15d
0x18000af15  mov     edx, edi
0x18000af17  mov     rax, [rax+50h]
0x18000af1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af20  mov     rcx, [rsp+138h]; this
0x18000af28  test    eax, eax
0x18000af2a  js      loc_18000B07C
0x18000af30  sub     esi, edi
0x18000af32  jmp     short loc_18000AEBD
0x18000af34  mov     rcx, [rsp+138h+var_E8]
0x18000af39  mov     rax, [rcx]
0x18000af3c  mov     rax, [rax+60h]
0x18000af40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af45  mov     rcx, [rsp+138h]; this
0x18000af4d  test    eax, eax
0x18000af4f  js      loc_18000B090
0x18000af55  lea     rcx, [rsp+138h+pvarg]; pvarg
0x18000af5d  call    cs:__imp_VariantClear
0x18000af63  nop
0x18000af64  cmp     [rsp+138h+var_E8], 0
0x18000af6a  jz      short loc_18000AF77
0x18000af6c  lea     rcx, [rsp+138h+var_E8]
0x18000af71  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000af76  nop
0x18000af77  cmp     [rsp+138h+var_E0], 0
0x18000af7d  jz      short loc_18000AF8A
0x18000af7f  lea     rcx, [rsp+138h+var_E0]
0x18000af84  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000af89  nop
0x18000af8a  lea     rcx, [rsp+138h+var_C8]
0x18000af8f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000af94  nop
0x18000af95  test    rbx, rbx
0x18000af98  jz      short loc_18000AFA4
0x18000af9a  lea     rcx, [rsp+138h+var_D8]
0x18000af9f  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000afa4  xor     eax, eax
0x18000afa6  jmp     short loc_18000AFAC
0x18000afa8  mov     eax, dword ptr [rsp+138h+var_E8]
0x18000afac  mov     rcx, [rsp+138h+var_48]
0x18000afb4  xor     rcx, rsp; StackCookie
0x18000afb7  call    __security_check_cookie
0x18000afbc  add     rsp, 108h
0x18000afc3  pop     r15
0x18000afc5  pop     r14
0x18000afc7  pop     r12
0x18000afc9  pop     rdi
0x18000afca  pop     rsi
0x18000afcb  pop     rbx
0x18000afcc  retn
0x18000afcd  mov     rcx, [rsp+138h]; this
0x18000afd5  lea     r9, aUnexpectedPage; "Unexpected page output color"
0x18000afdc  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000afe3  mov     edx, 81h; void *
0x18000afe8  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x18000afee  mov     r9d, eax; char *
0x18000aff1  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000aff8  mov     edx, 32h ; '2'; void *
0x18000affd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b003  mov     r9d, eax; char *
0x18000b006  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b00d  mov     edx, 3Ch ; '<'; void *
0x18000b012  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b018  mov     r9d, eax; char *
0x18000b01b  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b022  mov     edx, 43h ; 'C'; void *
0x18000b027  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b02c  mov     r9d, eax; char *
0x18000b02f  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b036  mov     edx, 44h ; 'D'; void *
0x18000b03b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b040  mov     r9d, eax; char *
0x18000b043  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b04a  mov     edx, 45h ; 'E'; void *
0x18000b04f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b054  mov     r9d, eax; char *
0x18000b057  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b05e  mov     edx, 46h ; 'F'; void *
0x18000b063  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b068  mov     r9d, eax; char *
0x18000b06b  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b072  mov     edx, 4Ch ; 'L'; void *
0x18000b077  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b07c  mov     r9d, eax; char *
0x18000b07f  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b086  mov     edx, 4Fh ; 'O'; void *
0x18000b08b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b090  mov     r9d, eax; char *
0x18000b093  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000b09a  mov     edx, 51h ; 'Q'; void *
0x18000b09f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
