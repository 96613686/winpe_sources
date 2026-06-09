# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x18002cc48`
- end: `0x18002cd7d`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `309`
- prototype: `int(const unsigned __int16 *, const char *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002cf30`

## callees

- `0x180005890`
- `0x18002b538`
- `0x18002cc48`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd59`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002ccd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002ccd1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd43`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cd43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cc9b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cc9b`

## pseudocode

```c
__int64 __fastcall AslLogpAppendLog(const unsigned __int16 *a1, const char *a2, DWORD a3, char a4, unsigned __int8 a5)
{
  HANDLE FileW; // rdi
  unsigned int v8; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-18h] BYREF
  int v13; // [rsp+60h] [rbp-10h]
  char v14; // [rsp+64h] [rbp-Ch]

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 4u, 1u, 0, 4u, a4 == 0 ? 0x80000000 : 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-1073741790;
  }
  else
  {
    if ( a5 )
    {
      Buffer = 0;
      v13 = 0;
      v14 = 0;
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      if ( (int)RtlStringCchPrintfA(
                  (char *)&Buffer,
                  0xDu,
                  "%02d:%02d:%02d.%03d",
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond,
                  SystemTime.wMilliseconds) >= 0 )
        WriteFile(FileW, &Buffer, 0xDu, &NumberOfBytesWritten, 0);
    }
    v8 = !WriteFile(FileW, a2, a3, &NumberOfBytesWritten, 0) ? 0xC0000022 : 0;
    CloseHandle(FileW);
  }
  return v8;
}

```

## disassembly

```asm
0x18002cc48  mov     [rsp-18h+arg_18], rbx
0x18002cc4d  push    rbp
0x18002cc4e  push    rsi
0x18002cc4f  push    rdi
0x18002cc50  mov     rbp, rsp
0x18002cc53  sub     rsp, 70h
0x18002cc57  mov     rax, cs:__security_cookie
0x18002cc5e  xor     rax, rsp
0x18002cc61  mov     [rbp+var_8], rax
0x18002cc65  neg     r9b
0x18002cc68  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18002cc71  mov     rbx, rdx
0x18002cc74  mov     [rbp+NumberOfBytesWritten], 0
0x18002cc7b  sbb     eax, eax
0x18002cc7d  mov     edx, 4; dwDesiredAccess
0x18002cc82  not     eax
0x18002cc84  mov     rsi, r8
0x18002cc87  and     eax, 80000000h
0x18002cc8c  xor     r9d, r9d; lpSecurityAttributes
0x18002cc8f  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18002cc93  lea     r8d, [rdx-3]; dwShareMode
0x18002cc97  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x18002cc9b  call    cs:__imp_CreateFileW
0x18002cca1  mov     rdi, rax
0x18002cca4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cca8  jnz     short loc_18002CCB4
0x18002ccaa  mov     ebx, 0C0000022h
0x18002ccaf  jmp     loc_18002CD5F
0x18002ccb4  cmp     [rbp+arg_20], 0
0x18002ccb8  jz      short loc_18002CD2D
0x18002ccba  xor     eax, eax
0x18002ccbc  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002ccc0  xorps   xmm0, xmm0
0x18002ccc3  mov     [rbp+Buffer], rax
0x18002ccc7  mov     [rbp+var_10], eax
0x18002ccca  mov     [rbp+var_C], al
0x18002cccd  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002ccd1  call    cs:__imp_GetLocalTime
0x18002ccd7  movzx   ecx, [rbp+SystemTime.wSecond]
0x18002ccdb  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x18002cce2  movzx   edx, [rbp+SystemTime.wMinute]
0x18002cce6  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x18002ccea  movzx   r9d, [rbp+SystemTime.wHour]
0x18002ccef  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x18002ccf3  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x18002ccf7  lea     rcx, [rbp+Buffer]; char *
0x18002ccfb  mov     [rsp+70h+dwCreationDisposition], edx
0x18002ccff  mov     edx, 0Dh; unsigned __int64
0x18002cd04  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002cd09  test    eax, eax
0x18002cd0b  js      short loc_18002CD2D
0x18002cd0d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002cd11  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18002cd1a  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x18002cd20  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002cd24  mov     rcx, rdi; hFile
0x18002cd27  call    cs:__imp_WriteFile
0x18002cd2d  mov     r8d, esi; nNumberOfBytesToWrite
0x18002cd30  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18002cd39  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002cd3d  mov     rdx, rbx; lpBuffer
0x18002cd40  mov     rcx, rdi; hFile
0x18002cd43  call    cs:__imp_WriteFile
0x18002cd49  neg     eax
0x18002cd4b  mov     ebx, 0C0000022h
0x18002cd50  sbb     ecx, ecx
0x18002cd52  not     ecx
0x18002cd54  and     ebx, ecx
0x18002cd56  mov     rcx, rdi; hObject
0x18002cd59  call    cs:__imp_CloseHandle
0x18002cd5f  mov     eax, ebx
0x18002cd61  mov     rcx, [rbp+var_8]
0x18002cd65  xor     rcx, rsp; StackCookie
0x18002cd68  call    __security_check_cookie
0x18002cd6d  mov     rbx, [rsp+70h+arg_18]
0x18002cd75  add     rsp, 70h
0x18002cd79  pop     rdi
0x18002cd7a  pop     rsi
0x18002cd7b  pop     rbp
0x18002cd7c  retn
```
