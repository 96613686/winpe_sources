# BfeAuthzInit

- ea: `0x18002fe28`
- end: `0x180030038`
- name: `BfeAuthzInit`
- size: `528`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f7a0`

## callees

- `0x1800040ac`
- `0x18000474c`
- `0x18001236c`
- `0x180018b74`
- `0x180021858`
- `0x18002fe28`
- `0x180030180`
- `0x18003da38`
- `0x18003dc24`
- `0x180056a24`
- `0x1800684cc`
- `0x180069888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff23`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ff19`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ff19`

## string_xrefs

- `0x18002ff2c`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x18002ff40`: `BfeSecurityDescriptorCreateFromSddl`

## pseudocode

```c
__int64 BfeAuthzInit()
{
  __int64 String; // rbx
  __int64 *v1; // rcx
  unsigned __int64 v2; // r8
  __int64 v3; // rax
  __int64 *v4; // rdx
  DWORD LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int64 i; // rdi
  BOOL IsContainerObject; // [rsp+20h] [rbp-28h]

  String = WfpCriticalSectionCreate(&gBfeAuthz);
  if ( String )
    goto LABEL_20;
  String = WfpHashtableCreate(&qword_1800F2AB0);
  if ( String )
    goto LABEL_20;
  dword_1800F2AD8 = 1;
  qword_1800F2B00 = (__int64)&qword_1800F2AF8;
  v1 = &qword_1800F2AF8;
  qword_1800F2AF8 = (__int64)&qword_1800F2AF8;
  v2 = 0;
  qword_1800F2AE0 = 0;
  while ( 1 )
  {
    if ( (__int64 *)*v1 != &qword_1800F2AF8 )
      __fastfail(3u);
    v3 = 5 * v2++;
    v4 = &qword_1800F2B08[v3];
    *v4 = (__int64)&qword_1800F2AF8;
    v4[1] = (__int64)v1;
    *v1 = (__int64)v4;
    qword_1800F2B00 = (__int64)v4;
    if ( v2 >= 5 )
      break;
    v1 = &qword_1800F2B08[v3];
  }
  String = BfeObjectSecurityLoad(
             0,
             (__int64)FWPM_OBJECT_TYPE_ENGINE,
             (__int64)L"O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWGX;;;NO)(A;OICI;GRGWGX;;;S-1-5-80-3088073201-1464728630-1879"
                       "813800-1107566885-823218052)(A;OICI;GRGX;;;S-1-5-80-3635958274-2059881490-2225992882-984577281-63"
                       "3327304)(A;OICI;GRGWGX;;;S-1-5-80-3044542841-3639452079-4096941652-1606687743-1256249853)(A;OICI;"
                       "GRGWGX;;;S-1-5-80-979556362-403687129-3954533659-2335141334-1547273080)(A;OICI;GRGX;;;S-1-5-80-31"
                       "39157870-2983391045-3678747466-658725712-1809340420)(A;OICI;GRGWGX;;;S-1-5-80-1510742542-36323974"
                       "84-604094731-3920060944-1272132581)(A;OICI;0x50;;;WD)",
             0,
             1,
             &ParentDescriptor);
  if ( String )
    goto LABEL_20;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0x00000001;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v7 = WfpReportSysErrorAsWinError(v6, "ConvertStringSecurityDescriptorToSecurityDescriptorW", LastError);
    String = v7;
    if ( v7 )
    {
      WfpReportError(v7, "BfeSecurityDescriptorCreateFromSddl");
      BfeAuthzShutdown();
LABEL_21:
      WfpReportError(String, "BfeAuthzInit");
      return String;
    }
  }
  String = WfpLoadString(0x259u);
  if ( String )
    goto LABEL_20;
  for ( i = 0; i < 0xD; ++i )
  {
    String = WfpLoadString(*((_DWORD *)BFE_AUDIT_MATCH_TYPE_RESRCS + i));
    if ( String )
      goto LABEL_20;
  }
  if ( (unsigned int)BfeGlobalConfigIsAuditEnabled()
    && ((String = WfpAuditInitialize()) != 0
     || (dword_1800F2C50 = 1, (String = WfpAuditPolicyNotifyCreate(0, IsContainerObject, (__int64)&qword_1800F2C58)) != 0))
    || (String = BfeDriverSetEngineSecurityDescriptor(ParentDescriptor)) != 0 )
  {
LABEL_20:
    BfeAuthzShutdown();
    goto LABEL_21;
  }
  return String;
}

```

## disassembly

