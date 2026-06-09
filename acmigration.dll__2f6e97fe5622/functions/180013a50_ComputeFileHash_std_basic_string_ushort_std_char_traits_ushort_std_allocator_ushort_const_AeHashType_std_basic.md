# ComputeFileHash(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_AeHashType,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013a50`
- end: `0x1800141d3`
- name: `?ComputeFileHash@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4_AeHashType@@AEAV12@@Z`
- size: `1923`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001540c`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000c190`
- `0x180013a50`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180013eac`
- `KERNEL32!UnmapViewOfFile` at `0x180013fbb`
- `KERNEL32!UnmapViewOfFile` at `0x180014154`
- `KERNEL32!UnmapViewOfFile` at `0x180013eac`
- `KERNEL32!UnmapViewOfFile` at `0x180013fbb`
- `KERNEL32!UnmapViewOfFile` at `0x180014154`
- `KERNEL32!MapViewOfFile` at `0x180013dfa`
- `KERNEL32!MapViewOfFile` at `0x180013f03`
- `KERNEL32!MapViewOfFile` at `0x180013dfa`
- `KERNEL32!MapViewOfFile` at `0x180013f03`
- `KERNEL32!CreateFileMappingW` at `0x180013cc5`
- `KERNEL32!CreateFileMappingW` at `0x180013cc5`
- `KERNEL32!GetFileSize` at `0x180013bc9`
- `KERNEL32!GetFileSize` at `0x180013bc9`
- `KERNEL32!CreateFileW` at `0x180013b53`
- `KERNEL32!CreateFileW` at `0x180013b53`
- `KERNEL32!CloseHandle` at `0x18001418f`
- `KERNEL32!CloseHandle` at `0x18001419e`
- `KERNEL32!CloseHandle` at `0x18001418f`
- `KERNEL32!CloseHandle` at `0x18001419e`
- `KERNEL32!GetLastError` at `0x180013b66`
- `KERNEL32!GetLastError` at `0x180013d41`
- `KERNEL32!GetLastError` at `0x180013d9e`
- `KERNEL32!GetLastError` at `0x180013e0d`
- `KERNEL32!GetLastError` at `0x180013e69`
- `KERNEL32!GetLastError` at `0x180013f16`
- `KERNEL32!GetLastError` at `0x180013f73`
- `KERNEL32!GetLastError` at `0x180013fee`
- `KERNEL32!GetLastError` at `0x180014110`
- `KERNEL32!GetLastError` at `0x180013b66`
- `KERNEL32!GetLastError` at `0x180013d41`
- `KERNEL32!GetLastError` at `0x180013d9e`
- `KERNEL32!GetLastError` at `0x180013e0d`
- `KERNEL32!GetLastError` at `0x180013e69`
- `KERNEL32!GetLastError` at `0x180013f16`
- `KERNEL32!GetLastError` at `0x180013f73`
- `KERNEL32!GetLastError` at `0x180013fee`
- `KERNEL32!GetLastError` at `0x180014110`
- `ADVAPI32!CryptAcquireContextW` at `0x180013d37`
- `ADVAPI32!CryptAcquireContextW` at `0x180013d37`
- `ADVAPI32!CryptCreateHash` at `0x180013d94`
- `ADVAPI32!CryptCreateHash` at `0x180013d94`
- `ADVAPI32!CryptHashData` at `0x180013e5f`
- `ADVAPI32!CryptHashData` at `0x180013f69`
- `ADVAPI32!CryptHashData` at `0x180013e5f`
- `ADVAPI32!CryptHashData` at `0x180013f69`
- `ADVAPI32!CryptGetHashParam` at `0x180013fe4`
- `ADVAPI32!CryptGetHashParam` at `0x180013fe4`
- `ADVAPI32!CryptDestroyHash` at `0x180014164`
- `ADVAPI32!CryptDestroyHash` at `0x180014164`
- `ADVAPI32!CryptReleaseContext` at `0x18001417b`
- `ADVAPI32!CryptReleaseContext` at `0x18001417b`

## string_xrefs

- `0x180013b81`: `CreateFile failed (error code=%d) (path=%S).`
- `0x180013b8e`: `ComputeFileHash`
- `0x180013d67`: `ComputeFileHash`
- `0x180013e37`: `ComputeFileHash`
- `0x180013e93`: `ComputeFileHash`
- `0x180013f40`: `ComputeFileHash`
- `0x180013f9d`: `ComputeFileHash`
- `0x1800140d9`: `ComputeFileHash`
- `0x180014129`: `ComputeFileHash`
- `0x18001411c`: `CreateFileMapping failed (error code=%d).`

## pseudocode

```c
__int64 __fastcall ComputeFileHash(LPCWSTR lpFileName, int a2, _QWORD *a3)
{
  DWORD v6; // r13d
  const BYTE *v7; // r12
  __int64 v8; // r15
  signed int v9; // edi
  __int64 v10; // rbx
  const WCHAR *v11; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v14; // ebx
  _WORD *v15; // rbx
  _WORD *v16; // rbx
  _WORD *v17; // rbx
  int v18; // ebx
  const WCHAR *v19; // r8
  ALG_ID v20; // ebx
  DWORD v21; // r9d
  signed int v22; // eax
  const char *v23; // r9
  __int64 v24; // r8
  signed int v25; // eax
  DWORD v26; // r8d
  const BYTE *v27; // rax
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // ebx
  const BYTE *v31; // rax
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  unsigned __int64 v35; // rdx
  unsigned __int64 i; // r8
  BYTE v37; // cl
  unsigned __int64 v38; // rdx
  _WORD *v39; // rdi
  __int64 v40; // rbx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-168h]
  __int64 hFileMappingObject; // [rsp+40h] [rbp-148h]
  __int64 v44; // [rsp+50h] [rbp-138h]
  DWORD FileSizeHigh[2]; // [rsp+58h] [rbp-130h] BYREF
  const BYTE *v46; // [rsp+60h] [rbp-128h]
  HCRYPTHASH phHash; // [rsp+68h] [rbp-120h] BYREF
  DWORD pdwDataLen; // [rsp+70h] [rbp-118h] BYREF
  HCRYPTPROV phProv; // [rsp+78h] [rbp-110h] BYREF
  __int64 v50; // [rsp+80h] [rbp-108h]
  DWORD dwFileOffsetHigh[4]; // [rsp+88h] [rbp-100h]
  __int64 v52; // [rsp+98h] [rbp-F0h]
  BYTE pbData[16]; // [rsp+A0h] [rbp-E8h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-D8h]
  _WORD Src[72]; // [rsp+C0h] [rbp-C8h] BYREF

  hFileMappingObject = -1;
  FileSizeHigh[1] = 0;
  v6 = 0;
  v44 = 0;
  *(_QWORD *)dwFileOffsetHigh = 0;
  v7 = 0;
  v46 = 0;
  phProv = 0;
  phHash = 0;
  *(_OWORD *)pbData = 0;
  v54 = 0;
  pdwDataLen = 32;
  memset_0(Src, 0, 0x82u);
  if ( !*((_QWORD *)lpFileName + 2) )
  {
    v8 = -1;
    v9 = -2147024809;
    v10 = -1;
    goto LABEL_85;
  }
  if ( (_DWORD)dwDataLen )
  {
    if ( (unsigned int)dwDataLen > 0x40000000 )
      LODWORD(dwDataLen) = 0x40000000;
  }
  else
  {
    LODWORD(dwDataLen) = 0x2000000;
  }
  if ( *((_QWORD *)lpFileName + 3) <= 7u )
    v11 = lpFileName;
  else
    v11 = *(const WCHAR **)lpFileName;
  FileW = CreateFileW(v11, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v50 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( *((_QWORD *)lpFileName + 3) > 7u )
      lpFileName = *(LPCWSTR *)lpFileName;
    AslLogCallPrintf(1, "ComputeFileHash", 743, "CreateFile failed (error code=%d) (path=%S).", LastError, lpFileName);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v8 = v50;
    goto LABEL_84;
  }
  v9 = -2147467259;
  v8 = (__int64)FileW;
  FileSizeHigh[0] = GetFileSize(FileW, &FileSizeHigh[1]);
  if ( !*(_QWORD *)FileSizeHigh )
  {
    if ( a2 )
    {
      v14 = a2 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
LABEL_84:
          v10 = hFileMappingObject;
          goto LABEL_85;
        }
        if ( a3[3] >= 0x40u )
        {
          v15 = (_WORD *)*a3;
          a3[2] = 64;
          memmove_0(v15, L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855", 0x80u);
          v15[64] = 0;
          goto LABEL_84;
        }
      }
      else if ( a3[3] >= 0x28u )
      {
        v16 = (_WORD *)*a3;
        a3[2] = 40;
        memmove_0(v16, L"da39a3ee5e6b4b0d3255bfef95601890afd80709", 0x50u);
        v16[40] = 0;
        goto LABEL_84;
      }
    }
    else if ( a3[3] >= 0x20u )
    {
      v17 = (_WORD *)*a3;
      a3[2] = 32;
      memmove_0(v17, L"d41d8cd98f00b204e9800998ecf8427e", 0x40u);
      v17[32] = 0;
      goto LABEL_84;
    }
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a3);
    goto LABEL_84;
  }
  hFileMappingObject = (__int64)CreateFileMappingW((HANDLE)v8, 0, 0x8000002u, 0, 0, 0);
  v52 = hFileMappingObject;
  if ( (unsigned __int64)(hFileMappingObject - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = GetLastError();
    AslLogCallPrintf(1, "ComputeFileHash", 785, "CreateFileMapping failed (error code=%d).", v9);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_84;
  }
  if ( !a2 )
  {
    v19 = 0;
    v20 = 32771;
    goto LABEL_36;
  }
  v18 = a2 - 1;
  if ( !v18 )
  {
    v19 = L"Microsoft Base Cryptographic Provider v1.0";
    v20 = 32772;
LABEL_36:
    v21 = 1;
    goto LABEL_37;
  }
  if ( v18 != 1 )
    goto LABEL_84;
  v19 = L"Microsoft Enhanced RSA and AES Cryptographic Provider";
  v20 = 32780;
  v21 = 24;
LABEL_37:
  if ( !CryptAcquireContextW(&phProv, 0, v19, v21, 0xF0000000) )
  {
    v22 = GetLastError();
    v9 = v22;
    if ( v22 > 0 )
      v9 = (unsigned __int16)v22 | 0x80070000;
    v23 = "Failed acquiring the crypto context with 0x%x";
    v24 = 822;
LABEL_41:
    dwCreationDisposition[0] = v9;
    AslLogCallPrintf(1, "ComputeFileHash", v24, v23, *(_QWORD *)dwCreationDisposition);
    goto LABEL_84;
  }
  if ( !CryptCreateHash(phProv, v20, 0, 0, &phHash) )
  {
    v25 = GetLastError();
    v9 = v25;
    if ( v25 > 0 )
      v9 = (unsigned __int16)v25 | 0x80070000;
    v23 = "Failed creating SHA1 hash object with 0x%x";
    v24 = 834;
    goto LABEL_41;
  }
  v26 = dwFileOffsetHigh[0];
  v10 = hFileMappingObject;
  while ( *(_QWORD *)FileSizeHigh - v44 > (unsigned __int64)(unsigned int)dwDataLen )
  {
    v27 = (const BYTE *)MapViewOfFile((HANDLE)hFileMappingObject, 4u, v26, v6, (unsigned int)dwDataLen);
    v7 = v27;
    v46 = v27;
    if ( !v27 )
    {
      v28 = GetLastError();
      v9 = v28;
      if ( v28 > 0 )
        v9 = (unsigned __int16)v28 | 0x80070000;
      AslLogCallPrintf(1, "ComputeFileHash", 855, "MapViewOfFile failed with 0x%x.", v9);
      goto LABEL_85;
    }
    if ( !CryptHashData(phHash, v27, dwDataLen, 0) )
    {
      v29 = GetLastError();
      v9 = v29;
      if ( v29 > 0 )
        v9 = (unsigned __int16)v29 | 0x80070000;
      AslLogCallPrintf(1, "ComputeFileHash", 865, "Failed hashing data (SHA1) with 0x%x", v9);
      goto LABEL_85;
    }
    UnmapViewOfFile(v7);
    v46 = 0;
    v44 += (unsigned int)dwDataLen;
    v26 = HIDWORD(v44);
    v6 = v44;
  }
  v30 = FileSizeHigh[0] - v6;
  v7 = 0;
  v46 = 0;
  if ( (int)(FileSizeHigh[0] - v6) <= 0 )
  {
LABEL_67:
    if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
    {
      v35 = 0;
      for ( i = pdwDataLen; v35 < i; Src[2 * v35++ + 1] = a0123456789abcd[v37 & 0xF] )
      {
        v37 = pbData[v35];
        Src[2 * v35] = a0123456789abcd[(unsigned __int64)v37 >> 4];
      }
      Src[2 * v35] = 0;
      v38 = -1;
      do
        ++v38;
      while ( Src[v38] );
      if ( v38 > a3[3] )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a3);
      }
      else
      {
        if ( a3[3] <= 7u )
          v39 = a3;
        else
          v39 = (_WORD *)*a3;
        a3[2] = v38;
        v40 = v38;
        memmove_0(v39, Src, 2 * v38);
        v39[v40] = 0;
      }
      AslLogCallPrintf(3, "ComputeFileHash", 937, "Hash is %ws", Src);
      v9 = 0;
      goto LABEL_84;
    }
    v34 = GetLastError();
    v9 = v34;
    if ( v34 > 0 )
      v9 = (unsigned __int16)v34 | 0x80070000;
    v23 = "Failed to retrieve hash (SHA1) value: 0x%x";
    v24 = 921;
    goto LABEL_41;
  }
  v31 = (const BYTE *)MapViewOfFile((HANDLE)hFileMappingObject, 4u, HIDWORD(v44), v6, v30);
  v7 = v31;
  v46 = v31;
  if ( !v31 )
  {
    v32 = GetLastError();
    v9 = v32;
    if ( v32 > 0 )
      v9 = (unsigned __int16)v32 | 0x80070000;
    AslLogCallPrintf(1, "ComputeFileHash", 890, "MapViewOfFile failed with 0x%x.", v9);
    v10 = hFileMappingObject;
    goto LABEL_85;
  }
  if ( CryptHashData(phHash, v31, v30, 0) )
  {
    UnmapViewOfFile(v7);
    v7 = 0;
    v46 = 0;
    goto LABEL_67;
  }
  v33 = GetLastError();
  v9 = v33;
  if ( v33 > 0 )
    v9 = (unsigned __int16)v33 | 0x80070000;
  AslLogCallPrintf(1, "ComputeFileHash", 900, "Failed hashing data (SHA1) with 0x%x", v9);
  v10 = hFileMappingObject;
