# Microsoft::Windows::Autopilot::HttpNetworkWrapper::SendRequest(Microsoft::Windows::Autopilot::HTTP_VERB,ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,_CERT_CONTEXT const *,_WINHTTP_URL_COMPONENTS const &,char const *,ulong)

- ea: `0x1801b0ff0`
- end: `0x1801b129c`
- name: `?SendRequest@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJW4HTTP_VERB@234@PEBGPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBU_CERT_CONTEXT@@AEBU_WINHTTP_URL_COMPONENTS@@PEBDK@Z`
- size: `684`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::HttpNetworkWrapper *this@<rcx>, LPVOID lpBuffer, __int64, __int64, DWORD dwOptionalLength)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b12b0`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x18008afec`
- `0x18008c244`
- `0x18019ba78`
- `0x1801a0048`
- `0x1801aff14`
- `0x1801affe8`
- `0x1801b0ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1237`
- `WINHTTP!WinHttpOpenRequest` at `0x1801b1122`
- `WINHTTP!WinHttpOpenRequest` at `0x1801b1122`
- `WINHTTP!WinHttpSendRequest` at `0x1801b122d`
- `WINHTTP!WinHttpSendRequest` at `0x1801b122d`
- `WINHTTP!WinHttpSetOption` at `0x1801b1165`
- `WINHTTP!WinHttpSetOption` at `0x1801b1197`
- `WINHTTP!WinHttpSetOption` at `0x1801b1165`
- `WINHTTP!WinHttpSetOption` at `0x1801b1197`

## string_xrefs

