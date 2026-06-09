# DllRegisterServer

- ea: `0x1800d5f50`
- end: `0x1800d63ca`
- name: `DllRegisterServer`
- size: `1146`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180093588`
- `0x1800c1cf0`
- `0x1800c1cfc`
- `0x1800c2100`
- `0x1800d4758`
- `0x1800d5f50`
- `0x180196250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d5fd0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d5fd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d601b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d601b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d611a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d611a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d60e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d612b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d60e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d612b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d606d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d60d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d606d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d60d3`
- `MFPlat!MFTRegister` at `0x1800d61da`
- `MFPlat!MFTRegister` at `0x1800d627e`
- `MFPlat!MFTRegister` at `0x1800d6380`
- `MFPlat!MFTRegister` at `0x1800d61da`
- `MFPlat!MFTRegister` at `0x1800d627e`
- `MFPlat!MFTRegister` at `0x1800d6380`

## string_xrefs

- `0x1800d60fb`: `PreferredMPEG2VideoDecoderCLSID`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const WCHAR *v0; // rsi
  OLECHAR *v1; // rax
  const BYTE *v2; // rdi
  LSTATUS Key; // ebx
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  CLSID clsidMFT; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v8[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID guidCategory; // [rsp+80h] [rbp-80h] BYREF
  MFT_REGISTER_TYPE_INFO pInputTypes; // [rsp+90h] [rbp-70h] BYREF
  __int128 v11; // [rsp+B0h] [rbp-50h]
  __int128 v12; // [rsp+C0h] [rbp-40h]
  MFT_REGISTER_TYPE_INFO pOutputTypes; // [rsp+D0h] [rbp-30h] BYREF
  MFT_REGISTER_TYPE_INFO v14; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v15; // [rsp+110h] [rbp+10h]
  __int128 v16; // [rsp+120h] [rbp+20h]
  __int128 v17; // [rsp+130h] [rbp+30h]
  __int128 v18; // [rsp+140h] [rbp+40h]
  __int128 v19; // [rsp+150h] [rbp+50h]
  __int128 v20; // [rsp+160h] [rbp+60h]
  __int128 v21; // [rsp+170h] [rbp+70h]
  __int128 v22; // [rsp+180h] [rbp+80h]

  sub_180196250(1);
  v0 = (const WCHAR *)sub_1800C1CFC(520);
  v1 = (OLECHAR *)sub_1800C1CFC(78);
  hKey = 0;
  v2 = (const BYTE *)v1;
  v8[0] = 0;
  if ( v0 )
  {
    if ( v1 )
    {
      if ( StringFromGUID2(&rguid, v1, 39) >= 0
        && (int)sub_180093588(v0, 260, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion") >= 0
        && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 4u, &hKey) )
      {
        Key = RegCreateKeyExW(hKey, L"Media Center", 0, 0, 0, 2u, 0, v8, 0);
        RegCloseKey(hKey);
        if ( !Key )
        {
          hKey = v8[0];
          v4 = RegCreateKeyExW(v8[0], L"Decoder", 0, 0, 0, 2u, 0, v8, 0);
          RegCloseKey(hKey);
          if ( !v4 )
          {
            hKey = v8[0];
            RegSetValueExW(v8[0], L"PreferredMPEG2VideoDecoderCLSID", 0, 1u, v2, 0x4Eu);
            RegCloseKey(hKey);
          }
        }
      }
    }
    j__o_free(v0);
  }
  if ( v2 )
    j__o_free(v2);
  pInputTypes.guidMajorType = *(GUID *)"vids";
  pInputTypes.guidSubtype = (GUID)xmmword_180212038;
  v11 = *(_OWORD *)"vids";
  v12 = xmmword_1802139F0;
  pOutputTypes.guidMajorType = *(GUID *)"vids";
  pOutputTypes.guidSubtype = (GUID)xmmword_1802124B8;
  guidCategory = (GUID)xmmword_180214430;
  clsidMFT = (CLSID)xmmword_180212BD0;
  MFTRegister(
    &clsidMFT,
    &guidCategory,
    (LPWSTR)L"Microsoft H264 Video Decoder MFT",
    0,
    2u,
    &pInputTypes,
    1u,
    &pOutputTypes,
    0);
  clsidMFT = (CLSID)xmmword_180212BD0;
  sub_1800D4758(&clsidMFT, L"Microsoft H264 Video Decoder MFT");
  pInputTypes.guidMajorType = *(GUID *)"vids";
  pInputTypes.guidSubtype = (GUID)xmmword_1802139F0;
  pOutputTypes.guidMajorType = *(GUID *)"vids";
  pOutputTypes.guidSubtype = (GUID)xmmword_180212038;
  clsidMFT = (CLSID)xmmword_180214410;
  guidCategory = (GUID)xmmword_180212BE0;
  MFTRegister(
    &guidCategory,
    &clsidMFT,
    (LPWSTR)L"Microsoft H264 Video Remux (MPEG2TSToMP4) MFT",
    0,
    1u,
    &pInputTypes,
    1u,
    &pOutputTypes,
    0);
  clsidMFT = (CLSID)xmmword_180212BE0;
  sub_1800D4758(&clsidMFT, L"Microsoft H264 Video Remux (MPEG2TSToMP4) MFT");
  pInputTypes.guidMajorType = *(GUID *)"vids";
  pInputTypes.guidSubtype = (GUID)xmmword_180213910;
  v11 = *(_OWORD *)"vids";
  v12 = xmmword_180213AD8;
  v14.guidMajorType = *(GUID *)"vids";
  v14.guidSubtype = (GUID)xmmword_1802124A8;
  v15 = *(_OWORD *)"vids";
  v16 = xmmword_180213BE8;
  v17 = *(_OWORD *)"vids";
  v18 = xmmword_180214308;
  v19 = *(_OWORD *)"vids";
  v20 = xmmword_180213E20;
  v21 = *(_OWORD *)"vids";
  v22 = xmmword_180212850;
  clsidMFT = (CLSID)xmmword_180214430;
  guidCategory = (GUID)xmmword_180212BF0;
  MFTRegister(&guidCategory, &clsidMFT, (LPWSTR)L"Microsoft MPEG Video Decoder MFT", 0, 2u, &pInputTypes, 5u, &v14, 0);
  clsidMFT = (CLSID)xmmword_180212BF0;
  sub_1800D4758(&clsidMFT, L"Microsoft MPEG Video Decoder MFT");
  return 0;
}

```

