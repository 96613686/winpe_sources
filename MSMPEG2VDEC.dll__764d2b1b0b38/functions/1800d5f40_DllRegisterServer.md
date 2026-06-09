# DllRegisterServer

- ea: `0x1800d5f40`
- end: `0x1800d63ba`
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
- `0x1800d4748`
- `0x1800d5f40`
- `0x180196260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d5fc0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d5fc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d600b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d600b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d610a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d610a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d60d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d611b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d60d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d611b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d605d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d60c3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d605d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d60c3`
- `MFPlat!MFTRegister` at `0x1800d61ca`
- `MFPlat!MFTRegister` at `0x1800d626e`
- `MFPlat!MFTRegister` at `0x1800d6370`
- `MFPlat!MFTRegister` at `0x1800d61ca`
- `MFPlat!MFTRegister` at `0x1800d626e`
- `MFPlat!MFTRegister` at `0x1800d6370`

## string_xrefs

- `0x1800d60eb`: `PreferredMPEG2VideoDecoderCLSID`

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

  sub_180196260(1);
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
  v12 = xmmword_1802139E0;
  pOutputTypes.guidMajorType = *(GUID *)"vids";
  pOutputTypes.guidSubtype = (GUID)xmmword_1802124B8;
  guidCategory = (GUID)xmmword_180214420;
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
  sub_1800D4748(&clsidMFT, L"Microsoft H264 Video Decoder MFT");
  pInputTypes.guidMajorType = *(GUID *)"vids";
  pInputTypes.guidSubtype = (GUID)xmmword_1802139E0;
  pOutputTypes.guidMajorType = *(GUID *)"vids";
  pOutputTypes.guidSubtype = (GUID)xmmword_180212038;
  clsidMFT = (CLSID)xmmword_180214400;
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
  sub_1800D4748(&clsidMFT, L"Microsoft H264 Video Remux (MPEG2TSToMP4) MFT");
  pInputTypes.guidMajorType = *(GUID *)"vids";
  pInputTypes.guidSubtype = (GUID)xmmword_180213900;
  v11 = *(_OWORD *)"vids";
  v12 = xmmword_180213AC8;
  v14.guidMajorType = *(GUID *)"vids";
  v14.guidSubtype = (GUID)xmmword_1802124A8;
  v15 = *(_OWORD *)"vids";
  v16 = xmmword_180213BD8;
  v17 = *(_OWORD *)"vids";
  v18 = xmmword_1802142F8;
  v19 = *(_OWORD *)"vids";
  v20 = xmmword_180213E10;
  v21 = *(_OWORD *)"vids";
  v22 = xmmword_180212850;
  clsidMFT = (CLSID)xmmword_180214420;
  guidCategory = (GUID)xmmword_180212BF0;
  MFTRegister(&guidCategory, &clsidMFT, (LPWSTR)L"Microsoft MPEG Video Decoder MFT", 0, 2u, &pInputTypes, 5u, &v14, 0);
  clsidMFT = (CLSID)xmmword_180212BF0;
  sub_1800D4748(&clsidMFT, L"Microsoft MPEG Video Decoder MFT");
  return 0;
}

