# BfeRelativeSecurityDescriptorValidate

- ea: `0x180024078`
- end: `0x18002418e`
- name: `BfeRelativeSecurityDescriptorValidate`
- size: `278`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008cb0`
- `0x18000a140`
- `0x18000a730`
- `0x180023300`
- `0x180023f50`
- `0x18002eb1c`
- `0x180030180`
- `0x180071aa8`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180024078`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800240c2`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800240c2`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800240a6`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800240a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002416b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002416b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002410c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002410c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800240fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800240fb`

## string_xrefs

- `0x18002411a`: `RtlValidRelativeSecurityDescriptor`
- `0x18002415d`: `RtlGetSaclSecurityDescriptor`
- `0x180024174`: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- `0x180024151`: `BfeRelativeSecurityDescriptorValidate`
- `0x18002417d`: `BfeRelativeSecurityDescriptorValidate`

## pseudocode

```c
__int64 __fastcall BfeRelativeSecurityDescriptorValidate(PSECURITY_DESCRIPTOR SecurityDescriptor, ULONG a2)
{
  __int64 v3; // rcx
  NTSTATUS SaclSecurityDescriptor; // eax
  __int64 v5; // rbx
  __int64 LastError; // r8
  const char *v7; // rdx
  __int64 v8; // rax
  PACL Sacl; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 SaclPresent; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 SaclDefaulted[7]; // [rsp+41h] [rbp-17h] BYREF

  SaclPresent = 0;
  SaclDefaulted[0] = 0;
  Sacl = 0;
  if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptor, a2, 0) )
  {
    LastError = 1338;
    v7 = "RtlValidRelativeSecurityDescriptor";
LABEL_7:
    v8 = WfpReportSysErrorAsWinError(v3, v7, LastError);
    goto LABEL_8;
  }
  SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, SaclDefaulted);
  if ( SaclSecurityDescriptor >= 0 )
  {
    if ( Sacl && SaclPresent )
    {
      LastError = 50;
      v7 = "BfeRelativeSecurityDescriptorValidate";
    }
    else
    {
      StringSecurityDescriptor = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
             SecurityDescriptor,
             1u,
             0xFu,
             &StringSecurityDescriptor,
             0) )
      {
        v5 = 0;
        LocalFree(StringSecurityDescriptor);
        return v5;
      }
      LastError = GetLastError();
      v7 = "ConvertSecurityDescriptorToStringSecurityDescriptorW";
    }
    goto LABEL_7;
  }
  v8 = WfpReportSysErrorAsNtStatus(v3, "RtlGetSaclSecurityDescriptor", (unsigned int)SaclSecurityDescriptor);
LABEL_8:
  v5 = v8;
  if ( v8 )
    WfpReportError(v8, "BfeRelativeSecurityDescriptorValidate");
  return v5;
}

```

## disassembly

```asm
0x180024078  push    rbx
0x18002407a  sub     rsp, 50h
0x18002407e  mov     rax, cs:__security_cookie
0x180024085  xor     rax, rsp
0x180024088  mov     [rsp+58h+var_10], rax
0x18002408d  xor     r8d, r8d; RequiredInformation
0x180024090  mov     [rsp+58h+SaclPresent], 0
0x180024095  mov     rbx, rcx
0x180024098  mov     [rsp+58h+SaclDefaulted], 0
0x18002409d  mov     [rsp+58h+Sacl], 0
0x1800240a6  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800240ac  test    al, al
0x1800240ae  jz      short loc_180024114
0x1800240b0  lea     r9, [rsp+58h+SaclDefaulted]; SaclDefaulted
0x1800240b5  mov     rcx, rbx; SecurityDescriptor
0x1800240b8  lea     r8, [rsp+58h+Sacl]; Sacl
0x1800240bd  lea     rdx, [rsp+58h+SaclPresent]; SaclPresent
0x1800240c2  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1800240c8  test    eax, eax
0x1800240ca  js      loc_18002415A
0x1800240d0  cmp     [rsp+58h+Sacl], 0
0x1800240d6  jnz     short loc_180024144
0x1800240d8  mov     edx, 1; RequestedStringSDRevision
0x1800240dd  mov     [rsp+58h+StringSecurityDescriptor], 0
0x1800240e6  lea     r9, [rsp+58h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800240eb  mov     [rsp+58h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x1800240f4  mov     rcx, rbx; SecurityDescriptor
0x1800240f7  lea     r8d, [rdx+0Eh]; SecurityInformation
0x1800240fb  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180024101  test    eax, eax
0x180024103  jz      short loc_18002416B
0x180024105  mov     rcx, [rsp+58h+StringSecurityDescriptor]; hMem
0x18002410a  xor     ebx, ebx
0x18002410c  call    cs:__imp_LocalFree
0x180024112  jmp     short loc_18002412E
0x180024114  mov     r8d, 53Ah
0x18002411a  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x180024121  call    WfpReportSysErrorAsWinError
0x180024126  mov     rbx, rax
0x180024129  test    rax, rax
0x18002412c  jnz     short loc_18002417D
0x18002412e  mov     rax, rbx
0x180024131  mov     rcx, [rsp+58h+var_10]
0x180024136  xor     rcx, rsp; StackCookie
0x180024139  call    __security_check_cookie
0x18002413e  add     rsp, 50h
0x180024142  pop     rbx
0x180024143  retn
0x180024144  cmp     [rsp+58h+SaclPresent], 0
0x180024149  jz      short loc_1800240D8
0x18002414b  mov     r8d, 32h ; '2'
0x180024151  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x180024158  jmp     short loc_180024121
0x18002415a  mov     r8d, eax
0x18002415d  lea     rdx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor"
0x180024164  call    WfpReportSysErrorAsNtStatus
0x180024169  jmp     short loc_180024126
0x18002416b  call    cs:__imp_GetLastError
0x180024171  mov     r8d, eax
0x180024174  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x18002417b  jmp     short loc_180024121
0x18002417d  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x180024184  mov     rcx, rbx
0x180024187  call    WfpReportError
0x18002418c  jmp     short loc_18002412E
```
