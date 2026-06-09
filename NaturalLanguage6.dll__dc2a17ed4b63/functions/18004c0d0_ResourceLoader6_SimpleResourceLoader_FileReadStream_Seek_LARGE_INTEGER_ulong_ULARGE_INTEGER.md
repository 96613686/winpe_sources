# ResourceLoader6::SimpleResourceLoader::FileReadStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x18004c0d0`
- end: `0x18004c103`
- name: `?Seek@FileReadStream@SimpleResourceLoader@ResourceLoader6@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `51`
- prototype: `int(ResourceLoader6::SimpleResourceLoader::FileReadStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18004c0d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004c0ed`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004c0ed`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::FileReadStream::Seek(
        HANDLE *this,
        LARGE_INTEGER a2,
        DWORD a3,
        LARGE_INTEGER *a4)
{
  if ( a4 )
    return !SetFilePointerEx(this[6], a2, a4, a3) ? 0x80004005 : 0;
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18004c0d0  sub     rsp, 28h
0x18004c0d4  mov     rax, r9
0x18004c0d7  test    r9, r9
0x18004c0da  jnz     short loc_18004C0E3
0x18004c0dc  mov     eax, 80070057h
0x18004c0e1  jmp     short loc_18004C0FE
0x18004c0e3  mov     rcx, [rcx+30h]; hFile
0x18004c0e7  mov     r9d, r8d; dwMoveMethod
0x18004c0ea  mov     r8, rax; lpNewFilePointer
0x18004c0ed  call    cs:__imp_SetFilePointerEx
0x18004c0f3  neg     eax
0x18004c0f5  sbb     eax, eax
0x18004c0f7  not     eax
0x18004c0f9  and     eax, 80004005h
0x18004c0fe  add     rsp, 28h
0x18004c102  retn
```
