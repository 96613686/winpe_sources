# CSPath::WriteClassStorePathToFile(ushort const *,ushort const *)

- ea: `0x18000cd60`
- end: `0x18000ce28`
- name: `?WriteClassStorePathToFile@CSPath@@AEAAJPEBG0@Z`
- size: `200`
- prototype: `DWORD __fastcall(CSPath *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ccd4`

## callees

- `0x18000cd60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cda1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cda1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000cdbe`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000cdbe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000cdf8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000cdf8`

## pseudocode

```c
DWORD __fastcall CSPath::WriteClassStorePathToFile(
        CSPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HANDLE FileW; // rax
  __int64 v5; // rbx
  void *v6; // rsi
  DWORD LastError; // edi
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+64h] [rbp+Ch]

  v10 = HIDWORD(this);
  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 4u, 0);
  v5 = -1;
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  if ( !SetEndOfFile(FileW) )
    goto LABEL_8;
  LastError = 0;
  if ( a3 )
  {
    do
      ++v5;
    while ( a3[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  if ( !WriteFile(v6, a3, 2 * v5 + 2, &NumberOfBytesWritten, 0) )
LABEL_8:
    LastError = GetLastError();
  CloseHandle(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000cd60  mov     rax, rsp
0x18000cd63  mov     [rax+10h], rbx
0x18000cd67  mov     [rax+18h], rbp
0x18000cd6b  mov     [rax+8], rcx
0x18000cd6f  push    rsi
0x18000cd70  push    rdi
0x18000cd71  push    r14
0x18000cd73  sub     rsp, 40h
0x18000cd77  xor     r14d, r14d
0x18000cd7a  mov     rbp, r8
0x18000cd7d  mov     [rax-28h], r14
0x18000cd81  mov     rcx, rdx; lpFileName
0x18000cd84  mov     dword ptr [rax-30h], 4
0x18000cd8b  xor     r9d, r9d; lpSecurityAttributes
0x18000cd8e  xor     r8d, r8d; dwShareMode
0x18000cd91  mov     dword ptr [rax-38h], 2
0x18000cd98  mov     edx, 40000000h; dwDesiredAccess
0x18000cd9d  mov     [rax+8], r14d
0x18000cda1  call    cs:__imp_CreateFileW
0x18000cda7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cdab  mov     rsi, rax
0x18000cdae  cmp     rax, rbx
0x18000cdb1  jnz     short loc_18000CDBB
0x18000cdb3  call    cs:__imp_GetLastError
0x18000cdb9  jmp     short loc_18000CE15
0x18000cdbb  mov     rcx, rsi; hFile
0x18000cdbe  call    cs:__imp_SetEndOfFile
0x18000cdc4  test    eax, eax
0x18000cdc6  jz      short loc_18000CE02
0x18000cdc8  mov     edi, r14d
0x18000cdcb  test    rbp, rbp
0x18000cdce  jnz     short loc_18000CDD5
0x18000cdd0  mov     rbx, r14
0x18000cdd3  jmp     short loc_18000CDE0
0x18000cdd5  inc     rbx
0x18000cdd8  cmp     [rbp+rbx*2+0], r14w
0x18000cdde  jnz     short loc_18000CDD5
0x18000cde0  lea     r8d, ds:2[rbx*2]; nNumberOfBytesToWrite
0x18000cde8  mov     [rsp+58h+lpOverlapped], r14; lpOverlapped
0x18000cded  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000cdf2  mov     rdx, rbp; lpBuffer
0x18000cdf5  mov     rcx, rsi; hFile
0x18000cdf8  call    cs:__imp_WriteFile
0x18000cdfe  test    eax, eax
0x18000ce00  jnz     short loc_18000CE0A
0x18000ce02  call    cs:__imp_GetLastError
0x18000ce08  mov     edi, eax
0x18000ce0a  mov     rcx, rsi; hObject
0x18000ce0d  call    cs:__imp_CloseHandle
0x18000ce13  mov     eax, edi
0x18000ce15  mov     rbx, [rsp+58h+arg_8]
0x18000ce1a  mov     rbp, [rsp+58h+arg_10]
0x18000ce1f  add     rsp, 40h
0x18000ce23  pop     r14
0x18000ce25  pop     rdi
0x18000ce26  pop     rsi
0x18000ce27  retn
```
