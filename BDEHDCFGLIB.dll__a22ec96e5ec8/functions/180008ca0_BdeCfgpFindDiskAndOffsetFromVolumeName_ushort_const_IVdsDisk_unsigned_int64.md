# BdeCfgpFindDiskAndOffsetFromVolumeName(ushort const *,IVdsDisk * *,unsigned __int64 *)

- ea: `0x180008ca0`
- end: `0x180008e15`
- name: `?BdeCfgpFindDiskAndOffsetFromVolumeName@@YAJPEBGPEAPEAUIVdsDisk@@PEA_K@Z`
- size: `373`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IVdsDisk **, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800049d0`
- `0x180006738`
- `0x180007bd0`

## callees

- `0x180005884`
- `0x180006c30`
- `0x180008ca0`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008d18`
- `KERNEL32!GetLastError` at `0x180008d73`
- `KERNEL32!GetLastError` at `0x180008d80`
- `KERNEL32!GetLastError` at `0x180008d8b`
- `KERNEL32!GetLastError` at `0x180008d18`
- `KERNEL32!GetLastError` at `0x180008d73`
- `KERNEL32!GetLastError` at `0x180008d80`
- `KERNEL32!GetLastError` at `0x180008d8b`
- `KERNEL32!CreateFileW` at `0x180008d09`
- `KERNEL32!CreateFileW` at `0x180008d09`
- `KERNEL32!DeviceIoControl` at `0x180008d69`
- `KERNEL32!DeviceIoControl` at `0x180008d69`
- `KERNEL32!CloseHandle` at `0x180008daa`
- `KERNEL32!CloseHandle` at `0x180008db5`
- `KERNEL32!CloseHandle` at `0x180008daa`
- `KERNEL32!CloseHandle` at `0x180008db5`

## pseudocode

