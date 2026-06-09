# FileMapping::FileMapping(File const &)

- ea: `0x18000f0f8`
- end: `0x18000f194`
- name: `??0FileMapping@@QEAA@AEBVFile@@@Z`
- size: `156`
- prototype: `FileMapping *__fastcall(FileMapping *__hidden this, const struct File *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000df40`

## callees

- `0x18000f0f8`
- `0x1800217ac`
- `0x1800a1558`
- `0x1800a2180`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f142`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f142`

## pseudocode

```c
FileMapping *__fastcall FileMapping::FileMapping(FileMapping *this, const struct File *a2)
{
  HANDLE FileMappingW; // rax
  int v6; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( *((_BYTE *)a2 + 32) )
  {
    Exception::Exception((Exception *)&v6, -2003283968, 0);
    LogAndThrow<FileFormatException>(&v6, 1701603686, 291);
  }
  FileMappingW = CreateFileMappingW(*(HANDLE *)a2, 0, 2u, 0, 0, 0);
  if ( !FileMappingW )
    OSException::ThrowLastError();
  *(_QWORD *)this = FileMappingW;
  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 1);
  return this;
}

```

## disassembly

```asm
0x18000f0f8  mov     [rsp+arg_8], rbx
0x18000f0fd  push    rdi
0x18000f0fe  sub     rsp, 30h
0x18000f102  mov     qword ptr [rcx], 0
0x18000f109  mov     rdi, rdx
0x18000f10c  mov     qword ptr [rcx+8], 0
0x18000f114  mov     rbx, rcx
0x18000f117  mov     qword ptr [rcx+10h], 0
0x18000f11f  cmp     byte ptr [rdx+20h], 0
0x18000f123  jnz     short loc_18000F166
0x18000f125  mov     rcx, [rdi]; hFile
0x18000f128  xor     r9d, r9d; dwMaximumSizeHigh
0x18000f12b  mov     [rsp+38h+lpName], 0; lpName
0x18000f134  xor     edx, edx; lpFileMappingAttributes
0x18000f136  mov     [rsp+38h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18000f13e  lea     r8d, [r9+2]; flProtect
0x18000f142  call    cs:__imp_CreateFileMappingW
0x18000f148  test    rax, rax
0x18000f14b  jz      short loc_18000F18E
0x18000f14d  mov     [rbx], rax
0x18000f150  mov     rax, [rdi+8]
0x18000f154  mov     [rbx+10h], rax
0x18000f158  mov     rax, rbx
0x18000f15b  mov     rbx, [rsp+38h+arg_8]
0x18000f160  add     rsp, 30h
0x18000f164  pop     rdi
0x18000f165  retn
0x18000f166  xor     r8d, r8d; unsigned int
0x18000f169  lea     rcx, [rsp+38h+arg_0]; this
0x18000f16e  mov     edx, 88985000h; int
0x18000f173  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000f178  mov     edx, 656C6966h
0x18000f17d  lea     rcx, [rsp+38h+arg_0]
0x18000f182  mov     r8d, 123h
0x18000f188  call    ??$LogAndThrow@VFileFormatException@@@@YAXAEBVFileFormatException@@VEventTag@@I@Z; LogAndThrow<FileFormatException>(FileFormatException const &,EventTag,uint)
0x18000f18e  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
