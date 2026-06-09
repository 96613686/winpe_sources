# InternalSafeCreateFile

- ea: `0x14006e124`
- end: `0x14006e1ff`
- name: `InternalSafeCreateFile`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, __int64, DWORD dwCreationDisposition, int)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400066e8`
- `0x14000bf30`
- `0x14000de90`
- `0x14001d310`
- `0x14001dbc0`
- `0x140021e70`
- `0x140022460`
- `0x140028d5c`
- `0x1400292bc`
- `0x140036744`
- `0x140038d44`
- `0x14003c834`
- `0x140053b44`
- `0x140071b38`
- `0x1400720c8`
- `0x140072a70`
- `0x140076574`

## callees

- `0x140004c78`
- `0x14006e124`

## import_xrefs

- `KERNEL32!GetFileType` at `0x14006e1b8`
- `KERNEL32!GetFileType` at `0x14006e1b8`
- `KERNEL32!CreateFileW` at `0x14006e198`
- `KERNEL32!CreateFileW` at `0x14006e198`
- `KERNEL32!SetLastError` at `0x14006e1dd`
- `KERNEL32!SetLastError` at `0x14006e1dd`
- `KERNEL32!CloseHandle` at `0x14006e1cc`
- `KERNEL32!CloseHandle` at `0x14006e1cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InternalSafeCreateFile(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        __int64 a4,
        DWORD dwCreationDisposition,
        int a6)
{
  HANDLE FileW; // rax
  void *v10; // rbx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, a6 | 0x102000u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return -1;
  if ( GetFileType(FileW) != 1 )
  {
    CloseHandle(v10);
    SetLastError(0x65Eu);
    return -1;
  }
  return (__int64)v10;
}

```

## disassembly

```asm
0x14006e124  mov     [rsp+arg_0], rbx
0x14006e129  mov     [rsp+arg_8], rsi
0x14006e12e  push    rdi
0x14006e12f  sub     rsp, 40h
0x14006e133  mov     ebx, r8d
0x14006e136  mov     edi, edx
0x14006e138  mov     rsi, rcx
0x14006e13b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e142  lea     rax, WPP_GLOBAL_Control
0x14006e149  cmp     rcx, rax
0x14006e14c  jz      short loc_14006E16F
0x14006e14e  test    byte ptr [rcx+1Ch], 2
0x14006e152  jz      short loc_14006E16F
0x14006e154  cmp     byte ptr [rcx+19h], 5
0x14006e158  jb      short loc_14006E16F
0x14006e15a  mov     rcx, [rcx+10h]
0x14006e15e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e165  mov     edx, 4Ah ; 'J'
0x14006e16a  call    WPP_SF_
0x14006e16f  mov     eax, [rsp+48h+arg_28]
0x14006e173  xor     r9d, r9d; lpSecurityAttributes
0x14006e176  or      eax, 102000h
0x14006e17b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14006e184  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14006e188  mov     r8d, ebx; dwShareMode
0x14006e18b  mov     eax, [rsp+48h+arg_20]
0x14006e18f  mov     edx, edi; dwDesiredAccess
0x14006e191  mov     rcx, rsi; lpFileName
0x14006e194  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x14006e198  call    cs:__imp_CreateFileW
0x14006e19f  nop     dword ptr [rax+rax+00h]
0x14006e1a4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006e1a8  mov     rbx, rax
0x14006e1ab  cmp     rax, rdi
0x14006e1ae  jnz     short loc_14006E1B5
0x14006e1b0  mov     rax, rdi
0x14006e1b3  jmp     short loc_14006E1EE
0x14006e1b5  mov     rcx, rbx; hFile
0x14006e1b8  call    cs:__imp_GetFileType
0x14006e1bf  nop     dword ptr [rax+rax+00h]
0x14006e1c4  cmp     eax, 1
0x14006e1c7  jz      short loc_14006E1EB
0x14006e1c9  mov     rcx, rbx; hObject
0x14006e1cc  call    cs:__imp_CloseHandle
0x14006e1d3  nop     dword ptr [rax+rax+00h]
0x14006e1d8  mov     ecx, 65Eh; dwErrCode
0x14006e1dd  call    cs:__imp_SetLastError
0x14006e1e4  nop     dword ptr [rax+rax+00h]
0x14006e1e9  jmp     short loc_14006E1B0
0x14006e1eb  mov     rax, rbx
0x14006e1ee  mov     rbx, [rsp+48h+arg_0]
0x14006e1f3  mov     rsi, [rsp+48h+arg_8]
0x14006e1f8  add     rsp, 40h
0x14006e1fc  pop     rdi
0x14006e1fd  retn
```