- `0x1801b1053`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b108f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

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
0x1801b0ff0  mov     [rsp-38h+arg_8], rbx
0x1801b0ff5  push    rbp
0x1801b0ff6  push    rsi
0x1801b0ff7  push    rdi
0x1801b0ff8  push    r12
0x1801b0ffa  push    r13
0x1801b0ffc  push    r14
0x1801b0ffe  push    r15
0x1801b1000  mov     rbp, rsp
0x1801b1003  sub     rsp, 80h
0x1801b100a  mov     rax, cs:__security_cookie
0x1801b1011  xor     rax, rsp
0x1801b1014  mov     [rbp+var_8], rax
0x1801b1018  mov     r12, r9
0x1801b101b  mov     r13, r8
0x1801b101e  mov     ebx, edx
0x1801b1020  mov     rsi, rcx
0x1801b1023  mov     r15, [rbp+lpBuffer]
0x1801b1027  mov     rax, [rbp+arg_28]
0x1801b102b  mov     [rbp+Buffer], rax
0x1801b102f  mov     rax, [rbp+arg_30]
0x1801b1033  mov     [rbp+lpOptional], rax
0x1801b1037  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b103e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b1043  test    al, al
0x1801b1045  jnz     short loc_1801B1069
0x1801b1047  mov     rcx, [rbp+38h]; this
0x1801b104b  mov     ebx, 80004001h
0x1801b1050  mov     r9d, ebx; char *
0x1801b1053  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b105a  mov     edx, 0E7h; void *
0x1801b105f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b1064  jmp     loc_1801B1273
0x1801b1069  xorps   xmm0, xmm0
0x1801b106c  movups  [rbp+var_28], xmm0
0x1801b1070  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801b1078  movdqu  [rbp+var_18], xmm1
0x1801b107d  xor     eax, eax
0x1801b107f  mov     word ptr [rbp+var_28], ax
0x1801b1083  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b108a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b108f  lea     rdi, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b1096  test    al, al
0x1801b1098  jnz     short loc_1801B10B5
0x1801b109a  mov     rcx, [rbp+38h]; this
0x1801b109e  mov     ebx, 80004001h
0x1801b10a3  mov     r9d, ebx; char *
0x1801b10a6  mov     r8, rdi; unsigned int
0x1801b10a9  mov     edx, 13Ch; void *
0x1801b10ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b10b3  jmp     short loc_1801B10C3
0x1801b10b5  test    ebx, ebx
0x1801b10b7  jz      short loc_1801B10D9
0x1801b10b9  cmp     ebx, 1
0x1801b10bc  jz      short loc_1801B10D0
0x1801b10be  mov     ebx, 80004005h
0x1801b10c3  mov     r9d, ebx
0x1801b10c6  mov     edx, 0EBh
0x1801b10cb  jmp     loc_1801B11C6
0x1801b10d0  lea     rdx, aPost; "POST"
0x1801b10d7  jmp     short loc_1801B10E0
0x1801b10d9  lea     rdx, pwszVerb; "GET"
0x1801b10e0  lea     rcx, [rbp+var_28]
0x1801b10e4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b10e9  lea     r14, [rsi+18h]
0x1801b10ed  lea     rcx, [rbp+var_28]
0x1801b10f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b10f6  mov     rdx, rax; pwszVerb
0x1801b10f9  mov     [rsp+80h+dwFlags], 800000h; dwFlags
0x1801b1101  mov     [rsp+80h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1801b110a  mov     [rsp+80h+pwszReferrer], 0; int
0x1801b1113  mov     r9, r13; pwszVersion
0x1801b1116  mov     r8, [rbp+Buffer]
0x1801b111a  mov     r8, [r8+48h]; pwszObjectName
0x1801b111e  mov     rcx, [rsi+10h]; hConnect
0x1801b1122  call    cs:__imp_WinHttpOpenRequest
0x1801b1128  mov     rdx, rax
0x1801b112b  mov     rcx, r14
0x1801b112e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801b1133  mov     rcx, [r14]; hInternet
0x1801b1136  test    rcx, rcx
0x1801b1139  jnz     short loc_1801B1153
0x1801b113b  mov     edx, 0F5h; void *
0x1801b1140  mov     rcx, [rbp+38h]; this
0x1801b1144  mov     r8, rdi; unsigned int
0x1801b1147  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b114c  mov     ebx, eax
0x1801b114e  jmp     loc_1801B126A
0x1801b1153  test    r15, r15
0x1801b1156  jz      short loc_1801B1176
0x1801b1158  mov     r9d, 28h ; '('; dwBufferLength
0x1801b115e  mov     r8, r15; lpBuffer
0x1801b1161  lea     edx, [r9+7]; dwOption
0x1801b1165  call    cs:__imp_WinHttpSetOption
0x1801b116b  test    eax, eax
0x1801b116d  jnz     short loc_1801B1176
0x1801b116f  mov     edx, 0FEh
0x1801b1174  jmp     short loc_1801B1140
0x1801b1176  call    ?IsDogfoodEnvironment@DeviceLinkPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::IsDogfoodEnvironment(void)
0x1801b117b  test    al, al
0x1801b117d  jz      short loc_1801B11A8
0x1801b117f  mov     dword ptr [rbp+Buffer], 3100h
0x1801b1186  mov     r9d, 4; dwBufferLength
0x1801b118c  lea     r8, [rbp+Buffer]; lpBuffer
0x1801b1190  lea     edx, [r9+1Bh]; dwOption
0x1801b1194  mov     rcx, [r14]; hInternet
0x1801b1197  call    cs:__imp_WinHttpSetOption
0x1801b119d  test    eax, eax
0x1801b119f  jnz     short loc_1801B11A8
0x1801b11a1  mov     edx, 10Eh
0x1801b11a6  jmp     short loc_1801B1140
0x1801b11a8  test    r12, r12
0x1801b11ab  jz      short loc_1801B11D7
0x1801b11ad  mov     rdx, r12
0x1801b11b0  mov     rcx, rsi
0x1801b11b3  call    ?AddAllHeaders@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddAllHeaders(std::map<std::wstring,std::wstring> const *)
0x1801b11b8  mov     ebx, eax
0x1801b11ba  test    eax, eax
0x1801b11bc  jns     short loc_1801B11D7
0x1801b11be  mov     edx, 113h; void *
0x1801b11c3  mov     r9d, eax; char *
0x1801b11c6  mov     r8, rdi; unsigned int
0x1801b11c9  mov     rcx, [rbp+38h]; this
0x1801b11cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b11d2  jmp     loc_1801B126A
0x1801b11d7  lea     rcx, [rsi+20h]
0x1801b11db  cmp     qword ptr [rcx+10h], 0
0x1801b11e0  jz      short loc_1801B1206
0x1801b11e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b11e7  mov     r8, rax; unsigned __int16 *
0x1801b11ea  lea     rdx, aMsCv; "MS-CV"
0x1801b11f1  mov     rcx, rsi; this
0x1801b11f4  call    ?AddHeaderToRequest@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801b11f9  mov     ebx, eax
0x1801b11fb  test    eax, eax
0x1801b11fd  jns     short loc_1801B1206
0x1801b11ff  mov     edx, 118h
0x1801b1204  jmp     short loc_1801B11C3
0x1801b1206  mov     dword ptr [rbp+dwContext], 0
0x1801b120d  lea     rax, [rbp+dwContext]
0x1801b1211  mov     qword ptr [rsp+80h+dwFlags], rax; dwContext
0x1801b1216  mov     eax, [rbp+dwOptionalLength]
0x1801b1219  mov     dword ptr [rsp+80h+ppwszAcceptTypes], eax; dwTotalLength
0x1801b121d  mov     dword ptr [rsp+80h+pwszReferrer], eax; dwOptionalLength
0x1801b1221  mov     r9, [rbp+lpOptional]; lpOptional
0x1801b1225  xor     r8d, r8d; dwHeadersLength
0x1801b1228  xor     edx, edx; lpszHeaders
0x1801b122a  mov     rcx, [r14]; hRequest
0x1801b122d  call    cs:__imp_WinHttpSendRequest
0x1801b1233  test    eax, eax
0x1801b1235  jnz     short loc_1801B1268
0x1801b1237  call    cs:__imp_GetLastError
0x1801b123d  mov     ebx, eax
0x1801b123f  test    eax, eax
0x1801b1241  jle     short loc_1801B124C
0x1801b1243  movzx   ebx, ax
0x1801b1246  or      ebx, 80070000h
0x1801b124c  mov     ecx, ebx; int
0x1801b124e  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x1801b1253  test    al, al
0x1801b1255  jnz     short loc_1801B126A
0x1801b1257  test    ebx, ebx
0x1801b1259  jns     short loc_1801B126A
0x1801b125b  mov     r9d, ebx
0x1801b125e  mov     edx, 127h
0x1801b1263  jmp     loc_1801B11C6
0x1801b1268  xor     ebx, ebx
0x1801b126a  lea     rcx, [rbp+var_28]
0x1801b126e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b1273  mov     eax, ebx
0x1801b1275  mov     rcx, [rbp+var_8]
0x1801b1279  xor     rcx, rsp; StackCookie
0x1801b127c  call    __security_check_cookie
0x1801b1281  mov     rbx, [rsp+80h+arg_8]
0x1801b1289  add     rsp, 80h
0x1801b1290  pop     r15
0x1801b1292  pop     r14
0x1801b1294  pop     r13
0x1801b1296  pop     r12
0x1801b1298  pop     rdi
0x1801b1299  pop     rsi
0x1801b129a  pop     rbp
0x1801b129b  retn
```
