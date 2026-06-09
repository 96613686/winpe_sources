# CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool,bool,HWND__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180013a2c`
- end: `0x1800142e9`
- name: `?GetAuthorizationHeaderInternalStatic@CloudPrintHelper@CloudPrint@@KAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@_N2PEAUHWND__@@PEAV34@444@Z`
- size: `2237`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001364c`
- `0x180013948`
- `0x1800142f0`

## callees

- `0x180003a60`
- `0x180006b70`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000f958`
- `0x180011de0`
- `0x180012bc0`
- `0x180013a2c`
- `0x180016b54`
- `0x180017144`
- `0x1800179e8`
- `0x180017b98`
- `0x18001aaf4`
- `0x18001ac7c`
- `0x18001af0c`
- `0x18001c0a8`
- `0x18001c298`

## string_xrefs

- `0x180013cd7`: `User Interaction Required while trying to get a token silently. ErrorCode: %#x, Error: %s`
- `0x180013d05`: `User Interaction Required while trying to get a token silently. ErrorCode: %#x, Error: %s`
- `0x180013f16`: `Received AccountSwitch when getting a token. Cloud Print might not work as expected for the current user.`
- `0x180013f29`: `Received AccountSwitch when getting a token. Cloud Print might not work as expected for the current user.`
- `0x180013fd9`: `Error requesting OAuth token. hr: %#x, WebTokenRequestStatus: %d, Error: %ws`
- `0x180014003`: `Error requesting OAuth token. hr: %#x, WebTokenRequestStatus: %d, Error: %ws`
- `0x1800141da`: `Successfully received access_token for %s with OAuthClientId=%s and OAuthAuthority=%s`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int v10; // ebx
  __int64 v11; // rax
  int v12; // r8d
  _WORD *v14; // rax
  __int64 v15; // rdx
  _WORD *v16; // rax
  _WORD *v17; // rax
  _WORD *v18; // rax
  int v19; // ecx
  int WebTokenRequest; // ebx
  char v21; // bl
  int TokenResult; // edi
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // ecx
  int v26; // edi
  int WebProviderError; // eax
  signed int v28; // ebx
  __int64 v29; // rax
  int TokenAndUserInfo; // ebx
  __int64 v31; // rax
  unsigned __int16 *v32; // rax
  const unsigned __int16 *v33; // rax
  int v34; // [rsp+20h] [rbp-118h]
  int v35; // [rsp+20h] [rbp-118h]
  unsigned int v36; // [rsp+40h] [rbp-F8h] BYREF
  _DWORD v37[3]; // [rsp+44h] [rbp-F4h] BYREF
  char v38; // [rsp+50h] [rbp-E8h]
  __int64 v39; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v41; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+78h] [rbp-C0h]
  __int64 v44; // [rsp+80h] [rbp-B8h]
  __int64 v45; // [rsp+88h] [rbp-B0h]
  _BYTE v46[32]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v47[32]; // [rsp+B0h] [rbp-88h] BYREF
  _BYTE v48[32]; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v38 = a4;
  v10 = a3;
  v45 = a3;
  v43 = a2;
  v44 = a1;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v34 = v12;
  CloudPrintHelperTelemetry::WriteDbgTraceInfo(
    "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
    L"API Enter. TargetResourceId=%s, OAuthClientId=%s, OAuthAuthority=%s, Silent=%s, PromptOnDesktopWindow=%s",
    v11);
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x769,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)0x80004003LL,
      v34);
    return 2147500035LL;
  }
  *(_QWORD *)(a7 + 16) = 0;
  v14 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  *v14 = v15;
  if ( a8 )
  {
    *(_QWORD *)(a8 + 16) = v15;
    v16 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    *v16 = v15;
  }
  if ( a9 )
  {
    *(_QWORD *)(a9 + 16) = v15;
    v17 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    *v17 = v15;
  }
  if ( a10 )
  {
    *(_QWORD *)(a10 + 16) = v15;
    v18 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    *v18 = v15;
  }
  v41 = v15;
  v40 = v15;
  v39 = v15;
  *(_QWORD *)&v37[1] = v15;
  v36 = v15;
  WebTokenRequest = CloudPrint::CloudPrintHelper::GetWebTokenRequest(
                      v44,
                      v43,
                      v10,
                      (unsigned int)&v41,
                      (unsigned int)&v40,
                      (__int64)&v39);
  if ( WebTokenRequest < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    return (unsigned int)WebTokenRequest;
  }
  v21 = 1;
  LOBYTE(v19) = 1;
  TokenResult = CloudPrint::CloudPrintHelper::GetTokenResult(
                  v19,
                  (unsigned int)&v41,
                  (unsigned int)&v40,
                  (unsigned int)&v39,
                  a5,
                  a6,
                  (__int64)&v36,
                  (__int64)&v37[1]);
  if ( TokenResult < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    return (unsigned int)TokenResult;
  }
  if ( !v36 )
    goto LABEL_45;
  if ( v36 == 3 )
  {
    v37[0] = 0;
    std::wstring::wstring((__int64)v46);
    v42 = 0;
    CloudPrint::CloudPrintHelper::GetWebProviderError(&v37[1], &v42, v37, v46);
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
      L"User Interaction Required while trying to get a token silently. ErrorCode: %#x, Error: %s",
      v37[0],
      v23);
    if ( v38 )
    {
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      PrintCore::McpEvtSrc::ReportErrorEvent(
        L"User Interaction Required while trying to get a token silently. ErrorCode: %#x, Error: %s",
        v37[0],
        v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      std::wstring::_Tidy_deallocate((__int64)v46);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      return 2156265484LL;
    }
    v26 = CloudPrint::CloudPrintHelper::GetTokenResult(
            0,
            (unsigned int)&v41,
            (unsigned int)&v40,
            (unsigned int)&v39,
            a5,
            a6,
            (__int64)&v36,
            (__int64)&v37[1]);
    if ( v26 < 0 )
      goto LABEL_18;
    if ( v36 )
    {
      if ( v36 == 2 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
          L"Received AccountSwitch when getting a token. Cloud Print might not work as expected for the current user.");
        PrintCore::McpEvtSrc::ReportWarningEvent(L"Received AccountSwitch when getting a token. Cloud Print might not work as expected for the current user.");
      }
      else
      {
        if ( v36 != 1 )
          goto LABEL_28;
        LOBYTE(v25) = 1;
        v26 = CloudPrint::CloudPrintHelper::GetTokenResult(
                v25,
                (unsigned int)&v41,
                (unsigned int)&v40,
                (unsigned int)&v39,
                a5,
                a6,
                (__int64)&v36,
                (__int64)&v37[1]);
        if ( v26 < 0 )
        {
LABEL_18:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          std::wstring::_Tidy_deallocate((__int64)v46);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
          return (unsigned int)v26;
        }
        if ( v36 )
        {
          if ( v36 == 3 )
          {
            CloudPrintHelperTelemetry::WriteDbgTraceWarning(
              "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
              L"User Cancelled the login dialog.");
            PrintCore::McpEvtSrc::ReportWarningEvent(L"User Cancelled the login dialog.");
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
            std::wstring::_Tidy_deallocate((__int64)v46);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            return 2148073526LL;
          }
LABEL_28:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          std::wstring::_Tidy_deallocate((__int64)v46);
          if ( v21 )
            goto LABEL_29;
LABEL_45:
          std::wstring::wstring((__int64)v47);
          TokenAndUserInfo = CloudPrint::CloudPrintHelper::GetTokenAndUserInfo(
                               (unsigned int)&v37[1],
                               v45,
                               (unsigned int)v47,
                               a8,
                               a9,
                               a10);
          if ( TokenAndUserInfo >= 0 )
          {
            v31 = std::operator+<unsigned short>(v46, L"Bearer ", v47);
            std::wstring::operator=(a7, v31);
            std::wstring::_Tidy_deallocate((__int64)v46);
            std::wstring::wstring(
              (__int64)v48,
              (__int64)L"Successfully received access_token for %s with OAuthClientId=%s and OAuthAuthority=%s");
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            v32 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            CloudPrintHelperTelemetry::WriteDbgTraceInfo(
              "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
              v32);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            v33 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            PrintCore::McpEvtSrc::ReportInfoEvent(v33);
            std::wstring::_Tidy_deallocate((__int64)v48);
            std::wstring::_Tidy_deallocate((__int64)v47);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            return 0;
          }
          else
          {
            std::wstring::_Tidy_deallocate((__int64)v47);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            return (unsigned int)TokenAndUserInfo;
          }
        }
      }
    }
    v21 = 0;
    goto LABEL_28;
  }
