# RegistryHelper::AddDaclAllowAce(AadContextFunctions *,Auto<HKEY__ *,RegistryFunctor,DummyContext> const &,ushort const *,ulong)

- ea: `0x180071f1c`
- end: `0x18007232c`
- name: `?AddDaclAllowAce@RegistryHelper@@CAJPEAVAadContextFunctions@@AEBV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@PEBGK@Z`
- size: `1040`
- prototype: `__int64 __fastcall(__int64, HKEY *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180074008`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x1800256d0`
- `0x180071e14`
- `0x180071f1c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722f1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800720fb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800720fb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800721b2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800721b2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180072206`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180072206`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180072032`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800720ac`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180072032`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800720ac`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180072255`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180072255`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180071fd8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180071fd8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18007216e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18007216e`

## string_xrefs

- `0x180071f9f`: `RegistryHelper::AddDaclAllowAce`

## pseudocode

```c
__int64 __fastcall RegistryHelper::AddDaclAllowAce(__int64 a1, HKEY *a2, __int64 a3)
{
  void *v5; // rdi
  int LastError; // eax
  __int64 v7; // rbx
  unsigned int v8; // ebx
  int v10; // [rsp+38h] [rbp-D0h]
  WINBOOL bDaclPresent[2]; // [rsp+58h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+60h] [rbp-A8h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-A0h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-98h] BYREF
  void *v15; // [rsp+78h] [rbp-90h] BYREF
  __int64 v16; // [rsp+80h] [rbp-88h]
  __int64 v17; // [rsp+88h] [rbp-80h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-78h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-28h]
  const char *v21[12]; // [rsp+E8h] [rbp-20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+158h] [rbp+50h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+168h] [rbp+60h] BYREF
  int v24; // [rsp+16Ch] [rbp+64h]
  int v25; // [rsp+170h] [rbp+68h] BYREF

  v24 = HIDWORD(a3);
  v25 = 0;
  cbSecurityDescriptor = 0;
  v5 = 0;
  v15 = 0;
  v17 = a1;
  v16 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v20 = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  bDaclPresent[0] = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  NewAcl = 0;
  Sid = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v21,
    (int)"registry.cpp",
    (int)"RegistryHelper::AddDaclAllowAce",
    (int)&v25);
  if ( !a1 || !*a2 )
  {
    LastError = -1073741811;
    v10 = 1490;
    goto LABEL_43;
  }
  if ( !ConvertStringSidToSidW(
          L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
          &Sid) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0xC0070000;
    v25 = LastError;
    if ( LastError < 0 )
    {
      v10 = 1496;
      goto LABEL_44;
    }
  }
  LastError = RegGetKeySecurity(*a2, 4u, 0, &cbSecurityDescriptor);
  if ( LastError == 122 )
  {
    v7 = cbSecurityDescriptor;
    v5 = (void *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 8LL))(
                   a1,
                   64,
                   cbSecurityDescriptor);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v15);
    v15 = v5;
    v16 = v7;
    if ( !v5 )
    {
      LastError = -1073741801;
      v10 = 1506;
LABEL_43:
      v25 = LastError;
      goto LABEL_44;
    }
    LastError = RegGetKeySecurity(*a2, 4u, v5, &cbSecurityDescriptor);
  }
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0xC0070000;
    v25 = LastError;
    v10 = 1514;
  }
  else
  {
    if ( GetSecurityDescriptorDacl(v5, bDaclPresent, &pDacl, &bDaclDefaulted) )
      goto LABEL_22;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0xC0070000;
    v25 = LastError;
    if ( LastError >= 0 )
    {
LABEL_22:
      pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
      *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeForm = 0;
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
      LastError = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0xC0070000;
        v25 = LastError;
        v10 = 1535;
      }
      else
      {
        if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          goto LABEL_52;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0xC0070000;
        v25 = LastError;
        if ( LastError >= 0 )
        {
LABEL_52:
          if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
            goto LABEL_37;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0xC0070000;
          v25 = LastError;
          if ( LastError >= 0 )
          {
LABEL_37:
            LastError = RegSetKeySecurity(*a2, 4u, pSecurityDescriptor);
            if ( !LastError )
              goto LABEL_45;
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0xC0070000;
            v25 = LastError;
            v10 = 1555;
          }
          else
          {
            v10 = 1548;
          }
        }
        else
        {
          v10 = 1542;
        }
      }
    }
    else
    {
      v10 = 1520;
    }
  }
LABEL_44:
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, LastError, "registry.cpp", v10, "NTSTATUS", &base);
LABEL_45:
  if ( Sid )
    LocalFree(Sid);
  if ( NewAcl )
    LocalFree(NewAcl);
  v8 = v25;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v21);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v15);
  return v8;
}

