# InternalSafeCreateFile

- ea: `0x1800308e0`
- end: `0x1800309bb`
- name: `InternalSafeCreateFile`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, __int64, DWORD dwCreationDisposition, int)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001e5e0`
- `0x18002cf00`
- `0x1800309c4`
- `0x180030f60`
- `0x180031098`
- `0x1800312c4`
- `0x180038190`
- `0x180039128`
- `0x1800395f8`

## callees

- `0x18000abe4`
- `0x1800308e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180030954`
- `KERNEL32!CreateFileW` at `0x180030954`
- `KERNEL32!GetFileType` at `0x180030974`
- `KERNEL32!GetFileType` at `0x180030974`
- `KERNEL32!CloseHandle` at `0x180030988`
- `KERNEL32!CloseHandle` at `0x180030988`
- `KERNEL32!SetLastError` at `0x180030999`
- `KERNEL32!SetLastError` at `0x180030999`

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
0x1800308e0  mov     [rsp+arg_0], rbx
0x1800308e5  mov     [rsp+arg_8], rsi
0x1800308ea  push    rdi
0x1800308eb  sub     rsp, 40h
0x1800308ef  mov     ebx, r8d
0x1800308f2  mov     edi, edx
0x1800308f4  mov     rsi, rcx
0x1800308f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308fe  lea     rax, WPP_GLOBAL_Control
0x180030905  cmp     rcx, rax
0x180030908  jz      short loc_18003092B
0x18003090a  test    byte ptr [rcx+1Ch], 2
0x18003090e  jz      short loc_18003092B
0x180030910  cmp     byte ptr [rcx+19h], 5
0x180030914  jb      short loc_18003092B
0x180030916  mov     rcx, [rcx+10h]
0x18003091a  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030921  mov     edx, 4Ah ; 'J'
0x180030926  call    WPP_SF_
0x18003092b  mov     eax, [rsp+48h+arg_28]
0x18003092f  xor     r9d, r9d; lpSecurityAttributes
0x180030932  or      eax, 102000h
0x180030937  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180030940  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180030944  mov     r8d, ebx; dwShareMode
0x180030947  mov     eax, [rsp+48h+arg_20]
0x18003094b  mov     edx, edi; dwDesiredAccess
0x18003094d  mov     rcx, rsi; lpFileName
0x180030950  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x180030954  call    cs:__imp_CreateFileW
0x18003095b  nop     dword ptr [rax+rax+00h]
0x180030960  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180030964  mov     rbx, rax
0x180030967  cmp     rax, rdi
0x18003096a  jnz     short loc_180030971
0x18003096c  mov     rax, rdi
0x18003096f  jmp     short loc_1800309AA
0x180030971  mov     rcx, rbx; hFile
0x180030974  call    cs:__imp_GetFileType
0x18003097b  nop     dword ptr [rax+rax+00h]
0x180030980  cmp     eax, 1
0x180030983  jz      short loc_1800309A7
0x180030985  mov     rcx, rbx; hObject
0x180030988  call    cs:__imp_CloseHandle
0x18003098f  nop     dword ptr [rax+rax+00h]
0x180030994  mov     ecx, 65Eh; dwErrCode
0x180030999  call    cs:__imp_SetLastError
0x1800309a0  nop     dword ptr [rax+rax+00h]
0x1800309a5  jmp     short loc_18003096C
0x1800309a7  mov     rax, rbx
0x1800309aa  mov     rbx, [rsp+48h+arg_0]
0x1800309af  mov     rsi, [rsp+48h+arg_8]
0x1800309b4  add     rsp, 40h
0x1800309b8  pop     rdi
0x1800309b9  retn
```
