# BuildMachineAccessDACL

- ea: `0x180005f60`
- end: `0x180006048`
- name: `BuildMachineAccessDACL`
- size: `232`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSubKey@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001396c`

## callees

- `0x180005f60`
- `0x1800127ec`
- `0x180012ca8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005feb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005feb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005fa2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005fa2`

## pseudocode

```c
__int64 __fastcall BuildMachineAccessDACL(LPCWSTR lpSubKey, int a2, int a3, int a4, HLOCAL *a5)
{
  unsigned int AccessRights; // ebx
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF

  hKey = 0;
  AccessRights = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( AccessRights )
  {
    if ( a2 && a4 != 1 )
      return 3;
    hKey = 0;
    AccessRights = 0;
    if ( a2 != 1 )
      return AccessRights;
    goto LABEL_10;
  }
  if ( hKey )
  {
    AccessRights = GetAccessRights(hKey);
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( a2 == 1 )
  {
LABEL_10:
    if ( a4 == 1 && !a3 )
      return BuildMachinePolicyACL(0, a5);
  }
  if ( !AccessRights )
    return 3;
  return AccessRights;
}

```

## disassembly

```asm
0x180005f60  push    rbx
0x180005f62  push    rbp
0x180005f63  push    rsi
0x180005f64  push    rdi
0x180005f65  push    r14
0x180005f67  push    r15
0x180005f69  sub     rsp, 48h
0x180005f6d  xor     r15d, r15d
0x180005f70  lea     rax, [rsp+78h+hKey]
0x180005f75  mov     esi, edx
0x180005f77  mov     [rsp+78h+hKey], r15
0x180005f7c  mov     rdx, rcx; lpSubKey
0x180005f7f  mov     [rsp+78h+var_48], r15d
0x180005f84  mov     ebp, r9d
0x180005f87  mov     [rsp+78h+phkResult], rax; phkResult
0x180005f8c  mov     r14d, r8d
0x180005f8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005f96  mov     r9d, 20019h; samDesired
0x180005f9c  xor     r8d, r8d; ulOptions
0x180005f9f  mov     edi, r15d
0x180005fa2  call    cs:__imp_RegOpenKeyExW
0x180005fa8  mov     ebx, eax
0x180005faa  test    eax, eax
0x180005fac  jz      short loc_180005FCD
0x180005fae  test    esi, esi
0x180005fb0  jz      short loc_180005FBE
0x180005fb2  cmp     ebp, 1
0x180005fb5  jz      short loc_180005FBE
0x180005fb7  mov     eax, 3
0x180005fbc  jmp     short loc_18000603B
0x180005fbe  mov     [rsp+78h+hKey], r15
0x180005fc3  mov     ebx, r15d
0x180005fc6  cmp     esi, 1
0x180005fc9  jnz     short loc_180006039
0x180005fcb  jmp     short loc_180006014
0x180005fcd  mov     rcx, [rsp+78h+hKey]; hKey
0x180005fd2  test    rcx, rcx
0x180005fd5  jz      short loc_18000600F
0x180005fd7  mov     r8d, r14d
0x180005fda  lea     rdx, [rsp+78h+var_48]
0x180005fdf  call    GetAccessRights
0x180005fe4  mov     rcx, [rsp+78h+hKey]; hKey
0x180005fe9  mov     ebx, eax
0x180005feb  call    cs:__imp_RegCloseKey
0x180005ff1  mov     edi, [rsp+78h+var_48]
0x180005ff5  mov     [rsp+78h+hKey], r15
0x180005ffa  test    ebx, ebx
0x180005ffc  jnz     short loc_18000600F
0x180005ffe  test    edi, edi
0x180006000  jz      short loc_18000600F
0x180006002  mov     rax, [rsp+78h+arg_28]
0x18000600a  mov     [rax], r15d
0x18000600d  jmp     short loc_18000601E
0x18000600f  cmp     esi, 1
0x180006012  jnz     short loc_18000602F
0x180006014  cmp     ebp, 1
0x180006017  jnz     short loc_18000602F
0x180006019  test    r14d, r14d
0x18000601c  jnz     short loc_18000602F
0x18000601e  mov     rdx, [rsp+78h+arg_20]
0x180006026  mov     ecx, edi
0x180006028  call    BuildMachinePolicyACL
0x18000602d  jmp     short loc_18000603B
0x18000602f  test    ebx, ebx
0x180006031  mov     eax, 3
0x180006036  cmovz   ebx, eax
0x180006039  mov     eax, ebx
0x18000603b  add     rsp, 48h
0x18000603f  pop     r15
0x180006041  pop     r14
0x180006043  pop     rdi
0x180006044  pop     rsi
0x180006045  pop     rbp
0x180006046  pop     rbx
0x180006047  retn
```
