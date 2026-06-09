# MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)

- ea: `0x180008910`
- end: `0x180008a66`
- name: `?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z`
- size: `342`
- prototype: `__int64 __fastcall(HCRYPTHASH hHash, const struct _CRYPTOAPI_BLOB *, const int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800078ec`
- `0x180008328`

## callees

- `0x180006548`
- `0x180008910`
- `0x180008d58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a4e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800089f4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800089f4`

## string_xrefs

- `0x180008a33`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`

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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
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
0x180008910  mov     [rsp+arg_0], rbx
0x180008915  mov     [rsp+arg_8], rsi
0x18000891a  push    rdi
0x18000891b  sub     rsp, 40h
0x18000891f  mov     rax, rdx
0x180008922  xorps   xmm0, xmm0
0x180008925  mov     rdx, [rdx+8]; pbData
0x180008929  mov     rdi, r8
0x18000892c  mov     rsi, rcx
0x18000892f  movups  xmmword ptr [rsp+48h+hMem], xmm0
0x180008934  test    rdx, rdx
0x180008937  jnz     short loc_180008968
0x180008939  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008940  mov     r8d, 80070057h
0x180008946  mov     ebx, r8d
0x180008949  jz      loc_180008A3F
0x18000894f  lea     rax, aCprBlobtohashP; "CPR(blobToHash.pbData)"
0x180008956  mov     [rsp+48h+var_20], rax
0x18000895b  mov     dword ptr [rsp+48h+var_28], 287h
0x180008963  jmp     loc_180008A33
0x180008968  mov     r8d, [rax]; dwDataLen
0x18000896b  test    r8d, r8d
0x18000896e  jnz     short loc_18000899F
0x180008970  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008977  mov     r8d, 80070057h
0x18000897d  mov     ebx, r8d
0x180008980  jz      loc_180008A3F
0x180008986  lea     rax, aCbrBlobtohashC; "CBR(blobToHash.cbData > 0)"
0x18000898d  mov     [rsp+48h+var_20], rax
0x180008992  mov     dword ptr [rsp+48h+var_28], 288h
0x18000899a  jmp     loc_180008A33
0x18000899f  cmp     dword ptr [rdi], 0
0x1800089a2  jz      short loc_1800089E2
0x1800089a4  lea     rdx, [rsp+48h+hMem]; struct _CRYPTOAPI_BLOB *
0x1800089a9  mov     rcx, rax; struct _CRYPTOAPI_BLOB *
0x1800089ac  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x1800089b1  mov     ebx, eax
0x1800089b3  test    eax, eax
0x1800089b5  jns     short loc_1800089D6
0x1800089b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800089be  jz      short loc_180008A3F
0x1800089c0  lea     rax, aChrUnprotectda_0; "CHR(UnprotectData(blobToHash, &blobHash"...
0x1800089c7  mov     [rsp+48h+var_20], rax
0x1800089cc  mov     dword ptr [rsp+48h+var_28], 28Dh
0x1800089d4  jmp     short loc_180008A30
0x1800089d6  mov     rdx, [rsp+48h+hMem+8]
0x1800089db  mov     r8d, dword ptr [rsp+48h+hMem]
0x1800089e0  jmp     short loc_1800089EE
0x1800089e2  xor     ebx, ebx
0x1800089e4  mov     dword ptr [rsp+48h+hMem], r8d
0x1800089e9  mov     [rsp+48h+hMem+8], rdx
0x1800089ee  xor     r9d, r9d; dwFlags
0x1800089f1  mov     rcx, rsi; hHash
0x1800089f4  call    cs:__imp_CryptHashData
0x1800089fa  test    eax, eax
0x1800089fc  jnz     short loc_180008A3F
0x1800089fe  call    cs:__imp_GetLastError
0x180008a04  mov     ebx, eax
0x180008a06  test    eax, eax
0x180008a08  jle     short loc_180008A13
0x180008a0a  movzx   ebx, ax
0x180008a0d  or      ebx, 80070000h
0x180008a13  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008a1a  jz      short loc_180008A3F
0x180008a1c  lea     rax, aCbrCrypthashda_0; "CBR(CryptHashData(hHash, blobHash.pbDat"...
0x180008a23  mov     [rsp+48h+var_20], rax
0x180008a28  mov     dword ptr [rsp+48h+var_28], 29Ah
0x180008a30  mov     r8d, ebx
0x180008a33  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008a3a  call    McTemplateU0dsqs_EventWriteTransfer
0x180008a3f  cmp     dword ptr [rdi], 0
0x180008a42  jz      short loc_180008A54
0x180008a44  mov     rcx, [rsp+48h+hMem+8]; hMem
0x180008a49  test    rcx, rcx
0x180008a4c  jz      short loc_180008A54
0x180008a4e  call    cs:__imp_LocalFree
0x180008a54  mov     rsi, [rsp+48h+arg_8]
0x180008a59  mov     eax, ebx
0x180008a5b  mov     rbx, [rsp+48h+arg_0]
0x180008a60  add     rsp, 40h
0x180008a64  pop     rdi
0x180008a65  retn
```
