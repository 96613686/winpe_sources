# BfspSetAttributes

- ea: `0x14000d2b4`
- end: `0x14000d3be`
- name: `BfspSetAttributes`
- size: `266`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140009fd4`
- `0x14000b57c`

## callees

- `0x140003368`
- `0x14000d2b4`
- `0x14000e628`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000d3a6`
- `KERNEL32!SetLastError` at `0x14000d3a6`
- `KERNEL32!GetLastError` at `0x14000d307`
- `KERNEL32!GetLastError` at `0x14000d370`
- `KERNEL32!GetLastError` at `0x14000d307`
- `KERNEL32!GetLastError` at `0x14000d370`
- `KERNEL32!GetFileAttributesW` at `0x14000d2f8`
- `KERNEL32!GetFileAttributesW` at `0x14000d2f8`
- `KERNEL32!SetFileAttributesW` at `0x14000d364`
- `KERNEL32!SetFileAttributesW` at `0x14000d364`

## string_xrefs

- `0x14000d390`: `SetFileAttributes(%s) failed! Last Error = %#x.`

## pseudocode

```c
__int64 __fastcall BfspSetAttributes(LPCWSTR lpFileName, unsigned int a2)
{
  unsigned int v4; // esi
  DWORD v5; // ecx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  DWORD v8; // edi
  DWORD v9; // edx
  DWORD v10; // eax

  if ( a2 != 128 && (a2 & 0xFFFFFF78) != 0 )
  {
    v4 = 0;
    BfspLogMessage(4, L"Invalid attributes (%#x) specified for %s file!", a2, lpFileName);
    v5 = 87;
LABEL_19:
    SetLastError(v5);
    return v4;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    v4 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 5 || LastError - 32 <= 1 )
      BfspPrintFileOwnerProcess(lpFileName);
    if ( v8 == 2 )
      BfspLogMessage(2, L"GetFileAttributes(%s) failed: File not found.", lpFileName);
    else
      BfspLogMessage(3, L"GetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, v8);
LABEL_18:
    v5 = v8;
    goto LABEL_19;
  }
  v9 = a2 & 0xFFFFFF7F | FileAttributesW & 0x3120;
  if ( (a2 | FileAttributesW & 0x3120 | 0x80) == 0x80 )
    v9 = 128;
  v4 = SetFileAttributesW(lpFileName, v9);
  if ( !v4 )
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 == 5 || v10 - 32 <= 1 )
      BfspPrintFileOwnerProcess(lpFileName);
    BfspLogMessage(4, L"SetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, v8);
    goto LABEL_18;
  }
  return v4;
}

```

## disassembly

```asm
0x14000d2b4  mov     [rsp+arg_0], rbx
0x14000d2b9  mov     [rsp+arg_8], rsi
0x14000d2be  push    rdi
0x14000d2bf  sub     rsp, 20h
0x14000d2c3  mov     esi, 80h
0x14000d2c8  mov     edi, edx
0x14000d2ca  mov     rbx, rcx
0x14000d2cd  cmp     edx, esi
0x14000d2cf  jz      short loc_14000D2F8
0x14000d2d1  test    edx, 0FFFFFF78h
0x14000d2d7  jz      short loc_14000D2F8
0x14000d2d9  xor     esi, esi
0x14000d2db  mov     r9, rcx
0x14000d2de  mov     r8d, edx
0x14000d2e1  lea     rdx, aInvalidAttribu; "Invalid attributes (%#x) specified for "...
0x14000d2e8  lea     ecx, [rsi+4]
0x14000d2eb  call    BfspLogMessage
0x14000d2f0  lea     ecx, [rsi+57h]; lpFileName
0x14000d2f3  jmp     loc_14000D3A6
0x14000d2f8  call    cs:__imp_GetFileAttributesW
0x14000d2fe  mov     edx, eax
0x14000d300  cmp     eax, 0FFFFFFFFh
0x14000d303  jnz     short loc_14000D34C
0x14000d305  xor     esi, esi
0x14000d307  call    cs:__imp_GetLastError
0x14000d30d  mov     edi, eax
0x14000d30f  cmp     eax, 5
0x14000d312  jz      short loc_14000D31C
0x14000d314  add     eax, 0FFFFFFE0h
0x14000d317  cmp     eax, 1
0x14000d31a  ja      short loc_14000D324
0x14000d31c  mov     rcx, rbx; lpFileName
0x14000d31f  call    BfspPrintFileOwnerProcess
0x14000d324  mov     ecx, 2
0x14000d329  mov     r8, rbx
0x14000d32c  cmp     edi, ecx
0x14000d32e  jz      short loc_14000D33E
0x14000d330  lea     rdx, aGetfileattribu_0; "GetFileAttributes(%s) failed! Last Erro"...
0x14000d337  mov     ecx, 3
0x14000d33c  jmp     short loc_14000D39C
0x14000d33e  lea     rdx, aGetfileattribu; "GetFileAttributes(%s) failed: File not "...
0x14000d345  call    BfspLogMessage
0x14000d34a  jmp     short loc_14000D3A4
0x14000d34c  and     edx, 3120h
0x14000d352  mov     rcx, rbx; lpFileName
0x14000d355  or      edx, edi
0x14000d357  mov     eax, edx
0x14000d359  btr     edx, 7
0x14000d35d  or      eax, esi
0x14000d35f  cmp     eax, esi
0x14000d361  cmovz   edx, eax; dwFileAttributes
0x14000d364  call    cs:__imp_SetFileAttributesW
0x14000d36a  mov     esi, eax
0x14000d36c  test    eax, eax
0x14000d36e  jnz     short loc_14000D3AC
0x14000d370  call    cs:__imp_GetLastError
0x14000d376  mov     edi, eax
0x14000d378  cmp     eax, 5
0x14000d37b  jz      short loc_14000D385
0x14000d37d  lea     ecx, [rax-20h]
0x14000d380  cmp     ecx, 1
0x14000d383  ja      short loc_14000D38D
0x14000d385  mov     rcx, rbx; lpFileName
0x14000d388  call    BfspPrintFileOwnerProcess
0x14000d38d  mov     r8, rbx
0x14000d390  lea     rdx, aSetfileattribu; "SetFileAttributes(%s) failed! Last Erro"...
0x14000d397  mov     ecx, 4
0x14000d39c  mov     r9d, edi
0x14000d39f  call    BfspLogMessage
0x14000d3a4  mov     ecx, edi; dwErrCode
0x14000d3a6  call    cs:__imp_SetLastError
0x14000d3ac  mov     rbx, [rsp+28h+arg_0]
0x14000d3b1  mov     eax, esi
0x14000d3b3  mov     rsi, [rsp+28h+arg_8]
0x14000d3b8  add     rsp, 20h
0x14000d3bc  pop     rdi
0x14000d3bd  retn
```
