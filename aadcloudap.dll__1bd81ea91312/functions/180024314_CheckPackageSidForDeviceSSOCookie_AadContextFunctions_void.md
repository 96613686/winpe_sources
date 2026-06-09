# CheckPackageSidForDeviceSSOCookie(AadContextFunctions *,void *)

- ea: `0x180024314`
- end: `0x180024909`
- name: `?CheckPackageSidForDeviceSSOCookie@@YAJPEAVAadContextFunctions@@PEAX@Z`
- size: `1525`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043ef4`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180024314`
- `0x180028e50`
- `0x180029284`
- `0x18002a910`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002453c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002473b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002453c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002473b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024745`
- `ntdll!RtlEqualSid` at `0x1800246e4`
- `ntdll!RtlEqualSid` at `0x1800246f9`
- `ntdll!RtlEqualSid` at `0x18002470e`
- `ntdll!RtlEqualSid` at `0x180024803`
- `ntdll!RtlEqualSid` at `0x1800246e4`
- `ntdll!RtlEqualSid` at `0x1800246f9`
- `ntdll!RtlEqualSid` at `0x18002470e`
- `ntdll!RtlEqualSid` at `0x180024803`
- `ntdll!NtQueryInformationToken` at `0x1800243f5`
- `ntdll!NtQueryInformationToken` at `0x1800243f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024498`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024532`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024727`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024498`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024532`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180024727`

## string_xrefs

- `0x180024372`: `CheckPackageSidForDeviceSSOCookie`

## pseudocode

