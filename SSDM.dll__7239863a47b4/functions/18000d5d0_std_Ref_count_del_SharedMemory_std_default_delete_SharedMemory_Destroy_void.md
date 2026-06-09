# std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Destroy(void)

- ea: `0x18000d5d0`
- end: `0x18000d610`
- name: `?_Destroy@?$_Ref_count_del@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@EEAAXXZ`
- size: `64`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d5d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d604`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5fb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d5e8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d5e8`

## pseudocode

```c
void __fastcall std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Destroy(__int64 a1)
{
  __int64 v1; // rbx
  const void *v2; // rcx

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
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
0x18000d5d0  push    rbx
0x18000d5d2  sub     rsp, 20h
0x18000d5d6  mov     rbx, [rcx+10h]
0x18000d5da  test    rbx, rbx
0x18000d5dd  jz      short loc_18000D60A
0x18000d5df  mov     rcx, [rbx+8]; lpBaseAddress
0x18000d5e3  test    rcx, rcx
0x18000d5e6  jz      short loc_18000D5EE
0x18000d5e8  call    cs:__imp_UnmapViewOfFile
0x18000d5ee  mov     rcx, [rbx]; hObject
0x18000d5f1  lea     rax, [rcx-1]
0x18000d5f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d5f9  ja      short loc_18000D601
0x18000d5fb  call    cs:__imp_CloseHandle
0x18000d601  mov     rcx, rbx
0x18000d604  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d60a  add     rsp, 20h
0x18000d60e  pop     rbx
0x18000d60f  retn
```
