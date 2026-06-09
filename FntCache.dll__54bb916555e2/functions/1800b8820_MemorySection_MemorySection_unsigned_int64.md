# MemorySection::MemorySection(unsigned __int64)

- ea: `0x1800b8820`
- end: `0x1800b8864`
- name: `??0MemorySection@@QEAA@_K@Z`
- size: `68`
- prototype: `MemorySection *(MemorySection *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800b086c`

## callees

- `0x1800a1558`
- `0x1800b8820`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b8847`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b8847`

## pseudocode

```c
MemorySection *__fastcall MemorySection::MemorySection(MemorySection *this, __int64 dwMaximumSizeLow)
{
  HANDLE FileMappingW; // rax

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, HIDWORD(dwMaximumSizeLow), dwMaximumSizeLow, 0);
  if ( !FileMappingW )
    OSException::ThrowLastError();
  *(_QWORD *)this = FileMappingW;
  return this;
}

```

## disassembly

```asm
0x1800b8820  push    rbx
0x1800b8822  sub     rsp, 30h
0x1800b8826  mov     r9, rdx
0x1800b8829  mov     [rsp+38h+lpName], 0; lpName
0x1800b8832  mov     [rsp+38h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x1800b8836  mov     rbx, rcx
0x1800b8839  xor     edx, edx; lpFileMappingAttributes
0x1800b883b  shr     r9, 20h; dwMaximumSizeHigh
0x1800b883f  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800b8843  lea     r8d, [rdx+4]; flProtect
0x1800b8847  call    cs:__imp_CreateFileMappingW
0x1800b884d  test    rax, rax
0x1800b8850  jnz     short loc_1800B8858
0x1800b8852  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800b8858  mov     [rbx], rax
0x1800b885b  mov     rax, rbx
0x1800b885e  add     rsp, 30h
0x1800b8862  pop     rbx
0x1800b8863  retn
```
