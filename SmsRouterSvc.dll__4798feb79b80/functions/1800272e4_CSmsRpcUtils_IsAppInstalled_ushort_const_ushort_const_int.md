# CSmsRpcUtils::IsAppInstalled(ushort const *,ushort const *,int)

- ea: `0x1800272e4`
- end: `0x180027360`
- name: `?IsAppInstalled@CSmsRpcUtils@@SAHPEBG0H@Z`
- size: `124`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, LPCWSTR StringSid, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000fd94`
- `0x18003c580`

## callees

- `0x1800272e4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027310`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027310`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002734d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002734d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18002732a`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x18002732a`

## pseudocode

```c
__int64 __fastcall CSmsRpcUtils::IsAppInstalled(PCWSTR packageFullName, LPCWSTR StringSid, unsigned int a3)
{
  LONG v5; // eax
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+20h] [rbp-18h] BYREF
  PSID userSid; // [rsp+58h] [rbp+20h] BYREF

  packageInfoReference = 0;
  userSid = 0;
  if ( ConvertStringSidToSidW(StringSid, &userSid) )
  {
    v5 = OpenPackageInfoByFullNameForUser(userSid, packageFullName, 0, &packageInfoReference);
    if ( v5 )
    {
      if ( v5 == 1168 )
        a3 = 0;
    }
    else
    {
      a3 = 1;
    }
    if ( packageInfoReference )
      ClosePackageInfo(packageInfoReference);
  }
  return a3;
}

```

## disassembly

```asm
0x1800272e4  mov     r11, rsp
0x1800272e7  mov     [r11+8], rbx
0x1800272eb  push    rdi
0x1800272ec  sub     rsp, 30h
0x1800272f0  mov     rax, rdx
0x1800272f3  mov     qword ptr [r11-18h], 0
0x1800272fb  mov     rdi, rcx
0x1800272fe  mov     qword ptr [r11+20h], 0
0x180027306  mov     rcx, rax; StringSid
0x180027309  lea     rdx, [r11+20h]; Sid
0x18002730d  mov     ebx, r8d
0x180027310  call    cs:__imp_ConvertStringSidToSidW
0x180027316  test    eax, eax
0x180027318  jz      short loc_180027353
0x18002731a  mov     rcx, [rsp+38h+userSid]; userSid
0x18002731f  lea     r9, [rsp+38h+packageInfoReference]; packageInfoReference
0x180027324  xor     r8d, r8d; reserved
0x180027327  mov     rdx, rdi; packageFullName
0x18002732a  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x180027330  test    eax, eax
0x180027332  jnz     short loc_180027339
0x180027334  lea     ebx, [rax+1]
0x180027337  jmp     short loc_180027343
0x180027339  xor     ecx, ecx
0x18002733b  cmp     eax, 490h
0x180027340  cmovz   ebx, ecx
0x180027343  mov     rcx, [rsp+38h+packageInfoReference]; packageInfoReference
0x180027348  test    rcx, rcx
0x18002734b  jz      short loc_180027353
0x18002734d  call    cs:__imp_ClosePackageInfo
0x180027353  mov     eax, ebx
0x180027355  mov     rbx, [rsp+38h+arg_0]
0x18002735a  add     rsp, 30h
0x18002735e  pop     rdi
0x18002735f  retn
```
