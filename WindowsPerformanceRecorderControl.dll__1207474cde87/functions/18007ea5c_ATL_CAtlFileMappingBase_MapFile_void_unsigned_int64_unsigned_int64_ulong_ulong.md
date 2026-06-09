# ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)

- ea: `0x18007ea5c`
- end: `0x18007eb28`
- name: `?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z`
- size: `204`
- prototype: `int(ATL::CAtlFileMappingBase *__hidden this, void *, unsigned __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18007f144`

## callees

- `0x18004b39c`
- `0x18007ea5c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007eb09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007eb09`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007ea81`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007ea81`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007eaaa`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007eaaa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18007eaf0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18007eaf0`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFileMappingBase::MapFile(ATL::CAtlFileMappingBase *this, void *a2)
{
  HANDLE FileMappingW; // rax
  void *v5; // rcx
  __int64 result; // rax
  SIZE_T v7; // rax
  LPVOID v8; // rax
  unsigned int Error; // ebx
  SIZE_T dwNumberOfBytesToMap; // [rsp+58h] [rbp+20h] BYREF

  HIDWORD(dwNumberOfBytesToMap) = 0;
  LODWORD(dwNumberOfBytesToMap) = GetFileSize(a2, (LPDWORD)&dwNumberOfBytesToMap + 1);
  FileMappingW = CreateFileMappingW(a2, 0, 2u, HIDWORD(dwNumberOfBytesToMap), dwNumberOfBytesToMap, 0);
  *((_QWORD *)this + 2) = FileMappingW;
  v5 = FileMappingW;
  if ( !FileMappingW )
    return ATL::AtlHresultFromLastError();
  v7 = dwNumberOfBytesToMap;
  *((_QWORD *)this + 1) = dwNumberOfBytesToMap;
  *((_DWORD *)this + 8) = 4;
  *((_QWORD *)this + 3) = 0;
  v8 = MapViewOfFileEx(v5, 4u, 0, 0, v7, 0);
  *(_QWORD *)this = v8;
  if ( v8 )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  CloseHandle(*((HANDLE *)this + 2));
  result = Error;
  *((_QWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x18007ea5c  mov     rax, rsp
0x18007ea5f  mov     [rax+8], rbx
0x18007ea63  mov     [rax+20h], r9
0x18007ea67  push    rdi
0x18007ea68  sub     rsp, 30h
0x18007ea6c  mov     rbx, rdx
0x18007ea6f  mov     qword ptr [rax+20h], 0
0x18007ea77  mov     rdi, rcx
0x18007ea7a  lea     rdx, [rax+24h]; lpFileSizeHigh
0x18007ea7e  mov     rcx, rbx; hFile
0x18007ea81  call    cs:__imp_GetFileSize
0x18007ea87  xor     edx, edx; lpFileMappingAttributes
0x18007ea89  mov     [rsp+38h+lpName], 0; lpName
0x18007ea92  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x18007ea96  mov     rcx, rbx; hFile
0x18007ea99  mov     r9, [rsp+38h+dwNumberOfBytesToMap]
0x18007ea9e  shr     r9, 20h; dwMaximumSizeHigh
0x18007eaa2  lea     r8d, [rdx+2]; flProtect
0x18007eaa6  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18007eaaa  call    cs:__imp_CreateFileMappingW
0x18007eab0  mov     [rdi+10h], rax
0x18007eab4  mov     rcx, rax; hFileMappingObject
0x18007eab7  test    rax, rax
0x18007eaba  jnz     short loc_18007EAC3
0x18007eabc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007eac1  jmp     short loc_18007EB1D
0x18007eac3  mov     rax, [rsp+38h+dwNumberOfBytesToMap]
0x18007eac8  mov     edx, 4; dwDesiredAccess
0x18007eacd  mov     [rdi+8], rax
0x18007ead1  xor     r9d, r9d; dwFileOffsetLow
0x18007ead4  mov     [rsp+38h+lpName], 0; lpBaseAddress
0x18007eadd  xor     r8d, r8d; dwFileOffsetHigh
0x18007eae0  mov     [rdi+20h], edx
0x18007eae3  mov     qword ptr [rdi+18h], 0
0x18007eaeb  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18007eaf0  call    cs:__imp_MapViewOfFileEx
0x18007eaf6  mov     [rdi], rax
0x18007eaf9  test    rax, rax
0x18007eafc  jnz     short loc_18007EB1B
0x18007eafe  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007eb03  mov     rcx, [rdi+10h]; hObject
0x18007eb07  mov     ebx, eax
0x18007eb09  call    cs:__imp_CloseHandle
0x18007eb0f  mov     eax, ebx
0x18007eb11  mov     qword ptr [rdi+10h], 0
0x18007eb19  jmp     short loc_18007EB1D
0x18007eb1b  xor     eax, eax
0x18007eb1d  mov     rbx, [rsp+38h+arg_0]
0x18007eb22  add     rsp, 30h
0x18007eb26  pop     rdi
0x18007eb27  retn
```