```c
__int64 __fastcall CheckPackageSidForDeviceSSOCookie(struct AadContextFunctions *a1, void *a2)
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
  PSID v16; // [rsp+60h] [rbp-29h] BYREF
  PSID Sid2; // [rsp+68h] [rbp-21h] BYREF
  struct _TOKEN_GROUPS *v18; // [rsp+70h] [rbp-19h] BYREF
  PSID v19; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v20[96]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v21; // [rsp+F0h] [rbp+67h] BYREF
  int TokenInformation; // [rsp+100h] [rbp+77h] BYREF
  ULONG TokenInformationLength; // [rsp+108h] [rbp+7Fh] BYREF

  v21 = 0;
  TokenInformation = 0;
  TokenInformationLength = 4;
  Sid = 0;
  Sid1 = 0;
  v4 = 0;
  Sid2 = 0;
  v16 = 0;
  v19 = 0;
  v5 = 0;
  v18 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v20,
    "login.cpp",
    "CheckPackageSidForDeviceSSOCookie",
    &v21);
  if ( !a1 )
  {
    v21 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "login.cpp", 2857, "NTSTATUS", &base);
    goto LABEL_59;
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
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "login.cpp", 2862, "lowboxCaller", TokenInformation);
    if ( !TokenInformation )
      goto LABEL_47;
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
        if ( ConvertStringSidToSidW(
               L"S-1-15-2-2434737943-167758768-3180539153-984336765-1107280622-3591121930-2677285773",
               &Sid1)
          || ((int)GetLastError() > 0
            ? (TokenBrokerPluginSID = (unsigned __int16)GetLastError() | 0xC0070000)
            : (TokenBrokerPluginSID = GetLastError()),
              v21 = TokenBrokerPluginSID,
              TokenBrokerPluginSID >= 0) )
        {
          if ( Sid1 )
          {
            TokenBrokerPluginSID = GetTokenBrokerPluginSID(&v16);
            v21 = TokenBrokerPluginSID;
            if ( TokenBrokerPluginSID >= 0 )
            {
              if ( v16 )
              {
                CallerPackageSid = GetCallerPackageSid(a1, a2, &Sid2);
                v21 = CallerPackageSid;
                if ( CallerPackageSid < 0 )
                {
                  LODWORD(v13) = 2892;
                  LODWORD(ReturnLength) = CallerPackageSid;
                  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "NTSTATUS", &base);
                  v4 = Sid2;
                  goto LABEL_47;
                }
                v4 = Sid2;
                if ( !Sid2 )
                {
                  LODWORD(v13) = 2896;
                  LODWORD(ReturnLength) = -2147187437;
                  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                  v21 = -1073445613;
                  goto LABEL_47;
                }
                if ( RtlEqualSid(Sid, Sid2) || RtlEqualSid(Sid1, v4) || RtlEqualSid(v16, v4) )
                  goto LABEL_47;
                if ( ConvertStringSidToSidW(
                       L"S-1-15-3-1024-983922258-2159917625-2751362240-3284369410-2497023943-943411171-3503282929-3741434461",
                       &v19)
                  || ((int)GetLastError() > 0
                    ? (TokenBrokerPluginSID = (unsigned __int16)GetLastError() | 0xC0070000)
                    : (TokenBrokerPluginSID = GetLastError()),
                      v21 = TokenBrokerPluginSID,
                      TokenBrokerPluginSID >= 0) )
                {
                  CallerPackageCapabilities = GetCallerPackageCapabilities(a1, a2, &v18);
                  v21 = CallerPackageCapabilities;
                  if ( CallerPackageCapabilities >= 0 )
                  {
                    v9 = 0;
                    v5 = v18;
                    if ( v18 )
                    {
                      while ( v9 < v5->GroupCount )
                      {
                        if ( RtlEqualSid(v5->Groups[v9].Sid, v19) )
                          goto LABEL_47;
                        ++v9;
                      }
                    }
                    LODWORD(v13) = 2919;
                    LODWORD(ReturnLength) = -2147187435;
                    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                    v21 = -1073445611;
                  }
                  else
                  {
                    LODWORD(v13) = 2908;
                    LODWORD(ReturnLength) = CallerPackageCapabilities;
                    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "HRESULT", &base);
                    v21 = CallerPackageCapabilities & 0xAFFFFFFF | 0x40000000;
                    v5 = v18;
                  }
                  goto LABEL_47;
                }
                LODWORD(v13) = 2905;
              }
              else
              {
                TokenBrokerPluginSID = -1073741595;
                v21 = -1073741595;
                LODWORD(v13) = 2889;
              }
            }
            else
            {
              LODWORD(v13) = 2886;
            }
          }
          else
          {
            TokenBrokerPluginSID = -1073741595;
            v21 = -1073741595;
            LODWORD(v13) = 2883;
          }
        }
        else
        {
          LODWORD(v13) = 2879;
        }
      }
      else
      {
        TokenBrokerPluginSID = -1073741595;
        v21 = -1073741595;
        LODWORD(v13) = 2874;
      }
    }
    else
    {
      LODWORD(v13) = 2870;
    }
  }
  else
  {
    LODWORD(v13) = 2860;
  }
  LODWORD(ReturnLength) = TokenBrokerPluginSID;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "NTSTATUS", &base);
LABEL_47:
  if ( Sid )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( Sid1 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v4 )
    (*(void (__fastcall **)(struct AadContextFunctions *, PSID))(*(_QWORD *)a1 + 32LL))(a1, v4);
  if ( v16 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v19 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v5 )
    (*(void (__fastcall **)(struct AadContextFunctions *, struct _TOKEN_GROUPS *))(*(_QWORD *)a1 + 32LL))(a1, v5);
LABEL_59:
  v10 = v21;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v20);
  return v10;
}

```

## disassembly

