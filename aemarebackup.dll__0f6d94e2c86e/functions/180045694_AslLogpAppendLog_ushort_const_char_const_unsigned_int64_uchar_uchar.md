# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x180045694`
- end: `0x1800457c8`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `308`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *, DWORD, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180045950`

## callees

- `0x180004ea0`
- `0x180005bc0`
- `0x180045694`
- `0x1800467bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004571d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004571d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800456e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800456e7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045773`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004578f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045773`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004578f`

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
    CloseHandle_0(FileW);
  }
  return v8;
}

```

## disassembly

```asm
0x180045694  mov     [rsp-18h+arg_18], rbx
0x180045699  push    rbp
0x18004569a  push    rsi
0x18004569b  push    rdi
0x18004569c  mov     rbp, rsp
0x18004569f  sub     rsp, 70h
0x1800456a3  mov     rax, cs:__security_cookie
0x1800456aa  xor     rax, rsp
0x1800456ad  mov     [rbp+var_8], rax
0x1800456b1  neg     r9b
0x1800456b4  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800456bd  mov     rbx, rdx
0x1800456c0  mov     [rbp+NumberOfBytesWritten], 0
0x1800456c7  sbb     eax, eax
0x1800456c9  mov     edx, 4; dwDesiredAccess
0x1800456ce  not     eax
0x1800456d0  mov     rsi, r8
0x1800456d3  and     eax, 80000000h
0x1800456d8  xor     r9d, r9d; lpSecurityAttributes
0x1800456db  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800456df  lea     r8d, [rdx-3]; dwShareMode
0x1800456e3  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x1800456e7  call    cs:__imp_CreateFileW
0x1800456ed  mov     rdi, rax
0x1800456f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800456f4  jnz     short loc_180045700
0x1800456f6  mov     ebx, 0C0000022h
0x1800456fb  jmp     loc_1800457AA
0x180045700  cmp     [rbp+arg_20], 0
0x180045704  jz      short loc_180045779
0x180045706  xor     eax, eax
0x180045708  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18004570c  xorps   xmm0, xmm0
0x18004570f  mov     [rbp+Buffer], rax
0x180045713  mov     [rbp+var_10], eax
0x180045716  mov     [rbp+var_C], al
0x180045719  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18004571d  call    cs:__imp_GetLocalTime
0x180045723  movzx   ecx, [rbp+SystemTime.wSecond]
0x180045727  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x18004572e  movzx   edx, [rbp+SystemTime.wMinute]
0x180045732  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x180045736  movzx   r9d, [rbp+SystemTime.wHour]
0x18004573b  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x18004573f  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x180045743  lea     rcx, [rbp+Buffer]; char *
0x180045747  mov     [rsp+70h+dwCreationDisposition], edx
0x18004574b  mov     edx, 0Dh; unsigned __int64
0x180045750  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180045755  test    eax, eax
0x180045757  js      short loc_180045779
0x180045759  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004575d  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180045766  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x18004576c  lea     rdx, [rbp+Buffer]; lpBuffer
0x180045770  mov     rcx, rdi; hFile
0x180045773  call    cs:__imp_WriteFile
0x180045779  mov     r8d, esi; nNumberOfBytesToWrite
0x18004577c  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180045785  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180045789  mov     rdx, rbx; lpBuffer
0x18004578c  mov     rcx, rdi; hFile
0x18004578f  call    cs:__imp_WriteFile
0x180045795  neg     eax
0x180045797  mov     ebx, 0C0000022h
0x18004579c  sbb     ecx, ecx
0x18004579e  not     ecx
0x1800457a0  and     ebx, ecx
0x1800457a2  mov     rcx, rdi; hObject
0x1800457a5  call    CloseHandle_0
0x1800457aa  mov     eax, ebx
0x1800457ac  mov     rcx, [rbp+var_8]
0x1800457b0  xor     rcx, rsp; StackCookie
0x1800457b3  call    __security_check_cookie
0x1800457b8  mov     rbx, [rsp+70h+arg_18]
0x1800457c0  add     rsp, 70h
0x1800457c4  pop     rdi
0x1800457c5  pop     rsi
0x1800457c6  pop     rbp
0x1800457c7  retn
```
