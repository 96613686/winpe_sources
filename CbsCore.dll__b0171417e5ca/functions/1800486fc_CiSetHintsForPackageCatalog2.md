# CiSetHintsForPackageCatalog2

- ea: `0x1800486fc`
- end: `0x180048932`
- name: `CiSetHintsForPackageCatalog2`
- size: `566`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1801519f0`

## callees

- `0x18001a17c`
- `0x1800444cc`
- `0x1800486fc`
- `0x180048938`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800487fa`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800487fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800488a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800488a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800488fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048912`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800488fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048912`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048748`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048748`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004876c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004876c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800488e9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800488e9`
- `ntdll!RtlInitUnicodeString` at `0x180048858`
- `ntdll!RtlInitUnicodeString` at `0x180048858`
- `KERNEL32!CreateFileMappingW` at `0x1800487b2`
- `KERNEL32!CreateFileMappingW` at `0x1800487b2`
- `KERNEL32!MapViewOfFile` at `0x1800487dc`
- `KERNEL32!MapViewOfFile` at `0x1800487dc`
- `CRYPT32!CertCreateContext` at `0x180048834`
- `CRYPT32!CertCreateContext` at `0x180048834`
- `CRYPT32!CertFreeCTLContext` at `0x1800488d5`
- `CRYPT32!CertFreeCTLContext` at `0x1800488d5`

## pseudocode

```c
__int64 __fastcall CiSetHintsForPackageCatalog2(PCWSTR SourceString, __int64 a2)
{
  const CTL_CONTEXT *Context; // rsi
  struct Windows::WCP::Implementation::Rtl::ChunkedStream::ChunkPiece *v5; // rdi
  const BYTE *v6; // r14
  void *v7; // r15
  HANDLE FileW; // rax
  void *v9; // rbp
  DWORD LowPart; // ebx
  HANDLE FileMappingW; // rax
  wchar_t *v12; // rax
  const WCHAR *v13; // rdi
  int v14; // eax
  signed int v15; // ebx
  signed int LastError; // eax
  unsigned int v17; // ebx
  struct Windows::WCP::Implementation::Rtl::ChunkedStream::ChunkPiece *v19; // [rsp+40h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-60h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+C8h] [rbp+20h] BYREF

  FileSize.QuadPart = 0;
  v19 = 0;
  Context = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  FileW = CreateFileW(SourceString, 0x80000000, 5u, 0, 3u, 0x8000080u, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL && GetFileSizeEx(FileW, &FileSize) )
  {
    if ( FileSize.HighPart || (LowPart = FileSize.LowPart) == 0 )
    {
      v15 = -1073741538;
LABEL_14:
      if ( v5 )
        Windows::WCP::Implementation::Rtl::AutoChunkPiece::DeleteInstance(v5);
      goto LABEL_20;
    }
    FileMappingW = CreateFileMappingW(v9, 0, 2u, 0, 0, 0);
    v7 = FileMappingW;
    if ( FileMappingW )
    {
      v6 = (const BYTE *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      if ( v6 )
      {
        v12 = wcsrchr(SourceString, 0x5Cu);
        v13 = v12 ? v12 + 1 : SourceString;
        Context = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, v6, LowPart, 5u, 0);
        if ( Context )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, v13);
          v14 = CiCreateCatalogHintFromUnicodeString(&DestinationString, &v19);
          v5 = v19;
          v15 = v14;
          if ( v14 >= 0 )
            v15 = CipSetEasForEachHint(Context->pCtlInfo, a2, v19);
          goto LABEL_14;
        }
      }
    }
  }
  LastError = GetLastError();
  v17 = LastError;
  if ( LastError > 0 )
    v17 = (unsigned __int16)LastError | 0x80070000;
  v15 = v17 & 0xEFFFFFFF;
  if ( v15 >= 0 )
    v15 = -1073741823;
LABEL_20:
  if ( Context )
    CertFreeCTLContext(Context);
  if ( v6 )
    UnmapViewOfFile(v6);
  if ( v7 )
    CloseHandle(v7);
  if ( v9 != (void *)-1LL )
    CloseHandle(v9);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800486fc  mov     rax, rsp
