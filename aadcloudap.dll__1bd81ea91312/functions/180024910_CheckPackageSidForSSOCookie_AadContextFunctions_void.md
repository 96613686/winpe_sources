# CheckPackageSidForSSOCookie(AadContextFunctions *,void *)

- ea: `0x180024910`
- end: `0x180024f4b`
- name: `?CheckPackageSidForSSOCookie@@YAJPEAVAadContextFunctions@@PEAX@Z`
- size: `1595`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180045694`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180024910`
- `0x180028e50`
- `0x180029284`
- `0x18002a910`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d87`
- `ntdll!RtlEqualSid` at `0x180024c48`
- `ntdll!RtlEqualSid` at `0x180024c5d`
- `ntdll!RtlEqualSid` at `0x180024d05`
- `ntdll!RtlEqualSid` at `0x180024e45`
- `ntdll!RtlEqualSid` at `0x180024c48`
- `ntdll!RtlEqualSid` at `0x180024c5d`
- `ntdll!RtlEqualSid` at `0x180024d05`
- `ntdll!RtlEqualSid` at `0x180024e45`
- `ntdll!NtQueryInformationToken` at `0x1800249f1`
- `ntdll!NtQueryInformationToken` at `0x1800249f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024a94`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024c76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024d69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024a94`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024c76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024d69`

## string_xrefs

- `0x18002496e`: `CheckPackageSidForSSOCookie`

## pseudocode

```c
__int64 __fastcall CheckPackageSidForSSOCookie(struct AadContextFunctions *a1, void *a2)
{
  PSID v4; // rsi
  struct _TOKEN_GROUPS *v5; // r14
  int TokenBrokerPluginSID; // ecx
  int CallerPackageSid; // ecx
  int CallerPackageCapabilities; // edi
  DWORD v9; // edi
  unsigned int v10; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-69h]
  __int64 v13; // [rsp+30h] [rbp-59h]
  PSID Sid; // [rsp+50h] [rbp-39h] BYREF
  PSID Sid1; // [rsp+58h] [rbp-31h] BYREF
  PSID Sid2; // [rsp+60h] [rbp-29h] BYREF
  struct _TOKEN_GROUPS *v17; // [rsp+68h] [rbp-21h] BYREF
  PSID v18; // [rsp+70h] [rbp-19h] BYREF
  PSID v19; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v20[96]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v21; // [rsp+F0h] [rbp+67h] BYREF
  int TokenInformation; // [rsp+100h] [rbp+77h] BYREF
  ULONG TokenInformationLength; // [rsp+108h] [rbp+7Fh] BYREF

  v21 = 0;
  TokenInformation = 0;
  TokenInformationLength = 4;
  Sid = 0;
  v18 = 0;
  v4 = 0;
  Sid2 = 0;
  Sid1 = 0;
  v19 = 0;
  v5 = 0;
  v17 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v20,
    "login.cpp",
    "CheckPackageSidForSSOCookie",
    &v21);
  if ( !a1 )
  {
    v21 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "login.cpp", 2729, "NTSTATUS", &base);
    goto LABEL_60;
  }
  TokenBrokerPluginSID = NtQueryInformationToken(
                           a2,
                           TokenIsAppContainer,
                           &TokenInformation,
                           TokenInformationLength,
                           &TokenInformationLength);
  v21 = TokenBrokerPluginSID;
  if ( TokenBrokerPluginSID >= 0 )
  {
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "login.cpp", 2734, "lowboxCaller", TokenInformation);
    if ( !TokenInformation )
      goto LABEL_48;
    if ( ConvertStringSidToSidW(
           L"S-1-15-2-3624051433-2125758914-1423191267-1740899205-1073925389-3782572162-737981194",
           &Sid)
      || ((int)GetLastError() > 0
        ? (TokenBrokerPluginSID = (unsigned __int16)GetLastError() | 0xC0070000)
        : (TokenBrokerPluginSID = GetLastError()),
          v21 = TokenBrokerPluginSID,
          TokenBrokerPluginSID >= 0) )
    {
      if ( Sid )
      {
        TokenBrokerPluginSID = GetTokenBrokerPluginSID(&Sid1);
        v21 = TokenBrokerPluginSID;
        if ( TokenBrokerPluginSID >= 0 )
        {
          if ( Sid1 )
          {
            CallerPackageSid = GetCallerPackageSid(a1, a2, &Sid2);
            v21 = CallerPackageSid;
            if ( CallerPackageSid < 0 )
            {
              LODWORD(v13) = 2755;
              LODWORD(ReturnLength) = CallerPackageSid;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "NTSTATUS", &base);
              v4 = Sid2;
              goto LABEL_48;
            }
            v4 = Sid2;
            if ( !Sid2 )
            {
              LODWORD(v13) = 2759;
              LODWORD(ReturnLength) = -2147187437;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
              v21 = -1073445613;
              goto LABEL_48;
            }
            if ( RtlEqualSid(Sid, Sid2) || RtlEqualSid(Sid1, v4) )
              goto LABEL_48;
            if ( ConvertStringSidToSidW(
                   L"S-1-15-2-2434737943-167758768-3180539153-984336765-1107280622-3591121930-2677285773",
                   &v18)
              || ((int)GetLastError() > 0
                ? (TokenBrokerPluginSID = (unsigned __int16)GetLastError() | 0xC0070000)
                : (TokenBrokerPluginSID = GetLastError()),
                  v21 = TokenBrokerPluginSID,
                  TokenBrokerPluginSID >= 0) )
            {
              if ( v18 )
              {
                if ( RtlEqualSid(v18, v4) )
                {
                  LODWORD(v13) = 2775;
                  LODWORD(ReturnLength) = -2147187408;
                  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                  v21 = -1073445584;
                  goto LABEL_48;
                }
                if ( ConvertStringSidToSidW(
                       L"S-1-15-3-1024-983922258-2159917625-2751362240-3284369410-2497023943-943411171-3503282929-3741434461",
                       &v19)
                  || ((int)GetLastError() > 0
                    ? (TokenBrokerPluginSID = (unsigned __int16)GetLastError() | 0xC0070000)
                    : (TokenBrokerPluginSID = GetLastError()),
                      v21 = TokenBrokerPluginSID,
                      TokenBrokerPluginSID >= 0) )
                {
                  CallerPackageCapabilities = GetCallerPackageCapabilities(a1, a2, &v17);
                  v21 = CallerPackageCapabilities;
                  if ( CallerPackageCapabilities >= 0 )
                  {
                    v9 = 0;
                    v5 = v17;
                    if ( v17 )
                    {
                      while ( v9 < v5->GroupCount )
                      {
                        if ( RtlEqualSid(v5->Groups[v9].Sid, v19) )
                          goto LABEL_48;
                        ++v9;
                      }
                    }
                    LODWORD(v13) = 2797;
                    LODWORD(ReturnLength) = -2147187435;
                    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                    v21 = -1073445611;
                  }
                  else
                  {
                    LODWORD(v13) = 2786;
                    LODWORD(ReturnLength) = CallerPackageCapabilities;
                    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                    v21 = CallerPackageCapabilities & 0xAFFFFFFF | 0x40000000;
                    v5 = v17;
                  }
                  goto LABEL_48;
                }
                LODWORD(v13) = 2783;
              }
              else
              {
                TokenBrokerPluginSID = -1073741595;
                v21 = -1073741595;
                LODWORD(v13) = 2770;
              }
            }
            else
            {
              LODWORD(v13) = 2766;
            }
          }
          else
          {
            TokenBrokerPluginSID = -1073741595;
            v21 = -1073741595;
            LODWORD(v13) = 2752;
          }
        }
        else
        {
          LODWORD(v13) = 2749;
        }
      }
      else
      {
        TokenBrokerPluginSID = -1073741595;
        v21 = -1073741595;
        LODWORD(v13) = 2746;
      }
    }
    else
    {
      LODWORD(v13) = 2742;
    }
  }
  else
  {
    LODWORD(v13) = 2732;
  }
  LODWORD(ReturnLength) = TokenBrokerPluginSID;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "NTSTATUS", &base);
