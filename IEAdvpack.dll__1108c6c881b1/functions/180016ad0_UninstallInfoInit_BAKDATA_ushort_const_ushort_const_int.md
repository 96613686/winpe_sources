# UninstallInfoInit(_BAKDATA *,ushort const *,ushort const *,int)

- ea: `0x180016ad0`
- end: `0x180016c06`
- name: `?UninstallInfoInit@@YAHPEAU_BAKDATA@@PEBG1H@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct _BAKDATA *, size_t *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800152d8`
- `0x180016268`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x180016ad0`
- `0x180017fdc`
- `0x18001b980`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180016b87`
- `KERNEL32!CreateFileW` at `0x180016b87`
- `KERNEL32!SetFilePointer` at `0x180016ba8`
- `KERNEL32!SetFilePointer` at `0x180016ba8`
- `KERNEL32!SetFileAttributesW` at `0x180016b53`
- `KERNEL32!SetFileAttributesW` at `0x180016bdd`
- `KERNEL32!SetFileAttributesW` at `0x180016b53`
- `KERNEL32!SetFileAttributesW` at `0x180016bdd`

## pseudocode

```c
__int64 __fastcall UninstallInfoInit(struct _BAKDATA *a1, size_t *a2, const unsigned __int16 *a3, int a4)
{
  char *v5; // rdi
  __int64 v8; // rdx
  HANDLE FileW; // rax
  unsigned __int16 *v11; // rbx
  __int64 v12; // rdx
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  *(_QWORD *)a1 = -1;
  v5 = (char *)a1 + 532;
  StringCchCopyW((unsigned __int16 *)a1 + 266, 0x104u, a2);
  if ( *(_QWORD *)a1 == -1 )
  {
    BuildPath(FileName, v8, v5, a3);
    StringCchCatW(FileName, 260, L".DAT");
    SetFileAttributesW(FileName, 0x80u);
    FileW = CreateFileW(FileName, 0xC0000000, 0, 0, (unsigned int)(a4 != 0) + 3, 0x80u, 0);
    *(_QWORD *)a1 = FileW;
    if ( FileW == (HANDLE)-1LL )
      return 0;
    *((_DWORD *)a1 + 2) = SetFilePointer(FileW, 0, 0, 2u);
    v11 = (unsigned __int16 *)((char *)a1 + 12);
    BuildPath(v11, v12, v5, a3);
    StringCchCatW(v11, 260, L".INI");
    SetFileAttributesW(v11, 0x80u);
  }
  return 1;
}

```

## disassembly

```asm
0x180016ad0  push    rbx
0x180016ad2  push    rbp
0x180016ad3  push    rsi
0x180016ad4  push    rdi
0x180016ad5  push    r14
0x180016ad7  sub     rsp, 260h
0x180016ade  mov     rax, cs:__security_cookie
0x180016ae5  xor     rax, rsp
0x180016ae8  mov     [rsp+288h+var_38], rax
0x180016af0  mov     rsi, r8
0x180016af3  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180016afa  lea     rdi, [rcx+214h]
0x180016b01  mov     r8, rdx; unsigned __int16 *
0x180016b04  mov     rbx, rcx
0x180016b07  mov     r14d, 104h
0x180016b0d  mov     edx, r14d; unsigned __int64
0x180016b10  mov     rcx, rdi; unsigned __int16 *
0x180016b13  mov     ebp, r9d
0x180016b16  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016b1b  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180016b1f  jnz     loc_180016BE3
0x180016b25  mov     r9, rsi
0x180016b28  lea     rcx, [rsp+288h+FileName]
0x180016b2d  mov     r8, rdi
0x180016b30  call    BuildPath
0x180016b35  lea     r8, aDat_1; ".DAT"
0x180016b3c  mov     edx, r14d; unsigned __int64
0x180016b3f  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180016b44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016b49  mov     edx, 80h; dwFileAttributes
0x180016b4e  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180016b53  call    cs:__imp_SetFileAttributesW
0x180016b59  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180016b62  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180016b67  neg     ebp
0x180016b69  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016b71  mov     edx, 0C0000000h; dwDesiredAccess
0x180016b76  sbb     eax, eax
0x180016b78  xor     r9d, r9d; lpSecurityAttributes
0x180016b7b  neg     eax
0x180016b7d  xor     r8d, r8d; dwShareMode
0x180016b80  add     eax, 3
0x180016b83  mov     [rsp+288h+dwCreationDisposition], eax; dwCreationDisposition
0x180016b87  call    cs:__imp_CreateFileW
0x180016b8d  mov     [rbx], rax
0x180016b90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016b94  jnz     short loc_180016B9A
0x180016b96  xor     eax, eax
0x180016b98  jmp     short loc_180016BE8
0x180016b9a  mov     r9d, 2; dwMoveMethod
0x180016ba0  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016ba3  xor     edx, edx; lDistanceToMove
0x180016ba5  mov     rcx, rax; hFile
0x180016ba8  call    cs:__imp_SetFilePointer
0x180016bae  mov     [rbx+8], eax
0x180016bb1  mov     r9, rsi
0x180016bb4  add     rbx, 0Ch
0x180016bb8  mov     r8, rdi
0x180016bbb  mov     rcx, rbx
0x180016bbe  call    BuildPath
0x180016bc3  lea     r8, aIni_0; ".INI"
0x180016bca  mov     rdx, r14; unsigned __int64
0x180016bcd  mov     rcx, rbx; unsigned __int16 *
0x180016bd0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016bd5  mov     edx, 80h; dwFileAttributes
0x180016bda  mov     rcx, rbx; lpFileName
0x180016bdd  call    cs:__imp_SetFileAttributesW
0x180016be3  mov     eax, 1
0x180016be8  mov     rcx, [rsp+288h+var_38]
0x180016bf0  xor     rcx, rsp; StackCookie
0x180016bf3  call    __security_check_cookie
0x180016bf8  add     rsp, 260h
0x180016bff  pop     r14
0x180016c01  pop     rdi
0x180016c02  pop     rsi
0x180016c03  pop     rbp
0x180016c04  pop     rbx
0x180016c05  retn
```
