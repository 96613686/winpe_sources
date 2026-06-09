# DllRegisterServer

- ea: `0x18002e240`
- end: `0x18002e43e`
- name: `DllRegisterServer`
- size: `510`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002a6b0`
- `0x18002aac0`
- `0x18002ce8c`
- `0x18002e240`
- `0x18002e600`
- `0x18002e7d4`

## import_xrefs

- `MFPlat!MFTRegister` at `0x18002e3e7`
- `MFPlat!MFTRegister` at `0x18002e3e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e2f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e2b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e2b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2ec`
- `msdmo!DMORegister` at `0x18002e365`
- `msdmo!DMORegister` at `0x18002e365`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rcx
  DMO_PARTIAL_MEDIATYPE *v2; // rdi
  __int64 v3; // rcx
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  DMO_PARTIAL_MEDIATYPE *v5; // rbx
  int v6; // esi
  HRESULT CLSIDRegKey; // eax
  HRESULT v8; // ecx
  DMO_PARTIAL_MEDIATYPE *v9; // rcx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-A0h] BYREF
  CLSID clsidMFT; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[80]; // [rsp+80h] [rbp-80h] BYREF

  result = CreateCLSIDRegKey(&CLSID_CMpeg4sDecMediaObject, "Mpeg4s Decoder DMO");
  if ( result < 0 )
    return result;
  result = MakeCLSIDRegPath(&CLSID_CMpeg4sDecMediaObject, SubKey);
  if ( result < 0 )
    return result;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
  {
    *(_DWORD *)Data = 8388609;
    RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  v2 = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v1, 13, &off_180059030);
  pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v3, 11, off_1800590A0);
  v5 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
  if ( !v2 )
  {
    if ( !pOutTypes )
      return -2147024882;
    v9 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
LABEL_16:
    operator delete(v9);
    return -2147024882;
  }
  if ( !pOutTypes )
  {
    v9 = v2;
    goto LABEL_16;
  }
  v6 = DMORegister(
         L"Mpeg4s Decoder DMO",
         &CLSID_CMpeg4sDecMediaObject,
         &DMOCATEGORY_VIDEO_DECODER,
         0,
         0xDu,
         v2,
         0xBu,
         pOutTypes);
  operator delete(v2);
  operator delete(v5);
  if ( v6 < 0 )
    return v6;
  guidCategory = MFT_CATEGORY_VIDEO_DECODER;
  clsidMFT = CLSID_CMpeg4sDecMFT;
  result = MFTRegister(
             &clsidMFT,
             &guidCategory,
             (LPWSTR)L"Mpeg4s Decoder MFT",
             0,
             7u,
             &pInputTypes,
             2u,
             &pOutputTypes,
             0);
  if ( result >= 0 )
  {
    CLSIDRegKey = CreateCLSIDRegKey(&CLSID_CMpeg4sDecMFT, "Mpeg4s Decoder MFT");
    v8 = 0;
    if ( CLSIDRegKey < 0 )
      return CLSIDRegKey;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18002e240  push    rbp
0x18002e242  push    rbx
0x18002e243  push    rsi
0x18002e244  push    rdi
0x18002e245  lea     rbp, [rsp-38h]
0x18002e24a  sub     rsp, 138h
0x18002e251  mov     rax, cs:__security_cookie
0x18002e258  xor     rax, rsp
0x18002e25b  mov     [rbp+50h+var_30], rax
0x18002e25f  lea     rsi, CLSID_CMpeg4sDecMediaObject
0x18002e266  mov     rcx, rsi; struct _GUID *
0x18002e269  lea     rdx, aMpeg4sDecoderD_0; "Mpeg4s Decoder DMO"
0x18002e270  call    CreateCLSIDRegKey
0x18002e275  test    eax, eax
0x18002e277  js      loc_18002E426
0x18002e27d  lea     rdx, [rbp+50h+SubKey]; unsigned __int16 *
0x18002e281  mov     rcx, rsi; struct _GUID *
0x18002e284  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18002e289  test    eax, eax
0x18002e28b  js      loc_18002E426
0x18002e291  lea     rax, [rsp+150h+hKey]
0x18002e296  mov     [rsp+150h+hKey], 0
0x18002e29f  mov     r9d, 2; samDesired
0x18002e2a5  mov     [rsp+150h+phkResult], rax; phkResult
0x18002e2aa  xor     r8d, r8d; ulOptions
0x18002e2ad  lea     rdx, [rbp+50h+SubKey]; lpSubKey
0x18002e2b1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002e2b8  call    cs:__imp_RegOpenKeyExW
0x18002e2be  test    eax, eax
0x18002e2c0  jnz     short loc_18002E2FD
0x18002e2c2  mov     rcx, [rsp+150h+hKey]; hKey
0x18002e2c7  lea     r9d, [rax+4]; dwType
0x18002e2cb  lea     rax, [rsp+150h+Data]
0x18002e2d0  mov     [rsp+150h+cbData], r9d; cbData
0x18002e2d5  xor     r8d, r8d; Reserved
0x18002e2d8  mov     [rsp+150h+phkResult], rax; lpData
0x18002e2dd  lea     rdx, aMerit; "Merit"
0x18002e2e4  mov     dword ptr [rsp+150h+Data], 800001h
0x18002e2ec  call    cs:__imp_RegSetValueExW
0x18002e2f2  mov     rcx, [rsp+150h+hKey]; hKey
0x18002e2f7  call    cs:__imp_RegCloseKey
0x18002e2fd  lea     r8, off_180059030
0x18002e304  mov     edx, 0Dh
0x18002e309  call    GuidPairArray
0x18002e30e  lea     r8, off_1800590A0
0x18002e315  mov     edx, 0Bh
0x18002e31a  mov     rdi, rax
0x18002e31d  call    GuidPairArray
0x18002e322  mov     rbx, rax
0x18002e325  test    rdi, rdi
0x18002e328  jz      loc_18002E414
0x18002e32e  test    rax, rax
0x18002e331  jz      loc_18002E40F
0x18002e337  mov     [rsp+150h+pOutTypes], rax; pOutTypes
0x18002e33c  lea     r8, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x18002e343  mov     [rsp+150h+cOutTypes], 0Bh; cOutTypes
0x18002e34b  lea     rcx, szName; "Mpeg4s Decoder DMO"
0x18002e352  mov     qword ptr [rsp+150h+cbData], rdi; pInTypes
0x18002e357  xor     r9d, r9d; dwFlags
0x18002e35a  mov     rdx, rsi; clsidDMO
0x18002e35d  mov     dword ptr [rsp+150h+phkResult], 0Dh; cInTypes
0x18002e365  call    cs:__imp_DMORegister
0x18002e36b  mov     rcx, rdi; Block
0x18002e36e  mov     esi, eax
0x18002e370  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002e375  mov     rcx, rbx; Block
0x18002e378  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002e37d  test    esi, esi
0x18002e37f  jns     short loc_18002E388
0x18002e381  mov     eax, esi
0x18002e383  jmp     loc_18002E426
0x18002e388  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x18002e38f  mov     [rsp+150h+pAttributes], 0; pAttributes
0x18002e398  lea     rax, pOutputTypes
0x18002e39f  movups  xmm1, xmmword ptr cs:CLSID_CMpeg4sDecMFT.Data1
0x18002e3a6  mov     [rsp+150h+pOutTypes], rax; pOutputTypes
0x18002e3ab  lea     r8, pszName; "Mpeg4s Decoder MFT"
0x18002e3b2  lea     rax, pInputTypes
0x18002e3b9  mov     [rsp+150h+cOutTypes], 2; cOutputTypes
0x18002e3c1  mov     qword ptr [rsp+150h+cbData], rax; pInputTypes
0x18002e3c6  lea     rdx, [rsp+150h+guidCategory]; guidCategory
0x18002e3cb  xor     r9d, r9d; Flags
0x18002e3ce  mov     dword ptr [rsp+150h+phkResult], 7; cInputTypes
0x18002e3d6  lea     rcx, [rsp+150h+clsidMFT]; clsidMFT
0x18002e3db  movdqu  xmmword ptr [rsp+150h+guidCategory.Data1], xmm0
0x18002e3e1  movdqu  xmmword ptr [rsp+150h+clsidMFT.Data1], xmm1
0x18002e3e7  call    cs:__imp_MFTRegister
0x18002e3ed  test    eax, eax
0x18002e3ef  js      short loc_18002E426
0x18002e3f1  lea     rdx, aMpeg4sDecoderM_0; "Mpeg4s Decoder MFT"
0x18002e3f8  lea     rcx, CLSID_CMpeg4sDecMFT; struct _GUID *
0x18002e3ff  call    CreateCLSIDRegKey
0x18002e404  xor     ecx, ecx
0x18002e406  test    eax, eax
0x18002e408  cmovs   ecx, eax
0x18002e40b  mov     eax, ecx
0x18002e40d  jmp     short loc_18002E426
0x18002e40f  mov     rcx, rdi
0x18002e412  jmp     short loc_18002E41C
0x18002e414  test    rbx, rbx
0x18002e417  jz      short loc_18002E421
0x18002e419  mov     rcx, rbx; Block
0x18002e41c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002e421  mov     eax, 8007000Eh
0x18002e426  mov     rcx, [rbp+50h+var_30]
0x18002e42a  xor     rcx, rsp; StackCookie
0x18002e42d  call    __security_check_cookie
0x18002e432  add     rsp, 138h
0x18002e439  pop     rdi
0x18002e43a  pop     rsi
0x18002e43b  pop     rbx
0x18002e43c  pop     rbp
0x18002e43d  retn
```
