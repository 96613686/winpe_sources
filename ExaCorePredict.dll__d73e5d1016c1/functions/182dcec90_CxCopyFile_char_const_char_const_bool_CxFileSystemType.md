# CxCopyFile(char const *,char const *,bool,CxFileSystemType)

- ea: `0x182dcec90`
- end: `0x182dced2a`
- name: `?CxCopyFile@@YA_NPEBD0_NW4CxFileSystemType@@@Z`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x182dcc420`
- `0x182dcc6d0`
- `0x182dceaf0`
- `0x182dcec90`

## import_xrefs

- `KERNEL32!CopyFileA` at `0x182dced0a`
- `KERNEL32!CopyFileA` at `0x182dced0a`

## string_xrefs

- `0x182dcecce`: `Invalid file system type in CopyFile()`
- `0x182dcecf0`: `Invalid file system type in CopyFile()`
- `0x182dcece4`: `Cannot copy to and from HDFS on Windows.`

## pseudocode

```c
char __fastcall CxCopyFile(const CHAR *a1, const CHAR *a2, __int64 a3, int a4)
{
  int v4; // ebx
  unsigned __int8 v5; // di
  int v9; // ebx

  v4 = a4;
  v5 = a3;
  if ( !a4 )
    v4 = gg_fileSysType;
  if ( v4 == 3 )
    return CxBaseCopyFile(a1, a2, a3, 3);
  if ( !v4 )
    CxInternalError("Invalid file system type in CopyFile()");
  v9 = v4 - 1;
  if ( !v9 )
    return CopyFileA(a1, a2, v5);
  if ( v9 == 1 )
    CxReportError("Cannot copy to and from HDFS on Windows.");
  CxInternalError("Invalid file system type in CopyFile()");
  return 0;
}

```

## disassembly

```asm
0x182dcec90  mov     [rsp+arg_0], rbx
0x182dcec95  mov     [rsp+arg_8], rbp
0x182dcec9a  mov     [rsp+arg_10], rsi
0x182dcec9f  push    rdi
0x182dceca0  sub     rsp, 20h
0x182dceca4  test    r9d, r9d
0x182dceca7  mov     ebx, r9d
0x182dcecaa  movzx   edi, r8b
0x182dcecae  mov     rsi, rdx
0x182dcecb1  cmovz   ebx, cs:?gg_fileSysType@@3W4CxFileSystemType@@A; CxFileSystemType gg_fileSysType
0x182dcecb8  mov     rbp, rcx
0x182dcecbb  cmp     ebx, 3
0x182dcecbe  jnz     short loc_182DCECCA
0x182dcecc0  mov     r9d, ebx
0x182dcecc3  call    CxBaseCopyFile
0x182dcecc8  jmp     short loc_182DCED15
0x182dcecca  test    ebx, ebx
0x182dceccc  jnz     short loc_182DCECDA
0x182dcecce  lea     rcx, aInvalidFileSys_0; "Invalid file system type in CopyFile()"
0x182dcecd5  call    ?CxInternalError@@YAXPEBDZZ; CxInternalError(char const *,...)
0x182dcecda  sub     ebx, 1
0x182dcecdd  jz      short loc_182DCED00
0x182dcecdf  cmp     ebx, 1
0x182dcece2  jnz     short loc_182DCECF0
0x182dcece4  lea     rcx, aCannotCopyToAn; "Cannot copy to and from HDFS on Windows"...
0x182dceceb  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcecf0  lea     rcx, aInvalidFileSys_0; "Invalid file system type in CopyFile()"
0x182dcecf7  call    ?CxInternalError@@YAXPEBDZZ; CxInternalError(char const *,...)
0x182dcecfc  xor     al, al
0x182dcecfe  jmp     short loc_182DCED15
0x182dced00  movzx   r8d, dil; bFailIfExists
0x182dced04  mov     rdx, rsi; lpNewFileName
0x182dced07  mov     rcx, rbp; lpExistingFileName
0x182dced0a  call    cs:__imp_CopyFileA
0x182dced10  test    eax, eax
0x182dced12  setnz   al
0x182dced15  mov     rbx, [rsp+28h+arg_0]
0x182dced1a  mov     rbp, [rsp+28h+arg_8]
0x182dced1f  mov     rsi, [rsp+28h+arg_10]
0x182dced24  add     rsp, 20h
0x182dced28  pop     rdi
0x182dced29  retn
```
