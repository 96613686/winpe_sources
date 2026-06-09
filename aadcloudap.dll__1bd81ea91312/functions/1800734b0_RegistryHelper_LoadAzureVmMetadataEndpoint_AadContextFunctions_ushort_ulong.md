# RegistryHelper::LoadAzureVmMetadataEndpoint(AadContextFunctions *,ushort *,ulong)

- ea: `0x1800734b0`
- end: `0x1800737e7`
- name: `?LoadAzureVmMetadataEndpoint@RegistryHelper@@SAJPEAVAadContextFunctions@@PEAGK@Z`
- size: `823`
- prototype: `static int(struct AadContextFunctions *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037b1c`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180071e14`
- `0x180072334`
- `0x1800734b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800735b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800735b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073686`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073726`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073686`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073726`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180073552`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180073552`

## string_xrefs

- `0x180073678`: `AzureVmComputeMetadataEndpoint`
- `0x18007371a`: `AzureVmComputeMetadataEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryHelper::LoadAzureVmMetadataEndpoint(struct AadContextFunctions *a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  int PersistedRegistryLocationW; // eax
  LSTATUS v6; // eax
  LSTATUS ValueW; // eax
  LSTATUS v8; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  DWORD v12; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hkey[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  memset(hkey, 0, sizeof(hkey));
  pdwType = 0;
  v12 = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( !a1 || !a2 )
  {
    v4 = -1073741811;
    LODWORD(pcbData) = 924;
    goto LABEL_28;
  }
  v4 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"CloudDomainJoinParameters",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ",
                                 SubKey,
                                 520,
                                 0);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v4 = (unsigned __int16)PersistedRegistryLocationW | 0xC0070000;
    else
      v4 = PersistedRegistryLocationW;
    LODWORD(pcbData) = 935;
    goto LABEL_28;
  }
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hkey);
  if ( !v6 )
  {
    ValueW = RegGetValueW(hkey[0], 0, L"AzureVmComputeMetadataEndpoint", 6u, &pdwType, 0, &v12);
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v4 = (unsigned __int16)ValueW | 0xC0070000;
      else
        v4 = ValueW;
      LODWORD(pcbData) = 965;
      goto LABEL_28;
    }
    if ( v12 <= 0x401 )
    {
      v8 = RegGetValueW(hkey[0], 0, L"AzureVmComputeMetadataEndpoint", 6u, &pdwType, a2, &v12);
      if ( v8 )
      {
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0xC0070000;
        else
          v4 = v8;
        LODWORD(pcbData) = 984;
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    v4 = -2147483643;
    LODWORD(pcbData) = 970;
LABEL_28:
    LODWORD(phkResult) = v4;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", pcbData, "NTSTATUS", &base);
    goto LABEL_29;
  }
  if ( v6 != 2 )
  {
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0xC0070000;
    else
      v4 = v6;
    LODWORD(pcbData) = 951;
    goto LABEL_28;
  }
  LODWORD(phkResult) = -2147187212;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", 948, "HRESULT", &base);
  v4 = -1073445388;
LABEL_29:
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(hkey);
  return v4;
}

```

## disassembly

