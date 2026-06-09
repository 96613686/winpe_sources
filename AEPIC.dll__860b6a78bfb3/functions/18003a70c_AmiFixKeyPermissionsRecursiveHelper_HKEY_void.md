# AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)

- ea: `0x18003a70c`
- end: `0x18003a87a`
- name: `?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z`
- size: `366`
- prototype: `unsigned int __fastcall(HKEY, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a5a8`
- `0x18003a70c`

## callees

- `0x180005890`
- `0x1800295dc`
- `0x18003a70c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18003a73c`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18003a73c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a7e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a7e7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a7b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a7b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a807`

## string_xrefs

- `0x18003a748`: `RegSetKeySecurity failed [%d]`
- `0x18003a82e`: `RegOpenKeyEx failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiFixKeyPermissionsRecursiveHelper(HKEY a1, void *a2)
{
  LSTATUS v4; // eax
  unsigned int fixed; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  DWORD i; // esi
  LPDWORD lpReserved; // [rsp+20h] [rbp-268h]
  DWORD cchName; // [rsp+40h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  v4 = RegSetKeySecurity(a1, 5u, a2);
  fixed = v4;
  if ( v4 )
  {
    v6 = "RegSetKeySecurity failed [%d]";
    v7 = 937;
LABEL_3:
    LODWORD(lpReserved) = v4;
    AslLogCallPrintf(1, "AmiFixKeyPermissionsRecursiveHelper", v7, v6, lpReserved);
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      hKey = 0;
      v4 = RegEnumKeyExW(a1, i, Name, &cchName, 0, 0, 0, 0);
      fixed = v4;
      if ( v4 == 259 )
        break;
      if ( v4 )
      {
        v6 = "RegEnumKeyEx failed [%d]";
        v7 = 966;
        goto LABEL_3;
      }
      v4 = RegOpenKeyExW(a1, Name, 0, 0xF003Fu, &hKey);
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
        LODWORD(lpReserved) = fixed;
        AslLogCallPrintf(
          1,
          "AmiFixKeyPermissionsRecursiveHelper",
          985,
          "AmiFixKeyPermissionsRecursiveHelper failed [%d]",
          lpReserved);
        return fixed;
      }
    }
    return 0;
  }
  return fixed;
}

```

## disassembly

```asm
0x18003a70c  mov     [rsp+arg_10], rbx
0x18003a711  push    rbp
0x18003a712  push    rsi
0x18003a713  push    r14
0x18003a715  sub     rsp, 270h
0x18003a71c  mov     rax, cs:__security_cookie
0x18003a723  xor     rax, rsp
0x18003a726  mov     [rsp+288h+var_28], rax
0x18003a72e  mov     r14, rdx
0x18003a731  mov     r8, rdx; pSecurityDescriptor
0x18003a734  mov     edx, 5; SecurityInformation
0x18003a739  mov     rbp, rcx
0x18003a73c  call    cs:__imp_RegSetKeySecurity
0x18003a742  mov     ebx, eax
0x18003a744  test    eax, eax
0x18003a746  jz      short loc_18003A76F
0x18003a748  lea     r9, aRegsetkeysecur; "RegSetKeySecurity failed [%d]"
0x18003a74f  mov     r8d, 3A9h
0x18003a755  mov     dword ptr [rsp+288h+lpReserved], eax
0x18003a759  lea     rdx, aAmifixkeypermi_1; "AmiFixKeyPermissionsRecursiveHelper"
0x18003a760  mov     ecx, 1
0x18003a765  call    AslLogCallPrintf
0x18003a76a  jmp     loc_18003A854
0x18003a76f  xor     esi, esi
0x18003a771  mov     [rsp+288h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003a77a  lea     r9, [rsp+288h+cchName]; lpcchName
0x18003a77f  mov     [rsp+288h+lpcchClass], 0; lpcchClass
0x18003a788  lea     r8, [rsp+288h+Name]; lpName
0x18003a78d  mov     [rsp+288h+lpClass], 0; lpClass
0x18003a796  mov     edx, esi; dwIndex
0x18003a798  mov     rcx, rbp; hKey
0x18003a79b  mov     [rsp+288h+lpReserved], 0; lpReserved
0x18003a7a4  mov     [rsp+288h+cchName], 104h
0x18003a7ac  mov     [rsp+288h+hKey], 0
0x18003a7b5  call    cs:__imp_RegEnumKeyExW
0x18003a7bb  mov     ebx, eax
0x18003a7bd  cmp     eax, 103h
0x18003a7c2  jz      loc_18003A852
0x18003a7c8  test    eax, eax
0x18003a7ca  jnz     short loc_18003A840
0x18003a7cc  lea     rax, [rsp+288h+hKey]
0x18003a7d1  mov     r9d, 0F003Fh; samDesired
0x18003a7d7  xor     r8d, r8d; ulOptions
0x18003a7da  mov     [rsp+288h+lpReserved], rax; phkResult
0x18003a7df  lea     rdx, [rsp+288h+Name]; lpSubKey
0x18003a7e4  mov     rcx, rbp; hKey
0x18003a7e7  call    cs:__imp_RegOpenKeyExW
0x18003a7ed  mov     ebx, eax
0x18003a7ef  test    eax, eax
0x18003a7f1  jnz     short loc_18003A82E
0x18003a7f3  mov     rcx, [rsp+288h+hKey]; HKEY
0x18003a7f8  mov     rdx, r14; void *
0x18003a7fb  call    ?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z; AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)
0x18003a800  mov     rcx, [rsp+288h+hKey]; hKey
0x18003a805  mov     ebx, eax
0x18003a807  call    cs:__imp_RegCloseKey
0x18003a80d  test    ebx, ebx
0x18003a80f  jnz     short loc_18003A818
0x18003a811  inc     esi
0x18003a813  jmp     loc_18003A771
0x18003a818  mov     dword ptr [rsp+288h+lpReserved], ebx
0x18003a81c  lea     r9, aAmifixkeypermi_0; "AmiFixKeyPermissionsRecursiveHelper fai"...
0x18003a823  mov     r8d, 3D9h
0x18003a829  jmp     loc_18003A759
0x18003a82e  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed [%d]"
0x18003a835  mov     r8d, 3D1h
0x18003a83b  jmp     loc_18003A755
0x18003a840  lea     r9, aRegenumkeyexFa; "RegEnumKeyEx failed [%d]"
0x18003a847  mov     r8d, 3C6h
0x18003a84d  jmp     loc_18003A755
0x18003a852  xor     ebx, ebx
0x18003a854  mov     eax, ebx
0x18003a856  mov     rcx, [rsp+288h+var_28]
0x18003a85e  xor     rcx, rsp; StackCookie
0x18003a861  call    __security_check_cookie
0x18003a866  mov     rbx, [rsp+288h+arg_10]
0x18003a86e  add     rsp, 270h
0x18003a875  pop     r14
0x18003a877  pop     rsi
0x18003a878  pop     rbp
0x18003a879  retn
```
