# DllRegisterServer

- ea: `0x18006bbf0`
- end: `0x18006bdea`
- name: `DllRegisterServer`
- size: `506`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ab90`
- `0x18000b79c`
- `0x18006b99c`
- `0x18006bbf0`
- `0x18006c224`

## import_xrefs

- `msdmo!DMORegister` at `0x18006bdc0`
- `msdmo!DMORegister` at `0x18006bdc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006bd3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006bd3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bd09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bd09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bd48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bd48`

## string_xrefs

- `0x18006bc29`: `CLSID\{`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  int v1; // eax
  HRESULT v2; // ecx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int cbData; // [rsp+28h] [rbp-D8h]
  DWORD cOutTypes; // [rsp+30h] [rbp-D0h]
  int pOutTypes; // [rsp+38h] [rbp-C8h]
  int v7; // [rsp+40h] [rbp-C0h]
  int v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+50h] [rbp-B0h]
  int v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+68h] [rbp-98h]
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DMO_PARTIAL_MEDIATYPE v15; // [rsp+80h] [rbp-80h] BYREF
  GUID v16; // [rsp+A0h] [rbp-60h]
  GUID v17; // [rsp+B0h] [rbp-50h]
  DMO_PARTIAL_MEDIATYPE pInTypes; // [rsp+C0h] [rbp-40h] BYREF
  GUID v19; // [rsp+E0h] [rbp-20h]
  GUID v20; // [rsp+F0h] [rbp-10h]
  WCHAR SubKey[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v22[144]; // [rsp+110h] [rbp+10h] BYREF

  result = CreateCLSIDRegKey(&CLSID_CResamplerMediaObject);
  if ( result >= 0 )
  {
    wcscpy(SubKey, L"CLSID\\{");
    memset_0(v22, 0, sizeof(v22));
    v12 = CLSID_CResamplerMediaObject.Data4[7];
    v11 = CLSID_CResamplerMediaObject.Data4[6];
    v10 = CLSID_CResamplerMediaObject.Data4[5];
    v9 = CLSID_CResamplerMediaObject.Data4[4];
    v8 = CLSID_CResamplerMediaObject.Data4[3];
    v7 = CLSID_CResamplerMediaObject.Data4[2];
    pOutTypes = CLSID_CResamplerMediaObject.Data4[1];
    cOutTypes = CLSID_CResamplerMediaObject.Data4[0];
    cbData = CLSID_CResamplerMediaObject.Data3;
    phkResult = CLSID_CResamplerMediaObject.Data2;
    result = StringCchPrintfW(
               &SubKey[7],
               0x49u,
               L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
               CLSID_CResamplerMediaObject.Data1,
               phkResult,
               cbData,
               cOutTypes,
               pOutTypes,
               v7,
               v8,
               v9,
               v10,
               v11,
               v12);
    if ( result >= 0 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
      {
        *(_DWORD *)Data = 8390656;
        RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
        RegCloseKey(hKey);
      }
      pInTypes.type = MEDIATYPE_Audio;
      pInTypes.subtype = MEDIASUBTYPE_PCM;
      v19 = MEDIATYPE_Audio;
      v20 = MEDIASUBTYPE_IEEE_FLOAT;
      v15.type = MEDIATYPE_Audio;
      v15.subtype = MEDIASUBTYPE_PCM;
      v16 = MEDIATYPE_Audio;
      v17 = MEDIASUBTYPE_IEEE_FLOAT;
      v1 = DMORegister(
             L"Resampler DMO",
             &CLSID_CResamplerMediaObject,
             &DMOCATEGORY_AUDIO_EFFECT,
             1u,
             2u,
             &pInTypes,
             2u,
             &v15);
      v2 = 0;
      if ( v1 < 0 )
        return v1;
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006bbf0  push    rbp
0x18006bbf2  push    rbx
0x18006bbf3  push    rsi
0x18006bbf4  push    rdi
0x18006bbf5  lea     rbp, [rsp-0B8h]
0x18006bbfd  sub     rsp, 1B8h
0x18006bc04  mov     rax, cs:__security_cookie
0x18006bc0b  xor     rax, rsp
0x18006bc0e  mov     [rbp+0D0h+var_30], rax
0x18006bc15  lea     rcx, CLSID_CResamplerMediaObject; struct _GUID *
0x18006bc1c  call    CreateCLSIDRegKey
0x18006bc21  test    eax, eax
0x18006bc23  js      loc_18006BDCF
0x18006bc29  movups  xmm0, xmmword ptr cs:aClsid; "CLSID\\{"
0x18006bc30  xor     edx, edx; Val
0x18006bc32  lea     rcx, [rbp+0D0h+var_C0]; void *
0x18006bc36  mov     r8d, 90h; Size
0x18006bc3c  movdqu  xmmword ptr [rbp+0D0h+SubKey], xmm0
0x18006bc41  call    memset_0
0x18006bc46  movzx   r9d, cs:CLSID_CResamplerMediaObject.Data4+2
0x18006bc4e  movzx   r8d, cs:CLSID_CResamplerMediaObject.Data4+1
0x18006bc56  movzx   edx, cs:CLSID_CResamplerMediaObject.Data4
0x18006bc5d  movzx   ecx, cs:CLSID_CResamplerMediaObject.Data3
0x18006bc64  movzx   esi, cs:CLSID_CResamplerMediaObject.Data4+7
0x18006bc6b  movzx   edi, cs:CLSID_CResamplerMediaObject.Data4+6
0x18006bc72  movzx   ebx, cs:CLSID_CResamplerMediaObject.Data4+5
0x18006bc79  movzx   r11d, cs:CLSID_CResamplerMediaObject.Data4+4
0x18006bc81  movzx   r10d, cs:CLSID_CResamplerMediaObject.Data4+3
0x18006bc89  movzx   eax, cs:CLSID_CResamplerMediaObject.Data2
0x18006bc90  mov     [rsp+1D0h+var_168], esi
0x18006bc94  mov     [rsp+1D0h+var_170], edi
0x18006bc98  mov     [rsp+1D0h+var_178], ebx
0x18006bc9c  mov     [rsp+1D0h+var_180], r11d
0x18006bca1  mov     [rsp+1D0h+var_188], r10d
0x18006bca6  mov     [rsp+1D0h+var_190], r9d
0x18006bcab  mov     r9d, cs:CLSID_CResamplerMediaObject.Data1
0x18006bcb2  mov     dword ptr [rsp+1D0h+pOutTypes], r8d
0x18006bcb7  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x18006bcbe  mov     [rsp+1D0h+cOutTypes], edx
0x18006bcc2  mov     edx, 49h ; 'I'; unsigned __int64
0x18006bcc7  mov     [rsp+1D0h+cbData], ecx
0x18006bccb  lea     rcx, [rbp+0D0h+SubKey+0Eh]; unsigned __int16 *
0x18006bccf  mov     dword ptr [rsp+1D0h+phkResult], eax
0x18006bcd3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bcd8  test    eax, eax
0x18006bcda  js      loc_18006BDCF
0x18006bce0  lea     rax, [rsp+1D0h+hKey]
0x18006bce5  mov     [rsp+1D0h+hKey], 0
0x18006bcee  mov     ebx, 2
0x18006bcf3  mov     [rsp+1D0h+phkResult], rax; phkResult
0x18006bcf8  mov     r9d, ebx; samDesired
0x18006bcfb  lea     rdx, [rbp+0D0h+SubKey]; lpSubKey
0x18006bcff  xor     r8d, r8d; ulOptions
0x18006bd02  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006bd09  call    cs:__imp_RegOpenKeyExW
0x18006bd0f  test    eax, eax
0x18006bd11  jnz     short loc_18006BD4E
0x18006bd13  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18006bd18  lea     r9d, [rbx+2]; dwType
0x18006bd1c  lea     rax, [rsp+1D0h+Data]
0x18006bd21  mov     [rsp+1D0h+cbData], r9d; cbData
0x18006bd26  xor     r8d, r8d; Reserved
0x18006bd29  mov     [rsp+1D0h+phkResult], rax; lpData
0x18006bd2e  lea     rdx, ValueName; "Merit"
0x18006bd35  mov     dword ptr [rsp+1D0h+Data], 800800h
0x18006bd3d  call    cs:__imp_RegSetValueExW
0x18006bd43  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18006bd48  call    cs:__imp_RegCloseKey
0x18006bd4e  movups  xmm2, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18006bd55  lea     rax, [rbp+0D0h+var_150]
0x18006bd59  mov     r9d, 1; dwFlags
0x18006bd5f  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_PCM.Data1
0x18006bd66  mov     [rsp+1D0h+pOutTypes], rax; pOutTypes
0x18006bd6b  lea     rax, [rbp+0D0h+pInTypes]
0x18006bd6f  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x18006bd76  mov     [rsp+1D0h+cOutTypes], ebx; cOutTypes
0x18006bd7a  lea     r8, DMOCATEGORY_AUDIO_EFFECT; guidCategory
0x18006bd81  mov     qword ptr [rsp+1D0h+cbData], rax; pInTypes
0x18006bd86  lea     rdx, CLSID_CResamplerMediaObject; clsidDMO
0x18006bd8d  lea     rcx, szName; "Resampler DMO"
0x18006bd94  mov     dword ptr [rsp+1D0h+phkResult], ebx; cInTypes
0x18006bd98  movdqu  xmmword ptr [rbp+0D0h+pInTypes.type.Data1], xmm2
0x18006bd9d  movdqu  xmmword ptr [rbp+0D0h+pInTypes.subtype.Data1], xmm1
0x18006bda2  movdqu  [rbp+0D0h+var_F0], xmm2
0x18006bda7  movdqu  [rbp+0D0h+var_E0], xmm0
0x18006bdac  movdqu  xmmword ptr [rbp+0D0h+var_150.type.Data1], xmm2
0x18006bdb1  movdqu  xmmword ptr [rbp+0D0h+var_150.subtype.Data1], xmm1
0x18006bdb6  movdqu  [rbp+0D0h+var_130], xmm2
0x18006bdbb  movdqu  [rbp+0D0h+var_120], xmm0
0x18006bdc0  call    cs:__imp_DMORegister
0x18006bdc6  xor     ecx, ecx
0x18006bdc8  test    eax, eax
0x18006bdca  cmovs   ecx, eax
0x18006bdcd  mov     eax, ecx
0x18006bdcf  mov     rcx, [rbp+0D0h+var_30]
0x18006bdd6  xor     rcx, rsp; StackCookie
0x18006bdd9  call    __security_check_cookie
0x18006bdde  add     rsp, 1B8h
0x18006bde5  pop     rdi
0x18006bde6  pop     rsi
0x18006bde7  pop     rbx
0x18006bde8  pop     rbp
0x18006bde9  retn
```
