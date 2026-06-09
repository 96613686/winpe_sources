# DllRegisterServer

- ea: `0x180008350`
- end: `0x18000866b`
- name: `DllRegisterServer`
- size: `795`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001420`
- `0x180001880`
- `0x180004ecc`
- `0x180008350`
- `0x180008bd0`

## import_xrefs

- `MFPlat!MFTRegister` at `0x18000863b`
- `MFPlat!MFTRegister` at `0x18000863b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180008389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180008389`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800084b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800084b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008547`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008547`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000853c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000853c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008508`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008508`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800083b5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180008430`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800083b5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180008430`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x1800083e3`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180008476`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x1800083e3`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180008476`
- `msdmo!DMORegister` at `0x1800085b9`
- `msdmo!DMORegister` at `0x1800085b9`

## string_xrefs

- `0x1800084a2`: `ThreadingModel`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const struct _GUID *v0; // rcx
  HRESULT result; // eax
  HKEY v2; // rbx
  HKEY v3; // rdi
  __int64 cbData; // rax
  HKEY v5; // rcx
  LSTATUS v6; // eax
  const struct _GUID *v7; // rcx
  __int64 v8; // rcx
  DMO_PARTIAL_MEDIATYPE *v9; // rdi
  __int64 v10; // rcx
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  unsigned __int64 v12; // rdx
  DMO_PARTIAL_MEDIATYPE *v13; // rbx
  int v14; // esi
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  int v17; // eax
  HRESULT v18; // ecx
  DMO_PARTIAL_MEDIATYPE *v19; // rcx
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v21; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v24[80]; // [rsp+120h] [rbp+20h] BYREF
  CHAR Filename[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = MakeCLSIDRegPath(v0, SubKey);
  if ( result >= 0 )
  {
    phkResult[0] = 0;
    if ( RegCreateKeyW(HKEY_CLASSES_ROOT, SubKey, phkResult) )
      return -2147467259;
    v2 = phkResult[0];
    if ( !phkResult[0] )
      return -2147467259;
    if ( RegSetValueA(phkResult[0], 0, 1u, "Mpeg43 Decoder DMO", 0x12u) )
    {
LABEL_5:
      RegCloseKey(v2);
      return -2147467259;
    }
    hKey[0] = 0;
    if ( RegCreateKeyW(phkResult[0], L"InprocServer32", hKey) )
    {
      hKey[0] = 0;
      goto LABEL_5;
    }
    v3 = hKey[0];
    if ( !hKey[0] )
      goto LABEL_5;
    cbData = -1;
    do
      ++cbData;
    while ( Filename[cbData] );
    if ( RegSetValueA(hKey[0], 0, 1u, Filename, cbData) )
    {
      v5 = v3;
LABEL_15:
      RegCloseKey(v5);
      goto LABEL_5;
    }
    v6 = RegSetValueExA(hKey[0], "ThreadingModel", 0, 1u, "Both", 5u);
    v5 = v3;
    if ( v6 )
      goto LABEL_15;
    RegCloseKey(v3);
    RegCloseKey(v2);
    result = MakeCLSIDRegPath(v7, v24);
    if ( result >= 0 )
    {
      v21 = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, v24, 0, 2u, &v21) )
      {
        LODWORD(hKey[0]) = 8388609;
        RegSetValueExW(v21, L"Merit", 0, 4u, (const BYTE *)hKey, 4u);
        RegCloseKey(v21);
      }
      v9 = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v8, 2, &off_180027010);
      pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v10, 9, &off_180027020);
      v13 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
      if ( v9 )
      {
        if ( pOutTypes )
        {
          v14 = DMORegister(
                  L"Mpeg43 Decoder DMO",
                  &CLSID_CMpeg43DecMediaObject,
                  &DMOCATEGORY_VIDEO_DECODER,
                  0,
                  2u,
                  v9,
                  9u,
                  pOutTypes);
          operator delete(v9, v15);
          operator delete(v13, v16);
          if ( v14 < 0 )
            return v14;
          *(GUID *)phkResult = MFT_CATEGORY_VIDEO_DECODER;
          *(GUID *)hKey = CLSID_CMpeg43DecMediaObject;
          v17 = MFTRegister(
                  (CLSID *)hKey,
                  (GUID *)phkResult,
                  (LPWSTR)L"Mpeg43 Decoder DMO",
                  0,
                  2u,
                  &pInputTypes,
                  9u,
                  &pOutputTypes,
                  0);
          v18 = 0;
          if ( v17 < 0 )
            return v17;
          return v18;
        }
        v19 = v9;
      }
      else
      {
        if ( !pOutTypes )
          return -2147024882;
        v19 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
      }
      operator delete(v19, v12);
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008350  push    rbp
0x180008352  push    rbx
0x180008353  push    rsi
0x180008354  push    rdi
0x180008355  lea     rbp, [rsp-1E8h]
0x18000835d  sub     rsp, 2E8h
0x180008364  mov     rax, cs:__security_cookie
0x18000836b  xor     rax, rsp
0x18000836e  mov     [rbp+200h+var_30], rax
0x180008375  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18000837c  lea     rdx, [rbp+200h+Filename]; lpFilename
0x180008383  mov     r8d, 104h; nSize
0x180008389  call    cs:__imp_GetModuleFileNameA
0x18000838f  lea     rdx, [rbp+200h+SubKey]; unsigned __int16 *
0x180008393  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x180008398  test    eax, eax
0x18000839a  js      short loc_1800083FB
0x18000839c  lea     r8, [rsp+300h+phkResult]; phkResult
0x1800083a1  mov     [rsp+300h+phkResult], 0
0x1800083aa  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x1800083ae  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800083b5  call    cs:__imp_RegCreateKeyW
0x1800083bb  test    eax, eax
0x1800083bd  jnz     short loc_1800083F6
0x1800083bf  mov     rbx, [rsp+300h+phkResult]
0x1800083c4  test    rbx, rbx
0x1800083c7  jz      short loc_1800083F6
0x1800083c9  lea     esi, [rax+1]
0x1800083cc  mov     [rsp+300h+cbData], 12h; cbData
0x1800083d4  mov     r8d, esi; dwType
0x1800083d7  lea     r9, Data; "Mpeg43 Decoder DMO"
0x1800083de  xor     edx, edx; lpSubKey
0x1800083e0  mov     rcx, rbx; hKey
0x1800083e3  call    cs:__imp_RegSetValueA
0x1800083e9  test    eax, eax
0x1800083eb  jz      short loc_180008416
0x1800083ed  mov     rcx, rbx; hKey
0x1800083f0  call    cs:__imp_RegCloseKey
0x1800083f6  mov     eax, 80004005h
0x1800083fb  mov     rcx, [rbp+200h+var_30]
0x180008402  xor     rcx, rsp; StackCookie
0x180008405  call    __security_check_cookie
0x18000840a  add     rsp, 2E8h
0x180008411  pop     rdi
0x180008412  pop     rsi
0x180008413  pop     rbx
0x180008414  pop     rbp
0x180008415  retn
0x180008416  mov     rcx, [rsp+300h+phkResult]; hKey
0x18000841b  lea     r8, [rsp+300h+hKey]; phkResult
0x180008420  lea     rdx, SubKey; "InprocServer32"
0x180008427  mov     [rsp+300h+hKey], 0
0x180008430  call    cs:__imp_RegCreateKeyW
0x180008436  test    eax, eax
0x180008438  jz      short loc_180008445
0x18000843a  mov     [rsp+300h+hKey], 0
0x180008443  jmp     short loc_1800083ED
0x180008445  mov     rdi, [rsp+300h+hKey]
0x18000844a  test    rdi, rdi
0x18000844d  jz      short loc_1800083ED
0x18000844f  lea     rcx, [rbp+200h+Filename]
0x180008456  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000845a  inc     rax
0x18000845d  cmp     byte ptr [rcx+rax], 0
0x180008461  jnz     short loc_18000845A
0x180008463  lea     r9, [rbp+200h+Filename]; lpData
0x18000846a  mov     [rsp+300h+cbData], eax; cbData
0x18000846e  mov     r8d, esi; dwType
0x180008471  xor     edx, edx; lpSubKey
0x180008473  mov     rcx, rdi; hKey
0x180008476  call    cs:__imp_RegSetValueA
0x18000847c  test    eax, eax
0x18000847e  jz      short loc_18000848E
0x180008480  mov     rcx, rdi; hKey
0x180008483  call    cs:__imp_RegCloseKey
0x180008489  jmp     loc_1800083ED
0x18000848e  mov     rcx, [rsp+300h+hKey]; hKey
0x180008493  lea     rax, aBoth; "Both"
0x18000849a  mov     [rsp+300h+var_2D8], 5; cbData
0x1800084a2  lea     rdx, ValueName; "ThreadingModel"
0x1800084a9  mov     r9d, esi; dwType
0x1800084ac  mov     qword ptr [rsp+300h+cbData], rax; lpData
0x1800084b1  xor     r8d, r8d; Reserved
0x1800084b4  call    cs:__imp_RegSetValueExA
0x1800084ba  mov     rcx, rdi; hKey
0x1800084bd  test    eax, eax
0x1800084bf  jnz     short loc_180008483
0x1800084c1  call    cs:__imp_RegCloseKey
0x1800084c7  mov     rcx, rbx; hKey
0x1800084ca  call    cs:__imp_RegCloseKey
0x1800084d0  lea     rdx, [rbp+200h+var_1E0]; unsigned __int16 *
0x1800084d4  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x1800084d9  test    eax, eax
0x1800084db  js      loc_1800083FB
0x1800084e1  lea     rax, [rsp+300h+var_2A0]
0x1800084e6  mov     [rsp+300h+var_2A0], 0
0x1800084ef  mov     r9d, 2; samDesired
0x1800084f5  mov     qword ptr [rsp+300h+cbData], rax; phkResult
0x1800084fa  xor     r8d, r8d; ulOptions
0x1800084fd  lea     rdx, [rbp+200h+var_1E0]; lpSubKey
0x180008501  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180008508  call    cs:__imp_RegOpenKeyExW
0x18000850e  test    eax, eax
0x180008510  jnz     short loc_18000854D
0x180008512  mov     rcx, [rsp+300h+var_2A0]; hKey
0x180008517  lea     r9d, [rax+4]; dwType
0x18000851b  lea     rax, [rsp+300h+hKey]
0x180008520  mov     [rsp+300h+var_2D8], r9d; cbData
0x180008525  xor     r8d, r8d; Reserved
0x180008528  mov     qword ptr [rsp+300h+cbData], rax; lpData
0x18000852d  lea     rdx, aMerit; "Merit"
0x180008534  mov     dword ptr [rsp+300h+hKey], 800001h
0x18000853c  call    cs:__imp_RegSetValueExW
0x180008542  mov     rcx, [rsp+300h+var_2A0]; hKey
0x180008547  call    cs:__imp_RegCloseKey
0x18000854d  lea     r8, off_180027010
0x180008554  mov     edx, 2
0x180008559  call    GuidPairArray
0x18000855e  lea     r8, off_180027020
0x180008565  mov     edx, 9
0x18000856a  mov     rdi, rax
0x18000856d  call    GuidPairArray
0x180008572  mov     rbx, rax
0x180008575  test    rdi, rdi
0x180008578  jz      loc_180008654
0x18000857e  test    rax, rax
0x180008581  jz      loc_18000864F
0x180008587  mov     [rsp+300h+pOutTypes], rax; pOutTypes
0x18000858c  lea     r8, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x180008593  mov     [rsp+300h+cOutTypes], 9; cOutTypes
0x18000859b  lea     rdx, CLSID_CMpeg43DecMediaObject; clsidDMO
0x1800085a2  mov     qword ptr [rsp+300h+var_2D8], rdi; pInTypes
0x1800085a7  lea     rcx, pszName; "Mpeg43 Decoder DMO"
0x1800085ae  xor     r9d, r9d; dwFlags
0x1800085b1  mov     [rsp+300h+cbData], 2; cInTypes
0x1800085b9  call    cs:__imp_DMORegister
0x1800085bf  mov     rcx, rdi; void *
0x1800085c2  mov     esi, eax
0x1800085c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800085c9  mov     rcx, rbx; void *
0x1800085cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800085d1  test    esi, esi
0x1800085d3  jns     short loc_1800085DC
0x1800085d5  mov     eax, esi
0x1800085d7  jmp     loc_1800083FB
0x1800085dc  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800085e3  mov     [rsp+300h+pAttributes], 0; pAttributes
0x1800085ec  lea     rax, pOutputTypes
0x1800085f3  movups  xmm1, xmmword ptr cs:CLSID_CMpeg43DecMediaObject.Data1
0x1800085fa  mov     [rsp+300h+pOutTypes], rax; pOutputTypes
0x1800085ff  lea     r8, pszName; "Mpeg43 Decoder DMO"
0x180008606  lea     rax, pInputTypes
0x18000860d  mov     [rsp+300h+cOutTypes], 9; cOutputTypes
0x180008615  mov     qword ptr [rsp+300h+var_2D8], rax; pInputTypes
0x18000861a  lea     rdx, [rsp+300h+phkResult]; guidCategory
0x18000861f  xor     r9d, r9d; Flags
0x180008622  mov     [rsp+300h+cbData], 2; cInputTypes
0x18000862a  lea     rcx, [rsp+300h+hKey]; clsidMFT
0x18000862f  movdqu  xmmword ptr [rsp+300h+phkResult], xmm0
0x180008635  movdqu  xmmword ptr [rsp+300h+hKey], xmm1
0x18000863b  call    cs:__imp_MFTRegister
0x180008641  xor     ecx, ecx
0x180008643  test    eax, eax
0x180008645  cmovs   ecx, eax
0x180008648  mov     eax, ecx
0x18000864a  jmp     loc_1800083FB
0x18000864f  mov     rcx, rdi
0x180008652  jmp     short loc_18000865C
0x180008654  test    rbx, rbx
0x180008657  jz      short loc_180008661
0x180008659  mov     rcx, rbx; void *
0x18000865c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008661  mov     eax, 8007000Eh
0x180008666  jmp     loc_1800083FB
```
