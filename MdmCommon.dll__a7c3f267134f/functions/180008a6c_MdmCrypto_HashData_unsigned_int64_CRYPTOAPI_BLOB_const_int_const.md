# MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)

- ea: `0x180008a6c`
- end: `0x180008bd9`
- name: `?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z`
- size: `365`
- prototype: `__int64 __fastcall(HCRYPTHASH hHash, const struct _CRYPTOAPI_BLOB *, const int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007974`
- `0x180008438`

## callees

- `0x1800065c0`
- `0x180008a6c`
- `0x180008efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008bba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008bba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008b54`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008b54`

## string_xrefs

- `0x180008b9f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

## pseudocode

```c
__int64 __fastcall MdmCrypto::HashData(HCRYPTHASH hHash, const struct _CRYPTOAPI_BLOB *a2, const int *a3)
{
  BYTE *pbData; // rdx
  signed int v7; // ebx
  DWORD cbData; // r8d
  int v9; // edx
  int v10; // ecx
  signed int LastError; // eax
  char v13; // [rsp+20h] [rbp-28h]
  const char *v14; // [rsp+28h] [rbp-20h]
  HLOCAL hMem[3]; // [rsp+30h] [rbp-18h] BYREF

  pbData = a2->pbData;
  *(_OWORD *)hMem = 0;
  if ( !pbData )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        hHash,
        0,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        135,
        "CPR(blobToHash.pbData)",
        hMem[0]);
    goto LABEL_19;
  }
  cbData = a2->cbData;
  if ( !a2->cbData )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        hHash,
        (_DWORD)pbData,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        136,
        "CBR(blobToHash.cbData > 0)",
        hMem[0]);
    goto LABEL_19;
  }
  if ( *a3 )
  {
    v7 = MdmCrypto::UnprotectData(a2, (struct _CRYPTOAPI_BLOB *)hMem);
    if ( v7 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_19;
      v14 = "CHR(UnprotectData(blobToHash, &blobHash))";
      v13 = -115;
LABEL_18:
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        v7,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        v13,
        v14,
        hMem[0]);
      goto LABEL_19;
    }
    pbData = (BYTE *)hMem[1];
    cbData = (DWORD)hMem[0];
  }
  else
  {
    v7 = 0;
    LODWORD(hMem[0]) = a2->cbData;
    hMem[1] = pbData;
  }
  if ( !CryptHashData(hHash, pbData, cbData, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v14 = "CBR(CryptHashData(hHash, blobHash.pbData, blobHash.cbData, 0))";
      v13 = -102;
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( *a3 && hMem[1] )
    LocalFree(hMem[1]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008a6c  mov     [rsp+arg_0], rbx
0x180008a71  mov     [rsp+arg_8], rsi
0x180008a76  push    rdi
0x180008a77  sub     rsp, 40h
0x180008a7b  mov     rax, rdx
0x180008a7e  xorps   xmm0, xmm0
0x180008a81  mov     rdx, [rdx+8]; pbData
0x180008a85  mov     rdi, r8
0x180008a88  mov     rsi, rcx
0x180008a8b  movups  xmmword ptr [rsp+48h+hMem], xmm0
0x180008a90  test    rdx, rdx
0x180008a93  jnz     short loc_180008AC4
0x180008a95  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008a9c  mov     r8d, 80070057h
0x180008aa2  mov     ebx, r8d
0x180008aa5  jz      loc_180008BAB
0x180008aab  lea     rax, aCprBlobtohashP; "CPR(blobToHash.pbData)"
0x180008ab2  mov     [rsp+48h+var_20], rax
0x180008ab7  mov     dword ptr [rsp+48h+var_28], 287h
0x180008abf  jmp     loc_180008B9F
0x180008ac4  mov     r8d, [rax]; dwDataLen
0x180008ac7  test    r8d, r8d
0x180008aca  jnz     short loc_180008AFB
0x180008acc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008ad3  mov     r8d, 80070057h
0x180008ad9  mov     ebx, r8d
0x180008adc  jz      loc_180008BAB
0x180008ae2  lea     rax, aCbrBlobtohashC; "CBR(blobToHash.cbData > 0)"
0x180008ae9  mov     [rsp+48h+var_20], rax
0x180008aee  mov     dword ptr [rsp+48h+var_28], 288h
0x180008af6  jmp     loc_180008B9F
0x180008afb  cmp     dword ptr [rdi], 0
0x180008afe  jz      short loc_180008B42
0x180008b00  lea     rdx, [rsp+48h+hMem]; struct _CRYPTOAPI_BLOB *
0x180008b05  mov     rcx, rax; struct _CRYPTOAPI_BLOB *
0x180008b08  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x180008b0d  mov     ebx, eax
0x180008b0f  test    eax, eax
0x180008b11  jns     short loc_180008B36
0x180008b13  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008b1a  jz      loc_180008BAB
0x180008b20  lea     rax, aChrUnprotectda_0; "CHR(UnprotectData(blobToHash, &blobHash"...
0x180008b27  mov     [rsp+48h+var_20], rax
0x180008b2c  mov     dword ptr [rsp+48h+var_28], 28Dh
0x180008b34  jmp     short loc_180008B9C
0x180008b36  mov     rdx, [rsp+48h+hMem+8]
0x180008b3b  mov     r8d, dword ptr [rsp+48h+hMem]
0x180008b40  jmp     short loc_180008B4E
0x180008b42  xor     ebx, ebx
0x180008b44  mov     dword ptr [rsp+48h+hMem], r8d
0x180008b49  mov     [rsp+48h+hMem+8], rdx
0x180008b4e  xor     r9d, r9d; dwFlags
0x180008b51  mov     rcx, rsi; hHash
0x180008b54  call    cs:__imp_CryptHashData
0x180008b5b  nop     dword ptr [rax+rax+00h]
0x180008b60  test    eax, eax
0x180008b62  jnz     short loc_180008BAB
0x180008b64  call    cs:__imp_GetLastError
0x180008b6b  nop     dword ptr [rax+rax+00h]
0x180008b70  mov     ebx, eax
0x180008b72  test    eax, eax
0x180008b74  jle     short loc_180008B7F
0x180008b76  movzx   ebx, ax
0x180008b79  or      ebx, 80070000h
0x180008b7f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008b86  jz      short loc_180008BAB
0x180008b88  lea     rax, aCbrCrypthashda_0; "CBR(CryptHashData(hHash, blobHash.pbDat"...
0x180008b8f  mov     [rsp+48h+var_20], rax
0x180008b94  mov     dword ptr [rsp+48h+var_28], 29Ah
0x180008b9c  mov     r8d, ebx
0x180008b9f  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008ba6  call    McTemplateU0dsqs_EventWriteTransfer
0x180008bab  cmp     dword ptr [rdi], 0
0x180008bae  jz      short loc_180008BC6
0x180008bb0  mov     rcx, [rsp+48h+hMem+8]; hMem
0x180008bb5  test    rcx, rcx
0x180008bb8  jz      short loc_180008BC6
0x180008bba  call    cs:__imp_LocalFree
0x180008bc1  nop     dword ptr [rax+rax+00h]
0x180008bc6  mov     rsi, [rsp+48h+arg_8]
0x180008bcb  mov     eax, ebx
0x180008bcd  mov     rbx, [rsp+48h+arg_0]
0x180008bd2  add     rsp, 40h
0x180008bd6  pop     rdi
0x180008bd7  retn
```
