# ModernDeployment::Autopilot::Core::SignedJwt::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180164fb0`
- end: `0x18016561c`
- name: `?Initialize@SignedJwt@Core@Autopilot@ModernDeployment@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1644`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180149168`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x180084574`
- `0x18008aecc`
- `0x18008af70`
- `0x18008fe3c`
- `0x1800905dc`
- `0x180090810`
- `0x1801329e4`
- `0x180132c38`
- `0x18014878c`
- `0x180164fb0`
- `0x180165740`
- `0x180165acc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180165205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180165392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180165205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180165392`

## string_xrefs

- `0x180165009`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180165035`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x18016514b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x1801651a4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180165222`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x180165289`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x18016530b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x1801653af`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`
- `0x18016542f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\signedjwt.cpp`

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
0x180164fb0  mov     rax, rsp
0x180164fb3  mov     [rax+18h], rbx
0x180164fb7  mov     [rax+20h], rsi
0x180164fbb  push    rdi
0x180164fbc  push    r12
0x180164fbe  push    r13
0x180164fc0  push    r14
0x180164fc2  push    r15
0x180164fc4  sub     rsp, 1B0h
0x180164fcb  movaps  xmmword ptr [rax-38h], xmm6
0x180164fcf  mov     rax, cs:__security_cookie
0x180164fd6  xor     rax, rsp
0x180164fd9  mov     [rsp+1D8h+var_48], rax
0x180164fe1  mov     r14, rdx
0x180164fe4  mov     rbx, rcx
0x180164fe7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180164fee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180164ff3  xor     esi, esi
0x180164ff5  test    al, al
0x180164ff7  jnz     short loc_18016501F
0x180164ff9  mov     rcx, [rsp+1D8h]; this
0x180165001  mov     ebx, 80004001h
0x180165006  mov     r9d, ebx; char *
0x180165009  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165010  lea     edx, [rsi+2Ah]; void *
0x180165013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165018  mov     eax, ebx
0x18016501a  jmp     loc_1801655E9
0x18016501f  cmp     [r14+10h], rsi
0x180165023  jnz     short loc_18016504D
0x180165025  mov     rcx, [rsp+1D8h]; this
0x18016502d  mov     ebx, 80070057h
0x180165032  mov     r9d, ebx; char *
0x180165035  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016503c  mov     edx, 2Bh ; '+'; void *
0x180165041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165046  mov     eax, ebx
0x180165048  jmp     loc_1801655E9
0x18016504d  mov     [rbx], sil
0x180165050  lea     r13, [rbx+0F8h]
0x180165057  mov     [r13+10h], rsi
0x18016505b  mov     rcx, r13
0x18016505e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180165063  mov     [rax], si
0x180165066  lea     rax, [rbx+118h]
0x18016506d  mov     [rax+10h], rsi
0x180165071  mov     rcx, rax
0x180165074  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180165079  mov     [rax], si
0x18016507c  mov     [rbx+18h], rsi
0x180165080  lea     rcx, [rbx+8]
0x180165084  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180165089  mov     [rax], si
0x18016508c  xorps   xmm0, xmm0
0x18016508f  movups  [rsp+1D8h+var_188], xmm0
0x180165094  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18016509c  movdqa  [rsp+1D8h+var_178], xmm6
0x1801650a2  mov     word ptr [rsp+1D8h+var_188], si
0x1801650a7  movups  [rsp+1D8h+var_168], xmm0
0x1801650ac  movdqa  [rsp+1D8h+var_158], xmm6
0x1801650b5  mov     word ptr [rsp+1D8h+var_168], si
0x1801650ba  movups  [rsp+1D8h+var_148], xmm0
0x1801650c2  movdqa  [rsp+1D8h+var_138], xmm6
0x1801650cb  mov     word ptr [rsp+1D8h+var_148], si
0x1801650d3  movdqa  [rsp+1D8h+var_128], xmm0
0x1801650dc  xorps   xmm1, xmm1
0x1801650df  movdqa  [rsp+1D8h+var_118], xmm1
0x1801650e8  movdqa  [rsp+1D8h+var_108], xmm0
0x1801650f1  movdqa  [rsp+1D8h+var_F8], xmm1
0x1801650fa  mov     [rsp+1D8h+var_E8], rsi
0x180165102  lea     rdx, [rsp+1D8h+var_188]
0x180165107  lea     rcx, [rbx+28h]
0x18016510b  call    ??4JwtParts@JwtParser@Core@Autopilot@ModernDeployment@@QEAAAEAU01234@$$QEAU01234@@Z; ModernDeployment::Autopilot::Core::JwtParser::JwtParts::operator=(ModernDeployment::Autopilot::Core::JwtParser::JwtParts &&)
0x180165110  lea     rcx, [rsp+1D8h+var_188]; this
0x180165115  call    ??1JwtParts@JwtParser@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::JwtParser::JwtParts::~JwtParts(void)
0x18016511a  lea     r15, [rbx+0E0h]
0x180165121  mov     rax, [r15]
0x180165124  cmp     rax, [r15+8]
0x180165128  jz      short loc_18016512E
0x18016512a  mov     [r15+8], rax
0x18016512e  lea     r9, [rbx+28h]
0x180165132  mov     rdx, r14
0x180165135  call    ?ParseJwt@JwtParser@Core@Autopilot@ModernDeployment@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUValidationOptions@1234@AEAUJwtParts@1234@@Z; ModernDeployment::Autopilot::Core::JwtParser::ParseJwt(std::wstring const &,ModernDeployment::Autopilot::Core::JwtParser::ValidationOptions const *,ModernDeployment::Autopilot::Core::JwtParser::JwtParts &)
0x18016513a  mov     edi, eax
0x18016513c  test    eax, eax
0x18016513e  jns     short loc_180165163
0x180165140  mov     rcx, [rsp+1D8h]; this
0x180165148  mov     r9d, eax; char *
0x18016514b  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165152  mov     edx, 35h ; '5'; void *
0x180165157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016515c  mov     eax, edi
0x18016515e  jmp     loc_1801655E9
0x180165163  xorps   xmm0, xmm0
0x180165166  movups  [rsp+1D8h+var_C8], xmm0
0x18016516e  movdqu  xmmword ptr [rsp+1D8h+length], xmm6
0x180165177  mov     word ptr [rsp+1D8h+var_C8], si
0x18016517f  lea     rcx, [rbx+88h]
0x180165186  lea     rdx, [rsp+1D8h+var_C8]
0x18016518e  call    ModernDeployment__Autopilot__Core__Utf8BytesToWideString
0x180165193  mov     edi, eax
0x180165195  test    eax, eax
0x180165197  jns     short loc_1801651CA
0x180165199  mov     rcx, [rsp+1D8h]; this
0x1801651a1  mov     r9d, eax; char *
0x1801651a4  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801651ab  mov     edx, 39h ; '9'; void *
0x1801651b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801651b5  nop
0x1801651b6  lea     rcx, [rsp+1D8h+var_C8]
0x1801651be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801651c3  mov     eax, edi
0x1801651c5  jmp     loc_1801655E9
0x1801651ca  mov     qword ptr [rsp+1D8h+var_1B8], rsi; int
0x1801651cf  mov     [rsp+1D8h+string], rsi
0x1801651d7  xor     edx, edx
0x1801651d9  lea     rcx, [rsp+1D8h+string]
0x1801651e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801651e6  lea     rcx, [rsp+1D8h+var_C8]
0x1801651ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801651f3  mov     rcx, rax; sourceString
0x1801651f6  lea     r8, [rsp+1D8h+string]; string
0x1801651fe  mov     edx, [rsp+1D8h+length]; length
0x180165205  call    cs:__imp_WindowsCreateString
0x18016520c  nop     dword ptr [rax+rax+00h]
0x180165211  mov     edi, eax
0x180165213  test    eax, eax
0x180165215  jns     short loc_180165261
0x180165217  mov     rcx, [rsp+1D8h]; this
0x18016521f  mov     r9d, eax; char *
0x180165222  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165229  mov     edx, 3Ch ; '<'; void *
0x18016522e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165233  nop
0x180165234  lea     rcx, [rsp+1D8h+string]; this
0x18016523c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180165241  nop
0x180165242  lea     rcx, [rsp+1D8h+var_1B8]
0x180165247  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016524c  nop
0x18016524d  lea     rcx, [rsp+1D8h+var_C8]
0x180165255  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016525a  mov     eax, edi
0x18016525c  jmp     loc_1801655E9
0x180165261  lea     rsi, [rbx+0D0h]
0x180165268  mov     rdx, rsi
0x18016526b  lea     rcx, [rsp+1D8h+string]
0x180165273  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180165278  mov     edi, eax
0x18016527a  test    eax, eax
0x18016527c  jns     short loc_1801652C8
0x18016527e  mov     rcx, [rsp+1D8h]; this
0x180165286  mov     r9d, eax; char *
0x180165289  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165290  mov     edx, 3Dh ; '='; void *
0x180165295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016529a  nop
0x18016529b  lea     rcx, [rsp+1D8h+string]; this
0x1801652a3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801652a8  nop
0x1801652a9  lea     rcx, [rsp+1D8h+var_1B8]
0x1801652ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801652b3  nop
0x1801652b4  lea     rcx, [rsp+1D8h+var_C8]
0x1801652bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801652c1  mov     eax, edi
0x1801652c3  jmp     loc_1801655E9
0x1801652c8  xorps   xmm0, xmm0
0x1801652cb  movups  [rsp+1D8h+var_A8], xmm0
0x1801652d3  movdqu  xmmword ptr [rsp+1D8h+var_98], xmm6
0x1801652dc  xor     eax, eax
0x1801652de  mov     word ptr [rsp+1D8h+var_A8], ax
0x1801652e6  lea     rcx, [rbx+0A0h]
0x1801652ed  lea     rdx, [rsp+1D8h+var_A8]
0x1801652f5  call    ModernDeployment__Autopilot__Core__Utf8BytesToWideString
0x1801652fa  mov     edi, eax
0x1801652fc  test    eax, eax
0x1801652fe  jns     short loc_180165358
0x180165300  mov     rcx, [rsp+1D8h]; this
0x180165308  mov     r9d, eax; char *
0x18016530b  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165312  mov     edx, 40h ; '@'; void *
0x180165317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016531c  nop
0x18016531d  lea     rcx, [rsp+1D8h+var_A8]
0x180165325  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016532a  nop
0x18016532b  lea     rcx, [rsp+1D8h+string]; this
0x180165333  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180165338  nop
0x180165339  lea     rcx, [rsp+1D8h+var_1B8]
0x18016533e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165343  nop
0x180165344  lea     rcx, [rsp+1D8h+var_C8]
0x18016534c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180165351  mov     eax, edi
0x180165353  jmp     loc_1801655E9
0x180165358  mov     [rsp+1D8h+var_D0], 0
0x180165364  xor     edx, edx
0x180165366  lea     rcx, [rsp+1D8h+var_D0]
0x18016536e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180165373  lea     rcx, [rsp+1D8h+var_A8]
0x18016537b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180165380  mov     rcx, rax; sourceString
0x180165383  lea     r8, [rsp+1D8h+var_D0]; string
0x18016538b  mov     edx, [rsp+1D8h+var_98]; length
0x180165392  call    cs:__imp_WindowsCreateString
0x180165399  nop     dword ptr [rax+rax+00h]
0x18016539e  mov     edi, eax
0x1801653a0  test    eax, eax
0x1801653a2  jns     short loc_18016540A
0x1801653a4  mov     rcx, [rsp+1D8h]; this
0x1801653ac  mov     r9d, eax; char *
0x1801653af  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801653b6  mov     edx, 42h ; 'B'; void *
0x1801653bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801653c0  nop
0x1801653c1  lea     rcx, [rsp+1D8h+var_D0]; this
0x1801653c9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801653ce  nop
0x1801653cf  lea     rcx, [rsp+1D8h+var_A8]
0x1801653d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801653dc  nop
0x1801653dd  lea     rcx, [rsp+1D8h+string]; this
0x1801653e5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801653ea  nop
0x1801653eb  lea     rcx, [rsp+1D8h+var_1B8]
0x1801653f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801653f5  nop
0x1801653f6  lea     rcx, [rsp+1D8h+var_C8]
0x1801653fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180165403  mov     eax, edi
0x180165405  jmp     loc_1801655E9
0x18016540a  lea     rdx, [rbx+0D8h]
0x180165411  lea     rcx, [rsp+1D8h+var_D0]
0x180165419  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18016541e  mov     edi, eax
0x180165420  test    eax, eax
0x180165422  jns     short loc_18016548A
0x180165424  mov     rcx, [rsp+1D8h]; this
0x18016542c  mov     r9d, eax; char *
0x18016542f  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\moderndeployment\\au"...
0x180165436  mov     edx, 43h ; 'C'; void *
0x18016543b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165440  nop
0x180165441  lea     rcx, [rsp+1D8h+var_D0]; this
0x180165449  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18016544e  nop
0x18016544f  lea     rcx, [rsp+1D8h+var_A8]
0x180165457  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016545c  nop
0x18016545d  lea     rcx, [rsp+1D8h+string]; this
0x180165465  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18016546a  nop
0x18016546b  lea     rcx, [rsp+1D8h+var_1B8]
0x180165470  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165475  nop
0x180165476  lea     rcx, [rsp+1D8h+var_C8]
0x18016547e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180165483  mov     eax, edi
0x180165485  jmp     loc_1801655E9
0x18016548a  lea     rdx, [rbx+0B8h]
0x180165491  mov     rcx, r15
0x180165494  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180165499  xorps   xmm0, xmm0
0x18016549c  movups  [rsp+1D8h+var_68], xmm0
0x1801654a4  movdqu  [rsp+1D8h+var_58], xmm6
0x1801654ad  xor     eax, eax
0x1801654af  mov     word ptr [rsp+1D8h+var_68], ax
0x1801654b7  lea     rdx, aAlg_0; "alg"
0x1801654be  lea     rcx, [rsp+1D8h+var_1B0]
0x1801654c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801654c8  nop
0x1801654c9  lea     r8, [rsp+1D8h+var_68]
0x1801654d1  lea     rdx, [rsp+1D8h+var_1B0]
0x1801654d6  mov     rcx, [rsi]
0x1801654d9  call    ?TryGetNamedStringValue@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV89@@Z; Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(Windows::Data::Json::IJsonObject *,std::wstring const &,std::wstring &)
0x1801654de  mov     edi, eax
0x1801654e0  lea     rcx, [rsp+1D8h+var_1B0]
0x1801654e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801654ea  shr     edi, 1Fh
0x1801654ed  xor     dil, 1
0x1801654f1  jz      short loc_180165503
0x1801654f3  lea     rdx, [rsp+1D8h+var_68]
0x1801654fb  mov     rcx, r13
0x1801654fe  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180165503  xorps   xmm0, xmm0
0x180165506  movups  [rsp+1D8h+var_88], xmm0
0x18016550e  movdqu  [rsp+1D8h+var_78], xmm6
0x180165517  xor     eax, eax
0x180165519  mov     word ptr [rsp+1D8h+var_88], ax
0x180165521  lea     rdx, aKid; "kid"
0x180165528  lea     rcx, [rsp+1D8h+var_1B0]
0x18016552d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180165532  nop
0x180165533  lea     r8, [rsp+1D8h+var_88]
0x18016553b  lea     rdx, [rsp+1D8h+var_1B0]
0x180165540  mov     rcx, [rsi]
0x180165543  call    ?TryGetNamedStringValue@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV89@@Z; Microsoft::Windows::Autopilot::JsonHelpers::TryGetNamedStringValue(Windows::Data::Json::IJsonObject *,std::wstring const &,std::wstring &)
0x180165548  mov     edi, eax
  ... truncated ...
```
