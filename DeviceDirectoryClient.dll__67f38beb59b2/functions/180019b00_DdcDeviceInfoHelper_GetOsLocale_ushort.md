# DdcDeviceInfoHelper::GetOsLocale(ushort * *)

- ea: `0x180019b00`
- end: `0x180019cfe`
- name: `?GetOsLocale@DdcDeviceInfoHelper@@CAJPEAPEAG@Z`
- size: `510`
- prototype: `__int64 __fastcall(unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800028d4`
- `0x180003288`
- `0x1800050b8`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c69`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180019b9d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180019c5f`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180019b9d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180019c5f`

## string_xrefs

- `0x180019c96`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019ce0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019bc9`: `CBR(GetSystemPreferredUILanguages(0x8, &ulNumLanguages, nullptr, &cchLanguages))`
- `0x180019c87`: `CBR(GetSystemPreferredUILanguages(0x8, &ulNumLanguages, pwszOsLocale, &cchLanguages))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DdcDeviceInfoHelper::GetOsLocale(unsigned __int16 **a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // ecx
  signed int v6; // eax
  unsigned __int64 v7; // rax
  WCHAR *v8; // rax
  unsigned __int16 *v9; // rsi
  signed int LastError; // eax
  int v11; // edx
  int v12; // ecx
  char v14; // [rsp+20h] [rbp-18h]
  const char *v15; // [rsp+28h] [rbp-10h]
  ULONG pcchLanguagesBuffer; // [rsp+40h] [rbp+8h] BYREF
  ULONG pulNumLanguages; // [rsp+48h] [rbp+10h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        14,
        "CPR(ppwszOsLocale)");
    return v3;
  }
  if ( *a1 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        15,
        "CBR(*ppwszOsLocale == nullptr)");
    return v3;
  }
  if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    if ( pulNumLanguages && pcchLanguagesBuffer )
    {
      v7 = 2LL * pcchLanguagesBuffer;
      if ( !is_mul_ok(pcchLanguagesBuffer, 2u) )
        v7 = -1;
      v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, v8, &pcchLanguagesBuffer) )
        {
          v3 = 0;
          *a1 = v9;
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v12,
              v11,
              v3,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              26,
              "CBR(GetSystemPreferredUILanguages(0x8, &ulNumLanguages, pwszOsLocale, &cchLanguages))");
          operator delete(v9);
        }
        return v3;
      }
      v3 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v3;
      v15 = "CPR(pwszOsLocale)";
      v14 = 23;
    }
    else
    {
      v3 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v3;
      v15 = "CBR(ulNumLanguages > 0 && cchLanguages > 0)";
      v14 = 19;
    }
LABEL_28:
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v14,
      v15);
    return v3;
  }
  v6 = GetLastError();
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v15 = "CBR(GetSystemPreferredUILanguages(0x8, &ulNumLanguages, nullptr, &cchLanguages))";
    v14 = 18;
    goto LABEL_28;
  }
  return v3;
}

```

## disassembly

