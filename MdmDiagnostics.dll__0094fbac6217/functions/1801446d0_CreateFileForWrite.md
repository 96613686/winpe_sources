# CreateFileForWrite

- ea: `0x1801446d0`
- end: `0x1801447a4`
- name: `CreateFileForWrite`
- size: `212`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801447ac`

## callees

- `0x180019f58`
- `0x1801446d0`
- `0x180145a98`
- `0x180145c24`
- `0x1801595f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014475a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014475a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144766`

## pseudocode

```c
__int64 __fastcall CreateFileForWrite(LPCWSTR lpFileName, _QWORD *a2)
{
  void *v2; // rdi
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int Directory; // eax
  __int64 v9; // rdx
  HANDLE FileW; // rax
  signed int LastError; // eax
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  Block = 0;
  if ( !lpFileName || !a2 )
  {
    v7 = -2147024809;
    goto LABEL_13;
  }
  v5 = PathDecompose(lpFileName, &Block);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v2 = Block;
    if ( Block )
    {
      Directory = PathCreateDirectory(Block);
      v7 = Directory;
      if ( Directory < 0 )
      {
        v9 = (unsigned int)Directory;
LABEL_14:
        LogErrorFxn(lpFileName, v9);
        goto LABEL_15;
      }
    }
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 1u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      *a2 = FileW;
      v7 = 0;
      goto LABEL_15;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
    v9 = v7;
    goto LABEL_14;
  }
  LogErrorFxn(v6, (unsigned int)v5);
  v2 = Block;
LABEL_15:
  free(v2);
  return v7;
}

```

## disassembly

```asm
0x1801446d0  push    rbx
0x1801446d2  push    rsi
0x1801446d3  push    rdi
0x1801446d4  push    r14
0x1801446d6  sub     rsp, 48h
0x1801446da  xor     edi, edi
0x1801446dc  mov     r14, rdx
0x1801446df  mov     [rsp+68h+Block], rdi
0x1801446e4  mov     rsi, rcx
0x1801446e7  test    rcx, rcx
0x1801446ea  jz      loc_180144784
0x1801446f0  test    rdx, rdx
0x1801446f3  jz      loc_180144784
0x1801446f9  lea     rdx, [rsp+68h+Block]
0x1801446fe  call    PathDecompose
0x180144703  mov     ebx, eax
0x180144705  test    eax, eax
0x180144707  jns     short loc_180144717
0x180144709  mov     edx, eax
0x18014470b  call    LogErrorFxn
0x180144710  mov     rdi, [rsp+68h+Block]
0x180144715  jmp     short loc_180144790
0x180144717  mov     rdi, [rsp+68h+Block]
0x18014471c  test    rdi, rdi
0x18014471f  jz      short loc_180144733
0x180144721  mov     rcx, rdi
0x180144724  call    PathCreateDirectory
0x180144729  mov     ebx, eax
0x18014472b  test    eax, eax
0x18014472d  jns     short loc_180144733
0x18014472f  mov     edx, eax
0x180144731  jmp     short loc_18014478B
0x180144733  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18014473c  xor     r9d, r9d; lpSecurityAttributes
0x18014473f  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180144747  xor     r8d, r8d; dwShareMode
0x18014474a  mov     edx, 0C0000000h; dwDesiredAccess
0x18014474f  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x180144757  mov     rcx, rsi; lpFileName
0x18014475a  call    cs:__imp_CreateFileW
0x180144760  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180144764  jnz     short loc_18014477D
0x180144766  call    cs:__imp_GetLastError
0x18014476c  mov     ebx, eax
0x18014476e  test    eax, eax
0x180144770  jle     short loc_180144789
0x180144772  movzx   ebx, ax
0x180144775  or      ebx, 80070000h
0x18014477b  jmp     short loc_180144789
0x18014477d  mov     [r14], rax
0x180144780  xor     ebx, ebx
0x180144782  jmp     short loc_180144790
0x180144784  mov     ebx, 80070057h
0x180144789  mov     edx, ebx
0x18014478b  call    LogErrorFxn
0x180144790  mov     rcx, rdi; Block
0x180144793  call    free
0x180144798  mov     eax, ebx
0x18014479a  add     rsp, 48h
0x18014479e  pop     r14
0x1801447a0  pop     rdi
0x1801447a1  pop     rsi
0x1801447a2  pop     rbx
0x1801447a3  retn
```
