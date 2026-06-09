# DllRegisterServer

- ea: `0x18000e190`
- end: `0x18000e478`
- name: `DllRegisterServer`
- size: `744`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800010c0`
- `0x180001520`
- `0x180001550`
- `0x180001f78`
- `0x18000b300`
- `0x18000e190`
- `0x18000ea74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18000e282`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18000e282`
- `MFPlat!MFTRegister` at `0x18000e431`
- `MFPlat!MFTRegister` at `0x18000e431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e335`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e335`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e2f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e324`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e2f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e324`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2b5`
- `msdmo!DMORegister` at `0x18000e3ad`
- `msdmo!DMORegister` at `0x18000e3ad`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rcx
  const DMO_PARTIAL_MEDIATYPE *v2; // rdi
  __int64 v3; // rcx
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  const DMO_PARTIAL_MEDIATYPE *v5; // rbx
  int v6; // esi
  int v7; // eax
  HRESULT v8; // ecx
  const DMO_PARTIAL_MEDIATYPE *v9; // rcx
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  GUID guidCategory; // [rsp+80h] [rbp-80h] BYREF
  CLSID clsidMFT; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v15[72]; // [rsp+A8h] [rbp-58h] BYREF

  result = sub_18000EA74((__int64)&clsidDMO);
  if ( result < 0 )
    return result;
  *(_QWORD *)SubKey = 0x7B5C4449534C43LL;
  memset(v15, 0, sizeof(v15));
  sub_180001550(
    (char *)&SubKey[3] + 1,
    73,
    "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    2075112369,
    55540,
    17017,
    146,
    83,
    39,
    218,
    66,
    49,
    8,
    222);
  o_strcat_s(SubKey, 80, "}");
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
  {
    *(_DWORD *)Data = 8388609;
    RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
    *(_DWORD *)Data = 256;
    RegSetValueExW(hKey, L"WMSDKMerit", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  v2 = (const DMO_PARTIAL_MEDIATYPE *)sub_18000B300(v1, 2, off_180042010);
  pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)sub_18000B300(v3, 6, off_180042020);
  v5 = pOutTypes;
  if ( !v2 )
  {
    if ( !pOutTypes )
      return -2147024882;
    v9 = pOutTypes;
LABEL_14:
    j_j__o_free(v9);
    return -2147024882;
  }
  if ( !pOutTypes )
  {
    v9 = v2;
    goto LABEL_14;
  }
  v6 = DMORegister(L"WMV Screen decoder DMO", &clsidDMO, &::guidCategory, 0, 2u, v2, 6u, pOutTypes);
  j_j__o_free(v2);
  j_j__o_free(v5);
  if ( v6 < 0 )
    return v6;
  guidCategory = (GUID)xmmword_18003E1A0;
  clsidMFT = clsidDMO;
  v7 = MFTRegister(
         &clsidMFT,
         &guidCategory,
         (LPWSTR)L"WMV Screen decoder DMO",
         0,
         2u,
         &pInputTypes,
         6u,
         &pOutputTypes,
         0);
  v8 = 0;
  if ( v7 < 0 )
    return v7;
  return v8;
}

