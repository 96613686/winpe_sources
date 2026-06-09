# InternalSafeCreateFile

- ea: `0x180012ad4`
- end: `0x180012b96`
- name: `InternalSafeCreateFile`
- size: `194`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, __int64, DWORD dwCreationDisposition, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800057a0`
- `0x180007d60`
- `0x1800087a0`
- `0x180008c80`
- `0x18001613c`
- `0x1800165d0`

## callees

- `0x180009a7c`
- `0x180012ad4`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180012b48`
- `KERNEL32!CreateFileW` at `0x180012b48`
- `KERNEL32!GetFileType` at `0x180012b62`
- `KERNEL32!GetFileType` at `0x180012b62`
- `KERNEL32!SetLastError` at `0x180012b7b`
- `KERNEL32!SetLastError` at `0x180012b7b`
- `KERNEL32!CloseHandle` at `0x180012b70`
- `KERNEL32!CloseHandle` at `0x180012b70`

## pseudocode

```c
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

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
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
0x180012ad4  mov     [rsp+arg_0], rbx
0x180012ad9  mov     [rsp+arg_8], rsi
0x180012ade  push    rdi
0x180012adf  sub     rsp, 40h
0x180012ae3  mov     ebx, r8d
0x180012ae6  mov     edi, edx
0x180012ae8  mov     rsi, rcx
0x180012aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012af2  lea     rax, WPP_GLOBAL_Control
0x180012af9  cmp     rcx, rax
0x180012afc  jz      short loc_180012B1F
0x180012afe  test    byte ptr [rcx+1Ch], 2
0x180012b02  jz      short loc_180012B1F
0x180012b04  cmp     byte ptr [rcx+19h], 5
0x180012b08  jb      short loc_180012B1F
0x180012b0a  mov     rcx, [rcx+10h]
0x180012b0e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180012b15  mov     edx, 4Ah ; 'J'
0x180012b1a  call    WPP_SF_
0x180012b1f  mov     eax, [rsp+48h+arg_28]
0x180012b23  xor     r9d, r9d; lpSecurityAttributes
0x180012b26  or      eax, 102000h
0x180012b2b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180012b34  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180012b38  mov     r8d, ebx; dwShareMode
0x180012b3b  mov     eax, [rsp+48h+arg_20]
0x180012b3f  mov     edx, edi; dwDesiredAccess
0x180012b41  mov     rcx, rsi; lpFileName
0x180012b44  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x180012b48  call    cs:__imp_CreateFileW
0x180012b4e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012b52  mov     rbx, rax
0x180012b55  cmp     rax, rdi
0x180012b58  jnz     short loc_180012B5F
0x180012b5a  mov     rax, rdi
0x180012b5d  jmp     short loc_180012B86
0x180012b5f  mov     rcx, rbx; hFile
0x180012b62  call    cs:__imp_GetFileType
0x180012b68  cmp     eax, 1
0x180012b6b  jz      short loc_180012B83
0x180012b6d  mov     rcx, rbx; hObject
0x180012b70  call    cs:__imp_CloseHandle
0x180012b76  mov     ecx, 65Eh; dwErrCode
0x180012b7b  call    cs:__imp_SetLastError
0x180012b81  jmp     short loc_180012B5A
0x180012b83  mov     rax, rbx
0x180012b86  mov     rbx, [rsp+48h+arg_0]
0x180012b8b  mov     rsi, [rsp+48h+arg_8]
0x180012b90  add     rsp, 40h
0x180012b94  pop     rdi
0x180012b95  retn
```