LABEL_48:
  if ( Sid )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v18 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v4 )
    (*(void (__fastcall **)(struct AadContextFunctions *, PSID))(*(_QWORD *)a1 + 32LL))(a1, v4);
  if ( Sid1 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v19 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v5 )
    (*(void (__fastcall **)(struct AadContextFunctions *, struct _TOKEN_GROUPS *))(*(_QWORD *)a1 + 32LL))(a1, v5);
LABEL_60:
  v10 = v21;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v20);
  return v10;
}

```

## disassembly

```asm
0x180024910  push    rbp
0x180024912  push    rbx
0x180024913  push    rsi
0x180024914  push    rdi
0x180024915  push    r12
0x180024917  push    r13
0x180024919  push    r14
0x18002491b  lea     rbp, [rsp-27h]
0x180024920  sub     rsp, 0B0h
0x180024927  mov     rdi, rdx
0x18002492a  mov     rbx, rcx
0x18002492d  mov     [rbp+57h+arg_0], 0
0x180024934  mov     [rbp+57h+TokenInformation], 0
0x18002493b  mov     r13d, 4
0x180024941  mov     [rbp+57h+TokenInformationLength], r13d
0x180024945  mov     [rbp+57h+Sid], 0
0x18002494d  mov     [rbp+57h+var_70], 0
0x180024955  xor     esi, esi
0x180024957  mov     [rbp+57h+Sid2], rsi
0x18002495b  mov     [rbp+57h+Sid1], rsi
0x18002495f  mov     [rbp+57h+var_68], rsi
0x180024963  xor     r14d, r14d
0x180024966  mov     [rbp+57h+var_78], r14
0x18002496a  lea     r9, [rbp+57h+arg_0]
0x18002496e  lea     r8, aCheckpackagesi_0; "CheckPackageSidForSSOCookie"
0x180024975  lea     r12, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002497c  mov     rdx, r12
0x18002497f  lea     rcx, [rbp+57h+var_60]
0x180024983  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180024988  nop
0x180024989  test    rbx, rbx
0x18002498c  jnz     short loc_1800249D8
0x18002498e  mov     ecx, 0C000000Dh
0x180024993  mov     [rbp+57h+arg_0], ecx
0x180024996  lea     rax, base
0x18002499d  mov     [rsp+0E0h+var_A0], rax
0x1800249a2  lea     rax, aNtstatus; "NTSTATUS"
0x1800249a9  mov     [rsp+0E0h+var_A8], rax
0x1800249ae  mov     dword ptr [rsp+0E0h+var_B0], 0AA9h
0x1800249b6  mov     [rsp+0E0h+var_B8], r12
0x1800249bb  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x1800249bf  lea     ecx, [rsi+2]
0x1800249c2  mov     r9d, ecx
0x1800249c5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800249cc  xor     edx, edx
0x1800249ce  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800249d3  jmp     loc_180024F2B
0x1800249d8  lea     rax, [rbp+57h+TokenInformationLength]
0x1800249dc  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800249e1  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800249e5  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800249e9  mov     edx, 1Dh; TokenInformationClass
0x1800249ee  mov     rcx, rdi; TokenHandle
0x1800249f1  call    cs:__imp_NtQueryInformationToken
0x1800249f7  mov     ecx, eax
0x1800249f9  mov     [rbp+57h+arg_0], eax
0x1800249fc  xor     edx, edx
0x1800249fe  test    eax, eax
0x180024a00  jns     short loc_180024A44
0x180024a02  lea     rax, base
0x180024a09  mov     [rsp+0E0h+var_A0], rax
0x180024a0e  lea     rax, aNtstatus; "NTSTATUS"
0x180024a15  mov     [rsp+0E0h+var_A8], rax
0x180024a1a  mov     dword ptr [rsp+0E0h+var_B0], 0AACh
0x180024a22  mov     [rsp+0E0h+var_B8], r12
0x180024a27  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x180024a2b  mov     ecx, 2
0x180024a30  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024a37  mov     r9d, ecx
0x180024a3a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024a3f  jmp     loc_180024E9D
0x180024a44  mov     eax, [rbp+57h+TokenInformation]
0x180024a47  mov     dword ptr [rsp+0E0h+var_A0], eax
0x180024a4b  lea     rax, aLowboxcaller; "lowboxCaller"
0x180024a52  mov     [rsp+0E0h+var_A8], rax
0x180024a57  mov     dword ptr [rsp+0E0h+var_B0], 0AAEh
0x180024a5f  mov     [rsp+0E0h+var_B8], r12
0x180024a64  mov     [rsp+0E0h+ReturnLength], 0
0x180024a6d  mov     r9d, r13d
0x180024a70  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x180024a77  mov     ecx, r13d
0x180024a7a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024a7f  cmp     [rbp+57h+TokenInformation], 0
0x180024a83  jz      loc_180024E9D
0x180024a89  lea     rdx, [rbp+57h+Sid]; Sid
0x180024a8d  lea     rcx, aS1152362405143; "S-1-15-2-3624051433-2125758914-14231912"...
0x180024a94  call    cs:__imp_ConvertStringSidToSidW
0x180024a9a  mov     r13d, 0C0070000h
0x180024aa0  test    eax, eax
0x180024aa2  jnz     short loc_180024AF2
0x180024aa4  call    cs:__imp_GetLastError
0x180024aaa  test    eax, eax
0x180024aac  jg      short loc_180024AB8
0x180024aae  call    cs:__imp_GetLastError
0x180024ab4  mov     ecx, eax
0x180024ab6  jmp     short loc_180024AC4
0x180024ab8  call    cs:__imp_GetLastError
0x180024abe  movzx   ecx, ax
0x180024ac1  or      ecx, r13d
0x180024ac4  mov     [rbp+57h+arg_0], ecx
0x180024ac7  test    ecx, ecx
0x180024ac9  jns     short loc_180024AF2
0x180024acb  lea     rax, base
0x180024ad2  mov     [rsp+0E0h+var_A0], rax
0x180024ad7  lea     rax, aNtstatus; "NTSTATUS"
0x180024ade  mov     [rsp+0E0h+var_A8], rax
0x180024ae3  mov     dword ptr [rsp+0E0h+var_B0], 0AB6h
0x180024aeb  xor     edx, edx
0x180024aed  jmp     loc_180024A22
0x180024af2  cmp     [rbp+57h+Sid], 0
0x180024af7  jnz     short loc_180024B23
0x180024af9  mov     ecx, 0C00000E5h
0x180024afe  mov     [rbp+57h+arg_0], ecx
0x180024b01  lea     rax, base
0x180024b08  mov     [rsp+0E0h+var_A0], rax
0x180024b0d  lea     rax, aNtstatus; "NTSTATUS"
0x180024b14  mov     [rsp+0E0h+var_A8], rax
0x180024b19  mov     dword ptr [rsp+0E0h+var_B0], 0ABAh
0x180024b21  jmp     short loc_180024AEB
0x180024b23  lea     rcx, [rbp+57h+Sid1]; Sid
0x180024b27  call    ?GetTokenBrokerPluginSID@@YAJPEAPEAX@Z; GetTokenBrokerPluginSID(void * *)
0x180024b2c  mov     ecx, eax
0x180024b2e  mov     [rbp+57h+arg_0], eax
0x180024b31  test    eax, eax
0x180024b33  jns     short loc_180024B57
0x180024b35  lea     rax, base
0x180024b3c  mov     [rsp+0E0h+var_A0], rax
0x180024b41  lea     rax, aNtstatus; "NTSTATUS"
0x180024b48  mov     [rsp+0E0h+var_A8], rax
0x180024b4d  mov     dword ptr [rsp+0E0h+var_B0], 0ABDh
0x180024b55  jmp     short loc_180024AEB
0x180024b57  cmp     [rbp+57h+Sid1], 0
0x180024b5c  jnz     short loc_180024B8B
0x180024b5e  mov     ecx, 0C00000E5h
0x180024b63  mov     [rbp+57h+arg_0], ecx
0x180024b66  lea     rax, base
0x180024b6d  mov     [rsp+0E0h+var_A0], rax
0x180024b72  lea     rax, aNtstatus; "NTSTATUS"
0x180024b79  mov     [rsp+0E0h+var_A8], rax
0x180024b7e  mov     dword ptr [rsp+0E0h+var_B0], 0AC0h
0x180024b86  jmp     loc_180024AEB
0x180024b8b  lea     r8, [rbp+57h+Sid2]; void **
0x180024b8f  mov     rdx, rdi; void *
0x180024b92  mov     rcx, rbx; struct AadContextFunctions *
0x180024b95  call    ?GetCallerPackageSid@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; GetCallerPackageSid(AadContextFunctions *,void *,void * *)
0x180024b9a  mov     ecx, eax
0x180024b9c  mov     [rbp+57h+arg_0], eax
0x180024b9f  test    eax, eax
0x180024ba1  jns     short loc_180024BEB
0x180024ba3  lea     rax, base
0x180024baa  mov     [rsp+0E0h+var_A0], rax
0x180024baf  lea     rax, aNtstatus; "NTSTATUS"
0x180024bb6  mov     [rsp+0E0h+var_A8], rax
0x180024bbb  mov     dword ptr [rsp+0E0h+var_B0], 0AC3h
0x180024bc3  mov     [rsp+0E0h+var_B8], r12
0x180024bc8  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x180024bcc  mov     ecx, 2
0x180024bd1  mov     r9d, ecx
0x180024bd4  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024bdb  xor     edx, edx
0x180024bdd  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024be2  mov     rsi, [rbp+57h+Sid2]
0x180024be6  jmp     loc_180024E9D
0x180024beb  mov     rsi, [rbp+57h+Sid2]
0x180024bef  test    rsi, rsi
0x180024bf2  jnz     short loc_180024C41
0x180024bf4  lea     rax, base
0x180024bfb  mov     [rsp+0E0h+var_A0], rax
0x180024c00  lea     rax, aHresult; "HRESULT"
0x180024c07  mov     [rsp+0E0h+var_A8], rax
0x180024c0c  mov     dword ptr [rsp+0E0h+var_B0], 0AC7h
0x180024c14  mov     [rsp+0E0h+var_B8], r12
0x180024c19  mov     dword ptr [rsp+0E0h+ReturnLength], 80048513h
0x180024c21  lea     ecx, [rsi+2]
0x180024c24  mov     r9d, ecx
0x180024c27  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024c2e  xor     edx, edx
0x180024c30  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024c35  mov     [rbp+57h+arg_0], 0C0048513h
0x180024c3c  jmp     loc_180024E9D
0x180024c41  mov     rdx, rsi; Sid2
0x180024c44  mov     rcx, [rbp+57h+Sid]; Sid1
0x180024c48  call    cs:__imp_RtlEqualSid
0x180024c4e  test    al, al
0x180024c50  jnz     loc_180024E9D
0x180024c56  mov     rdx, rsi; Sid2
0x180024c59  mov     rcx, [rbp+57h+Sid1]; Sid1
0x180024c5d  call    cs:__imp_RtlEqualSid
0x180024c63  test    al, al
0x180024c65  jnz     loc_180024E9D
0x180024c6b  lea     rdx, [rbp+57h+var_70]; Sid
0x180024c6f  lea     rcx, aS1152243473794; "S-1-15-2-2434737943-167758768-318053915"...
0x180024c76  call    cs:__imp_ConvertStringSidToSidW
0x180024c7c  test    eax, eax
0x180024c7e  jnz     short loc_180024CCC
0x180024c80  call    cs:__imp_GetLastError
0x180024c86  test    eax, eax
0x180024c88  jg      short loc_180024C94
0x180024c8a  call    cs:__imp_GetLastError
0x180024c90  mov     ecx, eax
0x180024c92  jmp     short loc_180024CA0
0x180024c94  call    cs:__imp_GetLastError
0x180024c9a  movzx   ecx, ax
0x180024c9d  or      ecx, r13d
0x180024ca0  mov     [rbp+57h+arg_0], ecx
0x180024ca3  test    ecx, ecx
0x180024ca5  jns     short loc_180024CCC
0x180024ca7  lea     rax, base
0x180024cae  mov     [rsp+0E0h+var_A0], rax
0x180024cb3  lea     rax, aNtstatus; "NTSTATUS"
0x180024cba  mov     [rsp+0E0h+var_A8], rax
0x180024cbf  mov     dword ptr [rsp+0E0h+var_B0], 0ACEh
0x180024cc7  jmp     loc_180024AEB
0x180024ccc  mov     rcx, [rbp+57h+var_70]; Sid1
0x180024cd0  test    rcx, rcx
0x180024cd3  jnz     short loc_180024D02
0x180024cd5  mov     ecx, 0C00000E5h
0x180024cda  mov     [rbp+57h+arg_0], ecx
0x180024cdd  lea     rax, base
0x180024ce4  mov     [rsp+0E0h+var_A0], rax
0x180024ce9  lea     rax, aNtstatus; "NTSTATUS"
0x180024cf0  mov     [rsp+0E0h+var_A8], rax
0x180024cf5  mov     dword ptr [rsp+0E0h+var_B0], 0AD2h
0x180024cfd  jmp     loc_180024AEB
0x180024d02  mov     rdx, rsi; Sid2
0x180024d05  call    cs:__imp_RtlEqualSid
0x180024d0b  test    al, al
0x180024d0d  jz      short loc_180024D5E
0x180024d0f  lea     rax, base
0x180024d16  mov     [rsp+0E0h+var_A0], rax
0x180024d1b  lea     rax, aHresult; "HRESULT"
0x180024d22  mov     [rsp+0E0h+var_A8], rax
0x180024d27  mov     dword ptr [rsp+0E0h+var_B0], 0AD7h
0x180024d2f  mov     [rsp+0E0h+var_B8], r12
0x180024d34  mov     dword ptr [rsp+0E0h+ReturnLength], 80048530h
0x180024d3c  mov     ecx, 2
0x180024d41  mov     r9d, ecx
0x180024d44  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024d4b  xor     edx, edx
0x180024d4d  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024d52  mov     [rbp+57h+arg_0], 0C0048530h
0x180024d59  jmp     loc_180024E9D
0x180024d5e  lea     rdx, [rbp+57h+var_68]; Sid
0x180024d62  lea     rcx, aS1153102498392; "S-1-15-3-1024-983922258-2159917625-2751"...
0x180024d69  call    cs:__imp_ConvertStringSidToSidW
0x180024d6f  test    eax, eax
0x180024d71  jnz     short loc_180024DBF
0x180024d73  call    cs:__imp_GetLastError
0x180024d79  test    eax, eax
0x180024d7b  jg      short loc_180024D87
0x180024d7d  call    cs:__imp_GetLastError
0x180024d83  mov     ecx, eax
0x180024d85  jmp     short loc_180024D93
0x180024d87  call    cs:__imp_GetLastError
0x180024d8d  movzx   ecx, ax
0x180024d90  or      ecx, r13d
0x180024d93  mov     [rbp+57h+arg_0], ecx
0x180024d96  test    ecx, ecx
0x180024d98  jns     short loc_180024DBF
0x180024d9a  lea     rax, base
0x180024da1  mov     [rsp+0E0h+var_A0], rax
0x180024da6  lea     rax, aNtstatus; "NTSTATUS"
0x180024dad  mov     [rsp+0E0h+var_A8], rax
0x180024db2  mov     dword ptr [rsp+0E0h+var_B0], 0ADFh
0x180024dba  jmp     loc_180024AEB
0x180024dbf  lea     r8, [rbp+57h+var_78]; struct _TOKEN_GROUPS **
0x180024dc3  mov     rdx, rdi; void *
0x180024dc6  mov     rcx, rbx; struct AadContextFunctions *
0x180024dc9  call    ?GetCallerPackageCapabilities@@YAJPEAVAadContextFunctions@@PEAXPEAPEAU_TOKEN_GROUPS@@@Z; GetCallerPackageCapabilities(AadContextFunctions *,void *,_TOKEN_GROUPS * *)
0x180024dce  mov     edi, eax
0x180024dd0  mov     [rbp+57h+arg_0], eax
0x180024dd3  test    eax, eax
0x180024dd5  jns     short loc_180024E27
0x180024dd7  lea     rax, base
0x180024dde  mov     [rsp+0E0h+var_A0], rax
0x180024de3  lea     rax, aHresult; "HRESULT"
0x180024dea  mov     [rsp+0E0h+var_A8], rax
0x180024def  mov     dword ptr [rsp+0E0h+var_B0], 0AE2h
0x180024df7  mov     [rsp+0E0h+var_B8], r12
0x180024dfc  mov     dword ptr [rsp+0E0h+ReturnLength], edi
0x180024e00  mov     ecx, 2
0x180024e05  mov     r9d, ecx
0x180024e08  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024e0f  xor     edx, edx
0x180024e11  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024e16  btr     edi, 1Ch
0x180024e1a  bts     edi, 1Eh
0x180024e1e  mov     [rbp+57h+arg_0], edi
0x180024e21  mov     r14, [rbp+57h+var_78]
0x180024e25  jmp     short loc_180024E9D
0x180024e27  xor     edi, edi
0x180024e29  mov     r14, [rbp+57h+var_78]
0x180024e2d  test    r14, r14
0x180024e30  jz      short loc_180024E53
0x180024e32  cmp     edi, [r14]
0x180024e35  jnb     short loc_180024E53
0x180024e37  mov     ecx, edi
0x180024e39  add     rcx, rcx
0x180024e3c  mov     rdx, [rbp+57h+var_68]; Sid2
0x180024e40  mov     rcx, [r14+rcx*8+8]; Sid1
  ... truncated ...
```
