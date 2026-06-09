# ModernDeployment::Autopilot::Core::SignedJwt::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180160bf8`
- end: `0x180161258`
- name: `?Initialize@SignedJwt@Core@Autopilot@ModernDeployment@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1632`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180145284`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x1800839bc`
- `0x18008a014`
- `0x18008a0a8`
- `0x18008ecf8`
- `0x18008f480`
- `0x18008f6a8`
- `0x18012ed40`
- `0x1801447c4`
- `0x1801448b8`
- `0x180160bf8`
- `0x180161378`
- `0x180161700`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180160e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180160fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180160e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180160fd4`

## string_xrefs

- `0x180160c51`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160c7d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160d93`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160dec`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160e64`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160ecb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160f4d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180160feb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x18016106b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::SignedJwt::Initialize(__int64 a1, __int64 a2)
{
  __m128i si128; // xmm6
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  const WCHAR *v13; // rax
  HRESULT v14; // eax
  unsigned int v15; // edi
  _QWORD *v16; // rsi
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  unsigned int v20; // edi
  const WCHAR *v21; // rax
  HRESULT v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  int NamedStringValue; // edi
  int v27; // edi
  int v28[2]; // [rsp+20h] [rbp-1B8h] BYREF
  _BYTE v29[40]; // [rsp+28h] [rbp-1B0h] BYREF
  _OWORD v30[2]; // [rsp+50h] [rbp-188h] BYREF
  __int128 v31; // [rsp+70h] [rbp-168h]
  __m128i v32; // [rsp+80h] [rbp-158h]
  __int128 v33; // [rsp+90h] [rbp-148h]
  __m128i v34; // [rsp+A0h] [rbp-138h]
  __int128 v35; // [rsp+B0h] [rbp-128h]
  __int128 v36; // [rsp+C0h] [rbp-118h]
  __int128 v37; // [rsp+D0h] [rbp-108h]
  __int128 v38; // [rsp+E0h] [rbp-F8h]
  __int64 v39; // [rsp+F0h] [rbp-E8h]
  HSTRING string; // [rsp+100h] [rbp-D8h] BYREF
  HSTRING v41; // [rsp+108h] [rbp-D0h] BYREF
  __int128 v42; // [rsp+110h] [rbp-C8h] BYREF
  UINT32 length[4]; // [rsp+120h] [rbp-B8h]
  __int128 v44; // [rsp+130h] [rbp-A8h] BYREF
  UINT32 v45[4]; // [rsp+140h] [rbp-98h]
  _OWORD v46[2]; // [rsp+150h] [rbp-88h] BYREF
  _OWORD v47[2]; // [rsp+170h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    if ( *(_QWORD *)(a2 + 16) )
    {
      *(_BYTE *)a1 = 0;
      *(_QWORD *)(a1 + 264) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 248) = 0;
      *(_QWORD *)(a1 + 296) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 280) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8) = 0;
      v30[0] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v30[1] = si128;
      LOWORD(v30[0]) = 0;
      v31 = 0;
      v32 = si128;
      LOWORD(v31) = 0;
      v33 = 0;
      v34 = si128;
      LOWORD(v33) = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      ModernDeployment::Autopilot::Core::JwtParser::JwtParts::operator=(a1 + 40, v30);
      ModernDeployment::Autopilot::Core::JwtParser::JwtParts::~JwtParts((ModernDeployment::Autopilot::Core::JwtParser::JwtParts *)v30);
      v8 = *(_QWORD *)(a1 + 224);
      if ( v8 != *(_QWORD *)(a1 + 232) )
        *(_QWORD *)(a1 + 232) = v8;
      v9 = ModernDeployment::Autopilot::Core::JwtParser::ParseJwt(v6, a2, v7, a1 + 40);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v42 = 0;
        *(__m128i *)length = si128;
        LOWORD(v42) = 0;
        v11 = ModernDeployment::Autopilot::Core::Utf8BytesToWideString(a1 + 136, &v42);
        v12 = v11;
        if ( v11 >= 0 )
        {
          *(_QWORD *)v28 = 0;
          string = 0;
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
            &string,
            0);
          v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v42);
          v14 = WindowsCreateString(v13, length[0], &string);
          v15 = v14;
          if ( v14 >= 0 )
          {
            v16 = (_QWORD *)(a1 + 208);
            v17 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&string, a1 + 208);
            v18 = v17;
            if ( v17 >= 0 )
            {
              v44 = 0;
              *(__m128i *)v45 = si128;
              LOWORD(v44) = 0;
              v19 = ModernDeployment::Autopilot::Core::Utf8BytesToWideString(a1 + 160, &v44);
              v20 = v19;
              if ( v19 >= 0 )
              {
                v41 = 0;
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                  &v41,
                  0);
                v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v44);
                v22 = WindowsCreateString(v21, v45[0], &v41);
                v23 = v22;
                if ( v22 >= 0 )
                {
                  v24 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&v41, a1 + 216);
                  v25 = v24;
                  if ( v24 >= 0 )
                  {
                    std::vector<unsigned char>::operator=(a1 + 224, a1 + 184);
                    v47[0] = 0;
                    v47[1] = si128;
                    LOWORD(v47[0]) = 0;
                    std::wstring::wstring(v29, L"alg");
                    NamedStringValue = Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(
                                         *v16,
                                         v29,
                                         v47);
                    std::wstring::_Tidy_deallocate(v29);
                    if ( NamedStringValue >= 0 )
                      std::wstring::operator=(a1 + 248, v47);
                    v46[0] = 0;
                    v46[1] = si128;
                    LOWORD(v46[0]) = 0;
                    std::wstring::wstring(v29, L"kid");
                    v27 = Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(*v16, v29, v46);
                    std::wstring::_Tidy_deallocate(v29);
                    if ( v27 >= 0 )
                      std::wstring::operator=(a1 + 280, v46);
                    std::wstring::operator=(a1 + 8, a2);
                    *(_BYTE *)a1 = 1;
                    std::wstring::_Tidy_deallocate(v46);
                    std::wstring::_Tidy_deallocate(v47);
                    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
                    std::wstring::_Tidy_deallocate(&v44);
                    Windows::Internal::String::~String((Windows::Internal::String *)&string);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
                    std::wstring::_Tidy_deallocate(&v42);
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x43,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
                      (const char *)(unsigned int)v24,
                      v28[0]);
                    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
                    std::wstring::_Tidy_deallocate(&v44);
                    Windows::Internal::String::~String((Windows::Internal::String *)&string);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
                    std::wstring::_Tidy_deallocate(&v42);
                    return v25;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x42,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
                    (const char *)(unsigned int)v22,
                    v28[0]);
                  Windows::Internal::String::~String((Windows::Internal::String *)&v41);
                  std::wstring::_Tidy_deallocate(&v44);
                  Windows::Internal::String::~String((Windows::Internal::String *)&string);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
                  std::wstring::_Tidy_deallocate(&v42);
                  return v23;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x40,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
                  (const char *)(unsigned int)v19,
                  v28[0]);
                std::wstring::_Tidy_deallocate(&v44);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
                std::wstring::_Tidy_deallocate(&v42);
                return v20;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3D,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
                (const char *)(unsigned int)v17,
                v28[0]);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
              std::wstring::_Tidy_deallocate(&v42);
              return v18;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
              (const char *)(unsigned int)v14,
              v28[0]);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
            std::wstring::_Tidy_deallocate(&v42);
            return v15;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x39,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
            (const char *)(unsigned int)v11,
            v28[0]);
          std::wstring::_Tidy_deallocate(&v42);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
          (const char *)(unsigned int)v9,
          v28[0]);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
        (const char *)0x80070057LL,
        v28[0]);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\signedjwt.cpp",
      (const char *)0x80004001LL,
      v28[0]);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180160bf8  mov     rax, rsp
