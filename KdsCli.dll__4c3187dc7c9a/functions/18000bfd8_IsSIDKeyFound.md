# IsSIDKeyFound

- ea: `0x18000bfd8`
- end: `0x18000c1f6`
- name: `IsSIDKeyFound`
- size: `542`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int, unsigned int, int, __int64, int *, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c1fc`

## callees

- `0x18000bfd8`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c12b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c12b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c1d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c1d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c01a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c01a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000c076`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000c076`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c121`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c121`

## string_xrefs

- `0x18000c035`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000c091`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000c0da`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall IsSIDKeyFound(
        const WCHAR *a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        int *a6,
        _QWORD *a7,
        DWORD *a8)
{
  HANDLE FileW; // rax
  void *v12; // rsi
  signed int LastError; // ebx
  _BYTE *v14; // rdi
  int v15; // r15d
  DWORD FileSize; // eax
  DWORD v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  _BYTE *v21; // rax
  unsigned __int16 *v22; // rdx
  __int64 v23; // r8
  int v24; // ecx
  int v25; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-48h] BYREF

  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v12 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    SidKeyDebugTraceError(
      LastError,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x398u);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a6 = 0;
    return (unsigned int)LastError;
  }
  v14 = 0;
  v15 = 0;
  FileSize = GetFileSize(FileW, 0);
  NumberOfBytesRead = FileSize;
  if ( FileSize == -1 )
  {
    v17 = GetLastError();
    v18 = 932;
LABEL_7:
    LastError = v17;
    SidKeyDebugTraceError(
      v17,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      v18);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  if ( FileSize >= 0x50 )
  {
    v21 = SIDKeyProvAlloc(FileSize);
    v14 = v21;
    if ( v21 )
    {
      if ( ReadFile(v12, v21, NumberOfBytesRead, &NumberOfBytesRead, 0) )
      {
        LastError = 0;
        if ( *((_DWORD *)v14 + 4) >= a2 && (*((_DWORD *)v14 + 4) != a2 || *((_DWORD *)v14 + 5) >= a3) )
        {
          if ( !a5 )
            goto LABEL_25;
          v22 = (unsigned __int16 *)&v14[*((unsigned int *)v14 + 11)
                                       + 80
                                       + *((unsigned int *)v14 + 12)
                                       + *((unsigned int *)v14 + 13)
                                       + (unsigned __int64)*((unsigned int *)v14 + 18)
                                       + *((unsigned int *)v14 + 10)];
          v23 = a5 - (_QWORD)v22;
          do
          {
            v24 = *(unsigned __int16 *)((char *)v22 + v23);
            v25 = *v22 - v24;
            if ( v25 )
              break;
            ++v22;
          }
          while ( v24 );
          if ( !v25 )
          {
LABEL_25:
            if ( !a4 || (v14[8] & 2) != 0 )
            {
              *a7 = v14;
              v14 = 0;
              *a8 = NumberOfBytesRead;
              v15 = 1;
            }
          }
        }
        goto LABEL_27;
      }
      v17 = GetLastError();
      v18 = 960;
      goto LABEL_7;
    }
    LastError = -2147024882;
    v19 = 948;
    v20 = -2147024882;
  }
  else
  {
    LastError = -2146893821;
    v19 = 940;
    v20 = -2146893821;
  }
  SidKeyDebugTraceError(v20, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v19);
LABEL_27:
  *a6 = v15;
  if ( v12 )
    CloseHandle(v12);
  if ( v14 )
    SIDKeyProvFree(v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000bfd8  mov     rax, rsp
0x18000bfdb  push    rbx
0x18000bfdc  push    rbp
0x18000bfdd  push    rsi
0x18000bfde  push    rdi
0x18000bfdf  push    r12
0x18000bfe1  push    r14
0x18000bfe3  push    r15
0x18000bfe5  sub     rsp, 50h
0x18000bfe9  mov     qword ptr [rax-58h], 0
0x18000bff1  mov     r12d, r9d
0x18000bff4  xor     r9d, r9d; lpSecurityAttributes
0x18000bff7  mov     dword ptr [rax-60h], 8000000h
0x18000bffe  mov     r14d, r8d
0x18000c001  mov     dword ptr [rax-48h], 0
0x18000c008  mov     ebp, edx
0x18000c00a  mov     dword ptr [rax-68h], 3
0x18000c011  mov     edx, 80000000h; dwDesiredAccess
0x18000c016  lea     r8d, [r9+1]; dwShareMode
0x18000c01a  call    cs:__imp_CreateFileW
0x18000c020  mov     rsi, rax
0x18000c023  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c027  jnz     short loc_18000C06C
0x18000c029  call    cs:__imp_GetLastError
0x18000c02f  mov     r9d, 398h; unsigned int
0x18000c035  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000c03c  mov     ecx, eax; unsigned int
0x18000c03e  lea     rdx, aDwreturn; "dwReturn"
0x18000c045  mov     ebx, eax
0x18000c047  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c04c  test    ebx, ebx
0x18000c04e  jle     short loc_18000C059
0x18000c050  movzx   ebx, bx
0x18000c053  or      ebx, 80070000h
0x18000c059  mov     rax, [rsp+88h+arg_28]
0x18000c061  mov     dword ptr [rax], 0
0x18000c067  jmp     loc_18000C1E5
0x18000c06c  xor     edx, edx; lpFileSizeHigh
0x18000c06e  mov     rcx, rsi; hFile
0x18000c071  xor     edi, edi
0x18000c073  xor     r15d, r15d
0x18000c076  call    cs:__imp_GetFileSize
0x18000c07c  mov     [rsp+88h+NumberOfBytesRead], eax
0x18000c080  cmp     eax, 0FFFFFFFFh
0x18000c083  jnz     short loc_18000C0BE
0x18000c085  call    cs:__imp_GetLastError
0x18000c08b  mov     r9d, 3A4h; unsigned int
0x18000c091  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000c098  mov     ecx, eax; unsigned int
0x18000c09a  lea     rdx, aDwreturn; "dwReturn"
0x18000c0a1  mov     ebx, eax
0x18000c0a3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c0a8  test    ebx, ebx
0x18000c0aa  jle     loc_18000C1BF
0x18000c0b0  movzx   ebx, bx
0x18000c0b3  or      ebx, 80070000h
0x18000c0b9  jmp     loc_18000C1BF
0x18000c0be  cmp     eax, 50h ; 'P'
0x18000c0c1  jnb     short loc_18000C0EB
0x18000c0c3  mov     ebx, 80090003h
0x18000c0c8  mov     r9d, 3ACh; unsigned int
0x18000c0ce  mov     ecx, 80090003h; unsigned int
0x18000c0d3  lea     rdx, aHr; "hr"
0x18000c0da  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000c0e1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c0e6  jmp     loc_18000C1BF
0x18000c0eb  mov     ecx, eax; unsigned __int64
0x18000c0ed  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000c0f2  mov     rdi, rax
0x18000c0f5  test    rax, rax
0x18000c0f8  jnz     short loc_18000C10C
0x18000c0fa  mov     ebx, 8007000Eh
0x18000c0ff  mov     r9d, 3B4h
0x18000c105  mov     ecx, 8007000Eh
0x18000c10a  jmp     short loc_18000C0D3
0x18000c10c  mov     r8d, [rsp+88h+NumberOfBytesRead]; nNumberOfBytesToRead
0x18000c111  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000c116  mov     rdx, rdi; lpBuffer
0x18000c119  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18000c11e  mov     rcx, rsi; hFile
0x18000c121  call    cs:__imp_ReadFile
0x18000c127  test    eax, eax
0x18000c129  jnz     short loc_18000C13C
0x18000c12b  call    cs:__imp_GetLastError
0x18000c131  mov     r9d, 3C0h
0x18000c137  jmp     loc_18000C091
0x18000c13c  xor     ebx, ebx
0x18000c13e  cmp     [rdi+10h], ebp
0x18000c141  jb      short loc_18000C1BF
0x18000c143  jnz     short loc_18000C14B
0x18000c145  cmp     [rdi+14h], r14d
0x18000c149  jb      short loc_18000C1BF
0x18000c14b  mov     r8, [rsp+88h+arg_20]
0x18000c153  test    r8, r8
0x18000c156  jz      short loc_18000C195
0x18000c158  mov     eax, [rdi+34h]
0x18000c15b  mov     edx, [rdi+48h]
0x18000c15e  mov     ecx, [rdi+2Ch]
0x18000c161  add     rdx, rax
0x18000c164  mov     eax, [rdi+30h]
0x18000c167  add     rcx, rdi
0x18000c16a  add     rdx, rax
0x18000c16d  mov     eax, [rdi+28h]
0x18000c170  add     rdx, 50h ; 'P'
0x18000c174  add     rdx, rcx
0x18000c177  add     rdx, rax
0x18000c17a  sub     r8, rdx
0x18000c17d  movzx   eax, word ptr [rdx]
0x18000c180  movzx   ecx, word ptr [rdx+r8]
0x18000c185  sub     eax, ecx
0x18000c187  jnz     short loc_18000C191
0x18000c189  add     rdx, 2
0x18000c18d  test    ecx, ecx
0x18000c18f  jnz     short loc_18000C17D
0x18000c191  test    eax, eax
0x18000c193  jnz     short loc_18000C1BF
0x18000c195  test    r12d, r12d
0x18000c198  jz      short loc_18000C1A0
0x18000c19a  test    byte ptr [rdi+8], 2
0x18000c19e  jz      short loc_18000C1BF
0x18000c1a0  mov     rax, [rsp+88h+arg_30]
0x18000c1a8  mov     rcx, [rsp+88h+arg_38]
0x18000c1b0  mov     [rax], rdi
0x18000c1b3  xor     edi, edi
0x18000c1b5  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18000c1b9  mov     [rcx], eax
0x18000c1bb  lea     r15d, [rdi+1]
0x18000c1bf  mov     rax, [rsp+88h+arg_28]
0x18000c1c7  mov     [rax], r15d
0x18000c1ca  test    rsi, rsi
0x18000c1cd  jz      short loc_18000C1D8
0x18000c1cf  mov     rcx, rsi; hObject
0x18000c1d2  call    cs:__imp_CloseHandle
0x18000c1d8  test    rdi, rdi
0x18000c1db  jz      short loc_18000C1E5
0x18000c1dd  mov     rcx, rdi; lpMem
0x18000c1e0  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000c1e5  mov     eax, ebx
0x18000c1e7  add     rsp, 50h
0x18000c1eb  pop     r15
0x18000c1ed  pop     r14
0x18000c1ef  pop     r12
0x18000c1f1  pop     rdi
0x18000c1f2  pop     rsi
0x18000c1f3  pop     rbp
0x18000c1f4  pop     rbx
0x18000c1f5  retn
```
