# MdmCrypto::Decrypt(unsigned __int64,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008050`
- end: `0x180008320`
- name: `?Decrypt@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z`
- size: `720`
- prototype: `__int64 __fastcall(HCRYPTKEY hKey, const struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008328`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180006548`
- `0x180006620`
- `0x180008050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x1800081ca`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x1800081ca`

## string_xrefs

- `0x18000809c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008106`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008201`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x1800082e1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008150`: `CPR(pbTempData)`
- `0x180008196`: `CBR(memcpy_s(pbTempData, dwSize, blobEncrypted.pbData, blobEncrypted.cbData) == 0)`
- `0x1800081f2`: `CBR(CryptDecrypt(hKey, 0, 1, 0, pbTempData, &dwSize))`
- `0x1800082cd`: `CBR(memcpy_s(pblobDecrypted->pbData, dwSize, pbTempData, dwSize) == 0)`

## pseudocode

```c
__int64 __fastcall MdmCrypto::Decrypt(HCRYPTKEY hKey, const struct _CRYPTOAPI_BLOB *a2, struct _CRYPTOAPI_BLOB *a3)
{
  void *pbData; // rsi
  signed int v7; // ebx
  void *v8; // rax
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  signed int LastError; // eax
  int v16; // edx
  int v17; // ecx
  BYTE *v18; // rax
  int v19; // edx
  BYTE *v20; // rcx
  unsigned int v21; // eax
  rsize_t v22; // rdx
  int v23; // edx
  int v24; // ecx
  BYTE *v25; // rcx
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
        v10,
        v9,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        101,
        "CPR(pbTempData)");
LABEL_34:
    v25 = a3->pbData;
    if ( v25 )
    {
      operator delete(v25);
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
        v12,
        v11,
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
      v18 = (BYTE *)operator new[]((unsigned int)DestinationSize, (const struct std::nothrow_t *)&std::nothrow);
      a3->pbData = v18;
      v20 = v18;
      if ( v18 )
      {
        v21 = DestinationSize;
        v22 = (unsigned int)DestinationSize;
        a3->cbData = DestinationSize;
        if ( !memcpy_s(v20, v22, pbData, v21) )
        {
          v7 = 0;
          goto LABEL_37;
        }
        v7 = -2147467259;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v24,
            v23,
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
            v19,
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
          v14,
          v13,
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
      v17,
      v16,
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
  operator delete(pbData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008050  push    rbx
0x180008052  push    rbp
0x180008053  push    rsi
0x180008054  push    rdi
0x180008055  sub     rsp, 38h
0x180008059  xor     esi, esi
0x18000805b  mov     dword ptr [rsp+58h+DestinationSize], 0
0x180008063  mov     rdi, r8
0x180008066  mov     rbx, rdx
0x180008069  mov     rbp, rcx
0x18000806c  cmp     [rdx+8], rsi
0x180008070  jnz     short loc_1800080AD
0x180008072  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008079  mov     r8d, 80070057h
0x18000807f  mov     ebx, r8d
0x180008082  jz      loc_18000821D
0x180008088  lea     rax, aCprBlobencrypt_0; "CPR(blobEncrypted.pbData)"
0x18000808f  mov     [rsp+58h+pdwDataLen], rax
0x180008094  mov     dword ptr [rsp+58h+pbData], 35Eh
0x18000809c  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800080a3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800080a8  jmp     loc_18000821D
0x1800080ad  mov     eax, [rdx]
0x1800080af  test    eax, eax
0x1800080b1  jnz     short loc_1800080DF
0x1800080b3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800080ba  mov     r8d, 80070057h
0x1800080c0  mov     ebx, r8d
0x1800080c3  jz      loc_18000821D
0x1800080c9  lea     rax, aCbrBlobencrypt; "CBR(blobEncrypted.cbData > 0)"
0x1800080d0  mov     [rsp+58h+pdwDataLen], rax
0x1800080d5  mov     dword ptr [rsp+58h+pbData], 35Fh
0x1800080dd  jmp     short loc_18000809C
0x1800080df  test    rdi, rdi
0x1800080e2  jnz     short loc_18000811F
0x1800080e4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800080eb  mov     r8d, 80070057h
0x1800080f1  mov     ebx, r8d
0x1800080f4  jz      loc_18000830D
0x1800080fa  lea     rax, aCprPblobdecryp_0; "CPR(pblobDecrypted)"
0x180008101  mov     [rsp+58h+pdwDataLen], rax
0x180008106  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000810d  mov     dword ptr [rsp+58h+pbData], 360h
0x180008115  call    McTemplateU0dsqs_EventWriteTransfer
0x18000811a  jmp     loc_18000830D
0x18000811f  mov     rcx, rax; unsigned __int64
0x180008122  mov     dword ptr [rsp+58h+DestinationSize], eax
0x180008126  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000812d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008132  mov     rsi, rax
0x180008135  test    rax, rax
0x180008138  jnz     short loc_180008169
0x18000813a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008141  mov     r8d, 8007000Eh
0x180008147  mov     ebx, r8d
0x18000814a  jz      loc_1800082ED
0x180008150  lea     rax, aCprPbtempdata; "CPR(pbTempData)"
0x180008157  mov     [rsp+58h+pdwDataLen], rax
0x18000815c  mov     dword ptr [rsp+58h+pbData], 365h
0x180008164  jmp     loc_1800082E1
0x180008169  mov     r9d, [rbx]; SourceSize
0x18000816c  mov     rcx, rsi; Destination
0x18000816f  mov     edx, dword ptr [rsp+58h+DestinationSize]; DestinationSize
0x180008173  mov     r8, [rbx+8]; Source
0x180008177  call    memcpy_s
0x18000817c  test    eax, eax
0x18000817e  jz      short loc_1800081AF
0x180008180  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008187  mov     r8d, 80004005h
0x18000818d  mov     ebx, r8d
0x180008190  jz      loc_1800082ED
0x180008196  lea     rax, aCbrMemcpySPbte; "CBR(memcpy_s(pbTempData, dwSize, blobEn"...
0x18000819d  mov     [rsp+58h+pdwDataLen], rax
0x1800081a2  mov     dword ptr [rsp+58h+pbData], 366h
0x1800081aa  jmp     loc_1800082E1
0x1800081af  xor     r9d, r9d; dwFlags
0x1800081b2  lea     rax, [rsp+58h+DestinationSize]
0x1800081b7  mov     [rsp+58h+pdwDataLen], rax; pdwDataLen
0x1800081bc  xor     edx, edx; hHash
0x1800081be  mov     rcx, rbp; hKey
0x1800081c1  mov     [rsp+58h+pbData], rsi; pbData
0x1800081c6  lea     r8d, [r9+1]; Final
0x1800081ca  call    cs:__imp_CryptDecrypt
0x1800081d0  test    eax, eax
0x1800081d2  jnz     short loc_18000822B
0x1800081d4  call    cs:__imp_GetLastError
0x1800081da  mov     ebx, eax
0x1800081dc  test    eax, eax
0x1800081de  jle     short loc_1800081E9
0x1800081e0  movzx   ebx, ax
0x1800081e3  or      ebx, 80070000h
0x1800081e9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800081f0  jz      short loc_180008215
0x1800081f2  lea     rax, aCbrCryptdecryp; "CBR(CryptDecrypt(hKey, 0, 1, 0, pbTempD"...
0x1800081f9  mov     r8d, ebx
0x1800081fc  mov     [rsp+58h+pdwDataLen], rax
0x180008201  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008208  mov     dword ptr [rsp+58h+pbData], 36Fh
0x180008210  call    McTemplateU0dsqs_EventWriteTransfer
0x180008215  test    ebx, ebx
0x180008217  jns     loc_18000830D
0x18000821d  test    rdi, rdi
0x180008220  jz      loc_18000830D
0x180008226  jmp     loc_1800082ED
0x18000822b  mov     eax, dword ptr [rsp+58h+DestinationSize]
0x18000822f  test    eax, eax
0x180008231  jnz     short loc_180008261
0x180008233  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000823a  mov     ebx, 8000FFFFh
0x18000823f  jz      loc_1800082ED
0x180008245  lea     rax, aCbrDwsize0; "CBR(dwSize > 0)"
0x18000824c  mov     r8d, ebx
0x18000824f  mov     [rsp+58h+pdwDataLen], rax
0x180008254  mov     dword ptr [rsp+58h+pbData], 371h
0x18000825c  jmp     loc_1800082E1
0x180008261  mov     rcx, rax; unsigned __int64
0x180008264  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000826b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008270  mov     [rdi+8], rax
0x180008274  mov     rcx, rax; Destination
0x180008277  test    rax, rax
0x18000827a  jnz     short loc_1800082A4
0x18000827c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008283  mov     r8d, 8007000Eh
0x180008289  mov     ebx, r8d
0x18000828c  jz      short loc_1800082ED
0x18000828e  lea     rax, aCprPblobdecryp; "CPR(pblobDecrypted->pbData)"
0x180008295  mov     [rsp+58h+pdwDataLen], rax
0x18000829a  mov     dword ptr [rsp+58h+pbData], 375h
0x1800082a2  jmp     short loc_1800082E1
0x1800082a4  mov     eax, dword ptr [rsp+58h+DestinationSize]
0x1800082a8  mov     r8, rsi; Source
0x1800082ab  mov     edx, eax; DestinationSize
0x1800082ad  mov     [rdi], eax
0x1800082af  mov     r9d, eax; SourceSize
0x1800082b2  call    memcpy_s
0x1800082b7  test    eax, eax
0x1800082b9  jz      short loc_18000830B
0x1800082bb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800082c2  mov     r8d, 80004005h
0x1800082c8  mov     ebx, r8d
0x1800082cb  jz      short loc_1800082ED
0x1800082cd  lea     rax, aCbrMemcpySPblo; "CBR(memcpy_s(pblobDecrypted->pbData, dw"...
0x1800082d4  mov     [rsp+58h+pdwDataLen], rax
0x1800082d9  mov     dword ptr [rsp+58h+pbData], 377h
0x1800082e1  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800082e8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800082ed  mov     rcx, [rdi+8]; void *
0x1800082f1  test    rcx, rcx
0x1800082f4  jz      short loc_18000830D
0x1800082f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800082fb  mov     qword ptr [rdi+8], 0
0x180008303  mov     dword ptr [rdi], 0
0x180008309  jmp     short loc_18000830D
0x18000830b  xor     ebx, ebx
0x18000830d  mov     rcx, rsi; void *
0x180008310  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008315  mov     eax, ebx
0x180008317  add     rsp, 38h
0x18000831b  pop     rdi
0x18000831c  pop     rsi
0x18000831d  pop     rbp
0x18000831e  pop     rbx
0x18000831f  retn
```
