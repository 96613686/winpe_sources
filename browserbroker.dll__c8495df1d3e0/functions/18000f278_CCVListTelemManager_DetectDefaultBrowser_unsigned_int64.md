# CCVListTelemManager::DetectDefaultBrowser(unsigned __int64 *)

- ea: `0x18000f278`
- end: `0x18000f45d`
- name: `?DetectDefaultBrowser@CCVListTelemManager@@CAJPEA_K@Z`
- size: `485`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f1a4`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000f278`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000f357`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000f418`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000f357`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000f418`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f330`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f3f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f330`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f3f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f33d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f33d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f400`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f396`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f396`

## pseudocode

```c
__int64 __fastcall CCVListTelemManager::DetectDefaultBrowser(unsigned __int64 *a1)
{
  LSTATUS ValueW; // ebx
  bool v3; // cc
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pvData[512]; // [rsp+270h] [rbp+170h] BYREF

  *a1 = 0;
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\Shell\\Associations\\UrlAssociations\\http\\UserChoice",
             0,
             0x20019u,
             &hkey);
  if ( !ValueW )
  {
    memset_0(Str, 0, 0x208u);
    pcbData = 260;
    ValueW = RegGetValueW(hkey, 0, L"ProgId", 2u, 0, Str, &pcbData);
    RegCloseKey(hkey);
    v3 = ValueW <= 0;
    if ( ValueW )
      goto LABEL_10;
    if ( wcsstr(Str, L"IE.HTTP") )
    {
      *a1 = 256;
      return (unsigned int)ValueW;
    }
    hKey = 0;
    ValueW = RegOpenKeyExW(HKEY_CLASSES_ROOT, Str, 0, 0x20019u, &hKey);
    if ( !ValueW )
    {
      memset_0(pvData, 0, sizeof(pvData));
      pcbData = 512;
      ValueW = RegGetValueW(hKey, 0, L"FriendlyTypeName", 2u, 0, pvData, &pcbData);
      RegCloseKey(hKey);
      v3 = ValueW <= 0;
      if ( ValueW )
        goto LABEL_10;
      if ( !wcsstr(pvData, L"MicrosoftEdge") )
        return (unsigned int)ValueW;
      *a1 = 512;
    }
  }
  v3 = ValueW <= 0;
