# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x1800693f8`
- end: `0x18006952b`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `307`
- prototype: `int(const unsigned __int16 *, const char *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800695f4`

## callees

- `0x18002a2ec`
- `0x180059920`
- `0x18005abc0`
- `0x18005aca0`
- `0x1800693f8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800694d6`
- `KERNEL32!WriteFile` at `0x1800694f2`
- `KERNEL32!WriteFile` at `0x1800694d6`
- `KERNEL32!WriteFile` at `0x1800694f2`
- `KERNEL32!GetLocalTime` at `0x180069480`
- `KERNEL32!GetLocalTime` at `0x180069480`

## pseudocode

```c
__int64 __fastcall AslLogpAppendLog(const unsigned __int16 *a1, const char *a2, DWORD a3, char a4, unsigned __int8 a5)
{
  HANDLE FileW_0; // rdi
  unsigned int v8; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-18h] BYREF
  int v13; // [rsp+60h] [rbp-10h]
  char v14; // [rsp+64h] [rbp-Ch]

  NumberOfBytesWritten = 0;
  FileW_0 = CreateFileW_0(a1, 4u, 1u, 0, 4u, a4 == 0 ? 0x80000000 : 0, 0);
  if ( FileW_0 == (HANDLE)-1LL )
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
        WriteFile(FileW_0, &Buffer, 0xDu, &NumberOfBytesWritten, 0);
    }
    v8 = !WriteFile(FileW_0, a2, a3, &NumberOfBytesWritten, 0) ? 0xC0000022 : 0;
    CloseHandle_0(FileW_0);
  }
  return v8;
}

```

## disassembly

```asm
0x1800693f8  mov     [rsp-18h+arg_18], rbx
0x1800693fd  push    rbp
0x1800693fe  push    rsi
0x1800693ff  push    rdi
0x180069400  mov     rbp, rsp
0x180069403  sub     rsp, 70h
0x180069407  mov     rax, cs:__security_cookie
0x18006940e  xor     rax, rsp
0x180069411  mov     [rbp+var_8], rax
0x180069415  neg     r9b
0x180069418  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180069421  mov     rbx, rdx
0x180069424  mov     [rbp+NumberOfBytesWritten], 0
0x18006942b  sbb     eax, eax
0x18006942d  mov     edx, 4; dwDesiredAccess
0x180069432  not     eax
0x180069434  mov     rsi, r8
0x180069437  and     eax, 80000000h
0x18006943c  xor     r9d, r9d; lpSecurityAttributes
0x18006943f  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180069443  lea     r8d, [rdx-3]; dwShareMode
0x180069447  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x18006944b  call    CreateFileW_0
0x180069450  mov     rdi, rax
0x180069453  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069457  jnz     short loc_180069463
0x180069459  mov     ebx, 0C0000022h
0x18006945e  jmp     loc_18006950D
0x180069463  cmp     [rbp+arg_20], 0
0x180069467  jz      short loc_1800694DC
0x180069469  xor     eax, eax
0x18006946b  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18006946f  xorps   xmm0, xmm0
0x180069472  mov     [rbp+Buffer], rax
0x180069476  mov     [rbp+var_10], eax
0x180069479  mov     [rbp+var_C], al
0x18006947c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180069480  call    cs:__imp_GetLocalTime
0x180069486  movzx   ecx, [rbp+SystemTime.wSecond]
0x18006948a  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x180069491  movzx   edx, [rbp+SystemTime.wMinute]
0x180069495  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x180069499  movzx   r9d, [rbp+SystemTime.wHour]
0x18006949e  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x1800694a2  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x1800694a6  lea     rcx, [rbp+Buffer]; char *
0x1800694aa  mov     [rsp+70h+dwCreationDisposition], edx
0x1800694ae  mov     edx, 0Dh; unsigned __int64
0x1800694b3  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800694b8  test    eax, eax
0x1800694ba  js      short loc_1800694DC
0x1800694bc  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800694c0  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800694c9  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x1800694cf  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800694d3  mov     rcx, rdi; hFile
0x1800694d6  call    cs:__imp_WriteFile
0x1800694dc  mov     r8d, esi; nNumberOfBytesToWrite
0x1800694df  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800694e8  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800694ec  mov     rdx, rbx; lpBuffer
0x1800694ef  mov     rcx, rdi; hFile
0x1800694f2  call    cs:__imp_WriteFile
0x1800694f8  neg     eax
0x1800694fa  mov     ebx, 0C0000022h
0x1800694ff  sbb     ecx, ecx
0x180069501  not     ecx
0x180069503  and     ebx, ecx
0x180069505  mov     rcx, rdi; hObject
0x180069508  call    CloseHandle_0
0x18006950d  mov     eax, ebx
0x18006950f  mov     rcx, [rbp+var_8]
0x180069513  xor     rcx, rsp; StackCookie
0x180069516  call    __security_check_cookie
0x18006951b  mov     rbx, [rsp+70h+arg_18]
0x180069523  add     rsp, 70h
0x180069527  pop     rdi
0x180069528  pop     rsi
0x180069529  pop     rbp
0x18006952a  retn
```
