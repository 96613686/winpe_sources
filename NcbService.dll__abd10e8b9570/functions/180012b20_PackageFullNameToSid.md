# PackageFullNameToSid

- ea: `0x180012b20`
- end: `0x180012bd5`
- name: `PackageFullNameToSid`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022b80`

## callees

- `0x18000a0a0`
- `0x180012b20`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180012b68`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180012b68`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180012b54`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180012b54`

## string_xrefs

- `0x180012bc4`: `NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - `

## pseudocode

```c
__int64 __fastcall PackageFullNameToSid(const WCHAR *a1)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  UINT32 packageFamilyNameLength; // [rsp+20h] [rbp-238h] BYREF
  __int64 v9; // [rsp+28h] [rbp-230h] BYREF
  WCHAR packageFamilyName[264]; // [rsp+30h] [rbp-228h] BYREF

  v9 = 0;
  packageFamilyNameLength = 260;
  v1 = PackageFamilyNameFromFullName(a1, &packageFamilyNameLength, packageFamilyName);
  if ( v1 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v3, v2, L"NcbPolicy: PackageFamilyNameFromFullName failed with error - ", v1);
  }
  else
  {
    v4 = AppContainerDeriveSidFromMoniker(packageFamilyName, &v9);
    if ( v4 >= 0 )
      return v9;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v6,
        v5,
        L"NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - ",
        (unsigned int)v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180012b20  sub     rsp, 258h
0x180012b27  mov     rax, cs:__security_cookie
0x180012b2e  xor     rax, rsp
0x180012b31  mov     [rsp+258h+var_18], rax
0x180012b39  lea     r8, [rsp+258h+packageFamilyName]; packageFamilyName
0x180012b3e  mov     [rsp+258h+var_230], 0
0x180012b47  lea     rdx, [rsp+258h+packageFamilyNameLength]; packageFamilyNameLength
0x180012b4c  mov     [rsp+258h+packageFamilyNameLength], 104h
0x180012b54  call    cs:__imp_PackageFamilyNameFromFullName
0x180012b5a  test    eax, eax
0x180012b5c  jnz     short loc_180012B8F
0x180012b5e  lea     rdx, [rsp+258h+var_230]
0x180012b63  lea     rcx, [rsp+258h+packageFamilyName]
0x180012b68  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180012b6e  test    eax, eax
0x180012b70  js      short loc_180012BBB
0x180012b72  mov     rax, [rsp+258h+var_230]
0x180012b77  mov     rcx, [rsp+258h+var_18]
0x180012b7f  xor     rcx, rsp; StackCookie
0x180012b82  call    __security_check_cookie
0x180012b87  add     rsp, 258h
0x180012b8e  retn
0x180012b8f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012b96  jnz     short loc_180012BB2
0x180012b98  xor     eax, eax
0x180012b9a  mov     rcx, [rsp+258h+var_18]
0x180012ba2  xor     rcx, rsp; StackCookie
0x180012ba5  call    __security_check_cookie
0x180012baa  add     rsp, 258h
0x180012bb1  retn
0x180012bb2  lea     r8, aNcbpolicyPacka; "NcbPolicy: PackageFamilyNameFromFullNam"...
0x180012bb9  jmp     short loc_180012BCB
0x180012bbb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012bc2  jz      short loc_180012B98
0x180012bc4  lea     r8, aNcbpolicyAppco; "NcbPolicy: AppContainerDeriveSidFromMon"...
0x180012bcb  mov     r9d, eax
0x180012bce  call    McTemplateU0zq_EventWriteTransfer
0x180012bd3  jmp     short loc_180012B98
```
