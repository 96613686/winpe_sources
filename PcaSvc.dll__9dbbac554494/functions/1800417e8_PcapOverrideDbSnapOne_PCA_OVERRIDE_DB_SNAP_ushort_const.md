# PcapOverrideDbSnapOne(_PCA_OVERRIDE_DB_SNAP *,ushort const *)

- ea: `0x1800417e8`
- end: `0x18004194c`
- name: `?PcapOverrideDbSnapOne@@YAKPEAU_PCA_OVERRIDE_DB_SNAP@@PEBG@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct _PCA_OVERRIDE_DB_SNAP *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18004cbb4`

## callees

- `0x180012920`
- `0x1800417e8`
- `0x180049a30`
- `0x18004cc98`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004188e`
- `ntdll!RtlAllocateHeap` at `0x18004188e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004192d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004192d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800418cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800418cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041829`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041829`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004186d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004186d`

## string_xrefs

- `0x180041842`: `Failed to open %S: %08lx`
- `0x1800418eb`: `Failed to read the sdb: %08lx`

## pseudocode

```c
__int64 __fastcall PcapOverrideDbSnapOne(struct _PCA_OVERRIDE_DB_SNAP *a1, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  void *v5; // rsi
  DWORD LastError; // ebx
  DWORD FileSize; // eax
  PVOID Heap; // rax
  int v9; // r8d
  __int64 inited; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-48h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]

  PcapOverrideDbSnapFree(a1);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(dwFlagsAndAttributes) = GetLastError();
    LastError = dwFlagsAndAttributes;
    AslLogCallPrintf(
      1,
      (unsigned int)"PcapOverrideDbSnapOne",
      126,
      (unsigned int)"Failed to open %S: %08lx",
      lpFileName,
      dwFlagsAndAttributes);
    goto LABEL_12;
  }
  FileSize = GetFileSize(FileW, 0);
  LastError = 8;
  *((_DWORD *)a1 + 4) = FileSize;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, FileSize);
  *((_QWORD *)a1 + 1) = Heap;
  if ( Heap )
  {
    if ( ReadFile(v5, Heap, *((_DWORD *)a1 + 4), 0, 0) )
    {
      inited = SdbInitDatabaseInMemory(*((_QWORD *)a1 + 1), *((unsigned int *)a1 + 4));
      *(_QWORD *)a1 = inited;
      if ( inited )
      {
        LastError = 0;
        goto LABEL_11;
      }
      LastError = 1359;
      v9 = 158;
      dwCreationDisposition[0] = 1359;
    }
    else
    {
      LastError = GetLastError();
      dwCreationDisposition[0] = LastError;
      v9 = 146;
    }
    AslLogCallPrintf(
      1,
      (unsigned int)"PcapOverrideDbSnapOne",
      v9,
      (unsigned int)"Failed to read the sdb: %08lx",
      *(_QWORD *)dwCreationDisposition);
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"PcapOverrideDbSnapOne", 135, (unsigned int)"Out of memory");
  }
LABEL_11:
  CloseHandle(v5);
LABEL_12:
  if ( LastError )
    PcapOverrideDbSnapFree(a1);
  return LastError;
}

