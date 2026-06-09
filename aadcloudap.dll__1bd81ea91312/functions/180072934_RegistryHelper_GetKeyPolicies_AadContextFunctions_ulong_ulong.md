# RegistryHelper::GetKeyPolicies(AadContextFunctions *,ulong *,ulong *)

- ea: `0x180072934`
- end: `0x180072be8`
- name: `?GetKeyPolicies@RegistryHelper@@SAJPEAVAadContextFunctions@@PEAK1@Z`
- size: `692`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180081208`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x1800256d0`
- `0x180071e14`
- `0x180072334`
- `0x18007261c`
- `0x180072934`
- `0x180074ecc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072a92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072a92`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180072a32`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180072a32`

## string_xrefs

- `0x18007297e`: `RegistryHelper::GetKeyPolicies`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegistryHelper::GetKeyPolicies(struct AadContextFunctions *a1, unsigned int *a2, unsigned int *a3)
{
  const WCHAR *v6; // rsi
  int PersistedRegistryLocationW; // eax
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-59h]
  int v13; // [rsp+30h] [rbp-49h]
  const WCHAR *v14; // [rsp+50h] [rbp-29h] BYREF
  __int64 v15; // [rsp+58h] [rbp-21h]
  struct AadContextFunctions *v16; // [rsp+60h] [rbp-19h]
  HKEY v17[3]; // [rsp+68h] [rbp-11h] BYREF
  const char *v18[6]; // [rsp+80h] [rbp+7h] BYREF
  int DWORDValue; // [rsp+E0h] [rbp+67h] BYREF

  DWORDValue = 0;
  memset(v17, 0, sizeof(v17));
  v14 = 0;
  v16 = a1;
  v15 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v18,
    (int)"registry.cpp",
    (int)"RegistryHelper::GetKeyPolicies",
    (int)&DWORDValue);
  if ( !a1 || !a2 || !a3 )
  {
    PersistedRegistryLocationW = -1073741811;
    v13 = 1052;
    goto LABEL_30;
  }
  *a2 = 0;
  *a3 = 0;
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, __int64))(*(_QWORD *)a1 + 8LL))(
                        a1,
                        64,
                        520);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v14);
  v14 = v6;
  v15 = 520;
  if ( !v6 )
  {
    PersistedRegistryLocationW = -1073741801;
    v13 = 1061;
LABEL_30:
    DWORDValue = PersistedRegistryLocationW;
LABEL_31:
    LODWORD(phkResult) = PersistedRegistryLocationW;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", v13, "NTSTATUS", &base);
    goto LABEL_32;
  }
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"PoliciesWindows",
                                 L"Software\\Policies\\Microsoft\\Windows\\WorkplaceJoin",
                                 v6,
                                 520,
                                 0);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0xC0070000;
    DWORDValue = PersistedRegistryLocationW;
    v13 = 1072;
    goto LABEL_31;
  }
  PersistedRegistryLocationW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, v17);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0xC0070000;
    DWORDValue = PersistedRegistryLocationW;
    v13 = 1078;
    goto LABEL_31;
  }
  DWORDValue = RegistryHelper::GetDWORDValue(v17, L"KeyPolicy", a2);
  if ( DWORDValue < 0 )
    *a2 = 0;
  DWORDValue = RegistryHelper::GetDWORDValue(v17, L"HwPolicy", a3);
  if ( DWORDValue < 0 )
    *a3 = 0;
  if ( (*a2 & 0xFFFFFFFC) != 0 || (v9 = 2, *a2 == 2) )
  {
    if ( (Microsoft_Windows_AADEnableBits & 8) != 0 )
      McTemplateU0zzd_EventWriteTransfer(v9, v8, (_DWORD)v6, (unsigned int)L"KeyPolicy", *a2);
    *a2 = 0;
  }
  if ( *a3 >= 4 )
  {
    if ( (Microsoft_Windows_AADEnableBits & 8) != 0 )
      McTemplateU0zzd_EventWriteTransfer(v9, v8, (_DWORD)v6, (unsigned int)L"HwPolicy", *a3);
    *a3 = 0;
  }
LABEL_32:
  v10 = DWORDValue;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v18);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v14);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v17);
  return v10;
}

