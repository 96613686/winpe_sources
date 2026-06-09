# MdmCrypto::DeriveKey(unsigned __int64,unsigned __int64,uint,unsigned __int64 *)

- ea: `0x1800087d0`
- end: `0x180008866`
- name: `?DeriveKey@MdmCrypto@@CAJ_K0IPEA_K@Z`
- size: `150`
- prototype: `__int64 __fastcall(HCRYPTPROV, HCRYPTHASH, __int64, unsigned __int64 *phKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008328`

## callees

- `0x180006548`
- `0x1800087d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008828`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18000881e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18000881e`

## string_xrefs

- `0x1800087fd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        206,
        "CPR(phKey)");
  }
  return v4;
}

```

## disassembly

```asm
0x1800087d0  push    rbx
0x1800087d2  sub     rsp, 30h
0x1800087d6  test    r9, r9
0x1800087d9  jnz     short loc_18000880E
0x1800087db  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800087e2  mov     ebx, 80070057h
0x1800087e7  jz      short loc_18000885E
0x1800087e9  lea     rax, aCprPhkey; "CPR(phKey)"
0x1800087f0  mov     [rsp+38h+var_10], rax
0x1800087f5  mov     dword ptr [rsp+38h+phKey], 2CEh
0x1800087fd  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008804  mov     r8d, ebx
0x180008807  call    McTemplateU0dsqs_EventWriteTransfer
0x18000880c  jmp     short loc_18000885E
0x18000880e  mov     [rsp+38h+phKey], r9; phKey
0x180008813  mov     r8, rdx; hBaseData
0x180008816  xor     r9d, r9d; dwFlags
0x180008819  mov     edx, 660Fh; Algid
0x18000881e  call    cs:__imp_CryptDeriveKey
0x180008824  test    eax, eax
0x180008826  jnz     short loc_18000885C
0x180008828  call    cs:__imp_GetLastError
0x18000882e  mov     ebx, eax
0x180008830  test    eax, eax
0x180008832  jle     short loc_18000883D
0x180008834  movzx   ebx, ax
0x180008837  or      ebx, 80070000h
0x18000883d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008844  jz      short loc_18000885E
0x180008846  lea     rax, aCbrCryptderive_0; "CBR(CryptDeriveKey(hProv, algorithmId, "...
0x18000884d  mov     [rsp+38h+var_10], rax
0x180008852  mov     dword ptr [rsp+38h+phKey], 2D9h
0x18000885a  jmp     short loc_1800087FD
0x18000885c  xor     ebx, ebx
0x18000885e  mov     eax, ebx
0x180008860  add     rsp, 30h
0x180008864  pop     rbx
0x180008865  retn
```
