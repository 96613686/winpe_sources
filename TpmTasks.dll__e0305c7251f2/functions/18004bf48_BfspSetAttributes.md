# BfspSetAttributes

- ea: `0x18004bf48`
- end: `0x18004c036`
- name: `BfspSetAttributes`
- size: `238`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180049234`
- `0x18004a678`

## callees

- `0x180047280`
- `0x18004bf48`
- `0x18004cdd4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004bfe9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004bfe9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004bf8c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004bf8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c01e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c01e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bff5`

## string_xrefs

- `0x18004c00a`: `SetFileAttributes(%s) failed! Last Error = %#x.`

## pseudocode

```c
__int64 __fastcall BfspSetAttributes(LPCWSTR lpFileName, unsigned int a2)
{
  unsigned int v4; // esi
  DWORD v5; // ecx
  DWORD FileAttributesW; // eax
  __int64 LastError; // rbx
  DWORD v8; // edx

  if ( a2 != 128 && (a2 & 0xFFFFFF78) != 0 )
  {
    v4 = 0;
    BfspLogMessage(4, L"Invalid attributes (%#x) specified for %s file!", a2, lpFileName);
    v5 = 87;
LABEL_13:
    SetLastError(v5);
    return v4;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    v4 = 0;
    LastError = GetLastError();
    BfspPrintOwnerProcessOnSharingError(lpFileName, LastError);
    if ( (_DWORD)LastError == 2 )
      BfspLogMessage(2, L"GetFileAttributes(%s) failed: File not found.", lpFileName);
    else
      BfspLogMessage(3, L"GetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, (unsigned int)LastError);
    goto LABEL_12;
  }
  v8 = a2 & 0xFFFFFF7F | FileAttributesW & 0x3120;
  if ( (a2 | FileAttributesW & 0x3120 | 0x80) == 0x80 )
    v8 = 128;
  v4 = SetFileAttributesW(lpFileName, v8);
  if ( !v4 )
  {
    LastError = GetLastError();
    BfspPrintOwnerProcessOnSharingError(lpFileName, LastError);
    BfspLogMessage(4, L"SetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, (unsigned int)LastError);
LABEL_12:
    v5 = LastError;
    goto LABEL_13;
  }
  return v4;
}

```

## disassembly

```asm
0x18004bf48  mov     [rsp+arg_0], rbx
0x18004bf4d  mov     [rsp+arg_8], rsi
0x18004bf52  push    rdi
0x18004bf53  sub     rsp, 20h
0x18004bf57  mov     esi, 80h
0x18004bf5c  mov     ebx, edx
0x18004bf5e  mov     rdi, rcx
0x18004bf61  cmp     edx, esi
0x18004bf63  jz      short loc_18004BF8C
0x18004bf65  test    edx, 0FFFFFF78h
0x18004bf6b  jz      short loc_18004BF8C
0x18004bf6d  xor     esi, esi
0x18004bf6f  mov     r9, rcx
0x18004bf72  mov     r8d, edx
0x18004bf75  lea     rdx, aInvalidAttribu; "Invalid attributes (%#x) specified for "...
0x18004bf7c  lea     ecx, [rsi+4]
0x18004bf7f  call    BfspLogMessage
0x18004bf84  lea     ecx, [rsi+57h]; lpFileName
0x18004bf87  jmp     loc_18004C01E
0x18004bf8c  call    cs:__imp_GetFileAttributesW
0x18004bf92  mov     edx, eax
0x18004bf94  cmp     eax, 0FFFFFFFFh
0x18004bf97  jnz     short loc_18004BFD1
0x18004bf99  xor     esi, esi
0x18004bf9b  call    cs:__imp_GetLastError
0x18004bfa1  mov     edx, eax
0x18004bfa3  mov     rcx, rdi
0x18004bfa6  mov     ebx, eax
0x18004bfa8  call    BfspPrintOwnerProcessOnSharingError
0x18004bfad  lea     ecx, [rsi+2]
0x18004bfb0  mov     r8, rdi
0x18004bfb3  cmp     ebx, ecx
0x18004bfb5  jz      short loc_18004BFC3
0x18004bfb7  lea     rdx, aGetfileattribu_0; "GetFileAttributes(%s) failed! Last Erro"...
0x18004bfbe  lea     ecx, [rsi+3]
0x18004bfc1  jmp     short loc_18004C014
0x18004bfc3  lea     rdx, aGetfileattribu; "GetFileAttributes(%s) failed: File not "...
0x18004bfca  call    BfspLogMessage
0x18004bfcf  jmp     short loc_18004C01C
0x18004bfd1  and     edx, 3120h
0x18004bfd7  mov     rcx, rdi; lpFileName
0x18004bfda  or      edx, ebx
0x18004bfdc  mov     eax, edx
0x18004bfde  btr     edx, 7
0x18004bfe2  or      eax, esi
0x18004bfe4  cmp     eax, esi
0x18004bfe6  cmovz   edx, eax; dwFileAttributes
0x18004bfe9  call    cs:__imp_SetFileAttributesW
0x18004bfef  mov     esi, eax
0x18004bff1  test    eax, eax
0x18004bff3  jnz     short loc_18004C024
0x18004bff5  call    cs:__imp_GetLastError
0x18004bffb  mov     edx, eax
0x18004bffd  mov     rcx, rdi
0x18004c000  mov     ebx, eax
0x18004c002  call    BfspPrintOwnerProcessOnSharingError
0x18004c007  mov     r8, rdi
0x18004c00a  lea     rdx, aSetfileattribu; "SetFileAttributes(%s) failed! Last Erro"...
0x18004c011  lea     ecx, [rsi+4]
0x18004c014  mov     r9d, ebx
0x18004c017  call    BfspLogMessage
0x18004c01c  mov     ecx, ebx; dwErrCode
0x18004c01e  call    cs:__imp_SetLastError
0x18004c024  mov     rbx, [rsp+28h+arg_0]
0x18004c029  mov     eax, esi
0x18004c02b  mov     rsi, [rsp+28h+arg_8]
0x18004c030  add     rsp, 20h
0x18004c034  pop     rdi
0x18004c035  retn
```
