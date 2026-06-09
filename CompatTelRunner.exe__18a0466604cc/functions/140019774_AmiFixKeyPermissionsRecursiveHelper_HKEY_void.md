# AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)

- ea: `0x140019774`
- end: `0x140019921`
- name: `?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z`
- size: `429`
- prototype: `__int64 __fastcall(HKEY, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019610`
- `0x140019774`

## callees

- `0x140001ba0`
- `0x1400151b0`
- `0x140019774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001984e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001984e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400197b1`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400197b1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400198a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400198a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001982a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001982a`

## string_xrefs

- `0x1400197bd`: `RegSetKeySecurity failed [%d]`
- `0x1400198f9`: `RegOpenKeyEx failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiFixKeyPermissionsRecursiveHelper(HKEY a1, void *a2)
{
  LSTATUS v4; // eax
  unsigned int fixed; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  int v8; // r14d
  DWORD v9; // edx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = RegSetKeySecurity(a1, 5u, a2);
  fixed = v4;
  if ( v4 )
  {
    v6 = "RegSetKeySecurity failed [%d]";
    v7 = 937;
LABEL_3:
    LODWORD(phkResult) = v4;
    AslLogCallPrintf(1, "AmiFixKeyPermissionsRecursiveHelper", v7, v6, phkResult);
  }
  else
  {
    v8 = 0;
    v9 = 0;
    for ( hKey = 0; ; hKey = 0 )
    {
      cchName = 260;
      fixed = RegEnumKeyExW(a1, v9, SubKey, &cchName, 0, 0, 0, 0);
      if ( fixed == 259 )
        return 0;
      if ( fixed )
        break;
      v4 = RegOpenKeyExW(a1, SubKey, 0, 0xF003Fu, &hKey);
      fixed = v4;
      if ( v4 )
      {
        v6 = "RegOpenKeyEx failed [%d]";
        v7 = 977;
        goto LABEL_3;
      }
      fixed = AmiFixKeyPermissionsRecursiveHelper(hKey, a2);
      RegCloseKey(hKey);
      if ( fixed )
      {
        LODWORD(phkResult) = fixed;
        AslLogCallPrintf(
          1,
          "AmiFixKeyPermissionsRecursiveHelper",
          985,
          "AmiFixKeyPermissionsRecursiveHelper failed [%d]",
          phkResult);
        return fixed;
      }
      v9 = ++v8;
    }
    LODWORD(phkResulta) = fixed;
    AslLogCallPrintf(1, "AmiFixKeyPermissionsRecursiveHelper", 966, "RegEnumKeyEx failed [%d]", phkResulta);
  }
  return fixed;
}

