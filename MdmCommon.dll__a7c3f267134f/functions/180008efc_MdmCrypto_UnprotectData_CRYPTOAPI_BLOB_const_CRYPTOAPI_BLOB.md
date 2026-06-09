# MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008efc`
- end: `0x18000901f`
- name: `?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z`
- size: `291`
- prototype: `static int(const struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007974`
- `0x180008438`
- `0x180008a6c`

## callees

- `0x1800065c0`
- `0x180008efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fd4`
- `CRYPT32!CryptUnprotectData` at `0x180008fc4`
- `CRYPT32!CryptUnprotectData` at `0x180008fc4`

## string_xrefs

- `0x180008f31`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

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
              "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
            "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        86,
        "CPR(pDataOut)");
  }
  return v2;
}

```

## disassembly

```asm
0x180008efc  push    rbx
0x180008efe  sub     rsp, 40h
0x180008f02  test    rdx, rdx
0x180008f05  jnz     short loc_180008F42
0x180008f07  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008f0e  mov     r8d, 80070057h
0x180008f14  mov     ebx, r8d
0x180008f17  jz      loc_180009016
0x180008f1d  lea     rax, aCprPdataout; "CPR(pDataOut)"
0x180008f24  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008f29  mov     dword ptr [rsp+48h+pPromptStruct], 156h
0x180008f31  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008f38  call    McTemplateU0dsqs_EventWriteTransfer
0x180008f3d  jmp     loc_180009016
0x180008f42  cmp     qword ptr [rcx+8], 0
0x180008f47  jnz     short loc_180008F75
0x180008f49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008f50  mov     r8d, 80070057h
0x180008f56  mov     ebx, r8d
0x180008f59  jz      loc_180009016
0x180008f5f  lea     rax, aCprBlobdatainP; "CPR(blobDataIn.pbData)"
0x180008f66  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008f6b  mov     dword ptr [rsp+48h+pPromptStruct], 157h
0x180008f73  jmp     short loc_180008F31
0x180008f75  cmp     dword ptr [rcx], 0
0x180008f78  ja      short loc_180008FA6
0x180008f7a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008f81  mov     r8d, 80070057h
0x180008f87  mov     ebx, r8d
0x180008f8a  jz      loc_180009016
0x180008f90  lea     rax, aCbrBlobdatainC; "CBR(blobDataIn.cbData > 0)"
0x180008f97  mov     qword ptr [rsp+48h+dwFlags], rax
0x180008f9c  mov     dword ptr [rsp+48h+pPromptStruct], 158h
0x180008fa4  jmp     short loc_180008F31
0x180008fa6  mov     [rsp+48h+pDataOut], rdx; pDataOut
0x180008fab  xor     r9d, r9d; pvReserved
0x180008fae  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180008fb6  xor     edx, edx; ppszDataDescr
0x180008fb8  xor     r8d, r8d; pOptionalEntropy
0x180008fbb  mov     [rsp+48h+pPromptStruct], 0; pPromptStruct
0x180008fc4  call    cs:__imp_CryptUnprotectData
0x180008fcb  nop     dword ptr [rax+rax+00h]
0x180008fd0  test    eax, eax
0x180008fd2  jnz     short loc_180009014
0x180008fd4  call    cs:__imp_GetLastError
0x180008fdb  nop     dword ptr [rax+rax+00h]
0x180008fe0  mov     ebx, eax
0x180008fe2  test    eax, eax
0x180008fe4  jle     short loc_180008FEF
0x180008fe6  movzx   ebx, ax
0x180008fe9  or      ebx, 80070000h
0x180008fef  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008ff6  jz      short loc_180009016
0x180008ff8  lea     rax, aCbrCryptunprot; "CBR(CryptUnprotectData(const_cast<DATA_"...
0x180008fff  mov     r8d, ebx
0x180009002  mov     qword ptr [rsp+48h+dwFlags], rax
0x180009007  mov     dword ptr [rsp+48h+pPromptStruct], 164h
0x18000900f  jmp     loc_180008F31
0x180009014  xor     ebx, ebx
0x180009016  mov     eax, ebx
0x180009018  add     rsp, 40h
0x18000901c  pop     rbx
0x18000901d  retn
```
