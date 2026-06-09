# SdbpWriteDatabase

- ea: `0x1800408c4`
- end: `0x180040984`
- name: `SdbpWriteDatabase`
- size: `192`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180038240`

## callees

- `0x18000f114`
- `0x18003cbb8`
- `0x1800408c4`
- `0x180050248`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180040949`
- `ntdll!NtWriteFile` at `0x180040949`

## string_xrefs

- `0x1800408ea`: `Failed to write compressed sdb.`
- `0x1800408f7`: `SdbpWriteDatabase`
- `0x180040964`: `SdbpWriteDatabase`
- `0x180040953`: `Failed to write the sdb [%x]`

## pseudocode

```c
__int64 __fastcall SdbpWriteDatabase(__int64 *a1)
{
  unsigned int v1; // ebx
  bool v2; // zf
  __int64 v4; // rcx
  void *FileHandle; // rax
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  v2 = (a1[3] & 4) == 0;
  IoStatusBlock = 0;
  if ( v2 )
  {
    v4 = *a1;
    ByteOffset.QuadPart = 0;
    FileHandle = (void *)AslFileMappingGetFileHandle(v4, a1);
    v7 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(v6 + 8), *(_DWORD *)(v6 + 20), &ByteOffset, 0);
    if ( v7 < 0 )
    {
      AslLogCallPrintf(1, "SdbpWriteDatabase", 1716, "Failed to write the sdb [%x]", v7);
      return v1;
    }
    return 1;
  }
  if ( (unsigned int)SdbpWriteCompressedDatabase(a1, a1) )
    return 1;
  AslLogCallPrintf(1, "SdbpWriteDatabase", 1695, "Failed to write compressed sdb.");
  return v1;
}

```

## disassembly

```asm
0x1800408c4  push    rbx
0x1800408c6  sub     rsp, 60h
0x1800408ca  xor     ebx, ebx
0x1800408cc  xorps   xmm0, xmm0
0x1800408cf  test    byte ptr [rcx+18h], 4
0x1800408d3  mov     rdx, rcx
0x1800408d6  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1800408db  jz      short loc_180040908
0x1800408dd  call    SdbpWriteCompressedDatabase
0x1800408e2  test    eax, eax
0x1800408e4  jnz     loc_180040977
0x1800408ea  lea     r9, aFailedToWriteC; "Failed to write compressed sdb."
0x1800408f1  mov     r8d, 69Fh
0x1800408f7  lea     rdx, aSdbpwritedatab; "SdbpWriteDatabase"
0x1800408fe  lea     ecx, [rbx+1]
0x180040901  call    AslLogCallPrintf
0x180040906  jmp     short loc_18004097C
0x180040908  mov     rcx, [rcx]
0x18004090b  mov     qword ptr [rsp+68h+arg_0], rbx
0x180040910  call    AslFileMappingGetFileHandle
0x180040915  mov     rcx, rax; FileHandle
0x180040918  mov     [rsp+68h+Key], rbx; Key
0x18004091d  lea     rax, [rsp+68h+arg_0]
0x180040922  xor     r9d, r9d; ApcContext
0x180040925  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x18004092a  xor     r8d, r8d; ApcRoutine
0x18004092d  mov     eax, [rdx+14h]
0x180040930  mov     [rsp+68h+Length], eax; Length
0x180040934  mov     rax, [rdx+8]
0x180040938  xor     edx, edx; Event
0x18004093a  mov     [rsp+68h+Buffer], rax; Buffer
0x18004093f  lea     rax, [rsp+68h+var_18]
0x180040944  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180040949  call    cs:__imp_NtWriteFile
0x18004094f  test    eax, eax
0x180040951  jns     short loc_180040977
0x180040953  lea     r9, aFailedToWriteT_2; "Failed to write the sdb [%x]"
0x18004095a  mov     dword ptr [rsp+68h+IoStatusBlock], eax
0x18004095e  mov     r8d, 6B4h
0x180040964  lea     rdx, aSdbpwritedatab; "SdbpWriteDatabase"
0x18004096b  mov     ecx, 1
0x180040970  call    AslLogCallPrintf
0x180040975  jmp     short loc_18004097C
0x180040977  mov     ebx, 1
0x18004097c  mov     eax, ebx
0x18004097e  add     rsp, 60h
0x180040982  pop     rbx
0x180040983  retn
```
