# _WriteErrorOut(ushort *,char *,int)

- ea: `0x18013be9c`
- end: `0x18013bff9`
- name: `?_WriteErrorOut@@YAXPEAGPEADH@Z`
- size: `349`
- prototype: `void(unsigned __int16 *, char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18004500c`

## callees

- `0x18013be9c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18013bec1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18013bec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013bfea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013bfea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013bef7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013bef7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013bfdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013bfdb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013bf7e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013bfa3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013bf7e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013bfa3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18013bf8b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18013bf8b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18013bf63`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18013bf63`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18013bfd2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18013bfd2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18013bf4f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18013bf4f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18013bee0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18013bf1a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18013bee0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18013bf1a`

## string_xrefs

- `0x18013bed7`: `%SystemRoot%\System32\CatRoot2\dberr.txt`
- `0x18013bf0c`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

## pseudocode

```c
void __fastcall _WriteErrorOut(unsigned __int16 *a1, char *a2)
{
  DWORD v3; // eax
  DWORD v4; // edi
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  __int64 v7; // rbx
  HANDLE FileW; // rax
  __int64 v9; // r8
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  if ( g_fLogErrorsToDebugger )
    OutputDebugStringA(a2);
  if ( g_fLogErrorsToFile )
  {
    v3 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", 0, 0);
    v4 = v3;
    if ( v3 )
    {
      v5 = (WCHAR *)LocalAlloc(0, 2LL * v3);
      v6 = v5;
      if ( v5 )
      {
        v7 = -1;
        if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", v5, v4) )
        {
          FileW = CreateFileW(v6, 0xC0000000, 0, 0, 4u, 0x80u, 0);
          v7 = (__int64)FileW;
          if ( FileW != (HANDLE)-1LL
            && (GetFileSize(FileW, 0) < 0x30D40 || SetFilePointer((HANDLE)v7, 0, 0, 0) != -1 && SetEndOfFile((HANDLE)v7))
            && SetFilePointer((HANDLE)v7, 0, 0, 2u) != -1 )
          {
            v9 = -1;
            do
              ++v9;
            while ( a2[v9] );
            WriteFile((HANDLE)v7, a2, v9, &NumberOfBytesWritten, 0);
          }
        }
        LocalFree(v6);
        if ( v7 != -1 )
          CloseHandle((HANDLE)v7);
      }
    }
  }
}

```

## disassembly

```asm
0x18013be9c  mov     rax, rsp
0x18013be9f  mov     [rax+18h], r8d
0x18013bea3  push    rbx
0x18013bea4  push    rbp
0x18013bea5  push    rsi
0x18013bea6  push    rdi
0x18013bea7  sub     rsp, 48h
0x18013beab  cmp     cs:?g_fLogErrorsToDebugger@@3HA, 0; int g_fLogErrorsToDebugger
0x18013beb2  mov     rbp, rdx
0x18013beb5  mov     dword ptr [rax+18h], 0
0x18013bebc  jz      short loc_18013BEC7
0x18013bebe  mov     rcx, rdx; lpOutputString
0x18013bec1  call    cs:__imp_OutputDebugStringA
0x18013bec7  cmp     cs:?g_fLogErrorsToFile@@3HA, 0; int g_fLogErrorsToFile
0x18013bece  jz      loc_18013BFF0
0x18013bed4  xor     r8d, r8d; nSize
0x18013bed7  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x18013bede  xor     edx, edx; lpDst
0x18013bee0  call    cs:__imp_ExpandEnvironmentStringsW
0x18013bee6  mov     edi, eax
0x18013bee8  test    eax, eax
0x18013beea  jz      loc_18013BFF0
0x18013bef0  mov     edx, edi
0x18013bef2  xor     ecx, ecx; uFlags
0x18013bef4  add     rdx, rdx; uBytes
0x18013bef7  call    cs:__imp_LocalAlloc
0x18013befd  mov     rsi, rax
0x18013bf00  test    rax, rax
0x18013bf03  jz      loc_18013BFF0
0x18013bf09  mov     r8d, edi; nSize
0x18013bf0c  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x18013bf13  mov     rdx, rax; lpDst
0x18013bf16  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18013bf1a  call    cs:__imp_ExpandEnvironmentStringsW
0x18013bf20  test    eax, eax
0x18013bf22  jz      loc_18013BFD8
0x18013bf28  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18013bf31  xor     r9d, r9d; lpSecurityAttributes
0x18013bf34  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18013bf3c  xor     r8d, r8d; dwShareMode
0x18013bf3f  mov     edx, 0C0000000h; dwDesiredAccess
0x18013bf44  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18013bf4c  mov     rcx, rsi; lpFileName
0x18013bf4f  call    cs:__imp_CreateFileW
0x18013bf55  mov     rbx, rax
0x18013bf58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013bf5c  jz      short loc_18013BFD8
0x18013bf5e  xor     edx, edx; lpFileSizeHigh
0x18013bf60  mov     rcx, rax; hFile
0x18013bf63  call    cs:__imp_GetFileSize
0x18013bf69  or      edi, 0FFFFFFFFh
0x18013bf6c  cmp     eax, 30D40h
0x18013bf71  jb      short loc_18013BF95
0x18013bf73  xor     r9d, r9d; dwMoveMethod
0x18013bf76  xor     r8d, r8d; lpDistanceToMoveHigh
0x18013bf79  xor     edx, edx; lDistanceToMove
0x18013bf7b  mov     rcx, rbx; hFile
0x18013bf7e  call    cs:__imp_SetFilePointer
0x18013bf84  cmp     eax, edi
0x18013bf86  jz      short loc_18013BFD8
0x18013bf88  mov     rcx, rbx; hFile
0x18013bf8b  call    cs:__imp_SetEndOfFile
0x18013bf91  test    eax, eax
0x18013bf93  jz      short loc_18013BFD8
0x18013bf95  mov     r9d, 2; dwMoveMethod
0x18013bf9b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18013bf9e  xor     edx, edx; lDistanceToMove
0x18013bfa0  mov     rcx, rbx; hFile
0x18013bfa3  call    cs:__imp_SetFilePointer
0x18013bfa9  cmp     eax, edi
0x18013bfab  jz      short loc_18013BFD8
0x18013bfad  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013bfb1  inc     r8; nNumberOfBytesToWrite
0x18013bfb4  cmp     byte ptr [r8+rbp], 0
0x18013bfb9  jnz     short loc_18013BFB1
0x18013bfbb  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18013bfc3  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18013bfcc  mov     rdx, rbp; lpBuffer
0x18013bfcf  mov     rcx, rbx; hFile
0x18013bfd2  call    cs:__imp_WriteFile
0x18013bfd8  mov     rcx, rsi; hMem
0x18013bfdb  call    cs:__imp_LocalFree
0x18013bfe1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18013bfe5  jz      short loc_18013BFF0
0x18013bfe7  mov     rcx, rbx; hObject
0x18013bfea  call    cs:__imp_CloseHandle
0x18013bff0  add     rsp, 48h
0x18013bff4  pop     rdi
0x18013bff5  pop     rsi
0x18013bff6  pop     rbp
0x18013bff7  pop     rbx
0x18013bff8  retn
```
