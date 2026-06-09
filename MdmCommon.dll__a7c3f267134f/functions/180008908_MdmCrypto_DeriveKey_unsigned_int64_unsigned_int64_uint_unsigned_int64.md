# MdmCrypto::DeriveKey(unsigned __int64,unsigned __int64,uint,unsigned __int64 *)

- ea: `0x180008908`
- end: `0x1800089af`
- name: `?DeriveKey@MdmCrypto@@CAJ_K0IPEA_K@Z`
- size: `167`
- prototype: `static int(unsigned __int64, unsigned __int64, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008438`

## callees

- `0x1800065c0`
- `0x180008908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000896a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000896a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18000895a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18000895a`

## string_xrefs

- `0x180008939`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

## pseudocode

```c
__int64 __fastcall MdmCrypto::DeriveKey(HCRYPTPROV a1, HCRYPTHASH a2, __int64 a3, unsigned __int64 *phKey)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  int v6; // edx
  int v7; // ecx

  if ( phKey )
  {
    if ( CryptDeriveKey(a1, 0x660Fu, a2, 0, phKey) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v4,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          217,
          "CBR(CryptDeriveKey(hProv, algorithmId, hBaseHash, 0, phKey))");
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        206,
        "CPR(phKey)");
  }
  return v4;
}

```

## disassembly

```asm
0x180008908  push    rbx
0x18000890a  sub     rsp, 30h
0x18000890e  test    r9, r9
0x180008911  jnz     short loc_18000894A
0x180008913  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000891a  mov     ebx, 80070057h
0x18000891f  jz      loc_1800089A6
0x180008925  lea     rax, aCprPhkey; "CPR(phKey)"
0x18000892c  mov     [rsp+38h+var_10], rax
0x180008931  mov     dword ptr [rsp+38h+phKey], 2CEh
0x180008939  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008940  mov     r8d, ebx
0x180008943  call    McTemplateU0dsqs_EventWriteTransfer
0x180008948  jmp     short loc_1800089A6
0x18000894a  mov     [rsp+38h+phKey], r9; phKey
0x18000894f  mov     r8, rdx; hBaseData
0x180008952  xor     r9d, r9d; dwFlags
0x180008955  mov     edx, 660Fh; Algid
0x18000895a  call    cs:__imp_CryptDeriveKey
0x180008961  nop     dword ptr [rax+rax+00h]
0x180008966  test    eax, eax
0x180008968  jnz     short loc_1800089A4
0x18000896a  call    cs:__imp_GetLastError
0x180008971  nop     dword ptr [rax+rax+00h]
0x180008976  mov     ebx, eax
0x180008978  test    eax, eax
0x18000897a  jle     short loc_180008985
0x18000897c  movzx   ebx, ax
0x18000897f  or      ebx, 80070000h
0x180008985  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000898c  jz      short loc_1800089A6
0x18000898e  lea     rax, aCbrCryptderive_0; "CBR(CryptDeriveKey(hProv, algorithmId, "...
0x180008995  mov     [rsp+38h+var_10], rax
0x18000899a  mov     dword ptr [rsp+38h+phKey], 2D9h
0x1800089a2  jmp     short loc_180008939
0x1800089a4  xor     ebx, ebx
0x1800089a6  mov     eax, ebx
0x1800089a8  add     rsp, 30h
0x1800089ac  pop     rbx
0x1800089ad  retn
```
