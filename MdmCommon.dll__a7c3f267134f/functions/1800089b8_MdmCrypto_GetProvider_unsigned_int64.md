# MdmCrypto::GetProvider(unsigned __int64 *)

- ea: `0x1800089b8`
- end: `0x180008a66`
- name: `?GetProvider@MdmCrypto@@CAJPEA_K@Z`
- size: `174`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007974`
- `0x180008438`
- `0x180008be0`

## callees

- `0x1800065c0`
- `0x1800089b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a21`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180008a11`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180008a11`

## string_xrefs

- `0x1800089e9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

## pseudocode

```c
__int64 __fastcall MdmCrypto::GetProvider(unsigned __int64 *a1, int a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int v4; // edx
  int v5; // ecx

  if ( a1 )
  {
    if ( CryptAcquireContextA(a1, 0, "Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v5,
          v4,
          v2,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          52,
          "CBR(CryptAcquireContextA(phProv, 0, \"Microsoft Enhanced RSA and AES Cryptographic Provider\", 24, 0xF0000000 | 0x00000040))");
    }
  }
  else
  {
    v2 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        44,
        "CPR(phProv)");
  }
  return v2;
}

```

## disassembly

```asm
0x1800089b8  push    rbx
0x1800089ba  sub     rsp, 30h
0x1800089be  test    rcx, rcx
0x1800089c1  jnz     short loc_1800089FA
0x1800089c3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800089ca  mov     ebx, 80070057h
0x1800089cf  jz      loc_180008A5D
0x1800089d5  lea     rax, aCprPhprov; "CPR(phProv)"
0x1800089dc  mov     [rsp+38h+var_10], rax
0x1800089e1  mov     [rsp+38h+dwFlags], 22Ch
0x1800089e9  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800089f0  mov     r8d, ebx
0x1800089f3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800089f8  jmp     short loc_180008A5D
0x1800089fa  mov     r9d, 18h; dwProvType
0x180008a00  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x180008a08  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180008a0f  xor     edx, edx; szContainer
0x180008a11  call    cs:__imp_CryptAcquireContextA
0x180008a18  nop     dword ptr [rax+rax+00h]
0x180008a1d  test    eax, eax
0x180008a1f  jnz     short loc_180008A5B
0x180008a21  call    cs:__imp_GetLastError
0x180008a28  nop     dword ptr [rax+rax+00h]
0x180008a2d  mov     ebx, eax
0x180008a2f  test    eax, eax
0x180008a31  jle     short loc_180008A3C
0x180008a33  movzx   ebx, ax
0x180008a36  or      ebx, 80070000h
0x180008a3c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008a43  jz      short loc_180008A5D
0x180008a45  lea     rax, aCbrCryptacquir; "CBR(CryptAcquireContextA(phProv, 0, \"M"...
0x180008a4c  mov     [rsp+38h+var_10], rax
0x180008a51  mov     [rsp+38h+dwFlags], 234h
0x180008a59  jmp     short loc_1800089E9
0x180008a5b  xor     ebx, ebx
0x180008a5d  mov     eax, ebx
0x180008a5f  add     rsp, 30h
0x180008a63  pop     rbx
0x180008a64  retn
```
