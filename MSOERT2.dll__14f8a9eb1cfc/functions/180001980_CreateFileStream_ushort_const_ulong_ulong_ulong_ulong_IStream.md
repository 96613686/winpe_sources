# CreateFileStream(ushort const *,ulong,ulong,ulong,ulong,IStream * *)

- ea: `0x180001980`
- end: `0x180001a1d`
- name: `?CreateFileStream@@YAJPEBGKKKKPEAPEAUIStream@@@Z`
- size: `157`
- prototype: `int(const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, struct IStream **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ebc0`
- `0x18000f5c0`
- `0x18000f6b0`

## callees

- `0x180001980`
- `0x180001c80`
- `0x180001f7c`
- `0x18000e424`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180001a0a`
- `KERNEL32!CloseHandle` at `0x180001a0a`
- `KERNEL32!CreateFileW` at `0x1800019b9`
- `KERNEL32!CreateFileW` at `0x1800019b9`

## pseudocode

```c
__int64 __fastcall CreateFileStream(
        const unsigned __int16 *a1,
        DWORD a2,
        DWORD a3,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        struct IStream **a6)
{
  HANDLE FileW; // rdi
  unsigned int v8; // ebx
  CFileStream *v9; // rax
  struct IStream *v10; // rax

  if ( !a6 )
    return 2147942487LL;
  FileW = CreateFileW(a1, a2, a3, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)HrGetLastError();
  }
  else
  {
    v9 = (CFileStream *)operator new(0x18u);
    if ( v9 && (v10 = (struct IStream *)CFileStream::CFileStream(v9, FileW)) != 0 )
    {
      *a6 = v10;
      return 0;
    }
    else
    {
      v8 = -2147024882;
      CloseHandle(FileW);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180001980  push    rbx
0x180001982  sub     rsp, 40h
0x180001986  mov     rbx, [rsp+48h+arg_28]
0x18000198b  test    rbx, rbx
0x18000198e  jnz     short loc_18000199B
0x180001990  mov     eax, 80070057h
0x180001995  add     rsp, 40h
0x180001999  pop     rbx
0x18000199a  retn
0x18000199b  mov     eax, [rsp+48h+arg_20]
0x18000199f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800019a8  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800019ac  mov     [rsp+48h+dwCreationDisposition], r9d; dwCreationDisposition
0x1800019b1  xor     r9d, r9d; lpSecurityAttributes
0x1800019b4  mov     [rsp+48h+arg_0], rdi
0x1800019b9  call    cs:__imp_CreateFileW
0x1800019bf  mov     rdi, rax
0x1800019c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800019c6  jnz     short loc_1800019D1
0x1800019c8  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800019cd  mov     ebx, eax
0x1800019cf  jmp     short loc_180001A10
0x1800019d1  mov     ecx, 18h; Size
0x1800019d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019db  test    rax, rax
0x1800019de  jz      short loc_180001A02
0x1800019e0  mov     rdx, rdi; void *
0x1800019e3  mov     rcx, rax; this
0x1800019e6  call    ??0CFileStream@@AEAA@PEAX@Z; CFileStream::CFileStream(void *)
0x1800019eb  test    rax, rax
0x1800019ee  jz      short loc_180001A02
0x1800019f0  mov     [rbx], rax
0x1800019f3  mov     ecx, 8007000Eh
0x1800019f8  xor     ebx, ebx
0x1800019fa  test    rax, rax
0x1800019fd  cmovz   ebx, ecx
0x180001a00  jmp     short loc_180001A10
0x180001a02  mov     rcx, rdi; hObject
0x180001a05  mov     ebx, 8007000Eh
0x180001a0a  call    cs:__imp_CloseHandle
0x180001a10  mov     rdi, [rsp+48h+arg_0]
0x180001a15  mov     eax, ebx
0x180001a17  add     rsp, 40h
0x180001a1b  pop     rbx
0x180001a1c  retn
```
