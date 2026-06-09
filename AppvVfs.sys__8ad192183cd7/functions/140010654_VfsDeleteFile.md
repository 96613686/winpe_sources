# VfsDeleteFile

- ea: `0x140010654`
- end: `0x140010704`
- name: `VfsDeleteFile`
- size: `176`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000eb14`

## callees

- `0x140010654`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400106d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400106d9`
- `FLTMGR!FltClose` at `0x1400106ea`
- `FLTMGR!FltClose` at `0x1400106ea`

## string_xrefs

- `0x1400106c1`: `VfsDeleteFile() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsDeleteFile(struct _FLT_INSTANCE *a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-28h]
  PVOID Object; // [rsp+58h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp+20h] BYREF

  FileHandle = 0;
  Object = 0;
  v4 = VfsOpenFile(a1, 1u, 0x5020u, &FileHandle, (PFILE_OBJECT *)&Object);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ObfDereferenceObject(Object);
    FltClose(FileHandle);
  }
  else if ( v4 != -1073741772 && v4 != -1073741766 )
  {
    LODWORD(v7) = v4;
    LogWrite(1, 0, L"VfsDeleteFile() - Failed to open file: %wZ\n Status: 0x%08X", a3, v7);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x140010654  mov     r11, rsp
0x140010657  mov     [r11+8], rbx
0x14001065b  mov     [r11+10h], rdx
0x14001065f  push    rdi
0x140010660  sub     rsp, 40h
0x140010664  lea     rax, [r11+10h]
0x140010668  mov     qword ptr [r11+20h], 0
0x140010670  mov     [r11-10h], rax
0x140010674  xor     edx, edx
0x140010676  lea     rax, [r11+20h]
0x14001067a  mov     qword ptr [r11+10h], 0
0x140010682  mov     [r11-18h], rax
0x140010686  mov     r9d, 110000h
0x14001068c  mov     [rsp+48h+var_20], 5020h; ULONG
0x140010694  mov     rdi, r8
0x140010697  mov     dword ptr [rsp+48h+var_28], 1; ULONG
0x14001069f  call    VfsOpenFile
0x1400106a4  mov     ebx, eax
0x1400106a6  test    eax, eax
0x1400106a8  jns     short loc_1400106D4
0x1400106aa  cmp     eax, 0C0000034h
0x1400106af  jz      short loc_1400106F6
0x1400106b1  cmp     eax, 0C000003Ah
0x1400106b6  jz      short loc_1400106F6
0x1400106b8  xor     edx, edx
0x1400106ba  mov     dword ptr [rsp+48h+var_28], eax
0x1400106be  mov     r9, rdi
0x1400106c1  lea     r8, aVfsdeletefileF; "VfsDeleteFile() - Failed to open file: "...
0x1400106c8  lea     ecx, [rdx+1]
0x1400106cb  call    LogWrite
0x1400106d0  mov     eax, ebx
0x1400106d2  jmp     short loc_1400106F8
0x1400106d4  mov     rcx, [rsp+48h+Object]; Object
0x1400106d9  call    cs:__imp_ObfDereferenceObject
0x1400106e0  nop     dword ptr [rax+rax+00h]
0x1400106e5  mov     rcx, [rsp+48h+FileHandle]; FileHandle
0x1400106ea  call    cs:__imp_FltClose
0x1400106f1  nop     dword ptr [rax+rax+00h]
0x1400106f6  xor     eax, eax
0x1400106f8  mov     rbx, [rsp+48h+arg_0]
0x1400106fd  add     rsp, 40h
0x140010701  pop     rdi
0x140010702  retn
```
