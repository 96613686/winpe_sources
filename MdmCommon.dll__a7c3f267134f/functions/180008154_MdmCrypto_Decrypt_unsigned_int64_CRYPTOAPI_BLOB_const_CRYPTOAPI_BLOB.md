# MdmCrypto::Decrypt(unsigned __int64,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008154`
- end: `0x180008431`
- name: `?Decrypt@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z`
- size: `733`
- prototype: `__int64 __fastcall(HCRYPTKEY hKey, const struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008438`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x1800065c0`
- `0x180006698`
- `0x180008154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082de`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x1800082ce`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x1800082ce`

## string_xrefs

- `0x1800081a0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x18000820a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008311`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x1800083f1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008254`: `CPR(pbTempData)`
- `0x18000829a`: `CBR(memcpy_s(pbTempData, dwSize, blobEncrypted.pbData, blobEncrypted.cbData) == 0)`
- `0x180008302`: `CBR(CryptDecrypt(hKey, 0, 1, 0, pbTempData, &dwSize))`
- `0x1800083dd`: `CBR(memcpy_s(pblobDecrypted->pbData, dwSize, pbTempData, dwSize) == 0)`

## pseudocode

```c
__int64 __fastcall MdmCrypto::Decrypt(HCRYPTKEY hKey, const struct _CRYPTOAPI_BLOB *a2, struct _CRYPTOAPI_BLOB *a3)
{
  void *pbData; // rsi
  signed int v7; // ebx
  void *v8; // rax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  signed int LastError; // eax
  int v13; // ecx
  BYTE *v14; // rax
  BYTE *v15; // rcx
  unsigned int v16; // eax
  rsize_t v17; // rdx
  int v18; // ecx
  BYTE *v19; // rcx
  rsize_t DestinationSize; // [rsp+68h] [rbp+10h] BYREF

  pbData = 0;
  LODWORD(DestinationSize) = 0;
  if ( !a2->pbData )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        hKey,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        94,
        "CPR(blobEncrypted.pbData)");
    goto LABEL_23;
  }
  if ( !a2->cbData )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        hKey,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        95,
        "CBR(blobEncrypted.cbData > 0)");
    goto LABEL_23;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        hKey,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        96,
        "CPR(pblobDecrypted)");
    goto LABEL_37;
  }
  LODWORD(DestinationSize) = a2->cbData;
  v8 = operator new[]((unsigned int)DestinationSize, (const struct std::nothrow_t *)&std::nothrow);
  pbData = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        (_DWORD)a2,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        101,
        "CPR(pbTempData)");
LABEL_34:
    v19 = a3->pbData;
    if ( v19 )
    {
      operator delete(v19, (unsigned __int64)a2);
      a3->pbData = 0;
      a3->cbData = 0;
    }
    goto LABEL_37;
  }
  if ( memcpy_s(v8, (unsigned int)DestinationSize, a2->pbData, a2->cbData) )
  {
    v7 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)a2,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        102,
        "CBR(memcpy_s(pbTempData, dwSize, blobEncrypted.pbData, blobEncrypted.cbData) == 0)");
    goto LABEL_34;
  }
  if ( CryptDecrypt(hKey, 0, 1, 0, (BYTE *)pbData, (DWORD *)&DestinationSize) )
  {
    if ( (_DWORD)DestinationSize )
    {
      v14 = (BYTE *)operator new[]((unsigned int)DestinationSize, (const struct std::nothrow_t *)&std::nothrow);
      a3->pbData = v14;
      v15 = v14;
      if ( v14 )
      {
        v16 = DestinationSize;
        v17 = (unsigned int)DestinationSize;
        a3->cbData = DestinationSize;
        if ( !memcpy_s(v15, v17, pbData, v16) )
        {
          v7 = 0;
          goto LABEL_37;
        }
        v7 = -2147467259;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            (_DWORD)a2,
            -2147467259,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
            119,
            "CBR(memcpy_s(pblobDecrypted->pbData, dwSize, pbTempData, dwSize) == 0)");
      }
      else
      {
        v7 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            0,
            (_DWORD)a2,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
            117,
            "CPR(pblobDecrypted->pbData)");
      }
    }
    else
    {
      v7 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          (_DWORD)a2,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          113,
          "CBR(dwSize > 0)");
    }
    goto LABEL_34;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v13,
      (_DWORD)a2,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      111,
      "CBR(CryptDecrypt(hKey, 0, 1, 0, pbTempData, &dwSize))");
  if ( v7 < 0 )
  {
LABEL_23:
    if ( !a3 )
      goto LABEL_37;
    goto LABEL_34;
  }
LABEL_37:
  operator delete(pbData, (unsigned __int64)a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008154  push    rbx
0x180008156  push    rbp
0x180008157  push    rsi
0x180008158  push    rdi
0x180008159  sub     rsp, 38h
0x18000815d  xor     esi, esi
0x18000815f  mov     dword ptr [rsp+58h+DestinationSize], 0
0x180008167  mov     rdi, r8
0x18000816a  mov     rbx, rdx
0x18000816d  mov     rbp, rcx
0x180008170  cmp     [rdx+8], rsi
0x180008174  jnz     short loc_1800081B1
0x180008176  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000817d  mov     r8d, 80070057h
0x180008183  mov     ebx, r8d
0x180008186  jz      loc_18000832D
0x18000818c  lea     rax, aCprBlobencrypt_0; "CPR(blobEncrypted.pbData)"
0x180008193  mov     [rsp+58h+pdwDataLen], rax
0x180008198  mov     dword ptr [rsp+58h+pbData], 35Eh
0x1800081a0  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800081a7  call    McTemplateU0dsqs_EventWriteTransfer
0x1800081ac  jmp     loc_18000832D
0x1800081b1  mov     eax, [rdx]
0x1800081b3  test    eax, eax
0x1800081b5  jnz     short loc_1800081E3
0x1800081b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800081be  mov     r8d, 80070057h
0x1800081c4  mov     ebx, r8d
0x1800081c7  jz      loc_18000832D
0x1800081cd  lea     rax, aCbrBlobencrypt; "CBR(blobEncrypted.cbData > 0)"
0x1800081d4  mov     [rsp+58h+pdwDataLen], rax
0x1800081d9  mov     dword ptr [rsp+58h+pbData], 35Fh
0x1800081e1  jmp     short loc_1800081A0
0x1800081e3  test    rdi, rdi
0x1800081e6  jnz     short loc_180008223
0x1800081e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800081ef  mov     r8d, 80070057h
0x1800081f5  mov     ebx, r8d
0x1800081f8  jz      loc_18000841D
0x1800081fe  lea     rax, aCprPblobdecryp_0; "CPR(pblobDecrypted)"
0x180008205  mov     [rsp+58h+pdwDataLen], rax
0x18000820a  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008211  mov     dword ptr [rsp+58h+pbData], 360h
0x180008219  call    McTemplateU0dsqs_EventWriteTransfer
0x18000821e  jmp     loc_18000841D
0x180008223  mov     rcx, rax; unsigned __int64
0x180008226  mov     dword ptr [rsp+58h+DestinationSize], eax
0x18000822a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008231  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008236  mov     rsi, rax
0x180008239  test    rax, rax
0x18000823c  jnz     short loc_18000826D
0x18000823e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008245  mov     r8d, 8007000Eh
0x18000824b  mov     ebx, r8d
0x18000824e  jz      loc_1800083FD
0x180008254  lea     rax, aCprPbtempdata; "CPR(pbTempData)"
0x18000825b  mov     [rsp+58h+pdwDataLen], rax
0x180008260  mov     dword ptr [rsp+58h+pbData], 365h
0x180008268  jmp     loc_1800083F1
0x18000826d  mov     r9d, [rbx]; SourceSize
0x180008270  mov     rcx, rsi; Destination
0x180008273  mov     edx, dword ptr [rsp+58h+DestinationSize]; DestinationSize
0x180008277  mov     r8, [rbx+8]; Source
0x18000827b  call    memcpy_s
0x180008280  test    eax, eax
0x180008282  jz      short loc_1800082B3
0x180008284  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000828b  mov     r8d, 80004005h
0x180008291  mov     ebx, r8d
0x180008294  jz      loc_1800083FD
0x18000829a  lea     rax, aCbrMemcpySPbte; "CBR(memcpy_s(pbTempData, dwSize, blobEn"...
0x1800082a1  mov     [rsp+58h+pdwDataLen], rax
0x1800082a6  mov     dword ptr [rsp+58h+pbData], 366h
0x1800082ae  jmp     loc_1800083F1
0x1800082b3  xor     r9d, r9d; dwFlags
0x1800082b6  lea     rax, [rsp+58h+DestinationSize]
0x1800082bb  mov     [rsp+58h+pdwDataLen], rax; pdwDataLen
0x1800082c0  xor     edx, edx; hHash
0x1800082c2  mov     rcx, rbp; hKey
0x1800082c5  mov     [rsp+58h+pbData], rsi; pbData
0x1800082ca  lea     r8d, [r9+1]; Final
0x1800082ce  call    cs:__imp_CryptDecrypt
0x1800082d5  nop     dword ptr [rax+rax+00h]
0x1800082da  test    eax, eax
0x1800082dc  jnz     short loc_18000833B
0x1800082de  call    cs:__imp_GetLastError
0x1800082e5  nop     dword ptr [rax+rax+00h]
0x1800082ea  mov     ebx, eax
0x1800082ec  test    eax, eax
0x1800082ee  jle     short loc_1800082F9
0x1800082f0  movzx   ebx, ax
0x1800082f3  or      ebx, 80070000h
0x1800082f9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008300  jz      short loc_180008325
0x180008302  lea     rax, aCbrCryptdecryp; "CBR(CryptDecrypt(hKey, 0, 1, 0, pbTempD"...
0x180008309  mov     r8d, ebx
0x18000830c  mov     [rsp+58h+pdwDataLen], rax
0x180008311  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008318  mov     dword ptr [rsp+58h+pbData], 36Fh
0x180008320  call    McTemplateU0dsqs_EventWriteTransfer
0x180008325  test    ebx, ebx
0x180008327  jns     loc_18000841D
0x18000832d  test    rdi, rdi
0x180008330  jz      loc_18000841D
0x180008336  jmp     loc_1800083FD
0x18000833b  mov     eax, dword ptr [rsp+58h+DestinationSize]
0x18000833f  test    eax, eax
0x180008341  jnz     short loc_180008371
0x180008343  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000834a  mov     ebx, 8000FFFFh
0x18000834f  jz      loc_1800083FD
0x180008355  lea     rax, aCbrDwsize0; "CBR(dwSize > 0)"
0x18000835c  mov     r8d, ebx
0x18000835f  mov     [rsp+58h+pdwDataLen], rax
0x180008364  mov     dword ptr [rsp+58h+pbData], 371h
0x18000836c  jmp     loc_1800083F1
0x180008371  mov     rcx, rax; unsigned __int64
0x180008374  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000837b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008380  mov     [rdi+8], rax
0x180008384  mov     rcx, rax; Destination
0x180008387  test    rax, rax
0x18000838a  jnz     short loc_1800083B4
0x18000838c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008393  mov     r8d, 8007000Eh
0x180008399  mov     ebx, r8d
0x18000839c  jz      short loc_1800083FD
0x18000839e  lea     rax, aCprPblobdecryp; "CPR(pblobDecrypted->pbData)"
0x1800083a5  mov     [rsp+58h+pdwDataLen], rax
0x1800083aa  mov     dword ptr [rsp+58h+pbData], 375h
0x1800083b2  jmp     short loc_1800083F1
0x1800083b4  mov     eax, dword ptr [rsp+58h+DestinationSize]
0x1800083b8  mov     r8, rsi; Source
0x1800083bb  mov     edx, eax; DestinationSize
0x1800083bd  mov     [rdi], eax
0x1800083bf  mov     r9d, eax; SourceSize
0x1800083c2  call    memcpy_s
0x1800083c7  test    eax, eax
0x1800083c9  jz      short loc_18000841B
0x1800083cb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800083d2  mov     r8d, 80004005h
0x1800083d8  mov     ebx, r8d
0x1800083db  jz      short loc_1800083FD
0x1800083dd  lea     rax, aCbrMemcpySPblo; "CBR(memcpy_s(pblobDecrypted->pbData, dw"...
0x1800083e4  mov     [rsp+58h+pdwDataLen], rax
0x1800083e9  mov     dword ptr [rsp+58h+pbData], 377h
0x1800083f1  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800083f8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800083fd  mov     rcx, [rdi+8]; void *
0x180008401  test    rcx, rcx
0x180008404  jz      short loc_18000841D
0x180008406  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000840b  mov     qword ptr [rdi+8], 0
0x180008413  mov     dword ptr [rdi], 0
0x180008419  jmp     short loc_18000841D
0x18000841b  xor     ebx, ebx
0x18000841d  mov     rcx, rsi; void *
0x180008420  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008425  mov     eax, ebx
0x180008427  add     rsp, 38h
0x18000842b  pop     rdi
0x18000842c  pop     rsi
0x18000842d  pop     rbp
0x18000842e  pop     rbx
0x18000842f  retn
```
