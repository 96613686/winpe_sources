# CMapiManager::InitSharedOutlookMemory(void)

- ea: `0x18002ebe4`
- end: `0x18002ec6f`
- name: `?InitSharedOutlookMemory@CMapiManager@@AEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015970`

## callees

- `0x18000b9f0`
- `0x18002ebe4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002ec49`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002ec49`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002ec08`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002ec08`

## string_xrefs

- `0x18002ebfc`: `mapiph.dll-profilename`

## pseudocode

```c
__int64 __fastcall CMapiManager::InitSharedOutlookMemory(HANDLE *this)
{
  int Error; // ebx
  HANDLE v3; // rax
  LPVOID v4; // rax

  Error = 0;
  if ( this[25]
    || (v3 = OpenFileMappingW(4u, 0, L"mapiph.dll-profilename"), (this[25] = v3) != 0)
    || (Error = ResultFromLastError(), Error >= 0) )
  {
    if ( !this[26] )
    {
      v4 = MapViewOfFile(this[25], 4u, 0, 0, 0x200u);
      this[26] = v4;
      if ( !v4 )
        return (unsigned int)ResultFromLastError();
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002ebe4  mov     [rsp+arg_0], rbx
0x18002ebe9  push    rdi
0x18002ebea  sub     rsp, 30h
0x18002ebee  xor     ebx, ebx
0x18002ebf0  mov     rdi, rcx
0x18002ebf3  cmp     [rcx+0C8h], rbx
0x18002ebfa  jnz     short loc_18002EC25
0x18002ebfc  lea     r8, aMapiphDllProfi; "mapiph.dll-profilename"
0x18002ec03  xor     edx, edx; bInheritHandle
0x18002ec05  lea     ecx, [rbx+4]; dwDesiredAccess
0x18002ec08  call    cs:__imp_OpenFileMappingW
0x18002ec0e  mov     [rdi+0C8h], rax
0x18002ec15  test    rax, rax
0x18002ec18  jnz     short loc_18002EC25
0x18002ec1a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002ec1f  mov     ebx, eax
0x18002ec21  test    eax, eax
0x18002ec23  js      short loc_18002EC62
0x18002ec25  cmp     qword ptr [rdi+0D0h], 0
0x18002ec2d  jnz     short loc_18002EC62
0x18002ec2f  mov     rcx, [rdi+0C8h]; hFileMappingObject
0x18002ec36  xor     r9d, r9d; dwFileOffsetLow
0x18002ec39  xor     r8d, r8d; dwFileOffsetHigh
0x18002ec3c  mov     [rsp+38h+dwNumberOfBytesToMap], 200h; dwNumberOfBytesToMap
0x18002ec45  lea     edx, [r9+4]; dwDesiredAccess
0x18002ec49  call    cs:__imp_MapViewOfFile
0x18002ec4f  mov     [rdi+0D0h], rax
0x18002ec56  test    rax, rax
0x18002ec59  jnz     short loc_18002EC62
0x18002ec5b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002ec60  mov     ebx, eax
0x18002ec62  mov     eax, ebx
0x18002ec64  mov     rbx, [rsp+38h+arg_0]
0x18002ec69  add     rsp, 30h
0x18002ec6d  pop     rdi
0x18002ec6e  retn
```
