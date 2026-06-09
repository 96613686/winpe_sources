# WinReGetGroupPolicies

- ea: `0x1800227ac`
- end: `0x1800228fd`
- name: `WinReGetGroupPolicies`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180026670`

## callees

- `0x1800059fc`
- `0x1800227ac`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180022867`
- `ADVAPI32!RegQueryValueExW` at `0x180022867`
- `ADVAPI32!RegOpenKeyExW` at `0x180022812`
- `ADVAPI32!RegOpenKeyExW` at `0x180022812`
- `ADVAPI32!RegCloseKey` at `0x1800228a2`
- `ADVAPI32!RegCloseKey` at `0x1800228a2`

## string_xrefs

- `0x180022821`: `RegOpenKeyEx(GP) failed: 0x%x`
- `0x1800228cb`: `NOTE: overwrite error code 0x%x because it is not critical`

## pseudocode

```c
__int64 __fastcall WinReGetGroupPolicies(_DWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-10h] BYREF

  *a1 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRE", 0, 1u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    UnattendLogW(2, L"RegOpenKeyEx(GP) failed: 0x%x", v2);
    hKey = 0;
LABEL_11:
    UnattendLogW(2, L"WinReGetGroupPolicies failed with error code 0x%x", v3);
    UnattendLogW(2, L"NOTE: overwrite error code 0x%x because it is not critical", v3);
    return 1;
  }
  cbData = 4;
  v3 = RegQueryValueExW(hKey, L"DisableSetup", 0, &Type, Data, &cbData);
  if ( !v3 && Type == 4 && cbData == 4 && *(_DWORD *)Data == 1 )
  {
    UnattendLogW(0, L"Group policy is enabled!");
    *a1 = 1;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
    goto LABEL_11;
  return 1;
}

```

## disassembly

```asm
0x1800227ac  mov     [rsp-8+arg_8], rbx
0x1800227b1  mov     [rsp-8+arg_10], rdi
0x1800227b6  push    rbp
0x1800227b7  mov     rbp, rsp
0x1800227ba  sub     rsp, 50h
0x1800227be  mov     rax, cs:__security_cookie
0x1800227c5  xor     rax, rsp
0x1800227c8  mov     [rbp+var_8], rax
0x1800227cc  mov     rdi, rcx
0x1800227cf  mov     dword ptr [rcx], 0
0x1800227d5  lea     rax, [rbp+hKey]
0x1800227d9  mov     [rbp+hKey], 0
0x1800227e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800227e8  mov     [rsp+50h+phkResult], rax; phkResult
0x1800227ed  mov     r9d, 1; samDesired
0x1800227f3  mov     [rbp+Type], 0
0x1800227fa  xor     r8d, r8d; ulOptions
0x1800227fd  mov     dword ptr [rbp+Data], 0
0x180022804  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002280b  mov     [rbp+cbData], 0
0x180022812  call    cs:__imp_RegOpenKeyExW
0x180022818  mov     ebx, eax
0x18002281a  test    eax, eax
0x18002281c  jz      short loc_18002283C
0x18002281e  mov     r8d, eax
0x180022821  lea     rdx, aRegopenkeyexGp; "RegOpenKeyEx(GP) failed: 0x%x"
0x180022828  mov     ecx, 2
0x18002282d  call    UnattendLogW
0x180022832  mov     [rbp+hKey], 0
0x18002283a  jmp     short loc_1800228B4
0x18002283c  mov     rcx, [rbp+hKey]; hKey
0x180022840  lea     rax, [rbp+cbData]
0x180022844  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180022849  lea     r9, [rbp+Type]; lpType
0x18002284d  lea     rax, [rbp+Data]
0x180022851  mov     [rbp+cbData], 4
0x180022858  xor     r8d, r8d; lpReserved
0x18002285b  mov     [rsp+50h+phkResult], rax; lpData
0x180022860  lea     rdx, aDisablesetup; "DisableSetup"
0x180022867  call    cs:__imp_RegQueryValueExW
0x18002286d  mov     ebx, eax
0x18002286f  test    eax, eax
0x180022871  jnz     short loc_180022899
0x180022873  cmp     [rbp+Type], 4
0x180022877  jnz     short loc_180022899
0x180022879  cmp     [rbp+cbData], 4
0x18002287d  jnz     short loc_180022899
0x18002287f  cmp     dword ptr [rbp+Data], 1
0x180022883  jnz     short loc_180022899
0x180022885  lea     rdx, aGroupPolicyIsE; "Group policy is enabled!"
0x18002288c  xor     ecx, ecx
0x18002288e  call    UnattendLogW
0x180022893  mov     dword ptr [rdi], 1
0x180022899  mov     rcx, [rbp+hKey]; hKey
0x18002289d  test    rcx, rcx
0x1800228a0  jz      short loc_1800228B0
0x1800228a2  call    cs:__imp_RegCloseKey
0x1800228a8  mov     [rbp+hKey], 0
0x1800228b0  test    ebx, ebx
0x1800228b2  jz      short loc_1800228DC
0x1800228b4  mov     r8d, ebx
0x1800228b7  lea     rdx, aWinregetgroupp; "WinReGetGroupPolicies failed with error"...
0x1800228be  mov     ecx, 2
0x1800228c3  call    UnattendLogW
0x1800228c8  mov     r8d, ebx
0x1800228cb  lea     rdx, aNoteOverwriteE; "NOTE: overwrite error code 0x%x because"...
0x1800228d2  mov     ecx, 2
0x1800228d7  call    UnattendLogW
0x1800228dc  mov     eax, 1
0x1800228e1  mov     rcx, [rbp+var_8]
0x1800228e5  xor     rcx, rsp; StackCookie
0x1800228e8  call    __security_check_cookie
0x1800228ed  mov     rbx, [rsp+50h+arg_8]
0x1800228f2  mov     rdi, [rsp+50h+arg_10]
0x1800228f7  add     rsp, 50h
0x1800228fb  pop     rbp
0x1800228fc  retn
```
