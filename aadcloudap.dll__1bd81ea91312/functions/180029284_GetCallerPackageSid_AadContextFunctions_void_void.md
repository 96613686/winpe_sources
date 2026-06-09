# GetCallerPackageSid(AadContextFunctions *,void *,void * *)

- ea: `0x180029284`
- end: `0x1800295e1`
- name: `?GetCallerPackageSid@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z`
- size: `861`
- prototype: `int(struct AadContextFunctions *, void *, void **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024314`
- `0x180024910`
- `0x180024f54`
- `0x18002904c`
- `0x180047320`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180029284`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002949d`
- `ntdll!RtlLengthSid` at `0x18002949d`
- `ntdll!NtQueryInformationToken` at `0x18002931a`
- `ntdll!NtQueryInformationToken` at `0x180029399`
- `ntdll!NtQueryInformationToken` at `0x180029436`
- `ntdll!NtQueryInformationToken` at `0x18002931a`
- `ntdll!NtQueryInformationToken` at `0x180029399`
- `ntdll!NtQueryInformationToken` at `0x180029436`
- `ntdll!RtlCopySid` at `0x1800294f2`
- `ntdll!RtlCopySid` at `0x1800294f2`

## string_xrefs

- `0x1800292c4`: `GetCallerPackageSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCallerPackageSid(struct AadContextFunctions *a1, void *a2, void **a3)
{
  NTSTATUS v6; // eax
  PSID *v7; // rsi
  void *v8; // rdi
  NTSTATUS v9; // eax
  void *v10; // rax
  unsigned int v11; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-39h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-39h]
  int v15; // [rsp+30h] [rbp-29h]
  int v16; // [rsp+30h] [rbp-29h]
  int TokenInformation; // [rsp+50h] [rbp-9h] BYREF
  const char *v18[7]; // [rsp+58h] [rbp-1h] BYREF
  int v19; // [rsp+C0h] [rbp+67h] BYREF
  ULONG TokenInformationLength; // [rsp+D8h] [rbp+7Fh] BYREF

  v19 = 0;
  TokenInformation = 0;
  TokenInformationLength = 4;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v18,
    (int)"login.cpp",
    (int)"GetCallerPackageSid",
    (int)&v19);
  if ( !a1 || !a2 || !a3 )
  {
    v6 = -1073741811;
    v15 = 2490;
    goto LABEL_26;
  }
  *a3 = 0;
  v6 = NtQueryInformationToken(
         a2,
         TokenIsAppContainer,
         &TokenInformation,
         TokenInformationLength,
         &TokenInformationLength);
  v19 = v6;
  if ( v6 < 0 )
  {
    v15 = 2495;
LABEL_27:
    LODWORD(ReturnLength) = v6;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v15, "NTSTATUS", &base);
    goto LABEL_28;
  }
  if ( !TokenInformation )
  {
    v6 = -1073741790;
    v15 = 2499;
LABEL_26:
    v19 = v6;
    goto LABEL_27;
  }
  TokenInformationLength = 0;
  v6 = NtQueryInformationToken(a2, TokenAppContainerSid, 0, 0, &TokenInformationLength);
  v19 = v6;
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741789 )
  {
    v15 = 2506;
    goto LABEL_27;
  }
  v7 = (PSID *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a1 + 24LL))(
                 a1,
                 TokenInformationLength);
  if ( !v7 )
  {
    v6 = -1073741801;
    v15 = 2512;
    goto LABEL_26;
  }
  v8 = 0;
  v9 = NtQueryInformationToken(a2, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength);
  v19 = v9;
  if ( v9 < 0 )
  {
    v16 = 2515;
LABEL_21:
    LODWORD(ReturnLengtha) = v9;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLengtha, "login.cpp", v16, "NTSTATUS", &base);
    goto LABEL_23;
  }
  if ( !*v7 )
  {
    v9 = -1073741801;
    v19 = -1073741801;
    v16 = 2519;
    goto LABEL_21;
  }
  TokenInformationLength = RtlLengthSid(*v7);
  v10 = (void *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a1 + 24LL))(
                  a1,
                  TokenInformationLength);
  v8 = v10;
  if ( !v10 )
  {
    v9 = -1073741801;
    v19 = -1073741801;
    v16 = 2526;
    goto LABEL_21;
  }
  v9 = RtlCopySid(TokenInformationLength, v10, *v7);
  v19 = v9;
  if ( v9 < 0 )
  {
    v16 = 2529;
    goto LABEL_21;
  }
  *a3 = v8;
  v8 = 0;
LABEL_23:
  (*(void (__fastcall **)(struct AadContextFunctions *, PSID *))(*(_QWORD *)a1 + 32LL))(a1, v7);
  if ( v8 )
    (*(void (__fastcall **)(struct AadContextFunctions *, void *))(*(_QWORD *)a1 + 32LL))(a1, v8);
LABEL_28:
  v11 = v19;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v18);
  return v11;
}

```

