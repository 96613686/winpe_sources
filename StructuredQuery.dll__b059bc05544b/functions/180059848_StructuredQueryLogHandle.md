# StructuredQueryLogHandle

- ea: `0x180059848`
- end: `0x18005991a`
- name: `StructuredQueryLogHandle`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010ce0`
- `0x180049900`
- `0x180049b64`

## callees

- `0x180059848`
- `0x180059920`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800598ce`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800598ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800598b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800598b3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180059881`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180059881`

## string_xrefs

- `0x180059874`: `%TEMP%\StructuredQuery.log`

## pseudocode

```c
__int64 __fastcall StructuredQueryLogHandle(_QWORD *a1)
{
  unsigned int Error; // ebx
  HANDLE FileW; // rax
  HANDLE v4; // rsi
  WCHAR Dst[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( ExpandEnvironmentStringsW(L"%TEMP%\\StructuredQuery.log", Dst, 0x104u) )
  {
    Error = 0;
    FileW = CreateFileW(Dst, 0x40000000u, 2u, 0, 4u, 0x80u, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL && SetFilePointer(FileW, 0, 0, 2u) == -1 )
      Error = ResultFromKnownLastError();
    *a1 = v4;
  }
  else
  {
    *a1 = -1;
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x180059848  mov     [rsp+arg_8], rbx
0x18005984d  mov     [rsp+arg_10], rsi
0x180059852  push    rdi
0x180059853  sub     rsp, 260h
0x18005985a  mov     rax, cs:__security_cookie
0x180059861  xor     rax, rsp
0x180059864  mov     [rsp+268h+var_18], rax
0x18005986c  mov     rdi, rcx
0x18005986f  lea     rdx, [rsp+268h+Dst]; lpDst
0x180059874  lea     rcx, Src; "%TEMP%\\StructuredQuery.log"
0x18005987b  mov     r8d, 104h; nSize
0x180059881  call    cs:__imp_ExpandEnvironmentStringsW
0x180059887  test    eax, eax
0x180059889  jz      short loc_1800598E5
0x18005988b  xor     ebx, ebx
0x18005988d  lea     rcx, [rsp+268h+Dst]; lpFileName
0x180059892  mov     [rsp+268h+hTemplateFile], rbx; hTemplateFile
0x180059897  xor     r9d, r9d; lpSecurityAttributes
0x18005989a  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800598a2  mov     edx, 40000000h; dwDesiredAccess
0x1800598a7  mov     [rsp+268h+dwCreationDisposition], 4; dwCreationDisposition
0x1800598af  lea     r8d, [rbx+2]; dwShareMode
0x1800598b3  call    cs:__imp_CreateFileW
0x1800598b9  mov     rsi, rax
0x1800598bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800598c0  jz      short loc_1800598E0
0x1800598c2  lea     r9d, [rbx+2]; dwMoveMethod
0x1800598c6  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800598c9  xor     edx, edx; lDistanceToMove
0x1800598cb  mov     rcx, rax; hFile
0x1800598ce  call    cs:__imp_SetFilePointer
0x1800598d4  cmp     eax, 0FFFFFFFFh
0x1800598d7  jnz     short loc_1800598E0
0x1800598d9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800598de  mov     ebx, eax
0x1800598e0  mov     [rdi], rsi
0x1800598e3  jmp     short loc_1800598F3
0x1800598e5  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800598ec  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800598f1  mov     ebx, eax
0x1800598f3  mov     eax, ebx
0x1800598f5  mov     rcx, [rsp+268h+var_18]
0x1800598fd  xor     rcx, rsp; StackCookie
0x180059900  call    __security_check_cookie
0x180059905  lea     r11, [rsp+268h+var_8]
0x18005990d  mov     rbx, [r11+18h]
0x180059911  mov     rsi, [r11+20h]
0x180059915  mov     rsp, r11
0x180059918  pop     rdi
0x180059919  retn
```
