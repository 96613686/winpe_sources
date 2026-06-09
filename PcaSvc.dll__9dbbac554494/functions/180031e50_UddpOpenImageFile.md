# UddpOpenImageFile

- ea: `0x180031e50`
- end: `0x180032225`
- name: `UddpOpenImageFile`
- size: `981`
- prototype: `unsigned int *__fastcall(struct _IMAGE_NT_HEADERS64 *, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800319f0`

## callees

- `0x180012920`
- `0x180031e50`
- `0x1800322a0`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x180032029`
- `ntdll!RtlImageNtHeaderEx` at `0x180032029`
- `ntdll!RtlAllocateHeap` at `0x180031ea3`
- `ntdll!RtlAllocateHeap` at `0x180031ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003210d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003217b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003210d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003217b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031f83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031f83`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031f3a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031f3a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031f9f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031f9f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180031f51`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180031f51`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180031ffd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180031ffd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031fcf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031fcf`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180031f15`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180031f15`

## string_xrefs

- `0x180031ec3`: `UddpOpenImageFile`
- `0x1800320a1`: `UddpOpenImageFile`
- `0x1800320d2`: `UddpOpenImageFile`
- `0x180032129`: `UddpOpenImageFile`
- `0x180032197`: `UddpOpenImageFile`
- `0x180032214`: `UddpOpenImageFile`
- `0x18003211c`: `Failed to GetTempFileName for Driver: '%ls' [%d]`
- `0x1800321f9`: `Failed to GetTempPath2 for Driver: '%ls' [%d]`
- `0x180032094`: `Failed to RtlImageNtHeaderEx for Driver: '%ls' [%d]`
- `0x1800321cf`: `Failed to CreateFileMapping for Driver: '%ls' [%d]`
- `0x18003218a`: `Failed to CreateFile for Driver: '%ls' [%d]`
- `0x18003216f`: `Failed to CopyFile for Driver: '%ls' [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
unsigned int *__fastcall UddpOpenImageFile(struct _IMAGE_NT_HEADERS64 *a1, const WCHAR *a2)
{
  int v4; // r14d
  unsigned int *Heap; // rdi
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rcx
  void *v10; // rax
  NTSTATUS v11; // eax
  PIMAGE_NT_HEADERS v12; // rdx
  IMAGE_DATA_DIRECTORY *v13; // rcx
  DWORD v14; // eax
  int v15; // edx
  int v16; // r8d
  DWORD LastError; // eax
  const char *v18; // r9
  int v19; // r8d
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-270h]
  DWORD dwFlagsAndAttributesa; // [rsp+28h] [rbp-270h]
  PIMAGE_NT_HEADERS NtHeader[3]; // [rsp+48h] [rbp-250h] BYREF
  WCHAR PathName[264]; // [rsp+60h] [rbp-238h] BYREF

  NtHeader[1] = a1;
  if ( !a2 )
    return 0;
  v4 = 0;
  Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x230u);
  NtHeader[2] = (PIMAGE_NT_HEADERS)Heap;
  if ( Heap )
  {
    if ( (unsigned int)GetTempPath2W(260, PathName) - 1 > 0x102 )
    {
      LastError = GetLastError();
      v18 = "Failed to GetTempPath2 for Driver: '%ls' [%d]";
      v19 = 1938;
    }
    else
    {
      if ( !GetTempFileNameW(PathName, L"UDD", 0, (LPWSTR)Heap) )
      {
        dwFlagsAndAttributesa = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"UddpOpenImageFile",
          1948,
          (unsigned int)"Failed to GetTempFileName for Driver: '%ls' [%d]",
          a1,
          dwFlagsAndAttributesa);
        *(_WORD *)Heap = 0;
        goto LABEL_4;
      }
      if ( !CopyFileW(a2, (LPCWSTR)Heap, 0) )
      {
        v14 = GetLastError();
        v15 = 2;
        if ( v14 != 2 )
          v15 = v14;
        v16 = 1960;
        if ( v14 == 2 )
          v16 = 1962;
        AslLogCallPrintf(
          (v14 == 2) + 1,
          (unsigned int)"UddpOpenImageFile",
          v16,
          (unsigned int)"Failed to CopyFile for Driver: '%ls' [%d]",
          a1,
          v15);
        goto LABEL_4;
      }
      FileW = CreateFileW((LPCWSTR)Heap, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      *((_QWORD *)Heap + 65) = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        dwFlagsAndAttributes[0] = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"UddpOpenImageFile",
          1978,
          (unsigned int)"Failed to CreateFile for Driver: '%ls' [%d]",
          a1,
          *(_QWORD *)dwFlagsAndAttributes);
        *((_QWORD *)Heap + 65) = 0;
        goto LABEL_4;
      }
      FileSize = GetFileSize(FileW, 0);
      Heap[132] = FileSize;
      if ( FileSize == -1 )
      {
        LastError = GetLastError();
        v18 = "Failed to GetFileSize for Driver: '%ls' [%d]";
        v19 = 1987;
      }
      else
      {
        FileMappingW = CreateFileMappingW(*((HANDLE *)Heap + 65), 0, 0x11000002u, 0, 0, 0);
        *((_QWORD *)Heap + 67) = FileMappingW;
        if ( FileMappingW )
        {
          v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, Heap[132]);
          *((_QWORD *)Heap + 68) = v10;
          if ( v10 )
          {
            NtHeader[0] = 0;
            v11 = RtlImageNtHeaderEx(0, v10, Heap[132], NtHeader);
            if ( v11 >= 0 && (v12 = NtHeader[0]) != 0 )
            {
              v13 = 0;
              *((_WORD *)Heap + 276) = NtHeader[0]->FileHeader.Machine;
              if ( v12->OptionalHeader.Magic == 267 )
              {
                v13 = &v12->OptionalHeader.DataDirectory[2];
              }
              else if ( v12->OptionalHeader.Magic == 523 )
              {
                v13 = &v12->OptionalHeader.DataDirectory[4];
              }
              if ( v13 && v13->VirtualAddress && v13->Size )
                Heap[139] = 1;
              v4 = 1;
            }
            else
            {
              dwFlagsAndAttributes[0] = v11;
              AslLogCallPrintf(
                1,
                (unsigned int)"UddpOpenImageFile",
                2029,
                (unsigned int)"Failed to RtlImageNtHeaderEx for Driver: '%ls' [%d]",
                a1,
                *(_QWORD *)dwFlagsAndAttributes);
            }
            goto LABEL_4;
          }
          LastError = GetLastError();
          v18 = "Failed to MapViewOfFile for Driver: '%ls' [%d]";
          v19 = 2014;
        }
        else
        {
          LastError = GetLastError();
          v18 = "Failed to CreateFileMapping for Driver: '%ls' [%d]";
          v19 = 2001;
        }
      }
    }
    dwFlagsAndAttributes[0] = LastError;
    AslLogCallPrintf(1, (unsigned int)"UddpOpenImageFile", v19, (_DWORD)v18, a1, *(_QWORD *)dwFlagsAndAttributes);
    goto LABEL_4;
  }
  AslLogCallPrintf(1, (unsigned int)"UddpOpenImageFile", 1931, (unsigned int)"Failed to allocate memory for file info");
LABEL_4:
  if ( !v4 )
  {
    UddpCloseImageFile(Heap);
    return 0;
  }
  return Heap;
}

```

