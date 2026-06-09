# CWriteEnum::WriteWord(ushort const *,ulong)

- ea: `0x1800757e8`
- end: `0x1800758d9`
- name: `?WriteWord@CWriteEnum@@QEAA_NPEBGK@Z`
- size: `241`
- prototype: `bool(CWriteEnum *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180075670`

## callees

- `0x1800757e8`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180075888`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180075888`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180075837`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800758ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180075837`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800758ab`

## pseudocode

```c
bool __fastcall CWriteEnum::WriteWord(CWriteEnum *this, const unsigned __int16 *a2, DWORD a3)
{
  bool v3; // zf
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-128h] BYREF
  CHAR MultiByteStr[256]; // [rsp+50h] [rbp-118h] BYREF

  v3 = *((_BYTE *)this + 1060) == 0;
  NumberOfBytesWritten = 0;
  if ( v3 )
  {
    WideCharToMultiByte(*((_DWORD *)this + 264), 0, a2, a3, MultiByteStr, 256, " ", 0);
    WriteFile(*((HANDLE *)this + 131), MultiByteStr, a3, &NumberOfBytesWritten, 0);
    return NumberOfBytesWritten == a3;
  }
  else
  {
    WriteFile(*((HANDLE *)this + 131), a2, 2 * a3, &NumberOfBytesWritten, 0);
    return NumberOfBytesWritten == 2LL * a3;
  }
}

```

## disassembly

```asm
0x1800757e8  mov     [rsp+arg_18], rbx
0x1800757ed  push    rdi
0x1800757ee  sub     rsp, 160h
0x1800757f5  mov     rax, cs:__security_cookie
0x1800757fc  xor     rax, rsp
0x1800757ff  mov     [rsp+168h+var_18], rax
0x180075807  cmp     byte ptr [rcx+424h], 0
0x18007580e  mov     rdi, rcx
0x180075811  mov     ebx, r8d
0x180075814  mov     [rsp+168h+NumberOfBytesWritten], 0
0x18007581c  jz      short loc_180075853
0x18007581e  mov     rcx, [rcx+418h]; hFile
0x180075825  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180075829  lea     r9, [rsp+168h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007582e  mov     [rsp+168h+lpOverlapped], 0; lpOverlapped
0x180075837  call    cs:__imp_WriteFile
0x18007583d  mov     eax, [rsp+168h+NumberOfBytesWritten]
0x180075841  mov     ecx, ebx
0x180075843  add     rcx, rcx
0x180075846  cmp     rax, rcx
0x180075849  jnz     short loc_18007584F
0x18007584b  mov     al, 1
0x18007584d  jmp     short loc_1800758B8
0x18007584f  xor     al, al
0x180075851  jmp     short loc_1800758B8
0x180075853  mov     ecx, [rcx+420h]; CodePage
0x180075859  lea     rax, DefaultChar; " "
0x180075860  mov     [rsp+168h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180075869  mov     r8, rdx; lpWideCharStr
0x18007586c  mov     [rsp+168h+lpDefaultChar], rax; lpDefaultChar
0x180075871  mov     r9d, ebx; cchWideChar
0x180075874  lea     rax, [rsp+168h+MultiByteStr]
0x180075879  mov     [rsp+168h+cbMultiByte], 100h; cbMultiByte
0x180075881  xor     edx, edx; dwFlags
0x180075883  mov     [rsp+168h+lpOverlapped], rax; lpMultiByteStr
0x180075888  call    cs:__imp_WideCharToMultiByte
0x18007588e  mov     rcx, [rdi+418h]; hFile
0x180075895  lea     r9, [rsp+168h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007589a  mov     r8d, ebx; nNumberOfBytesToWrite
0x18007589d  mov     [rsp+168h+lpOverlapped], 0; lpOverlapped
0x1800758a6  lea     rdx, [rsp+168h+MultiByteStr]; lpBuffer
0x1800758ab  call    cs:__imp_WriteFile
0x1800758b1  cmp     [rsp+168h+NumberOfBytesWritten], ebx
0x1800758b5  setz    al
0x1800758b8  mov     rcx, [rsp+168h+var_18]
0x1800758c0  xor     rcx, rsp; StackCookie
0x1800758c3  call    __security_check_cookie
0x1800758c8  mov     rbx, [rsp+168h+arg_18]
0x1800758d0  add     rsp, 160h
0x1800758d7  pop     rdi
0x1800758d8  retn
```
