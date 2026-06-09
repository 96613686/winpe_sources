# Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveLogoForUrl(ushort const *,ushort,ushort,_GUID,ulong,uchar *,ushort)

- ea: `0x180013ed0`
- end: `0x180014086`
- name: `?SaveLogoForUrl@CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAAJPEBGGGU_GUID@@KPEAEG@Z`
- size: `438`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, const wchar_t *lpcwszUrl, unsigned __int16 nWidth, unsigned __int16 nHeight, _GUID guidPixelFormat, unsigned int dwStride, unsigned __int8 *pImageData, unsigned __int16 nImageSize)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013250`

## callees

- `0x180013ed0`
- `0x1800204e2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001406b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001406b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013fb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001403c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013fb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001403c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fca`

## string_xrefs

- `0x180013f80`: `Software\Microsoft\Web Authentication Broker`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveLogoForUrl(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this,
        const wchar_t *lpcwszUrl,
        unsigned __int16 nWidth,
        unsigned __int16 nHeight,
        _GUID *guidPixelFormat,
        unsigned int dwStride,
        unsigned __int8 *pImageData,
        unsigned __int16 nImageSize)
{
  size_t v8; // rbx
  DWORD v12; // esi
  char *v13; // rax
  char *v14; // rdi
  unsigned int v15; // ebx
  unsigned __int8 *v16; // rdx
  void *v17; // rcx
  _GUID *v18; // rax
  _GUID v19; // xmm0
  LSTATUS v20; // eax
  bool v21; // cc
  HKEY__ *hWABRootKey; // [rsp+50h] [rbp-48h] BYREF
  HKEY__ *hSiteKey; // [rsp+A0h] [rbp+8h] BYREF

  v8 = nImageSize;
  hWABRootKey = 0;
  hSiteKey = 0;
  v12 = nImageSize + 36;
  v13 = (char *)LocalAlloc(0x40u, v12);
  v14 = v13;
  if ( !v13 )
  {
    v15 = -2147024882;
    goto $Cleanup_1;
  }
  v16 = pImageData;
  v17 = v13 + 36;
  *(_DWORD *)v13 = 0;
  *((_DWORD *)v13 + 1) = v12;
  *((_WORD *)v13 + 4) = nWidth;
  *((_WORD *)v13 + 5) = nHeight;
  v18 = guidPixelFormat;
  *((_WORD *)v14 + 16) = v8;
  v19 = *v18;
  LODWORD(v18) = dwStride;
  *(_GUID *)(v14 + 12) = v19;
  *((_DWORD *)v14 + 7) = (_DWORD)v18;
  memcpy_0(v17, v16, v8);
  v20 = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Web Authentication Broker",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hWABRootKey,
          0);
  v15 = v20;
  v21 = v20 <= 0;
  if ( v20
    || (v20 = RegCreateKeyExW(hWABRootKey, lpcwszUrl, 0, 0, 0, 0xF003Fu, 0, &hSiteKey, 0), v15 = v20,
                                                                                           v21 = v20 <= 0,
                                                                                           v20) )
  {
    if ( v21 )
      goto $Cleanup_1;
    goto LABEL_5;
  }
  v20 = RegSetValueExW(hSiteKey, L"Logo", 0, 3u, (const BYTE *)v14, v12);
  if ( !v20 )
    goto $Cleanup_1;
  if ( v20 > 0 )
  {
LABEL_5:
    v15 = (unsigned __int16)v20 | 0x80070000;
    goto $Cleanup_1;
  }
  v15 = v20;
$Cleanup_1:
  LocalFree(v14);
  if ( hSiteKey )
    RegCloseKey(hSiteKey);
  if ( hWABRootKey )
    RegCloseKey(hWABRootKey);
  return v15;
}

```

## disassembly

