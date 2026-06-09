# GetHandleForPhysicalDrive(ulong)

- ea: `0x140046ce0`
- end: `0x140046d6e`
- name: `?GetHandleForPhysicalDrive@@YAPEAXK@Z`
- size: `142`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140026110`
- `0x140046f94`

## callees

- `0x140005f4c`
- `0x140016d04`
- `0x140019a1c`
- `0x140046ce0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140046d4b`
- `KERNEL32!CreateFileW` at `0x140046d4b`
- `KERNEL32!SetLastError` at `0x140046cf2`
- `KERNEL32!SetLastError` at `0x140046cf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetHandleForPhysicalDrive(unsigned int a1)
{
  HANDLE FileW; // rbx
  __int64 result; // rax
  __int64 v4; // [rsp+58h] [rbp+10h] BYREF

  if ( a1 < 0x20 )
  {
    try
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v4,
        64);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
        &v4,
        L"\\\\.\\PhysicalDrive%d",
        a1);
      FileW = CreateFileW(*(LPCWSTR *)(v4 + 24), 0x80000000, 3u, 0, 3u, 0, 0);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v4);
      result = (__int64)FileW;
    }
    catch ( std::bad_alloc )
    {
      SetLastError(8u);
      return -1;
    }
  }
  else
  {
    SetLastError(6u);
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x140046ce0  push    rbx
0x140046ce2  sub     rsp, 40h
0x140046ce6  mov     ebx, ecx
0x140046ce8  cmp     ecx, 20h ; ' '
0x140046ceb  jb      short loc_140046CFA
0x140046ced  mov     ecx, 6; dwErrCode
0x140046cf2  call    cs:__imp_SetLastError
0x140046cf8  jmp     short loc_140046D63
0x140046cfa  mov     edx, 40h ; '@'
0x140046cff  lea     rcx, [rsp+48h+arg_8]
0x140046d04  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140046d09  nop
0x140046d0a  mov     r8d, ebx
0x140046d0d  lea     rdx, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x140046d14  lea     rcx, [rsp+48h+arg_8]
0x140046d19  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140046d1e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140046d27  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140046d2f  mov     r8d, 3; dwShareMode
0x140046d35  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x140046d3a  xor     r9d, r9d; lpSecurityAttributes
0x140046d3d  mov     edx, 80000000h; dwDesiredAccess
0x140046d42  mov     rcx, [rsp+48h+arg_8]
0x140046d47  mov     rcx, [rcx+18h]; lpFileName
0x140046d4b  call    cs:__imp_CreateFileW
0x140046d51  mov     rbx, rax
0x140046d54  lea     rcx, [rsp+48h+arg_8]
0x140046d59  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140046d5e  mov     rax, rbx
0x140046d61  jmp     short loc_140046D67
0x140046d63  or      rax, 0FFFFFFFFFFFFFFFFh
0x140046d67  add     rsp, 40h
0x140046d6b  pop     rbx
0x140046d6c  retn
```