LABEL_29:
  v37[0] = 0;
  std::wstring::wstring((__int64)v46);
  v42 = 0;
  WebProviderError = CloudPrint::CloudPrintHelper::GetWebProviderError(&v37[1], &v42, v37, v46);
  if ( WebProviderError < 0 )
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
      L"Failed to GetWebProviderError. hr=%#x",
      (unsigned int)WebProviderError);
  v28 = v37[0];
  if ( v37[0] > 0 )
    v28 = LOWORD(v37[0]) | 0x80070000;
  v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  CloudPrintHelperTelemetry::WriteDbgTraceWarning(
    "CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternalStatic",
    L"Error requesting OAuth token. hr: %#x, WebTokenRequestStatus: %d, Error: %ws",
    (unsigned int)v28,
    v36);
  v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  PrintCore::McpEvtSrc::ReportErrorEvent(
    L"Error requesting OAuth token. hr: %#x, WebTokenRequestStatus: %d, Error: %ws",
    (unsigned int)v28,
    v36,
    v29);
  if ( ((v28 >> 16) & 0x1FFF) != 0xAA3
    && ((v28 >> 16) & 0x1FFF) != 0xAA7
    && ((v28 >> 16) & 0x1FFF) != 0xAA8
    && ((v28 >> 16) & 0x1FFF) != 0xAAD
    && v28 != -2146958592
    && v28 != -2147024638
    && v28 != -2147024894
    && v28 != -895352827
    && v28 != -895352824
    && v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x813,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)(unsigned int)v28,
      v35);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  std::wstring::_Tidy_deallocate((__int64)v46);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37[1]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180013a2c  push    rbx
