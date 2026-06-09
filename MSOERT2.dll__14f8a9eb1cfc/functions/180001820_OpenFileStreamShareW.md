# OpenFileStreamShareW

- ea: `0x180001820`
- end: `0x1800018c8`
- name: `OpenFileStreamShareW`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001820`
- `0x180001c80`
- `0x180001f7c`
- `0x18000e424`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800018b5`
- `KERNEL32!CloseHandle` at `0x1800018b5`
- `KERNEL32!CreateFileW` at `0x180001864`
- `KERNEL32!CreateFileW` at `0x180001864`

## pseudocode

```c
__int64 __fastcall OpenFileStreamShareW(
        const WCHAR *a1,
        DWORD dwCreationDisposition,
        DWORD a3,
        DWORD a4,
        CFileStream **a5)
{
  HANDLE FileW; // rdi
  unsigned int v7; // ebx
  CFileStream *v8; // rax
  CFileStream *v9; // rax

  if ( !a5 )
    return 2147942487LL;
  FileW = CreateFileW(a1, a3, a4, 0, dwCreationDisposition, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)HrGetLastError();
  }
  else
  {
    v8 = (CFileStream *)operator new(0x18u);
    if ( v8 && (v9 = CFileStream::CFileStream(v8, FileW)) != 0 )
    {
      *a5 = v9;
      return 0;
    }
    else
    {
      v7 = -2147024882;
      CloseHandle(FileW);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180001820  push    rbx
0x180001822  sub     rsp, 40h
0x180001826  mov     rbx, [rsp+48h+arg_20]
0x18000182b  mov     eax, r9d
0x18000182e  mov     r10d, r8d
0x180001831  test    rbx, rbx
0x180001834  jnz     short loc_180001841
0x180001836  mov     eax, 80070057h
0x18000183b  add     rsp, 40h
0x18000183f  pop     rbx
0x180001840  retn
0x180001841  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000184a  xor     r9d, r9d; lpSecurityAttributes
0x18000184d  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001855  mov     r8d, eax; dwShareMode
0x180001858  mov     [rsp+48h+dwCreationDisposition], edx; dwCreationDisposition
0x18000185c  mov     edx, r10d; dwDesiredAccess
0x18000185f  mov     [rsp+48h+arg_0], rdi
0x180001864  call    cs:__imp_CreateFileW
0x18000186a  mov     rdi, rax
0x18000186d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001871  jnz     short loc_18000187C
0x180001873  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180001878  mov     ebx, eax
0x18000187a  jmp     short loc_1800018BB
0x18000187c  mov     ecx, 18h; Size
0x180001881  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001886  test    rax, rax
0x180001889  jz      short loc_1800018AD
0x18000188b  mov     rdx, rdi; void *
0x18000188e  mov     rcx, rax; this
0x180001891  call    ??0CFileStream@@AEAA@PEAX@Z; CFileStream::CFileStream(void *)
0x180001896  test    rax, rax
0x180001899  jz      short loc_1800018AD
0x18000189b  mov     [rbx], rax
0x18000189e  mov     ecx, 8007000Eh
0x1800018a3  xor     ebx, ebx
0x1800018a5  test    rax, rax
0x1800018a8  cmovz   ebx, ecx
0x1800018ab  jmp     short loc_1800018BB
0x1800018ad  mov     rcx, rdi; hObject
0x1800018b0  mov     ebx, 8007000Eh
0x1800018b5  call    cs:__imp_CloseHandle
0x1800018bb  mov     rdi, [rsp+48h+arg_0]
0x1800018c0  mov     eax, ebx
0x1800018c2  add     rsp, 40h
0x1800018c6  pop     rbx
0x1800018c7  retn
```
