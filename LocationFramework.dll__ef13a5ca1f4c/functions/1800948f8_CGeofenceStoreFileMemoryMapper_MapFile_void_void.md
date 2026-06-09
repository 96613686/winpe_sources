# CGeofenceStoreFileMemoryMapper::MapFile(void *,void * *)

- ea: `0x1800948f8`
- end: `0x180094a04`
- name: `?MapFile@CGeofenceStoreFileMemoryMapper@@QEAAJPEAXPEAPEAX@Z`
- size: `268`
- prototype: `int(CGeofenceStoreFileMemoryMapper *__hidden this, void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180043f64`

## callees

- `0x180016e30`
- `0x1800948f8`
- `0x1801004ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800949b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800949b3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800949a4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800949a4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180094934`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180094934`

## string_xrefs

- `0x180094976`: `CreateFileMapping failed`

## pseudocode

```c
__int64 __fastcall CGeofenceStoreFileMemoryMapper::MapFile(HANDLE *this, void *a2, void **a3)
{
  HANDLE FileMappingW; // rax
  unsigned int v6; // ebx
  signed int v7; // eax
  __int64 v8; // rcx
  LPVOID v9; // rax
  signed int LastError; // eax
  __int64 v11; // rcx

  *a3 = 0;
  FileMappingW = CreateFileMappingW(a2, 0, 4u, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this,
    FileMappingW);
  if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = 0;
LABEL_8:
    v9 = MapViewOfFile(*this, 0xF001Fu, 0, 0, 0);
    this[1] = v9;
    if ( v9 )
      goto LABEL_14;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, GeofenceStoreInternalError, L"MapViewOfFile failed", v6);
    if ( (v6 & 0x80000000) == 0 )
LABEL_14:
      *a3 = this[1];
    return v6;
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( (byte_1801E39C4 & 0x10) != 0 )
    McTemplateU0zq_EventWriteTransfer(v8, GeofenceStoreInternalError, L"CreateFileMapping failed", v6);
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_8;
  return v6;
}

```

## disassembly

```asm
0x1800948f8  mov     [rsp+arg_0], rbx
0x1800948fd  mov     [rsp+arg_8], rsi
0x180094902  push    rdi
0x180094903  sub     rsp, 30h
0x180094907  mov     rax, rdx
0x18009490a  mov     qword ptr [r8], 0
0x180094911  xor     r9d, r9d; dwMaximumSizeHigh
0x180094914  mov     [rsp+38h+lpName], 0; lpName
0x18009491d  mov     rsi, r8
0x180094920  mov     [rsp+38h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180094928  mov     rdi, rcx
0x18009492b  xor     edx, edx; lpFileMappingAttributes
0x18009492d  mov     rcx, rax; hFile
0x180094930  lea     r8d, [r9+4]; flProtect
0x180094934  call    cs:__imp_CreateFileMappingW
0x18009493a  mov     rdx, rax
0x18009493d  mov     rcx, rdi
0x180094940  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180094945  mov     rax, [rdi]
0x180094948  dec     rax
0x18009494b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009494f  ja      short loc_180094955
0x180094951  xor     ebx, ebx
0x180094953  jmp     short loc_18009498D
0x180094955  call    cs:__imp_GetLastError
0x18009495b  mov     ebx, eax
0x18009495d  test    eax, eax
0x18009495f  jle     short loc_18009496A
0x180094961  movzx   ebx, ax
0x180094964  or      ebx, 80070000h
0x18009496a  test    cs:byte_1801E39C4, 10h
0x180094971  jz      short loc_180094989
0x180094973  mov     r9d, ebx
0x180094976  lea     r8, aCreatefilemapp; "CreateFileMapping failed"
0x18009497d  lea     rdx, GeofenceStoreInternalError
0x180094984  call    McTemplateU0zq_EventWriteTransfer
0x180094989  test    ebx, ebx
0x18009498b  js      short loc_1800949F2
0x18009498d  mov     rcx, [rdi]; hFileMappingObject
0x180094990  xor     r9d, r9d; dwFileOffsetLow
0x180094993  xor     r8d, r8d; dwFileOffsetHigh
0x180094996  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18009499f  mov     edx, 0F001Fh; dwDesiredAccess
0x1800949a4  call    cs:__imp_MapViewOfFile
0x1800949aa  mov     [rdi+8], rax
0x1800949ae  test    rax, rax
0x1800949b1  jnz     short loc_1800949EB
0x1800949b3  call    cs:__imp_GetLastError
0x1800949b9  mov     ebx, eax
0x1800949bb  test    eax, eax
0x1800949bd  jle     short loc_1800949C8
0x1800949bf  movzx   ebx, ax
0x1800949c2  or      ebx, 80070000h
0x1800949c8  test    cs:byte_1801E39C4, 10h
0x1800949cf  jz      short loc_1800949E7
0x1800949d1  mov     r9d, ebx
0x1800949d4  lea     r8, aMapviewoffileF; "MapViewOfFile failed"
0x1800949db  lea     rdx, GeofenceStoreInternalError
0x1800949e2  call    McTemplateU0zq_EventWriteTransfer
0x1800949e7  test    ebx, ebx
0x1800949e9  js      short loc_1800949F2
0x1800949eb  mov     rcx, [rdi+8]
0x1800949ef  mov     [rsi], rcx
0x1800949f2  mov     rsi, [rsp+38h+arg_8]
0x1800949f7  mov     eax, ebx
0x1800949f9  mov     rbx, [rsp+38h+arg_0]
0x1800949fe  add     rsp, 30h
0x180094a02  pop     rdi
0x180094a03  retn
```
