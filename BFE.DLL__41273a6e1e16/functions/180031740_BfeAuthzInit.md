# BfeAuthzInit

- ea: `0x180031740`
- end: `0x18003195d`
- name: `BfeAuthzInit`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040a40`

## callees

- `0x180004094`
- `0x180004798`
- `0x180012d8c`
- `0x1800197d0`
- `0x180023f18`
- `0x180031740`
- `0x180031aa8`
- `0x180032420`
- `0x180032628`
- `0x1800588e4`
- `0x18006aa98`
- `0x18006be5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031841`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031831`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031831`

## string_xrefs

- `0x180031850`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x180031864`: `BfeSecurityDescriptorCreateFromSddl`

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
  String = WfpHashtableCreate(&qword_1800F5AD0);
  if ( String )
    goto LABEL_20;
  dword_1800F5AF8 = 1;
  qword_1800F5B20 = (__int64)&qword_1800F5B18;
  v1 = &qword_1800F5B18;
  qword_1800F5B18 = (__int64)&qword_1800F5B18;
  v2 = 0;
  qword_1800F5B00 = 0;
  while ( 1 )
  {
    if ( (__int64 *)*v1 != &qword_1800F5B18 )
      __fastfail(3u);
    v3 = 5 * v2++;
    v4 = &qword_1800F5B28[v3];
    *v4 = (__int64)&qword_1800F5B18;
    v4[1] = (__int64)v1;
    *v1 = (__int64)v4;
    qword_1800F5B20 = (__int64)v4;
    if ( v2 >= 5 )
      break;
    v1 = &qword_1800F5B28[v3];
  }
  String = BfeObjectSecurityLoad(0, 1, (__int64)&ParentDescriptor);
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
     || (dword_1800F5C70 = 1,
         (String = WfpAuditPolicyNotifyCreate(
                     0,
                     1u,
                     (char *)&WFP_DRIVER_AUDIT_POLICY_INFO,
                     (__int64)BfeAuditOnDriverPolicyChange,
                     IsContainerObject,
                     &qword_1800F5C78)) != 0))
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
0x180031740  mov     [rsp+arg_0], rbx
0x180031745  mov     [rsp+arg_8], rbp
0x18003174a  push    rdi
0x18003174b  sub     rsp, 40h
0x18003174f  lea     rbp, gBfeAuthz
0x180031756  mov     rcx, rbp
0x180031759  call    WfpCriticalSectionCreate
0x18003175e  mov     rbx, rax
0x180031761  test    rax, rax
0x180031764  jnz     loc_180031929
0x18003176a  lea     rcx, qword_1800F5AD0
0x180031771  call    WfpHashtableCreate
0x180031776  mov     rbx, rax
0x180031779  test    rax, rax
0x18003177c  jnz     loc_180031929
0x180031782  lea     r9, qword_1800F5B18
0x180031789  mov     cs:dword_1800F5AF8, 1
0x180031793  mov     cs:qword_1800F5B20, r9
0x18003179a  mov     rcx, r9
0x18003179d  mov     cs:qword_1800F5B18, r9
0x1800317a4  xor     r8d, r8d
0x1800317a7  mov     cs:qword_1800F5B00, rax
0x1800317ae  cmp     [rcx], r9
0x1800317b1  jnz     loc_180031956
0x1800317b7  lea     rax, [r8+r8*4]
0x1800317bb  inc     r8
0x1800317be  lea     rdx, [rbp+88h]
0x1800317c5  lea     rdx, [rdx+rax*8]
0x1800317c9  mov     [rdx], r9
0x1800317cc  mov     [rdx+8], rcx
0x1800317d0  mov     [rcx], rdx
0x1800317d3  mov     cs:qword_1800F5B20, rdx
0x1800317da  cmp     r8, 5
0x1800317de  jnb     short loc_1800317E5
0x1800317e0  mov     rcx, rdx
0x1800317e3  jmp     short loc_1800317AE
0x1800317e5  lea     rax, ParentDescriptor
0x1800317ec  xor     r9d, r9d
0x1800317ef  mov     [rsp+48h+var_20], rax; __int64
0x1800317f4  lea     r8, aOLsgLsdAOiciGa; "O:LSG:LSD:(A;OICI;GA;;;BA)(A;OICI;GRGWG"...
0x1800317fb  lea     rdx, FWPM_OBJECT_TYPE_ENGINE
0x180031802  mov     [rsp+48h+IsContainerObject], 1; int
0x18003180a  xor     ecx, ecx; ParentDescriptor
0x18003180c  call    BfeObjectSecurityLoad
0x180031811  mov     rbx, rax
0x180031814  test    rax, rax
0x180031817  jnz     loc_180031929
0x18003181d  xor     r9d, r9d; SecurityDescriptorSize
0x180031820  lea     r8, SecurityDescriptor; SecurityDescriptor
0x180031827  lea     edx, [rax+1]; StringSDRevision
0x18003182a  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x00000001;;;BA)"
0x180031831  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180031838  nop     dword ptr [rax+rax+00h]
0x18003183d  test    eax, eax
0x18003183f  jnz     short loc_18003187D
0x180031841  call    cs:__imp_GetLastError
0x180031848  nop     dword ptr [rax+rax+00h]
0x18003184d  mov     r8d, eax
0x180031850  lea     rdx, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x180031857  call    WfpReportSysErrorAsWinError
0x18003185c  mov     rbx, rax
0x18003185f  test    rax, rax
0x180031862  jz      short loc_18003187D
0x180031864  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorCreateFromSddl"
0x18003186b  mov     rcx, rax
0x18003186e  call    WfpReportError
0x180031873  call    BfeAuthzShutdown
0x180031878  jmp     loc_180031933
0x18003187d  lea     rdx, qword_1800F5C00
0x180031884  mov     ecx, 259h; uID
0x180031889  call    WfpLoadString
0x18003188e  mov     rbx, rax
0x180031891  test    rax, rax
0x180031894  jnz     loc_180031929
0x18003189a  xor     edi, edi
0x18003189c  cmp     rdi, 0Dh
0x1800318a0  jnb     short loc_1800318C9
0x1800318a2  lea     rcx, BFE_AUDIT_MATCH_TYPE_RESRCS
0x1800318a9  mov     ecx, [rcx+rdi*4]; uID
0x1800318ac  lea     rdx, [rbp+168h]
0x1800318b3  lea     rdx, [rdx+rdi*8]
0x1800318b7  call    WfpLoadString
0x1800318bc  mov     rbx, rax
0x1800318bf  test    rax, rax
0x1800318c2  jnz     short loc_180031929
0x1800318c4  inc     rdi
0x1800318c7  jmp     short loc_18003189C
0x1800318c9  call    BfeGlobalConfigIsAuditEnabled
0x1800318ce  test    eax, eax
0x1800318d0  jz      short loc_180031915
0x1800318d2  call    WfpAuditInitialize
0x1800318d7  mov     rbx, rax
0x1800318da  test    rax, rax
0x1800318dd  jnz     short loc_180031929
0x1800318df  lea     rax, qword_1800F5C78
0x1800318e6  mov     cs:dword_1800F5C70, 1
0x1800318f0  lea     r9, BfeAuditOnDriverPolicyChange
0x1800318f7  mov     [rsp+48h+var_20], rax; __int64
0x1800318fc  lea     r8, WFP_DRIVER_AUDIT_POLICY_INFO
0x180031903  xor     ecx, ecx; pSourceSid
0x180031905  lea     edx, [rbx+1]
0x180031908  call    WfpAuditPolicyNotifyCreate
0x18003190d  mov     rbx, rax
0x180031910  test    rax, rax
0x180031913  jnz     short loc_180031929
0x180031915  mov     rcx, cs:ParentDescriptor; InputBuffer
0x18003191c  call    BfeDriverSetEngineSecurityDescriptor
0x180031921  mov     rbx, rax
0x180031924  test    rax, rax
0x180031927  jz      short loc_180031942
0x180031929  call    BfeAuthzShutdown
0x18003192e  test    rbx, rbx
0x180031931  jz      short loc_180031942
0x180031933  lea     rdx, aBfeauthzinit; "BfeAuthzInit"
0x18003193a  mov     rcx, rbx
0x18003193d  call    WfpReportError
0x180031942  mov     rbp, [rsp+48h+arg_8]
0x180031947  mov     rax, rbx
0x18003194a  mov     rbx, [rsp+48h+arg_0]
0x18003194f  add     rsp, 40h
0x180031953  pop     rdi
0x180031954  retn
0x180031956  mov     ecx, 3
0x18003195b  int     29h; Win8: RtlFailFast(ecx)
```
