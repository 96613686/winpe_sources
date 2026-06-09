# FwppCalloutInit

- ea: `0x180052008`
- end: `0x18005215d`
- name: `FwppCalloutInit`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000faa0`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x1800203c0`
- `0x1800208c0`
- `0x180052008`
- `0x180052164`
- `0x18005320c`
- `0x1800664d8`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1800520ce`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1800520ce`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x18005203a`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x18005203a`
- `NETIO!KfdRegisterCalloutTelemetryValidateFn` at `0x18005214f`
- `NETIO!KfdRegisterCalloutTelemetryValidateFn` at `0x18005214f`
- `NETIO!KfdRegisterCalloutFilterChangeNotify` at `0x18005213c`
- `NETIO!KfdRegisterCalloutFilterChangeNotify` at `0x18005213c`

## string_xrefs

- `0x1800520f0`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 FwppCalloutInit()
{
  __int64 v0; // rbx
  __int64 v1; // r8
  GUID **v2; // r9
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // ecx
  int RegistryValues; // eax
  __int64 v8; // rcx
  _QWORD v10[14]; // [rsp+30h] [rbp-88h] BYREF

  memset(v10, 0, sizeof(v10));
  KeInitializeGuardedMutex(&gFwppCallouts);
  v0 = FwppCalloutReserve(256);
  if ( v0 )
    goto LABEL_7;
  v1 = 0;
  v2 = &FWPP_BUILTIN_CALLOUTS;
  do
  {
    v3 = FwppCalloutFindById(LODWORD(v2[2 * v1 + 1]));
    v1 = v5 + 1;
    *(GUID *)v3 = *v2[v4];
    v6 = (int)v2[v4 + 1];
    *(_DWORD *)(v3 + 32) |= 1u;
    *(_DWORD *)(v3 + 16) = v6;
    *(_DWORD *)(v3 + 24) = 1;
  }
  while ( v1 != 50 );
  LODWORD(v10[1]) = 16;
  v10[0] = FwppCalloutAddPersistent;
  RegistryValues = RtlQueryRegistryValuesEx(2147483649LL, L"BFE\\Parameters\\Policy\\Persistent\\Callout", v10, 0, 0);
  v8 = RegistryValues + 0x80000000;
  if ( (int)v8 < 0 || RegistryValues == -1073741772 )
  {
    KfdRegisterCalloutFilterChangeNotify(FwppCalloutModifyNumReferencingFilters);
    KfdRegisterCalloutTelemetryValidateFn(FwppCalloutHasReferencingFilters);
    return v0;
  }
  v0 = WfpReportSysErrorAsNtStatus(v8, (int)"RtlQueryRegistryValuesEx", RegistryValues);
  if ( v0 )
  {
LABEL_7:
    FwppCalloutShutdown();
    WfpReportError(v0, (int)"FwppCalloutInit");
  }
  return v0;
}

```

## disassembly

```asm
0x180052008  push    rbx
0x18005200a  sub     rsp, 0B0h
0x180052011  mov     rax, cs:__security_cookie
0x180052018  xor     rax, rsp
0x18005201b  mov     [rsp+0B8h+var_18], rax
0x180052023  xor     edx, edx; Val
0x180052025  lea     rcx, [rsp+0B8h+var_88]; void *
0x18005202a  lea     r8d, [rdx+70h]; Size
0x18005202e  call    memset
0x180052033  lea     rcx, gFwppCallouts; Mutex
0x18005203a  call    cs:__imp_KeInitializeGuardedMutex
0x180052041  nop     dword ptr [rax+rax+00h]
0x180052046  mov     ecx, 100h
0x18005204b  call    FwppCalloutReserve
0x180052050  mov     rbx, rax
0x180052053  test    rax, rax
0x180052056  jnz     loc_180052104
0x18005205c  xor     r8d, r8d
0x18005205f  lea     r9, FWPP_BUILTIN_CALLOUTS
0x180052066  mov     rdx, r8
0x180052069  add     rdx, rdx
0x18005206c  mov     ecx, [r9+rdx*8+8]
0x180052071  call    FwppCalloutFindById
0x180052076  mov     rcx, [r9+rdx*8]
0x18005207a  inc     r8
0x18005207d  movups  xmm0, xmmword ptr [rcx]
0x180052080  movdqu  xmmword ptr [rax], xmm0
0x180052084  mov     ecx, [r9+rdx*8+8]
0x180052089  or      dword ptr [rax+20h], 1
0x18005208d  mov     [rax+10h], ecx
0x180052090  mov     dword ptr [rax+18h], 1
0x180052097  cmp     r8, 32h ; '2'
0x18005209b  jnz     short loc_180052066
0x18005209d  lea     rax, FwppCalloutAddPersistent
0x1800520a4  mov     [rsp+0B8h+var_80], 10h
0x1800520ac  xor     r9d, r9d
0x1800520af  mov     [rsp+0B8h+var_88], rax
0x1800520b4  lea     r8, [rsp+0B8h+var_88]
0x1800520b9  mov     [rsp+0B8h+var_98], 0
0x1800520c2  lea     rdx, aBfeParametersP; "BFE\\Parameters\\Policy\\Persistent\\Ca"...
0x1800520c9  mov     ecx, 80000001h
0x1800520ce  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800520d5  nop     dword ptr [rax+rax+00h]
0x1800520da  mov     edx, 80000000h
0x1800520df  lea     ecx, [rax+rdx]
0x1800520e2  test    edx, ecx
0x1800520e4  jnz     short loc_180052135
0x1800520e6  cmp     eax, 0C0000034h
0x1800520eb  jz      short loc_180052135
0x1800520ed  mov     r8d, eax
0x1800520f0  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1800520f7  call    WfpReportSysErrorAsNtStatus
0x1800520fc  mov     rbx, rax
0x1800520ff  test    rax, rax
0x180052102  jz      short loc_180052118
0x180052104  call    FwppCalloutShutdown
0x180052109  lea     rdx, aFwppcalloutini; "FwppCalloutInit"
0x180052110  mov     rcx, rbx
0x180052113  call    WfpReportError
0x180052118  mov     rax, rbx
0x18005211b  mov     rcx, [rsp+0B8h+var_18]
0x180052123  xor     rcx, rsp; StackCookie
0x180052126  call    __security_check_cookie
0x18005212b  add     rsp, 0B0h
0x180052132  pop     rbx
0x180052133  retn
0x180052135  lea     rcx, FwppCalloutModifyNumReferencingFilters
0x18005213c  call    cs:__imp_KfdRegisterCalloutFilterChangeNotify
0x180052143  nop     dword ptr [rax+rax+00h]
0x180052148  lea     rcx, FwppCalloutHasReferencingFilters
0x18005214f  call    cs:__imp_KfdRegisterCalloutTelemetryValidateFn
0x180052156  nop     dword ptr [rax+rax+00h]
0x18005215b  jmp     short loc_180052118
```
