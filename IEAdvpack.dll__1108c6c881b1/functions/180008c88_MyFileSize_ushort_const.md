# MyFileSize(ushort const *)

- ea: `0x180008c88`
- end: `0x180008cea`
- name: `?MyFileSize@@YAKPEBG@Z`
- size: `98`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800078d8`
- `0x18000e060`
- `0x18000f32c`
- `0x18000f480`

## callees

- `0x180008c88`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180008cb8`
- `KERNEL32!CreateFileW` at `0x180008cb8`
- `KERNEL32!CloseHandle` at `0x180008cd7`
- `KERNEL32!CloseHandle` at `0x180008cd7`
- `KERNEL32!GetFileSize` at `0x180008ccc`
- `KERNEL32!GetFileSize` at `0x180008ccc`

## pseudocode

```c
__int64 __fastcall MyFileSize(const unsigned __int16 *a1)
{
  __int64 result; // rax
  DWORD FileSize; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi

  result = 0;
  if ( *a1 )
  {
    FileSize = 0;
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileSize = GetFileSize(FileW, 0);
      CloseHandle(v4);
    }
    return FileSize;
  }
  return result;
}

```

## disassembly

```asm
0x180008c88  mov     [rsp+arg_0], rbx
0x180008c8d  push    rdi
0x180008c8e  sub     rsp, 40h
0x180008c92  xor     eax, eax
0x180008c94  cmp     [rcx], ax
0x180008c97  jz      short loc_180008CDF
0x180008c99  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x180008c9e  lea     r8d, [rax+1]; dwShareMode
0x180008ca2  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180008ca6  xor     r9d, r9d; lpSecurityAttributes
0x180008ca9  mov     edx, 80000000h; dwDesiredAccess
0x180008cae  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180008cb6  mov     ebx, eax
0x180008cb8  call    cs:__imp_CreateFileW
0x180008cbe  mov     rdi, rax
0x180008cc1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008cc5  jz      short loc_180008CDD
0x180008cc7  xor     edx, edx; lpFileSizeHigh
0x180008cc9  mov     rcx, rax; hFile
0x180008ccc  call    cs:__imp_GetFileSize
0x180008cd2  mov     rcx, rdi; hObject
0x180008cd5  mov     ebx, eax
0x180008cd7  call    cs:__imp_CloseHandle
0x180008cdd  mov     eax, ebx
0x180008cdf  mov     rbx, [rsp+48h+arg_0]
0x180008ce4  add     rsp, 40h
0x180008ce8  pop     rdi
0x180008ce9  retn
```
