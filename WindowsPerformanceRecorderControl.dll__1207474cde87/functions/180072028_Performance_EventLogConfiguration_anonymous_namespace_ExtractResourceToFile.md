# Performance::EventLogConfiguration::_anonymous_namespace_::ExtractResourceToFile

- ea: `0x180072028`
- end: `0x180072188`
- name: `Performance::EventLogConfiguration::_anonymous_namespace_::ExtractResourceToFile`
- size: `352`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180071cfc`

## callees

- `0x1800102a0`
- `0x18002a6b4`
- `0x180037634`
- `0x18004b39c`
- `0x180072028`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x180072074`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x180072074`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x180072087`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x180072087`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180072095`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180072095`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007210f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007210f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800720bf`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800720bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180072142`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180072142`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceW` at `0x180072056`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceW` at `0x180072056`

## string_xrefs

- `0x18007204f`: `WindowsPerformanceRecorderControlManifest.evtxml`

## pseudocode

```c
__int64 __fastcall Performance::EventLogConfiguration::_anonymous_namespace_::ExtractResourceToFile(
        HMODULE hModule,
        __int64 a2,
        LPCWSTR *a3)
{
  HRSRC ResourceW; // rax
  HRSRC v6; // rdi
  DWORD v8; // r14d
  HGLOBAL Resource; // rax
  const void *v10; // rax
  const void *v11; // rbx
  WCHAR *v12; // rax
  UINT TempFileNameW; // eax
  HANDLE FileW; // rax
  unsigned int Error; // ebx
  ATL::CAtlException *v16; // [rsp+48h] [rbp-20h] BYREF
  __int64 NumberOfBytesWritten; // [rsp+78h] [rbp+10h] BYREF
  HANDLE v18; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = a2;
  ResourceW = FindResourceW(hModule, L"WindowsPerformanceRecorderControlManifest.evtxml", (LPCWSTR)0xA);
  v6 = ResourceW;
  if ( !ResourceW )
    return ATL::AtlHresultFromLastError();
  v8 = SizeofResource(hModule, ResourceW);
  if ( !v8 )
    return ATL::AtlHresultFromLastError();
  Resource = LoadResource(hModule, v6);
  if ( !Resource )
    return ATL::AtlHresultFromLastError();
  v10 = LockResource(Resource);
  try
  {
    v11 = v10;
    v12 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(a3, 260);
    TempFileNameW = GetTempFileNameW(L".", L"WPRC", 0, v12);
  }
  catch ( ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  if ( !TempFileNameW )
    return ATL::AtlHresultFromLastError();
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a3);
  v18 = 0;
  FileW = CreateFileW(*a3, 0x40000000u, 0, 0, 2u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    && (v18 = FileW, LODWORD(NumberOfBytesWritten) = 0, WriteFile(FileW, v11, v8, (LPDWORD)&NumberOfBytesWritten, 0)) )
  {
    ATL::CHandle::~CHandle((ATL::CHandle *)&v18);
    return 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    ATL::CHandle::~CHandle((ATL::CHandle *)&v18);
    return Error;
  }
}

```

## disassembly

```asm
0x180072028  mov     [rsp+NumberOfBytesWritten], rdx
0x18007202d  push    rsi
0x18007202e  push    rdi
0x18007202f  push    r14
0x180072031  sub     rsp, 50h
0x180072035  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFEh
0x18007203e  mov     [rsp+68h+arg_0], rbx
0x180072043  mov     rsi, r8
0x180072046  mov     rbx, rcx
0x180072049  mov     r8d, 0Ah; lpType
0x18007204f  lea     rdx, Name; "WindowsPerformanceRecorderControlManife"...
0x180072056  call    cs:__imp_FindResourceW
0x18007205c  mov     rdi, rax
0x18007205f  test    rax, rax
0x180072062  jnz     short loc_18007206E
0x180072064  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180072069  jmp     loc_180072179
0x18007206e  mov     rdx, rdi; hResInfo
0x180072071  mov     rcx, rbx; hModule
0x180072074  call    cs:__imp_SizeofResource
0x18007207a  mov     r14d, eax
0x18007207d  test    eax, eax
0x18007207f  jz      short loc_180072064
0x180072081  mov     rdx, rdi; hResInfo
0x180072084  mov     rcx, rbx; hModule
0x180072087  call    cs:__imp_LoadResource
0x18007208d  test    rax, rax
0x180072090  jz      short loc_180072064
0x180072092  mov     rcx, rax; hResData
0x180072095  call    cs:__imp_LockResource
0x18007209b  mov     rbx, rax
0x18007209e  mov     edx, 104h
0x1800720a3  mov     rcx, rsi
0x1800720a6  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800720ab  mov     r9, rax; lpTempFileName
0x1800720ae  xor     r8d, r8d; uUnique
0x1800720b1  lea     rdx, PrefixString; "WPRC"
0x1800720b8  lea     rcx, PathName; "."
0x1800720bf  call    cs:__imp_GetTempFileNameW
0x1800720c5  test    eax, eax
0x1800720c7  jnz     short loc_1800720D3
0x1800720c9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800720ce  jmp     loc_180072179
0x1800720d3  mov     rcx, rsi
0x1800720d6  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1800720db  nop
0x1800720dc  mov     [rsp+68h+arg_18], 0
0x1800720e8  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800720f1  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800720f9  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180072101  xor     r9d, r9d; lpSecurityAttributes
0x180072104  xor     r8d, r8d; dwShareMode
0x180072107  mov     edx, 40000000h; dwDesiredAccess
0x18007210c  mov     rcx, [rsi]; lpFileName
0x18007210f  call    cs:__imp_CreateFileW
0x180072115  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072119  jz      short loc_18007214C
0x18007211b  mov     [rsp+68h+arg_18], rax
0x180072123  mov     dword ptr [rsp+68h+NumberOfBytesWritten], 0
0x18007212b  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180072134  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180072139  mov     r8d, r14d; nNumberOfBytesToWrite
0x18007213c  mov     rdx, rbx; lpBuffer
0x18007213f  mov     rcx, rax; hFile
0x180072142  call    cs:__imp_WriteFile
0x180072148  test    eax, eax
0x18007214a  jnz     short loc_180072164
0x18007214c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180072151  mov     ebx, eax
0x180072153  lea     rcx, [rsp+68h+arg_18]; this
0x18007215b  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180072160  mov     eax, ebx
0x180072162  jmp     short loc_180072179
0x180072164  lea     rcx, [rsp+68h+arg_18]; this
0x18007216c  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180072171  xor     eax, eax
0x180072173  jmp     short loc_180072179
0x180072175  mov     eax, dword ptr [rsp+68h+NumberOfBytesWritten]
0x180072179  mov     rbx, [rsp+68h+arg_0]
0x18007217e  add     rsp, 50h
0x180072182  pop     r14
0x180072184  pop     rdi
0x180072185  pop     rsi
0x180072186  retn
```