## disassembly

```asm
0x1800d5f50  push    rbp
0x1800d5f52  push    rbx
0x1800d5f53  push    rsi
0x1800d5f54  push    rdi
0x1800d5f55  push    r15
0x1800d5f57  lea     rbp, [rsp-0A0h]
0x1800d5f5f  sub     rsp, 1A0h
0x1800d5f66  mov     rax, cs:__security_cookie
0x1800d5f6d  xor     rax, rsp
0x1800d5f70  mov     [rbp+0C0h+var_30], rax
0x1800d5f77  mov     r15d, 1
0x1800d5f7d  mov     ecx, r15d
0x1800d5f80  call    sub_180196250
0x1800d5f85  mov     ecx, 208h
0x1800d5f8a  call    sub_1800C1CFC
0x1800d5f8f  lea     ecx, [r15+4Dh]
0x1800d5f93  mov     rsi, rax
0x1800d5f96  call    sub_1800C1CFC
0x1800d5f9b  mov     [rsp+1C0h+hKey], 0
0x1800d5fa4  mov     rdi, rax
0x1800d5fa7  mov     [rsp+1C0h+var_150], 0
0x1800d5fb0  test    rsi, rsi
0x1800d5fb3  jz      loc_1800D613F
0x1800d5fb9  test    rax, rax
0x1800d5fbc  jz      loc_1800D6137
0x1800d5fc2  lea     r8d, [r15+26h]; cchMax
0x1800d5fc6  mov     rdx, rax; lpsz
0x1800d5fc9  lea     rcx, rguid; rguid
0x1800d5fd0  call    cs:StringFromGUID2
0x1800d5fd7  nop     dword ptr [rax+rax+00h]
0x1800d5fdc  test    eax, eax
0x1800d5fde  js      loc_1800D6137
0x1800d5fe4  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d5feb  mov     edx, 104h
0x1800d5ff0  mov     rcx, rsi
0x1800d5ff3  call    sub_180093588
0x1800d5ff8  test    eax, eax
0x1800d5ffa  js      loc_1800D6137
0x1800d6000  lea     rax, [rsp+1C0h+hKey]
0x1800d6005  xor     r8d, r8d; ulOptions
0x1800d6008  lea     r9d, [r15+3]; samDesired
0x1800d600c  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d6011  mov     rdx, rsi; lpSubKey
0x1800d6014  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d601b  call    cs:RegOpenKeyExW
0x1800d6022  nop     dword ptr [rax+rax+00h]
0x1800d6027  test    eax, eax
0x1800d6029  jnz     loc_1800D6137
0x1800d602f  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d6034  lea     rax, [rsp+1C0h+var_150]
0x1800d6039  mov     [rsp+1C0h+lpdwDisposition], 0; lpdwDisposition
0x1800d6042  lea     rdx, aMediaCenter; "Media Center"
0x1800d6049  mov     [rsp+1C0h+var_188], rax; phkResult
0x1800d604e  xor     r9d, r9d; lpClass
0x1800d6051  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d605a  xor     r8d, r8d; Reserved
0x1800d605d  mov     [rsp+1C0h+samDesired], 2; samDesired
0x1800d6065  mov     dword ptr [rsp+1C0h+phkResult], 0; dwOptions
0x1800d606d  call    cs:RegCreateKeyExW
0x1800d6074  nop     dword ptr [rax+rax+00h]
0x1800d6079  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d607e  mov     ebx, eax
0x1800d6080  call    cs:RegCloseKey
0x1800d6087  nop     dword ptr [rax+rax+00h]
0x1800d608c  test    ebx, ebx
0x1800d608e  jnz     loc_1800D6137
0x1800d6094  mov     rcx, [rsp+1C0h+var_150]; hKey
0x1800d6099  lea     rax, [rsp+1C0h+var_150]
0x1800d609e  mov     [rsp+1C0h+lpdwDisposition], 0; lpdwDisposition
0x1800d60a7  lea     rdx, aDecoder; "Decoder"
0x1800d60ae  mov     [rsp+1C0h+var_188], rax; phkResult
0x1800d60b3  xor     r9d, r9d; lpClass
0x1800d60b6  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d60bf  xor     r8d, r8d; Reserved
0x1800d60c2  mov     [rsp+1C0h+samDesired], 2; samDesired
0x1800d60ca  mov     dword ptr [rsp+1C0h+phkResult], ebx; dwOptions
0x1800d60ce  mov     [rsp+1C0h+hKey], rcx
0x1800d60d3  call    cs:RegCreateKeyExW
0x1800d60da  nop     dword ptr [rax+rax+00h]
0x1800d60df  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d60e4  mov     ebx, eax
0x1800d60e6  call    cs:RegCloseKey
0x1800d60ed  nop     dword ptr [rax+rax+00h]
0x1800d60f2  test    ebx, ebx
0x1800d60f4  jnz     short loc_1800D6137
0x1800d60f6  mov     rcx, [rsp+1C0h+var_150]; hKey
0x1800d60fb  lea     rdx, aPreferredmpeg2; "PreferredMPEG2VideoDecoderCLSID"
0x1800d6102  mov     [rsp+1C0h+samDesired], 4Eh ; 'N'; cbData
0x1800d610a  mov     r9d, r15d; dwType
0x1800d610d  xor     r8d, r8d; Reserved
0x1800d6110  mov     [rsp+1C0h+hKey], rcx
0x1800d6115  mov     [rsp+1C0h+phkResult], rdi; lpData
0x1800d611a  call    cs:RegSetValueExW
0x1800d6121  nop     dword ptr [rax+rax+00h]
0x1800d6126  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d612b  call    cs:RegCloseKey
0x1800d6132  nop     dword ptr [rax+rax+00h]
0x1800d6137  mov     rcx, rsi
0x1800d613a  call    j__o_free
0x1800d613f  test    rdi, rdi
0x1800d6142  jz      short loc_1800D614C
0x1800d6144  mov     rcx, rdi
0x1800d6147  call    j__o_free
0x1800d614c  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d6153  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d615c  lea     rax, [rbp+0C0h+pOutputTypes]
0x1800d6160  movups  xmm0, cs:xmmword_180212038
0x1800d6167  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d616c  lea     r8, pszName; "Microsoft H264 Video Decoder MFT"
0x1800d6173  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d6178  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d617c  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], r15d; cOutputTypes
0x1800d6181  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d6186  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d618b  xor     r9d, r9d; Flags
0x1800d618e  movups  xmm0, cs:xmmword_1802139F0
0x1800d6195  lea     rdx, [rbp+0C0h+guidCategory]; guidCategory
0x1800d6199  mov     dword ptr [rsp+1C0h+phkResult], 2; cInputTypes
0x1800d61a1  movdqu  [rbp+0C0h+var_110], xmm1
0x1800d61a6  lea     rcx, [rsp+1C0h+clsidMFT]; clsidMFT
0x1800d61ab  movdqu  [rbp+0C0h+var_100], xmm0
0x1800d61b0  movups  xmm0, cs:xmmword_1802124B8
0x1800d61b7  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidMajorType.Data1], xmm1
0x1800d61bc  movups  xmm1, cs:xmmword_180214430
0x1800d61c3  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidSubtype.Data1], xmm0
0x1800d61c8  movups  xmm0, cs:xmmword_180212BD0
0x1800d61cf  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm1
0x1800d61d4  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d61da  call    cs:MFTRegister
0x1800d61e1  nop     dword ptr [rax+rax+00h]
0x1800d61e6  movups  xmm0, cs:xmmword_180212BD0
0x1800d61ed  lea     rdx, pszName; "Microsoft H264 Video Decoder MFT"
0x1800d61f4  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d61f9  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d61ff  call    sub_1800D4758
0x1800d6204  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d620b  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d6214  lea     rax, [rbp+0C0h+pOutputTypes]
0x1800d6218  movups  xmm0, cs:xmmword_1802139F0
0x1800d621f  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d6224  lea     r8, aMicrosoftH264V_0; "Microsoft H264 Video Remux (MPEG2TSToMP"...
0x1800d622b  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d6230  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d6234  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], r15d; cOutputTypes
0x1800d6239  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d623e  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d6243  xor     r9d, r9d; Flags
0x1800d6246  movups  xmm0, cs:xmmword_180212038
0x1800d624d  lea     rdx, [rsp+1C0h+clsidMFT]; guidCategory
0x1800d6252  mov     dword ptr [rsp+1C0h+phkResult], r15d; cInputTypes
0x1800d6257  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidMajorType.Data1], xmm1
0x1800d625c  lea     rcx, [rbp+0C0h+guidCategory]; clsidMFT
0x1800d6260  movups  xmm1, cs:xmmword_180214410
0x1800d6267  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidSubtype.Data1], xmm0
0x1800d626c  movups  xmm0, cs:xmmword_180212BE0
0x1800d6273  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm1
0x1800d6279  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm0
0x1800d627e  call    cs:MFTRegister
0x1800d6285  nop     dword ptr [rax+rax+00h]
0x1800d628a  movups  xmm0, cs:xmmword_180212BE0
0x1800d6291  lea     rdx, aMicrosoftH264V_0; "Microsoft H264 Video Remux (MPEG2TSToMP"...
0x1800d6298  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d629d  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d62a3  call    sub_1800D4758
0x1800d62a8  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d62af  movups  xmm0, cs:xmmword_180213910
0x1800d62b6  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d62bb  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d62c0  movups  xmm0, cs:xmmword_180213AD8
0x1800d62c7  movdqu  [rbp+0C0h+var_110], xmm1
0x1800d62cc  movdqu  [rbp+0C0h+var_100], xmm0
0x1800d62d1  movups  xmm0, cs:xmmword_1802124A8
0x1800d62d8  movdqu  xmmword ptr [rbp+0C0h+var_D0.guidMajorType.Data1], xmm1
0x1800d62dd  movdqu  xmmword ptr [rbp+0C0h+var_D0.guidSubtype.Data1], xmm0
0x1800d62e2  movups  xmm0, cs:xmmword_180213BE8
0x1800d62e9  movdqu  [rbp+0C0h+var_B0], xmm1
0x1800d62ee  movdqu  [rbp+0C0h+var_A0], xmm0
0x1800d62f3  movups  xmm0, cs:xmmword_180214308
0x1800d62fa  movdqu  [rbp+0C0h+var_90], xmm1
0x1800d62ff  movdqu  [rbp+0C0h+var_80], xmm0
0x1800d6304  movups  xmm0, cs:xmmword_180213E20
0x1800d630b  movdqu  [rbp+0C0h+var_70], xmm1
0x1800d6310  movdqu  [rbp+0C0h+var_60], xmm0
0x1800d6315  movups  xmm0, cs:xmmword_180212850
0x1800d631c  movdqu  [rbp+0C0h+var_50], xmm1
0x1800d6321  movdqu  [rbp+0C0h+var_40], xmm0
0x1800d6329  movups  xmm1, cs:xmmword_180214430
0x1800d6330  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d6339  lea     rax, [rbp+0C0h+var_D0]
0x1800d633d  movups  xmm0, cs:xmmword_180212BF0
0x1800d6344  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d6349  lea     r8, aMicrosoftMpegV; "Microsoft MPEG Video Decoder MFT"
0x1800d6350  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d6354  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], 5; cOutputTypes
0x1800d635c  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d6361  lea     rdx, [rsp+1C0h+clsidMFT]; guidCategory
0x1800d6366  xor     r9d, r9d; Flags
0x1800d6369  mov     dword ptr [rsp+1C0h+phkResult], 2; cInputTypes
0x1800d6371  lea     rcx, [rbp+0C0h+guidCategory]; clsidMFT
0x1800d6375  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm1
0x1800d637b  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm0
0x1800d6380  call    cs:MFTRegister
0x1800d6387  nop     dword ptr [rax+rax+00h]
0x1800d638c  movups  xmm0, cs:xmmword_180212BF0
0x1800d6393  lea     rdx, aMicrosoftMpegV; "Microsoft MPEG Video Decoder MFT"
0x1800d639a  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d639f  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d63a5  call    sub_1800D4758
0x1800d63aa  xor     eax, eax
0x1800d63ac  mov     rcx, [rbp+0C0h+var_30]
0x1800d63b3  xor     rcx, rsp; StackCookie
0x1800d63b6  call    __security_check_cookie
0x1800d63bb  add     rsp, 1A0h
0x1800d63c2  pop     r15
0x1800d63c4  pop     rdi
0x1800d63c5  pop     rsi
0x1800d63c6  pop     rbx
0x1800d63c7  pop     rbp
0x1800d63c8  retn
```