## disassembly

```asm
0x180029284  mov     [rsp-8+arg_8], rbx
0x180029289  mov     [rsp-8+arg_10], rsi
0x18002928e  push    rbp
0x18002928f  push    rdi
0x180029290  push    r13
0x180029292  push    r14
0x180029294  push    r15
0x180029296  lea     rbp, [rsp-37h]
0x18002929b  sub     rsp, 90h
0x1800292a2  mov     r15, r8
0x1800292a5  mov     r14, rdx
0x1800292a8  mov     rbx, rcx
0x1800292ab  mov     [rbp+57h+arg_0], 0
0x1800292b2  mov     [rbp+57h+TokenInformation], 0
0x1800292b9  mov     [rbp+57h+TokenInformationLength], 4
0x1800292c0  lea     r9, [rbp+57h+arg_0]
0x1800292c4  lea     r8, aGetcallerpacka_0; "GetCallerPackageSid"
0x1800292cb  lea     r13, aOnecoreuapDsEx_25+21h; "login.cpp"
0x1800292d2  mov     rdx, r13
0x1800292d5  lea     rcx, [rbp+57h+var_58]
0x1800292d9  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800292de  nop
0x1800292df  test    rbx, rbx
0x1800292e2  jz      loc_180029570
0x1800292e8  test    r14, r14
0x1800292eb  jz      loc_180029570
0x1800292f1  test    r15, r15
0x1800292f4  jz      loc_180029570
0x1800292fa  mov     qword ptr [r15], 0
0x180029301  lea     rax, [rbp+57h+TokenInformationLength]
0x180029305  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18002930a  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002930e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180029312  mov     edx, 1Dh; TokenInformationClass
0x180029317  mov     rcx, r14; TokenHandle
0x18002931a  call    cs:__imp_NtQueryInformationToken
0x180029320  mov     [rbp+57h+arg_0], eax
0x180029323  test    eax, eax
0x180029325  jns     short loc_18002934C
0x180029327  lea     rcx, base
0x18002932e  mov     [rsp+0B0h+var_70], rcx
0x180029333  lea     rcx, aNtstatus; "NTSTATUS"
0x18002933a  mov     [rsp+0B0h+var_78], rcx
0x18002933f  mov     [rsp+0B0h+var_80], 9BFh
0x180029347  jmp     loc_180029598
0x18002934c  cmp     [rbp+57h+TokenInformation], 0
0x180029350  jnz     short loc_18002937C
0x180029352  mov     eax, 0C0000022h
0x180029357  lea     rcx, base
0x18002935e  mov     [rsp+0B0h+var_70], rcx
0x180029363  lea     rcx, aNtstatus; "NTSTATUS"
0x18002936a  mov     [rsp+0B0h+var_78], rcx
0x18002936f  mov     [rsp+0B0h+var_80], 9C3h
0x180029377  jmp     loc_180029595
0x18002937c  mov     [rbp+57h+TokenInformationLength], 0
0x180029383  lea     rax, [rbp+57h+TokenInformationLength]
0x180029387  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18002938c  xor     r9d, r9d; TokenInformationLength
0x18002938f  xor     r8d, r8d; TokenInformation
0x180029392  lea     edx, [r9+1Fh]; TokenInformationClass
0x180029396  mov     rcx, r14; TokenHandle
0x180029399  call    cs:__imp_NtQueryInformationToken
0x18002939f  mov     [rbp+57h+arg_0], eax
0x1800293a2  mov     edx, 80000000h
0x1800293a7  lea     ecx, [rax+rdx]
0x1800293aa  test    edx, ecx
0x1800293ac  jnz     short loc_1800293DA
0x1800293ae  cmp     eax, 0C0000023h
0x1800293b3  jz      short loc_1800293DA
0x1800293b5  lea     rcx, base
0x1800293bc  mov     [rsp+0B0h+var_70], rcx
0x1800293c1  lea     rcx, aNtstatus; "NTSTATUS"
0x1800293c8  mov     [rsp+0B0h+var_78], rcx
0x1800293cd  mov     [rsp+0B0h+var_80], 9CAh
0x1800293d5  jmp     loc_180029598
0x1800293da  mov     rax, [rbx]
0x1800293dd  mov     edx, [rbp+57h+TokenInformationLength]
0x1800293e0  mov     rcx, rbx
0x1800293e3  mov     rax, [rax+18h]
0x1800293e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293ec  mov     rsi, rax
0x1800293ef  test    rax, rax
0x1800293f2  jnz     short loc_18002941E
0x1800293f4  mov     eax, 0C0000017h
0x1800293f9  lea     rcx, base
0x180029400  mov     [rsp+0B0h+var_70], rcx
0x180029405  lea     rcx, aNtstatus; "NTSTATUS"
0x18002940c  mov     [rsp+0B0h+var_78], rcx
0x180029411  mov     [rsp+0B0h+var_80], 9D0h
0x180029419  jmp     loc_180029595
0x18002941e  xor     edi, edi
0x180029420  lea     rax, [rbp+57h+TokenInformationLength]
0x180029424  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180029429  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002942d  mov     r8, rsi; TokenInformation
0x180029430  lea     edx, [rdi+1Fh]; TokenInformationClass
0x180029433  mov     rcx, r14; TokenHandle
0x180029436  call    cs:__imp_NtQueryInformationToken
0x18002943c  mov     [rbp+57h+arg_0], eax
0x18002943f  test    eax, eax
0x180029441  jns     short loc_180029468
0x180029443  lea     rcx, base
0x18002944a  mov     [rsp+0B0h+var_70], rcx
0x18002944f  lea     rcx, aNtstatus; "NTSTATUS"
0x180029456  mov     [rsp+0B0h+var_78], rcx
0x18002945b  mov     [rsp+0B0h+var_80], 9D3h
0x180029463  jmp     loc_18002951F
0x180029468  mov     rcx, [rsi]; Sid
0x18002946b  test    rcx, rcx
0x18002946e  jnz     short loc_18002949D
0x180029470  mov     eax, 0C0000017h
0x180029475  mov     [rbp+57h+arg_0], eax
0x180029478  lea     rcx, base
0x18002947f  mov     [rsp+0B0h+var_70], rcx
0x180029484  lea     rcx, aNtstatus; "NTSTATUS"
0x18002948b  mov     [rsp+0B0h+var_78], rcx
0x180029490  mov     [rsp+0B0h+var_80], 9D7h
0x180029498  jmp     loc_18002951F
0x18002949d  call    cs:__imp_RtlLengthSid
0x1800294a3  mov     edx, eax
0x1800294a5  mov     [rbp+57h+TokenInformationLength], eax
0x1800294a8  mov     rcx, [rbx]
0x1800294ab  mov     rax, [rcx+18h]
0x1800294af  mov     rcx, rbx
0x1800294b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294b7  mov     rdi, rax
0x1800294ba  test    rax, rax
0x1800294bd  jnz     short loc_1800294E9
0x1800294bf  mov     eax, 0C0000017h
0x1800294c4  mov     [rbp+57h+arg_0], eax
0x1800294c7  lea     rcx, base
0x1800294ce  mov     [rsp+0B0h+var_70], rcx
0x1800294d3  lea     rcx, aNtstatus; "NTSTATUS"
0x1800294da  mov     [rsp+0B0h+var_78], rcx
0x1800294df  mov     [rsp+0B0h+var_80], 9DEh
0x1800294e7  jmp     short loc_18002951F
0x1800294e9  mov     r8, [rsi]; SourceSid
0x1800294ec  mov     rdx, rdi; DestinationSid
0x1800294ef  mov     ecx, [rbp+57h+TokenInformationLength]; DestinationSidLength
0x1800294f2  call    cs:__imp_RtlCopySid
0x1800294f8  mov     [rbp+57h+arg_0], eax
0x1800294fb  test    eax, eax
0x1800294fd  jns     short loc_180029540
0x1800294ff  lea     rcx, base
0x180029506  mov     [rsp+0B0h+var_70], rcx
0x18002950b  lea     rcx, aNtstatus; "NTSTATUS"
0x180029512  mov     [rsp+0B0h+var_78], rcx
0x180029517  mov     [rsp+0B0h+var_80], 9E1h
0x18002951f  mov     [rsp+0B0h+var_88], r13
0x180029524  mov     dword ptr [rsp+0B0h+ReturnLength], eax
0x180029528  mov     ecx, 2
0x18002952d  mov     r9d, ecx
0x180029530  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180029537  xor     edx, edx
0x180029539  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002953e  jmp     short loc_180029545
0x180029540  mov     [r15], rdi
0x180029543  xor     edi, edi
0x180029545  mov     rax, [rbx]
0x180029548  mov     rdx, rsi
0x18002954b  mov     rcx, rbx
0x18002954e  mov     rax, [rax+20h]
0x180029552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029557  test    rdi, rdi
0x18002955a  jz      short loc_1800295B7
0x18002955c  mov     rax, [rbx]
0x18002955f  mov     rdx, rdi
0x180029562  mov     rcx, rbx
0x180029565  mov     rax, [rax+20h]
0x180029569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002956e  jmp     short loc_1800295B7
0x180029570  mov     eax, 0C000000Dh
0x180029575  lea     rcx, base
0x18002957c  mov     [rsp+0B0h+var_70], rcx
0x180029581  lea     rcx, aNtstatus; "NTSTATUS"
0x180029588  mov     [rsp+0B0h+var_78], rcx
0x18002958d  mov     [rsp+0B0h+var_80], 9BAh
0x180029595  mov     [rbp+57h+arg_0], eax
0x180029598  mov     [rsp+0B0h+var_88], r13
0x18002959d  mov     ecx, 2
0x1800295a2  mov     dword ptr [rsp+0B0h+ReturnLength], eax
0x1800295a6  mov     r9d, ecx
0x1800295a9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800295b0  xor     edx, edx
0x1800295b2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800295b7  mov     ebx, [rbp+57h+arg_0]
0x1800295ba  lea     rcx, [rbp+57h+var_58]
0x1800295be  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800295c3  mov     eax, ebx
0x1800295c5  lea     r11, [rsp+0B0h+var_20]
0x1800295cd  mov     rbx, [r11+38h]
0x1800295d1  mov     rsi, [r11+40h]
0x1800295d5  mov     rsp, r11
0x1800295d8  pop     r15
0x1800295da  pop     r14
0x1800295dc  pop     r13
0x1800295de  pop     rdi
0x1800295df  pop     rbp
0x1800295e0  retn
```
