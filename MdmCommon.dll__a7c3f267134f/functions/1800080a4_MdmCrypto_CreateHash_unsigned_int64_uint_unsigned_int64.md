# MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)

- ea: `0x1800080a4`
- end: `0x18000814b`
- name: `?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z`
- size: `167`
- prototype: `static int(unsigned __int64, unsigned int, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007974`
- `0x180008438`
- `0x180008be0`

## callees

- `0x1800065c0`
- `0x1800080a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008106`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800080f6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800080f6`

## string_xrefs

- `0x1800080d5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x18000812a`: `CBR(CryptCreateHash(hProv, algorithmId, 0, 0, phHash))`

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
          "CBR(CryptCreateHash(hProv, algorithmId, 0, 0, phHash))");
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
        "CPR(phHash)");
  }
  return v3;
}

```

## disassembly

```asm
0x1800080a4  push    rbx
0x1800080a6  sub     rsp, 30h
0x1800080aa  test    r8, r8
0x1800080ad  jnz     short loc_1800080E6
0x1800080af  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800080b6  mov     ebx, 80070057h
0x1800080bb  jz      loc_180008142
0x1800080c1  lea     rax, aCprPhhash; "CPR(phHash)"
0x1800080c8  mov     [rsp+38h+var_10], rax
0x1800080cd  mov     dword ptr [rsp+38h+phHash], 255h
0x1800080d5  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800080dc  mov     r8d, ebx
0x1800080df  call    McTemplateU0dsqs_EventWriteTransfer
0x1800080e4  jmp     short loc_180008142
0x1800080e6  mov     [rsp+38h+phHash], r8; phHash
0x1800080eb  xor     r9d, r9d; dwFlags
0x1800080ee  xor     r8d, r8d; hKey
0x1800080f1  mov     edx, 800Ch; Algid
0x1800080f6  call    cs:__imp_CryptCreateHash
0x1800080fd  nop     dword ptr [rax+rax+00h]
0x180008102  test    eax, eax
0x180008104  jnz     short loc_180008140
0x180008106  call    cs:__imp_GetLastError
0x18000810d  nop     dword ptr [rax+rax+00h]
0x180008112  mov     ebx, eax
0x180008114  test    eax, eax
0x180008116  jle     short loc_180008121
0x180008118  movzx   ebx, ax
0x18000811b  or      ebx, 80070000h
0x180008121  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008128  jz      short loc_180008142
0x18000812a  lea     rax, aCbrCryptcreate; "CBR(CryptCreateHash(hProv, algorithmId,"...
0x180008131  mov     [rsp+38h+var_10], rax
0x180008136  mov     dword ptr [rsp+38h+phHash], 25Dh
0x18000813e  jmp     short loc_1800080D5
0x180008140  xor     ebx, ebx
0x180008142  mov     eax, ebx
0x180008144  add     rsp, 30h
0x180008148  pop     rbx
0x180008149  retn
```
