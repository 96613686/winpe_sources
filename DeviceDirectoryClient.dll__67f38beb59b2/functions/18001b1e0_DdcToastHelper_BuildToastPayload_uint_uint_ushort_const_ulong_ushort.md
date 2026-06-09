# DdcToastHelper::BuildToastPayload(uint,uint,ushort const *,ulong,ushort * *)

- ea: `0x18001b1e0`
- end: `0x18001b42a`
- name: `?BuildToastPayload@DdcToastHelper@@CAJIIPEBGKPEAPEAG@Z`
- size: `586`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, __int64, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b530`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18001b1e0`
- `0x18001b430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b30e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b374`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b30e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b374`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b35a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b37e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b37e`

## string_xrefs

- `0x18001b2e5`: `DeviceDirectoryClient.dll`
- `0x18001b353`: `DeviceDirectoryClient.dll`
- `0x18001b3f9`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctoasthelper.cpp`
- `0x18001b235`: `https://account.microsoft.com/devices`
- `0x18001b247`: `<toast activationType="protocol" launch="%1"><visual><binding template="ToastGeneric"><text id="1">%2</text><text id="2">%3</text></binding></visual></toast>`
- `0x18001b33a`: `CBR(LoadStringW( GetModuleHandleW(L"DeviceDirectoryClient.dll"), uiResIdAction, pszActionValue, (sizeof(*RtlpNumberOf(pszActionValue)))) != 0)`
- `0x18001b39c`: `CBR(LoadStringW( GetModuleHandleW(L"DeviceDirectoryClient.dll"), uiResIdDescription, pszTitleDescription, (sizeof(*RtlpNumberOf(pszTitleDescription)))) != 0)`
- `0x18001b3e5`: `CHR(FormatMessageFromStringAlloc( ppszFormattedToastXMLPayload, c_szToastPayloadFormat, c_szTaskUri, pszTitleDescription, pszActionValue))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcToastHelper::BuildToastPayload(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        LPWSTR lpBuffer)
{
  unsigned __int16 *v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  HMODULE ModuleHandleW; // rax
  signed int v19; // eax
  int v20; // edx
  int v21; // ecx
  signed int v22; // ebx
  HMODULE v23; // rax
  signed int LastError; // eax
  int v25; // edx
  int v26; // ecx
  int v27; // edx
  int v28; // ecx
  _OWORD v30[3]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v31[2]; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v32[160]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[512]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR v34[512]; // [rsp+5C0h] [rbp+4C0h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v34, 0, sizeof(v34));
  v5 = v32;
  v6 = L"<toast activationType=\"protocol\" launch=\"%1\"><visual><binding template=\"ToastGeneric\"><text id=\"1\">%2</te"
        "xt><text id=\"2\">%3</text></binding></visual></toast>";
  v30[0] = *(_OWORD *)L"https://account.microsoft.com/devices";
  v7 = 2;
  v30[2] = *(_OWORD *)L"microsoft.com/devices";
  v30[1] = *(_OWORD *)L"account.microsoft.com/devices";
  v31[0] = *(_OWORD *)L"t.com/devices";
  *(_OWORD *)((char *)v31 + 12) = *(_OWORD *)L"devices";
  do
  {
    v8 = *((_OWORD *)v6 + 1);
    *(_OWORD *)v5 = *(_OWORD *)v6;
    v9 = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 1) = v8;
    v10 = *((_OWORD *)v6 + 3);
    *((_OWORD *)v5 + 2) = v9;
    v11 = *((_OWORD *)v6 + 4);
    *((_OWORD *)v5 + 3) = v10;
    v12 = *((_OWORD *)v6 + 5);
    *((_OWORD *)v5 + 4) = v11;
    v13 = *((_OWORD *)v6 + 6);
    *((_OWORD *)v5 + 5) = v12;
    v14 = *((_OWORD *)v6 + 7);
    v6 += 64;
    *((_OWORD *)v5 + 6) = v13;
    *((_OWORD *)v5 + 7) = v14;
    v5 += 64;
    --v7;
  }
  while ( v7 );
  v15 = *((_OWORD *)v6 + 1);
  *(_OWORD *)v5 = *(_OWORD *)v6;
  v16 = *((_OWORD *)v6 + 2);
  *((_OWORD *)v5 + 1) = v15;
  v17 = *(_OWORD *)(v6 + 22);
  *((_OWORD *)v5 + 2) = v16;
  *(_OWORD *)(v5 + 22) = v17;
  ModuleHandleW = GetModuleHandleW(L"DeviceDirectoryClient.dll");
  if ( LoadStringW(ModuleHandleW, 0x25Cu, Buffer, 512) )
  {
    v23 = GetModuleHandleW(L"DeviceDirectoryClient.dll");
    if ( LoadStringW(v23, 0x25Bu, v34, 512) )
    {
      v22 = FormatMessageFromStringAlloc(lpBuffer, v32, v30, v34, Buffer);
      if ( v22 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v28,
          v27,
          v22,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
          168,
          (__int64)"CHR(FormatMessageFromStringAlloc( ppszFormattedToastXMLPayload, c_szToastPayloadFormat, c_szTaskUri, "
                   "pszTitleDescription, pszActionValue))");
    }
    else
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v26,
          v25,
          v22,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
          149,
          (__int64)"CBR(LoadStringW( GetModuleHandleW(L\"DeviceDirectoryClient.dll\"), uiResIdDescription, pszTitleDescri"
                   "ption, (sizeof(*RtlpNumberOf(pszTitleDescription)))) != 0)");
    }
  }
  else
  {
    v19 = GetLastError();
    v22 = v19;
    if ( v19 > 0 )
      v22 = (unsigned __int16)v19 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v21,
        v20,
        v22,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
        141,
        (__int64)"CBR(LoadStringW( GetModuleHandleW(L\"DeviceDirectoryClient.dll\"), uiResIdAction, pszActionValue, (size"
                 "of(*RtlpNumberOf(pszActionValue)))) != 0)");
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18001b1e0  mov     [rsp-8+arg_0], rbx
0x18001b1e5  push    rbp
0x18001b1e6  lea     rbp, [rsp-8D0h]
0x18001b1ee  sub     rsp, 9D0h
0x18001b1f5  mov     rax, cs:__security_cookie
0x18001b1fc  xor     rax, rsp
0x18001b1ff  mov     [rbp+8D0h+var_10], rax
0x18001b206  mov     rbx, [rbp+8D0h+lpBuffer]
0x18001b20d  lea     rcx, [rbp+8D0h+Buffer]; void *
0x18001b214  xor     edx, edx; Val
0x18001b216  mov     r8d, 400h; Size
0x18001b21c  call    memset_0
0x18001b221  xor     edx, edx; Val
0x18001b223  lea     rcx, [rbp+8D0h+var_410]; void *
0x18001b22a  mov     r8d, 400h; Size
0x18001b230  call    memset_0
0x18001b235  movaps  xmm0, xmmword ptr cs:aHttpsAccountMi; "https://account.microsoft.com/devices"
0x18001b23c  lea     rax, [rbp+8D0h+var_950]
0x18001b240  movaps  xmm1, xmmword ptr cs:aHttpsAccountMi+10h; "account.microsoft.com/devices"
0x18001b247  lea     rcx, aToastActivatio; "<toast activationType=\"protocol\" laun"...
0x18001b24e  movaps  [rsp+9D0h+var_9A0], xmm0
0x18001b253  mov     edx, 2
0x18001b258  movaps  xmm0, xmmword ptr cs:aHttpsAccountMi+20h; "microsoft.com/devices"
0x18001b25f  movaps  [rsp+9D0h+var_980], xmm0
0x18001b264  movups  xmm0, xmmword ptr cs:aHttpsAccountMi+3Ch; "devices"
0x18001b26b  lea     r8d, [rdx+7Eh]
0x18001b26f  movaps  [rsp+9D0h+var_990], xmm1
0x18001b274  movaps  xmm1, xmmword ptr cs:aHttpsAccountMi+30h; "t.com/devices"
0x18001b27b  movaps  xmmword ptr [rsp+9D0h+var_970], xmm1
0x18001b280  movups  xmmword ptr [rsp+9D0h+var_970+0Ch], xmm0
0x18001b285  movups  xmm0, xmmword ptr [rcx]
0x18001b288  movups  xmm1, xmmword ptr [rcx+10h]
0x18001b28c  movups  xmmword ptr [rax], xmm0
0x18001b28f  movups  xmm0, xmmword ptr [rcx+20h]
0x18001b293  movups  xmmword ptr [rax+10h], xmm1
0x18001b297  movups  xmm1, xmmword ptr [rcx+30h]
0x18001b29b  movups  xmmword ptr [rax+20h], xmm0
0x18001b29f  movups  xmm0, xmmword ptr [rcx+40h]
0x18001b2a3  movups  xmmword ptr [rax+30h], xmm1
0x18001b2a7  movups  xmm1, xmmword ptr [rcx+50h]
0x18001b2ab  movups  xmmword ptr [rax+40h], xmm0
0x18001b2af  movups  xmm0, xmmword ptr [rcx+60h]
0x18001b2b3  movups  xmmword ptr [rax+50h], xmm1
0x18001b2b7  movups  xmm1, xmmword ptr [rcx+70h]
0x18001b2bb  add     rcx, r8
0x18001b2be  movups  xmmword ptr [rax+60h], xmm0
0x18001b2c2  movups  xmmword ptr [rax+70h], xmm1
0x18001b2c6  add     rax, r8
0x18001b2c9  sub     rdx, 1
0x18001b2cd  jnz     short loc_18001B285
0x18001b2cf  movups  xmm0, xmmword ptr [rcx]
0x18001b2d2  movups  xmm1, xmmword ptr [rcx+10h]
0x18001b2d6  movups  xmmword ptr [rax], xmm0
0x18001b2d9  movups  xmm0, xmmword ptr [rcx+20h]
0x18001b2dd  movups  xmmword ptr [rax+10h], xmm1
0x18001b2e1  movups  xmm1, xmmword ptr [rcx+2Ch]
0x18001b2e5  lea     rcx, aDevicedirector_0; "DeviceDirectoryClient.dll"
0x18001b2ec  movups  xmmword ptr [rax+20h], xmm0
0x18001b2f0  movups  xmmword ptr [rax+2Ch], xmm1
0x18001b2f4  call    cs:__imp_GetModuleHandleW
0x18001b2fa  mov     r9d, 200h; cchBufferMax
0x18001b300  lea     r8, [rbp+8D0h+Buffer]; lpBuffer
0x18001b307  mov     rcx, rax; hInstance
0x18001b30a  lea     edx, [r9+5Ch]; uID
0x18001b30e  call    cs:__imp_LoadStringW
0x18001b314  test    eax, eax
0x18001b316  jnz     short loc_18001B353
0x18001b318  call    cs:__imp_GetLastError
0x18001b31e  mov     ebx, eax
0x18001b320  test    eax, eax
0x18001b322  jle     short loc_18001B32D
0x18001b324  movzx   ebx, ax
0x18001b327  or      ebx, 80070000h
0x18001b32d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b334  jz      loc_18001B408
0x18001b33a  lea     rax, aCbrLoadstringw; "CBR(LoadStringW( GetModuleHandleW(L\"De"...
0x18001b341  mov     [rsp+9D0h+var_9A8], rax
0x18001b346  mov     dword ptr [rsp+9D0h+var_9B0], 8Dh
0x18001b34e  jmp     loc_18001B3F9
0x18001b353  lea     rcx, aDevicedirector_0; "DeviceDirectoryClient.dll"
0x18001b35a  call    cs:__imp_GetModuleHandleW
0x18001b360  mov     r9d, 200h; cchBufferMax
0x18001b366  lea     r8, [rbp+8D0h+var_410]; lpBuffer
0x18001b36d  mov     rcx, rax; hInstance
0x18001b370  lea     edx, [r9+5Bh]; uID
0x18001b374  call    cs:__imp_LoadStringW
0x18001b37a  test    eax, eax
0x18001b37c  jnz     short loc_18001B3B2
0x18001b37e  call    cs:__imp_GetLastError
0x18001b384  mov     ebx, eax
0x18001b386  test    eax, eax
0x18001b388  jle     short loc_18001B393
0x18001b38a  movzx   ebx, ax
0x18001b38d  or      ebx, 80070000h
0x18001b393  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b39a  jz      short loc_18001B408
0x18001b39c  lea     rax, aCbrLoadstringw_0; "CBR(LoadStringW( GetModuleHandleW(L\"De"...
0x18001b3a3  mov     [rsp+9D0h+var_9A8], rax
0x18001b3a8  mov     dword ptr [rsp+9D0h+var_9B0], 95h
0x18001b3b0  jmp     short loc_18001B3F9
0x18001b3b2  lea     rax, [rbp+8D0h+Buffer]
0x18001b3b9  mov     rcx, rbx; lpBuffer
0x18001b3bc  lea     r9, [rbp+8D0h+var_410]
0x18001b3c3  mov     [rsp+9D0h+var_9B0], rax
0x18001b3c8  lea     r8, [rsp+9D0h+var_9A0]
0x18001b3cd  lea     rdx, [rbp+8D0h+var_950]; unsigned __int16 *
0x18001b3d1  call    ?FormatMessageFromStringAlloc@@YAJPEAPEAGPEBGZZ; FormatMessageFromStringAlloc(ushort * *,ushort const *,...)
0x18001b3d6  mov     ebx, eax
0x18001b3d8  test    eax, eax
0x18001b3da  jns     short loc_18001B408
0x18001b3dc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b3e3  jz      short loc_18001B408
0x18001b3e5  lea     rax, aChrFormatmessa; "CHR(FormatMessageFromStringAlloc( ppszF"...
0x18001b3ec  mov     [rsp+9D0h+var_9A8], rax
0x18001b3f1  mov     dword ptr [rsp+9D0h+var_9B0], 0A8h
0x18001b3f9  lea     r9, aOnecoreuapShel_15; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001b400  mov     r8d, ebx
0x18001b403  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b408  mov     eax, ebx
0x18001b40a  mov     rcx, [rbp+8D0h+var_10]
0x18001b411  xor     rcx, rsp; StackCookie
0x18001b414  call    __security_check_cookie
0x18001b419  mov     rbx, [rsp+9D0h+arg_0]
0x18001b421  add     rsp, 9D0h
0x18001b428  pop     rbp
0x18001b429  retn
```
