# P2PCertificatesHelper::SetSecurityDescriptor(AadContextFunctions *,unsigned __int64,_ACL * const,bool)

- ea: `0x180050674`
- end: `0x18005097d`
- name: `?SetSecurityDescriptor@P2PCertificatesHelper@@CAJPEAVAadContextFunctions@@_KQEAU_ACL@@_N@Z`
- size: `777`
- prototype: `static int(struct AadContextFunctions *, unsigned __int64, struct _ACL *const, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e2b8`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180050674`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005073c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800507e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005073c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800507e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050846`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005072c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005072c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180050787`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180050787`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800507d9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800507d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180050885`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180050885`
- `ncrypt!NCryptIsKeyHandle` at `0x180050821`
- `ncrypt!NCryptIsKeyHandle` at `0x180050821`
- `ncrypt!NCryptSetProperty` at `0x1800508a3`
- `ncrypt!NCryptSetProperty` at `0x1800508a3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetProvParam` at `0x180050838`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetProvParam` at `0x180050838`

## string_xrefs

- `0x180050899`: `Security Descr`
- `0x1800506a4`: `P2PCertificatesHelper::SetSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall P2PCertificatesHelper::SetSecurityDescriptor(
        struct AadContextFunctions *a1,
        HCRYPTPROV a2,
        struct _ACL *const a3,
        char a4)
{
  void *v8; // rax
  void *v9; // rdi
  int v10; // ecx
  signed int LastError; // eax
  int v12; // ebx
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  DWORD SecurityDescriptorLength; // eax
  unsigned int v17; // ebx
  __int64 dwFlags; // [rsp+20h] [rbp-49h]
  int v20; // [rsp+30h] [rbp-39h]
  int v21; // [rsp+30h] [rbp-39h]
  const char *v22[14]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v23; // [rsp+D0h] [rbp+67h] BYREF

  v23 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v22,
    (int)"p2pcertificateshelper.cpp",
    (int)"P2PCertificatesHelper::SetSecurityDescriptor",
    (int)&v23);
  if ( !a1 || !a2 || !a3 )
  {
    v10 = -1073741811;
    v20 = 820;
    goto LABEL_33;
  }
  v8 = (void *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, __int64))(*(_QWORD *)a1 + 8LL))(
                 a1,
                 64,
                 40);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -1073741801;
    v20 = 826;
LABEL_33:
    v23 = v10;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v10, "p2pcertificateshelper.cpp", v20, "NTSTATUS", &base);
    goto LABEL_34;
  }
  if ( !InitializeSecurityDescriptor(v8, 1u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 )
    {
      v21 = 831;
LABEL_30:
      LODWORD(dwFlags) = v12;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, dwFlags, "p2pcertificateshelper.cpp", v21, "HRESULT", &base);
      v23 = v12 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_31;
    }
  }
  if ( a4 && !SetSecurityDescriptorControl(v9, 0x1000u, 0x1000u) )
  {
    v13 = GetLastError();
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
    if ( v12 < 0 )
    {
      v21 = 839;
      goto LABEL_30;
    }
  }
  if ( !SetSecurityDescriptorDacl(v9, 1, a3, 0) )
  {
    v14 = GetLastError();
    v12 = v14;
    if ( v14 > 0 )
      v12 = (unsigned __int16)v14 | 0x80070000;
    if ( v12 < 0 )
    {
      v21 = 846;
      goto LABEL_30;
    }
  }
  if ( !NCryptIsKeyHandle(a2) )
  {
    if ( CryptSetProvParam(a2, 8u, (const BYTE *)v9, 4u) )
      goto LABEL_31;
    v15 = GetLastError();
    v12 = v15;
    if ( v15 > 0 )
      v12 = (unsigned __int16)v15 | 0x80070000;
    if ( v12 >= 0 )
      goto LABEL_31;
    v21 = 853;
    goto LABEL_30;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(v9);
  v12 = NCryptSetProperty(a2, L"Security Descr", (PBYTE)v9, SecurityDescriptorLength, 4u);
  if ( v12 < 0 )
  {
    v21 = 859;
    goto LABEL_30;
  }
LABEL_31:
  (*(void (__fastcall **)(struct AadContextFunctions *, void *))(*(_QWORD *)a1 + 16LL))(a1, v9);
LABEL_34:
  v17 = v23;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v22);
  return v17;
}