LABEL_85:
  if ( v7 )
    UnmapViewOfFile(v7);
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv )
  {
    CryptReleaseContext(phProv, 0);
    phProv = 0;
  }
  if ( v10 != -1 )
    CloseHandle((HANDLE)v10);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013a50  mov     [rsp+arg_8], rbx
0x180013a55  mov     [rsp+arg_18], rsi
0x180013a5a  push    rdi
0x180013a5b  push    r12
0x180013a5d  push    r13
0x180013a5f  push    r14
0x180013a61  push    r15
0x180013a63  sub     rsp, 160h
0x180013a6a  mov     rax, cs:__security_cookie
0x180013a71  xor     rax, rsp
0x180013a74  mov     [rsp+188h+var_38], rax
0x180013a7c  mov     r14, r8
0x180013a7f  mov     ebx, edx
0x180013a81  mov     r15, rcx
0x180013a84  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013a88  mov     [rsp+188h+hFileMappingObject], rdi
0x180013a8d  xor     esi, esi
0x180013a8f  mov     qword ptr [rsp+188h+FileSizeHigh], rsi
0x180013a94  mov     r13d, esi
0x180013a97  mov     [rsp+188h+var_138], rsi
0x180013a9c  xor     eax, eax
0x180013a9e  mov     qword ptr [rsp+188h+dwFileOffsetHigh], rax
0x180013aa6  mov     r12d, esi
0x180013aa9  mov     [rsp+188h+var_128], rsi
0x180013aae  mov     [rsp+188h+phProv], rsi
0x180013ab3  mov     [rsp+188h+phHash], rsi
0x180013ab8  xorps   xmm0, xmm0
0x180013abb  movups  xmmword ptr [rsp+188h+pbData], xmm0
0x180013ac3  movups  [rsp+188h+var_D8], xmm0
0x180013acb  mov     [rsp+188h+pdwDataLen], 20h ; ' '
0x180013ad3  xor     edx, edx; Val
0x180013ad5  mov     r8d, 82h; Size
0x180013adb  lea     rcx, [rsp+188h+Src]; void *
0x180013ae3  call    memset_0
0x180013ae8  cmp     [r15+10h], rsi
0x180013aec  jnz     short loc_180013AFE
0x180013aee  mov     r15, rdi
0x180013af1  mov     edi, 80070057h
0x180013af6  mov     rbx, r15
0x180013af9  jmp     loc_18001414C
0x180013afe  mov     eax, cs:dwDataLen
0x180013b04  test    eax, eax
0x180013b06  jnz     short loc_180013B14
0x180013b08  mov     cs:dwDataLen, 2000000h
0x180013b12  jmp     short loc_180013B23
0x180013b14  mov     ecx, 40000000h
0x180013b19  cmp     eax, ecx
0x180013b1b  jbe     short loc_180013B23
0x180013b1d  mov     cs:dwDataLen, ecx
0x180013b23  cmp     qword ptr [r15+18h], 7
0x180013b28  jbe     short loc_180013B2F
0x180013b2a  mov     rcx, [r15]
0x180013b2d  jmp     short loc_180013B32
0x180013b2f  mov     rcx, r15; lpFileName
0x180013b32  mov     [rsp+188h+hTemplateFile], rsi; hTemplateFile
0x180013b37  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013b3f  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x180013b47  xor     r9d, r9d; lpSecurityAttributes
0x180013b4a  mov     edx, 80000000h; dwDesiredAccess
0x180013b4f  lea     r8d, [r9+1]; dwShareMode
0x180013b53  call    cs:__imp_CreateFileW
0x180013b59  mov     [rsp+188h+var_108], rax
0x180013b61  cmp     rax, rdi
0x180013b64  jnz     short loc_180013BB9
0x180013b66  call    cs:__imp_GetLastError
0x180013b6c  mov     edi, eax
0x180013b6e  cmp     qword ptr [r15+18h], 7
0x180013b73  jbe     short loc_180013B78
0x180013b75  mov     r15, [r15]
0x180013b78  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], r15
0x180013b7d  mov     [rsp+188h+dwCreationDisposition], edi
0x180013b81  lea     r9, aCreatefileFail; "CreateFile failed (error code=%d) (path"...
0x180013b88  mov     r8d, 2E7h
0x180013b8e  lea     rdx, aComputefilehas; "ComputeFileHash"
0x180013b95  mov     ecx, 1
0x180013b9a  call    AslLogCallPrintf
0x180013b9f  test    edi, edi
0x180013ba1  jle     short loc_180013BAC
0x180013ba3  movzx   edi, di
0x180013ba6  or      edi, 80070000h
0x180013bac  mov     r15, [rsp+188h+var_108]
0x180013bb4  jmp     loc_180014147
0x180013bb9  mov     edi, 80004005h
0x180013bbe  lea     rdx, [rsp+188h+FileSizeHigh+4]; lpFileSizeHigh
0x180013bc3  mov     r15, rax
0x180013bc6  mov     rcx, rax; hFile
0x180013bc9  call    cs:__imp_GetFileSize
0x180013bcf  mov     [rsp+188h+FileSizeHigh], eax
0x180013bd3  cmp     qword ptr [rsp+188h+FileSizeHigh], rsi
0x180013bd8  jnz     loc_180013CAE
0x180013bde  test    ebx, ebx
0x180013be0  jz      loc_180013C74
0x180013be6  sub     ebx, 1
0x180013be9  jz      short loc_180013C3D
0x180013beb  cmp     ebx, 1
0x180013bee  jnz     loc_180014147
0x180013bf4  lea     r8d, [rbx+3Fh]
0x180013bf8  cmp     [r14+18h], r8
0x180013bfc  jb      short loc_180013C26
0x180013bfe  mov     rbx, [r14]
0x180013c01  mov     [r14+10h], r8
0x180013c05  mov     r8d, 80h; Size
0x180013c0b  lea     rdx, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x180013c12  mov     rcx, rbx; void *
0x180013c15  call    memmove_0
0x180013c1a  mov     [rbx+80h], si
0x180013c21  jmp     loc_180014147
0x180013c26  lea     r9, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x180013c2d  mov     rdx, r8
0x180013c30  mov     rcx, r14
0x180013c33  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180013c38  jmp     loc_180014147
0x180013c3d  mov     edx, 28h ; '('
0x180013c42  cmp     [r14+18h], rdx
0x180013c46  jb      short loc_180013C6B
0x180013c48  mov     rbx, [r14]
0x180013c4b  mov     [r14+10h], rdx
0x180013c4f  lea     r8d, [rdx+28h]; Size
0x180013c53  lea     rdx, aDa39a3ee5e6b4b; "da39a3ee5e6b4b0d3255bfef95601890afd8070"...
0x180013c5a  mov     rcx, rbx; void *
0x180013c5d  call    memmove_0
0x180013c62  mov     [rbx+50h], si
0x180013c66  jmp     loc_180014147
0x180013c6b  lea     r9, aDa39a3ee5e6b4b; "da39a3ee5e6b4b0d3255bfef95601890afd8070"...
0x180013c72  jmp     short loc_180013C30
0x180013c74  mov     eax, 20h ; ' '
0x180013c79  cmp     [r14+18h], rax
0x180013c7d  jb      short loc_180013CA2
0x180013c7f  mov     rbx, [r14]
0x180013c82  mov     [r14+10h], rax
0x180013c86  lea     r8d, [rax+20h]; Size
0x180013c8a  lea     rdx, aD41d8cd98f00b2; "d41d8cd98f00b204e9800998ecf8427e"
0x180013c91  mov     rcx, rbx; void *
0x180013c94  call    memmove_0
0x180013c99  mov     [rbx+40h], si
0x180013c9d  jmp     loc_180014147
0x180013ca2  lea     r9, aD41d8cd98f00b2; "d41d8cd98f00b204e9800998ecf8427e"
0x180013ca9  mov     rdx, rax
0x180013cac  jmp     short loc_180013C30
0x180013cae  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], rsi; lpName
0x180013cb3  mov     [rsp+188h+dwCreationDisposition], esi; dwMaximumSizeLow
0x180013cb7  xor     r9d, r9d; dwMaximumSizeHigh
0x180013cba  xor     edx, edx; lpFileMappingAttributes
0x180013cbc  mov     r8d, 8000002h; flProtect
0x180013cc2  mov     rcx, r15; hFile
0x180013cc5  call    cs:__imp_CreateFileMappingW
0x180013ccb  mov     [rsp+188h+hFileMappingObject], rax
0x180013cd0  mov     [rsp+188h+var_F0], rax
0x180013cd8  lea     rcx, [rax-1]
0x180013cdc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180013ce0  ja      loc_180014110
0x180013ce6  test    ebx, ebx
0x180013ce8  jz      short loc_180013D1A
0x180013cea  sub     ebx, 1
0x180013ced  jz      short loc_180013D0C
0x180013cef  cmp     ebx, 1
0x180013cf2  jnz     loc_180014147
0x180013cf8  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180013cff  mov     ebx, 800Ch
0x180013d04  mov     r9d, 18h
0x180013d0a  jmp     short loc_180013D28
0x180013d0c  lea     r8, aMicrosoftBaseC; "Microsoft Base Cryptographic Provider v"...
0x180013d13  mov     ebx, 8004h
0x180013d18  jmp     short loc_180013D22
0x180013d1a  mov     r8, rsi; szProvider
0x180013d1d  mov     ebx, 8003h
0x180013d22  mov     r9d, 1; dwProvType
0x180013d28  mov     [rsp+188h+dwCreationDisposition], 0F0000000h; dwFlags
0x180013d30  xor     edx, edx; szContainer
0x180013d32  lea     rcx, [rsp+188h+phProv]; phProv
0x180013d37  call    cs:__imp_CryptAcquireContextW
0x180013d3d  test    eax, eax
0x180013d3f  jnz     short loc_180013D7D
0x180013d41  call    cs:__imp_GetLastError
0x180013d47  mov     edi, eax
0x180013d49  test    eax, eax
0x180013d4b  jle     short loc_180013D56
0x180013d4d  movzx   edi, ax
0x180013d50  or      edi, 80070000h
0x180013d56  lea     r9, aFailedAcquirin; "Failed acquiring the crypto context wit"...
0x180013d5d  mov     r8d, 336h
0x180013d63  mov     [rsp+188h+dwCreationDisposition], edi
0x180013d67  lea     rdx, aComputefilehas; "ComputeFileHash"
0x180013d6e  mov     ecx, 1
0x180013d73  call    AslLogCallPrintf
0x180013d78  jmp     loc_180014147
0x180013d7d  lea     rax, [rsp+188h+phHash]
0x180013d82  mov     qword ptr [rsp+188h+dwCreationDisposition], rax; phHash
0x180013d87  xor     r9d, r9d; dwFlags
0x180013d8a  xor     r8d, r8d; hKey
0x180013d8d  mov     edx, ebx; Algid
0x180013d8f  mov     rcx, [rsp+188h+phProv]; hProv
0x180013d94  call    cs:__imp_CryptCreateHash
0x180013d9a  test    eax, eax
0x180013d9c  jnz     short loc_180013DC2
0x180013d9e  call    cs:__imp_GetLastError
0x180013da4  mov     edi, eax
0x180013da6  test    eax, eax
0x180013da8  jle     short loc_180013DB3
0x180013daa  movzx   edi, ax
0x180013dad  or      edi, 80070000h
0x180013db3  lea     r9, aFailedCreating; "Failed creating SHA1 hash object with 0"...
0x180013dba  mov     r8d, 342h
0x180013dc0  jmp     short loc_180013D63
0x180013dc2  mov     edi, 4
0x180013dc7  mov     r8, qword ptr [rsp+188h+dwFileOffsetHigh]; dwFileOffsetHigh
0x180013dcf  mov     rbx, [rsp+188h+hFileMappingObject]
0x180013dd4  mov     ecx, cs:dwDataLen
0x180013dda  mov     rax, qword ptr [rsp+188h+FileSizeHigh]
0x180013ddf  sub     rax, [rsp+188h+var_138]
0x180013de4  cmp     rax, rcx
0x180013de7  jbe     loc_180013ED1
0x180013ded  mov     qword ptr [rsp+188h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x180013df2  mov     r9d, r13d; dwFileOffsetLow
0x180013df5  mov     edx, edi; dwDesiredAccess
0x180013df7  mov     rcx, rbx; hFileMappingObject
0x180013dfa  call    cs:__imp_MapViewOfFile
0x180013e00  mov     r12, rax
0x180013e03  mov     [rsp+188h+var_128], rax
0x180013e08  test    rax, rax
0x180013e0b  jnz     short loc_180013E4D
0x180013e0d  call    cs:__imp_GetLastError
0x180013e13  mov     edi, eax
0x180013e15  test    eax, eax
0x180013e17  jle     short loc_180013E22
0x180013e19  movzx   edi, ax
0x180013e1c  or      edi, 80070000h
0x180013e22  mov     [rsp+188h+var_140], edi
0x180013e26  mov     [rsp+188h+dwCreationDisposition], edi
0x180013e2a  lea     r9, aMapviewoffileF; "MapViewOfFile failed with 0x%x."
0x180013e31  mov     r8d, 357h
0x180013e37  lea     rdx, aComputefilehas; "ComputeFileHash"
0x180013e3e  mov     ecx, 1
0x180013e43  call    AslLogCallPrintf
0x180013e48  jmp     loc_18001414C
0x180013e4d  xor     r9d, r9d; dwFlags
0x180013e50  mov     r8d, cs:dwDataLen; dwDataLen
0x180013e57  mov     rdx, r12; pbData
0x180013e5a  mov     rcx, [rsp+188h+phHash]; hHash
0x180013e5f  call    cs:__imp_CryptHashData
0x180013e65  test    eax, eax
0x180013e67  jnz     short loc_180013EA9
0x180013e69  call    cs:__imp_GetLastError
0x180013e6f  mov     edi, eax
0x180013e71  test    eax, eax
0x180013e73  jle     short loc_180013E7E
0x180013e75  movzx   edi, ax
0x180013e78  or      edi, 80070000h
0x180013e7e  mov     [rsp+188h+var_140], edi
0x180013e82  mov     [rsp+188h+dwCreationDisposition], edi
0x180013e86  lea     r9, aFailedHashingD; "Failed hashing data (SHA1) with 0x%x"
0x180013e8d  mov     r8d, 361h
0x180013e93  lea     rdx, aComputefilehas; "ComputeFileHash"
0x180013e9a  mov     ecx, 1
0x180013e9f  call    AslLogCallPrintf
0x180013ea4  jmp     loc_18001414C
0x180013ea9  mov     rcx, r12; lpBaseAddress
0x180013eac  call    cs:__imp_UnmapViewOfFile
0x180013eb2  mov     [rsp+188h+var_128], rsi
0x180013eb7  mov     eax, cs:dwDataLen
0x180013ebd  add     [rsp+188h+var_138], rax
0x180013ec2  mov     r8d, dword ptr [rsp+188h+var_138+4]
0x180013ec7  mov     r13d, dword ptr [rsp+188h+var_138]
0x180013ecc  jmp     loc_180013DD4
0x180013ed1  mov     ebx, [rsp+188h+FileSizeHigh]
0x180013ed5  sub     ebx, r13d
0x180013ed8  mov     r12, rsi
0x180013edb  mov     [rsp+188h+var_128], rsi
0x180013ee0  test    ebx, ebx
0x180013ee2  jle     loc_180013FC9
0x180013ee8  movsxd  rax, ebx
0x180013eeb  mov     r8, [rsp+188h+var_138]
0x180013ef0  shr     r8, 20h; dwFileOffsetHigh
0x180013ef4  mov     qword ptr [rsp+188h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x180013ef9  mov     r9d, r13d; dwFileOffsetLow
0x180013efc  mov     edx, edi; dwDesiredAccess
0x180013efe  mov     rcx, [rsp+188h+hFileMappingObject]; hFileMappingObject
0x180013f03  call    cs:__imp_MapViewOfFile
0x180013f09  mov     r12, rax
0x180013f0c  mov     [rsp+188h+var_128], rax
0x180013f11  test    rax, rax
0x180013f14  jnz     short loc_180013F5B
0x180013f16  call    cs:__imp_GetLastError
0x180013f1c  mov     edi, eax
0x180013f1e  test    eax, eax
0x180013f20  jle     short loc_180013F2B
0x180013f22  movzx   edi, ax
0x180013f25  or      edi, 80070000h
0x180013f2b  mov     [rsp+188h+var_140], edi
0x180013f2f  mov     [rsp+188h+dwCreationDisposition], edi
0x180013f33  lea     r9, aMapviewoffileF; "MapViewOfFile failed with 0x%x."
0x180013f3a  mov     r8d, 37Ah
0x180013f40  lea     rdx, aComputefilehas; "ComputeFileHash"
0x180013f47  mov     ecx, 1
0x180013f4c  call    AslLogCallPrintf
0x180013f51  mov     rbx, [rsp+188h+hFileMappingObject]
0x180013f56  jmp     loc_18001414C
0x180013f5b  xor     r9d, r9d; dwFlags
0x180013f5e  mov     r8d, ebx; dwDataLen
0x180013f61  mov     rdx, r12; pbData
  ... truncated ...
```