```

## disassembly

```asm
0x1800d5f40  push    rbp
0x1800d5f42  push    rbx
0x1800d5f43  push    rsi
0x1800d5f44  push    rdi
0x1800d5f45  push    r15
0x1800d5f47  lea     rbp, [rsp-0A0h]
0x1800d5f4f  sub     rsp, 1A0h
0x1800d5f56  mov     rax, cs:__security_cookie
0x1800d5f5d  xor     rax, rsp
0x1800d5f60  mov     [rbp+0C0h+var_30], rax
0x1800d5f67  mov     r15d, 1
0x1800d5f6d  mov     ecx, r15d
0x1800d5f70  call    sub_180196260
0x1800d5f75  mov     ecx, 208h
0x1800d5f7a  call    sub_1800C1CFC
0x1800d5f7f  lea     ecx, [r15+4Dh]
0x1800d5f83  mov     rsi, rax
0x1800d5f86  call    sub_1800C1CFC
0x1800d5f8b  mov     [rsp+1C0h+hKey], 0
0x1800d5f94  mov     rdi, rax
0x1800d5f97  mov     [rsp+1C0h+var_150], 0
0x1800d5fa0  test    rsi, rsi
0x1800d5fa3  jz      loc_1800D612F
0x1800d5fa9  test    rax, rax
0x1800d5fac  jz      loc_1800D6127
0x1800d5fb2  lea     r8d, [r15+26h]; cchMax
0x1800d5fb6  mov     rdx, rax; lpsz
0x1800d5fb9  lea     rcx, rguid; rguid
0x1800d5fc0  call    cs:StringFromGUID2
0x1800d5fc7  nop     dword ptr [rax+rax+00h]
0x1800d5fcc  test    eax, eax
0x1800d5fce  js      loc_1800D6127
0x1800d5fd4  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d5fdb  mov     edx, 104h
0x1800d5fe0  mov     rcx, rsi
0x1800d5fe3  call    sub_180093588
0x1800d5fe8  test    eax, eax
0x1800d5fea  js      loc_1800D6127
0x1800d5ff0  lea     rax, [rsp+1C0h+hKey]
0x1800d5ff5  xor     r8d, r8d; ulOptions
0x1800d5ff8  lea     r9d, [r15+3]; samDesired
0x1800d5ffc  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d6001  mov     rdx, rsi; lpSubKey
0x1800d6004  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d600b  call    cs:RegOpenKeyExW
0x1800d6012  nop     dword ptr [rax+rax+00h]
0x1800d6017  test    eax, eax
0x1800d6019  jnz     loc_1800D6127
0x1800d601f  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d6024  lea     rax, [rsp+1C0h+var_150]
0x1800d6029  mov     [rsp+1C0h+lpdwDisposition], 0; lpdwDisposition
0x1800d6032  lea     rdx, aMediaCenter; "Media Center"
0x1800d6039  mov     [rsp+1C0h+var_188], rax; phkResult
0x1800d603e  xor     r9d, r9d; lpClass
0x1800d6041  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d604a  xor     r8d, r8d; Reserved
0x1800d604d  mov     [rsp+1C0h+samDesired], 2; samDesired
0x1800d6055  mov     dword ptr [rsp+1C0h+phkResult], 0; dwOptions
0x1800d605d  call    cs:RegCreateKeyExW
0x1800d6064  nop     dword ptr [rax+rax+00h]
0x1800d6069  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d606e  mov     ebx, eax
0x1800d6070  call    cs:RegCloseKey
0x1800d6077  nop     dword ptr [rax+rax+00h]
0x1800d607c  test    ebx, ebx
0x1800d607e  jnz     loc_1800D6127
0x1800d6084  mov     rcx, [rsp+1C0h+var_150]; hKey
0x1800d6089  lea     rax, [rsp+1C0h+var_150]
0x1800d608e  mov     [rsp+1C0h+lpdwDisposition], 0; lpdwDisposition
0x1800d6097  lea     rdx, aDecoder; "Decoder"
0x1800d609e  mov     [rsp+1C0h+var_188], rax; phkResult
0x1800d60a3  xor     r9d, r9d; lpClass
0x1800d60a6  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d60af  xor     r8d, r8d; Reserved
0x1800d60b2  mov     [rsp+1C0h+samDesired], 2; samDesired
0x1800d60ba  mov     dword ptr [rsp+1C0h+phkResult], ebx; dwOptions
0x1800d60be  mov     [rsp+1C0h+hKey], rcx
0x1800d60c3  call    cs:RegCreateKeyExW
0x1800d60ca  nop     dword ptr [rax+rax+00h]
0x1800d60cf  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d60d4  mov     ebx, eax
0x1800d60d6  call    cs:RegCloseKey
0x1800d60dd  nop     dword ptr [rax+rax+00h]
0x1800d60e2  test    ebx, ebx
0x1800d60e4  jnz     short loc_1800D6127
0x1800d60e6  mov     rcx, [rsp+1C0h+var_150]; hKey
0x1800d60eb  lea     rdx, aPreferredmpeg2; "PreferredMPEG2VideoDecoderCLSID"
0x1800d60f2  mov     [rsp+1C0h+samDesired], 4Eh ; 'N'; cbData
0x1800d60fa  mov     r9d, r15d; dwType
0x1800d60fd  xor     r8d, r8d; Reserved
0x1800d6100  mov     [rsp+1C0h+hKey], rcx
0x1800d6105  mov     [rsp+1C0h+phkResult], rdi; lpData
0x1800d610a  call    cs:RegSetValueExW
0x1800d6111  nop     dword ptr [rax+rax+00h]
0x1800d6116  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d611b  call    cs:RegCloseKey
0x1800d6122  nop     dword ptr [rax+rax+00h]
0x1800d6127  mov     rcx, rsi
0x1800d612a  call    j__o_free
0x1800d612f  test    rdi, rdi
0x1800d6132  jz      short loc_1800D613C
0x1800d6134  mov     rcx, rdi
0x1800d6137  call    j__o_free
0x1800d613c  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d6143  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d614c  lea     rax, [rbp+0C0h+pOutputTypes]
0x1800d6150  movups  xmm0, cs:xmmword_180212038
0x1800d6157  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d615c  lea     r8, pszName; "Microsoft H264 Video Decoder MFT"
0x1800d6163  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d6168  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d616c  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], r15d; cOutputTypes
0x1800d6171  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d6176  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d617b  xor     r9d, r9d; Flags
0x1800d617e  movups  xmm0, cs:xmmword_1802139E0
0x1800d6185  lea     rdx, [rbp+0C0h+guidCategory]; guidCategory
0x1800d6189  mov     dword ptr [rsp+1C0h+phkResult], 2; cInputTypes
0x1800d6191  movdqu  [rbp+0C0h+var_110], xmm1
0x1800d6196  lea     rcx, [rsp+1C0h+clsidMFT]; clsidMFT
0x1800d619b  movdqu  [rbp+0C0h+var_100], xmm0
0x1800d61a0  movups  xmm0, cs:xmmword_1802124B8
0x1800d61a7  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidMajorType.Data1], xmm1
0x1800d61ac  movups  xmm1, cs:xmmword_180214420
0x1800d61b3  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidSubtype.Data1], xmm0
0x1800d61b8  movups  xmm0, cs:xmmword_180212BD0
0x1800d61bf  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm1
0x1800d61c4  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d61ca  call    cs:MFTRegister
0x1800d61d1  nop     dword ptr [rax+rax+00h]
0x1800d61d6  movups  xmm0, cs:xmmword_180212BD0
0x1800d61dd  lea     rdx, pszName; "Microsoft H264 Video Decoder MFT"
0x1800d61e4  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d61e9  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d61ef  call    sub_1800D4748
0x1800d61f4  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d61fb  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d6204  lea     rax, [rbp+0C0h+pOutputTypes]
0x1800d6208  movups  xmm0, cs:xmmword_1802139E0
0x1800d620f  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d6214  lea     r8, aMicrosoftH264V_0; "Microsoft H264 Video Remux (MPEG2TSToMP"...
0x1800d621b  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d6220  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d6224  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], r15d; cOutputTypes
0x1800d6229  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d622e  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d6233  xor     r9d, r9d; Flags
0x1800d6236  movups  xmm0, cs:xmmword_180212038
0x1800d623d  lea     rdx, [rsp+1C0h+clsidMFT]; guidCategory
0x1800d6242  mov     dword ptr [rsp+1C0h+phkResult], r15d; cInputTypes
0x1800d6247  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidMajorType.Data1], xmm1
0x1800d624c  lea     rcx, [rbp+0C0h+guidCategory]; clsidMFT
0x1800d6250  movups  xmm1, cs:xmmword_180214400
0x1800d6257  movdqu  xmmword ptr [rbp+0C0h+pOutputTypes.guidSubtype.Data1], xmm0
0x1800d625c  movups  xmm0, cs:xmmword_180212BE0
0x1800d6263  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm1
0x1800d6269  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm0
0x1800d626e  call    cs:MFTRegister
0x1800d6275  nop     dword ptr [rax+rax+00h]
0x1800d627a  movups  xmm0, cs:xmmword_180212BE0
0x1800d6281  lea     rdx, aMicrosoftH264V_0; "Microsoft H264 Video Remux (MPEG2TSToMP"...
0x1800d6288  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d628d  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d6293  call    sub_1800D4748
0x1800d6298  movups  xmm1, xmmword ptr cs:aVids; "vids"
0x1800d629f  movups  xmm0, cs:xmmword_180213900
0x1800d62a6  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidMajorType.Data1], xmm1
0x1800d62ab  movdqu  xmmword ptr [rbp+0C0h+pInputTypes.guidSubtype.Data1], xmm0
0x1800d62b0  movups  xmm0, cs:xmmword_180213AC8
0x1800d62b7  movdqu  [rbp+0C0h+var_110], xmm1
0x1800d62bc  movdqu  [rbp+0C0h+var_100], xmm0
0x1800d62c1  movups  xmm0, cs:xmmword_1802124A8
0x1800d62c8  movdqu  xmmword ptr [rbp+0C0h+var_D0.guidMajorType.Data1], xmm1
0x1800d62cd  movdqu  xmmword ptr [rbp+0C0h+var_D0.guidSubtype.Data1], xmm0
0x1800d62d2  movups  xmm0, cs:xmmword_180213BD8
0x1800d62d9  movdqu  [rbp+0C0h+var_B0], xmm1
0x1800d62de  movdqu  [rbp+0C0h+var_A0], xmm0
0x1800d62e3  movups  xmm0, cs:xmmword_1802142F8
0x1800d62ea  movdqu  [rbp+0C0h+var_90], xmm1
0x1800d62ef  movdqu  [rbp+0C0h+var_80], xmm0
0x1800d62f4  movups  xmm0, cs:xmmword_180213E10
0x1800d62fb  movdqu  [rbp+0C0h+var_70], xmm1
0x1800d6300  movdqu  [rbp+0C0h+var_60], xmm0
0x1800d6305  movups  xmm0, cs:xmmword_180212850
0x1800d630c  movdqu  [rbp+0C0h+var_50], xmm1
0x1800d6311  movdqu  [rbp+0C0h+var_40], xmm0
0x1800d6319  movups  xmm1, cs:xmmword_180214420
0x1800d6320  mov     [rsp+1C0h+lpdwDisposition], 0; pAttributes
0x1800d6329  lea     rax, [rbp+0C0h+var_D0]
0x1800d632d  movups  xmm0, cs:xmmword_180212BF0
0x1800d6334  mov     [rsp+1C0h+var_188], rax; pOutputTypes
0x1800d6339  lea     r8, aMicrosoftMpegV; "Microsoft MPEG Video Decoder MFT"
0x1800d6340  lea     rax, [rbp+0C0h+pInputTypes]
0x1800d6344  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], 5; cOutputTypes
0x1800d634c  mov     qword ptr [rsp+1C0h+samDesired], rax; pInputTypes
0x1800d6351  lea     rdx, [rsp+1C0h+clsidMFT]; guidCategory
0x1800d6356  xor     r9d, r9d; Flags
0x1800d6359  mov     dword ptr [rsp+1C0h+phkResult], 2; cInputTypes
0x1800d6361  lea     rcx, [rbp+0C0h+guidCategory]; clsidMFT
0x1800d6365  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm1
0x1800d636b  movdqu  xmmword ptr [rbp+0C0h+guidCategory.Data1], xmm0
0x1800d6370  call    cs:MFTRegister
0x1800d6377  nop     dword ptr [rax+rax+00h]
0x1800d637c  movups  xmm0, cs:xmmword_180212BF0
0x1800d6383  lea     rdx, aMicrosoftMpegV; "Microsoft MPEG Video Decoder MFT"
0x1800d638a  lea     rcx, [rsp+1C0h+clsidMFT]
0x1800d638f  movdqu  xmmword ptr [rsp+1C0h+clsidMFT.Data1], xmm0
0x1800d6395  call    sub_1800D4748
0x1800d639a  xor     eax, eax
0x1800d639c  mov     rcx, [rbp+0C0h+var_30]
0x1800d63a3  xor     rcx, rsp; StackCookie
0x1800d63a6  call    __security_check_cookie
0x1800d63ab  add     rsp, 1A0h
0x1800d63b2  pop     r15
0x1800d63b4  pop     rdi
0x1800d63b5  pop     rsi
0x1800d63b6  pop     rbx
0x1800d63b7  pop     rbp
0x1800d63b8  retn
```
