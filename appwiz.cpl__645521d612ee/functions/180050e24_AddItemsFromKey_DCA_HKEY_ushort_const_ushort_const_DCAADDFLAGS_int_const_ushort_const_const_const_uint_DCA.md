# _AddItemsFromKey(_DCA *,HKEY__ *,ushort const *,ushort const *,DCAADDFLAGS,int * const,ushort const * const * const,uint,_DCA *)

- ea: `0x180050e24`
- end: `0x180050ff2`
- name: `?_AddItemsFromKey@@YAXPEAU_DCA@@PEAUHKEY__@@PEBG2W4DCAADDFLAGS@@QEAHQEBQEBGI0@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008708`

## callees

- `0x180050d60`
- `0x180050e24`
- `0x180055870`
- `0x180058296`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x180050ef6`
- `SHCORE!SHGetValueW` at `0x180050ef6`
- `SHCORE!__imp_GUIDFromStringW` at `0x180050f35`
- `SHCORE!__imp_GUIDFromStringW` at `0x180050f6c`
- `SHCORE!__imp_GUIDFromStringW` at `0x180050f35`
- `SHCORE!__imp_GUIDFromStringW` at `0x180050f6c`
- `SHELL32!__imp_SHRestricted` at `0x180050f04`
- `SHELL32!__imp_SHRestricted` at `0x180050f04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050eb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fd4`
- `ADVAPI32!RegEnumKeyW` at `0x180050fc1`
- `ADVAPI32!RegEnumKeyW` at `0x180050fc1`
- `ADVAPI32!RegQueryValueW` at `0x180050f58`
- `ADVAPI32!RegQueryValueW` at `0x180050f58`

## string_xrefs

- `0x180050f17`: `CoCreateCLSIDOOP`

## pseudocode

```c
LSTATUS __fastcall _AddItemsFromKey(struct _DSA *a1)
{
  LSTATUS result; // eax
  int v3; // esi
  int v4; // ebx
  DWORD v5; // edx
  int v6; // eax
  int v7; // edx
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  RESTRICTIONS pvData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID Buf1; // [rsp+48h] [rbp-B8h] BYREF
  GUID Buf2; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[64]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\App Management\\Publishers",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    v3 = *(_DWORD *)a1;
    v4 = 0;
    v5 = 0;
    Buf2 = GUID_NULL;
    while ( !RegEnumKeyW(hKey, v5, SubKey, 0x40u) )
    {
      hkey = 0;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hkey) )
      {
        pvData = REST_NONE;
        pcbData = 4;
        if ( SHGetValueW(hkey, 0, L"SuppressionPolicy", 0, &pvData, &pcbData) || !SHRestricted(pvData) )
        {
          Buf1 = 0;
          SHRegSubKeyExistsW(hkey, L"CoCreateCLSIDOOP");
          if ( (unsigned int)GUIDFromStringW(SubKey, &Buf1)
            || (pcbData = 128, !RegQueryValueW(hkey, 0, SubKey, (PLONG)&pcbData))
            && (unsigned int)GUIDFromStringW(SubKey, &Buf1) )
          {
            v6 = memcmp_0(&Buf1, &Buf2, 0x10u);
            v7 = 0x7FFFFFFF;
            if ( !v6 )
              v7 = v3;
            DCA_InsertItem(a1, v7, &Buf1);
          }
        }
        RegCloseKey(hkey);
      }
      v5 = ++v4;
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180050e24  push    rbp
0x180050e26  push    rbx
0x180050e27  push    rsi
0x180050e28  push    rdi
0x180050e29  lea     rbp, [rsp-8]
0x180050e2e  sub     rsp, 108h
0x180050e35  mov     rax, cs:__security_cookie
0x180050e3c  xor     rax, rsp
0x180050e3f  mov     [rbp+20h+var_30], rax
0x180050e43  mov     rdi, rcx
0x180050e46  mov     [rsp+120h+hKey], 0
0x180050e4f  lea     rax, [rsp+120h+hKey]
0x180050e54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050e5b  mov     r9d, 20019h; samDesired
0x180050e61  mov     [rsp+120h+phkResult], rax; phkResult
0x180050e66  xor     r8d, r8d; ulOptions
0x180050e69  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180050e70  call    cs:__imp_RegOpenKeyExW
0x180050e76  test    eax, eax
0x180050e78  jnz     loc_180050FDA
0x180050e7e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180050e85  mov     esi, [rdi]
0x180050e87  xor     ebx, ebx
0x180050e89  xor     edx, edx
0x180050e8b  movdqu  xmmword ptr [rsp+120h+Buf2.Data1], xmm0
0x180050e91  jmp     loc_180050FB1
0x180050e96  lea     rax, [rsp+120h+hkey]
0x180050e9b  mov     [rsp+120h+hkey], 0
0x180050ea4  mov     r9d, 20019h; samDesired
0x180050eaa  mov     [rsp+120h+phkResult], rax; phkResult
0x180050eaf  xor     r8d, r8d; ulOptions
0x180050eb2  lea     rdx, [rsp+120h+SubKey]; lpSubKey
0x180050eb7  call    cs:__imp_RegOpenKeyExW
0x180050ebd  test    eax, eax
0x180050ebf  jnz     loc_180050FAD
0x180050ec5  mov     rcx, [rsp+120h+hkey]; hkey
0x180050eca  lea     r8, aSuppressionpol; "SuppressionPolicy"
0x180050ed1  mov     [rsp+120h+pvData], eax
0x180050ed5  xor     r9d, r9d; pdwType
0x180050ed8  lea     rax, [rsp+120h+var_F0]
0x180050edd  mov     [rsp+120h+var_F0], 4
0x180050ee5  mov     [rsp+120h+pcbData], rax; pcbData
0x180050eea  xor     edx, edx; pszSubKey
0x180050eec  lea     rax, [rsp+120h+pvData]
0x180050ef1  mov     [rsp+120h+phkResult], rax; pvData
0x180050ef6  call    cs:__imp_SHGetValueW
0x180050efc  test    eax, eax
0x180050efe  jnz     short loc_180050F12
0x180050f00  mov     ecx, [rsp+120h+pvData]; rest
0x180050f04  call    cs:__imp_SHRestricted
0x180050f0a  test    eax, eax
0x180050f0c  jnz     loc_180050FA2
0x180050f12  mov     rcx, [rsp+120h+hkey]
0x180050f17  lea     rdx, aCocreateclsido; "CoCreateCLSIDOOP"
0x180050f1e  xorps   xmm0, xmm0
0x180050f21  movups  [rsp+120h+Buf1], xmm0
0x180050f26  call    SHRegSubKeyExistsW
0x180050f2b  lea     rdx, [rsp+120h+Buf1]
0x180050f30  lea     rcx, [rsp+120h+SubKey]
0x180050f35  call    cs:__imp_GUIDFromStringW
0x180050f3b  test    eax, eax
0x180050f3d  jnz     short loc_180050F76
0x180050f3f  mov     rcx, [rsp+120h+hkey]; hKey
0x180050f44  lea     r9, [rsp+120h+var_F0]; lpcbData
0x180050f49  lea     r8, [rsp+120h+SubKey]; lpData
0x180050f4e  mov     [rsp+120h+var_F0], 80h
0x180050f56  xor     edx, edx; lpSubKey
0x180050f58  call    cs:__imp_RegQueryValueW
0x180050f5e  test    eax, eax
0x180050f60  jnz     short loc_180050FA2
0x180050f62  lea     rdx, [rsp+120h+Buf1]
0x180050f67  lea     rcx, [rsp+120h+SubKey]
0x180050f6c  call    cs:__imp_GUIDFromStringW
0x180050f72  test    eax, eax
0x180050f74  jz      short loc_180050FA2
0x180050f76  mov     r8d, 10h; Size
0x180050f7c  lea     rdx, [rsp+120h+Buf2]; Buf2
0x180050f81  lea     rcx, [rsp+120h+Buf1]; Buf1
0x180050f86  call    memcmp_0
0x180050f8b  test    eax, eax
0x180050f8d  lea     r8, [rsp+120h+Buf1]; pitem
0x180050f92  mov     edx, 7FFFFFFFh
0x180050f97  mov     rcx, rdi; hdsa
0x180050f9a  cmovz   edx, esi; i
0x180050f9d  call    ?DCA_InsertItem@@YAHPEAU_DCA@@HAEBU_GUID@@@Z; DCA_InsertItem(_DCA *,int,_GUID const &)
0x180050fa2  mov     rcx, [rsp+120h+hkey]; hKey
0x180050fa7  call    cs:__imp_RegCloseKey
0x180050fad  inc     ebx
0x180050faf  mov     edx, ebx; dwIndex
0x180050fb1  mov     rcx, [rsp+120h+hKey]; hKey
0x180050fb6  lea     r8, [rsp+120h+SubKey]; lpName
0x180050fbb  mov     r9d, 40h ; '@'; cchName
0x180050fc1  call    cs:__imp_RegEnumKeyW
0x180050fc7  mov     rcx, [rsp+120h+hKey]; hKey
0x180050fcc  test    eax, eax
0x180050fce  jz      loc_180050E96
0x180050fd4  call    cs:__imp_RegCloseKey
0x180050fda  mov     rcx, [rbp+20h+var_30]
0x180050fde  xor     rcx, rsp; StackCookie
0x180050fe1  call    __security_check_cookie
0x180050fe6  add     rsp, 108h
0x180050fed  pop     rdi
0x180050fee  pop     rsi
0x180050fef  pop     rbx
0x180050ff0  pop     rbp
0x180050ff1  retn
```
