# std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>::~unique_ptr<SharedMemory,std::default_delete<SharedMemory>>(void)

- ea: `0x1800049bc`
- end: `0x1800049fb`
- name: `??1?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000fa58`
- `0x18000fa6a`

## callees

- `0x1800049bc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800049ef`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800049ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800049d3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800049d3`

## pseudocode

```c
void __fastcall std::unique_ptr<SharedMemory>::~unique_ptr<SharedMemory>(__int64 *a1)
{
  __int64 v1; // rbx
  const void *v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = *(const void **)(v1 + 8);
    if ( v2 )
      UnmapViewOfFile(v2);
    if ( (unsigned __int64)(*(_QWORD *)v1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)v1);
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x1800049bc  push    rbx
0x1800049be  sub     rsp, 20h
0x1800049c2  mov     rbx, [rcx]
0x1800049c5  test    rbx, rbx
0x1800049c8  jz      short loc_1800049F5
0x1800049ca  mov     rcx, [rbx+8]; lpBaseAddress
0x1800049ce  test    rcx, rcx
0x1800049d1  jz      short loc_1800049D9
0x1800049d3  call    cs:__imp_UnmapViewOfFile
0x1800049d9  mov     rcx, [rbx]; hObject
0x1800049dc  lea     rax, [rcx-1]
0x1800049e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800049e4  ja      short loc_1800049EC
0x1800049e6  call    cs:__imp_CloseHandle
0x1800049ec  mov     rcx, rbx
0x1800049ef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800049f5  add     rsp, 20h
0x1800049f9  pop     rbx
0x1800049fa  retn
```