```asm
0x180013ed0  mov     rax, rsp
0x180013ed3  mov     [rax+8], rcx
0x180013ed7  push    rbx
0x180013ed8  push    rbp
0x180013ed9  push    rsi
0x180013eda  push    rdi
0x180013edb  push    r14
0x180013edd  push    r15
0x180013edf  sub     rsp, 68h
0x180013ee3  movzx   ebx, [rsp+98h+arg_38]
0x180013eeb  mov     rbp, lpcwszUrl
0x180013eee  mov     ecx, 40h ; '@'; uFlags
0x180013ef3  mov     qword ptr [rax-48h], 0
0x180013efb  movzx   r14d, nHeight
0x180013eff  mov     qword ptr [rax+8], 0
0x180013f07  movzx   r15d, nWidth
0x180013f0b  lea     esi, [rbx+24h]
0x180013f0e  mov     edx, esi; uBytes
0x180013f10  call    cs:__imp_LocalAlloc
0x180013f16  mov     rdi, rax
0x180013f19  test    rax, rax
0x180013f1c  jnz     short loc_180013F28
0x180013f1e  mov     ebx, 8007000Eh
0x180013f23  jmp     $Cleanup_1
0x180013f28  mov     lpcwszUrl, [rsp+98h+Src]; Src
0x180013f30  lea     rcx, [rdi+24h]; void *
0x180013f34  mov     dword ptr [rax], 0
0x180013f3a  mov     r8, rbx; Size
0x180013f3d  mov     [rax+4], esi
0x180013f40  mov     [rax+8], r15w
0x180013f45  mov     [rax+0Ah], r14w
0x180013f4a  mov     rax, qword ptr [rsp+98h+guidPixelFormat.Data1]
0x180013f52  mov     [rdi+20h], bx
0x180013f56  movaps  xmm0, xmmword ptr [rax]
0x180013f59  mov     eax, dword ptr [rsp+98h+guidPixelFormat.Data4]
0x180013f60  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180013f65  mov     [rdi+1Ch], eax
0x180013f68  call    memcpy_0
0x180013f6d  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x180013f76  lea     rax, [rsp+98h+hWABRootKey]
0x180013f7b  mov     [rsp+98h+phkResult], rax; phkResult
0x180013f80  lea     lpcwszUrl, aSoftwareMicros_5; "Software\\Microsoft\\Web Authentication"...
0x180013f87  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013f90  mov     r14d, 0F003Fh
0x180013f96  mov     [rsp+98h+samDesired], r14d; samDesired
0x180013f9b  xor     r9d, r9d; lpClass
0x180013f9e  xor     r8d, r8d; Reserved
0x180013fa1  mov     [rsp+98h+dwOptions], 0; dwOptions
0x180013fa9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013fb0  call    cs:__imp_RegCreateKeyExW
0x180013fb6  mov     ebx, eax
0x180013fb8  test    eax, eax
0x180013fba  jz      short loc_180014002
0x180013fbc  jle     short $Cleanup_1
0x180013fbe  movzx   ebx, ax
0x180013fc1  or      ebx, 80070000h
0x180013fc7  mov     rcx, rdi; hMem
0x180013fca  call    cs:__imp_LocalFree
0x180013fd0  mov     rcx, [rsp+98h+hSiteKey]; hKey
0x180013fd8  test    rcx, rcx
0x180013fdb  jz      short loc_180013FE3
0x180013fdd  call    cs:__imp_RegCloseKey
0x180013fe3  mov     rcx, [rsp+98h+hWABRootKey]; hKey
0x180013fe8  test    rcx, rcx
0x180013feb  jz      short loc_180013FF3
0x180013fed  call    cs:__imp_RegCloseKey
0x180013ff3  mov     eax, ebx
0x180013ff5  add     rsp, 68h
0x180013ff9  pop     r15
0x180013ffb  pop     r14
0x180013ffd  pop     rdi
0x180013ffe  pop     rsi
0x180013fff  pop     rbp
0x180014000  pop     rbx
0x180014001  retn
0x180014002  mov     rcx, [rsp+98h+hWABRootKey]; hKey
0x180014007  lea     rax, [rsp+98h+hSiteKey]
0x18001400f  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x180014018  xor     r9d, r9d; lpClass
0x18001401b  mov     [rsp+98h+phkResult], rax; phkResult
0x180014020  xor     r8d, r8d; Reserved
0x180014023  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001402c  mov     lpcwszUrl, rbp; lpSubKey
0x18001402f  mov     [rsp+98h+samDesired], r14d; samDesired
0x180014034  mov     [rsp+98h+dwOptions], 0; dwOptions
0x18001403c  call    cs:__imp_RegCreateKeyExW
0x180014042  mov     ebx, eax
0x180014044  test    eax, eax
0x180014046  jnz     loc_180013FBC
0x18001404c  mov     rcx, [rsp+98h+hSiteKey]; hKey
0x180014054  lea     r9d, [rax+3]; dwType
0x180014058  mov     [rsp+98h+samDesired], esi; cbData
0x18001405c  lea     lpcwszUrl, aLogo; "Logo"
0x180014063  xor     r8d, r8d; Reserved
0x180014066  mov     qword ptr [rsp+98h+dwOptions], rdi; lpData
0x18001406b  call    cs:__imp_RegSetValueExW
0x180014071  test    eax, eax
0x180014073  jz      $Cleanup_1
0x180014079  jg      loc_180013FBE
0x18001407f  mov     ebx, eax
0x180014081  jmp     $Cleanup_1
```
