# OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(Windows::Internal::String const &,Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String &)

- ea: `0x18003e9d0`
- end: `0x18003f0b6`
- name: `?RetrieveAttribute@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEBVString@2Windows@@V?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEAV526@@Z`
- size: `1766`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003df60`
- `0x18003e6d0`
- `0x180045a04`
- `0x18009b5a0`
- `0x18009bf68`
- `0x1801384e0`
- `0x18013865c`

## callees

- `0x18000b3bc`
- `0x18003e9d0`
- `0x1800434a0`
- `0x180098bf4`
- `0x18009aff4`
- `0x1800a219c`
- `0x1800f0700`
- `0x1800f073c`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003eac9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003eac9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ea81`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ebe6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ea81`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ebe6`
- `OLEAUT32!__imp_VariantClear` at `0x18003ebf1`
- `OLEAUT32!__imp_VariantClear` at `0x18003ebf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ec2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ec2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ea3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ea3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec47`

## string_xrefs

- `0x18003ee61`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003eeed`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003ef9f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003efcb`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003eff3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003f010`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003f061`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003f079`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18003edb8`: `Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)`
- `0x18003ee32`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18003eed0`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18003f09f`: `onecore\admin\appmodel\common\xmltools.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(
        __int64 a1,
        HSTRING *a2,
        __int64 *a3,
        HSTRING *a4)
{
  __int64 *v4; // r12
  int v6; // eax
  unsigned int v7; // edi
  const OLECHAR *StringRawBuffer; // rsi
  __int64 v9; // r15
  OLECHAR *v10; // rbx
  unsigned __int64 v11; // rdi
  HRESULT v12; // r13d
  __int64 v13; // rcx
  const OLECHAR *v14; // rax
  int v15; // r14d
  int v16; // eax
  const void *bstrVal; // r12
  unsigned __int64 v18; // rdx
  BSTR v19; // rax
  unsigned int v20; // ecx
  unsigned int v21; // r15d
  WCHAR *v22; // rsi
  unsigned int v23; // eax
  unsigned __int64 v24; // rdx
  HSTRING v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v29; // ecx
  bool v30; // zf
  __int64 v31; // rcx
  WCHAR *v32; // rax
  unsigned int i; // r14d
  WCHAR *v34; // xmm6_8
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rdx
  WCHAR *v37; // r13
  unsigned int v38; // edx
  unsigned __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  unsigned __int64 v44; // rdx
  WCHAR *v45; // xmm6_8
  int v46; // [rsp+20h] [rbp-60h]
  int v47; // [rsp+20h] [rbp-60h]
  char *v48; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  PCNZWCH sourceString[2]; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-38h]
  VARIANTARG Src; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v54; // [rsp+C0h] [rbp+40h] BYREF
  __int64 *v55; // [rsp+D0h] [rbp+50h]
  HSTRING *v56; // [rsp+D8h] [rbp+58h]

  v56 = a4;
  v55 = a3;
  v4 = a3;
  *(_OWORD *)sourceString = 0;
  v51 = 0;
  v54 = 0;
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))*a3)(
         *a3,
         &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
         &v54);
  v7 = v6;
  if ( v6 < 0 )
  {
    LODWORD(v48) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "node.As(&element)",
      v48,
      (int)string);
    v42 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v4);
    return v7;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
  v9 = v54;
  memset(&Src, 0, sizeof(Src));
  Src.vt = 0;
  v10 = 0;
  v11 = -1;
  v12 = -2147024362;
  if ( v54 && StringRawBuffer )
  {
    SysFreeString(0);
    string = 0;
    v13 = 0x7FFFFFFF;
    v14 = StringRawBuffer;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v15 = -2147024809;
    if ( v13 )
    {
      if ( (unsigned int)(0x7FFFFFFF - v13) > 0x3FFFFFFF )
      {
        v15 = -2147024809;
      }
      else
      {
        v10 = SysAllocStringLen(StringRawBuffer, 0x7FFFFFFF - (int)v13);
        string = (HSTRING)v10;
        v15 = 0;
        if ( !v10 )
          v15 = -2147024882;
      }
    }
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v15,
        v46);
      v22 = (WCHAR *)sourceString[1];
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v9 + 352LL))(v9, v10, &Src);
      v15 = v16;
      if ( v16 >= 0 )
      {
        bstrVal = Src.bstrVal;
        string = (HSTRING)Src.llVal;
        if ( !Src.llVal )
        {
          v29 = _mm_cvtsi128_si32((__m128i)0LL);
          v30 = 2LL * v29 == 0;
          v31 = 2LL * v29;
          v22 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          v32 = v22;
          if ( !v30 )
          {
            do
            {
              *(_BYTE *)v32 = 0;
              v32 = (WCHAR *)((char *)v32 + 1);
              --v31;
            }
            while ( v31 );
          }
          goto LABEL_34;
        }
        v18 = 1073741822;
        v19 = Src.bstrVal;
        do
        {
          if ( !*v19 )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        v15 = -2147024809;
        if ( v18 )
          v15 = 0;
        v20 = 1073741822 - v18;
        if ( !v18 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v15,
            v46);
          v22 = (WCHAR *)sourceString[1];
          goto LABEL_32;
        }
        v21 = 1073741822 - v18;
        v15 = 0;
        if ( v20 > 0x7FFFFFFF )
          v15 = -2147024362;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v15,
            v46);
          v22 = (WCHAR *)sourceString[1];
          goto LABEL_32;
        }
        if ( !v20 )
        {
          v22 = (WCHAR *)sourceString[1];
          goto LABEL_25;
        }
        if ( v20 > 0x20 )
        {
          i = 1073741822 - v18;
        }
        else
        {
          for ( i = 8; i < v20; i *= 2 )
            ;
        }
        if ( i > 0x3FFFFFFF )
        {
          v15 = -2147023613;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A9,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)0x80070503LL,
            v46);
          v22 = (WCHAR *)sourceString[1];
          v38 = v51;
        }
        else
        {
          if ( !i )
          {
            v45 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            v22 = v45;
            if ( v45 )
            {
              operator delete(v45, v18);
              v22 = 0;
              sourceString[1] = 0;
              LODWORD(sourceString[0]) = 0;
            }
            v38 = 0;
            v51 = 0;
            goto LABEL_66;
          }
          v34 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          v22 = v34;
          v35 = 2LL * (i + 1);
          if ( !is_mul_ok(i + 1, 2u) )
            v35 = -1;
          v37 = (WCHAR *)operator new[](v35, (const struct std::nothrow_t *)std::nothrow);
          if ( v37 )
          {
            operator delete(v34, v36);
            v22 = v37;
            v12 = -2147024362;
            v38 = i + 1;
            v51 = i + 1;
            sourceString[1] = v22;
            if ( LODWORD(sourceString[0]) > i )
            {
              LODWORD(sourceString[0]) = i;
              v22[i] = 0;
            }
            else if ( LODWORD(sourceString[0]) < i && !LODWORD(sourceString[0]) )
            {
              *v22 = 0;
            }
            bstrVal = string;
LABEL_66:
            v15 = 0;
            goto LABEL_67;
          }
          v15 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x193,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)0x8007000ELL,
            v46);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C4,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)0x8007000ELL,
            v47);
          bstrVal = string;
          v12 = -2147024362;
          v38 = v51;
        }
LABEL_67:
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x232,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v15,
            v46);
          goto LABEL_32;
        }
        if ( v38 )
        {
          v23 = v38 - 1;
LABEL_26:
          if ( v21 > v23 )
          {
            v43 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)sourceString, v21);
            v15 = v43;
            if ( v43 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x20C,
                (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                (const char *)(unsigned int)v43,
                v46);
              v22 = (WCHAR *)sourceString[1];
LABEL_30:
              if ( v15 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x235,
                  (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                  (const char *)(unsigned int)v15,
                  v46);
              }
              else
              {
                memcpy_0(v22, bstrVal, 2 * v21);
                v15 = 0;
              }
LABEL_32:
              if ( v15 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x13D,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                  (const char *)(unsigned int)v15,
                  v46);
LABEL_34:
              v4 = v55;
              goto LABEL_35;
            }
            v22 = (WCHAR *)sourceString[1];
          }
          LODWORD(sourceString[0]) = v21;
          if ( v21 )
            v22[v21] = 0;
          v15 = 0;
          goto LABEL_30;
        }
LABEL_25:
        v23 = 0;
        goto LABEL_26;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v16,
        v46);
      v22 = (WCHAR *)sourceString[1];
    }
  }
  else
  {
    v15 = -2147024809;
    v22 = (WCHAR *)sourceString[1];
  }
LABEL_35:
  SysFreeString(v10);
  VariantClear(&Src);
  if ( v15 < 0 )
  {
    LODWORD(v48) = v15;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)",
      v48,
      (int)string);
    v40 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    if ( v22 )
      operator delete(v22, v39);
    v41 = *v4;
    if ( *v4 )
    {
      *v4 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    return (unsigned int)v15;
  }
  else
  {
    if ( v22 )
    {
      string = 0;
      do
        ++v11;
      while ( v22[v11] );
      if ( v11 <= 0xFFFFFFFF )
      {
        v12 = WindowsCreateString(v22, v11, &string);
        if ( v12 >= 0 )
        {
          v25 = *v56;
          *v56 = string;
          WindowsDeleteString(v25);
        }
      }
      if ( v12 >= 0 )
      {
        v26 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        operator delete(v22, v24);
        v27 = *v4;
        if ( *v4 )
        {
          *v4 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        return 0;
      }
    }
    else
    {
      v12 = -2147467261;
    }
    LODWORD(v48) = v12;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "result.Initialize(buffer.GetChars())",
      v48,
      (int)string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    if ( v22 )
      operator delete(v22, v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v4);
    return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x18003e9d0  mov     [rsp-38h+arg_8], rbx
0x18003e9d5  mov     [rsp-38h+arg_18], r9
0x18003e9da  mov     [rsp-38h+arg_10], r8
0x18003e9df  mov     [rsp-38h+arg_0], rcx
0x18003e9e4  push    rbp
0x18003e9e5  push    rsi
0x18003e9e6  push    rdi
0x18003e9e7  push    r12
0x18003e9e9  push    r13
0x18003e9eb  push    r14
0x18003e9ed  push    r15
0x18003e9ef  mov     rbp, rsp
0x18003e9f2  sub     rsp, 80h
0x18003e9f9  movaps  [rsp+80h+var_10], xmm6
0x18003e9fe  mov     r12, r8
0x18003ea01  mov     rbx, rdx
0x18003ea04  xorps   xmm6, xmm6
0x18003ea07  movups  xmmword ptr [rbp+sourceString], xmm6
0x18003ea0b  xor     r14d, r14d
0x18003ea0e  mov     [rbp+var_38], r14d
0x18003ea12  mov     [rbp+arg_0], r14
0x18003ea16  mov     rcx, [r8]
0x18003ea19  mov     rax, [rcx]
0x18003ea1c  lea     r8, [rbp+arg_0]
0x18003ea20  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003ea27  mov     rax, [rax]
0x18003ea2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea2f  mov     edi, eax
0x18003ea31  test    eax, eax
0x18003ea33  js      loc_18003EE77
0x18003ea39  xor     edx, edx; length
0x18003ea3b  mov     rcx, [rbx]; string
0x18003ea3e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ea44  mov     rsi, rax
0x18003ea47  mov     r15, [rbp+arg_0]
0x18003ea4b  xorps   xmm0, xmm0
0x18003ea4e  xor     eax, eax
0x18003ea50  movups  xmmword ptr [rbp+Src], xmm0
0x18003ea54  mov     [rbp+var_20], rax
0x18003ea58  mov     word ptr [rbp+Src], r14w
0x18003ea5d  mov     ebx, r14d
0x18003ea60  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18003ea67  mov     r13d, 80070216h
0x18003ea6d  test    r15, r15
0x18003ea70  jz      loc_18003EF03
0x18003ea76  test    rsi, rsi
0x18003ea79  jz      loc_18003EF03
0x18003ea7f  xor     ecx, ecx; bstrString
0x18003ea81  call    cs:__imp_SysFreeString
0x18003ea87  mov     [rbp+string], rbx
0x18003ea8b  mov     ecx, 7FFFFFFFh
0x18003ea90  mov     rax, rsi
0x18003ea93  cmp     [rax], bx
0x18003ea96  jz      short loc_18003EAA2
0x18003ea98  add     rax, 2
0x18003ea9c  sub     rcx, 1
0x18003eaa0  jnz     short loc_18003EA93
0x18003eaa2  xor     eax, eax
0x18003eaa4  mov     r14d, 80070057h
0x18003eaaa  test    rcx, rcx
0x18003eaad  cmovnz  r14d, eax
0x18003eab1  jz      short loc_18003EAE5
0x18003eab3  mov     edx, 7FFFFFFFh
0x18003eab8  sub     edx, ecx; ui
0x18003eaba  cmp     edx, 3FFFFFFFh
0x18003eac0  ja      loc_18003EFE5
0x18003eac6  mov     rcx, rsi; strIn
0x18003eac9  call    cs:__imp_SysAllocStringLen
0x18003eacf  mov     rbx, rax
0x18003ead2  mov     [rbp+string], rax
0x18003ead6  xor     r14d, r14d
0x18003ead9  test    rax, rax
0x18003eadc  mov     eax, 8007000Eh
0x18003eae1  cmovz   r14d, eax
0x18003eae5  mov     rcx, [rbp+38h]; this
0x18003eae9  test    r14d, r14d
0x18003eaec  js      loc_18003EECD
0x18003eaf2  mov     rax, [r15]
0x18003eaf5  lea     r8, [rbp+Src]
0x18003eaf9  mov     rdx, rbx
0x18003eafc  mov     rcx, r15
0x18003eaff  mov     rax, [rax+160h]
0x18003eb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb0b  mov     r14d, eax
0x18003eb0e  mov     rcx, [rbp+38h]; this
0x18003eb12  test    eax, eax
0x18003eb14  js      loc_18003EE2F
0x18003eb1a  mov     r12, [rbp+Src+8]
0x18003eb1e  mov     [rbp+string], r12
0x18003eb22  test    r12, r12
0x18003eb25  jz      loc_18003ECBA
0x18003eb2b  mov     ecx, 3FFFFFFEh
0x18003eb30  mov     edx, ecx
0x18003eb32  mov     rax, r12
0x18003eb35  cmp     word ptr [rax], 0
0x18003eb39  jz      short loc_18003EB45
0x18003eb3b  add     rax, 2
0x18003eb3f  sub     rdx, 1; unsigned __int64
0x18003eb43  jnz     short loc_18003EB35
0x18003eb45  xor     eax, eax
0x18003eb47  mov     r14d, 80070057h
0x18003eb4d  test    rdx, rdx
0x18003eb50  cmovnz  r14d, eax
0x18003eb54  sub     rcx, rdx
0x18003eb57  xor     r15d, r15d
0x18003eb5a  test    rdx, rdx
0x18003eb5d  cmovnz  r15, rcx
0x18003eb61  mov     rcx, [rbp+38h]; this
0x18003eb65  jz      loc_18003EFF0
0x18003eb6b  xor     r14d, r14d
0x18003eb6e  cmp     r15d, 7FFFFFFFh
0x18003eb75  cmova   r14d, r13d
0x18003eb79  mov     rcx, [rbp+38h]; this
0x18003eb7d  test    r14d, r14d
0x18003eb80  js      loc_18003F00D
0x18003eb86  test    r15d, r15d
0x18003eb89  jnz     loc_18003ECE6
0x18003eb8f  mov     rsi, [rbp+sourceString+8]
0x18003eb93  xor     eax, eax
0x18003eb95  cmp     r15d, eax
0x18003eb98  ja      loc_18003EF12
0x18003eb9e  mov     dword ptr [rbp+sourceString], r15d
0x18003eba2  test    r15d, r15d
0x18003eba5  jz      short loc_18003EBB0
0x18003eba7  mov     ecx, r15d
0x18003ebaa  xor     eax, eax
0x18003ebac  mov     [rsi+rcx*2], ax
0x18003ebb0  xor     r14d, r14d
0x18003ebb3  mov     rcx, [rbp+38h]; this
0x18003ebb7  test    r14d, r14d
0x18003ebba  js      loc_18003EE5E
0x18003ebc0  lea     r8d, [r15+r15]; Size
0x18003ebc4  mov     rdx, r12; Src
0x18003ebc7  mov     rcx, rsi; void *
0x18003ebca  call    memcpy_0
0x18003ebcf  xor     r14d, r14d
0x18003ebd2  mov     rcx, [rbp+38h]; this
0x18003ebd6  test    r14d, r14d
0x18003ebd9  js      loc_18003F09C
0x18003ebdf  mov     r12, [rbp+arg_10]
0x18003ebe3  mov     rcx, rbx; bstrString
0x18003ebe6  call    cs:__imp_SysFreeString
0x18003ebec  nop
0x18003ebed  lea     rcx, [rbp+Src]; pvarg
0x18003ebf1  call    cs:__imp_VariantClear
0x18003ebf7  test    r14d, r14d
0x18003ebfa  js      loc_18003EDAF
0x18003ec00  test    rsi, rsi
0x18003ec03  jz      loc_18003EF36
0x18003ec09  xor     ebx, ebx
0x18003ec0b  mov     [rbp+string], rbx
0x18003ec0f  nop
0x18003ec10  inc     rdi
0x18003ec13  cmp     [rsi+rdi*2], bx
0x18003ec17  jnz     short loc_18003EC10
0x18003ec19  mov     eax, 0FFFFFFFFh
0x18003ec1e  cmp     rdi, rax
0x18003ec21  ja      short loc_18003EC4D
0x18003ec23  mov     edx, edi; length
0x18003ec25  lea     r8, [rbp+string]; string
0x18003ec29  mov     rcx, rsi; sourceString
0x18003ec2c  call    cs:__imp_WindowsCreateString
0x18003ec32  mov     r13d, eax
0x18003ec35  test    eax, eax
0x18003ec37  js      short loc_18003EC4D
0x18003ec39  mov     rdx, [rbp+arg_18]
0x18003ec3d  mov     rcx, [rdx]; string
0x18003ec40  mov     rax, [rbp+string]
0x18003ec44  mov     [rdx], rax
0x18003ec47  call    cs:__imp_WindowsDeleteString
0x18003ec4d  test    r13d, r13d
0x18003ec50  js      loc_18003EF3C
0x18003ec56  mov     rcx, [rbp+arg_0]
0x18003ec5a  test    rcx, rcx
0x18003ec5d  jz      short loc_18003EC70
0x18003ec5f  mov     [rbp+arg_0], rbx
0x18003ec63  mov     rax, [rcx]
0x18003ec66  mov     rax, [rax+10h]
0x18003ec6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec6f  nop
0x18003ec70  test    rsi, rsi
0x18003ec73  jz      short loc_18003EC7E
0x18003ec75  mov     rcx, rsi; void *
0x18003ec78  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ec7d  nop
0x18003ec7e  mov     rcx, [r12]
0x18003ec82  test    rcx, rcx
0x18003ec85  jz      short loc_18003EC98
0x18003ec87  mov     [r12], rbx
0x18003ec8b  mov     rax, [rcx]
0x18003ec8e  mov     rax, [rax+10h]
0x18003ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec97  nop
0x18003ec98  xor     eax, eax
0x18003ec9a  mov     rbx, [rsp+80h+arg_8]
0x18003eca2  movaps  xmm6, [rsp+80h+var_10]
0x18003eca7  add     rsp, 80h
0x18003ecae  pop     r15
0x18003ecb0  pop     r14
0x18003ecb2  pop     r13
0x18003ecb4  pop     r12
0x18003ecb6  pop     rdi
0x18003ecb7  pop     rsi
0x18003ecb8  pop     rbp
0x18003ecb9  retn
0x18003ecba  movd    ecx, xmm6
0x18003ecbe  add     rcx, rcx
0x18003ecc1  psrldq  xmm6, 8
0x18003ecc6  movq    rsi, xmm6
0x18003eccb  mov     rax, rsi
0x18003ecce  jz      loc_18003EBDF
0x18003ecd4  mov     byte ptr [rax], 0
0x18003ecd7  lea     rax, [rax+1]
0x18003ecdb  sub     rcx, 1
0x18003ecdf  jnz     short loc_18003ECD4
0x18003ece1  jmp     loc_18003EBDF
0x18003ece6  cmp     r15d, 20h ; ' '
0x18003ecea  ja      short loc_18003ED01
0x18003ecec  mov     r14d, 8
0x18003ecf2  cmp     r15d, r14d
0x18003ecf5  jbe     short loc_18003ED04
0x18003ecf7  add     r14d, r14d
0x18003ecfa  cmp     r14d, r15d
0x18003ecfd  jb      short loc_18003ECF7
0x18003ecff  jmp     short loc_18003ED04
0x18003ed01  mov     r14d, r15d
0x18003ed04  cmp     r14d, 3FFFFFFFh
0x18003ed0b  ja      loc_18003EF92
0x18003ed11  test    r14d, r14d
0x18003ed14  jz      loc_18003F02A
0x18003ed1a  lea     r12d, [r14+1]
0x18003ed1e  test    r12d, r12d
0x18003ed21  jz      loc_18003EFBC
0x18003ed27  psrldq  xmm6, 8
0x18003ed2c  movq    rsi, xmm6
0x18003ed31  mov     ecx, r12d
0x18003ed34  mov     eax, 2
0x18003ed39  mul     rcx
0x18003ed3c  cmovb   rax, rdi
0x18003ed40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ed47  mov     rcx, rax; unsigned __int64
0x18003ed4a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003ed4f  mov     r13, rax
0x18003ed52  test    rax, rax
0x18003ed55  jz      loc_18003F054
0x18003ed5b  mov     rcx, rsi; void *
0x18003ed5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ed63  mov     rsi, r13
0x18003ed66  mov     r13d, 80070216h
0x18003ed6c  mov     edx, r12d
0x18003ed6f  mov     [rbp+var_38], edx
0x18003ed72  mov     [rbp+sourceString+8], rsi
0x18003ed76  mov     eax, dword ptr [rbp+sourceString]
0x18003ed79  cmp     eax, r14d
0x18003ed7c  ja      loc_18003EE4C
0x18003ed82  jnb     short loc_18003ED8B
0x18003ed84  test    eax, eax
0x18003ed86  jnz     short loc_18003ED8B
0x18003ed88  mov     [rsi], ax
0x18003ed8b  mov     r12, [rbp+string]
0x18003ed8f  xor     r14d, r14d
0x18003ed92  mov     rcx, [rbp+38h]; this
0x18003ed96  test    r14d, r14d
0x18003ed99  js      loc_18003EEEA
0x18003ed9f  test    edx, edx
0x18003eda1  jz      loc_18003EB93
0x18003eda7  lea     eax, [rdx-1]
0x18003edaa  jmp     loc_18003EB95
0x18003edaf  mov     rcx, [rbp+38h]; this
0x18003edb3  mov     dword ptr [rsp+80h+var_58], r14d; char *
0x18003edb8  lea     rax, aCommonXmlGetat_0; "Common::Xml::GetAttributeValueStringFro"...
0x18003edbf  mov     [rsp+80h+var_60], rax; char *
0x18003edc4  lea     r9, aOsintegrationD_273; "OSIntegration::DEH::Internal::Activatab"...
0x18003edcb  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003edd2  mov     edx, 34Dh; void *
0x18003edd7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003eddc  nop
0x18003eddd  mov     rcx, [rbp+arg_0]
0x18003ede1  test    rcx, rcx
0x18003ede4  jz      short loc_18003EDFB
0x18003ede6  mov     [rbp+arg_0], 0
0x18003edee  mov     rax, [rcx]
0x18003edf1  mov     rax, [rax+10h]
0x18003edf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edfa  nop
0x18003edfb  test    rsi, rsi
0x18003edfe  jz      short loc_18003EE09
0x18003ee00  mov     rcx, rsi; void *
0x18003ee03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ee08  nop
0x18003ee09  mov     rcx, [r12]
0x18003ee0d  test    rcx, rcx
0x18003ee10  jz      short loc_18003EE27
0x18003ee12  mov     qword ptr [r12], 0
0x18003ee1a  mov     rax, [rcx]
0x18003ee1d  mov     rax, [rax+10h]
0x18003ee21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee26  nop
0x18003ee27  mov     eax, r14d
0x18003ee2a  jmp     loc_18003EC9A
  ... truncated ...
```