0x180013a2e  push    rsi
0x180013a2f  push    rdi
0x180013a30  push    r12
0x180013a32  push    r13
0x180013a34  push    r14
0x180013a36  push    r15
0x180013a38  sub     rsp, 100h
0x180013a3f  mov     rax, cs:__security_cookie
0x180013a46  xor     rax, rsp
0x180013a49  mov     [rsp+138h+var_48], rax
0x180013a51  mov     r10b, r9b
0x180013a54  mov     [rsp+138h+var_E8], r9b
0x180013a59  mov     rbx, r8
0x180013a5c  mov     [rsp+138h+var_B0], rbx
0x180013a64  mov     r9, rdx
0x180013a67  mov     [rsp+138h+var_C0], rdx
0x180013a6c  mov     rdx, rcx
0x180013a6f  mov     [rsp+138h+var_B8], rcx
0x180013a77  mov     rsi, [rsp+138h+arg_48]
0x180013a7f  mov     r14, [rsp+138h+arg_40]
0x180013a87  mov     r15, [rsp+138h+arg_38]
0x180013a8f  mov     r13, [rsp+138h+arg_30]
0x180013a97  mov     r12, [rsp+138h+arg_28]
0x180013a9f  mov     rcx, rbx
0x180013aa2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013aa7  mov     r8, rax
0x180013aaa  mov     rcx, r9
0x180013aad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013ab2  mov     r9, rax
0x180013ab5  mov     rcx, rdx
0x180013ab8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013abd  lea     r11, aFalse; "false"
0x180013ac4  lea     rdx, aTrue; "true"
0x180013acb  mov     rcx, rdx
0x180013ace  mov     dil, [rsp+138h+arg_20]
0x180013ad6  test    dil, dil
0x180013ad9  cmovz   rcx, r11
0x180013add  test    r10b, r10b
0x180013ae0  cmovz   rdx, r11
0x180013ae4  mov     [rsp+138h+var_108], rcx
0x180013ae9  mov     [rsp+138h+var_110], rdx
0x180013aee  mov     qword ptr [rsp+138h+var_118], r8; int
0x180013af3  mov     r8, rax
0x180013af6  lea     rdx, aApiEnterTarget; "API Enter. TargetResourceId=%s, OAuthCl"...
0x180013afd  lea     rcx, aCloudprintClou_32; "CloudPrint::CloudPrintHelper::GetAuthor"...
0x180013b04  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013b09  xor     edx, edx
0x180013b0b  test    r13, r13
0x180013b0e  jnz     short loc_180013B38
0x180013b10  mov     rcx, [rsp+138h]; this
0x180013b18  mov     ebx, 80004003h
0x180013b1d  mov     r9d, ebx; char *
0x180013b20  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180013b27  mov     edx, 769h; void *
0x180013b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b31  mov     eax, ebx
0x180013b33  jmp     loc_1800142C5
0x180013b38  mov     [r13+10h], rdx
0x180013b3c  mov     rcx, r13
0x180013b3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013b44  mov     [rax], dx
0x180013b47  test    r15, r15
0x180013b4a  jz      short loc_180013B5B
0x180013b4c  mov     [r15+10h], rdx
0x180013b50  mov     rcx, r15
0x180013b53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013b58  mov     [rax], dx
0x180013b5b  test    r14, r14
0x180013b5e  jz      short loc_180013B6F
0x180013b60  mov     [r14+10h], rdx
0x180013b64  mov     rcx, r14
0x180013b67  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013b6c  mov     [rax], dx
0x180013b6f  test    rsi, rsi
0x180013b72  jz      short loc_180013B83
0x180013b74  mov     [rsi+10h], rdx
0x180013b78  mov     rcx, rsi
0x180013b7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013b80  mov     [rax], dx
0x180013b83  mov     [rsp+138h+var_D0], rdx
0x180013b88  mov     [rsp+138h+var_D8], rdx
0x180013b8d  mov     [rsp+138h+var_E0], rdx
0x180013b92  mov     qword ptr [rsp+138h+var_F4+4], rdx
0x180013b97  mov     [rsp+138h+var_F8], edx
0x180013b9b  lea     rax, [rsp+138h+var_E0]
0x180013ba0  mov     [rsp+138h+var_110], rax
0x180013ba5  lea     rax, [rsp+138h+var_D8]
0x180013baa  mov     qword ptr [rsp+138h+var_118], rax
0x180013baf  lea     r9, [rsp+138h+var_D0]
0x180013bb4  mov     r8, rbx
0x180013bb7  mov     rdx, [rsp+138h+var_C0]
0x180013bbc  mov     rcx, [rsp+138h+var_B8]
0x180013bc4  call    ?GetWebTokenRequest@CloudPrintHelper@CloudPrint@@KAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@678@V?$ComPtrRef@V?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@678@@Z; CloudPrint::CloudPrintHelper::GetWebTokenRequest(std::wstring const &,std::wstring const &,std::wstring const &,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest>>,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>>)
0x180013bc9  mov     ebx, eax
0x180013bcb  test    eax, eax
0x180013bcd  jns     short loc_180013C01
0x180013bcf  lea     rcx, [rsp+138h+var_F4+4]
0x180013bd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013bd9  nop
0x180013bda  lea     rcx, [rsp+138h+var_E0]
0x180013bdf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013be4  nop
0x180013be5  lea     rcx, [rsp+138h+var_D8]
0x180013bea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013bef  nop
0x180013bf0  lea     rcx, [rsp+138h+var_D0]
0x180013bf5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013bfa  mov     eax, ebx
0x180013bfc  jmp     loc_1800142C5
0x180013c01  lea     rax, [rsp+138h+var_F4+4]
0x180013c06  mov     [rsp+138h+var_100], rax
0x180013c0b  lea     rax, [rsp+138h+var_F8]
0x180013c10  mov     [rsp+138h+var_108], rax
0x180013c15  mov     [rsp+138h+var_110], r12
0x180013c1a  mov     byte ptr [rsp+138h+var_118], dil
0x180013c1f  lea     r9, [rsp+138h+var_E0]
0x180013c24  lea     r8, [rsp+138h+var_D8]
0x180013c29  lea     rdx, [rsp+138h+var_D0]
0x180013c2e  mov     ebx, 1
0x180013c33  mov     cl, bl
0x180013c35  call    ?GetTokenResult@CloudPrintHelper@CloudPrint@@KAJ_NAEAV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@AEAV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@45@0PEAUHWND__@@PEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@45@@Z; CloudPrint::CloudPrintHelper::GetTokenResult(bool,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &,Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> &,bool,HWND__ *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>)
0x180013c3a  mov     edi, eax
0x180013c3c  test    eax, eax
0x180013c3e  jns     short loc_180013C72
0x180013c40  lea     rcx, [rsp+138h+var_F4+4]
0x180013c45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c4a  nop
0x180013c4b  lea     rcx, [rsp+138h+var_E0]
0x180013c50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c55  nop
0x180013c56  lea     rcx, [rsp+138h+var_D8]
0x180013c5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c60  nop
0x180013c61  lea     rcx, [rsp+138h+var_D0]
0x180013c66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c6b  mov     eax, edi
0x180013c6d  jmp     loc_1800142C5
0x180013c72  mov     eax, [rsp+138h+var_F8]
0x180013c76  test    eax, eax
0x180013c78  jz      loc_180014128
0x180013c7e  cmp     eax, 3
0x180013c81  jnz     loc_180013F57
0x180013c87  mov     dword ptr [rsp+138h+var_F4], 0
0x180013c8f  lea     rcx, [rsp+138h+var_A8]
0x180013c97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013c9c  nop
0x180013c9d  mov     [rsp+138h+var_C8], 0
0x180013ca6  lea     r9, [rsp+138h+var_A8]
0x180013cae  lea     r8, [rsp+138h+var_F4]
0x180013cb3  lea     rdx, [rsp+138h+var_C8]
0x180013cb8  lea     rcx, [rsp+138h+var_F4+4]
0x180013cbd  call    ?GetWebProviderError@CloudPrintHelper@CloudPrint@@KAJAEAV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@45@PEAKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetWebProviderError(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IFindAllAccountsResult> &,ulong *,std::wstring *)
0x180013cc2  lea     rcx, [rsp+138h+var_A8]
0x180013cca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013ccf  mov     r9, rax
0x180013cd2  mov     r8d, dword ptr [rsp+138h+var_F4]
0x180013cd7  lea     rdx, aUserInteractio; "User Interaction Required while trying "...
0x180013cde  lea     rcx, aCloudprintClou_32; "CloudPrint::CloudPrintHelper::GetAuthor"...
0x180013ce5  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180013cea  cmp     [rsp+138h+var_E8], 0
0x180013cef  jz      short loc_180013D60
0x180013cf1  lea     rcx, [rsp+138h+var_A8]
0x180013cf9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013cfe  mov     r8, rax
0x180013d01  mov     edx, dword ptr [rsp+138h+var_F4]
0x180013d05  lea     rcx, aUserInteractio; "User Interaction Required while trying "...
0x180013d0c  call    ?ReportErrorEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportErrorEvent(ushort const *,...)
0x180013d11  nop
0x180013d12  lea     rcx, [rsp+138h+var_C8]
0x180013d17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d1c  nop
0x180013d1d  lea     rcx, [rsp+138h+var_A8]
0x180013d25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013d2a  nop
0x180013d2b  lea     rcx, [rsp+138h+var_F4+4]
0x180013d30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d35  nop
0x180013d36  lea     rcx, [rsp+138h+var_E0]
0x180013d3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d40  nop
0x180013d41  lea     rcx, [rsp+138h+var_D8]
0x180013d46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d4b  nop
0x180013d4c  lea     rcx, [rsp+138h+var_D0]
0x180013d51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d56  mov     eax, 8086000Ch
0x180013d5b  jmp     loc_1800142C5
0x180013d60  lea     rax, [rsp+138h+var_F4+4]
0x180013d65  mov     [rsp+138h+var_100], rax
0x180013d6a  lea     rax, [rsp+138h+var_F8]
0x180013d6f  mov     [rsp+138h+var_108], rax
0x180013d74  mov     [rsp+138h+var_110], r12
0x180013d79  mov     al, [rsp+138h+arg_20]
0x180013d80  mov     byte ptr [rsp+138h+var_118], al
0x180013d84  lea     r9, [rsp+138h+var_E0]
0x180013d89  lea     r8, [rsp+138h+var_D8]
0x180013d8e  lea     rdx, [rsp+138h+var_D0]
0x180013d93  xor     ecx, ecx
0x180013d95  call    ?GetTokenResult@CloudPrintHelper@CloudPrint@@KAJ_NAEAV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@AEAV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@45@0PEAUHWND__@@PEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@45@@Z; CloudPrint::CloudPrintHelper::GetTokenResult(bool,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &,Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> &,bool,HWND__ *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>)
0x180013d9a  mov     edi, eax
0x180013d9c  test    eax, eax
0x180013d9e  jns     short loc_180013DEB
0x180013da0  lea     rcx, [rsp+138h+var_C8]
0x180013da5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013daa  nop
0x180013dab  lea     rcx, [rsp+138h+var_A8]
0x180013db3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013db8  nop
0x180013db9  lea     rcx, [rsp+138h+var_F4+4]
0x180013dbe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013dc3  nop
0x180013dc4  lea     rcx, [rsp+138h+var_E0]
0x180013dc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013dce  nop
0x180013dcf  lea     rcx, [rsp+138h+var_D8]
0x180013dd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013dd9  nop
0x180013dda  lea     rcx, [rsp+138h+var_D0]
0x180013ddf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013de4  mov     eax, edi
0x180013de6  jmp     loc_1800142C5
0x180013deb  mov     eax, [rsp+138h+var_F8]
0x180013def  test    eax, eax
0x180013df1  jz      loc_180013F35
0x180013df7  cmp     eax, 2
0x180013dfa  jz      loc_180013F16
0x180013e00  cmp     eax, ebx
0x180013e02  jnz     loc_180013F37
0x180013e08  lea     rax, [rsp+138h+var_F4+4]
0x180013e0d  mov     [rsp+138h+var_100], rax
0x180013e12  lea     rax, [rsp+138h+var_F8]
0x180013e17  mov     [rsp+138h+var_108], rax
0x180013e1c  mov     [rsp+138h+var_110], r12
0x180013e21  mov     al, [rsp+138h+arg_20]
0x180013e28  mov     byte ptr [rsp+138h+var_118], al
0x180013e2c  lea     r9, [rsp+138h+var_E0]
0x180013e31  lea     r8, [rsp+138h+var_D8]
0x180013e36  lea     rdx, [rsp+138h+var_D0]
0x180013e3b  mov     cl, bl
0x180013e3d  call    ?GetTokenResult@CloudPrintHelper@CloudPrint@@KAJ_NAEAV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@AEAV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@45@0PEAUHWND__@@PEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@45@@Z; CloudPrint::CloudPrintHelper::GetTokenResult(bool,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &,Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> &,bool,HWND__ *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>)
0x180013e42  mov     edi, eax
0x180013e44  test    eax, eax
0x180013e46  jns     short loc_180013E93
0x180013e48  lea     rcx, [rsp+138h+var_C8]
0x180013e4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e52  nop
0x180013e53  lea     rcx, [rsp+138h+var_A8]
0x180013e5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013e60  nop
0x180013e61  lea     rcx, [rsp+138h+var_F4+4]
0x180013e66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e6b  nop
0x180013e6c  lea     rcx, [rsp+138h+var_E0]
0x180013e71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e76  nop
0x180013e77  lea     rcx, [rsp+138h+var_D8]
0x180013e7c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e81  nop
0x180013e82  lea     rcx, [rsp+138h+var_D0]
0x180013e87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e8c  mov     eax, edi
0x180013e8e  jmp     loc_1800142C5
0x180013e93  mov     eax, [rsp+138h+var_F8]
0x180013e97  test    eax, eax
0x180013e99  jz      loc_180013F35
0x180013e9f  cmp     eax, 3
0x180013ea2  jnz     loc_180013F37
0x180013ea8  lea     rdx, aUserCancelledT; "User Cancelled the login dialog."
0x180013eaf  lea     rcx, aCloudprintClou_32; "CloudPrint::CloudPrintHelper::GetAuthor"...
0x180013eb6  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180013ebb  lea     rcx, aUserCancelledT; "User Cancelled the login dialog."
0x180013ec2  call    ?ReportWarningEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportWarningEvent(ushort const *,...)
0x180013ec7  nop
0x180013ec8  lea     rcx, [rsp+138h+var_C8]
0x180013ecd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013ed2  nop
0x180013ed3  lea     rcx, [rsp+138h+var_A8]
0x180013edb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013ee0  nop
0x180013ee1  lea     rcx, [rsp+138h+var_F4+4]
0x180013ee6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013eeb  nop
0x180013eec  lea     rcx, [rsp+138h+var_E0]
0x180013ef1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013ef6  nop
0x180013ef7  lea     rcx, [rsp+138h+var_D8]
0x180013efc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f01  nop
0x180013f02  lea     rcx, [rsp+138h+var_D0]
0x180013f07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f0c  mov     eax, 80090036h
0x180013f11  jmp     loc_1800142C5
0x180013f16  lea     rdx, aReceivedAccoun; "Received AccountSwitch when getting a t"...
0x180013f1d  lea     rcx, aCloudprintClou_32; "CloudPrint::CloudPrintHelper::GetAuthor"...
0x180013f24  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180013f29  lea     rcx, aReceivedAccoun; "Received AccountSwitch when getting a t"...
0x180013f30  call    ?ReportWarningEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportWarningEvent(ushort const *,...)
0x180013f35  xor     bl, bl
0x180013f37  lea     rcx, [rsp+138h+var_C8]
  ... truncated ...
```
