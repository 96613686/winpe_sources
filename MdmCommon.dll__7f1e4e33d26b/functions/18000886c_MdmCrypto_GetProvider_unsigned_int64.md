# MdmCrypto::GetProvider(unsigned __int64 *)

- ea: `0x18000886c`
- end: `0x180008909`
- name: `?GetProvider@MdmCrypto@@CAJPEA_K@Z`
- size: `157`
- prototype: `__int64 __fastcall(unsigned __int64 *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078ec`
- `0x180008328`
- `0x180008a6c`

## callees

- `0x180006548`
- `0x18000886c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088cb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x1800088c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x1800088c1`

## string_xrefs

- `0x180008899`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        44,
        "CPR(phProv)");
  }
  return v2;
}

```

## disassembly

```asm
0x18000886c  push    rbx
0x18000886e  sub     rsp, 30h
0x180008872  test    rcx, rcx
0x180008875  jnz     short loc_1800088AA
0x180008877  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000887e  mov     ebx, 80070057h
0x180008883  jz      short loc_180008901
0x180008885  lea     rax, aCprPhprov; "CPR(phProv)"
0x18000888c  mov     [rsp+38h+var_10], rax
0x180008891  mov     [rsp+38h+dwFlags], 22Ch
0x180008899  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800088a0  mov     r8d, ebx
0x1800088a3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800088a8  jmp     short loc_180008901
0x1800088aa  mov     r9d, 18h; dwProvType
0x1800088b0  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x1800088b8  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800088bf  xor     edx, edx; szContainer
0x1800088c1  call    cs:__imp_CryptAcquireContextA
0x1800088c7  test    eax, eax
0x1800088c9  jnz     short loc_1800088FF
0x1800088cb  call    cs:__imp_GetLastError
0x1800088d1  mov     ebx, eax
0x1800088d3  test    eax, eax
0x1800088d5  jle     short loc_1800088E0
0x1800088d7  movzx   ebx, ax
0x1800088da  or      ebx, 80070000h
0x1800088e0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800088e7  jz      short loc_180008901
0x1800088e9  lea     rax, aCbrCryptacquir; "CBR(CryptAcquireContextA(phProv, 0, \"M"...
0x1800088f0  mov     [rsp+38h+var_10], rax
0x1800088f5  mov     [rsp+38h+dwFlags], 234h
0x1800088fd  jmp     short loc_180008899
0x1800088ff  xor     ebx, ebx
0x180008901  mov     eax, ebx
0x180008903  add     rsp, 30h
0x180008907  pop     rbx
0x180008908  retn
```
