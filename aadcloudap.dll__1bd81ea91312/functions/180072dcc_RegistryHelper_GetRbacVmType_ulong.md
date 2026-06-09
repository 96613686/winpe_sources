# RegistryHelper::GetRbacVmType(ulong *)

- ea: `0x180072dcc`
- end: `0x180072fd1`
- name: `?GetRbacVmType@RegistryHelper@@SAJPEAK@Z`
- size: `517`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5cc`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180071e14`
- `0x180072334`
- `0x18007261c`
- `0x180072dcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072ea5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072ea5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180072e41`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180072e41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryHelper::GetRbacVmType(unsigned int *a1)
{
  int PersistedRegistryLocationW; // eax
  signed int DWORDValue; // ebx
  LSTATUS v4; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-278h]
  int v7; // [rsp+30h] [rbp-268h]
  HKEY v8[4]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-228h] BYREF

  memset(v8, 0, 24);
  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"CloudDomainJoinParameters",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ",
                                 SubKey,
                                 520,
                                 0);
  DWORDValue = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      DWORDValue = (unsigned __int16)PersistedRegistryLocationW | 0xC0070000;
    if ( DWORDValue < 0 )
    {
      v7 = 1009;
LABEL_15:
      LODWORD(phkResult) = DWORDValue;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", v7, "NTSTATUS", &base);
      goto LABEL_16;
    }
  }
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, v8);
  DWORDValue = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      LODWORD(phkResult) = -2147187208;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", 1022, "HRESULT", &base);
      DWORDValue = -1073445384;
      goto LABEL_16;
    }
    if ( v4 > 0 )
      DWORDValue = (unsigned __int16)v4 | 0xC0070000;
    if ( DWORDValue < 0 )
    {
      v7 = 1025;
      goto LABEL_15;
    }
  }
  DWORDValue = RegistryHelper::GetDWORDValue(v8, L"ArcEnabledVM", a1);
  if ( DWORDValue < 0 )
  {
    v7 = 1031;
    goto LABEL_15;
  }
