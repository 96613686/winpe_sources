# DllRegisterServer

- ea: `0x1800bff80`
- end: `0x1800c01dc`
- name: `DllRegisterServer`
- size: `604`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180099040`
- `0x1800994a0`
- `0x1800b7084`
- `0x1800bff00`
- `0x1800bff80`
- `0x1800c6990`
- `0x1800c6b84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bffec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bffec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c006c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c006c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0027`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c005b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0027`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c005b`
- `msdmo!DMORegister` at `0x1800c011d`
- `msdmo!DMORegister` at `0x1800c011d`
- `MFPlat!MFTRegister` at `0x1800c0180`
- `MFPlat!MFTRegister` at `0x1800c0180`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  HRESULT v1; // ebx
  __int64 v2; // rcx
  __int64 v3; // rcx
  const DMO_PARTIAL_MEDIATYPE *v4; // r15
  MFT_REGISTER_TYPE_INFO *v5; // r14
  __int64 v6; // rcx
  MFT_REGISTER_TYPE_INFO *v7; // rsi
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rdi
  __int64 v9; // rcx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-A0h] BYREF
  CLSID clsidMFT; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[80]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  v1 = sub_1800C6B84();
  if ( v1 < 0 )
    return v1;
  v1 = sub_1800C6990(v0, SubKey);
  if ( v1 < 0 )
    return v1;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
  {
    *(_DWORD *)Data = 8388609;
    RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
    *(_DWORD *)Data = 256;
    RegSetValueExW(hKey, L"WMSDKMerit", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  v4 = (const DMO_PARTIAL_MEDIATYPE *)sub_1800BFF00(v2, 9, off_180212200);
  if ( !v4 )
    return -2147024882;
  v5 = 0;
  v7 = (MFT_REGISTER_TYPE_INFO *)sub_1800B7084(v3, 9, off_180212200);
  if ( v7 )
  {
    pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)sub_1800BFF00(v6, 13, &off_180210040);
    if ( pOutTypes )
    {
      v5 = (MFT_REGISTER_TYPE_INFO *)sub_1800B7084(v9, 13, off_1802122C0);
      v1 = DMORegister(L"WMVideo Decoder DMO", &clsidDMO, &::guidCategory, 0, 9u, v4, 0xDu, pOutTypes);
      if ( v1 >= 0 )
      {
        guidCategory = (GUID)xmmword_18021E978;
        clsidMFT = clsidDMO;
        v1 = MFTRegister(&clsidMFT, &guidCategory, (LPWSTR)L"WMVideo Decoder DMO", 0, 0, v7, 0xDu, v5, 0);
      }
      goto LABEL_13;
    }
  }
  else
  {
    pOutTypes = 0;
  }
  v1 = -2147024882;
LABEL_13:
  j_j__o_free(v4);
  if ( pOutTypes )
    j_j__o_free(pOutTypes);
  if ( v7 )
    j_j__o_free(v7);
  if ( v5 )
    j_j__o_free(v5);
  return v1;
}

```

## disassembly