```

## disassembly

```asm
0x180072934  mov     [rsp-8+arg_8], rbx
0x180072939  mov     [rsp-8+arg_10], rsi
0x18007293e  push    rbp
0x18007293f  push    rdi
0x180072940  push    r12
0x180072942  push    r14
0x180072944  push    r15
0x180072946  lea     rbp, [rsp-37h]
0x18007294b  sub     rsp, 0B0h
0x180072952  mov     rbx, r8
0x180072955  mov     rdi, rdx
0x180072958  mov     rsi, rcx
0x18007295b  xor     r14d, r14d
0x18007295e  mov     [rbp+57h+arg_0], r14d
0x180072962  mov     [rbp+57h+var_68], r14
0x180072966  mov     [rbp+57h+var_58], r14
0x18007296a  mov     [rbp+57h+var_60], r14
0x18007296e  mov     [rbp+57h+var_80], r14
0x180072972  mov     [rbp+57h+var_70], rcx
0x180072976  mov     [rbp+57h+var_78], r14
0x18007297a  lea     r9, [rbp+57h+arg_0]
0x18007297e  lea     r8, aRegistryhelper_6; "RegistryHelper::GetKeyPolicies"
0x180072985  lea     r15, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x18007298c  mov     rdx, r15
0x18007298f  lea     rcx, [rbp+57h+var_50]
0x180072993  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180072998  nop
0x180072999  test    rsi, rsi
0x18007299c  jz      loc_180072B63
0x1800729a2  test    rdi, rdi
0x1800729a5  jz      loc_180072B63
0x1800729ab  test    rbx, rbx
0x1800729ae  jz      loc_180072B63
0x1800729b4  mov     [rdi], r14d
0x1800729b7  mov     [rbx], r14d
0x1800729ba  mov     rax, [rsi]
0x1800729bd  mov     r12d, 208h
0x1800729c3  mov     r8d, r12d
0x1800729c6  lea     edx, [r14+40h]
0x1800729ca  mov     rcx, rsi
0x1800729cd  mov     rax, [rax+8]
0x1800729d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729d6  mov     rsi, rax
0x1800729d9  lea     rcx, [rbp+57h+var_80]
0x1800729dd  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x1800729e2  mov     [rbp+57h+var_80], rsi
0x1800729e6  mov     [rbp+57h+var_78], r12
0x1800729ea  test    rsi, rsi
0x1800729ed  jnz     short loc_180072A19
0x1800729ef  mov     eax, 0C0000017h
0x1800729f4  lea     rcx, base
0x1800729fb  mov     [rsp+0D0h+var_90], rcx
0x180072a00  lea     rcx, aNtstatus; "NTSTATUS"
0x180072a07  mov     [rsp+0D0h+var_98], rcx
0x180072a0c  mov     [rsp+0D0h+var_A0], 425h
0x180072a14  jmp     loc_180072B88
0x180072a19  mov     [rsp+0D0h+phkResult], r14
0x180072a1e  mov     r9d, r12d
0x180072a21  mov     r8, rsi
0x180072a24  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x180072a2b  lea     rcx, aPolicieswindow; "PoliciesWindows"
0x180072a32  call    cs:__imp_GetPersistedRegistryLocationW
0x180072a38  mov     r12d, 0C0070000h
0x180072a3e  test    eax, eax
0x180072a40  jz      short loc_180072A76
0x180072a42  jle     short loc_180072A4A
0x180072a44  movzx   eax, ax
0x180072a47  or      eax, r12d
0x180072a4a  mov     [rbp+57h+arg_0], eax
0x180072a4d  test    eax, eax
0x180072a4f  jns     short loc_180072A76
0x180072a51  lea     rcx, base
0x180072a58  mov     [rsp+0D0h+var_90], rcx
0x180072a5d  lea     rcx, aNtstatus; "NTSTATUS"
0x180072a64  mov     [rsp+0D0h+var_98], rcx
0x180072a69  mov     [rsp+0D0h+var_A0], 430h
0x180072a71  jmp     loc_180072B8B
0x180072a76  lea     rax, [rbp+57h+var_68]
0x180072a7a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180072a7f  mov     r9d, 20019h; samDesired
0x180072a85  xor     r8d, r8d; ulOptions
0x180072a88  mov     rdx, rsi; lpSubKey
0x180072a8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072a92  call    cs:__imp_RegOpenKeyExW
0x180072a98  test    eax, eax
0x180072a9a  jz      short loc_180072AD0
0x180072a9c  jle     short loc_180072AA4
0x180072a9e  movzx   eax, ax
0x180072aa1  or      eax, r12d
0x180072aa4  mov     [rbp+57h+arg_0], eax
0x180072aa7  test    eax, eax
0x180072aa9  jns     short loc_180072AD0
0x180072aab  lea     rcx, base
0x180072ab2  mov     [rsp+0D0h+var_90], rcx
0x180072ab7  lea     rcx, aNtstatus; "NTSTATUS"
0x180072abe  mov     [rsp+0D0h+var_98], rcx
0x180072ac3  mov     [rsp+0D0h+var_A0], 436h
0x180072acb  jmp     loc_180072B8B
0x180072ad0  mov     r8, rdi
0x180072ad3  lea     rdx, aKeypolicy; "KeyPolicy"
0x180072ada  lea     rcx, [rbp+57h+var_68]
0x180072ade  call    ?GetDWORDValue@RegistryHelper@@CAJAEBV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@PEBGPEAK@Z; RegistryHelper::GetDWORDValue(Auto<HKEY__ *,RegistryFunctor,DummyContext> const &,ushort const *,ulong *)
0x180072ae3  mov     [rbp+57h+arg_0], eax
0x180072ae6  test    eax, eax
0x180072ae8  jns     short loc_180072AED
0x180072aea  mov     [rdi], r14d
0x180072aed  mov     r8, rbx
0x180072af0  lea     rdx, aHwpolicy; "HwPolicy"
0x180072af7  lea     rcx, [rbp+57h+var_68]
0x180072afb  call    ?GetDWORDValue@RegistryHelper@@CAJAEBV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@PEBGPEAK@Z; RegistryHelper::GetDWORDValue(Auto<HKEY__ *,RegistryFunctor,DummyContext> const &,ushort const *,ulong *)
0x180072b00  mov     [rbp+57h+arg_0], eax
0x180072b03  test    eax, eax
0x180072b05  jns     short loc_180072B0A
0x180072b07  mov     [rbx], r14d
0x180072b0a  mov     eax, [rdi]
0x180072b0c  test    eax, 0FFFFFFFCh
0x180072b11  jnz     short loc_180072B1C
0x180072b13  mov     ecx, 2
0x180072b18  cmp     eax, ecx
0x180072b1a  jnz     short loc_180072B3B
0x180072b1c  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 8
0x180072b23  jz      short loc_180072B38
0x180072b25  mov     dword ptr [rsp+0D0h+phkResult], eax
0x180072b29  lea     r9, aKeypolicy; "KeyPolicy"
0x180072b30  mov     r8, rsi
0x180072b33  call    McTemplateU0zzd_EventWriteTransfer
0x180072b38  mov     [rdi], r14d
0x180072b3b  mov     eax, [rbx]
0x180072b3d  cmp     eax, 4
0x180072b40  jb      short loc_180072BAA
0x180072b42  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 8
0x180072b49  jz      short loc_180072B5E
0x180072b4b  mov     dword ptr [rsp+0D0h+phkResult], eax
0x180072b4f  lea     r9, aHwpolicy; "HwPolicy"
0x180072b56  mov     r8, rsi
0x180072b59  call    McTemplateU0zzd_EventWriteTransfer
0x180072b5e  mov     [rbx], r14d
0x180072b61  jmp     short loc_180072BAA
0x180072b63  mov     eax, 0C000000Dh
0x180072b68  lea     rcx, base
0x180072b6f  mov     [rsp+0D0h+var_90], rcx
0x180072b74  lea     rcx, aNtstatus; "NTSTATUS"
0x180072b7b  mov     [rsp+0D0h+var_98], rcx
0x180072b80  mov     [rsp+0D0h+var_A0], 41Ch
0x180072b88  mov     [rbp+57h+arg_0], eax
0x180072b8b  mov     [rsp+0D0h+var_A8], r15
0x180072b90  mov     ecx, 2
0x180072b95  mov     dword ptr [rsp+0D0h+phkResult], eax
0x180072b99  mov     r9d, ecx
0x180072b9c  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180072ba3  xor     edx, edx
0x180072ba5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180072baa  mov     ebx, [rbp+57h+arg_0]
0x180072bad  lea     rcx, [rbp+57h+var_50]
0x180072bb1  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180072bb6  nop
0x180072bb7  lea     rcx, [rbp+57h+var_80]
0x180072bbb  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180072bc0  nop
0x180072bc1  lea     rcx, [rbp+57h+var_68]
0x180072bc5  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180072bca  mov     eax, ebx
0x180072bcc  lea     r11, [rsp+0D0h+var_20]
0x180072bd4  mov     rbx, [r11+38h]
0x180072bd8  mov     rsi, [r11+40h]
0x180072bdc  mov     rsp, r11
0x180072bdf  pop     r15
0x180072be1  pop     r14
0x180072be3  pop     r12
0x180072be5  pop     rdi
0x180072be6  pop     rbp
0x180072be7  retn
```
