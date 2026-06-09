# DllRegisterServer

- ea: `0x180008410`
- end: `0x18000872b`
- name: `DllRegisterServer`
- size: `795`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001450`
- `0x1800018b0`
- `0x180004f8c`
- `0x180008410`
- `0x180008c90`

## import_xrefs

- `MFPlat!MFTRegister` at `0x1800086fb`
- `MFPlat!MFTRegister` at `0x1800086fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000844b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000844b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000857b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000857b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000854a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000860f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000854a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000860f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800085cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800085cb`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000847a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800084f7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000847a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800084f7`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x1800084a8`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000853d`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x1800084a8`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000853d`
- `msdmo!DMORegister` at `0x18000867c`
- `msdmo!DMORegister` at `0x18000867c`

## string_xrefs

- `0x180008569`: `ThreadingModel`

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
    if ( RegSetValueA(phkResult[0], 0, 1u, "Mpeg4 Decoder DMO", 0x11u) )
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
      v9 = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v8, 4, &off_180027010);
      pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v10, 9, &off_180027030);
      v13 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
      if ( v9 )
      {
        if ( pOutTypes )
        {
          v14 = DMORegister(
                  L"Mpeg4 Decoder DMO",
                  &CLSID_CMpeg4DecMediaObject,
                  &DMOCATEGORY_VIDEO_DECODER,
                  0,
                  4u,
                  v9,
                  9u,
                  pOutTypes);
          operator delete(v9, v15);
          operator delete(v13, v16);
          if ( v14 < 0 )
            return v14;
          *(GUID *)phkResult = MFT_CATEGORY_VIDEO_DECODER;
          *(GUID *)hKey = CLSID_CMpeg4DecMediaObject;
          v17 = MFTRegister(
                  (CLSID *)hKey,
                  (GUID *)phkResult,
                  (LPWSTR)L"Mpeg4 Decoder DMO",
                  0,
                  4u,
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
0x180008410  push    rbp
0x180008412  push    rbx
0x180008413  push    rsi
0x180008414  push    rdi
0x180008415  push    r15
0x180008417  lea     rbp, [rsp-1E0h]
0x18000841f  sub     rsp, 2E0h
0x180008426  mov     rax, cs:__security_cookie
0x18000842d  xor     rax, rsp
0x180008430  mov     [rbp+200h+var_30], rax
0x180008437  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18000843e  lea     rdx, [rbp+200h+Filename]; lpFilename
0x180008445  mov     r8d, 104h; nSize
0x18000844b  call    cs:__imp_GetModuleFileNameA
0x180008451  lea     rdx, [rbp+200h+SubKey]; unsigned __int16 *
0x180008455  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18000845a  test    eax, eax
0x18000845c  js      short loc_1800084C0
0x18000845e  mov     r15, 0FFFFFFFF80000000h
0x180008465  mov     [rsp+300h+phkResult], 0
0x18000846e  mov     rcx, r15; hKey
0x180008471  lea     r8, [rsp+300h+phkResult]; phkResult
0x180008476  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18000847a  call    cs:__imp_RegCreateKeyW
0x180008480  test    eax, eax
0x180008482  jnz     short loc_1800084BB
0x180008484  mov     rbx, [rsp+300h+phkResult]
0x180008489  test    rbx, rbx
0x18000848c  jz      short loc_1800084BB
0x18000848e  lea     esi, [rax+1]
0x180008491  mov     [rsp+300h+cbData], 11h; cbData
0x180008499  mov     r8d, esi; dwType
0x18000849c  lea     r9, Data; "Mpeg4 Decoder DMO"
0x1800084a3  xor     edx, edx; lpSubKey
0x1800084a5  mov     rcx, rbx; hKey
0x1800084a8  call    cs:__imp_RegSetValueA
0x1800084ae  test    eax, eax
0x1800084b0  jz      short loc_1800084DD
0x1800084b2  mov     rcx, rbx; hKey
0x1800084b5  call    cs:__imp_RegCloseKey
0x1800084bb  mov     eax, 80004005h
0x1800084c0  mov     rcx, [rbp+200h+var_30]
0x1800084c7  xor     rcx, rsp; StackCookie
0x1800084ca  call    __security_check_cookie
0x1800084cf  add     rsp, 2E0h
0x1800084d6  pop     r15
0x1800084d8  pop     rdi
0x1800084d9  pop     rsi
0x1800084da  pop     rbx
0x1800084db  pop     rbp
0x1800084dc  retn
0x1800084dd  mov     rcx, [rsp+300h+phkResult]; hKey
0x1800084e2  lea     r8, [rsp+300h+hKey]; phkResult
0x1800084e7  lea     rdx, SubKey; "InprocServer32"
0x1800084ee  mov     [rsp+300h+hKey], 0
0x1800084f7  call    cs:__imp_RegCreateKeyW
0x1800084fd  test    eax, eax
0x1800084ff  jz      short loc_18000850C
0x180008501  mov     [rsp+300h+hKey], 0
0x18000850a  jmp     short loc_1800084B2
0x18000850c  mov     rdi, [rsp+300h+hKey]
0x180008511  test    rdi, rdi
0x180008514  jz      short loc_1800084B2
0x180008516  lea     rcx, [rbp+200h+Filename]
0x18000851d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008521  inc     rax
0x180008524  cmp     byte ptr [rcx+rax], 0
0x180008528  jnz     short loc_180008521
0x18000852a  lea     r9, [rbp+200h+Filename]; lpData
0x180008531  mov     [rsp+300h+cbData], eax; cbData
0x180008535  mov     r8d, esi; dwType
0x180008538  xor     edx, edx; lpSubKey
0x18000853a  mov     rcx, rdi; hKey
0x18000853d  call    cs:__imp_RegSetValueA
0x180008543  test    eax, eax
0x180008545  jz      short loc_180008555
0x180008547  mov     rcx, rdi; hKey
0x18000854a  call    cs:__imp_RegCloseKey
0x180008550  jmp     loc_1800084B2
0x180008555  mov     rcx, [rsp+300h+hKey]; hKey
0x18000855a  lea     rax, aBoth; "Both"
0x180008561  mov     [rsp+300h+var_2D8], 5; cbData
0x180008569  lea     rdx, ValueName; "ThreadingModel"
0x180008570  mov     r9d, esi; dwType
0x180008573  mov     qword ptr [rsp+300h+cbData], rax; lpData
0x180008578  xor     r8d, r8d; Reserved
0x18000857b  call    cs:__imp_RegSetValueExA
0x180008581  mov     rcx, rdi; hKey
0x180008584  test    eax, eax
0x180008586  jnz     short loc_18000854A
0x180008588  call    cs:__imp_RegCloseKey
0x18000858e  mov     rcx, rbx; hKey
0x180008591  call    cs:__imp_RegCloseKey
0x180008597  lea     rdx, [rbp+200h+var_1E0]; unsigned __int16 *
0x18000859b  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x1800085a0  test    eax, eax
0x1800085a2  js      loc_1800084C0
0x1800085a8  lea     rax, [rsp+300h+var_2A0]
0x1800085ad  mov     [rsp+300h+var_2A0], 0
0x1800085b6  mov     r9d, 2; samDesired
0x1800085bc  mov     qword ptr [rsp+300h+cbData], rax; phkResult
0x1800085c1  xor     r8d, r8d; ulOptions
0x1800085c4  lea     rdx, [rbp+200h+var_1E0]; lpSubKey
0x1800085c8  mov     rcx, r15; hKey
0x1800085cb  call    cs:__imp_RegOpenKeyExW
0x1800085d1  mov     r15d, 4
0x1800085d7  test    eax, eax
0x1800085d9  jnz     short loc_180008615
0x1800085db  mov     rcx, [rsp+300h+var_2A0]; hKey
0x1800085e0  lea     rax, [rsp+300h+hKey]
0x1800085e5  mov     [rsp+300h+var_2D8], r15d; cbData
0x1800085ea  lea     rdx, aMerit; "Merit"
0x1800085f1  mov     r9d, r15d; dwType
0x1800085f4  mov     qword ptr [rsp+300h+cbData], rax; lpData
0x1800085f9  xor     r8d, r8d; Reserved
0x1800085fc  mov     dword ptr [rsp+300h+hKey], 800001h
0x180008604  call    cs:__imp_RegSetValueExW
0x18000860a  mov     rcx, [rsp+300h+var_2A0]; hKey
0x18000860f  call    cs:__imp_RegCloseKey
0x180008615  lea     r8, off_180027010
0x18000861c  mov     edx, r15d
0x18000861f  call    GuidPairArray
0x180008624  lea     r8, off_180027030
0x18000862b  mov     edx, 9
0x180008630  mov     rdi, rax
0x180008633  call    GuidPairArray
0x180008638  mov     rbx, rax
0x18000863b  test    rdi, rdi
0x18000863e  jz      loc_180008714
0x180008644  test    rax, rax
0x180008647  jz      loc_18000870F
0x18000864d  mov     [rsp+300h+pOutTypes], rax; pOutTypes
0x180008652  lea     r8, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x180008659  mov     [rsp+300h+cOutTypes], 9; cOutTypes
0x180008661  lea     rdx, CLSID_CMpeg4DecMediaObject; clsidDMO
0x180008668  mov     qword ptr [rsp+300h+var_2D8], rdi; pInTypes
0x18000866d  lea     rcx, pszName; "Mpeg4 Decoder DMO"
0x180008674  xor     r9d, r9d; dwFlags
0x180008677  mov     [rsp+300h+cbData], r15d; cInTypes
0x18000867c  call    cs:__imp_DMORegister
0x180008682  mov     rcx, rdi; void *
0x180008685  mov     esi, eax
0x180008687  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000868c  mov     rcx, rbx; void *
0x18000868f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008694  test    esi, esi
0x180008696  jns     short loc_18000869F
0x180008698  mov     eax, esi
0x18000869a  jmp     loc_1800084C0
0x18000869f  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800086a6  mov     [rsp+300h+pAttributes], 0; pAttributes
0x1800086af  lea     rax, pOutputTypes
0x1800086b6  movups  xmm1, xmmword ptr cs:CLSID_CMpeg4DecMediaObject.Data1
0x1800086bd  mov     [rsp+300h+pOutTypes], rax; pOutputTypes
0x1800086c2  lea     r8, pszName; "Mpeg4 Decoder DMO"
0x1800086c9  lea     rax, pInputTypes
0x1800086d0  mov     [rsp+300h+cOutTypes], 9; cOutputTypes
0x1800086d8  mov     qword ptr [rsp+300h+var_2D8], rax; pInputTypes
0x1800086dd  lea     rdx, [rsp+300h+phkResult]; guidCategory
0x1800086e2  xor     r9d, r9d; Flags
0x1800086e5  mov     [rsp+300h+cbData], r15d; cInputTypes
0x1800086ea  lea     rcx, [rsp+300h+hKey]; clsidMFT
0x1800086ef  movdqu  xmmword ptr [rsp+300h+phkResult], xmm0
0x1800086f5  movdqu  xmmword ptr [rsp+300h+hKey], xmm1
0x1800086fb  call    cs:__imp_MFTRegister
0x180008701  xor     ecx, ecx
0x180008703  test    eax, eax
0x180008705  cmovs   ecx, eax
0x180008708  mov     eax, ecx
0x18000870a  jmp     loc_1800084C0
0x18000870f  mov     rcx, rdi
0x180008712  jmp     short loc_18000871C
0x180008714  test    rbx, rbx
0x180008717  jz      short loc_180008721
0x180008719  mov     rcx, rbx; void *
0x18000871c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008721  mov     eax, 8007000Eh
0x180008726  jmp     loc_1800084C0
```
