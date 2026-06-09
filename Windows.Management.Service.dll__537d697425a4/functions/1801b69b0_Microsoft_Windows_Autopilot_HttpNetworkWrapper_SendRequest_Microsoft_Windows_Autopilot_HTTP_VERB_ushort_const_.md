# Microsoft::Windows::Autopilot::HttpNetworkWrapper::SendRequest(Microsoft::Windows::Autopilot::HTTP_VERB,ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,_CERT_CONTEXT const *,_WINHTTP_URL_COMPONENTS const &,char const *,ulong)

- ea: `0x1801b69b0`
- end: `0x1801b6c7b`
- name: `?SendRequest@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJW4HTTP_VERB@234@PEBGPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBU_CERT_CONTEXT@@AEBU_WINHTTP_URL_COMPONENTS@@PEBDK@Z`
- size: `715`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::HttpNetworkWrapper *this@<rcx>, LPVOID lpBuffer, __int64, __int64, DWORD dwOptionalLength)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b6c90`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x18008bf28`
- `0x18008d290`
- `0x1801a0e1c`
- `0x1801a54e0`
- `0x1801b5838`
- `0x1801b590c`
- `0x1801b69b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6c0f`
- `WINHTTP!WinHttpOpenRequest` at `0x1801b6ae2`
- `WINHTTP!WinHttpOpenRequest` at `0x1801b6ae2`
- `WINHTTP!WinHttpSendRequest` at `0x1801b6bff`
- `WINHTTP!WinHttpSendRequest` at `0x1801b6bff`
- `WINHTTP!WinHttpSetOption` at `0x1801b6b2b`
- `WINHTTP!WinHttpSetOption` at `0x1801b6b63`
- `WINHTTP!WinHttpSetOption` at `0x1801b6b2b`
- `WINHTTP!WinHttpSetOption` at `0x1801b6b63`

## string_xrefs

- `0x1801b6a13`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b6a4f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::HttpNetworkWrapper::SendRequest(
        HINTERNET *this,
        int a2,
        const WCHAR *a3,
        __int64 a4,
        LPVOID lpBuffer,
        __int64 a6,
        void *a7,
        DWORD dwOptionalLength)
{
  unsigned int v12; // ebx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  const wchar_t *v15; // rdx
  HINTERNET *v16; // r14
  const WCHAR *v17; // rax
  HINTERNET v18; // rax
  const char *v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  const unsigned __int16 *v22; // rax
  signed int LastError; // eax
  int pwszReferrer; // [rsp+20h] [rbp-60h]
  __int64 Buffer; // [rsp+40h] [rbp-40h] BYREF
  DWORD_PTR dwContext; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpOptional; // [rsp+50h] [rbp-30h]
  _OWORD v29[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  Buffer = a6;
  lpOptional = a7;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v29[0] = 0;
    v29[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v29[0]) = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      v12 = -2147467263;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
        (const char *)0x80004001LL,
        pwszReferrer);
LABEL_8:
      v13 = v12;
      v14 = 235;
      goto LABEL_24;
    }
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        v12 = -2147467259;
        goto LABEL_8;
      }
      v15 = L"POST";
    }
    else
    {
      v15 = L"GET";
    }
    std::wstring::assign(v29, v15);
    v16 = this + 3;
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v18 = WinHttpOpenRequest(this[2], v17, *(LPCWSTR *)(Buffer + 72), a3, 0, 0, 0x800000u);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      this + 3,
      v18);
    if ( this[3] )
    {
      if ( !lpBuffer || WinHttpSetOption(this[3], 0x2Fu, lpBuffer, 0x28u) )
      {
        if ( !Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::IsDogfoodEnvironment()
          || (LODWORD(Buffer) = 12544, WinHttpSetOption(*v16, 0x1Fu, &Buffer, 4u)) )
        {
          if ( a4
            && (v21 = Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddAllHeaders((Microsoft::Windows::Autopilot::HttpNetworkWrapper *)this),
                v12 = v21,
                v21 < 0) )
          {
            v14 = 275;
          }
          else
          {
            if ( !this[6]
              || (v22 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 4),
                  v21 = Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddHeaderToRequest(
                          (Microsoft::Windows::Autopilot::HttpNetworkWrapper *)this,
                          L"MS-CV",
                          v22),
                  v12 = v21,
                  v21 >= 0) )
            {
              LODWORD(dwContext) = 0;
              if ( WinHttpSendRequest(*v16, 0, 0, lpOptional, dwOptionalLength, dwOptionalLength, (DWORD_PTR)&dwContext) )
              {
                v12 = 0;
                goto LABEL_35;
              }
              LastError = GetLastError();
              v12 = LastError;
              if ( LastError > 0 )
                v12 = (unsigned __int16)LastError | 0x80070000;
              if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v12)
                || (v12 & 0x80000000) == 0 )
              {
                goto LABEL_35;
              }
              v13 = v12;
              v14 = 295;
              goto LABEL_24;
            }
            v14 = 280;
          }
          v13 = (unsigned int)v21;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
            (const char *)v13,
            pwszReferrer);
          goto LABEL_35;
        }
        v20 = 270;
      }
      else
      {
        v20 = 254;
      }
    }
    else
    {
      v20 = 245;
    }
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
            v19);
