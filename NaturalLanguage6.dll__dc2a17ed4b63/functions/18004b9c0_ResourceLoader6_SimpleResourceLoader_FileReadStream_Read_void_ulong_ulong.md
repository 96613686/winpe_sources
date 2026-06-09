# ResourceLoader6::SimpleResourceLoader::FileReadStream::Read(void *,ulong,ulong *)

- ea: `0x18004b9c0`
- end: `0x18004b9f8`
- name: `?Read@FileReadStream@SimpleResourceLoader@ResourceLoader6@@UEAAJPEAXKPEAK@Z`
- size: `56`
- prototype: `__int64 __fastcall(ResourceLoader6::SimpleResourceLoader::FileReadStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18004b9c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004b9db`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004b9db`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::FileReadStream::Read(
        HANDLE *this,
        void *a2,
        DWORD a3,
        unsigned int *a4)
{
  if ( a2 && a4 )
    return !ReadFile(this[6], a2, a3, a4, 0) ? 0x80004005 : 0;
  else
    return 2147680265LL;
}

```

## disassembly

```asm
0x18004b9c0  sub     rsp, 38h
0x18004b9c4  test    rdx, rdx
0x18004b9c7  jz      short loc_18004B9EE
0x18004b9c9  test    r9, r9
0x18004b9cc  jz      short loc_18004B9EE
0x18004b9ce  mov     rcx, [rcx+30h]; hFile
0x18004b9d2  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18004b9db  call    cs:__imp_ReadFile
0x18004b9e1  neg     eax
0x18004b9e3  sbb     eax, eax
0x18004b9e5  not     eax
0x18004b9e7  and     eax, 80004005h
0x18004b9ec  jmp     short loc_18004B9F3
0x18004b9ee  mov     eax, 80030009h
0x18004b9f3  add     rsp, 38h
0x18004b9f7  retn
```