```asm
0x1800bff80  push    rbp
0x1800bff82  push    rbx
0x1800bff83  push    rsi
0x1800bff84  push    rdi
0x1800bff85  push    r14
0x1800bff87  push    r15
0x1800bff89  lea     rbp, [rsp-38h]
0x1800bff8e  sub     rsp, 138h
0x1800bff95  mov     rax, cs:__security_cookie
0x1800bff9c  xor     rax, rsp
0x1800bff9f  mov     [rbp+60h+var_40], rax
0x1800bffa3  mov     [rsp+160h+hKey], 0
0x1800bffac  call    sub_1800C6B84
0x1800bffb1  mov     ebx, eax
0x1800bffb3  test    eax, eax
0x1800bffb5  js      loc_1800C01BD
0x1800bffbb  lea     rdx, [rbp+60h+SubKey]
0x1800bffbf  call    sub_1800C6990
0x1800bffc4  mov     ebx, eax
0x1800bffc6  test    eax, eax
0x1800bffc8  js      loc_1800C01BD
0x1800bffce  lea     rax, [rsp+160h+hKey]
0x1800bffd3  mov     r9d, 2; samDesired
0x1800bffd9  xor     r8d, r8d; ulOptions
0x1800bffdc  mov     [rsp+160h+phkResult], rax; phkResult
0x1800bffe1  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x1800bffe5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800bffec  call    cs:RegOpenKeyExW
0x1800bfff3  nop     dword ptr [rax+rax+00h]
0x1800bfff8  test    eax, eax
0x1800bfffa  jnz     short loc_1800C0078
0x1800bfffc  mov     rcx, [rsp+160h+hKey]; hKey
0x1800c0001  lea     ebx, [rax+4]
0x1800c0004  lea     rax, [rsp+160h+Data]
0x1800c0009  mov     [rsp+160h+cbData], ebx; cbData
0x1800c000d  mov     r9d, ebx; dwType
0x1800c0010  mov     [rsp+160h+phkResult], rax; lpData
0x1800c0015  xor     r8d, r8d; Reserved
0x1800c0018  mov     dword ptr [rsp+160h+Data], 800001h
0x1800c0020  lea     rdx, aMerit; "Merit"
0x1800c0027  call    cs:RegSetValueExW
0x1800c002e  nop     dword ptr [rax+rax+00h]
0x1800c0033  mov     rcx, [rsp+160h+hKey]; hKey
0x1800c0038  lea     rax, [rsp+160h+Data]
0x1800c003d  mov     [rsp+160h+cbData], ebx; cbData
0x1800c0041  lea     rdx, aWmsdkmerit; "WMSDKMerit"
0x1800c0048  mov     r9d, ebx; dwType
0x1800c004b  mov     [rsp+160h+phkResult], rax; lpData
0x1800c0050  xor     r8d, r8d; Reserved
0x1800c0053  mov     dword ptr [rsp+160h+Data], 100h
0x1800c005b  call    cs:RegSetValueExW
0x1800c0062  nop     dword ptr [rax+rax+00h]
0x1800c0067  mov     rcx, [rsp+160h+hKey]; hKey
0x1800c006c  call    cs:RegCloseKey
0x1800c0073  nop     dword ptr [rax+rax+00h]
0x1800c0078  mov     ebx, 9
0x1800c007d  lea     r8, off_180212200
0x1800c0084  mov     edx, ebx
0x1800c0086  call    sub_1800BFF00
0x1800c008b  mov     r15, rax
0x1800c008e  test    rax, rax
0x1800c0091  jnz     short loc_1800C009D
0x1800c0093  mov     ebx, 8007000Eh
0x1800c0098  jmp     loc_1800C01BD
0x1800c009d  lea     r8, off_180212200
0x1800c00a4  mov     edx, ebx
0x1800c00a6  xor     r14d, r14d
0x1800c00a9  call    sub_1800B7084
0x1800c00ae  mov     rsi, rax
0x1800c00b1  test    rax, rax
0x1800c00b4  jnz     short loc_1800C00C2
0x1800c00b6  xor     edi, edi
0x1800c00b8  mov     ebx, 8007000Eh
0x1800c00bd  jmp     loc_1800C018E
0x1800c00c2  lea     r8, off_180210040
0x1800c00c9  mov     edx, 0Dh
0x1800c00ce  call    sub_1800BFF00
0x1800c00d3  mov     rdi, rax
0x1800c00d6  test    rax, rax
0x1800c00d9  jz      short loc_1800C00B8
0x1800c00db  lea     r8, off_1802122C0; "NV12"
0x1800c00e2  mov     edx, 0Dh
0x1800c00e7  call    sub_1800B7084
0x1800c00ec  mov     [rsp+160h+pOutTypes], rdi; pOutTypes
0x1800c00f1  lea     r8, guidCategory; guidCategory
0x1800c00f8  mov     [rsp+160h+cOutTypes], 0Dh; cOutTypes
0x1800c0100  lea     rdx, clsidDMO; clsidDMO
0x1800c0107  mov     qword ptr [rsp+160h+cbData], r15; pInTypes
0x1800c010c  lea     rcx, pszName; "WMVideo Decoder DMO"
0x1800c0113  xor     r9d, r9d; dwFlags
0x1800c0116  mov     dword ptr [rsp+160h+phkResult], ebx; cInTypes
0x1800c011a  mov     r14, rax
0x1800c011d  call    cs:DMORegister
0x1800c0124  nop     dword ptr [rax+rax+00h]
0x1800c0129  mov     ebx, eax
0x1800c012b  test    eax, eax
0x1800c012d  js      short loc_1800C018E
0x1800c012f  movups  xmm0, cs:xmmword_18021E978
0x1800c0136  mov     [rsp+160h+pAttributes], 0; pAttributes
0x1800c013f  xor     r9d, r9d; Flags
0x1800c0142  movups  xmm1, xmmword ptr cs:clsidDMO.Data1
0x1800c0149  mov     [rsp+160h+pOutTypes], r14; pOutputTypes
0x1800c014e  lea     r8, pszName; "WMVideo Decoder DMO"
0x1800c0155  mov     [rsp+160h+cOutTypes], 0Dh; cOutputTypes
0x1800c015d  lea     rdx, [rsp+160h+guidCategory]; guidCategory
0x1800c0162  mov     qword ptr [rsp+160h+cbData], rsi; pInputTypes
0x1800c0167  lea     rcx, [rsp+160h+clsidMFT]; clsidMFT
0x1800c016c  movdqu  xmmword ptr [rsp+160h+guidCategory.Data1], xmm0
0x1800c0172  mov     dword ptr [rsp+160h+phkResult], 0; cInputTypes
0x1800c017a  movdqu  xmmword ptr [rsp+160h+clsidMFT.Data1], xmm1
0x1800c0180  call    cs:MFTRegister
0x1800c0187  nop     dword ptr [rax+rax+00h]
0x1800c018c  mov     ebx, eax
0x1800c018e  mov     rcx, r15
0x1800c0191  call    j_j__o_free
0x1800c0196  test    rdi, rdi
0x1800c0199  jz      short loc_1800C01A3
0x1800c019b  mov     rcx, rdi
0x1800c019e  call    j_j__o_free
0x1800c01a3  test    rsi, rsi
0x1800c01a6  jz      short loc_1800C01B0
0x1800c01a8  mov     rcx, rsi
0x1800c01ab  call    j_j__o_free
0x1800c01b0  test    r14, r14
0x1800c01b3  jz      short loc_1800C01BD
0x1800c01b5  mov     rcx, r14
0x1800c01b8  call    j_j__o_free
0x1800c01bd  mov     eax, ebx
0x1800c01bf  mov     rcx, [rbp+60h+var_40]
0x1800c01c3  xor     rcx, rsp; StackCookie
0x1800c01c6  call    __security_check_cookie
0x1800c01cb  add     rsp, 138h
0x1800c01d2  pop     r15
0x1800c01d4  pop     r14
0x1800c01d6  pop     rdi
0x1800c01d7  pop     rsi
0x1800c01d8  pop     rbx
0x1800c01d9  pop     rbp
0x1800c01da  retn
```