LABEL_10:
  if ( !v3 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18000f278  mov     [rsp-8+arg_8], rbx
0x18000f27d  mov     [rsp-8+arg_10], rdi
0x18000f282  push    rbp
0x18000f283  lea     rbp, [rsp-580h]
0x18000f28b  sub     rsp, 680h
0x18000f292  mov     rax, cs:__security_cookie
0x18000f299  xor     rax, rsp
0x18000f29c  mov     [rbp+580h+var_10], rax
0x18000f2a3  mov     rdi, rcx
0x18000f2a6  mov     qword ptr [rcx], 0
0x18000f2ad  lea     rax, [rsp+680h+hkey]
0x18000f2b2  mov     [rsp+680h+hkey], 0
0x18000f2bb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f2c2  mov     [rsp+680h+phkResult], rax; phkResult
0x18000f2c7  mov     r9d, 20019h; samDesired
0x18000f2cd  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\Shell\\As"...
0x18000f2d4  xor     r8d, r8d; ulOptions
0x18000f2d7  call    cs:__imp_RegOpenKeyExW
0x18000f2dd  mov     ebx, eax
0x18000f2df  test    eax, eax
0x18000f2e1  jnz     loc_18000F42A
0x18000f2e7  xor     edx, edx; Val
0x18000f2e9  lea     rcx, [rsp+680h+Str]; void *
0x18000f2ee  mov     r8d, 208h; Size
0x18000f2f4  call    memset_0
0x18000f2f9  mov     rcx, [rsp+680h+hkey]; hkey
0x18000f2fe  lea     rax, [rsp+680h+var_640]
0x18000f303  mov     [rsp+680h+pcbData], rax; pcbData
0x18000f308  lea     r9d, [rbx+2]; dwFlags
0x18000f30c  lea     rax, [rsp+680h+Str]
0x18000f311  mov     [rsp+680h+var_640], 104h
0x18000f319  mov     [rsp+680h+pvData], rax; pvData
0x18000f31e  lea     r8, Value; "ProgId"
0x18000f325  xor     edx, edx; lpSubKey
0x18000f327  mov     [rsp+680h+phkResult], 0; pdwType
0x18000f330  call    cs:__imp_RegGetValueW
0x18000f336  mov     rcx, [rsp+680h+hkey]; hKey
0x18000f33b  mov     ebx, eax
0x18000f33d  call    cs:__imp_RegCloseKey
0x18000f343  test    ebx, ebx
0x18000f345  jnz     loc_18000F42C
0x18000f34b  lea     rdx, aIeHttp; "IE.HTTP"
0x18000f352  lea     rcx, [rsp+680h+Str]; Str
0x18000f357  call    cs:__imp_wcsstr
0x18000f35d  test    rax, rax
0x18000f360  jz      short loc_18000F36E
0x18000f362  mov     qword ptr [rdi], 100h
0x18000f369  jmp     loc_18000F437
0x18000f36e  lea     rax, [rsp+680h+hKey]
0x18000f373  mov     [rsp+680h+hKey], 0
0x18000f37c  mov     r9d, 20019h; samDesired
0x18000f382  mov     [rsp+680h+phkResult], rax; phkResult
0x18000f387  xor     r8d, r8d; ulOptions
0x18000f38a  lea     rdx, [rsp+680h+Str]; lpSubKey
0x18000f38f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000f396  call    cs:__imp_RegOpenKeyExW
0x18000f39c  mov     ebx, eax
0x18000f39e  test    eax, eax
0x18000f3a0  jnz     loc_18000F42A
0x18000f3a6  xor     edx, edx; Val
0x18000f3a8  lea     rcx, [rbp+580h+var_410]; void *
0x18000f3af  mov     r8d, 400h; Size
0x18000f3b5  call    memset_0
0x18000f3ba  mov     rcx, [rsp+680h+hKey]; hkey
0x18000f3bf  lea     rax, [rsp+680h+var_640]
0x18000f3c4  mov     [rsp+680h+pcbData], rax; pcbData
0x18000f3c9  lea     r9d, [rbx+2]; dwFlags
0x18000f3cd  lea     rax, [rbp+580h+var_410]
0x18000f3d4  mov     [rsp+680h+var_640], 200h
0x18000f3dc  mov     [rsp+680h+pvData], rax; pvData
0x18000f3e1  lea     r8, aFriendlytypena; "FriendlyTypeName"
0x18000f3e8  xor     edx, edx; lpSubKey
0x18000f3ea  mov     [rsp+680h+phkResult], 0; pdwType
0x18000f3f3  call    cs:__imp_RegGetValueW
0x18000f3f9  mov     rcx, [rsp+680h+hKey]; hKey
0x18000f3fe  mov     ebx, eax
0x18000f400  call    cs:__imp_RegCloseKey
0x18000f406  test    ebx, ebx
0x18000f408  jnz     short loc_18000F42C
0x18000f40a  lea     rdx, aMicrosoftedge_0; "MicrosoftEdge"
0x18000f411  lea     rcx, [rbp+580h+var_410]; Str
0x18000f418  call    cs:__imp_wcsstr
0x18000f41e  test    rax, rax
0x18000f421  jz      short loc_18000F437
0x18000f423  mov     qword ptr [rdi], 200h
0x18000f42a  test    ebx, ebx
0x18000f42c  jle     short loc_18000F437
0x18000f42e  movzx   ebx, bx
0x18000f431  or      ebx, 80070000h
0x18000f437  mov     eax, ebx
0x18000f439  mov     rcx, [rbp+580h+var_10]
0x18000f440  xor     rcx, rsp; StackCookie
0x18000f443  call    __security_check_cookie
0x18000f448  lea     r11, [rsp+680h+var_s0]
0x18000f450  mov     rbx, [r11+18h]
0x18000f454  mov     rdi, [r11+20h]
0x18000f458  mov     rsp, r11
0x18000f45b  pop     rbp
0x18000f45c  retn
```