LABEL_35:
    std::wstring::_Tidy_deallocate(v29);
    return v12;
  }
  v12 = -2147467263;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE7,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
    (const char *)0x80004001LL,
    pwszReferrer);
  return v12;
}

```

## disassembly

```asm
0x1801b69b0  mov     [rsp-38h+arg_8], rbx
0x1801b69b5  push    rbp
0x1801b69b6  push    rsi
0x1801b69b7  push    rdi
0x1801b69b8  push    r12
0x1801b69ba  push    r13
0x1801b69bc  push    r14
0x1801b69be  push    r15
0x1801b69c0  mov     rbp, rsp
0x1801b69c3  sub     rsp, 80h
0x1801b69ca  mov     rax, cs:__security_cookie
0x1801b69d1  xor     rax, rsp
0x1801b69d4  mov     [rbp+var_8], rax
0x1801b69d8  mov     r12, r9
0x1801b69db  mov     r13, r8
0x1801b69de  mov     ebx, edx
0x1801b69e0  mov     rsi, rcx
0x1801b69e3  mov     r15, [rbp+lpBuffer]
0x1801b69e7  mov     rax, [rbp+arg_28]
0x1801b69eb  mov     [rbp+Buffer], rax
0x1801b69ef  mov     rax, [rbp+arg_30]
0x1801b69f3  mov     [rbp+lpOptional], rax
0x1801b69f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b69fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b6a03  test    al, al
0x1801b6a05  jnz     short loc_1801B6A29
0x1801b6a07  mov     rcx, [rbp+38h]; this
0x1801b6a0b  mov     ebx, 80004001h
0x1801b6a10  mov     r9d, ebx; char *
0x1801b6a13  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b6a1a  mov     edx, 0E7h; void *
0x1801b6a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b6a24  jmp     loc_1801B6C51
0x1801b6a29  xorps   xmm0, xmm0
0x1801b6a2c  movups  [rbp+var_28], xmm0
0x1801b6a30  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801b6a38  movdqu  [rbp+var_18], xmm1
0x1801b6a3d  xor     eax, eax
0x1801b6a3f  mov     word ptr [rbp+var_28], ax
0x1801b6a43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b6a4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b6a4f  lea     rdi, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b6a56  test    al, al
0x1801b6a58  jnz     short loc_1801B6A75
0x1801b6a5a  mov     rcx, [rbp+38h]; this
0x1801b6a5e  mov     ebx, 80004001h
0x1801b6a63  mov     r9d, ebx; char *
0x1801b6a66  mov     r8, rdi; unsigned int
0x1801b6a69  mov     edx, 13Ch; void *
0x1801b6a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b6a73  jmp     short loc_1801B6A83
0x1801b6a75  test    ebx, ebx
0x1801b6a77  jz      short loc_1801B6A99
0x1801b6a79  cmp     ebx, 1
0x1801b6a7c  jz      short loc_1801B6A90
0x1801b6a7e  mov     ebx, 80004005h
0x1801b6a83  mov     r9d, ebx
0x1801b6a86  mov     edx, 0EBh
0x1801b6a8b  jmp     loc_1801B6B98
0x1801b6a90  lea     rdx, aPost; "POST"
0x1801b6a97  jmp     short loc_1801B6AA0
0x1801b6a99  lea     rdx, pwszVerb; "GET"
0x1801b6aa0  lea     rcx, [rbp+var_28]
0x1801b6aa4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b6aa9  lea     r14, [rsi+18h]
0x1801b6aad  lea     rcx, [rbp+var_28]
0x1801b6ab1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b6ab6  mov     rdx, rax; pwszVerb
0x1801b6ab9  mov     [rsp+80h+dwFlags], 800000h; dwFlags
0x1801b6ac1  mov     [rsp+80h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1801b6aca  mov     [rsp+80h+pwszReferrer], 0; int
0x1801b6ad3  mov     r9, r13; pwszVersion
0x1801b6ad6  mov     r8, [rbp+Buffer]
0x1801b6ada  mov     r8, [r8+48h]; pwszObjectName
0x1801b6ade  mov     rcx, [rsi+10h]; hConnect
0x1801b6ae2  call    cs:__imp_WinHttpOpenRequest
0x1801b6ae9  nop     dword ptr [rax+rax+00h]
0x1801b6aee  mov     rdx, rax
0x1801b6af1  mov     rcx, r14
0x1801b6af4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801b6af9  mov     rcx, [r14]; hInternet
0x1801b6afc  test    rcx, rcx
0x1801b6aff  jnz     short loc_1801B6B19
0x1801b6b01  mov     edx, 0F5h; void *
0x1801b6b06  mov     rcx, [rbp+38h]; this
0x1801b6b0a  mov     r8, rdi; unsigned int
0x1801b6b0d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b6b12  mov     ebx, eax
0x1801b6b14  jmp     loc_1801B6C48
0x1801b6b19  test    r15, r15
0x1801b6b1c  jz      short loc_1801B6B42
0x1801b6b1e  mov     r9d, 28h ; '('; dwBufferLength
0x1801b6b24  mov     r8, r15; lpBuffer
0x1801b6b27  lea     edx, [r9+7]; dwOption
0x1801b6b2b  call    cs:__imp_WinHttpSetOption
0x1801b6b32  nop     dword ptr [rax+rax+00h]
0x1801b6b37  test    eax, eax
0x1801b6b39  jnz     short loc_1801B6B42
0x1801b6b3b  mov     edx, 0FEh
0x1801b6b40  jmp     short loc_1801B6B06
0x1801b6b42  call    ?IsDogfoodEnvironment@DeviceLinkPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::IsDogfoodEnvironment(void)
0x1801b6b47  test    al, al
0x1801b6b49  jz      short loc_1801B6B7A
0x1801b6b4b  mov     dword ptr [rbp+Buffer], 3100h
0x1801b6b52  mov     r9d, 4; dwBufferLength
0x1801b6b58  lea     r8, [rbp+Buffer]; lpBuffer
0x1801b6b5c  lea     edx, [r9+1Bh]; dwOption
0x1801b6b60  mov     rcx, [r14]; hInternet
0x1801b6b63  call    cs:__imp_WinHttpSetOption
0x1801b6b6a  nop     dword ptr [rax+rax+00h]
0x1801b6b6f  test    eax, eax
0x1801b6b71  jnz     short loc_1801B6B7A
0x1801b6b73  mov     edx, 10Eh
0x1801b6b78  jmp     short loc_1801B6B06
0x1801b6b7a  test    r12, r12
0x1801b6b7d  jz      short loc_1801B6BA9
0x1801b6b7f  mov     rdx, r12
0x1801b6b82  mov     rcx, rsi
0x1801b6b85  call    ?AddAllHeaders@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddAllHeaders(std::map<std::wstring,std::wstring> const *)
0x1801b6b8a  mov     ebx, eax
0x1801b6b8c  test    eax, eax
0x1801b6b8e  jns     short loc_1801B6BA9
0x1801b6b90  mov     edx, 113h; void *
0x1801b6b95  mov     r9d, eax; char *
0x1801b6b98  mov     r8, rdi; unsigned int
0x1801b6b9b  mov     rcx, [rbp+38h]; this
0x1801b6b9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b6ba4  jmp     loc_1801B6C48
0x1801b6ba9  lea     rcx, [rsi+20h]
0x1801b6bad  cmp     qword ptr [rcx+10h], 0
0x1801b6bb2  jz      short loc_1801B6BD8
0x1801b6bb4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b6bb9  mov     r8, rax; unsigned __int16 *
0x1801b6bbc  lea     rdx, aMsCv; "MS-CV"
0x1801b6bc3  mov     rcx, rsi; this
0x1801b6bc6  call    ?AddHeaderToRequest@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801b6bcb  mov     ebx, eax
0x1801b6bcd  test    eax, eax
0x1801b6bcf  jns     short loc_1801B6BD8
0x1801b6bd1  mov     edx, 118h
0x1801b6bd6  jmp     short loc_1801B6B95
0x1801b6bd8  mov     dword ptr [rbp+dwContext], 0
0x1801b6bdf  lea     rax, [rbp+dwContext]
0x1801b6be3  mov     qword ptr [rsp+80h+dwFlags], rax; dwContext
0x1801b6be8  mov     eax, [rbp+dwOptionalLength]
0x1801b6beb  mov     dword ptr [rsp+80h+ppwszAcceptTypes], eax; dwTotalLength
0x1801b6bef  mov     dword ptr [rsp+80h+pwszReferrer], eax; dwOptionalLength
0x1801b6bf3  mov     r9, [rbp+lpOptional]; lpOptional
0x1801b6bf7  xor     r8d, r8d; dwHeadersLength
0x1801b6bfa  xor     edx, edx; lpszHeaders
0x1801b6bfc  mov     rcx, [r14]; hRequest
0x1801b6bff  call    cs:__imp_WinHttpSendRequest
0x1801b6c06  nop     dword ptr [rax+rax+00h]
0x1801b6c0b  test    eax, eax
0x1801b6c0d  jnz     short loc_1801B6C46
0x1801b6c0f  call    cs:__imp_GetLastError
0x1801b6c16  nop     dword ptr [rax+rax+00h]
0x1801b6c1b  mov     ebx, eax
0x1801b6c1d  test    eax, eax
0x1801b6c1f  jle     short loc_1801B6C2A
0x1801b6c21  movzx   ebx, ax
0x1801b6c24  or      ebx, 80070000h
0x1801b6c2a  mov     ecx, ebx; int
0x1801b6c2c  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x1801b6c31  test    al, al
0x1801b6c33  jnz     short loc_1801B6C48
0x1801b6c35  test    ebx, ebx
0x1801b6c37  jns     short loc_1801B6C48
0x1801b6c39  mov     r9d, ebx
0x1801b6c3c  mov     edx, 127h
0x1801b6c41  jmp     loc_1801B6B98
0x1801b6c46  xor     ebx, ebx
0x1801b6c48  lea     rcx, [rbp+var_28]
0x1801b6c4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b6c51  mov     eax, ebx
0x1801b6c53  mov     rcx, [rbp+var_8]
0x1801b6c57  xor     rcx, rsp; StackCookie
0x1801b6c5a  call    __security_check_cookie
0x1801b6c5f  mov     rbx, [rsp+80h+arg_8]
0x1801b6c67  add     rsp, 80h
0x1801b6c6e  pop     r15
0x1801b6c70  pop     r14
0x1801b6c72  pop     r13
0x1801b6c74  pop     r12
0x1801b6c76  pop     rdi
0x1801b6c77  pop     rsi
0x1801b6c78  pop     rbp
0x1801b6c79  retn
```