```

## disassembly

```asm
0x1800417e8  push    rbx
0x1800417ea  push    rbp
0x1800417eb  push    rsi
0x1800417ec  push    rdi
0x1800417ed  push    r14
0x1800417ef  sub     rsp, 40h
0x1800417f3  mov     rbp, rdx
0x1800417f6  mov     rdi, rcx
0x1800417f9  call    ?PcapOverrideDbSnapFree@@YAXPEAU_PCA_OVERRIDE_DB_SNAP@@@Z; PcapOverrideDbSnapFree(_PCA_OVERRIDE_DB_SNAP *)
0x1800417fe  xor     r9d, r9d; lpSecurityAttributes
0x180041801  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18004180a  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180041812  mov     edx, 80000000h; dwDesiredAccess
0x180041817  mov     rcx, rbp; lpFileName
0x18004181a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180041822  lea     r14d, [r9+1]
0x180041826  mov     r8d, r14d; dwShareMode
0x180041829  call    cs:__imp_CreateFileW
0x18004182f  mov     rsi, rax
0x180041832  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041836  jnz     short loc_180041868
0x180041838  call    cs:__imp_GetLastError
0x18004183e  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], eax
0x180041842  lea     r9, aFailedToOpenS0; "Failed to open %S: %08lx"
0x180041849  mov     ecx, r14d
0x18004184c  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp
0x180041851  lea     r8d, [r14+7Dh]
0x180041855  mov     ebx, eax
0x180041857  lea     rdx, aPcapoverridedb; "PcapOverrideDbSnapOne"
0x18004185e  call    AslLogCallPrintf
0x180041863  jmp     loc_180041933
0x180041868  xor     edx, edx; lpFileSizeHigh
0x18004186a  mov     rcx, rsi; hFile
0x18004186d  call    cs:__imp_GetFileSize
0x180041873  mov     r8d, eax; Size
0x180041876  mov     ebx, 8
0x18004187b  mov     [rdi+10h], r8d
0x18004187f  mov     edx, ebx; Flags
0x180041881  mov     rcx, gs:60h
0x18004188a  mov     rcx, [rcx+30h]; HeapHandle
0x18004188e  call    cs:__imp_RtlAllocateHeap
0x180041894  mov     [rdi+8], rax
0x180041898  test    rax, rax
0x18004189b  jnz     short loc_1800418B9
0x18004189d  lea     r9, aOutOfMemory; "Out of memory"
0x1800418a4  mov     ecx, r14d
0x1800418a7  lea     r8d, [rbx+7Fh]
0x1800418ab  lea     rdx, aPcapoverridedb; "PcapOverrideDbSnapOne"
0x1800418b2  call    AslLogCallPrintf
0x1800418b7  jmp     short loc_18004192A
0x1800418b9  mov     r8d, [rdi+10h]; nNumberOfBytesToRead
0x1800418bd  xor     r9d, r9d; lpNumberOfBytesRead
0x1800418c0  mov     rdx, rax; lpBuffer
0x1800418c3  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800418cc  mov     rcx, rsi; hFile
0x1800418cf  call    cs:__imp_ReadFile
0x1800418d5  test    eax, eax
0x1800418d7  jnz     short loc_180041903
0x1800418d9  call    cs:__imp_GetLastError
0x1800418df  mov     ebx, eax
0x1800418e1  mov     [rsp+68h+dwCreationDisposition], eax
0x1800418e5  mov     r8d, 92h
0x1800418eb  lea     r9, aFailedToReadTh_7; "Failed to read the sdb: %08lx"
0x1800418f2  mov     ecx, r14d
0x1800418f5  lea     rdx, aPcapoverridedb; "PcapOverrideDbSnapOne"
0x1800418fc  call    AslLogCallPrintf
0x180041901  jmp     short loc_18004192A
0x180041903  mov     edx, [rdi+10h]
0x180041906  mov     rcx, [rdi+8]
0x18004190a  call    SdbInitDatabaseInMemory
0x18004190f  mov     [rdi], rax
0x180041912  test    rax, rax
0x180041915  jnz     short loc_180041928
0x180041917  mov     ebx, 54Fh
0x18004191c  mov     r8d, 9Eh
0x180041922  mov     [rsp+68h+dwCreationDisposition], ebx
0x180041926  jmp     short loc_1800418EB
0x180041928  xor     ebx, ebx
0x18004192a  mov     rcx, rsi; hObject
0x18004192d  call    cs:__imp_CloseHandle
0x180041933  test    ebx, ebx
0x180041935  jz      short loc_18004193F
0x180041937  mov     rcx, rdi; struct _PCA_OVERRIDE_DB_SNAP *
0x18004193a  call    ?PcapOverrideDbSnapFree@@YAXPEAU_PCA_OVERRIDE_DB_SNAP@@@Z; PcapOverrideDbSnapFree(_PCA_OVERRIDE_DB_SNAP *)
0x18004193f  mov     eax, ebx
0x180041941  add     rsp, 40h
0x180041945  pop     r14
0x180041947  pop     rdi
0x180041948  pop     rsi
0x180041949  pop     rbp
0x18004194a  pop     rbx
0x18004194b  retn
```
