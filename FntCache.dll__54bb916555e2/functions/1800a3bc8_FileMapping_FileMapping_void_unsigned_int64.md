# FileMapping::FileMapping(void *,unsigned __int64)

- ea: `0x1800a3bc8`
- end: `0x1800a3c35`
- name: `??0FileMapping@@QEAA@PEAX_K@Z`
- size: `109`
- prototype: `FileMapping *(FileMapping *__hidden this, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800105b4`
- `0x180041908`

## callees

- `0x1800a1558`
- `0x1800a3bc8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a3c0f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a3c0f`

## pseudocode

```c
FileMapping *__fastcall FileMapping::FileMapping(FileMapping *this, void *a2, __int64 dwMaximumSizeLow)
{
  HANDLE FileMappingW; // rax
  FileMapping *result; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  FileMappingW = CreateFileMappingW(a2, 0, 4u, HIDWORD(dwMaximumSizeLow), dwMaximumSizeLow, 0);
  if ( !FileMappingW )
    OSException::ThrowLastError();
  *(_QWORD *)this = FileMappingW;
  result = this;
  *((_QWORD *)this + 2) = dwMaximumSizeLow;
  return result;
}

```

## disassembly

```asm
0x1800a3bc8  mov     [rsp+arg_0], rbx
0x1800a3bcd  push    rdi
0x1800a3bce  sub     rsp, 30h
0x1800a3bd2  mov     rax, rdx
0x1800a3bd5  mov     qword ptr [rcx], 0
0x1800a3bdc  mov     r9, r8
0x1800a3bdf  mov     qword ptr [rcx+8], 0
0x1800a3be7  mov     rdi, r8
0x1800a3bea  mov     qword ptr [rcx+10h], 0
0x1800a3bf2  xor     edx, edx; lpFileMappingAttributes
0x1800a3bf4  shr     r9, 20h; dwMaximumSizeHigh
0x1800a3bf8  mov     rbx, rcx
0x1800a3bfb  mov     [rsp+38h+lpName], 0; lpName
0x1800a3c04  mov     rcx, rax; hFile
0x1800a3c07  mov     [rsp+38h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x1800a3c0b  lea     r8d, [rdx+4]; flProtect
0x1800a3c0f  call    cs:__imp_CreateFileMappingW
0x1800a3c15  test    rax, rax
0x1800a3c18  jnz     short loc_1800A3C20
0x1800a3c1a  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800a3c20  mov     [rbx], rax
0x1800a3c23  mov     rax, rbx
0x1800a3c26  mov     [rbx+10h], rdi
0x1800a3c2a  mov     rbx, [rsp+38h+arg_0]
0x1800a3c2f  add     rsp, 30h
0x1800a3c33  pop     rdi
0x1800a3c34  retn
```
