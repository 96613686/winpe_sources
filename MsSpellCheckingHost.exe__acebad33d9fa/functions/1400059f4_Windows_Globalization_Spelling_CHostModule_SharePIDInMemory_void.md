# Windows::Globalization::Spelling::CHostModule::SharePIDInMemory(void)

- ea: `0x1400059f4`
- end: `0x140005ae9`
- name: `?SharePIDInMemory@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ`
- size: `245`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CHostModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000584c`

## callees

- `0x1400059f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ad1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140005aa2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140005aa2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140005a2d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140005a2d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140005a71`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140005a71`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostModule::SharePIDInMemory(
        Windows::Globalization::Spelling::CHostModule *this)
{
  signed int v1; // ebx
  DWORD CurrentProcessId; // esi
  HANDLE FileMappingW; // rax
  signed int LastError; // eax
  _DWORD *v5; // rdi
  signed int v6; // eax
  signed int v7; // eax

  v1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x40u, 0, 4u, L"SpellingHostPIDSharedMemory");
  hObject = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_15;
    FileMappingW = hObject;
  }
  v5 = MapViewOfFile(FileMappingW, 2u, 0, 0, 4u);
  if ( !v5 )
  {
    v6 = GetLastError();
    v1 = v6;
    if ( v6 > 0 )
      v1 = (unsigned __int16)v6 | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_15;
  }
  *v5 = CurrentProcessId;
  if ( v5 )
  {
    if ( !UnmapViewOfFile(v5) )
    {
      v7 = GetLastError();
      v1 = v7;
      if ( v7 > 0 )
        v1 = (unsigned __int16)v7 | 0x80070000;
    }
  }
  if ( v1 < 0 )
  {
LABEL_15:
    if ( hObject )
      CloseHandle(hObject);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400059f4  mov     [rsp+arg_0], rbx
0x1400059f9  mov     [rsp+arg_8], rsi
0x1400059fe  push    rdi
0x1400059ff  sub     rsp, 30h
0x140005a03  xor     ebx, ebx
0x140005a05  call    cs:__imp_GetCurrentProcessId
0x140005a0b  lea     edi, [rbx+4]
0x140005a0e  xor     r9d, r9d; dwMaximumSizeHigh
0x140005a11  mov     esi, eax
0x140005a13  lea     r8d, [rbx+40h]; flProtect
0x140005a17  lea     rax, aSpellinghostpi; "SpellingHostPIDSharedMemory"
0x140005a1e  xor     edx, edx; lpFileMappingAttributes
0x140005a20  mov     [rsp+38h+lpName], rax; lpName
0x140005a25  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140005a29  mov     [rsp+38h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x140005a2d  call    cs:__imp_CreateFileMappingW
0x140005a33  mov     cs:hObject, rax
0x140005a3a  test    rax, rax
0x140005a3d  jnz     short loc_140005A5F
0x140005a3f  call    cs:__imp_GetLastError
0x140005a45  mov     ebx, eax
0x140005a47  test    eax, eax
0x140005a49  jle     short loc_140005A54
0x140005a4b  movzx   ebx, ax
0x140005a4e  or      ebx, 80070000h
0x140005a54  test    ebx, ebx
0x140005a56  js      short loc_140005AC5
0x140005a58  mov     rax, cs:hObject
0x140005a5f  xor     r9d, r9d; dwFileOffsetLow
0x140005a62  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x140005a67  xor     r8d, r8d; dwFileOffsetHigh
0x140005a6a  mov     rcx, rax; hFileMappingObject
0x140005a6d  lea     edx, [r9+2]; dwDesiredAccess
0x140005a71  call    cs:__imp_MapViewOfFile
0x140005a77  mov     rdi, rax
0x140005a7a  test    rax, rax
0x140005a7d  jnz     short loc_140005A98
0x140005a7f  call    cs:__imp_GetLastError
0x140005a85  mov     ebx, eax
0x140005a87  test    eax, eax
0x140005a89  jle     short loc_140005A94
0x140005a8b  movzx   ebx, ax
0x140005a8e  or      ebx, 80070000h
0x140005a94  test    ebx, ebx
0x140005a96  js      short loc_140005AC5
0x140005a98  mov     [rdi], esi
0x140005a9a  test    rdi, rdi
0x140005a9d  jz      short loc_140005AC1
0x140005a9f  mov     rcx, rdi; lpBaseAddress
0x140005aa2  call    cs:__imp_UnmapViewOfFile
0x140005aa8  test    eax, eax
0x140005aaa  jnz     short loc_140005AC1
0x140005aac  call    cs:__imp_GetLastError
0x140005ab2  mov     ebx, eax
0x140005ab4  test    eax, eax
0x140005ab6  jle     short loc_140005AC1
0x140005ab8  movzx   ebx, ax
0x140005abb  or      ebx, 80070000h
0x140005ac1  test    ebx, ebx
0x140005ac3  jns     short loc_140005AD7
0x140005ac5  mov     rcx, cs:hObject; hObject
0x140005acc  test    rcx, rcx
0x140005acf  jz      short loc_140005AD7
0x140005ad1  call    cs:__imp_CloseHandle
0x140005ad7  mov     rsi, [rsp+38h+arg_8]
0x140005adc  mov     eax, ebx
0x140005ade  mov     rbx, [rsp+38h+arg_0]
0x140005ae3  add     rsp, 30h
0x140005ae7  pop     rdi
0x140005ae8  retn
```