```

## disassembly

```asm
0x18000e190  push    rbp
0x18000e192  push    rbx
0x18000e193  push    rsi
0x18000e194  push    rdi
0x18000e195  lea     rbp, [rsp-8]
0x18000e19a  sub     rsp, 108h
0x18000e1a1  mov     rax, cs:__security_cookie
0x18000e1a8  xor     rax, rsp
0x18000e1ab  mov     [rbp+20h+var_30], rax
0x18000e1af  lea     rcx, clsidDMO
0x18000e1b6  call    sub_18000EA74
0x18000e1bb  test    eax, eax
0x18000e1bd  js      loc_18000E45F
0x18000e1c3  xor     edx, edx; Val
0x18000e1c5  lea     rcx, [rbp+20h+var_78]; void *
0x18000e1c9  mov     rax, 7B5C4449534C43h
0x18000e1d3  mov     qword ptr [rbp+20h+SubKey], rax
0x18000e1d7  lea     r8d, [rdx+48h]; Size
0x18000e1db  call    memset
0x18000e1e0  movzx   r9d, cs:clsidDMO.Data4+2
0x18000e1e8  movzx   r8d, cs:clsidDMO.Data4+1
0x18000e1f0  movzx   edx, cs:clsidDMO.Data4
0x18000e1f7  movzx   ecx, cs:clsidDMO.Data3
0x18000e1fe  movzx   esi, cs:clsidDMO.Data4+7
0x18000e205  movzx   edi, cs:clsidDMO.Data4+6
0x18000e20c  movzx   ebx, cs:clsidDMO.Data4+5
0x18000e213  movzx   r11d, cs:clsidDMO.Data4+4
0x18000e21b  movzx   r10d, cs:clsidDMO.Data4+3
0x18000e223  movzx   eax, cs:clsidDMO.Data2
0x18000e22a  mov     [rsp+120h+var_B8], esi
0x18000e22e  mov     [rsp+120h+var_C0], edi
0x18000e232  mov     [rsp+120h+var_C8], ebx
0x18000e236  mov     [rsp+120h+var_D0], r11d
0x18000e23b  mov     [rsp+120h+var_D8], r10d
0x18000e240  mov     dword ptr [rsp+120h+pAttributes], r9d
0x18000e245  mov     r9d, cs:clsidDMO.Data1
0x18000e24c  mov     dword ptr [rsp+120h+pOutTypes], r8d
0x18000e251  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x18000e258  mov     [rsp+120h+cOutTypes], edx
0x18000e25c  mov     edx, 49h ; 'I'
0x18000e261  mov     [rsp+120h+cbData], ecx
0x18000e265  lea     rcx, [rbp+20h+SubKey+7]
0x18000e269  mov     dword ptr [rsp+120h+phkResult], eax
0x18000e26d  call    sub_180001550
0x18000e272  lea     r8, asc_18003DD8C; "}"
0x18000e279  mov     edx, 50h ; 'P'
0x18000e27e  lea     rcx, [rbp+20h+SubKey]
0x18000e282  call    cs:_o_strcat_s
0x18000e289  nop     dword ptr [rax+rax+00h]
0x18000e28e  lea     rax, [rsp+120h+hKey]
0x18000e293  mov     [rsp+120h+hKey], 0
0x18000e29c  mov     r9d, 2; samDesired
0x18000e2a2  mov     [rsp+120h+phkResult], rax; phkResult
0x18000e2a7  xor     r8d, r8d; ulOptions
0x18000e2aa  lea     rdx, [rbp+20h+SubKey]; lpSubKey
0x18000e2ae  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e2b5  call    cs:RegOpenKeyExW
0x18000e2bc  nop     dword ptr [rax+rax+00h]
0x18000e2c1  test    eax, eax
0x18000e2c3  jnz     short loc_18000E341
0x18000e2c5  mov     rcx, [rsp+120h+hKey]; hKey
0x18000e2ca  lea     ebx, [rax+4]
0x18000e2cd  lea     rax, [rsp+120h+Data]
0x18000e2d2  mov     [rsp+120h+cbData], ebx; cbData
0x18000e2d6  mov     r9d, ebx; dwType
0x18000e2d9  mov     [rsp+120h+phkResult], rax; lpData
0x18000e2de  xor     r8d, r8d; Reserved
0x18000e2e1  mov     dword ptr [rsp+120h+Data], 800001h
0x18000e2e9  lea     rdx, ValueName; "Merit"
0x18000e2f0  call    cs:RegSetValueExW
0x18000e2f7  nop     dword ptr [rax+rax+00h]
0x18000e2fc  mov     rcx, [rsp+120h+hKey]; hKey
0x18000e301  lea     rax, [rsp+120h+Data]
0x18000e306  mov     [rsp+120h+cbData], ebx; cbData
0x18000e30a  lea     rdx, aWmsdkmerit; "WMSDKMerit"
0x18000e311  mov     r9d, ebx; dwType
0x18000e314  mov     [rsp+120h+phkResult], rax; lpData
0x18000e319  xor     r8d, r8d; Reserved
0x18000e31c  mov     dword ptr [rsp+120h+Data], 100h
0x18000e324  call    cs:RegSetValueExW
0x18000e32b  nop     dword ptr [rax+rax+00h]
0x18000e330  mov     rcx, [rsp+120h+hKey]; hKey
0x18000e335  call    cs:RegCloseKey
0x18000e33c  nop     dword ptr [rax+rax+00h]
0x18000e341  lea     r8, off_180042010
0x18000e348  mov     edx, 2
0x18000e34d  call    sub_18000B300
0x18000e352  lea     r8, off_180042020
0x18000e359  mov     edx, 6
0x18000e35e  mov     rdi, rax
0x18000e361  call    sub_18000B300
0x18000e366  mov     rbx, rax
0x18000e369  test    rdi, rdi
0x18000e36c  jz      loc_18000E44D
0x18000e372  test    rax, rax
0x18000e375  jz      loc_18000E448
0x18000e37b  mov     [rsp+120h+pOutTypes], rax; pOutTypes
0x18000e380  lea     r8, guidCategory; guidCategory
0x18000e387  mov     [rsp+120h+cOutTypes], 6; cOutTypes
0x18000e38f  lea     rdx, clsidDMO; clsidDMO
0x18000e396  mov     qword ptr [rsp+120h+cbData], rdi; pInTypes
0x18000e39b  lea     rcx, pszName; "WMV Screen decoder DMO"
0x18000e3a2  xor     r9d, r9d; dwFlags
0x18000e3a5  mov     dword ptr [rsp+120h+phkResult], 2; cInTypes
0x18000e3ad  call    cs:DMORegister
0x18000e3b4  nop     dword ptr [rax+rax+00h]
0x18000e3b9  mov     rcx, rdi
0x18000e3bc  mov     esi, eax
0x18000e3be  call    j_j__o_free
0x18000e3c3  mov     rcx, rbx
0x18000e3c6  call    j_j__o_free
0x18000e3cb  test    esi, esi
0x18000e3cd  jns     short loc_18000E3D6
0x18000e3cf  mov     eax, esi
0x18000e3d1  jmp     loc_18000E45F
0x18000e3d6  movups  xmm0, cs:xmmword_18003E1A0
0x18000e3dd  mov     [rsp+120h+pAttributes], 0; pAttributes
0x18000e3e6  lea     rax, pOutputTypes
0x18000e3ed  movups  xmm1, xmmword ptr cs:clsidDMO.Data1
0x18000e3f4  mov     [rsp+120h+pOutTypes], rax; pOutputTypes
0x18000e3f9  lea     r8, pszName; "WMV Screen decoder DMO"
0x18000e400  lea     rax, pInputTypes
0x18000e407  mov     [rsp+120h+cOutTypes], 6; cOutputTypes
0x18000e40f  mov     qword ptr [rsp+120h+cbData], rax; pInputTypes
0x18000e414  lea     rdx, [rbp+20h+guidCategory]; guidCategory
0x18000e418  xor     r9d, r9d; Flags
0x18000e41b  mov     dword ptr [rsp+120h+phkResult], 2; cInputTypes
0x18000e423  lea     rcx, [rbp+20h+clsidMFT]; clsidMFT
0x18000e427  movdqu  xmmword ptr [rbp+20h+guidCategory.Data1], xmm0
0x18000e42c  movdqu  xmmword ptr [rbp+20h+clsidMFT.Data1], xmm1
0x18000e431  call    cs:MFTRegister
0x18000e438  nop     dword ptr [rax+rax+00h]
0x18000e43d  xor     ecx, ecx
0x18000e43f  test    eax, eax
0x18000e441  cmovs   ecx, eax
0x18000e444  mov     eax, ecx
0x18000e446  jmp     short loc_18000E45F
0x18000e448  mov     rcx, rdi
0x18000e44b  jmp     short loc_18000E455
0x18000e44d  test    rbx, rbx
0x18000e450  jz      short loc_18000E45A
0x18000e452  mov     rcx, rbx
0x18000e455  call    j_j__o_free
0x18000e45a  mov     eax, 8007000Eh
0x18000e45f  mov     rcx, [rbp+20h+var_30]
0x18000e463  xor     rcx, rsp; StackCookie
0x18000e466  call    __security_check_cookie
0x18000e46b  add     rsp, 108h
0x18000e472  pop     rdi
0x18000e473  pop     rsi
0x18000e474  pop     rbx
0x18000e475  pop     rbp
0x18000e476  retn
```
