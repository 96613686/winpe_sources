# ClearTPMIfNotReady(void)

- ea: `0x18000f8ac`
- end: `0x18000fa3a`
- name: `?ClearTPMIfNotReady@@YAJXZ`
- size: `398`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000f8ac`
- `0x18000fa40`
- `0x18001a6ec`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000f93a`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000f93a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f979`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f979`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9b9`
- `TpmCoreProvisioning!TpmIsReadyInformation` at `0x18000f9d9`
- `TpmCoreProvisioning!TpmIsReadyInformation` at `0x18000f9d9`

## string_xrefs

- `0x18000f951`: `ClearTPMIfNotReadyCSP`
- `0x18000f991`: `ClearTPMIfNotReadyGP`

## pseudocode

```c
__int64 ClearTPMIfNotReady(void)
{
  unsigned __int8 v0; // bl
  int IsReadyInformation; // eax
  unsigned __int8 v3[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v5; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int pvData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v7; // [rsp+50h] [rbp-B0h] BYREF
  int v8[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  pvData = 0;
  v5 = 0;
  pcbData = 4;
  v3[0] = 0;
  v7 = 0;
  memset_0(SubKey, 0, 0x208u);
  v8[0] = 520;
  RtlGetPersistedStateLocation(
    L"TpmRegDriverGroupPolicyData",
    0,
    L"Software\\Policies\\Microsoft\\Tpm",
    0,
    SubKey,
    520,
    v8);
  RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ClearTPMIfNotReadyCSP", 0x10u, 0, &pvData, &pcbData);
  pcbData = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ClearTPMIfNotReadyGP", 0x10u, 0, &v5, &pcbData);
  if ( pvData || v5 )
  {
    v0 = 0;
    IsReadyInformation = TpmIsReadyInformation(v3, &v7);
    if ( IsReadyInformation >= 0 && !v3[0] && (v7 & 0x1B20) != 0 )
    {
      IsReadyInformation = ScheduleAdminClearTask();
      v0 = IsReadyInformation >= 0;
    }
    ProvisionTelemetryProvider::ClearTPMIfNotReady(IsReadyInformation, v0, pvData, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f8ac  mov     [rsp-8+arg_0], rbx
0x18000f8b1  push    rbp
0x18000f8b2  lea     rbp, [rsp-180h]
0x18000f8ba  sub     rsp, 280h
0x18000f8c1  mov     rax, cs:__security_cookie
0x18000f8c8  xor     rax, rsp
0x18000f8cb  mov     [rbp+180h+var_10], rax
0x18000f8d2  mov     ebx, 208h
0x18000f8d7  mov     [rsp+280h+var_234], 0
0x18000f8df  mov     r8d, ebx; Size
0x18000f8e2  mov     [rsp+280h+var_238], 0
0x18000f8ea  xor     edx, edx; Val
0x18000f8ec  mov     [rsp+280h+var_23C], 4
0x18000f8f4  lea     rcx, [rsp+280h+SubKey]; void *
0x18000f8f9  mov     [rsp+280h+var_240], 0
0x18000f8fe  mov     [rsp+280h+var_230], 0
0x18000f906  call    memset_0
0x18000f90b  lea     rax, [rsp+280h+var_22C]
0x18000f910  mov     [rsp+280h+var_22C], ebx
0x18000f914  mov     [rsp+280h+pcbData], rax
0x18000f919  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Tpm"
0x18000f920  lea     rax, [rsp+280h+SubKey]
0x18000f925  mov     dword ptr [rsp+280h+pvData], ebx
0x18000f929  xor     r9d, r9d
0x18000f92c  mov     [rsp+280h+pdwType], rax
0x18000f931  xor     edx, edx
0x18000f933  lea     rcx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x18000f93a  call    cs:__imp_RtlGetPersistedStateLocation
0x18000f940  lea     rax, [rsp+280h+var_23C]
0x18000f945  mov     rbx, 0FFFFFFFF80000002h
0x18000f94c  mov     [rsp+280h+pcbData], rax; pcbData
0x18000f951  lea     r8, aCleartpmifnotr_0; "ClearTPMIfNotReadyCSP"
0x18000f958  lea     rax, [rsp+280h+var_234]
0x18000f95d  mov     r9d, 10h; dwFlags
0x18000f963  mov     [rsp+280h+pvData], rax; pvData
0x18000f968  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18000f96d  mov     rcx, rbx; hkey
0x18000f970  mov     [rsp+280h+pdwType], 0; pdwType
0x18000f979  call    cs:__imp_RegGetValueW
0x18000f97f  lea     rax, [rsp+280h+var_23C]
0x18000f984  mov     [rsp+280h+var_23C], 4
0x18000f98c  mov     [rsp+280h+pcbData], rax; pcbData
0x18000f991  lea     r8, aCleartpmifnotr_1; "ClearTPMIfNotReadyGP"
0x18000f998  lea     rax, [rsp+280h+var_238]
0x18000f99d  mov     r9d, 10h; dwFlags
0x18000f9a3  mov     [rsp+280h+pvData], rax; pvData
0x18000f9a8  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18000f9ad  mov     rcx, rbx; hkey
0x18000f9b0  mov     [rsp+280h+pdwType], 0; pdwType
0x18000f9b9  call    cs:__imp_RegGetValueW
0x18000f9bf  cmp     [rsp+280h+var_234], 0
0x18000f9c4  jnz     short loc_18000F9CD
0x18000f9c6  cmp     [rsp+280h+var_238], 0
0x18000f9cb  jz      short loc_18000FA18
0x18000f9cd  lea     rdx, [rsp+280h+var_230]
0x18000f9d2  xor     bl, bl
0x18000f9d4  lea     rcx, [rsp+280h+var_240]
0x18000f9d9  call    cs:__imp_?TpmIsReadyInformation@@YAJPEAEPEAI@Z; TpmIsReadyInformation(uchar *,uint *)
0x18000f9df  test    eax, eax
0x18000f9e1  js      short loc_18000FA05
0x18000f9e3  cmp     [rsp+280h+var_240], bl
0x18000f9e7  jnz     short loc_18000FA05
0x18000f9e9  test    [rsp+280h+var_230], 1B20h
0x18000f9f1  jz      short loc_18000FA05
0x18000f9f3  call    ?ScheduleAdminClearTask@@YAJXZ; ScheduleAdminClearTask(void)
0x18000f9f8  test    eax, eax
0x18000f9fa  movzx   ebx, bl
0x18000f9fd  mov     ecx, 1
0x18000fa02  cmovns  ebx, ecx
0x18000fa05  mov     r9d, [rsp+280h+var_238]; unsigned int
0x18000fa0a  mov     dl, bl; unsigned __int8
0x18000fa0c  mov     r8d, [rsp+280h+var_234]; unsigned int
0x18000fa11  mov     ecx, eax; int
0x18000fa13  call    ?ClearTPMIfNotReady@ProvisionTelemetryProvider@@SAXJEII@Z; ProvisionTelemetryProvider::ClearTPMIfNotReady(long,uchar,uint,uint)
0x18000fa18  xor     eax, eax
0x18000fa1a  mov     rcx, [rbp+180h+var_10]
0x18000fa21  xor     rcx, rsp; StackCookie
0x18000fa24  call    __security_check_cookie
0x18000fa29  mov     rbx, [rsp+280h+arg_0]
0x18000fa31  add     rsp, 280h
0x18000fa38  pop     rbp
0x18000fa39  retn
```
