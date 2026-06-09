# SvgToBitmapConverter::SvgToBitmapConverter(CursorTypeInfo,IWICImagingFactory *,ID2D1Factory1 *,int,_D3DCOLORVALUE)

- ea: `0x18002ab30`
- end: `0x18002ae7c`
- name: `??0SvgToBitmapConverter@@QEAA@VCursorTypeInfo@@PEAUIWICImagingFactory@@PEAUID2D1Factory1@@HU_D3DCOLORVALUE@@@Z`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002b2b4`

## callees

- `0x180003980`
- `0x18000a6e0`
- `0x18000cf94`
- `0x1800166d4`
- `0x180016770`
- `0x18002ab30`
- `0x18002b89c`
- `0x18002b994`
- `0x18002bb80`
- `0x180035010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002acd8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002acd8`

## string_xrefs

- `0x18002abde`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002ac4d`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002ac9b`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002ace9`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002ad4e`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002ae13`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SvgToBitmapConverter::SvgToBitmapConverter(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _OWORD *a6)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, GUID *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  int v17; // eax
  __int64 SvgInputPath; // rax
  const WCHAR *v19; // rax
  HRESULT v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, IStream *, unsigned __int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 *, __int64, __int64); // rbx
  int v26; // eax
  __int64 v28; // [rsp+40h] [rbp-89h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-81h] BYREF
  __int64 v30; // [rsp+50h] [rbp-79h] BYREF
  __int64 v31; // [rsp+58h] [rbp-71h] BYREF
  IStream *ppstm[2]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v33; // [rsp+70h] [rbp-59h] BYREF
  int v34; // [rsp+78h] [rbp-51h]
  int v35; // [rsp+7Ch] [rbp-4Dh]
  _OWORD v36[2]; // [rsp+80h] [rbp-49h] BYREF
  int v37; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v38; // [rsp+A4h] [rbp-25h]
  __int64 v39; // [rsp+ACh] [rbp-1Dh]
  __int64 v40; // [rsp+B4h] [rbp-15h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  ppstm[1] = (IStream *)a1;
  *(_QWORD *)a1 = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 8) = a5;
  v36[0] = *a6;
  *(_BYTE *)(a1 + 12) = anonymous_namespace_::IsInvertedColor(v36, 0, a3, a4);
  v31 = v10;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)v11 + 136LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v13 = v12(a3, (unsigned int)a5, (unsigned int)a5, &GUID_WICPixelFormat32bppPBGRA);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v13,
      2);
  v37 = 1;
  v38 = 0x100000057LL;
  v39 = 0;
  v40 = 0;
  v29 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a4 + 104LL))(
          a4,
          v31,
          &v37,
          &v29);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v14,
      2);
  v28 = 0;
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
  v16 = **v29;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v17 = v16(v15, &GUID_7836d248_68cc_4df6_b9e8_de991bf62eb7, &v28);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v17,
      2);
  ppstm[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppstm);
  SvgInputPath = anonymous_namespace_::GetSvgInputPath(v36, a2);
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SvgInputPath);
  v20 = SHCreateStreamOnFileW(v19, 0, ppstm);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v20,
      2);
  std::wstring::_Tidy_deallocate(v36);
  v30 = 0;
  v21 = v28;
  v22 = *(__int64 (__fastcall **)(__int64, IStream *, unsigned __int64, __int64 *))(*(_QWORD *)v28 + 920LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v23 = v22(
          v21,
          ppstm[0],
          _mm_unpacklo_ps((__m128)COERCE_UNSIGNED_INT((float)a5), (__m128)COERCE_UNSIGNED_INT((float)a5)).m128_u64[0],
          &v30);
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v23,
      2);
  if ( *(_BYTE *)(a1 + 12) )
    v36[0] = _mm_load_si128((const __m128i *)&_xmm);
  else
    v36[0] = *a6;
  anonymous_namespace_::RecolorSvgDocument(v30, v36);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 384LL))(v28);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 928LL))(v28, v30);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v28 + 392LL))(v28, 0, 0);
  v33 = 0;
  v34 = a5;
  v35 = a5;
  v24 = v31;
  v25 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, __int64))(*(_QWORD *)v31 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v26 = v25(v24, &v33, 1, a1);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v26,
      2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppstm);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return a1;
}