```asm
0x18002fe28  mov     [rsp+arg_0], rbx
0x18002fe2d  mov     [rsp+arg_8], rbp
0x18002fe32  push    rdi
0x18002fe33  sub     rsp, 40h
0x18002fe37  lea     rbp, gBfeAuthz
0x18002fe3e  mov     rcx, rbp
0x18002fe41  call    WfpCriticalSectionCreate
0x18002fe46  mov     rbx, rax
0x18002fe49  test    rax, rax
0x18002fe4c  jnz     loc_180030005
0x18002fe52  lea     rcx, qword_1800F2AB0
0x18002fe59  call    WfpHashtableCreate
0x18002fe5e  mov     rbx, rax
0x18002fe61  test    rax, rax
0x18002fe64  jnz     loc_180030005
0x18002fe6a  lea     r9, qword_1800F2AF8
0x18002fe71  mov     cs:dword_1800F2AD8, 1
0x18002fe7b  mov     cs:qword_1800F2B00, r9
0x18002fe82  mov     rcx, r9
0x18002fe85  mov     cs:qword_1800F2AF8, r9
0x18002fe8c  xor     r8d, r8d
0x18002fe8f  mov     cs:qword_1800F2AE0, rax
0x18002fe96  cmp     [rcx], r9
0x18002fe99  jnz     loc_180030031
0x18002fe9f  lea     rax, [r8+r8*4]
0x18002fea3  inc     r8
0x18002fea6  lea     rdx, [rbp+88h]
0x18002fead  lea     rdx, [rdx+rax*8]
0x18002feb1  mov     [rdx], r9
0x18002feb4  mov     [rdx+8], rcx
0x18002feb8  mov     [rcx], rdx
0x18002febb  mov     cs:qword_1800F2B00, rdx
0x18002fec2  cmp     r8, 5
0x18002fec6  jnb     short loc_18002FECD
0x18002fec8  mov     rcx, rdx
0x18002fecb  jmp     short loc_18002FE96
0x18002fecd  lea     rax, ParentDescriptor
0x18002fed4  xor     r9d, r9d
0x18002fed7  mov     [rsp+48h+var_20], rax; __int64
0x18002fedc  lea     r8, aOLsgLsdAOiciGa; "O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWG"...
0x18002fee3  lea     rdx, FWPM_OBJECT_TYPE_ENGINE
0x18002feea  mov     [rsp+48h+IsContainerObject], 1; int
0x18002fef2  xor     ecx, ecx; ParentDescriptor
0x18002fef4  call    BfeObjectSecurityLoad
0x18002fef9  mov     rbx, rax
0x18002fefc  test    rax, rax
0x18002feff  jnz     loc_180030005
0x18002ff05  xor     r9d, r9d; SecurityDescriptorSize
0x18002ff08  lea     r8, SecurityDescriptor; SecurityDescriptor
0x18002ff0f  lea     edx, [rax+1]; StringSDRevision
0x18002ff12  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x00000001;;;BA)"
0x18002ff19  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ff1f  test    eax, eax
0x18002ff21  jnz     short loc_18002FF59
0x18002ff23  call    cs:__imp_GetLastError
0x18002ff29  mov     r8d, eax
0x18002ff2c  lea     rdx, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x18002ff33  call    WfpReportSysErrorAsWinError
0x18002ff38  mov     rbx, rax
0x18002ff3b  test    rax, rax
0x18002ff3e  jz      short loc_18002FF59
0x18002ff40  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorCreateFromSddl"
0x18002ff47  mov     rcx, rax
0x18002ff4a  call    WfpReportError
0x18002ff4f  call    BfeAuthzShutdown
0x18002ff54  jmp     loc_18003000F
0x18002ff59  lea     rdx, qword_1800F2BE0
0x18002ff60  mov     ecx, 259h; uID
0x18002ff65  call    WfpLoadString
0x18002ff6a  mov     rbx, rax
0x18002ff6d  test    rax, rax
0x18002ff70  jnz     loc_180030005
0x18002ff76  xor     edi, edi
0x18002ff78  cmp     rdi, 0Dh
0x18002ff7c  jnb     short loc_18002FFA5
0x18002ff7e  lea     rcx, BFE_AUDIT_MATCH_TYPE_RESRCS
0x18002ff85  mov     ecx, [rcx+rdi*4]; uID
0x18002ff88  lea     rdx, [rbp+168h]
0x18002ff8f  lea     rdx, [rdx+rdi*8]
0x18002ff93  call    WfpLoadString
0x18002ff98  mov     rbx, rax
0x18002ff9b  test    rax, rax
0x18002ff9e  jnz     short loc_180030005
0x18002ffa0  inc     rdi
0x18002ffa3  jmp     short loc_18002FF78
0x18002ffa5  call    BfeGlobalConfigIsAuditEnabled
0x18002ffaa  test    eax, eax
0x18002ffac  jz      short loc_18002FFF1
0x18002ffae  call    WfpAuditInitialize
0x18002ffb3  mov     rbx, rax
0x18002ffb6  test    rax, rax
0x18002ffb9  jnz     short loc_180030005
0x18002ffbb  lea     rax, qword_1800F2C58
0x18002ffc2  mov     cs:dword_1800F2C50, 1
0x18002ffcc  lea     r9, BfeAuditOnDriverPolicyChange
0x18002ffd3  mov     [rsp+48h+var_20], rax; __int64
0x18002ffd8  lea     r8, WFP_DRIVER_AUDIT_POLICY_INFO
0x18002ffdf  xor     ecx, ecx; pSourceSid
0x18002ffe1  lea     edx, [rbx+1]
0x18002ffe4  call    WfpAuditPolicyNotifyCreate
0x18002ffe9  mov     rbx, rax
0x18002ffec  test    rax, rax
0x18002ffef  jnz     short loc_180030005
0x18002fff1  mov     rcx, cs:ParentDescriptor; InputBuffer
0x18002fff8  call    BfeDriverSetEngineSecurityDescriptor
0x18002fffd  mov     rbx, rax
0x180030000  test    rax, rax
0x180030003  jz      short loc_18003001E
0x180030005  call    BfeAuthzShutdown
0x18003000a  test    rbx, rbx
0x18003000d  jz      short loc_18003001E
0x18003000f  lea     rdx, aBfeauthzinit; "BfeAuthzInit"
0x180030016  mov     rcx, rbx
0x180030019  call    WfpReportError
0x18003001e  mov     rbp, [rsp+48h+arg_8]
0x180030023  mov     rax, rbx
0x180030026  mov     rbx, [rsp+48h+arg_0]
0x18003002b  add     rsp, 40h
0x18003002f  pop     rdi
0x180030030  retn
0x180030031  mov     ecx, 3
0x180030036  int     29h; Win8: RtlFailFast(ecx)
```
