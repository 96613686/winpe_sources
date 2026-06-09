# SdbCreateDatabase

- ea: `0x18003f760`
- end: `0x18003f867`
- name: `SdbCreateDatabase`
- size: `263`
- prototype: `_QWORD *__fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18004525c`

## callees

- `0x18000f114`
- `0x180015a6c`
- `0x180015e8c`
- `0x180018f20`
- `0x18003f760`
- `0x180040584`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f7cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f7cb`

## string_xrefs

- `0x18003f813`: `Failed to create file mapping [%x]`
- `0x18003f77a`: `Failed to allocate and create pdb in memory.`
- `0x18003f787`: `SdbCreateDatabase`
- `0x18003f7e4`: `SdbCreateDatabase`
- `0x18003f824`: `SdbCreateDatabase`
- `0x18003f7d7`: `Failed to create file`

## pseudocode

```c
_QWORD *__fastcall SdbCreateDatabase(LPCWSTR lpFileName)
{
  _QWORD *DatabaseInMemory; // rbx
  HANDLE FileW; // rax
  int v4; // eax

  DatabaseInMemory = (_QWORD *)SdbpCreateDatabaseInMemory();
  if ( DatabaseInMemory )
  {
    if ( lpFileName )
    {
      FileW = CreateFileW(lpFileName, 0xC0100080, 0, 0, 2u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        AslLogCallPrintf(1, "SdbCreateDatabase", 2368, "Failed to create file");
      }
      else
      {
        v4 = AslFileMappingCreate(DatabaseInMemory, lpFileName, FileW, 0, 0);
        if ( v4 >= 0 )
          return DatabaseInMemory;
        AslLogCallPrintf(1, "SdbCreateDatabase", 2378, "Failed to create file mapping [%x]", v4);
      }
      if ( *DatabaseInMemory )
        AslFileMappingDelete(*DatabaseInMemory);
      AslFree(NtCurrentPeb()->ProcessHeap, DatabaseInMemory);
      return 0;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbCreateDatabase", 2350, "Failed to allocate and create pdb in memory.");
  }
  return DatabaseInMemory;
}

```

## disassembly

```asm
0x18003f760  mov     [rsp+arg_0], rbx
0x18003f765  push    rdi
0x18003f766  sub     rsp, 40h
0x18003f76a  mov     rdi, rcx
0x18003f76d  call    SdbpCreateDatabaseInMemory
0x18003f772  mov     rbx, rax
0x18003f775  test    rax, rax
0x18003f778  jnz     short loc_18003F79B
0x18003f77a  lea     r9, aFailedToAlloca_11; "Failed to allocate and create pdb in me"...
0x18003f781  mov     r8d, 92Eh
0x18003f787  lea     rdx, aSdbcreatedatab_0; "SdbCreateDatabase"
0x18003f78e  lea     ecx, [rax+1]
0x18003f791  call    AslLogCallPrintf
0x18003f796  jmp     loc_18003F859
0x18003f79b  test    rdi, rdi
0x18003f79e  jz      loc_18003F859
0x18003f7a4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18003f7ad  xor     r9d, r9d; lpSecurityAttributes
0x18003f7b0  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f7b8  xor     r8d, r8d; dwShareMode
0x18003f7bb  mov     edx, 0C0100080h; dwDesiredAccess
0x18003f7c0  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18003f7c8  mov     rcx, rdi; lpFileName
0x18003f7cb  call    cs:__imp_CreateFileW
0x18003f7d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f7d5  jnz     short loc_18003F7F5
0x18003f7d7  lea     r9, aFailedToCreate_12; "Failed to create file"
0x18003f7de  mov     r8d, 940h
0x18003f7e4  lea     rdx, aSdbcreatedatab_0; "SdbCreateDatabase"
0x18003f7eb  lea     ecx, [rax+2]
0x18003f7ee  call    AslLogCallPrintf
0x18003f7f3  jmp     short loc_18003F835
0x18003f7f5  xor     r9d, r9d
0x18003f7f8  mov     qword ptr [rsp+48h+dwCreationDisposition], 0
0x18003f801  mov     r8, rax
0x18003f804  mov     rdx, rdi
0x18003f807  mov     rcx, rbx
0x18003f80a  call    AslFileMappingCreate
0x18003f80f  test    eax, eax
0x18003f811  jns     short loc_18003F859
0x18003f813  lea     r9, aFailedToCreate_1; "Failed to create file mapping [%x]"
0x18003f81a  mov     [rsp+48h+dwCreationDisposition], eax
0x18003f81e  mov     r8d, 94Ah
0x18003f824  lea     rdx, aSdbcreatedatab_0; "SdbCreateDatabase"
0x18003f82b  mov     ecx, 1
0x18003f830  call    AslLogCallPrintf
0x18003f835  mov     rcx, [rbx]
0x18003f838  test    rcx, rcx
0x18003f83b  jz      short loc_18003F842
0x18003f83d  call    AslFileMappingDelete
0x18003f842  mov     rcx, gs:60h
0x18003f84b  mov     rdx, rbx
0x18003f84e  mov     rcx, [rcx+30h]
0x18003f852  call    AslFree
0x18003f857  xor     ebx, ebx
0x18003f859  mov     rax, rbx
0x18003f85c  mov     rbx, [rsp+48h+arg_0]
0x18003f861  add     rsp, 40h
0x18003f865  pop     rdi
0x18003f866  retn
```