```

## disassembly

```asm
0x18002ab30  push    rbp
0x18002ab32  push    rbx
0x18002ab33  push    rsi
0x18002ab34  push    rdi
0x18002ab35  push    r12
0x18002ab37  push    r13
0x18002ab39  push    r14
0x18002ab3b  push    r15
0x18002ab3d  lea     rbp, [rsp-0Fh]
0x18002ab42  sub     rsp, 0D8h
0x18002ab49  mov     rax, cs:__security_cookie
0x18002ab50  xor     rax, rsp
0x18002ab53  mov     [rbp+47h+var_50], rax
0x18002ab57  mov     r14, r9
0x18002ab5a  mov     rdi, r8
0x18002ab5d  mov     r13, rdx
0x18002ab60  mov     rsi, rcx
0x18002ab63  mov     [rbp+47h+var_A8], rcx
0x18002ab67  mov     r12, [rbp+47h+arg_28]
0x18002ab6b  xor     edx, edx
0x18002ab6d  mov     [rcx], rdx
0x18002ab70  mov     [rcx+0Ch], dl
0x18002ab73  mov     r15d, [rbp+47h+arg_20]
0x18002ab77  mov     [rcx+8], r15d
0x18002ab7b  movaps  xmm0, xmmword ptr [r12]
0x18002ab80  movdqu  [rbp+47h+var_90], xmm0
0x18002ab85  lea     rcx, [rbp+47h+var_90]
0x18002ab89  call    _anonymous_namespace___IsInvertedColor
0x18002ab8e  mov     [rsi+0Ch], al
0x18002ab91  mov     [rbp+47h+var_B8], rdx
0x18002ab95  mov     rax, [r8]
0x18002ab98  mov     rbx, [rax+88h]
0x18002ab9f  lea     rcx, [rbp+47h+var_B8]
0x18002aba3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002aba8  lea     rax, [rbp+47h+var_B8]
0x18002abac  mov     [rsp+110h+var_E8], rax
0x18002abb1  mov     [rsp+110h+var_F0], 2; int
0x18002abb9  lea     r9, GUID_WICPixelFormat32bppPBGRA
0x18002abc0  mov     r8d, r15d
0x18002abc3  mov     edx, r15d
0x18002abc6  mov     rcx, rdi
0x18002abc9  mov     rax, rbx
0x18002abcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abd1  mov     rcx, [rbp+4Fh]; this
0x18002abd5  xor     edx, edx
0x18002abd7  test    eax, eax
0x18002abd9  jns     short loc_18002ABF0
0x18002abdb  mov     r9d, eax; char *
0x18002abde  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002abe5  mov     edx, 195h; void *
0x18002abea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002abf0  mov     dword ptr [rsp+110h+var_C8], 57h ; 'W'
0x18002abf8  mov     eax, 1
0x18002abfd  mov     dword ptr [rbp+47h+var_C8+4], eax
0x18002ac00  mov     [rbp+47h+var_70], eax
0x18002ac03  mov     rax, [rsp+110h+var_C8]
0x18002ac08  mov     [rbp+47h+var_6C], rax
0x18002ac0c  mov     [rbp+47h+var_64], rdx
0x18002ac10  mov     [rbp+47h+var_5C], rdx
0x18002ac14  mov     [rsp+110h+var_C8], rdx
0x18002ac19  lea     rcx, [rsp+110h+var_C8]
0x18002ac1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ac23  mov     rax, [r14]
0x18002ac26  lea     r9, [rsp+110h+var_C8]
0x18002ac2b  lea     r8, [rbp+47h+var_70]
0x18002ac2f  mov     rdx, [rbp+47h+var_B8]
0x18002ac33  mov     rcx, r14
0x18002ac36  mov     rax, [rax+68h]
0x18002ac3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac3f  mov     rcx, [rbp+4Fh]; this
0x18002ac43  xor     r14d, r14d
0x18002ac46  test    eax, eax
0x18002ac48  jns     short loc_18002AC5F
0x18002ac4a  mov     r9d, eax; char *
0x18002ac4d  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002ac54  mov     edx, 1A3h; void *
0x18002ac59  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002ac5f  mov     [rsp+110h+var_D0], r14
0x18002ac64  mov     rdi, [rsp+110h+var_C8]
0x18002ac69  mov     rax, [rdi]
0x18002ac6c  mov     rbx, [rax]
0x18002ac6f  lea     rcx, [rsp+110h+var_D0]
0x18002ac74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ac79  lea     r8, [rsp+110h+var_D0]
0x18002ac7e  lea     rdx, _GUID_7836d248_68cc_4df6_b9e8_de991bf62eb7
0x18002ac85  mov     rcx, rdi
0x18002ac88  mov     rax, rbx
0x18002ac8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac90  mov     rcx, [rbp+4Fh]; this
0x18002ac94  test    eax, eax
0x18002ac96  jns     short loc_18002ACAD
0x18002ac98  mov     r9d, eax; char *
0x18002ac9b  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002aca2  mov     edx, 1A6h; void *
0x18002aca7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002acad  mov     [rbp+47h+ppstm], r14
0x18002acb1  lea     rcx, [rbp+47h+ppstm]
0x18002acb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002acba  mov     rdx, r13
0x18002acbd  lea     rcx, [rbp+47h+var_90]
0x18002acc1  call    _anonymous_namespace___GetSvgInputPath
0x18002acc6  nop
0x18002acc7  mov     rcx, rax
0x18002acca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002accf  lea     r8, [rbp+47h+ppstm]; ppstm
0x18002acd3  xor     edx, edx; grfMode
0x18002acd5  mov     rcx, rax; pszFile
0x18002acd8  call    cs:__imp_SHCreateStreamOnFileW
0x18002acde  mov     rcx, [rbp+4Fh]; this
0x18002ace2  test    eax, eax
0x18002ace4  jns     short loc_18002ACFB
0x18002ace6  mov     r9d, eax; char *
0x18002ace9  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002acf0  mov     edx, 1AAh; void *
0x18002acf5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002acfb  lea     rcx, [rbp+47h+var_90]
0x18002acff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ad04  mov     [rbp+47h+var_C0], r14
0x18002ad08  mov     rdi, [rsp+110h+var_D0]
0x18002ad0d  mov     rax, [rdi]
0x18002ad10  mov     rbx, [rax+398h]
0x18002ad17  lea     rcx, [rbp+47h+var_C0]
0x18002ad1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ad20  movd    xmm0, r15d
0x18002ad25  cvtdq2ps xmm0, xmm0
0x18002ad28  lea     r9, [rbp+47h+var_C0]
0x18002ad2c  unpcklps xmm0, xmm0
0x18002ad2f  movq    r8, xmm0
0x18002ad34  mov     rdx, [rbp+47h+ppstm]
0x18002ad38  mov     rcx, rdi
0x18002ad3b  mov     rax, rbx
0x18002ad3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad43  mov     rcx, [rbp+4Fh]; this
0x18002ad47  test    eax, eax
0x18002ad49  jns     short loc_18002AD60
0x18002ad4b  mov     r9d, eax; char *
0x18002ad4e  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002ad55  mov     edx, 1B2h; void *
0x18002ad5a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002ad60  lea     rdx, [rbp+47h+var_90]
0x18002ad64  mov     rcx, [rbp+47h+var_C0]
0x18002ad68  cmp     [rsi+0Ch], r14b
0x18002ad6c  jz      short loc_18002AD7D
0x18002ad6e  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x18002ad76  movdqa  [rbp+47h+var_90], xmm0
0x18002ad7b  jmp     short loc_18002AD87
0x18002ad7d  movaps  xmm0, xmmword ptr [r12]
0x18002ad82  movdqu  [rbp+47h+var_90], xmm0
0x18002ad87  call    _anonymous_namespace___RecolorSvgDocument
0x18002ad8c  mov     rcx, [rsp+110h+var_D0]
0x18002ad91  mov     rax, [rcx]
0x18002ad94  mov     rax, [rax+180h]
0x18002ad9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ada0  mov     rcx, [rsp+110h+var_D0]
0x18002ada5  mov     rax, [rcx]
0x18002ada8  mov     rdx, [rbp+47h+var_C0]
0x18002adac  mov     rax, [rax+3A0h]
0x18002adb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb8  mov     rcx, [rsp+110h+var_D0]
0x18002adbd  mov     rax, [rcx]
0x18002adc0  xor     r8d, r8d
0x18002adc3  xor     edx, edx
0x18002adc5  mov     rax, [rax+188h]
0x18002adcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002add1  mov     [rbp+47h+var_A0], r14
0x18002add5  mov     [rbp+47h+var_98], r15d
0x18002add9  mov     [rbp+47h+var_94], r15d
0x18002addd  mov     rdi, [rbp+47h+var_B8]
0x18002ade1  mov     rax, [rdi]
0x18002ade4  mov     rbx, [rax+40h]
0x18002ade8  mov     rcx, rsi
0x18002adeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002adf0  mov     r9, rsi
0x18002adf3  mov     r8d, 1
0x18002adf9  lea     rdx, [rbp+47h+var_A0]
0x18002adfd  mov     rcx, rdi
0x18002ae00  mov     rax, rbx
0x18002ae03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae08  mov     rcx, [rbp+4Fh]; this
0x18002ae0c  test    eax, eax
0x18002ae0e  jns     short loc_18002AE25
0x18002ae10  mov     r9d, eax; char *
0x18002ae13  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002ae1a  mov     edx, 1C9h; void *
0x18002ae1f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002ae25  lea     rcx, [rbp+47h+var_C0]
0x18002ae29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae2e  nop
0x18002ae2f  lea     rcx, [rbp+47h+ppstm]
0x18002ae33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae38  nop
0x18002ae39  lea     rcx, [rsp+110h+var_D0]
0x18002ae3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae43  nop
0x18002ae44  lea     rcx, [rsp+110h+var_C8]
0x18002ae49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae4e  nop
0x18002ae4f  lea     rcx, [rbp+47h+var_B8]
0x18002ae53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae58  nop
0x18002ae59  mov     rax, rsi
0x18002ae5c  mov     rcx, [rbp+47h+var_50]
0x18002ae60  xor     rcx, rsp; StackCookie
0x18002ae63  call    __security_check_cookie
0x18002ae68  add     rsp, 0D8h
0x18002ae6f  pop     r15
0x18002ae71  pop     r14
0x18002ae73  pop     r13
0x18002ae75  pop     r12
0x18002ae77  pop     rdi
0x18002ae78  pop     rsi
0x18002ae79  pop     rbx
0x18002ae7a  pop     rbp
0x18002ae7b  retn
```