0x180160bfb  mov     [rax+18h], rbx
0x180160bff  mov     [rax+20h], rsi
0x180160c03  push    rdi
0x180160c04  push    r12
0x180160c06  push    r13
0x180160c08  push    r14
0x180160c0a  push    r15
0x180160c0c  sub     rsp, 1B0h
0x180160c13  movaps  xmmword ptr [rax-38h], xmm6
0x180160c17  mov     rax, cs:__security_cookie
0x180160c1e  xor     rax, rsp
0x180160c21  mov     [rsp+1D8h+var_48], rax
0x180160c29  mov     r14, rdx
0x180160c2c  mov     rbx, rcx
0x180160c2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180160c36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180160c3b  xor     esi, esi
0x180160c3d  test    al, al
0x180160c3f  jnz     short loc_180160C67
0x180160c41  mov     rcx, [rsp+1D8h]; this
0x180160c49  mov     ebx, 80004001h
0x180160c4e  mov     r9d, ebx; char *
0x180160c51  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160c58  lea     edx, [rsi+2Ah]; void *
0x180160c5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160c60  mov     eax, ebx
0x180160c62  jmp     loc_180161225
0x180160c67  cmp     [r14+10h], rsi
0x180160c6b  jnz     short loc_180160C95
0x180160c6d  mov     rcx, [rsp+1D8h]; this
0x180160c75  mov     ebx, 80070057h
0x180160c7a  mov     r9d, ebx; char *
0x180160c7d  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160c84  mov     edx, 2Bh ; '+'; void *
0x180160c89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160c8e  mov     eax, ebx
0x180160c90  jmp     loc_180161225
0x180160c95  mov     [rbx], sil
0x180160c98  lea     r13, [rbx+0F8h]
0x180160c9f  mov     [r13+10h], rsi
0x180160ca3  mov     rcx, r13
0x180160ca6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180160cab  mov     [rax], si
0x180160cae  lea     rax, [rbx+118h]
0x180160cb5  mov     [rax+10h], rsi
0x180160cb9  mov     rcx, rax
0x180160cbc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180160cc1  mov     [rax], si
0x180160cc4  mov     [rbx+18h], rsi
0x180160cc8  lea     rcx, [rbx+8]
0x180160ccc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180160cd1  mov     [rax], si
0x180160cd4  xorps   xmm0, xmm0
0x180160cd7  movups  [rsp+1D8h+var_188], xmm0
0x180160cdc  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180160ce4  movdqa  [rsp+1D8h+var_178], xmm6
0x180160cea  mov     word ptr [rsp+1D8h+var_188], si
0x180160cef  movups  [rsp+1D8h+var_168], xmm0
0x180160cf4  movdqa  [rsp+1D8h+var_158], xmm6
0x180160cfd  mov     word ptr [rsp+1D8h+var_168], si
0x180160d02  movups  [rsp+1D8h+var_148], xmm0
0x180160d0a  movdqa  [rsp+1D8h+var_138], xmm6
0x180160d13  mov     word ptr [rsp+1D8h+var_148], si
0x180160d1b  movdqa  [rsp+1D8h+var_128], xmm0
0x180160d24  xorps   xmm1, xmm1
0x180160d27  movdqa  [rsp+1D8h+var_118], xmm1
0x180160d30  movdqa  [rsp+1D8h+var_108], xmm0
0x180160d39  movdqa  [rsp+1D8h+var_F8], xmm1
0x180160d42  mov     [rsp+1D8h+var_E8], rsi
0x180160d4a  lea     rdx, [rsp+1D8h+var_188]
0x180160d4f  lea     rcx, [rbx+28h]
0x180160d53  call    ??4JwtParts@JwtParser@Core@Autopilot@ModernDeployment@@QEAAAEAU01234@$$QEAU01234@@Z; ModernDeployment::Autopilot::Core::JwtParser::JwtParts::operator=(ModernDeployment::Autopilot::Core::JwtParser::JwtParts &&)
0x180160d58  lea     rcx, [rsp+1D8h+var_188]; this
0x180160d5d  call    ??1JwtParts@JwtParser@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::JwtParser::JwtParts::~JwtParts(void)
0x180160d62  lea     r15, [rbx+0E0h]
0x180160d69  mov     rax, [r15]
0x180160d6c  cmp     rax, [r15+8]
0x180160d70  jz      short loc_180160D76
0x180160d72  mov     [r15+8], rax
0x180160d76  lea     r9, [rbx+28h]
0x180160d7a  mov     rdx, r14
0x180160d7d  call    ?ParseJwt@JwtParser@Core@Autopilot@ModernDeployment@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUValidationOptions@1234@AEAUJwtParts@1234@@Z; ModernDeployment::Autopilot::Core::JwtParser::ParseJwt(std::wstring const &,ModernDeployment::Autopilot::Core::JwtParser::ValidationOptions const *,ModernDeployment::Autopilot::Core::JwtParser::JwtParts &)
0x180160d82  mov     edi, eax
0x180160d84  test    eax, eax
0x180160d86  jns     short loc_180160DAB
0x180160d88  mov     rcx, [rsp+1D8h]; this
0x180160d90  mov     r9d, eax; char *
0x180160d93  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160d9a  mov     edx, 35h ; '5'; void *
0x180160d9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160da4  mov     eax, edi
0x180160da6  jmp     loc_180161225
0x180160dab  xorps   xmm0, xmm0
0x180160dae  movups  [rsp+1D8h+var_C8], xmm0
0x180160db6  movdqu  xmmword ptr [rsp+1D8h+length], xmm6
0x180160dbf  mov     word ptr [rsp+1D8h+var_C8], si
0x180160dc7  lea     rcx, [rbx+88h]
0x180160dce  lea     rdx, [rsp+1D8h+var_C8]
0x180160dd6  call    ModernDeployment__Autopilot__Core__Utf8BytesToWideString
0x180160ddb  mov     edi, eax
0x180160ddd  test    eax, eax
0x180160ddf  jns     short loc_180160E12
0x180160de1  mov     rcx, [rsp+1D8h]; this
0x180160de9  mov     r9d, eax; char *
0x180160dec  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160df3  mov     edx, 39h ; '9'; void *
0x180160df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160dfd  nop
0x180160dfe  lea     rcx, [rsp+1D8h+var_C8]
0x180160e06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160e0b  mov     eax, edi
0x180160e0d  jmp     loc_180161225
0x180160e12  mov     qword ptr [rsp+1D8h+var_1B8], rsi; int
0x180160e17  mov     [rsp+1D8h+string], rsi
0x180160e1f  xor     edx, edx
0x180160e21  lea     rcx, [rsp+1D8h+string]
0x180160e29  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180160e2e  lea     rcx, [rsp+1D8h+var_C8]
0x180160e36  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180160e3b  mov     rcx, rax; sourceString
0x180160e3e  lea     r8, [rsp+1D8h+string]; string
0x180160e46  mov     edx, [rsp+1D8h+length]; length
0x180160e4d  call    cs:__imp_WindowsCreateString
0x180160e53  mov     edi, eax
0x180160e55  test    eax, eax
0x180160e57  jns     short loc_180160EA3
0x180160e59  mov     rcx, [rsp+1D8h]; this
0x180160e61  mov     r9d, eax; char *
0x180160e64  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160e6b  mov     edx, 3Ch ; '<'; void *
0x180160e70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160e75  nop
0x180160e76  lea     rcx, [rsp+1D8h+string]; this
0x180160e7e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180160e83  nop
0x180160e84  lea     rcx, [rsp+1D8h+var_1B8]
0x180160e89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180160e8e  nop
0x180160e8f  lea     rcx, [rsp+1D8h+var_C8]
0x180160e97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160e9c  mov     eax, edi
0x180160e9e  jmp     loc_180161225
0x180160ea3  lea     rsi, [rbx+0D0h]
0x180160eaa  mov     rdx, rsi
0x180160ead  lea     rcx, [rsp+1D8h+string]
0x180160eb5  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180160eba  mov     edi, eax
0x180160ebc  test    eax, eax
0x180160ebe  jns     short loc_180160F0A
0x180160ec0  mov     rcx, [rsp+1D8h]; this
0x180160ec8  mov     r9d, eax; char *
0x180160ecb  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160ed2  mov     edx, 3Dh ; '='; void *
0x180160ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160edc  nop
0x180160edd  lea     rcx, [rsp+1D8h+string]; this
0x180160ee5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180160eea  nop
0x180160eeb  lea     rcx, [rsp+1D8h+var_1B8]
0x180160ef0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180160ef5  nop
0x180160ef6  lea     rcx, [rsp+1D8h+var_C8]
0x180160efe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160f03  mov     eax, edi
0x180160f05  jmp     loc_180161225
0x180160f0a  xorps   xmm0, xmm0
0x180160f0d  movups  [rsp+1D8h+var_A8], xmm0
0x180160f15  movdqu  xmmword ptr [rsp+1D8h+var_98], xmm6
0x180160f1e  xor     eax, eax
0x180160f20  mov     word ptr [rsp+1D8h+var_A8], ax
0x180160f28  lea     rcx, [rbx+0A0h]
0x180160f2f  lea     rdx, [rsp+1D8h+var_A8]
0x180160f37  call    ModernDeployment__Autopilot__Core__Utf8BytesToWideString
0x180160f3c  mov     edi, eax
0x180160f3e  test    eax, eax
0x180160f40  jns     short loc_180160F9A
0x180160f42  mov     rcx, [rsp+1D8h]; this
0x180160f4a  mov     r9d, eax; char *
0x180160f4d  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160f54  mov     edx, 40h ; '@'; void *
0x180160f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160f5e  nop
0x180160f5f  lea     rcx, [rsp+1D8h+var_A8]
0x180160f67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160f6c  nop
0x180160f6d  lea     rcx, [rsp+1D8h+string]; this
0x180160f75  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180160f7a  nop
0x180160f7b  lea     rcx, [rsp+1D8h+var_1B8]
0x180160f80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180160f85  nop
0x180160f86  lea     rcx, [rsp+1D8h+var_C8]
0x180160f8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160f93  mov     eax, edi
0x180160f95  jmp     loc_180161225
0x180160f9a  mov     [rsp+1D8h+var_D0], 0
0x180160fa6  xor     edx, edx
0x180160fa8  lea     rcx, [rsp+1D8h+var_D0]
0x180160fb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180160fb5  lea     rcx, [rsp+1D8h+var_A8]
0x180160fbd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180160fc2  mov     rcx, rax; sourceString
0x180160fc5  lea     r8, [rsp+1D8h+var_D0]; string
0x180160fcd  mov     edx, [rsp+1D8h+var_98]; length
0x180160fd4  call    cs:__imp_WindowsCreateString
0x180160fda  mov     edi, eax
0x180160fdc  test    eax, eax
0x180160fde  jns     short loc_180161046
0x180160fe0  mov     rcx, [rsp+1D8h]; this
0x180160fe8  mov     r9d, eax; char *
0x180160feb  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160ff2  mov     edx, 42h ; 'B'; void *
0x180160ff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160ffc  nop
0x180160ffd  lea     rcx, [rsp+1D8h+var_D0]; this
0x180161005  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18016100a  nop
0x18016100b  lea     rcx, [rsp+1D8h+var_A8]
0x180161013  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180161018  nop
0x180161019  lea     rcx, [rsp+1D8h+string]; this
0x180161021  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180161026  nop
0x180161027  lea     rcx, [rsp+1D8h+var_1B8]
0x18016102c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161031  nop
0x180161032  lea     rcx, [rsp+1D8h+var_C8]
0x18016103a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016103f  mov     eax, edi
0x180161041  jmp     loc_180161225
0x180161046  lea     rdx, [rbx+0D8h]
0x18016104d  lea     rcx, [rsp+1D8h+var_D0]
0x180161055  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18016105a  mov     edi, eax
0x18016105c  test    eax, eax
0x18016105e  jns     short loc_1801610C6
0x180161060  mov     rcx, [rsp+1D8h]; this
0x180161068  mov     r9d, eax; char *
0x18016106b  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180161072  mov     edx, 43h ; 'C'; void *
0x180161077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016107c  nop
0x18016107d  lea     rcx, [rsp+1D8h+var_D0]; this
0x180161085  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18016108a  nop
0x18016108b  lea     rcx, [rsp+1D8h+var_A8]
0x180161093  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180161098  nop
0x180161099  lea     rcx, [rsp+1D8h+string]; this
0x1801610a1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801610a6  nop
0x1801610a7  lea     rcx, [rsp+1D8h+var_1B8]
0x1801610ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801610b1  nop
0x1801610b2  lea     rcx, [rsp+1D8h+var_C8]
0x1801610ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801610bf  mov     eax, edi
0x1801610c1  jmp     loc_180161225
0x1801610c6  lea     rdx, [rbx+0B8h]
0x1801610cd  mov     rcx, r15
0x1801610d0  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1801610d5  xorps   xmm0, xmm0
0x1801610d8  movups  [rsp+1D8h+var_68], xmm0
0x1801610e0  movdqu  [rsp+1D8h+var_58], xmm6
0x1801610e9  xor     eax, eax
0x1801610eb  mov     word ptr [rsp+1D8h+var_68], ax
0x1801610f3  lea     rdx, aAlg_0; "alg"
0x1801610fa  lea     rcx, [rsp+1D8h+var_1B0]
0x1801610ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180161104  nop
0x180161105  lea     r8, [rsp+1D8h+var_68]
0x18016110d  lea     rdx, [rsp+1D8h+var_1B0]
0x180161112  mov     rcx, [rsi]
0x180161115  call    ?TryGetNamedStringValue@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV89@@Z; Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(Windows::Data::Json::IJsonObject *,std::wstring const &,std::wstring &)
0x18016111a  mov     edi, eax
0x18016111c  lea     rcx, [rsp+1D8h+var_1B0]
0x180161121  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180161126  shr     edi, 1Fh
0x180161129  xor     dil, 1
0x18016112d  jz      short loc_18016113F
0x18016112f  lea     rdx, [rsp+1D8h+var_68]
0x180161137  mov     rcx, r13
0x18016113a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18016113f  xorps   xmm0, xmm0
0x180161142  movups  [rsp+1D8h+var_88], xmm0
0x18016114a  movdqu  [rsp+1D8h+var_78], xmm6
0x180161153  xor     eax, eax
0x180161155  mov     word ptr [rsp+1D8h+var_88], ax
0x18016115d  lea     rdx, aKid; "kid"
0x180161164  lea     rcx, [rsp+1D8h+var_1B0]
0x180161169  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18016116e  nop
0x18016116f  lea     r8, [rsp+1D8h+var_88]
0x180161177  lea     rdx, [rsp+1D8h+var_1B0]
0x18016117c  mov     rcx, [rsi]
0x18016117f  call    ?TryGetNamedStringValue@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV89@@Z; Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(Windows::Data::Json::IJsonObject *,std::wstring const &,std::wstring &)
0x180161184  mov     edi, eax
0x180161186  lea     rcx, [rsp+1D8h+var_1B0]
0x18016118b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
