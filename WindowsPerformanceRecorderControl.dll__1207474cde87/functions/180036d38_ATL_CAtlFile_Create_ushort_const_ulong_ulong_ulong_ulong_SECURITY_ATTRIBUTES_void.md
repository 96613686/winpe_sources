# ATL::CAtlFile::Create(ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x180036d38`
- end: `0x180036d8d`
- name: `?Create@CAtlFile@ATL@@QEAAJPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `85`
- prototype: `int(ATL::CAtlFile *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007f144`

## callees

- `0x180036d38`
- `0x18004b39c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036d6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036d6c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Create(ATL::CAtlFile *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return ATL::AtlHresultFromLastError();
  *(_QWORD *)this = FileW;
  return 0;
}

```

## disassembly

```asm
0x180036d38  push    rbx
0x180036d3a  sub     rsp, 40h
0x180036d3e  mov     rax, rdx
0x180036d41  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180036d4a  xor     r9d, r9d; lpSecurityAttributes
0x180036d4d  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180036d55  mov     rbx, rcx
0x180036d58  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180036d60  mov     edx, 80000000h; dwDesiredAccess
0x180036d65  mov     rcx, rax; lpFileName
0x180036d68  lea     r8d, [r9+1]; dwShareMode
0x180036d6c  call    cs:__imp_CreateFileW
0x180036d72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036d76  jnz     short loc_180036D82
0x180036d78  add     rsp, 40h
0x180036d7c  pop     rbx
0x180036d7d  jmp     ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180036d82  mov     [rbx], rax
0x180036d85  xor     eax, eax
0x180036d87  add     rsp, 40h
0x180036d8b  pop     rbx
0x180036d8c  retn
```