## disassembly

```asm
0x180031e50  mov     [rsp+arg_10], rbx
0x180031e55  mov     [rsp+arg_18], rsi
0x180031e5a  push    rdi
0x180031e5b  push    r14
0x180031e5d  push    r15
0x180031e5f  sub     rsp, 280h
0x180031e66  mov     rax, cs:__security_cookie
0x180031e6d  xor     rax, rsp
0x180031e70  mov     [rsp+298h+var_28], rax
0x180031e78  mov     r15, rdx
0x180031e7b  mov     rsi, rcx
0x180031e7e  mov     [rsp+298h+var_248], rcx
0x180031e83  xor     ebx, ebx
0x180031e85  test    rdx, rdx
0x180031e88  jz      short loc_180031F07
0x180031e8a  mov     r14d, ebx
0x180031e8d  mov     rcx, gs:60h
0x180031e96  lea     edx, [rbx+8]; Flags
0x180031e99  mov     r8d, 230h; Size
0x180031e9f  mov     rcx, [rcx+30h]; HeapHandle
0x180031ea3  call    cs:__imp_RtlAllocateHeap
0x180031ea9  mov     rdi, rax
0x180031eac  mov     [rsp+298h+var_240], rax
0x180031eb1  test    rax, rax
0x180031eb4  jnz     short loc_180031F0B
0x180031eb6  lea     r9, aFailedToAlloca_11; "Failed to allocate memory for file info"
0x180031ebd  mov     r8d, 78Bh
0x180031ec3  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x180031eca  lea     ecx, [rbx+1]
0x180031ecd  call    AslLogCallPrintf
0x180031ed2  test    r14d, r14d
0x180031ed5  jz      loc_1800320FD
0x180031edb  mov     rax, rdi
0x180031ede  mov     rcx, [rsp+298h+var_28]
0x180031ee6  xor     rcx, rsp; StackCookie
0x180031ee9  call    __security_check_cookie
0x180031eee  lea     r11, [rsp+298h+var_18]
0x180031ef6  mov     rbx, [r11+30h]
0x180031efa  mov     rsi, [r11+38h]
0x180031efe  mov     rsp, r11
0x180031f01  pop     r15
0x180031f03  pop     r14
0x180031f05  pop     rdi
0x180031f06  retn
0x180031f07  xor     eax, eax
0x180031f09  jmp     short loc_180031EDE
0x180031f0b  lea     rdx, [rsp+298h+PathName]
0x180031f10  mov     ecx, 104h
0x180031f15  call    cs:__imp_GetTempPath2W
0x180031f1b  dec     eax
0x180031f1d  cmp     eax, 102h
0x180031f22  ja      loc_1800321F3
0x180031f28  mov     r9, rdi; lpTempFileName
0x180031f2b  xor     r8d, r8d; uUnique
0x180031f2e  lea     rdx, PrefixString; "UDD"
0x180031f35  lea     rcx, [rsp+298h+PathName]; lpPathName
0x180031f3a  call    cs:__imp_GetTempFileNameW
0x180031f40  test    eax, eax
0x180031f42  jz      loc_18003210D
0x180031f48  xor     r8d, r8d; bFailIfExists
0x180031f4b  mov     rdx, rdi; lpNewFileName
0x180031f4e  mov     rcx, r15; lpExistingFileName
0x180031f51  call    cs:__imp_CopyFileW
0x180031f57  test    eax, eax
0x180031f59  jz      loc_180032142
0x180031f5f  mov     [rsp+298h+hTemplateFile], rbx; hTemplateFile
0x180031f64  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180031f6c  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x180031f74  xor     r9d, r9d; lpSecurityAttributes
0x180031f77  mov     edx, 80000000h; dwDesiredAccess
0x180031f7c  lea     r8d, [r9+5]; dwShareMode
0x180031f80  mov     rcx, rdi; lpFileName
0x180031f83  call    cs:__imp_CreateFileW
0x180031f89  mov     [rdi+208h], rax
0x180031f90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031f94  jz      loc_18003217B
0x180031f9a  xor     edx, edx; lpFileSizeHigh
0x180031f9c  mov     rcx, rax; hFile
0x180031f9f  call    cs:__imp_GetFileSize
0x180031fa5  mov     [rdi+210h], eax
0x180031fab  cmp     eax, 0FFFFFFFFh
0x180031fae  jz      loc_1800321B4
0x180031fb4  mov     qword ptr [rsp+298h+dwFlagsAndAttributes], rbx; lpName
0x180031fb9  mov     [rsp+298h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x180031fbd  xor     r9d, r9d; dwMaximumSizeHigh
0x180031fc0  xor     edx, edx; lpFileMappingAttributes
0x180031fc2  mov     r8d, 11000002h; flProtect
0x180031fc8  mov     rcx, [rdi+208h]; hFile
0x180031fcf  call    cs:__imp_CreateFileMappingW
0x180031fd5  mov     rcx, rax; hFileMappingObject
0x180031fd8  mov     [rdi+218h], rax
0x180031fdf  test    rax, rax
0x180031fe2  jz      loc_1800321C9
0x180031fe8  mov     eax, [rdi+210h]
0x180031fee  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x180031ff3  xor     r9d, r9d; dwFileOffsetLow
0x180031ff6  xor     r8d, r8d; dwFileOffsetHigh
0x180031ff9  lea     edx, [r9+4]; dwDesiredAccess
0x180031ffd  call    cs:__imp_MapViewOfFile
0x180032003  mov     [rdi+220h], rax
0x18003200a  test    rax, rax
0x18003200d  jz      loc_1800321DE
0x180032013  mov     [rsp+298h+NtHeader], rbx
0x180032018  mov     r8d, [rdi+210h]; Size
0x18003201f  lea     r9, [rsp+298h+NtHeader]; NtHeader
0x180032024  mov     rdx, rax; BaseAddress
0x180032027  xor     ecx, ecx; Flags
0x180032029  call    cs:__imp_RtlImageNtHeaderEx
0x18003202f  test    eax, eax
0x180032031  js      short loc_18003208B
0x180032033  mov     rdx, [rsp+298h+NtHeader]
0x180032038  test    rdx, rdx
0x18003203b  jz      short loc_18003208B
0x18003203d  mov     rcx, rbx
0x180032040  movzx   eax, word ptr [rdx+4]
0x180032044  mov     [rdi+228h], ax
0x18003204b  mov     eax, 10Bh
0x180032050  cmp     ax, [rdx+18h]
0x180032054  jz      short loc_180032082
0x180032056  mov     eax, 20Bh
0x18003205b  cmp     ax, [rdx+18h]
0x18003205f  jnz     short loc_180032068
0x180032061  lea     rcx, [rdx+0A8h]
0x180032068  test    rcx, rcx
0x18003206b  jz      short loc_180032080
0x18003206d  cmp     [rcx], ebx
0x18003206f  jz      short loc_180032080
0x180032071  cmp     [rcx+4], ebx
0x180032074  jz      short loc_180032080
0x180032076  mov     dword ptr [rdi+22Ch], 1
0x180032080  jmp     short loc_1800320F2
0x180032082  lea     rcx, [rdx+98h]
0x180032089  jmp     short loc_180032068
0x18003208b  mov     [rsp+298h+dwFlagsAndAttributes], eax
0x18003208f  mov     qword ptr [rsp+298h+dwCreationDisposition], rsi
0x180032094  lea     r9, aFailedToRtlima; "Failed to RtlImageNtHeaderEx for Driver"...
0x18003209b  mov     r8d, 7EDh
0x1800320a1  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x1800320a8  mov     ecx, 1
0x1800320ad  call    AslLogCallPrintf
0x1800320b2  jmp     loc_180031ED2
0x1800320b7  mov     [rsp+298h+dwFlagsAndAttributes], eax
0x1800320bb  mov     rax, [rsp+298h+var_248]
0x1800320c0  mov     qword ptr [rsp+298h+dwCreationDisposition], rax
0x1800320c5  lea     r9, aMappedMemoryEx; "Mapped memory exception for Driver: '%l"...
0x1800320cc  mov     r8d, 806h
0x1800320d2  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x1800320d9  mov     ecx, 1
0x1800320de  call    AslLogCallPrintf
0x1800320e3  xor     ebx, ebx
0x1800320e5  mov     r14d, ebx
0x1800320e8  mov     rdi, [rsp+298h+var_240]
0x1800320ed  jmp     loc_180031ED2
0x1800320f2  mov     r14d, 1
0x1800320f8  jmp     loc_180031ED2
0x1800320fd  mov     rcx, rdi; P
0x180032100  call    UddpCloseImageFile
0x180032105  mov     rdi, rbx
0x180032108  jmp     loc_180031EDB
0x18003210d  call    cs:__imp_GetLastError
0x180032113  mov     [rsp+298h+dwFlagsAndAttributes], eax
0x180032117  mov     qword ptr [rsp+298h+dwCreationDisposition], rsi
0x18003211c  lea     r9, aFailedToGettem_0; "Failed to GetTempFileName for Driver: '"...
0x180032123  mov     r8d, 79Ch
0x180032129  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x180032130  mov     ecx, 1
0x180032135  call    AslLogCallPrintf
0x18003213a  mov     [rdi], bx
0x18003213d  jmp     loc_180031ED2
0x180032142  call    cs:__imp_GetLastError
0x180032148  mov     r9d, 2
0x18003214e  mov     edx, r9d
0x180032151  cmp     eax, r9d
0x180032154  cmovnz  edx, eax
0x180032157  mov     ecx, 7AAh
0x18003215c  lea     r8d, [rcx-2]
0x180032160  cmovz   r8d, ecx
0x180032164  mov     ecx, ebx
0x180032166  setz    cl
0x180032169  inc     ecx
0x18003216b  mov     [rsp+298h+dwFlagsAndAttributes], edx
0x18003216f  lea     r9, aFailedToCopyfi; "Failed to CopyFile for Driver: '%ls' [%"...
0x180032176  jmp     loc_18003220F
0x18003217b  call    cs:__imp_GetLastError
0x180032181  mov     [rsp+298h+dwFlagsAndAttributes], eax
0x180032185  mov     qword ptr [rsp+298h+dwCreationDisposition], rsi
0x18003218a  lea     r9, aFailedToCreate_49; "Failed to CreateFile for Driver: '%ls' "...
0x180032191  mov     r8d, 7BAh
0x180032197  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x18003219e  mov     ecx, 1
0x1800321a3  call    AslLogCallPrintf
0x1800321a8  mov     [rdi+208h], rbx
0x1800321af  jmp     loc_180031ED2
0x1800321b4  call    cs:__imp_GetLastError
0x1800321ba  lea     r9, aFailedToGetfil; "Failed to GetFileSize for Driver: '%ls'"...
0x1800321c1  mov     r8d, 7C3h
0x1800321c7  jmp     short loc_180032206
0x1800321c9  call    cs:__imp_GetLastError
0x1800321cf  lea     r9, aFailedToCreate_94; "Failed to CreateFileMapping for Driver:"...
0x1800321d6  mov     r8d, 7D1h
0x1800321dc  jmp     short loc_180032206
0x1800321de  call    cs:__imp_GetLastError
0x1800321e4  lea     r9, aFailedToMapvie; "Failed to MapViewOfFile for Driver: '%l"...
0x1800321eb  mov     r8d, 7DEh
0x1800321f1  jmp     short loc_180032206
0x1800321f3  call    cs:__imp_GetLastError
0x1800321f9  lea     r9, aFailedToGettem; "Failed to GetTempPath2 for Driver: '%ls"...
0x180032200  mov     r8d, 792h
0x180032206  mov     ecx, 1
0x18003220b  mov     [rsp+298h+dwFlagsAndAttributes], eax
0x18003220f  mov     qword ptr [rsp+298h+dwCreationDisposition], rsi
0x180032214  lea     rdx, aUddpopenimagef; "UddpOpenImageFile"
0x18003221b  call    AslLogCallPrintf
0x180032220  jmp     loc_180031ED2
```
