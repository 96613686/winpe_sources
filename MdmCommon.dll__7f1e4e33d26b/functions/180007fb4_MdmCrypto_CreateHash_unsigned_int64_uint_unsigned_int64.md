# MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)

- ea: `0x180007fb4`
- end: `0x18000804a`
- name: `?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z`
- size: `150`
- prototype: `__int64 __fastcall(HCRYPTPROV, int, unsigned __int64 *phHash)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078ec`
- `0x180008328`
- `0x180008a6c`

## callees

- `0x180006548`
- `0x180007fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180008002`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180008002`

## string_xrefs

- `0x180007fe1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x18000802a`: `CBR(CryptCreateHash(hProv, algorithmId, 0, 0, phHash))`

## pseudocode

```c
__int64 __fastcall MdmCrypto::CreateHash(HCRYPTPROV a1, int a2, unsigned __int64 *phHash)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  int v5; // edx
  int v6; // ecx

  if ( phHash )
  {
    if ( CryptCreateHash(a1, 0x800Cu, 0, 0, phHash) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          93,
          (__int64)"CBR(CryptCreateHash(hProv, algorithmId, 0, 0, phHash))");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        85,
        (__int64)"CPR(phHash)");
  }
  return v3;
}

```

## disassembly

```asm
0x180007fb4  push    rbx
0x180007fb6  sub     rsp, 30h
0x180007fba  test    r8, r8
0x180007fbd  jnz     short loc_180007FF2
0x180007fbf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007fc6  mov     ebx, 80070057h
0x180007fcb  jz      short loc_180008042
0x180007fcd  lea     rax, aCprPhhash; "CPR(phHash)"
0x180007fd4  mov     [rsp+38h+var_10], rax
0x180007fd9  mov     dword ptr [rsp+38h+phHash], 255h
0x180007fe1  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180007fe8  mov     r8d, ebx
0x180007feb  call    McTemplateU0dsqs_EventWriteTransfer
0x180007ff0  jmp     short loc_180008042
0x180007ff2  mov     [rsp+38h+phHash], r8; phHash
0x180007ff7  xor     r9d, r9d; dwFlags
0x180007ffa  xor     r8d, r8d; hKey
0x180007ffd  mov     edx, 800Ch; Algid
0x180008002  call    cs:__imp_CryptCreateHash
0x180008008  test    eax, eax
0x18000800a  jnz     short loc_180008040
0x18000800c  call    cs:__imp_GetLastError
0x180008012  mov     ebx, eax
0x180008014  test    eax, eax
0x180008016  jle     short loc_180008021
0x180008018  movzx   ebx, ax
0x18000801b  or      ebx, 80070000h
0x180008021  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008028  jz      short loc_180008042
0x18000802a  lea     rax, aCbrCryptcreate; "CBR(CryptCreateHash(hProv, algorithmId,"...
0x180008031  mov     [rsp+38h+var_10], rax
0x180008036  mov     dword ptr [rsp+38h+phHash], 25Dh
0x18000803e  jmp     short loc_180007FE1
0x180008040  xor     ebx, ebx
0x180008042  mov     eax, ebx
0x180008044  add     rsp, 30h
0x180008048  pop     rbx
0x180008049  retn
```
