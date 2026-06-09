# WcAttachFilterAndGetToken

- ea: `0x180024e9c`
- end: `0x180024f8c`
- name: `WcAttachFilterAndGetToken`
- size: `240`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, LPCWSTR lpFileName@<rdx>, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180024d94`
- `0x1800254bc`

## callees

- `0x180024e9c`
- `0x180025300`
- `0x180026284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024ee5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024ee5`

## pseudocode

```c
__int64 __fastcall WcAttachFilterAndGetToken(
        void *Src,
        LPCWSTR lpFileName,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  HANDLE FileW; // rax
  void *v8; // rdi
  signed int LastError; // eax
  int v10; // ebx
  int RootToken; // eax

  FileW = CreateFileW(lpFileName, 0x80u, 1u, 0, 3u, a5 != 0 ? 0x2000000 : 35651584, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !a6 )
    {
      RootToken = WcpGetRootToken(FileW);
      v10 = RootToken;
      if ( RootToken >= 0 )
        goto LABEL_10;
      if ( RootToken != -2147024895 && RootToken != -2147024846 )
        goto LABEL_9;
    }
    v10 = WcpAttachFilterInstance(Src);
    if ( v10 >= 0 )
LABEL_9:
      v10 = WcpGetRootToken(v8);
LABEL_10:
    CloseHandle(v8);
    return (unsigned int)v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180024e9c  push    rbx
0x180024e9e  push    rbp
0x180024e9f  push    rsi
0x180024ea0  push    rdi
0x180024ea1  sub     rsp, 48h
0x180024ea5  neg     [rsp+68h+arg_20]
0x180024eac  mov     r10, rdx
0x180024eaf  mov     esi, r8d
0x180024eb2  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180024ebb  sbb     eax, eax
0x180024ebd  mov     rbp, rcx
0x180024ec0  xor     r9d, r9d; lpSecurityAttributes
0x180024ec3  and     eax, 0FFE00000h
0x180024ec8  add     eax, 2200000h
0x180024ecd  mov     edx, 80h; dwDesiredAccess
0x180024ed2  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180024ed6  mov     rcx, r10; lpFileName
0x180024ed9  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180024ee1  lea     r8d, [r9+1]; dwShareMode
0x180024ee5  call    cs:__imp_CreateFileW
0x180024eec  nop     dword ptr [rax+rax+00h]
0x180024ef1  mov     rdi, rax
0x180024ef4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024ef8  jnz     short loc_180024F17
0x180024efa  call    cs:__imp_GetLastError
0x180024f01  nop     dword ptr [rax+rax+00h]
0x180024f06  mov     ebx, eax
0x180024f08  test    eax, eax
0x180024f0a  jle     short loc_180024F80
0x180024f0c  movzx   ebx, ax
0x180024f0f  or      ebx, 80070000h
0x180024f15  jmp     short loc_180024F80
0x180024f17  mov     rdx, [rsp+68h+arg_28]
0x180024f1f  test    rdx, rdx
0x180024f22  jnz     short loc_180024F4C
0x180024f24  mov     r8, [rsp+68h+arg_30]
0x180024f2c  mov     edx, esi
0x180024f2e  mov     rcx, rdi; hDevice
0x180024f31  call    WcpGetRootToken
0x180024f36  mov     ebx, eax
0x180024f38  test    eax, eax
0x180024f3a  jns     short loc_180024F71
0x180024f3c  cmp     eax, 80070001h
0x180024f41  jz      short loc_180024F4A
0x180024f43  cmp     eax, 80070032h
0x180024f48  jnz     short loc_180024F5D
0x180024f4a  xor     edx, edx
0x180024f4c  mov     r8, rdi
0x180024f4f  mov     rcx, rbp; Src
0x180024f52  call    WcpAttachFilterInstance
0x180024f57  mov     ebx, eax
0x180024f59  test    eax, eax
0x180024f5b  js      short loc_180024F71
0x180024f5d  mov     r8, [rsp+68h+arg_30]
0x180024f65  mov     edx, esi
0x180024f67  mov     rcx, rdi; hDevice
0x180024f6a  call    WcpGetRootToken
0x180024f6f  mov     ebx, eax
0x180024f71  mov     rcx, rdi; hObject
0x180024f74  call    cs:__imp_CloseHandle
0x180024f7b  nop     dword ptr [rax+rax+00h]
0x180024f80  mov     eax, ebx
0x180024f82  add     rsp, 48h
0x180024f86  pop     rdi
0x180024f87  pop     rsi
0x180024f88  pop     rbp
0x180024f89  pop     rbx
0x180024f8a  retn
```