```

## disassembly

```asm
0x180071f1c  mov     rax, rsp
0x180071f1f  mov     [rax+10h], rbx
0x180071f23  mov     [rax+20h], r9d
0x180071f27  mov     [rax+18h], r8
0x180071f2b  push    rbp
0x180071f2c  push    rsi
0x180071f2d  push    rdi
0x180071f2e  push    r12
0x180071f30  push    r13
0x180071f32  push    r14
0x180071f34  push    r15
0x180071f36  lea     rbp, [rax-48h]
0x180071f3a  sub     rsp, 110h
0x180071f41  mov     rsi, rdx
0x180071f44  mov     r14, rcx
0x180071f47  xor     r15d, r15d
0x180071f4a  mov     [rbp+40h+arg_18], r15d
0x180071f4e  mov     [rbp+40h+cbSecurityDescriptor], r15d
0x180071f52  mov     edi, r15d
0x180071f55  mov     [rsp+140h+var_D0], r15
0x180071f5a  mov     [rbp+40h+var_C0], rcx
0x180071f5e  mov     [rsp+140h+var_C8], r15
0x180071f63  xorps   xmm0, xmm0
0x180071f66  xor     eax, eax
0x180071f68  movups  [rbp+40h+pSecurityDescriptor], xmm0
0x180071f6c  movups  [rbp+40h+var_78], xmm0
0x180071f70  mov     [rbp+40h+var_68], rax
0x180071f74  xorps   xmm1, xmm1
0x180071f77  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], xmm1
0x180071f7b  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm1
0x180071f7f  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.TrusteeType], xmm1
0x180071f83  mov     [rsp+140h+bDaclPresent], r15d
0x180071f88  mov     [rbp+40h+bDaclDefaulted], r15d
0x180071f8c  mov     [rsp+140h+pDacl], r15
0x180071f91  mov     [rsp+140h+NewAcl], r15
0x180071f96  mov     [rsp+140h+Sid], r15
0x180071f9b  lea     r9, [rbp+40h+arg_18]
0x180071f9f  lea     r8, aRegistryhelper_9; "RegistryHelper::AddDaclAllowAce"
0x180071fa6  lea     r13, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180071fad  mov     rdx, r13
0x180071fb0  lea     rcx, [rbp+40h+var_60]
0x180071fb4  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180071fb9  nop
0x180071fba  test    r14, r14
0x180071fbd  jz      loc_180072290
0x180071fc3  cmp     [rsi], r15
0x180071fc6  jz      loc_180072290
0x180071fcc  lea     rdx, [rsp+140h+Sid]; Sid
0x180071fd1  lea     rcx, StringSid; "S-1-15-2-1910091885-1573563583-11049412"...
0x180071fd8  call    cs:__imp_ConvertStringSidToSidW
0x180071fde  mov     r12d, 0C0070000h
0x180071fe4  test    eax, eax
0x180071fe6  jnz     short loc_180072024
0x180071fe8  call    cs:__imp_GetLastError
0x180071fee  test    eax, eax
0x180071ff0  jle     short loc_180071FF8
0x180071ff2  movzx   eax, ax
0x180071ff5  or      eax, r12d
0x180071ff8  mov     [rbp+40h+arg_18], eax
0x180071ffb  test    eax, eax
0x180071ffd  jns     short loc_180072024
0x180071fff  lea     rcx, base
0x180072006  mov     [rsp+40h], rcx
0x18007200b  lea     rcx, aNtstatus; "NTSTATUS"
0x180072012  mov     [rsp+140h+var_108], rcx
0x180072017  mov     dword ptr [rsp+140h+var_110], 5D8h
0x18007201f  jmp     loc_1800722B8
0x180072024  lea     r9, [rbp+40h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180072028  xor     r8d, r8d; pSecurityDescriptor
0x18007202b  lea     edx, [r8+4]; SecurityInformation
0x18007202f  mov     rcx, [rsi]; hKey
0x180072032  call    cs:__imp_RegGetKeySecurity
0x180072038  cmp     eax, 7Ah ; 'z'
0x18007203b  jnz     short loc_1800720B2
0x18007203d  mov     ebx, [rbp+40h+cbSecurityDescriptor]
0x180072040  mov     rax, [r14]
0x180072043  mov     r8d, ebx
0x180072046  mov     edx, 40h ; '@'
0x18007204b  mov     rcx, r14
0x18007204e  mov     rax, [rax+8]
0x180072052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072057  mov     rdi, rax
0x18007205a  lea     rcx, [rsp+140h+var_D0]
0x18007205f  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180072064  mov     [rsp+140h+var_D0], rdi
0x180072069  mov     [rsp+140h+var_C8], rbx
0x18007206e  test    rdi, rdi
0x180072071  jnz     short loc_18007209D
0x180072073  mov     eax, 0C0000017h
0x180072078  lea     rcx, base
0x18007207f  mov     [rsp+40h], rcx
0x180072084  lea     rcx, aNtstatus; "NTSTATUS"
0x18007208b  mov     [rsp+140h+var_108], rcx
0x180072090  mov     dword ptr [rsp+140h+var_110], 5E2h
0x180072098  jmp     loc_1800722B5
0x18007209d  lea     r9, [rbp+40h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800720a1  mov     r8, rdi; pSecurityDescriptor
0x1800720a4  mov     edx, 4; SecurityInformation
0x1800720a9  mov     rcx, [rsi]; hKey
0x1800720ac  call    cs:__imp_RegGetKeySecurity
0x1800720b2  test    eax, eax
0x1800720b4  jz      short loc_1800720EA
0x1800720b6  jle     short loc_1800720BE
0x1800720b8  movzx   eax, ax
0x1800720bb  or      eax, r12d
0x1800720be  mov     [rbp+40h+arg_18], eax
0x1800720c1  test    eax, eax
0x1800720c3  jns     short loc_1800720EA
0x1800720c5  lea     rcx, base
0x1800720cc  mov     [rsp+40h], rcx
0x1800720d1  lea     rcx, aNtstatus; "NTSTATUS"
0x1800720d8  mov     [rsp+140h+var_108], rcx
0x1800720dd  mov     dword ptr [rsp+140h+var_110], 5EAh
0x1800720e5  jmp     loc_1800722B8
0x1800720ea  lea     r9, [rbp+40h+bDaclDefaulted]; lpbDaclDefaulted
0x1800720ee  lea     r8, [rsp+140h+pDacl]; pDacl
0x1800720f3  lea     rdx, [rsp+140h+bDaclPresent]; lpbDaclPresent
0x1800720f8  mov     rcx, rdi; pSecurityDescriptor
0x1800720fb  call    cs:__imp_GetSecurityDescriptorDacl
0x180072101  test    eax, eax
0x180072103  jnz     short loc_180072141
0x180072105  call    cs:__imp_GetLastError
0x18007210b  test    eax, eax
0x18007210d  jle     short loc_180072115
0x18007210f  movzx   eax, ax
0x180072112  or      eax, r12d
0x180072115  mov     [rbp+40h+arg_18], eax
0x180072118  test    eax, eax
0x18007211a  jns     short loc_180072141
0x18007211c  lea     rcx, base
0x180072123  mov     [rsp+40h], rcx
0x180072128  lea     rcx, aNtstatus; "NTSTATUS"
0x18007212f  mov     [rsp+140h+var_108], rcx
0x180072134  mov     dword ptr [rsp+140h+var_110], 5F0h
0x18007213c  jmp     loc_1800722B8
0x180072141  mov     [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180072148  mov     ebx, 1
0x18007214d  mov     qword ptr [rbp+40h+pListOfExplicitEntries.grfAccessMode], rbx
0x180072151  mov     qword ptr [rbp+40h+pListOfExplicitEntries.Trustee.TrusteeForm], r15
0x180072155  mov     rax, [rsp+140h+Sid]
0x18007215a  mov     [rbp+40h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18007215e  lea     r9, [rsp+140h+NewAcl]; NewAcl
0x180072163  mov     r8, [rsp+140h+pDacl]; OldAcl
0x180072168  lea     rdx, [rbp+40h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18007216c  mov     ecx, ebx; cCountOfExplicitEntries
0x18007216e  call    cs:__imp_SetEntriesInAclW
0x180072174  test    eax, eax
0x180072176  jz      short loc_1800721AC
0x180072178  jle     short loc_180072180
0x18007217a  movzx   eax, ax
0x18007217d  or      eax, r12d
0x180072180  mov     [rbp+40h+arg_18], eax
0x180072183  test    eax, eax
0x180072185  jns     short loc_1800721AC
0x180072187  lea     rcx, base
0x18007218e  mov     [rsp+40h], rcx
0x180072193  lea     rcx, aNtstatus; "NTSTATUS"
0x18007219a  mov     [rsp+140h+var_108], rcx
0x18007219f  mov     dword ptr [rsp+140h+var_110], 5FFh
0x1800721a7  jmp     loc_1800722B8
0x1800721ac  mov     edx, ebx; dwRevision
0x1800721ae  lea     rcx, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x1800721b2  call    cs:__imp_InitializeSecurityDescriptor
0x1800721b8  test    eax, eax
0x1800721ba  jnz     short loc_1800721F8
0x1800721bc  call    cs:__imp_GetLastError
0x1800721c2  test    eax, eax
0x1800721c4  jle     short loc_1800721CC
0x1800721c6  movzx   eax, ax
0x1800721c9  or      eax, r12d
0x1800721cc  mov     [rbp+40h+arg_18], eax
0x1800721cf  test    eax, eax
0x1800721d1  jns     short loc_1800721F8
0x1800721d3  lea     rcx, base
0x1800721da  mov     [rsp+40h], rcx
0x1800721df  lea     rcx, aNtstatus; "NTSTATUS"
0x1800721e6  mov     [rsp+140h+var_108], rcx
0x1800721eb  mov     dword ptr [rsp+140h+var_110], 606h
0x1800721f3  jmp     loc_1800722B8
0x1800721f8  xor     r9d, r9d; bDaclDefaulted
0x1800721fb  mov     r8, [rsp+140h+NewAcl]; pDacl
0x180072200  mov     edx, ebx; bDaclPresent
0x180072202  lea     rcx, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x180072206  call    cs:__imp_SetSecurityDescriptorDacl
0x18007220c  test    eax, eax
0x18007220e  jnz     short loc_180072249
0x180072210  call    cs:__imp_GetLastError
0x180072216  test    eax, eax
0x180072218  jle     short loc_180072220
0x18007221a  movzx   eax, ax
0x18007221d  or      eax, r12d
0x180072220  mov     [rbp+40h+arg_18], eax
0x180072223  test    eax, eax
0x180072225  jns     short loc_180072249
0x180072227  lea     rcx, base
0x18007222e  mov     [rsp+40h], rcx
0x180072233  lea     rcx, aNtstatus; "NTSTATUS"
0x18007223a  mov     [rsp+140h+var_108], rcx
0x18007223f  mov     dword ptr [rsp+140h+var_110], 60Ch
0x180072247  jmp     short loc_1800722B8
0x180072249  lea     r8, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x18007224d  mov     edx, 4; SecurityInformation
0x180072252  mov     rcx, [rsi]; hKey
0x180072255  call    cs:__imp_RegSetKeySecurity
0x18007225b  test    eax, eax
0x18007225d  jz      short loc_1800722D7
0x18007225f  jle     short loc_180072267
0x180072261  movzx   eax, ax
0x180072264  or      eax, r12d
0x180072267  mov     [rbp+40h+arg_18], eax
0x18007226a  test    eax, eax
0x18007226c  jns     short loc_1800722D7
0x18007226e  lea     rcx, base
0x180072275  mov     [rsp+40h], rcx
0x18007227a  lea     rcx, aNtstatus; "NTSTATUS"
0x180072281  mov     [rsp+140h+var_108], rcx
0x180072286  mov     dword ptr [rsp+140h+var_110], 613h
0x18007228e  jmp     short loc_1800722B8
0x180072290  mov     eax, 0C000000Dh
0x180072295  lea     rcx, base
0x18007229c  mov     [rsp+40h], rcx
0x1800722a1  lea     rcx, aNtstatus; "NTSTATUS"
0x1800722a8  mov     [rsp+140h+var_108], rcx
0x1800722ad  mov     dword ptr [rsp+140h+var_110], 5D2h
0x1800722b5  mov     [rbp+40h+arg_18], eax
0x1800722b8  mov     qword ptr [rsp+140h+var_118], r13
0x1800722bd  mov     ecx, 2
0x1800722c2  mov     dword ptr [rsp+140h+var_120], eax
0x1800722c6  mov     r9d, ecx
0x1800722c9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800722d0  xor     edx, edx
0x1800722d2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800722d7  mov     rcx, [rsp+140h+Sid]; hMem
0x1800722dc  test    rcx, rcx
0x1800722df  jz      short loc_1800722E7
0x1800722e1  call    cs:__imp_LocalFree
0x1800722e7  mov     rcx, [rsp+140h+NewAcl]; hMem
0x1800722ec  test    rcx, rcx
0x1800722ef  jz      short loc_1800722F7
0x1800722f1  call    cs:__imp_LocalFree
0x1800722f7  mov     ebx, [rbp+40h+arg_18]
0x1800722fa  lea     rcx, [rbp+40h+var_60]
0x1800722fe  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180072303  nop
0x180072304  lea     rcx, [rsp+140h+var_D0]
0x180072309  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007230e  nop
0x18007230f  mov     eax, ebx
0x180072311  mov     rbx, [rsp+140h+arg_8]
0x180072319  add     rsp, 110h
0x180072320  pop     r15
0x180072322  pop     r14
0x180072324  pop     r13
0x180072326  pop     r12
0x180072328  pop     rdi
0x180072329  pop     rsi
0x18007232a  pop     rbp
0x18007232b  retn
```