```

## disassembly

```asm
0x180050674  push    rbp
0x180050676  push    rbx
0x180050677  push    rsi
0x180050678  push    rdi
0x180050679  push    r12
0x18005067b  push    r13
0x18005067d  push    r14
0x18005067f  push    r15
0x180050681  lea     rbp, [rsp-1Fh]
0x180050686  sub     rsp, 88h
0x18005068d  mov     r12b, r9b
0x180050690  mov     r15, r8
0x180050693  mov     rsi, rdx
0x180050696  mov     r14, rcx
0x180050699  mov     [rbp+57h+arg_0], 0
0x1800506a0  lea     r9, [rbp+57h+arg_0]
0x1800506a4  lea     r8, aP2pcertificate_4; "P2PCertificatesHelper::SetSecurityDescr"...
0x1800506ab  lea     rbx, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x1800506b2  mov     rdx, rbx
0x1800506b5  lea     rcx, [rbp+57h+var_70]
0x1800506b9  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800506be  nop
0x1800506bf  test    r14, r14
0x1800506c2  jz      loc_180050914
0x1800506c8  test    rsi, rsi
0x1800506cb  jz      loc_180050914
0x1800506d1  test    r15, r15
0x1800506d4  jz      loc_180050914
0x1800506da  mov     rax, [r14]
0x1800506dd  mov     edx, 40h ; '@'
0x1800506e2  lea     r8d, [rdx-18h]
0x1800506e6  mov     rcx, r14
0x1800506e9  mov     rax, [rax+8]
0x1800506ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506f2  mov     rdi, rax
0x1800506f5  test    rax, rax
0x1800506f8  jnz     short loc_180050724
0x1800506fa  mov     ecx, 0C0000017h
0x1800506ff  lea     rax, base
0x180050706  mov     [rsp+0C0h+var_80], rax
0x18005070b  lea     rax, aNtstatus; "NTSTATUS"
0x180050712  mov     [rsp+0C0h+var_88], rax
0x180050717  mov     [rsp+0C0h+var_90], 33Ah
0x18005071f  jmp     loc_180050939
0x180050724  mov     edx, 1; dwRevision
0x180050729  mov     rcx, rdi; pSecurityDescriptor
0x18005072c  call    cs:__imp_InitializeSecurityDescriptor
0x180050732  mov     r13d, 80070000h
0x180050738  test    eax, eax
0x18005073a  jnz     short loc_180050777
0x18005073c  call    cs:__imp_GetLastError
0x180050742  mov     ebx, eax
0x180050744  test    eax, eax
0x180050746  jle     short loc_18005074E
0x180050748  movzx   ebx, ax
0x18005074b  or      ebx, r13d
0x18005074e  test    ebx, ebx
0x180050750  jns     short loc_180050777
0x180050752  lea     rax, base
0x180050759  mov     [rsp+0C0h+var_80], rax
0x18005075e  lea     rax, aHresult; "HRESULT"
0x180050765  mov     [rsp+0C0h+var_88], rax
0x18005076a  mov     [rsp+0C0h+var_90], 33Fh
0x180050772  jmp     loc_1800508CF
0x180050777  test    r12b, r12b
0x18005077a  jz      short loc_1800507CC
0x18005077c  mov     edx, 1000h; ControlBitsOfInterest
0x180050781  mov     r8d, edx; ControlBitsToSet
0x180050784  mov     rcx, rdi; pSecurityDescriptor
0x180050787  call    cs:__imp_SetSecurityDescriptorControl
0x18005078d  test    eax, eax
0x18005078f  jnz     short loc_1800507CC
0x180050791  call    cs:__imp_GetLastError
0x180050797  mov     ebx, eax
0x180050799  test    eax, eax
0x18005079b  jle     short loc_1800507A3
0x18005079d  movzx   ebx, ax
0x1800507a0  or      ebx, r13d
0x1800507a3  test    ebx, ebx
0x1800507a5  jns     short loc_1800507CC
0x1800507a7  lea     rax, base
0x1800507ae  mov     [rsp+0C0h+var_80], rax
0x1800507b3  lea     rax, aHresult; "HRESULT"
0x1800507ba  mov     [rsp+0C0h+var_88], rax
0x1800507bf  mov     [rsp+0C0h+var_90], 347h
0x1800507c7  jmp     loc_1800508CF
0x1800507cc  xor     r9d, r9d; bDaclDefaulted
0x1800507cf  mov     r8, r15; pDacl
0x1800507d2  lea     edx, [r9+1]; bDaclPresent
0x1800507d6  mov     rcx, rdi; pSecurityDescriptor
0x1800507d9  call    cs:__imp_SetSecurityDescriptorDacl
0x1800507df  test    eax, eax
0x1800507e1  jnz     short loc_18005081E
0x1800507e3  call    cs:__imp_GetLastError
0x1800507e9  mov     ebx, eax
0x1800507eb  test    eax, eax
0x1800507ed  jle     short loc_1800507F5
0x1800507ef  movzx   ebx, ax
0x1800507f2  or      ebx, r13d
0x1800507f5  test    ebx, ebx
0x1800507f7  jns     short loc_18005081E
0x1800507f9  lea     rax, base
0x180050800  mov     [rsp+0C0h+var_80], rax
0x180050805  lea     rax, aHresult; "HRESULT"
0x18005080c  mov     [rsp+0C0h+var_88], rax
0x180050811  mov     [rsp+0C0h+var_90], 34Eh
0x180050819  jmp     loc_1800508CF
0x18005081e  mov     rcx, rsi; hKey
0x180050821  call    cs:__imp_NCryptIsKeyHandle
0x180050827  test    eax, eax
0x180050829  jnz     short loc_180050882
0x18005082b  lea     r9d, [rax+4]; dwFlags
0x18005082f  mov     r8, rdi; pbData
0x180050832  lea     edx, [rax+8]; dwParam
0x180050835  mov     rcx, rsi; hProv
0x180050838  call    cs:__imp_CryptSetProvParam
0x18005083e  test    eax, eax
0x180050840  jnz     loc_180050900
0x180050846  call    cs:__imp_GetLastError
0x18005084c  mov     ebx, eax
0x18005084e  test    eax, eax
0x180050850  jle     short loc_180050858
0x180050852  movzx   ebx, ax
0x180050855  or      ebx, r13d
0x180050858  test    ebx, ebx
0x18005085a  jns     loc_180050900
0x180050860  lea     rax, base
0x180050867  mov     [rsp+0C0h+var_80], rax
0x18005086c  lea     rax, aHresult; "HRESULT"
0x180050873  mov     [rsp+0C0h+var_88], rax
0x180050878  mov     [rsp+0C0h+var_90], 355h
0x180050880  jmp     short loc_1800508CF
0x180050882  mov     rcx, rdi; pSecurityDescriptor
0x180050885  call    cs:__imp_GetSecurityDescriptorLength
0x18005088b  mov     r9d, eax; cbInput
0x18005088e  mov     dword ptr [rsp+0C0h+dwFlags], 4; dwFlags
0x180050896  mov     r8, rdi; pbInput
0x180050899  lea     rdx, aSecurityDescr; "Security Descr"
0x1800508a0  mov     rcx, rsi; hObject
0x1800508a3  call    cs:__imp_NCryptSetProperty
0x1800508a9  mov     ebx, eax
0x1800508ab  test    eax, eax
0x1800508ad  jns     short loc_180050900
0x1800508af  lea     rax, base
0x1800508b6  mov     [rsp+0C0h+var_80], rax
0x1800508bb  lea     rax, aHresult; "HRESULT"
0x1800508c2  mov     [rsp+0C0h+var_88], rax
0x1800508c7  mov     [rsp+0C0h+var_90], 35Bh
0x1800508cf  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x1800508d6  mov     [rsp+0C0h+var_98], rax
0x1800508db  mov     ecx, 2
0x1800508e0  mov     dword ptr [rsp+0C0h+dwFlags], ebx
0x1800508e4  mov     r9d, ecx
0x1800508e7  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800508ee  xor     edx, edx
0x1800508f0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800508f5  btr     ebx, 1Ch
0x1800508f9  bts     ebx, 1Eh
0x1800508fd  mov     [rbp+57h+arg_0], ebx
0x180050900  mov     rax, [r14]
0x180050903  mov     rdx, rdi
0x180050906  mov     rcx, r14
0x180050909  mov     rax, [rax+10h]
0x18005090d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050912  jmp     short loc_18005095B
0x180050914  mov     ecx, 0C000000Dh
0x180050919  lea     rax, base
0x180050920  mov     [rsp+0C0h+var_80], rax
0x180050925  lea     rax, aNtstatus; "NTSTATUS"
0x18005092c  mov     [rsp+0C0h+var_88], rax
0x180050931  mov     [rsp+0C0h+var_90], 334h
0x180050939  mov     [rsp+0C0h+var_98], rbx
0x18005093e  mov     [rbp+57h+arg_0], ecx
0x180050941  mov     dword ptr [rsp+0C0h+dwFlags], ecx
0x180050945  mov     ecx, 2
0x18005094a  mov     r9d, ecx
0x18005094d  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180050954  xor     edx, edx
0x180050956  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18005095b  mov     ebx, [rbp+57h+arg_0]
0x18005095e  lea     rcx, [rbp+57h+var_70]
0x180050962  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180050967  mov     eax, ebx
0x180050969  add     rsp, 88h
0x180050970  pop     r15
0x180050972  pop     r14
0x180050974  pop     r13
0x180050976  pop     r12
0x180050978  pop     rdi
0x180050979  pop     rsi
0x18005097a  pop     rbx
0x18005097b  pop     rbp
0x18005097c  retn
```
