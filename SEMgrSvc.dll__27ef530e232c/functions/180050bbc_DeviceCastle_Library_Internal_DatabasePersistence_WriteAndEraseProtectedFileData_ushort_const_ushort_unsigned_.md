# DeviceCastle::Library::Internal::DatabasePersistence::WriteAndEraseProtectedFileData(ushort const *,ushort *,unsigned __int64,int *)

- ea: `0x180050bbc`
- end: `0x180050d7a`
- name: `?WriteAndEraseProtectedFileData@DatabasePersistence@Internal@Library@DeviceCastle@@AEAAJPEBGPEAG_KPEAH@Z`
- size: `446`
- prototype: `int(DeviceCastle::Library::Internal::DatabasePersistence *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18004e650`
- `0x18005069c`
- `0x180050934`

## callees

- `0x180050bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050cbb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050cbb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180050d23`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180050d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050d5e`
- `CRYPT32!CryptProtectData` at `0x180050c56`
- `CRYPT32!CryptProtectData` at `0x180050c56`

## pseudocode

```c
__int64 __fastcall DeviceCastle::Library::Internal::DatabasePersistence::WriteAndEraseProtectedFileData(
        DeviceCastle::Library::Internal::DatabasePersistence *this,
        const unsigned __int16 *a2,
        BYTE *a3,
        __int64 a4,
        int *a5)
{
  __int64 v6; // rbx
  BYTE *v7; // rdi
  __int64 v8; // rcx
  BYTE *v9; // rax
  signed int LastError; // esi
  BYTE *pbData; // rbx
  DWORD cbData; // r14d
  char *FileW; // rsi
  signed int v14; // eax
  signed int v15; // edi
  int *v16; // rdi
  signed int v17; // eax
  DATA_BLOB pOptionalEntropy; // [rsp+40h] [rbp-38h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-28h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+C8h] [rbp+50h] BYREF

  *(&pDataIn.cbData + 1) = 0;
  v6 = 2 * a4;
  v7 = a3;
  pOptionalEntropy = 0;
  pDataOut = 0;
  if ( (unsigned __int64)(2 * a4) > 0xFFFFFFFF )
    return (unsigned int)-2147024362;
  v8 = *((_QWORD *)this + 1);
  pDataIn.cbData = 2 * a4;
  pDataIn.pbData = a3;
  if ( (unsigned __int64)(2LL * *(_QWORD *)(v8 + 176)) > 0xFFFFFFFF )
    return (unsigned int)-2147024362;
  pOptionalEntropy.cbData = 2 * *(_DWORD *)(v8 + 176);
  v9 = (BYTE *)(v8 + 160);
  if ( *(_QWORD *)(v8 + 184) > 7u )
    v9 = *(BYTE **)v9;
  pOptionalEntropy.pbData = v9;
  if ( CryptProtectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 0, &pDataOut) )
    LastError = 0;
  else
    LastError = GetLastError();
  for ( ; v6; --v6 )
    *v7++ = 0;
  if ( LastError >= 0 )
  {
    pbData = pDataOut.pbData;
    cbData = pDataOut.cbData;
    NumberOfBytesWritten = 0;
    FileW = (char *)CreateFileW(a2, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v16 = a5;
      if ( a5 )
        *v16 = GetLastError() == 183;
      if ( WriteFile(FileW, pbData, cbData, &NumberOfBytesWritten, 0) )
      {
        v15 = 0;
      }
      else
      {
        v17 = GetLastError();
        v15 = v17;
        if ( v17 > 0 )
          v15 = (unsigned __int16)v17 | 0x80070000;
      }
    }
    else
    {
      v14 = GetLastError();
      v15 = v14;
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_23;
    }
    CloseHandle(FileW);
LABEL_23:
    LastError = 0;
    if ( v15 < 0 )
      LastError = v15;
    if ( pbData )
      LocalFree(pbData);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180050bbc  push    rbp
0x180050bbe  push    rbx
0x180050bbf  push    rsi
0x180050bc0  push    rdi
0x180050bc1  push    r14
0x180050bc3  push    r15
0x180050bc5  mov     rbp, rsp
0x180050bc8  sub     rsp, 78h
0x180050bcc  mov     r15, rdx
0x180050bcf  mov     dword ptr [rbp+pDataIn+4], 0
0x180050bd6  mov     edx, 0FFFFFFFFh
0x180050bdb  lea     rbx, [r9+r9]
0x180050bdf  xorps   xmm0, xmm0
0x180050be2  xorps   xmm1, xmm1
0x180050be5  mov     rdi, r8
0x180050be8  movups  xmmword ptr [rbp+pOptionalEntropy.cbData], xmm0
0x180050bec  movups  xmmword ptr [rbp+var_18.cbData], xmm1
0x180050bf0  cmp     rbx, rdx
0x180050bf3  ja      loc_180050D66
0x180050bf9  mov     rcx, [rcx+8]
0x180050bfd  mov     [rbp+pDataIn.cbData], ebx
0x180050c00  mov     [rbp+pDataIn.pbData], r8
0x180050c04  mov     rax, [rcx+0B0h]
0x180050c0b  add     rax, rax
0x180050c0e  cmp     rax, rdx
0x180050c11  ja      loc_180050D66
0x180050c17  mov     [rbp+pOptionalEntropy.cbData], eax
0x180050c1a  lea     rax, [rcx+0A0h]
0x180050c21  cmp     qword ptr [rax+18h], 7
0x180050c26  jbe     short loc_180050C2B
0x180050c28  mov     rax, [rax]
0x180050c2b  mov     [rbp+pOptionalEntropy.pbData], rax
0x180050c2f  lea     r8, [rbp+pOptionalEntropy]; pOptionalEntropy
0x180050c33  lea     rax, [rbp+var_18]
0x180050c37  xor     r9d, r9d; pvReserved
0x180050c3a  mov     [rsp+78h+pDataOut], rax; pDataOut
0x180050c3f  lea     rcx, [rbp+pDataIn]; pDataIn
0x180050c43  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180050c4b  xor     edx, edx; szDataDescr
0x180050c4d  mov     [rsp+78h+pPromptStruct], 0; pPromptStruct
0x180050c56  call    cs:__imp_CryptProtectData
0x180050c5c  test    eax, eax
0x180050c5e  jz      short loc_180050C64
0x180050c60  xor     esi, esi
0x180050c62  jmp     short loc_180050C6C
0x180050c64  call    cs:__imp_GetLastError
0x180050c6a  mov     esi, eax
0x180050c6c  test    rbx, rbx
0x180050c6f  jz      short loc_180050C7D
0x180050c71  mov     byte ptr [rdi], 0
0x180050c74  inc     rdi
0x180050c77  sub     rbx, 1
0x180050c7b  jnz     short loc_180050C71
0x180050c7d  test    esi, esi
0x180050c7f  js      loc_180050D6B
0x180050c85  mov     rbx, [rbp+var_18.pbData]
0x180050c89  xor     r9d, r9d; lpSecurityAttributes
0x180050c8c  mov     r14d, [rbp+var_18.cbData]
0x180050c90  xor     r8d, r8d; dwShareMode
0x180050c93  mov     [rsp+78h+pDataOut], 0; hTemplateFile
0x180050c9c  mov     edx, 0C0000000h; dwDesiredAccess
0x180050ca1  mov     [rsp+78h+dwFlags], 80h; dwFlagsAndAttributes
0x180050ca9  mov     rcx, r15; lpFileName
0x180050cac  mov     dword ptr [rsp+78h+pPromptStruct], 2; dwCreationDisposition
0x180050cb4  mov     [rbp+NumberOfBytesWritten], 0
0x180050cbb  call    cs:__imp_CreateFileW
0x180050cc1  mov     rsi, rax
0x180050cc4  lea     rcx, [rax+1]
0x180050cc8  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180050ccf  jnz     short loc_180050CF2
0x180050cd1  call    cs:__imp_GetLastError
0x180050cd7  mov     edi, eax
0x180050cd9  test    eax, eax
0x180050cdb  jle     short loc_180050CE6
0x180050cdd  movzx   edi, ax
0x180050ce0  or      edi, 80070000h
0x180050ce6  lea     rax, [rsi-1]
0x180050cea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180050cee  jbe     short loc_180050D46
0x180050cf0  jmp     short loc_180050D4F
0x180050cf2  mov     rdi, [rbp+arg_20]
0x180050cf6  test    rdi, rdi
0x180050cf9  jz      short loc_180050D0D
0x180050cfb  call    cs:__imp_GetLastError
0x180050d01  xor     ecx, ecx
0x180050d03  cmp     eax, 0B7h
0x180050d08  setz    cl
0x180050d0b  mov     [rdi], ecx
0x180050d0d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180050d11  mov     [rsp+78h+pPromptStruct], 0; lpOverlapped
0x180050d1a  mov     r8d, r14d; nNumberOfBytesToWrite
0x180050d1d  mov     rdx, rbx; lpBuffer
0x180050d20  mov     rcx, rsi; hFile
0x180050d23  call    cs:__imp_WriteFile
0x180050d29  test    eax, eax
0x180050d2b  jnz     short loc_180050D44
0x180050d2d  call    cs:__imp_GetLastError
0x180050d33  mov     edi, eax
0x180050d35  test    eax, eax
0x180050d37  jle     short loc_180050D46
0x180050d39  movzx   edi, ax
0x180050d3c  or      edi, 80070000h
0x180050d42  jmp     short loc_180050D46
0x180050d44  xor     edi, edi
0x180050d46  mov     rcx, rsi; hObject
0x180050d49  call    cs:__imp_CloseHandle
0x180050d4f  xor     esi, esi
0x180050d51  test    edi, edi
0x180050d53  cmovs   esi, edi
0x180050d56  test    rbx, rbx
0x180050d59  jz      short loc_180050D6B
0x180050d5b  mov     rcx, rbx; hMem
0x180050d5e  call    cs:__imp_LocalFree
0x180050d64  jmp     short loc_180050D6B
0x180050d66  mov     esi, 80070216h
0x180050d6b  mov     eax, esi
0x180050d6d  add     rsp, 78h
0x180050d71  pop     r15
0x180050d73  pop     r14
0x180050d75  pop     rdi
0x180050d76  pop     rsi
0x180050d77  pop     rbx
0x180050d78  pop     rbp
0x180050d79  retn
```
