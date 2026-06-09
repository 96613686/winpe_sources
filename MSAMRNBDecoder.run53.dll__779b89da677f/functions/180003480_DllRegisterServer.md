# DllRegisterServer

- ea: `0x180003480`
- end: `0x1800036bf`
- name: `DllRegisterServer`
- size: `575`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001400`
- `0x180003480`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800034f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800034f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003611`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003611`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000362b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000362b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800035c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800035c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003509`
- `MFPlat!MFTRegister` at `0x180003695`
- `MFPlat!MFTRegister` at `0x180003695`

## string_xrefs

- `0x180003533`: `Software\Classes\CLSID\{265011AE-5481-4f77-A295-ABB6FFE8D63E}`
- `0x180003544`: `Software\Classes\CLSID\{265011AE-5481-4f77-A295-ABB6FFE8D63E}\InProcServer32`
- `0x18000355b`: `ThreadingModel`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  signed int LastError; // eax
  HRESULT v1; // ebx
  int v2; // r14d
  LSTATUS Key; // eax
  const BYTE *v4; // rcx
  __int64 v5; // rax
  LSTATUS v6; // eax
  HKEY phkResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h]
  LPCWSTR lpValueName; // [rsp+70h] [rbp-90h]
  BYTE *lpData[9]; // [rsp+78h] [rbp-88h]
  CLSID clsidMFT; // [rsp+C0h] [rbp-40h] BYREF
  MFT_REGISTER_TYPE_INFO pOutputTypes; // [rsp+D0h] [rbp-30h] BYREF
  MFT_REGISTER_TYPE_INFO pInputTypes; // [rsp+F0h] [rbp-10h] BYREF
  GUID v16; // [rsp+110h] [rbp+10h]
  __int128 v17; // [rsp+120h] [rbp+20h]
  WCHAR Filename[264]; // [rsp+130h] [rbp+30h] BYREF

  pInputTypes.guidMajorType = MFMediaType_Audio;
  pInputTypes.guidSubtype = MFAudioFormat_AMR_NB;
  v16 = MFMediaType_Audio;
  v17 = MFMPEG4Format_SAMR;
  pOutputTypes.guidMajorType = MFMediaType_Audio;
  pOutputTypes.guidSubtype = MFAudioFormat_PCM;
  if ( GetModuleFileNameW(g_hModule, Filename, 0x104u) )
  {
    lpValueName = 0;
    hKey = HKEY_LOCAL_MACHINE;
    lpSubKey = L"Software\\Classes\\CLSID\\{265011AE-5481-4f77-A295-ABB6FFE8D63E}";
    lpData[0] = (BYTE *)L"MS AMRNB Decoder MFT";
    lpData[4] = (BYTE *)Filename;
    v2 = 0;
    lpData[1] = (BYTE *)-2147483646LL;
    lpData[7] = (BYTE *)L"ThreadingModel";
    lpData[8] = (BYTE *)L"Both";
    lpData[2] = (BYTE *)L"Software\\Classes\\CLSID\\{265011AE-5481-4f77-A295-ABB6FFE8D63E}\\InProcServer32";
    lpData[3] = 0;
    lpData[5] = (BYTE *)-2147483646LL;
    lpData[6] = (BYTE *)L"Software\\Classes\\CLSID\\{265011AE-5481-4f77-A295-ABB6FFE8D63E}\\InProcServer32";
    while ( 1 )
    {
      phkResult[0] = 0;
      Key = RegCreateKeyExW(*(&hKey + 4 * v2), (&lpSubKey)[4 * v2], 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      v1 = Key;
      if ( Key )
      {
        if ( Key > 0 )
          v1 = (unsigned __int16)Key | 0x80070000;
      }
      else
      {
        v4 = lpData[4 * v2];
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v4[2 * v5] );
        v6 = RegSetValueExW(phkResult[0], (LPCWSTR)lpData[4 * v2 - 1], 0, 1u, v4, 2 * v5 + 2);
        v1 = v6;
        if ( v6 > 0 )
          v1 = (unsigned __int16)v6 | 0x80070000;
        RegCloseKey(phkResult[0]);
      }
      if ( v1 < 0 )
        break;
      if ( (unsigned int)++v2 >= 3 )
        goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
    if ( v1 >= 0 )
    {
      *(GUID *)phkResult = MFT_CATEGORY_AUDIO_DECODER;
      clsidMFT = CLSID_MSAMRNBDecoder;
      return MFTRegister(
               &clsidMFT,
               (GUID *)phkResult,
               (LPWSTR)L"MS AMRNB Decoder MFT",
               0,
               2u,
               &pInputTypes,
               1u,
               &pOutputTypes,
               0);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180003480  push    rbp
0x180003482  push    rbx
0x180003483  push    rdi
0x180003484  push    r13
0x180003486  push    r14
0x180003488  push    r15
0x18000348a  lea     rbp, [rsp-258h]
0x180003492  sub     rsp, 358h
0x180003499  mov     rax, cs:__security_cookie
0x1800034a0  xor     rax, rsp
0x1800034a3  mov     [rbp+280h+var_40], rax
0x1800034aa  movups  xmm1, xmmword ptr cs:MFMediaType_Audio.Data1
0x1800034b1  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800034b8  mov     r8d, 104h; nSize
0x1800034be  movups  xmm0, xmmword ptr cs:MFAudioFormat_AMR_NB.Data1
0x1800034c5  lea     rdx, [rbp+280h+Filename]; lpFilename
0x1800034c9  movdqu  xmmword ptr [rbp+280h+pInputTypes.guidMajorType.Data1], xmm1
0x1800034ce  movdqu  xmmword ptr [rbp+280h+pInputTypes.guidSubtype.Data1], xmm0
0x1800034d3  movups  xmm0, cs:MFMPEG4Format_SAMR
0x1800034da  movdqu  [rbp+280h+var_270], xmm1
0x1800034df  movdqu  [rbp+280h+var_260], xmm0
0x1800034e4  movups  xmm0, xmmword ptr cs:MFAudioFormat_PCM.Data1
0x1800034eb  movdqu  xmmword ptr [rbp+280h+pOutputTypes.guidMajorType.Data1], xmm1
0x1800034f0  movdqu  xmmword ptr [rbp+280h+pOutputTypes.guidSubtype.Data1], xmm0
0x1800034f5  call    cs:__imp_GetModuleFileNameW
0x1800034fb  xor     r15d, r15d
0x1800034fe  lea     r13, pszName; "MS AMRNB Decoder MFT"
0x180003505  test    eax, eax
0x180003507  jnz     short loc_180003527
0x180003509  call    cs:__imp_GetLastError
0x18000350f  mov     ebx, eax
0x180003511  test    eax, eax
0x180003513  jle     loc_180003642
0x180003519  movzx   ebx, ax
0x18000351c  or      ebx, 80070000h
0x180003522  jmp     loc_180003642
0x180003527  mov     rdx, 0FFFFFFFF80000002h
0x18000352e  mov     [rsp+380h+lpValueName], r15
0x180003533  lea     rax, SubKey; "Software\\Classes\\CLSID\\{265011AE-548"...
0x18000353a  mov     [rsp+380h+hKey], rdx
0x18000353f  mov     [rsp+380h+lpSubKey], rax
0x180003544  lea     rcx, aSoftwareClasse_0; "Software\\Classes\\CLSID\\{265011AE-548"...
0x18000354b  lea     rax, [rbp+280h+Filename]
0x18000354f  mov     [rsp+380h+lpData], r13
0x180003554  mov     [rbp+280h+var_2E8], rax
0x180003558  mov     r14d, r15d
0x18000355b  lea     rax, aThreadingmodel; "ThreadingModel"
0x180003562  mov     [rbp+280h+var_300], rdx
0x180003566  mov     [rbp+280h+var_2D0], rax
0x18000356a  lea     rax, aBoth; "Both"
0x180003571  mov     [rbp+280h+var_2C8], rax
0x180003575  mov     [rbp+280h+var_2F8], rcx
0x180003579  mov     [rbp+280h+var_2F0], r15
0x18000357d  mov     [rbp+280h+var_2E0], rdx
0x180003581  mov     [rbp+280h+var_2D8], rcx
0x180003585  mov     [rsp+380h+lpdwDisposition], r15; lpdwDisposition
0x18000358a  lea     rax, [rsp+380h+var_330]
0x18000358f  mov     [rsp+380h+phkResult], rax; phkResult
0x180003594  xor     r9d, r9d; lpClass
0x180003597  mov     [rsp+380h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000359c  xor     r8d, r8d; Reserved
0x18000359f  movsxd  rdi, r14d
0x1800035a2  shl     rdi, 5
0x1800035a6  mov     [rsp+380h+samDesired], 0F003Fh; samDesired
0x1800035ae  mov     [rsp+380h+var_330], r15
0x1800035b3  mov     [rsp+380h+dwOptions], r15d; dwOptions
0x1800035b8  mov     rdx, [rsp+rdi+380h+lpSubKey]; lpSubKey
0x1800035bd  mov     rcx, [rsp+rdi+380h+hKey]; hKey
0x1800035c2  call    cs:__imp_RegCreateKeyExW
0x1800035c8  mov     ebx, eax
0x1800035ca  test    eax, eax
0x1800035cc  jz      short loc_1800035DB
0x1800035ce  jle     short loc_180003631
0x1800035d0  movzx   ebx, ax
0x1800035d3  or      ebx, 80070000h
0x1800035d9  jmp     short loc_180003631
0x1800035db  mov     rcx, [rsp+rdi+380h+lpData]
0x1800035e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035e4  inc     rax
0x1800035e7  cmp     [rcx+rax*2], r15w
0x1800035ec  jnz     short loc_1800035E4
0x1800035ee  mov     rdx, [rsp+rdi+380h+lpValueName]; lpValueName
0x1800035f3  lea     eax, ds:2[rax*2]
0x1800035fa  mov     [rsp+380h+samDesired], eax; cbData
0x1800035fe  mov     r9d, 1; dwType
0x180003604  mov     qword ptr [rsp+380h+dwOptions], rcx; lpData
0x180003609  xor     r8d, r8d; Reserved
0x18000360c  mov     rcx, [rsp+380h+var_330]; hKey
0x180003611  call    cs:__imp_RegSetValueExW
0x180003617  mov     ebx, eax
0x180003619  test    eax, eax
0x18000361b  jle     short loc_180003626
0x18000361d  movzx   ebx, ax
0x180003620  or      ebx, 80070000h
0x180003626  mov     rcx, [rsp+380h+var_330]; hKey
0x18000362b  call    cs:__imp_RegCloseKey
0x180003631  test    ebx, ebx
0x180003633  js      short loc_18000369D
0x180003635  inc     r14d
0x180003638  cmp     r14d, 3
0x18000363c  jb      loc_180003585
0x180003642  test    ebx, ebx
0x180003644  js      short loc_18000369D
0x180003646  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x18000364d  mov     [rsp+380h+lpdwDisposition], r15; pAttributes
0x180003652  lea     rax, [rbp+280h+pOutputTypes]
0x180003656  movups  xmm1, xmmword ptr cs:CLSID_MSAMRNBDecoder.Data1
0x18000365d  mov     [rsp+380h+phkResult], rax; pOutputTypes
0x180003662  lea     rdx, [rsp+380h+var_330]; guidCategory
0x180003667  lea     rax, [rbp+280h+pInputTypes]
0x18000366b  mov     dword ptr [rsp+380h+lpSecurityAttributes], 1; cOutputTypes
0x180003673  mov     qword ptr [rsp+380h+samDesired], rax; pInputTypes
0x180003678  lea     rcx, [rbp+280h+clsidMFT]; clsidMFT
0x18000367c  xor     r9d, r9d; Flags
0x18000367f  mov     [rsp+380h+dwOptions], 2; cInputTypes
0x180003687  mov     r8, r13; pszName
0x18000368a  movdqu  xmmword ptr [rsp+380h+var_330], xmm0
0x180003690  movdqu  xmmword ptr [rbp+280h+clsidMFT.Data1], xmm1
0x180003695  call    cs:__imp_MFTRegister
0x18000369b  mov     ebx, eax
0x18000369d  mov     eax, ebx
0x18000369f  mov     rcx, [rbp+280h+var_40]
0x1800036a6  xor     rcx, rsp; StackCookie
0x1800036a9  call    __security_check_cookie
0x1800036ae  add     rsp, 358h
0x1800036b5  pop     r15
0x1800036b7  pop     r14
0x1800036b9  pop     r13
0x1800036bb  pop     rdi
0x1800036bc  pop     rbx
0x1800036bd  pop     rbp
0x1800036be  retn
```