```asm
0x1800734b0  mov     [rsp-8+arg_0], rbx
0x1800734b5  mov     [rsp-8+arg_10], rsi
0x1800734ba  push    rbp
0x1800734bb  push    rdi
0x1800734bc  push    r15
0x1800734be  lea     rbp, [rsp-190h]
0x1800734c6  sub     rsp, 290h
0x1800734cd  mov     rax, cs:__security_cookie
0x1800734d4  xor     rax, rsp
0x1800734d7  mov     [rbp+1A0h+var_20], rax
0x1800734de  mov     rsi, rdx
0x1800734e1  mov     rbx, rcx
0x1800734e4  mov     [rsp+2A0h+hkey], 0
0x1800734ed  mov     [rsp+2A0h+var_238], 0
0x1800734f6  mov     [rsp+2A0h+var_240], 0
0x1800734ff  mov     [rsp+2A0h+pdwType], 0
0x180073507  mov     [rsp+2A0h+var_250], 0
0x18007350f  mov     edi, 208h
0x180073514  mov     r8d, edi; Size
0x180073517  xor     edx, edx; Val
0x180073519  lea     rcx, [rsp+2A0h+SubKey]; void *
0x18007351e  call    memset_0
0x180073523  test    rbx, rbx
0x180073526  jz      loc_180073766
0x18007352c  test    rsi, rsi
0x18007352f  jz      loc_180073766
0x180073535  xor     ebx, ebx
0x180073537  mov     [rsp+2A0h+phkResult], rbx
0x18007353c  mov     r9d, edi
0x18007353f  lea     r8, [rsp+2A0h+SubKey]
0x180073544  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007354b  lea     rcx, aClouddomainjoi; "CloudDomainJoinParameters"
0x180073552  call    cs:__imp_GetPersistedRegistryLocationW
0x180073558  mov     r15d, 0C0070000h
0x18007355e  test    eax, eax
0x180073560  jz      short loc_180073597
0x180073562  jg      short loc_180073568
0x180073564  mov     ebx, eax
0x180073566  jmp     short loc_18007356E
0x180073568  movzx   ebx, ax
0x18007356b  or      ebx, r15d
0x18007356e  test    ebx, ebx
0x180073570  jns     short loc_180073597
0x180073572  lea     rax, base
0x180073579  mov     [rsp+2A0h+var_260], rax
0x18007357e  lea     rax, aNtstatus; "NTSTATUS"
0x180073585  mov     [rsp+2A0h+var_268], rax
0x18007358a  mov     dword ptr [rsp+2A0h+pcbData], 3A7h
0x180073592  jmp     loc_18007378B
0x180073597  lea     rax, [rsp+2A0h+hkey]
0x18007359c  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800735a1  mov     r9d, 20019h; samDesired
0x1800735a7  xor     r8d, r8d; ulOptions
0x1800735aa  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800735af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800735b6  call    cs:__imp_RegOpenKeyExW
0x1800735bc  mov     edi, 2
0x1800735c1  test    eax, eax
0x1800735c3  jz      loc_180073655
0x1800735c9  cmp     eax, edi
0x1800735cb  jnz     short loc_18007361E
0x1800735cd  lea     rax, base
0x1800735d4  mov     [rsp+2A0h+var_260], rax
0x1800735d9  lea     rax, aHresult; "HRESULT"
0x1800735e0  mov     [rsp+2A0h+var_268], rax
0x1800735e5  mov     dword ptr [rsp+2A0h+pcbData], 3B4h
0x1800735ed  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x1800735f4  mov     [rsp+2A0h+pvData], rax
0x1800735f9  mov     dword ptr [rsp+2A0h+phkResult], 800485F4h
0x180073601  mov     r9d, edi
0x180073604  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007360b  xor     edx, edx
0x18007360d  mov     ecx, edi
0x18007360f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180073614  mov     ebx, 0C00485F4h
0x180073619  jmp     loc_1800737B4
0x18007361e  test    eax, eax
0x180073620  jg      short loc_180073626
0x180073622  mov     ebx, eax
0x180073624  jmp     short loc_18007362C
0x180073626  movzx   ebx, ax
0x180073629  or      ebx, r15d
0x18007362c  test    ebx, ebx
0x18007362e  jns     short loc_180073655
0x180073630  lea     rax, base
0x180073637  mov     [rsp+2A0h+var_260], rax
0x18007363c  lea     rax, aNtstatus; "NTSTATUS"
0x180073643  mov     [rsp+2A0h+var_268], rax
0x180073648  mov     dword ptr [rsp+2A0h+pcbData], 3B7h
0x180073650  jmp     loc_180073790
0x180073655  lea     rax, [rsp+2A0h+var_250]
0x18007365a  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18007365f  mov     [rsp+2A0h+pvData], 0; pvData
0x180073668  lea     rax, [rsp+2A0h+pdwType]
0x18007366d  mov     [rsp+2A0h+phkResult], rax; pdwType
0x180073672  mov     r9d, 6; dwFlags
0x180073678  lea     r8, aAzurevmcompute; "AzureVmComputeMetadataEndpoint"
0x18007367f  xor     edx, edx; lpSubKey
0x180073681  mov     rcx, [rsp+2A0h+hkey]; hkey
0x180073686  call    cs:__imp_RegGetValueW
0x18007368c  test    eax, eax
0x18007368e  jz      short loc_1800736C5
0x180073690  jg      short loc_180073696
0x180073692  mov     ebx, eax
0x180073694  jmp     short loc_18007369C
0x180073696  movzx   ebx, ax
0x180073699  or      ebx, r15d
0x18007369c  test    ebx, ebx
0x18007369e  jns     short loc_1800736C5
0x1800736a0  lea     rax, base
0x1800736a7  mov     [rsp+2A0h+var_260], rax
0x1800736ac  lea     rax, aNtstatus; "NTSTATUS"
0x1800736b3  mov     [rsp+2A0h+var_268], rax
0x1800736b8  mov     dword ptr [rsp+2A0h+pcbData], 3C5h
0x1800736c0  jmp     loc_180073790
0x1800736c5  xor     edx, edx; lpSubKey
0x1800736c7  cmp     [rsp+2A0h+var_250], 401h
0x1800736cf  jbe     short loc_1800736FB
0x1800736d1  mov     ebx, 80000005h
0x1800736d6  lea     rax, base
0x1800736dd  mov     [rsp+2A0h+var_260], rax
0x1800736e2  lea     rax, aNtstatus; "NTSTATUS"
0x1800736e9  mov     [rsp+2A0h+var_268], rax
0x1800736ee  mov     dword ptr [rsp+2A0h+pcbData], 3CAh
0x1800736f6  jmp     loc_180073792
0x1800736fb  lea     rax, [rsp+2A0h+var_250]
0x180073700  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180073705  mov     [rsp+2A0h+pvData], rsi; pvData
0x18007370a  lea     rax, [rsp+2A0h+pdwType]
0x18007370f  mov     [rsp+2A0h+phkResult], rax; pdwType
0x180073714  mov     r9d, 6; dwFlags
0x18007371a  lea     r8, aAzurevmcompute; "AzureVmComputeMetadataEndpoint"
0x180073721  mov     rcx, [rsp+2A0h+hkey]; hkey
0x180073726  call    cs:__imp_RegGetValueW
0x18007372c  test    eax, eax
0x18007372e  jz      loc_1800737B4
0x180073734  jg      short loc_18007373A
0x180073736  mov     ebx, eax
0x180073738  jmp     short loc_180073740
0x18007373a  movzx   ebx, ax
0x18007373d  or      ebx, r15d
0x180073740  test    ebx, ebx
0x180073742  jns     short loc_1800737B4
0x180073744  lea     rax, base
0x18007374b  mov     [rsp+2A0h+var_260], rax
0x180073750  lea     rax, aNtstatus; "NTSTATUS"
0x180073757  mov     [rsp+2A0h+var_268], rax
0x18007375c  mov     dword ptr [rsp+2A0h+pcbData], 3D8h
0x180073764  jmp     short loc_180073790
0x180073766  mov     ebx, 0C000000Dh
0x18007376b  lea     rax, base
0x180073772  mov     [rsp+2A0h+var_260], rax
0x180073777  lea     rax, aNtstatus; "NTSTATUS"
0x18007377e  mov     [rsp+2A0h+var_268], rax
0x180073783  mov     dword ptr [rsp+2A0h+pcbData], 39Ch
0x18007378b  mov     edi, 2
0x180073790  xor     edx, edx
0x180073792  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180073799  mov     [rsp+2A0h+pvData], rax
0x18007379e  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x1800737a2  mov     r9d, edi
0x1800737a5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800737ac  mov     ecx, edi
0x1800737ae  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800737b3  nop
0x1800737b4  lea     rcx, [rsp+2A0h+hkey]
0x1800737b9  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x1800737be  mov     eax, ebx
0x1800737c0  mov     rcx, [rbp+1A0h+var_20]
0x1800737c7  xor     rcx, rsp; StackCookie
0x1800737ca  call    __security_check_cookie
0x1800737cf  lea     r11, [rsp+2A0h+var_10]
0x1800737d7  mov     rbx, [r11+20h]
0x1800737db  mov     rsi, [r11+30h]
0x1800737df  mov     rsp, r11
0x1800737e2  pop     r15
0x1800737e4  pop     rdi
0x1800737e5  pop     rbp
0x1800737e6  retn
```
