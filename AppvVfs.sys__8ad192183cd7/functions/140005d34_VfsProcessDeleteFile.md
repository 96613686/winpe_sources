# VfsProcessDeleteFile

- ea: `0x140005d34`
- end: `0x140005dc0`
- name: `VfsProcessDeleteFile`
- size: `140`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140005c50`

## callees

- `0x140005d34`
- `0x14000aefc`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x140005d9f`
- `FLTMGR!FltSetInformationFile` at `0x140005d9f`

## string_xrefs

- `0x140005d67`: `VfsProcessDeleteFile() - Failed to delay copy file. Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsProcessDeleteFile(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // si
  int v5; // eax
  unsigned int v6; // ebx
  struct _FILE_OBJECT *v7; // rdx
  struct _FLT_INSTANCE *v8; // rcx
  char FileInformation; // [rsp+40h] [rbp+8h] BYREF

  v4 = **(_BYTE **)(*(_QWORD *)(a1 + 16) + 56LL);
  if ( (*(_DWORD *)(a3 + 4) & 4) != 0 && (v5 = VfsDelayedCopy(), v6 = v5, v5 < 0) )
  {
    LogWrite(1, 0, L"VfsProcessDeleteFile() - Failed to delay copy file. Status: 0x%08X", (unsigned int)v5);
  }
  else
  {
    v7 = *(struct _FILE_OBJECT **)(a3 + 72);
    v8 = *(struct _FLT_INSTANCE **)(a3 + 64);
    FileInformation = v4;
    return (unsigned int)FltSetInformationFile(v8, v7, &FileInformation, 1u, FileDispositionInformation);
  }
  return v6;
}

```

## disassembly

```asm
0x140005d34  mov     [rsp+arg_8], rbx
0x140005d39  mov     [rsp+arg_10], rsi
0x140005d3e  push    rdi
0x140005d3f  sub     rsp, 30h
0x140005d43  mov     rdi, r8
0x140005d46  mov     rax, [rcx+10h]
0x140005d4a  mov     r9, [rax+38h]
0x140005d4e  mov     sil, [r9]
0x140005d51  mov     eax, [r8+4]
0x140005d55  test    al, 4
0x140005d57  jz      short loc_140005D7A
0x140005d59  call    VfsDelayedCopy
0x140005d5e  mov     ebx, eax
0x140005d60  test    eax, eax
0x140005d62  jns     short loc_140005D7A
0x140005d64  mov     r9d, eax
0x140005d67  lea     r8, aVfsprocessdele_1; "VfsProcessDeleteFile() - Failed to dela"...
0x140005d6e  xor     edx, edx
0x140005d70  lea     ecx, [rdx+1]
0x140005d73  call    LogWrite
0x140005d78  jmp     short loc_140005DAD
0x140005d7a  mov     rdx, [rdi+48h]; FileObject
0x140005d7e  mov     rcx, [rdi+40h]; Instance
0x140005d82  mov     [rsp+38h+FileInformation], 0
0x140005d87  mov     [rsp+38h+FileInformation], sil
0x140005d8c  mov     [rsp+38h+FileInformationClass], 0Dh; FileInformationClass
0x140005d94  mov     r9d, 1; Length
0x140005d9a  lea     r8, [rsp+38h+FileInformation]; FileInformation
0x140005d9f  call    cs:__imp_FltSetInformationFile
0x140005da6  nop     dword ptr [rax+rax+00h]
0x140005dab  mov     ebx, eax
0x140005dad  mov     eax, ebx
0x140005daf  mov     rbx, [rsp+38h+arg_8]
0x140005db4  mov     rsi, [rsp+38h+arg_10]
0x140005db9  add     rsp, 30h
0x140005dbd  pop     rdi
0x140005dbe  retn
0x140014a2a  push    rbp
0x140014a2c  sub     rsp, 30h
0x140014a30  mov     rbp, rdx
0x140014a33  add     rsp, 30h
0x140014a37  pop     rbp
0x140014a38  retn
```