```c
__int64 __fastcall BdeCfgpFindDiskAndOffsetFromVolumeName(
        const unsigned __int16 *a1,
        struct IVdsDisk **a2,
        unsigned __int64 *a3)
{
  signed int v5; // ebx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v8; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-268h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-260h] BYREF
  __int128 v12; // [rsp+58h] [rbp-250h]
  wchar_t String2[264]; // [rsp+70h] [rbp-238h] BYREF

  BytesReturned = 0;
  OutBuffer = 0;
  v12 = 0;
  if ( a1 )
  {
    FileW = CreateFileW(a1, 0, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else if ( DeviceIoControl(FileW, 0x560000u, 0, 0, &OutBuffer, 0x20u, &BytesReturned, 0) )
    {
      CloseHandle(FileW);
      if ( a3 )
        *a3 = v12;
      v5 = StringCchPrintfW(String2, 0x104u, L"\\\\?\\PhysicalDrive%u", DWORD2(OutBuffer));
      if ( v5 >= 0 )
        return (unsigned int)BdeCfgpFindDiskWithName(String2, a2);
    }
    else
    {
      if ( GetLastError() == 234 || GetLastError() == 122 )
      {
        v5 = -1063256055;
      }
      else
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008ca0  push    rbx
0x180008ca2  push    rsi
0x180008ca3  push    rdi
0x180008ca4  sub     rsp, 290h
0x180008cab  mov     rax, cs:__security_cookie
0x180008cb2  xor     rax, rsp
0x180008cb5  mov     [rsp+2A8h+var_28], rax
0x180008cbd  mov     [rsp+2A8h+BytesReturned], 0
0x180008cc5  xorps   xmm0, xmm0
0x180008cc8  mov     rbx, r8
0x180008ccb  mov     rsi, rdx
0x180008cce  movups  [rsp+2A8h+OutBuffer], xmm0
0x180008cd3  movups  [rsp+2A8h+var_250], xmm0
0x180008cd8  test    rcx, rcx
0x180008cdb  jnz     short loc_180008CE7
0x180008cdd  mov     ebx, 80004003h
0x180008ce2  jmp     loc_180008DF8
0x180008ce7  xor     r9d, r9d; lpSecurityAttributes
0x180008cea  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x180008cf3  mov     [rsp+2A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008cfb  xor     edx, edx; dwDesiredAccess
0x180008cfd  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180008d05  lea     r8d, [r9+1]; dwShareMode
0x180008d09  call    cs:__imp_CreateFileW
0x180008d0f  mov     rdi, rax
0x180008d12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d16  jnz     short loc_180008D36
0x180008d18  call    cs:__imp_GetLastError
0x180008d1e  mov     ebx, eax
0x180008d20  test    eax, eax
0x180008d22  jle     loc_180008DF8
0x180008d28  movzx   ebx, ax
0x180008d2b  or      ebx, 80070000h
0x180008d31  jmp     loc_180008DF8
0x180008d36  mov     [rsp+2A8h+lpOverlapped], 0; lpOverlapped
0x180008d3f  lea     rax, [rsp+2A8h+BytesReturned]
0x180008d44  mov     [rsp+2A8h+hTemplateFile], rax; lpBytesReturned
0x180008d49  xor     r9d, r9d; nInBufferSize
0x180008d4c  lea     rax, [rsp+2A8h+OutBuffer]
0x180008d51  mov     [rsp+2A8h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180008d59  xor     r8d, r8d; lpInBuffer
0x180008d5c  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rax; lpOutBuffer
0x180008d61  mov     edx, 560000h; dwIoControlCode
0x180008d66  mov     rcx, rdi; hDevice
0x180008d69  call    cs:__imp_DeviceIoControl
0x180008d6f  test    eax, eax
0x180008d71  jnz     short loc_180008DB2
0x180008d73  call    cs:__imp_GetLastError
0x180008d79  cmp     eax, 0EAh
0x180008d7e  jz      short loc_180008DA2
0x180008d80  call    cs:__imp_GetLastError
0x180008d86  cmp     eax, 7Ah ; 'z'
0x180008d89  jz      short loc_180008DA2
0x180008d8b  call    cs:__imp_GetLastError
0x180008d91  mov     ebx, eax
0x180008d93  test    eax, eax
0x180008d95  jle     short loc_180008DA7
0x180008d97  movzx   ebx, ax
0x180008d9a  or      ebx, 80070000h
0x180008da0  jmp     short loc_180008DA7
0x180008da2  mov     ebx, 0C0A00009h
0x180008da7  mov     rcx, rdi; hObject
0x180008daa  call    cs:__imp_CloseHandle
0x180008db0  jmp     short loc_180008DF8
0x180008db2  mov     rcx, rdi; hObject
0x180008db5  call    cs:__imp_CloseHandle
0x180008dbb  test    rbx, rbx
0x180008dbe  jz      short loc_180008DC8
0x180008dc0  mov     rax, qword ptr [rsp+2A8h+var_250]
0x180008dc5  mov     [rbx], rax
0x180008dc8  mov     r9d, dword ptr [rsp+2A8h+OutBuffer+8]
0x180008dcd  lea     r8, aPhysicaldriveU; "\\\\?\\PhysicalDrive%u"
0x180008dd4  mov     edx, 104h; unsigned __int64
0x180008dd9  lea     rcx, [rsp+2A8h+String2]; unsigned __int16 *
0x180008dde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008de3  mov     ebx, eax
0x180008de5  test    eax, eax
0x180008de7  js      short loc_180008DF8
0x180008de9  mov     rdx, rsi; struct IVdsDisk **
0x180008dec  lea     rcx, [rsp+2A8h+String2]; String2
0x180008df1  call    ?BdeCfgpFindDiskWithName@@YAJPEBGPEAPEAUIVdsDisk@@@Z; BdeCfgpFindDiskWithName(ushort const *,IVdsDisk * *)
0x180008df6  mov     ebx, eax
0x180008df8  mov     eax, ebx
0x180008dfa  mov     rcx, [rsp+2A8h+var_28]
0x180008e02  xor     rcx, rsp; StackCookie
0x180008e05  call    __security_check_cookie
0x180008e0a  add     rsp, 290h
0x180008e11  pop     rdi
0x180008e12  pop     rsi
0x180008e13  pop     rbx
0x180008e14  retn
```
