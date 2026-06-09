# InternalSafeCreateFile

- ea: `0x1800131b4`
- end: `0x18001328f`
- name: `InternalSafeCreateFile`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, __int64, DWORD dwCreationDisposition, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005890`
- `0x180008070`
- `0x180008b70`
- `0x180009088`
- `0x180016d50`
- `0x1800172f4`

## callees

- `0x180009f04`
- `0x1800131b4`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180013228`
- `KERNEL32!CreateFileW` at `0x180013228`
- `KERNEL32!GetFileType` at `0x180013248`
- `KERNEL32!GetFileType` at `0x180013248`
- `KERNEL32!SetLastError` at `0x18001326d`
- `KERNEL32!SetLastError` at `0x18001326d`
- `KERNEL32!CloseHandle` at `0x18001325c`
- `KERNEL32!CloseHandle` at `0x18001325c`

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
0x1800131b4  mov     [rsp+arg_0], rbx
0x1800131b9  mov     [rsp+arg_8], rsi
0x1800131be  push    rdi
0x1800131bf  sub     rsp, 40h
0x1800131c3  mov     ebx, r8d
0x1800131c6  mov     edi, edx
0x1800131c8  mov     rsi, rcx
0x1800131cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131d2  lea     rax, WPP_GLOBAL_Control
0x1800131d9  cmp     rcx, rax
0x1800131dc  jz      short loc_1800131FF
0x1800131de  test    byte ptr [rcx+1Ch], 2
0x1800131e2  jz      short loc_1800131FF
0x1800131e4  cmp     byte ptr [rcx+19h], 5
0x1800131e8  jb      short loc_1800131FF
0x1800131ea  mov     rcx, [rcx+10h]
0x1800131ee  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1800131f5  mov     edx, 4Ah ; 'J'
0x1800131fa  call    WPP_SF_
0x1800131ff  mov     eax, [rsp+48h+arg_28]
0x180013203  xor     r9d, r9d; lpSecurityAttributes
0x180013206  or      eax, 102000h
0x18001320b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180013214  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180013218  mov     r8d, ebx; dwShareMode
0x18001321b  mov     eax, [rsp+48h+arg_20]
0x18001321f  mov     edx, edi; dwDesiredAccess
0x180013221  mov     rcx, rsi; lpFileName
0x180013224  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x180013228  call    cs:__imp_CreateFileW
0x18001322f  nop     dword ptr [rax+rax+00h]
0x180013234  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013238  mov     rbx, rax
0x18001323b  cmp     rax, rdi
0x18001323e  jnz     short loc_180013245
0x180013240  mov     rax, rdi
0x180013243  jmp     short loc_18001327E
0x180013245  mov     rcx, rbx; hFile
0x180013248  call    cs:__imp_GetFileType
0x18001324f  nop     dword ptr [rax+rax+00h]
0x180013254  cmp     eax, 1
0x180013257  jz      short loc_18001327B
0x180013259  mov     rcx, rbx; hObject
0x18001325c  call    cs:__imp_CloseHandle
0x180013263  nop     dword ptr [rax+rax+00h]
0x180013268  mov     ecx, 65Eh; dwErrCode
0x18001326d  call    cs:__imp_SetLastError
0x180013274  nop     dword ptr [rax+rax+00h]
0x180013279  jmp     short loc_180013240
0x18001327b  mov     rax, rbx
0x18001327e  mov     rbx, [rsp+48h+arg_0]
0x180013283  mov     rsi, [rsp+48h+arg_8]
0x180013288  add     rsp, 40h
0x18001328c  pop     rdi
0x18001328d  retn
```