```

## disassembly

```asm
0x140019774  mov     [rsp-8+arg_10], rbx
0x140019779  mov     [rsp-8+arg_18], rsi
0x14001977e  push    rbp
0x14001977f  push    r14
0x140019781  push    r15
0x140019783  lea     rbp, [rsp-170h]
0x14001978b  sub     rsp, 270h
0x140019792  mov     rax, cs:__security_cookie
0x140019799  xor     rax, rsp
0x14001979c  mov     [rbp+180h+var_20], rax
0x1400197a3  mov     r15, rdx
0x1400197a6  mov     r8, rdx; pSecurityDescriptor
0x1400197a9  mov     edx, 5; SecurityInformation
0x1400197ae  mov     rsi, rcx
0x1400197b1  call    cs:__imp_RegSetKeySecurity
0x1400197b7  mov     ebx, eax
0x1400197b9  test    eax, eax
0x1400197bb  jz      short loc_1400197E4
0x1400197bd  lea     r9, aRegsetkeysecur; "RegSetKeySecurity failed [%d]"
0x1400197c4  mov     r8d, 3A9h
0x1400197ca  mov     dword ptr [rsp+280h+phkResult], eax
0x1400197ce  lea     rdx, aAmifixkeypermi_1; "AmiFixKeyPermissionsRecursiveHelper"
0x1400197d5  mov     ecx, 1
0x1400197da  call    AslLogCallPrintf
0x1400197df  jmp     loc_1400198B9
0x1400197e4  xor     r14d, r14d
0x1400197e7  mov     [rsp+280h+lpftLastWriteTime], r14
0x1400197ec  xor     edx, edx
0x1400197ee  mov     [rsp+280h+lpcchClass], r14
0x1400197f3  mov     [rsp+280h+lpClass], r14
0x1400197f8  mov     [rsp+280h+phkResult], r14
0x1400197fd  mov     [rsp+280h+hKey], r14
0x140019802  jmp     loc_14001988F
0x140019807  test    ebx, ebx
0x140019809  jnz     loc_14001990B
0x14001980f  lea     rax, [rsp+280h+hKey]
0x140019814  mov     r9d, 0F003Fh; samDesired
0x14001981a  xor     r8d, r8d; ulOptions
0x14001981d  mov     [rsp+280h+phkResult], rax; phkResult
0x140019822  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x140019827  mov     rcx, rsi; hKey
0x14001982a  call    cs:__imp_RegOpenKeyExW
0x140019830  mov     ebx, eax
0x140019832  test    eax, eax
0x140019834  jnz     loc_1400198F9
0x14001983a  mov     rcx, [rsp+280h+hKey]; HKEY
0x14001983f  mov     rdx, r15; void *
0x140019842  call    ?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z; AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)
0x140019847  mov     rcx, [rsp+280h+hKey]; hKey
0x14001984c  mov     ebx, eax
0x14001984e  call    cs:__imp_RegCloseKey
0x140019854  test    ebx, ebx
0x140019856  jnz     loc_1400198E3
0x14001985c  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140019865  inc     r14d
0x140019868  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x140019871  mov     edx, r14d; dwIndex
0x140019874  mov     [rsp+280h+lpClass], 0; lpClass
0x14001987d  mov     [rsp+280h+phkResult], 0; lpReserved
0x140019886  mov     [rsp+280h+hKey], 0
0x14001988f  lea     r9, [rsp+280h+cchName]; lpcchName
0x140019894  mov     [rsp+280h+cchName], 104h
0x14001989c  lea     r8, [rsp+280h+SubKey]; lpName
0x1400198a1  mov     rcx, rsi; hKey
0x1400198a4  call    cs:__imp_RegEnumKeyExW
0x1400198aa  mov     ebx, eax
0x1400198ac  cmp     eax, 103h
0x1400198b1  jnz     loc_140019807
0x1400198b7  xor     ebx, ebx
0x1400198b9  mov     eax, ebx
0x1400198bb  mov     rcx, [rbp+180h+var_20]
0x1400198c2  xor     rcx, rsp; StackCookie
0x1400198c5  call    __security_check_cookie
0x1400198ca  lea     r11, [rsp+280h+var_10]
0x1400198d2  mov     rbx, [r11+30h]
0x1400198d6  mov     rsi, [r11+38h]
0x1400198da  mov     rsp, r11
0x1400198dd  pop     r15
0x1400198df  pop     r14
0x1400198e1  pop     rbp
0x1400198e2  retn
0x1400198e3  mov     dword ptr [rsp+280h+phkResult], ebx
0x1400198e7  lea     r9, aAmifixkeypermi_0; "AmiFixKeyPermissionsRecursiveHelper fai"...
0x1400198ee  mov     r8d, 3D9h
0x1400198f4  jmp     loc_1400197CE
0x1400198f9  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%d]"
0x140019900  mov     r8d, 3D1h
0x140019906  jmp     loc_1400197CA
0x14001990b  mov     dword ptr [rsp+280h+phkResult], ebx
0x14001990f  lea     r9, aRegenumkeyexFa; "RegEnumKeyEx failed [%d]"
0x140019916  mov     r8d, 3C6h
0x14001991c  jmp     loc_1400197CE
```