```asm
0x180019b00  mov     rax, rsp
0x180019b03  mov     [rax+18h], rbx
0x180019b07  mov     [rax+20h], rsi
0x180019b0b  push    rdi
0x180019b0c  sub     rsp, 30h
0x180019b10  mov     dword ptr [rax+10h], 0
0x180019b17  mov     rdi, rcx
0x180019b1a  mov     dword ptr [rax+8], 0
0x180019b21  test    rcx, rcx
0x180019b24  jnz     short loc_180019B55
0x180019b26  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019b2d  mov     r8d, 80070057h
0x180019b33  mov     ebx, r8d
0x180019b36  jz      loc_180019CEC
0x180019b3c  lea     rax, aCprPpwszosloca; "CPR(ppwszOsLocale)"
0x180019b43  mov     [rsp+38h+var_10], rax
0x180019b48  mov     dword ptr [rsp+38h+var_18], 40Eh
0x180019b50  jmp     loc_180019CE0
0x180019b55  cmp     qword ptr [rcx], 0
0x180019b59  jz      short loc_180019B8A
0x180019b5b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019b62  mov     r8d, 80070057h
0x180019b68  mov     ebx, r8d
0x180019b6b  jz      loc_180019CEC
0x180019b71  lea     rax, aCbrPpwszosloca; "CBR(*ppwszOsLocale == nullptr)"
0x180019b78  mov     [rsp+38h+var_10], rax
0x180019b7d  mov     dword ptr [rsp+38h+var_18], 40Fh
0x180019b85  jmp     loc_180019CE0
0x180019b8a  xor     r8d, r8d; pwszLanguagesBuffer
0x180019b8d  lea     r9, [rsp+38h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180019b92  lea     rdx, [rsp+38h+pulNumLanguages]; pulNumLanguages
0x180019b97  lea     ebx, [r8+8]
0x180019b9b  mov     ecx, ebx; dwFlags
0x180019b9d  call    cs:__imp_GetSystemPreferredUILanguages
0x180019ba3  test    eax, eax
0x180019ba5  jnz     short loc_180019BE2
0x180019ba7  call    cs:__imp_GetLastError
0x180019bad  mov     ebx, eax
0x180019baf  test    eax, eax
0x180019bb1  jle     short loc_180019BBC
0x180019bb3  movzx   ebx, ax
0x180019bb6  or      ebx, 80070000h
0x180019bbc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019bc3  jz      loc_180019CEC
0x180019bc9  lea     rax, aCbrGetsystempr; "CBR(GetSystemPreferredUILanguages(0x8, "...
0x180019bd0  mov     [rsp+38h+var_10], rax
0x180019bd5  mov     dword ptr [rsp+38h+var_18], 412h
0x180019bdd  jmp     loc_180019CDD
0x180019be2  cmp     [rsp+38h+pulNumLanguages], 0
0x180019be7  jbe     loc_180019CBB
0x180019bed  mov     eax, [rsp+38h+pcchLanguagesBuffer]
0x180019bf1  test    eax, eax
0x180019bf3  jz      loc_180019CBB
0x180019bf9  mov     ecx, eax
0x180019bfb  mov     eax, 2
0x180019c00  mul     rcx
0x180019c03  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019c0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019c11  cmovb   rax, rcx
0x180019c15  mov     rcx, rax; unsigned __int64
0x180019c18  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019c1d  mov     rsi, rax
0x180019c20  test    rax, rax
0x180019c23  jnz     short loc_180019C50
0x180019c25  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019c2c  mov     ebx, 8007000Eh
0x180019c31  jz      loc_180019CEC
0x180019c37  lea     rax, aCprPwszoslocal; "CPR(pwszOsLocale)"
0x180019c3e  mov     [rsp+38h+var_10], rax
0x180019c43  mov     dword ptr [rsp+38h+var_18], 417h
0x180019c4b  jmp     loc_180019CDD
0x180019c50  lea     r9, [rsp+38h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180019c55  mov     r8, rsi; pwszLanguagesBuffer
0x180019c58  lea     rdx, [rsp+38h+pulNumLanguages]; pulNumLanguages
0x180019c5d  mov     ecx, ebx; dwFlags
0x180019c5f  call    cs:__imp_GetSystemPreferredUILanguages
0x180019c65  test    eax, eax
0x180019c67  jnz     short loc_180019CB4
0x180019c69  call    cs:__imp_GetLastError
0x180019c6f  mov     ebx, eax
0x180019c71  test    eax, eax
0x180019c73  jle     short loc_180019C7E
0x180019c75  movzx   ebx, ax
0x180019c78  or      ebx, 80070000h
0x180019c7e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019c85  jz      short loc_180019CAA
0x180019c87  lea     rax, aCbrGetsystempr_0; "CBR(GetSystemPreferredUILanguages(0x8, "...
0x180019c8e  mov     r8d, ebx
0x180019c91  mov     [rsp+38h+var_10], rax
0x180019c96  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019c9d  mov     dword ptr [rsp+38h+var_18], 41Ah
0x180019ca5  call    McTemplateU0dsqs_EventWriteTransfer
0x180019caa  mov     rcx, rsi; Block
0x180019cad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019cb2  jmp     short loc_180019CEC
0x180019cb4  xor     ebx, ebx
0x180019cb6  mov     [rdi], rsi
0x180019cb9  jmp     short loc_180019CEC
0x180019cbb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019cc2  mov     ebx, 8000FFFFh
0x180019cc7  jz      short loc_180019CEC
0x180019cc9  lea     rax, aCbrUlnumlangua; "CBR(ulNumLanguages > 0 && cchLanguages "...
0x180019cd0  mov     [rsp+38h+var_10], rax
0x180019cd5  mov     dword ptr [rsp+38h+var_18], 413h
0x180019cdd  mov     r8d, ebx
0x180019ce0  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019ce7  call    McTemplateU0dsqs_EventWriteTransfer
0x180019cec  mov     rsi, [rsp+38h+arg_18]
0x180019cf1  mov     eax, ebx
0x180019cf3  mov     rbx, [rsp+38h+arg_10]
0x180019cf8  add     rsp, 30h
0x180019cfc  pop     rdi
0x180019cfd  retn
```
