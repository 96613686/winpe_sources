# CSessEnvRpc::SessEnvGetBinaryType(ushort const *)

- ea: `0x180036dd4`
- end: `0x180036ef2`
- name: `?SessEnvGetBinaryType@CSessEnvRpc@@SAKPEBG@Z`
- size: `286`
- prototype: `unsigned int __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180017e40`

## callees

- `0x18001a280`
- `0x18001ad5c`
- `0x180036dd4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ecb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036e47`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036e47`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036e72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036ec2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036e72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036ec2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180036e98`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180036e98`

## pseudocode

```c
__int64 __fastcall CSessEnvRpc::SessEnvGetBinaryType(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-178h] BYREF
  _WORD Buffer[30]; // [rsp+50h] [rbp-168h] BYREF
  LONG lDistanceToMove; // [rsp+8Ch] [rbp-12Ch]
  _BYTE v8[4]; // [rsp+90h] [rbp-128h] BYREF
  unsigned __int16 v9; // [rsp+94h] [rbp-124h]

  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  memset_0(v8, 0, 0x108u);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0)
      && Buffer[0] == 23117
      && SetFilePointer(v3, lDistanceToMove, 0, 0) != -1 )
    {
      ReadFile(v3, v8, 0x108u, &NumberOfBytesRead, 0);
    }
    CloseHandle(v3);
  }
  return v9;
}

```

## disassembly

```asm
0x180036dd4  push    rbx
0x180036dd6  sub     rsp, 1B0h
0x180036ddd  mov     rax, cs:__security_cookie
0x180036de4  xor     rax, rsp
0x180036de7  mov     [rsp+1B8h+var_18], rax
0x180036def  xor     edx, edx; Val
0x180036df1  mov     [rsp+1B8h+NumberOfBytesRead], 0
0x180036df9  mov     rbx, rcx
0x180036dfc  lea     rcx, [rsp+1B8h+Buffer]; void *
0x180036e01  lea     r8d, [rdx+40h]; Size
0x180036e05  call    memset_0
0x180036e0a  xor     edx, edx; Val
0x180036e0c  lea     rcx, [rsp+1B8h+var_128]; void *
0x180036e14  mov     r8d, 108h; Size
0x180036e1a  call    memset_0
0x180036e1f  xor     r9d, r9d; lpSecurityAttributes
0x180036e22  mov     [rsp+1B8h+hTemplateFile], 0; hTemplateFile
0x180036e2b  mov     [rsp+1B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180036e33  mov     edx, 80000000h; dwDesiredAccess
0x180036e38  mov     rcx, rbx; lpFileName
0x180036e3b  mov     [rsp+1B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180036e43  lea     r8d, [r9+1]; dwShareMode
0x180036e47  call    cs:__imp_CreateFileW
0x180036e4d  mov     rbx, rax
0x180036e50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036e54  jz      short loc_180036ED1
0x180036e56  lea     r9, [rsp+1B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180036e5b  mov     qword ptr [rsp+1B8h+dwCreationDisposition], 0; lpOverlapped
0x180036e64  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x180036e6a  lea     rdx, [rsp+1B8h+Buffer]; lpBuffer
0x180036e6f  mov     rcx, rax; hFile
0x180036e72  call    cs:__imp_ReadFile
0x180036e78  test    eax, eax
0x180036e7a  jz      short loc_180036EC8
0x180036e7c  mov     eax, 5A4Dh
0x180036e81  cmp     [rsp+1B8h+Buffer], ax
0x180036e86  jnz     short loc_180036EC8
0x180036e88  mov     edx, [rsp+1B8h+lDistanceToMove]; lDistanceToMove
0x180036e8f  xor     r9d, r9d; dwMoveMethod
0x180036e92  xor     r8d, r8d; lpDistanceToMoveHigh
0x180036e95  mov     rcx, rbx; hFile
0x180036e98  call    cs:__imp_SetFilePointer
0x180036e9e  cmp     eax, 0FFFFFFFFh
0x180036ea1  jz      short loc_180036EC8
0x180036ea3  lea     r9, [rsp+1B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180036ea8  mov     qword ptr [rsp+1B8h+dwCreationDisposition], 0; lpOverlapped
0x180036eb1  mov     r8d, 108h; nNumberOfBytesToRead
0x180036eb7  lea     rdx, [rsp+1B8h+var_128]; lpBuffer
0x180036ebf  mov     rcx, rbx; hFile
0x180036ec2  call    cs:__imp_ReadFile
0x180036ec8  mov     rcx, rbx; hObject
0x180036ecb  call    cs:__imp_CloseHandle
0x180036ed1  movzx   eax, [rsp+1B8h+var_124]
0x180036ed9  mov     rcx, [rsp+1B8h+var_18]
0x180036ee1  xor     rcx, rsp; StackCookie
0x180036ee4  call    __security_check_cookie
0x180036ee9  add     rsp, 1B0h
0x180036ef0  pop     rbx
0x180036ef1  retn
```