LABEL_16:
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v8);
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x180072dcc  mov     [rsp+arg_8], rbx
0x180072dd1  mov     [rsp+arg_10], rsi
0x180072dd6  push    rdi
0x180072dd7  sub     rsp, 290h
0x180072dde  mov     rax, cs:__security_cookie
0x180072de5  xor     rax, rsp
0x180072de8  mov     [rsp+298h+var_18], rax
0x180072df0  mov     rsi, rcx
0x180072df3  mov     [rsp+298h+var_248], 0
0x180072dfc  mov     [rsp+298h+var_238], 0
0x180072e05  mov     [rsp+298h+var_240], 0
0x180072e0e  mov     ebx, 208h
0x180072e13  mov     r8d, ebx; Size
0x180072e16  xor     edx, edx; Val
0x180072e18  lea     rcx, [rsp+298h+SubKey]; void *
0x180072e1d  call    memset_0
0x180072e22  mov     [rsp+298h+phkResult], 0
0x180072e2b  mov     r9d, ebx
0x180072e2e  lea     r8, [rsp+298h+SubKey]
0x180072e33  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180072e3a  lea     rcx, aClouddomainjoi; "CloudDomainJoinParameters"
0x180072e41  call    cs:__imp_GetPersistedRegistryLocationW
0x180072e47  mov     ebx, eax
0x180072e49  test    eax, eax
0x180072e4b  jz      short loc_180072E86
0x180072e4d  jle     short loc_180072E58
0x180072e4f  movzx   ebx, ax
0x180072e52  or      ebx, 0C0070000h
0x180072e58  test    ebx, ebx
0x180072e5a  jns     short loc_180072E86
0x180072e5c  lea     rax, base
0x180072e63  mov     [rsp+298h+var_258], rax
0x180072e68  lea     rax, aNtstatus; "NTSTATUS"
0x180072e6f  mov     [rsp+298h+var_260], rax
0x180072e74  mov     [rsp+298h+var_268], 3F1h
0x180072e7c  mov     edi, 2
0x180072e81  jmp     loc_180072F7C
0x180072e86  lea     rax, [rsp+298h+var_248]
0x180072e8b  mov     [rsp+298h+phkResult], rax; phkResult
0x180072e90  mov     r9d, 20019h; samDesired
0x180072e96  xor     r8d, r8d; ulOptions
0x180072e99  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180072e9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072ea5  call    cs:__imp_RegOpenKeyExW
0x180072eab  mov     ebx, eax
0x180072ead  mov     edi, 2
0x180072eb2  test    eax, eax
0x180072eb4  jz      loc_180072F42
0x180072eba  cmp     eax, edi
0x180072ebc  jnz     short loc_180072F0F
0x180072ebe  lea     rax, base
0x180072ec5  mov     [rsp+298h+var_258], rax
0x180072eca  lea     rax, aHresult; "HRESULT"
0x180072ed1  mov     [rsp+298h+var_260], rax
0x180072ed6  mov     [rsp+298h+var_268], 3FEh
0x180072ede  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180072ee5  mov     [rsp+298h+var_270], rax
0x180072eea  mov     dword ptr [rsp+298h+phkResult], 800485F8h
0x180072ef2  mov     r9d, edi
0x180072ef5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180072efc  xor     edx, edx
0x180072efe  mov     ecx, edi
0x180072f00  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180072f05  mov     ebx, 0C00485F8h
0x180072f0a  jmp     loc_180072FA0
0x180072f0f  test    eax, eax
0x180072f11  jle     short loc_180072F1C
0x180072f13  movzx   ebx, ax
0x180072f16  or      ebx, 0C0070000h
0x180072f1c  test    ebx, ebx
0x180072f1e  jns     short loc_180072F42
0x180072f20  lea     rax, base
0x180072f27  mov     [rsp+298h+var_258], rax
0x180072f2c  lea     rax, aNtstatus; "NTSTATUS"
0x180072f33  mov     [rsp+298h+var_260], rax
0x180072f38  mov     [rsp+298h+var_268], 401h
0x180072f40  jmp     short loc_180072F7C
0x180072f42  mov     r8, rsi
0x180072f45  lea     rdx, aArcenabledvm; "ArcEnabledVM"
0x180072f4c  lea     rcx, [rsp+298h+var_248]
0x180072f51  call    ?GetDWORDValue@RegistryHelper@@CAJAEBV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@PEBGPEAK@Z; RegistryHelper::GetDWORDValue(Auto<HKEY__ *,RegistryFunctor,DummyContext> const &,ushort const *,ulong *)
0x180072f56  mov     ebx, eax
0x180072f58  test    eax, eax
0x180072f5a  jns     short loc_180072FA0
0x180072f5c  lea     rax, base
0x180072f63  mov     [rsp+298h+var_258], rax
0x180072f68  lea     rax, aNtstatus; "NTSTATUS"
0x180072f6f  mov     [rsp+298h+var_260], rax
0x180072f74  mov     [rsp+298h+var_268], 407h
0x180072f7c  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180072f83  mov     [rsp+298h+var_270], rax
0x180072f88  mov     dword ptr [rsp+298h+phkResult], ebx
0x180072f8c  mov     r9d, edi
0x180072f8f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180072f96  xor     edx, edx
0x180072f98  mov     ecx, edi
0x180072f9a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180072f9f  nop
0x180072fa0  lea     rcx, [rsp+298h+var_248]
0x180072fa5  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180072faa  mov     eax, ebx
0x180072fac  mov     rcx, [rsp+298h+var_18]
0x180072fb4  xor     rcx, rsp; StackCookie
0x180072fb7  call    __security_check_cookie
0x180072fbc  lea     r11, [rsp+298h+var_8]
0x180072fc4  mov     rbx, [r11+18h]
0x180072fc8  mov     rsi, [r11+20h]
0x180072fcc  mov     rsp, r11
0x180072fcf  pop     rdi
0x180072fd0  retn
```