0x1800486ff  push    rbx
0x180048700  push    rbp
0x180048701  push    rsi
0x180048702  push    rdi
0x180048703  push    r12
0x180048705  push    r13
0x180048707  push    r14
0x180048709  push    r15
0x18004870b  sub     rsp, 68h
0x18004870f  xor     ebx, ebx
0x180048711  mov     r13, rdx
0x180048714  mov     [rax-78h], rbx
0x180048718  xor     r9d, r9d; lpSecurityAttributes
0x18004871b  mov     dword ptr [rax-80h], 8000080h
0x180048722  mov     edx, 80000000h; dwDesiredAccess
0x180048727  mov     r12, rcx
0x18004872a  mov     [rax+20h], rbx
0x18004872e  lea     r8d, [rbx+5]; dwShareMode
0x180048732  mov     [rax-68h], rbx
0x180048736  mov     esi, ebx
0x180048738  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180048740  mov     edi, ebx
0x180048742  mov     r14d, ebx
0x180048745  mov     r15d, ebx
0x180048748  call    cs:__imp_CreateFileW
0x18004874f  nop     dword ptr [rax+rax+00h]
0x180048754  mov     rbp, rax
0x180048757  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004875b  jz      loc_1800488A5
0x180048761  lea     rdx, [rsp+0A8h+FileSize]; lpFileSize
0x180048769  mov     rcx, rax; hFile
0x18004876c  call    cs:__imp_GetFileSizeEx
0x180048773  nop     dword ptr [rax+rax+00h]
0x180048778  test    eax, eax
0x18004877a  jz      loc_1800488A5
0x180048780  cmp     dword ptr [rsp+0A8h+FileSize+4], ebx
0x180048787  jnz     loc_180048891
0x18004878d  mov     rbx, qword ptr [rsp+0A8h+FileSize]
0x180048795  test    ebx, ebx
0x180048797  jz      loc_180048891
0x18004879d  mov     [rsp+0A8h+lpName], r15; lpName
0x1800487a2  lea     r8d, [r15+2]; flProtect
0x1800487a6  xor     r9d, r9d; dwMaximumSizeHigh
0x1800487a9  mov     [rsp+0A8h+dwCreationDisposition], esi; dwMaximumSizeLow
0x1800487ad  xor     edx, edx; lpFileMappingAttributes
0x1800487af  mov     rcx, rbp; hFile
0x1800487b2  call    cs:__imp_CreateFileMappingW
0x1800487b9  nop     dword ptr [rax+rax+00h]
0x1800487be  mov     r15, rax
0x1800487c1  test    rax, rax
0x1800487c4  jz      loc_1800488A5
0x1800487ca  xor     r9d, r9d; dwFileOffsetLow
0x1800487cd  mov     qword ptr [rsp+0A8h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x1800487d2  xor     r8d, r8d; dwFileOffsetHigh
0x1800487d5  lea     edx, [r14+4]; dwDesiredAccess
0x1800487d9  mov     rcx, rax; hFileMappingObject
0x1800487dc  call    cs:__imp_MapViewOfFile
0x1800487e3  nop     dword ptr [rax+rax+00h]
0x1800487e8  mov     r14, rax
0x1800487eb  test    rax, rax
0x1800487ee  jz      loc_1800488A5
0x1800487f4  lea     edx, [rdi+5Ch]; Ch
0x1800487f7  mov     rcx, r12; Str
0x1800487fa  call    cs:__imp_wcsrchr
0x180048801  nop     dword ptr [rax+rax+00h]
0x180048806  mov     rdi, rax
0x180048809  test    rax, rax
0x18004880c  jnz     short loc_180048813
0x18004880e  mov     rdi, r12
0x180048811  jmp     short loc_180048817
0x180048813  add     rdi, 2
0x180048817  mov     [rsp+0A8h+lpName], rsi; pCreatePara
0x18004881c  mov     r9d, ebx; cbEncoded
0x18004881f  mov     r8, r14; pbEncoded
0x180048822  mov     [rsp+0A8h+dwCreationDisposition], 5; dwFlags
0x18004882a  mov     edx, 10001h; dwEncodingType
0x18004882f  mov     ecx, 3; dwContextType
0x180048834  call    cs:__imp_CertCreateContext
0x18004883b  nop     dword ptr [rax+rax+00h]
0x180048840  mov     rsi, rax
0x180048843  test    rax, rax
0x180048846  jz      short loc_1800488A5
0x180048848  xorps   xmm0, xmm0
0x18004884b  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180048850  mov     rdx, rdi; SourceString
0x180048853  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180048858  call    cs:__imp_RtlInitUnicodeString
0x18004885f  nop     dword ptr [rax+rax+00h]
0x180048864  lea     rdx, [rsp+0A8h+var_68]
0x180048869  lea     rcx, [rsp+0A8h+DestinationString]
0x18004886e  call    CiCreateCatalogHintFromUnicodeString
0x180048873  mov     rdi, [rsp+0A8h+var_68]
0x180048878  mov     ebx, eax
0x18004887a  test    eax, eax
0x18004887c  js      short loc_180048896
0x18004887e  mov     rcx, [rsi+18h]
0x180048882  mov     r8, rdi
0x180048885  mov     rdx, r13
0x180048888  call    CipSetEasForEachHint
0x18004888d  mov     ebx, eax
0x18004888f  jmp     short loc_180048896
0x180048891  mov     ebx, 0C000011Eh
0x180048896  test    rdi, rdi
0x180048899  jz      short loc_1800488CD
0x18004889b  mov     rcx, rdi; struct Windows::WCP::Implementation::Rtl::ChunkedStream::ChunkPiece *
0x18004889e  call    ?DeleteInstance@AutoChunkPiece@Rtl@Implementation@WCP@Windows@@SAXPEAUChunkPiece@ChunkedStream@2345@@Z; Windows::WCP::Implementation::Rtl::AutoChunkPiece::DeleteInstance(Windows::WCP::Implementation::Rtl::ChunkedStream::ChunkPiece *)
0x1800488a3  jmp     short loc_1800488CD
0x1800488a5  call    cs:__imp_GetLastError
0x1800488ac  nop     dword ptr [rax+rax+00h]
0x1800488b1  mov     ebx, eax
0x1800488b3  test    eax, eax
0x1800488b5  jle     short loc_1800488C0
0x1800488b7  movzx   ebx, ax
0x1800488ba  or      ebx, 80070000h
0x1800488c0  and     ebx, 0EFFFFFFFh
0x1800488c6  jl      short loc_1800488CD
0x1800488c8  mov     ebx, 0C0000001h
0x1800488cd  test    rsi, rsi
0x1800488d0  jz      short loc_1800488E1
0x1800488d2  mov     rcx, rsi; pCtlContext
0x1800488d5  call    cs:__imp_CertFreeCTLContext
0x1800488dc  nop     dword ptr [rax+rax+00h]
0x1800488e1  test    r14, r14
0x1800488e4  jz      short loc_1800488F5
0x1800488e6  mov     rcx, r14; lpBaseAddress
0x1800488e9  call    cs:__imp_UnmapViewOfFile
0x1800488f0  nop     dword ptr [rax+rax+00h]
0x1800488f5  test    r15, r15
0x1800488f8  jz      short loc_180048909
0x1800488fa  mov     rcx, r15; hObject
0x1800488fd  call    cs:__imp_CloseHandle
0x180048904  nop     dword ptr [rax+rax+00h]
0x180048909  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18004890d  jz      short loc_18004891E
0x18004890f  mov     rcx, rbp; hObject
0x180048912  call    cs:__imp_CloseHandle
0x180048919  nop     dword ptr [rax+rax+00h]
0x18004891e  mov     eax, ebx
0x180048920  add     rsp, 68h
0x180048924  pop     r15
0x180048926  pop     r14
0x180048928  pop     r13
0x18004892a  pop     r12
0x18004892c  pop     rdi
0x18004892d  pop     rsi
0x18004892e  pop     rbp
0x18004892f  pop     rbx
0x180048930  retn
```
