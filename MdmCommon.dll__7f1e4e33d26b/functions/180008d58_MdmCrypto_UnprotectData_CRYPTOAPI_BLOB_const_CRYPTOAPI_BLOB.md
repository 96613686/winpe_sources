# MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008d58`
- end: `0x180008e6a`
- name: `?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *pDataOut)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078ec`
- `0x180008328`
- `0x180008910`

## callees

- `0x180006548`
- `0x180008d58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e26`
- `CRYPT32!CryptUnprotectData` at `0x180008e1c`
- `CRYPT32!CryptUnprotectData` at `0x180008e1c`

## string_xrefs

- `0x180008d8d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

## pseudocode

```c
__int64 __fastcall MdmCrypto::UnprotectData(struct _CRYPTOAPI_BLOB *a1, struct _CRYPTOAPI_BLOB *pDataOut)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int v4; // edx
  int v5; // ecx

  if ( pDataOut )
  {
    if ( a1->pbData )
    {
      if ( a1->cbData )
      {
        if ( CryptUnprotectData(a1, 0, 0, 0, 0, 0, pDataOut) )
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
              100,
              "CBR(CryptUnprotectData(const_cast<DATA_BLOB*>(&blobDataIn), 0, 0, 0, 0, 0, pDataOut))");
        }
      }
      else
      {
        v2 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)a1,
            (_DWORD)pDataOut,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
            88,
            "CBR(blobDataIn.cbData > 0)");
      }
    }
    else
    {
      v2 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)pDataOut,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          87,
          "CPR(blobDataIn.pbData)");
    }
  }
  else
  {
    v2 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        86,
        "CPR(pDataOut)");
  }
  return v2;
}

```

## disassembly

```asm
0x180008d58  push    rbx
0x180008d5a  sub     rsp, 40h
0x180008d5e  test    rdx, rdx
0x180008d61  jnz     short loc_180008D9E
0x180008d63  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008d6a  mov     r8d, 80070057h
0x180008d70  mov     ebx, r8d
0x180008d73  jz      loc_180008E62
0x180008d79  lea     rax, aCprPdataout; "CPR(pDataOut)"
0x180008d80  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008d85  mov     dword ptr [rsp+48h+pPromptStruct], 156h
0x180008d8d  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008d94  call    McTemplateU0dsqs_EventWriteTransfer
0x180008d99  jmp     loc_180008E62
0x180008d9e  cmp     qword ptr [rcx+8], 0
0x180008da3  jnz     short loc_180008DD1
0x180008da5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008dac  mov     r8d, 80070057h
0x180008db2  mov     ebx, r8d
0x180008db5  jz      loc_180008E62
0x180008dbb  lea     rax, aCprBlobdatainP; "CPR(blobDataIn.pbData)"
0x180008dc2  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008dc7  mov     dword ptr [rsp+48h+pPromptStruct], 157h
0x180008dcf  jmp     short loc_180008D8D
0x180008dd1  cmp     dword ptr [rcx], 0
0x180008dd4  ja      short loc_180008DFE
0x180008dd6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008ddd  mov     r8d, 80070057h
0x180008de3  mov     ebx, r8d
0x180008de6  jz      short loc_180008E62
0x180008de8  lea     rax, aCbrBlobdatainC; "CBR(blobDataIn.cbData > 0)"
0x180008def  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008df4  mov     dword ptr [rsp+48h+pPromptStruct], 158h
0x180008dfc  jmp     short loc_180008D8D
0x180008dfe  mov     [rsp+48h+pDataOut], rdx; pDataOut
0x180008e03  xor     r9d, r9d; pvReserved
0x180008e06  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180008e0e  xor     edx, edx; ppszDataDescr
0x180008e10  xor     r8d, r8d; pOptionalEntropy
0x180008e13  mov     [rsp+48h+pPromptStruct], 0; pPromptStruct
0x180008e1c  call    cs:__imp_CryptUnprotectData
0x180008e22  test    eax, eax
0x180008e24  jnz     short loc_180008E60
0x180008e26  call    cs:__imp_GetLastError
0x180008e2c  mov     ebx, eax
0x180008e2e  test    eax, eax
0x180008e30  jle     short loc_180008E3B
0x180008e32  movzx   ebx, ax
0x180008e35  or      ebx, 80070000h
0x180008e3b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008e42  jz      short loc_180008E62
0x180008e44  lea     rax, aCbrCryptunprot; "CBR(CryptUnprotectData(const_cast<DATA_"...
0x180008e4b  mov     r8d, ebx
0x180008e4e  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008e53  mov     dword ptr [rsp+48h+pPromptStruct], 164h
0x180008e5b  jmp     loc_180008D8D
0x180008e60  xor     ebx, ebx
0x180008e62  mov     eax, ebx
0x180008e64  add     rsp, 40h
0x180008e68  pop     rbx
0x180008e69  retn
```
