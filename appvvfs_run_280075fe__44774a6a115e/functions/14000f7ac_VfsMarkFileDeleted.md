# VfsMarkFileDeleted

- ea: `0x14000f7ac`
- end: `0x14000f89d`
- name: `VfsMarkFileDeleted`
- size: `241`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, char)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140005b48`
- `0x140005dc8`
- `0x14000a8d0`
- `0x14000c8c4`
- `0x14000eb14`

## callees

- `0x14000f7ac`
- `0x14000f8a4`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000f86d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f86d`
- `FLTMGR!FltClose` at `0x14000f87e`
- `FLTMGR!FltClose` at `0x14000f87e`

## string_xrefs

- `0x14000f824`: `VfsMarkFileDeleted() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x14000f859`: `VfsMarkFileDeleted() - Failed to mark tombstone file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsMarkFileDeleted(PFLT_INSTANCE Instance, __int64 a2, struct _UNICODE_STRING *a3, char a4)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-38h]
  HANDLE FileHandle; // [rsp+40h] [rbp-18h] BYREF
  PVOID Object; // [rsp+68h] [rbp+10h] BYREF

  FileHandle = 0;
  Object = 0;
  v6 = VfsOpenFile(Instance, 0, a3, 0x100010u, a4 != 0 ? 3 : 0, (a4 != 0) + 16416, &FileHandle, (PFILE_OBJECT *)&Object);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = VfsMarkTombstone(Instance, (PFILE_OBJECT)Object);
    v7 = v8;
    if ( v8 < 0 )
    {
      LODWORD(v10) = v8;
      LogWrite(1, 0, L"VfsMarkFileDeleted() - Failed to mark tombstone file: %wZ\n Status: 0x%08X", a3, v10);
    }
    ObfDereferenceObject(Object);
    FltClose(FileHandle);
  }
  else
  {
    LODWORD(v10) = v6;
    LogWrite(1, 0, L"VfsMarkFileDeleted() - Failed to open file: %wZ\n Status: 0x%08X", a3, v10);
  }
  return v7;
}

```

## disassembly

```asm
0x14000f7ac  mov     r11, rsp
0x14000f7af  mov     [r11+8], rbx
0x14000f7b3  mov     [r11+18h], rsi
0x14000f7b7  mov     [r11+10h], rdx
0x14000f7bb  push    rdi
0x14000f7bc  sub     rsp, 50h
0x14000f7c0  mov     al, r9b
0x14000f7c3  mov     qword ptr [r11-18h], 0
0x14000f7cb  neg     al
0x14000f7cd  mov     qword ptr [r11+10h], 0
0x14000f7d5  mov     rsi, rcx
0x14000f7d8  mov     rdi, r8
0x14000f7db  sbb     edx, edx
0x14000f7dd  lea     rcx, [r11+10h]
0x14000f7e1  mov     [r11-20h], rcx
0x14000f7e5  neg     edx
0x14000f7e7  add     edx, 4020h
0x14000f7ed  lea     rcx, [r11-18h]
0x14000f7f1  mov     [r11-28h], rcx
0x14000f7f5  neg     r9b
0x14000f7f8  mov     [rsp+58h+var_30], edx; ULONG
0x14000f7fc  mov     r9d, 100010h
0x14000f802  sbb     eax, eax
0x14000f804  mov     rcx, rsi; Instance
0x14000f807  and     eax, 3
0x14000f80a  xor     edx, edx
0x14000f80c  mov     dword ptr [rsp+58h+var_38], eax; ULONG
0x14000f810  call    VfsOpenFile
0x14000f815  mov     ebx, eax
0x14000f817  test    eax, eax
0x14000f819  jns     short loc_14000F835
0x14000f81b  xor     edx, edx
0x14000f81d  mov     dword ptr [rsp+58h+var_38], eax
0x14000f821  mov     r9, rdi
0x14000f824  lea     r8, aVfsmarkfiledel; "VfsMarkFileDeleted() - Failed to open f"...
0x14000f82b  lea     ecx, [rdx+1]
0x14000f82e  call    LogWrite
0x14000f833  jmp     short loc_14000F88A
0x14000f835  mov     r8b, [rsp+58h+arg_20]
0x14000f83d  mov     rcx, rsi; Instance
0x14000f840  mov     rdx, [rsp+58h+Object]; FileObject
0x14000f845  call    VfsMarkTombstone
0x14000f84a  mov     ebx, eax
0x14000f84c  test    eax, eax
0x14000f84e  jns     short loc_14000F868
0x14000f850  xor     edx, edx
0x14000f852  mov     dword ptr [rsp+58h+var_38], eax
0x14000f856  mov     r9, rdi
0x14000f859  lea     r8, aVfsmarkfiledel_0; "VfsMarkFileDeleted() - Failed to mark t"...
0x14000f860  lea     ecx, [rdx+1]
0x14000f863  call    LogWrite
0x14000f868  mov     rcx, [rsp+58h+Object]; Object
0x14000f86d  call    cs:__imp_ObfDereferenceObject
0x14000f874  nop     dword ptr [rax+rax+00h]
0x14000f879  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x14000f87e  call    cs:__imp_FltClose
0x14000f885  nop     dword ptr [rax+rax+00h]
0x14000f88a  mov     rsi, [rsp+58h+arg_10]
0x14000f88f  mov     eax, ebx
0x14000f891  mov     rbx, [rsp+58h+arg_0]
0x14000f896  add     rsp, 50h
0x14000f89a  pop     rdi
0x14000f89b  retn
```