```asm
0x180024314  push    rbp
0x180024316  push    rbx
0x180024317  push    rsi
0x180024318  push    rdi
0x180024319  push    r12
0x18002431b  push    r13
0x18002431d  push    r14
0x18002431f  lea     rbp, [rsp-27h]
0x180024324  sub     rsp, 0B0h
0x18002432b  mov     rdi, rdx
0x18002432e  mov     rbx, rcx
0x180024331  mov     [rbp+57h+arg_0], 0
0x180024338  mov     [rbp+57h+TokenInformation], 0
0x18002433f  mov     r13d, 4
0x180024345  mov     [rbp+57h+TokenInformationLength], r13d
0x180024349  mov     [rbp+57h+Sid], 0
0x180024351  mov     [rbp+57h+Sid1], 0
0x180024359  xor     esi, esi
0x18002435b  mov     [rbp+57h+Sid2], rsi
0x18002435f  mov     [rbp+57h+var_80], rsi
0x180024363  mov     [rbp+57h+var_68], rsi
0x180024367  xor     r14d, r14d
0x18002436a  mov     [rbp+57h+var_70], r14
0x18002436e  lea     r9, [rbp+57h+arg_0]
0x180024372  lea     r8, aCheckpackagesi; "CheckPackageSidForDeviceSSOCookie"
0x180024379  lea     r12, aOnecoreuapDsEx_25+21h; "login.cpp"
0x180024380  mov     rdx, r12
0x180024383  lea     rcx, [rbp+57h+var_60]
0x180024387  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18002438c  nop
0x18002438d  test    rbx, rbx
0x180024390  jnz     short loc_1800243DC
0x180024392  mov     ecx, 0C000000Dh
0x180024397  mov     [rbp+57h+arg_0], ecx
0x18002439a  lea     rax, base
0x1800243a1  mov     [rsp+0E0h+var_A0], rax
0x1800243a6  lea     rax, aNtstatus; "NTSTATUS"
0x1800243ad  mov     [rsp+0E0h+var_A8], rax
0x1800243b2  mov     dword ptr [rsp+0E0h+var_B0], 0B29h
0x1800243ba  mov     [rsp+0E0h+var_B8], r12
0x1800243bf  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x1800243c3  lea     ecx, [rsi+2]
0x1800243c6  mov     r9d, ecx
0x1800243c9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800243d0  xor     edx, edx
0x1800243d2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800243d7  jmp     loc_1800248E9
0x1800243dc  lea     rax, [rbp+57h+TokenInformationLength]
0x1800243e0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800243e5  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800243e9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800243ed  mov     edx, 1Dh; TokenInformationClass
0x1800243f2  mov     rcx, rdi; TokenHandle
0x1800243f5  call    cs:__imp_NtQueryInformationToken
0x1800243fb  mov     ecx, eax
0x1800243fd  mov     [rbp+57h+arg_0], eax
0x180024400  xor     edx, edx
0x180024402  test    eax, eax
0x180024404  jns     short loc_180024448
0x180024406  lea     rax, base
0x18002440d  mov     [rsp+0E0h+var_A0], rax
0x180024412  lea     rax, aNtstatus; "NTSTATUS"
0x180024419  mov     [rsp+0E0h+var_A8], rax
0x18002441e  mov     dword ptr [rsp+0E0h+var_B0], 0B2Ch
0x180024426  mov     [rsp+0E0h+var_B8], r12
0x18002442b  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x18002442f  mov     ecx, 2
0x180024434  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002443b  mov     r9d, ecx
0x18002443e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024443  jmp     loc_18002485B
0x180024448  mov     eax, [rbp+57h+TokenInformation]
0x18002444b  mov     dword ptr [rsp+0E0h+var_A0], eax
0x18002444f  lea     rax, aLowboxcaller; "lowboxCaller"
0x180024456  mov     [rsp+0E0h+var_A8], rax
0x18002445b  mov     dword ptr [rsp+0E0h+var_B0], 0B2Eh
0x180024463  mov     [rsp+0E0h+var_B8], r12
0x180024468  mov     [rsp+0E0h+ReturnLength], 0
0x180024471  mov     r9d, r13d
0x180024474  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18002447b  mov     ecx, r13d
0x18002447e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180024483  cmp     [rbp+57h+TokenInformation], 0
0x180024487  jz      loc_18002485B
0x18002448d  lea     rdx, [rbp+57h+Sid]; Sid
0x180024491  lea     rcx, aS1152362405143; "S-1-15-2-3624051433-2125758914-14231912"...
0x180024498  call    cs:__imp_ConvertStringSidToSidW
0x18002449e  mov     r13d, 0C0070000h
0x1800244a4  test    eax, eax
0x1800244a6  jnz     short loc_1800244F6
0x1800244a8  call    cs:__imp_GetLastError
0x1800244ae  test    eax, eax
0x1800244b0  jg      short loc_1800244BC
0x1800244b2  call    cs:__imp_GetLastError
0x1800244b8  mov     ecx, eax
0x1800244ba  jmp     short loc_1800244C8
0x1800244bc  call    cs:__imp_GetLastError
0x1800244c2  movzx   ecx, ax
0x1800244c5  or      ecx, r13d
0x1800244c8  mov     [rbp+57h+arg_0], ecx
0x1800244cb  test    ecx, ecx
0x1800244cd  jns     short loc_1800244F6
0x1800244cf  lea     rax, base
0x1800244d6  mov     [rsp+0E0h+var_A0], rax
0x1800244db  lea     rax, aNtstatus; "NTSTATUS"
0x1800244e2  mov     [rsp+0E0h+var_A8], rax
0x1800244e7  mov     dword ptr [rsp+0E0h+var_B0], 0B36h
0x1800244ef  xor     edx, edx
0x1800244f1  jmp     loc_180024426
0x1800244f6  cmp     [rbp+57h+Sid], 0
0x1800244fb  jnz     short loc_180024527
0x1800244fd  mov     ecx, 0C00000E5h
0x180024502  mov     [rbp+57h+arg_0], ecx
0x180024505  lea     rax, base
0x18002450c  mov     [rsp+0E0h+var_A0], rax
0x180024511  lea     rax, aNtstatus; "NTSTATUS"
0x180024518  mov     [rsp+0E0h+var_A8], rax
0x18002451d  mov     dword ptr [rsp+0E0h+var_B0], 0B3Ah
0x180024525  jmp     short loc_1800244EF
0x180024527  lea     rdx, [rbp+57h+Sid1]; Sid
0x18002452b  lea     rcx, aS1152243473794; "S-1-15-2-2434737943-167758768-318053915"...
0x180024532  call    cs:__imp_ConvertStringSidToSidW
0x180024538  test    eax, eax
0x18002453a  jnz     short loc_180024588
0x18002453c  call    cs:__imp_GetLastError
0x180024542  test    eax, eax
0x180024544  jg      short loc_180024550
0x180024546  call    cs:__imp_GetLastError
0x18002454c  mov     ecx, eax
0x18002454e  jmp     short loc_18002455C
0x180024550  call    cs:__imp_GetLastError
0x180024556  movzx   ecx, ax
0x180024559  or      ecx, r13d
0x18002455c  mov     [rbp+57h+arg_0], ecx
0x18002455f  test    ecx, ecx
0x180024561  jns     short loc_180024588
0x180024563  lea     rax, base
0x18002456a  mov     [rsp+0E0h+var_A0], rax
0x18002456f  lea     rax, aNtstatus; "NTSTATUS"
0x180024576  mov     [rsp+0E0h+var_A8], rax
0x18002457b  mov     dword ptr [rsp+0E0h+var_B0], 0B3Fh
0x180024583  jmp     loc_1800244EF
0x180024588  cmp     [rbp+57h+Sid1], 0
0x18002458d  jnz     short loc_1800245BC
0x18002458f  mov     ecx, 0C00000E5h
0x180024594  mov     [rbp+57h+arg_0], ecx
0x180024597  lea     rax, base
0x18002459e  mov     [rsp+0E0h+var_A0], rax
0x1800245a3  lea     rax, aNtstatus; "NTSTATUS"
0x1800245aa  mov     [rsp+0E0h+var_A8], rax
0x1800245af  mov     dword ptr [rsp+0E0h+var_B0], 0B43h
0x1800245b7  jmp     loc_1800244EF
0x1800245bc  lea     rcx, [rbp+57h+var_80]; Sid
0x1800245c0  call    ?GetTokenBrokerPluginSID@@YAJPEAPEAX@Z; GetTokenBrokerPluginSID(void * *)
0x1800245c5  mov     ecx, eax
0x1800245c7  mov     [rbp+57h+arg_0], eax
0x1800245ca  test    eax, eax
0x1800245cc  jns     short loc_1800245F3
0x1800245ce  lea     rax, base
0x1800245d5  mov     [rsp+0E0h+var_A0], rax
0x1800245da  lea     rax, aNtstatus; "NTSTATUS"
0x1800245e1  mov     [rsp+0E0h+var_A8], rax
0x1800245e6  mov     dword ptr [rsp+0E0h+var_B0], 0B46h
0x1800245ee  jmp     loc_1800244EF
0x1800245f3  cmp     [rbp+57h+var_80], 0
0x1800245f8  jnz     short loc_180024627
0x1800245fa  mov     ecx, 0C00000E5h
0x1800245ff  mov     [rbp+57h+arg_0], ecx
0x180024602  lea     rax, base
0x180024609  mov     [rsp+0E0h+var_A0], rax
0x18002460e  lea     rax, aNtstatus; "NTSTATUS"
0x180024615  mov     [rsp+0E0h+var_A8], rax
0x18002461a  mov     dword ptr [rsp+0E0h+var_B0], 0B49h
0x180024622  jmp     loc_1800244EF
0x180024627  lea     r8, [rbp+57h+Sid2]; void **
0x18002462b  mov     rdx, rdi; void *
0x18002462e  mov     rcx, rbx; struct AadContextFunctions *
0x180024631  call    ?GetCallerPackageSid@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; GetCallerPackageSid(AadContextFunctions *,void *,void * *)
0x180024636  mov     ecx, eax
0x180024638  mov     [rbp+57h+arg_0], eax
0x18002463b  test    eax, eax
0x18002463d  jns     short loc_180024687
0x18002463f  lea     rax, base
0x180024646  mov     [rsp+0E0h+var_A0], rax
0x18002464b  lea     rax, aNtstatus; "NTSTATUS"
0x180024652  mov     [rsp+0E0h+var_A8], rax
0x180024657  mov     dword ptr [rsp+0E0h+var_B0], 0B4Ch
0x18002465f  mov     [rsp+0E0h+var_B8], r12
0x180024664  mov     dword ptr [rsp+0E0h+ReturnLength], ecx
0x180024668  mov     ecx, 2
0x18002466d  mov     r9d, ecx
0x180024670  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180024677  xor     edx, edx
0x180024679  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002467e  mov     rsi, [rbp+57h+Sid2]
0x180024682  jmp     loc_18002485B
0x180024687  mov     rsi, [rbp+57h+Sid2]
0x18002468b  test    rsi, rsi
0x18002468e  jnz     short loc_1800246DD
0x180024690  lea     rax, base
0x180024697  mov     [rsp+0E0h+var_A0], rax
0x18002469c  lea     rax, aHresult; "HRESULT"
0x1800246a3  mov     [rsp+0E0h+var_A8], rax
0x1800246a8  mov     dword ptr [rsp+0E0h+var_B0], 0B50h
0x1800246b0  mov     [rsp+0E0h+var_B8], r12
0x1800246b5  mov     dword ptr [rsp+0E0h+ReturnLength], 80048513h
0x1800246bd  lea     ecx, [rsi+2]
0x1800246c0  mov     r9d, ecx
0x1800246c3  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800246ca  xor     edx, edx
0x1800246cc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800246d1  mov     [rbp+57h+arg_0], 0C0048513h
0x1800246d8  jmp     loc_18002485B
0x1800246dd  mov     rdx, rsi; Sid2
0x1800246e0  mov     rcx, [rbp+57h+Sid]; Sid1
0x1800246e4  call    cs:__imp_RtlEqualSid
0x1800246ea  test    al, al
0x1800246ec  jnz     loc_18002485B
0x1800246f2  mov     rdx, rsi; Sid2
0x1800246f5  mov     rcx, [rbp+57h+Sid1]; Sid1
0x1800246f9  call    cs:__imp_RtlEqualSid
0x1800246ff  test    al, al
0x180024701  jnz     loc_18002485B
0x180024707  mov     rdx, rsi; Sid2
0x18002470a  mov     rcx, [rbp+57h+var_80]; Sid1
0x18002470e  call    cs:__imp_RtlEqualSid
0x180024714  test    al, al
0x180024716  jnz     loc_18002485B
0x18002471c  lea     rdx, [rbp+57h+var_68]; Sid
0x180024720  lea     rcx, aS1153102498392; "S-1-15-3-1024-983922258-2159917625-2751"...
0x180024727  call    cs:__imp_ConvertStringSidToSidW
0x18002472d  test    eax, eax
0x18002472f  jnz     short loc_18002477D
0x180024731  call    cs:__imp_GetLastError
0x180024737  test    eax, eax
0x180024739  jg      short loc_180024745
0x18002473b  call    cs:__imp_GetLastError
0x180024741  mov     ecx, eax
0x180024743  jmp     short loc_180024751
0x180024745  call    cs:__imp_GetLastError
0x18002474b  movzx   ecx, ax
0x18002474e  or      ecx, r13d
0x180024751  mov     [rbp+57h+arg_0], ecx
0x180024754  test    ecx, ecx
0x180024756  jns     short loc_18002477D
0x180024758  lea     rax, base
0x18002475f  mov     [rsp+0E0h+var_A0], rax
0x180024764  lea     rax, aNtstatus; "NTSTATUS"
0x18002476b  mov     [rsp+0E0h+var_A8], rax
0x180024770  mov     dword ptr [rsp+0E0h+var_B0], 0B59h
0x180024778  jmp     loc_1800244EF
0x18002477d  lea     r8, [rbp+57h+var_70]; struct _TOKEN_GROUPS **
0x180024781  mov     rdx, rdi; void *
0x180024784  mov     rcx, rbx; struct AadContextFunctions *
0x180024787  call    ?GetCallerPackageCapabilities@@YAJPEAVAadContextFunctions@@PEAXPEAPEAU_TOKEN_GROUPS@@@Z; GetCallerPackageCapabilities(AadContextFunctions *,void *,_TOKEN_GROUPS * *)
0x18002478c  mov     edi, eax
0x18002478e  mov     [rbp+57h+arg_0], eax
0x180024791  test    eax, eax
0x180024793  jns     short loc_1800247E5
0x180024795  lea     rax, base
0x18002479c  mov     [rsp+0E0h+var_A0], rax
0x1800247a1  lea     rax, aHresult; "HRESULT"
0x1800247a8  mov     [rsp+0E0h+var_A8], rax
0x1800247ad  mov     dword ptr [rsp+0E0h+var_B0], 0B5Ch
0x1800247b5  mov     [rsp+0E0h+var_B8], r12
0x1800247ba  mov     dword ptr [rsp+0E0h+ReturnLength], edi
0x1800247be  mov     ecx, 2
0x1800247c3  mov     r9d, ecx
0x1800247c6  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800247cd  xor     edx, edx
0x1800247cf  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800247d4  btr     edi, 1Ch
0x1800247d8  bts     edi, 1Eh
0x1800247dc  mov     [rbp+57h+arg_0], edi
0x1800247df  mov     r14, [rbp+57h+var_70]
0x1800247e3  jmp     short loc_18002485B
0x1800247e5  xor     edi, edi
0x1800247e7  mov     r14, [rbp+57h+var_70]
0x1800247eb  test    r14, r14
0x1800247ee  jz      short loc_180024811
0x1800247f0  cmp     edi, [r14]
0x1800247f3  jnb     short loc_180024811
0x1800247f5  mov     ecx, edi
0x1800247f7  add     rcx, rcx
0x1800247fa  mov     rdx, [rbp+57h+var_68]; Sid2
0x1800247fe  mov     rcx, [r14+rcx*8+8]; Sid1
0x180024803  call    cs:__imp_RtlEqualSid
0x180024809  test    al, al
0x18002480b  jnz     short loc_18002485B
0x18002480d  inc     edi
0x18002480f  jmp     short loc_1800247F0
0x180024811  lea     rax, base
0x180024818  mov     [rsp+0E0h+var_A0], rax
0x18002481d  lea     rax, aHresult; "HRESULT"
0x180024824  mov     [rsp+0E0h+var_A8], rax
0x180024829  mov     dword ptr [rsp+0E0h+var_B0], 0B67h
0x180024831  mov     [rsp+0E0h+var_B8], r12
0x180024836  mov     dword ptr [rsp+0E0h+ReturnLength], 80048515h
0x18002483e  mov     ecx, 2
0x180024843  mov     r9d, ecx
  ... truncated ...
```
