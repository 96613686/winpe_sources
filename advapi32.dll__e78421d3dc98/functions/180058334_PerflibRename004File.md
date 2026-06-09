# PerflibRename004File

- ea: `0x180058334`
- end: `0x180058501`
- name: `PerflibRename004File`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002b984`

## callees

- `0x180017100`
- `0x1800175c8`
- `0x180058334`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800584e1`
- `KERNEL32!LocalFree` at `0x1800584e1`
- `KERNEL32!LocalFree` at `0x1800584fa`
- `KERNEL32!CloseHandle` at `0x1800584d8`
- `KERNEL32!CloseHandle` at `0x1800584d8`
- `KERNEL32!CreateFileW` at `0x1800584a4`
- `KERNEL32!CreateFileW` at `0x1800584a4`
- `KERNEL32!DeleteFileW` at `0x18005847c`
- `KERNEL32!DeleteFileW` at `0x18005847c`
- `KERNEL32!SetFileInformationByHandle` at `0x1800584cf`
- `KERNEL32!SetFileInformationByHandle` at `0x1800584cf`
- `KERNEL32!CopyFileExW` at `0x18005845a`
- `KERNEL32!CopyFileExW` at `0x18005845a`

## pseudocode

```c
HLOCAL __fastcall PerflibRename004File(__int64 a1, int a2, __int64 a3, char a4)
{
  __int64 v7; // rax
  unsigned __int64 v8; // r12
  _QWORD *v9; // rbx
  unsigned __int16 *v10; // rsi
  __int64 v11; // rax
  unsigned __int16 *v12; // r13
  const wchar_t *v13; // rax
  const wchar_t *v14; // rdi
  const wchar_t *v15; // rax
  HANDLE FileW; // rax
  void *v17; // rdi

  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v8 = (unsigned int)(v7 + 19);
  v9 = 0;
  v10 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
  if ( v10 )
  {
    v11 = operator new(2 * v8 + 24);
    v9 = (_QWORD *)v11;
    if ( v11 )
    {
      v12 = (unsigned __int16 *)(v11 + 20);
      if ( a2 == 4 )
      {
        v13 = L"perfh004.dat";
        v14 = L"perfc004.dat";
      }
      else
      {
        v14 = L"perfc016.dat";
        v13 = L"perfh016.dat";
      }
      if ( !a4 )
        v14 = v13;
      StringCchPrintfW(v10, v8, L"%ws\\%ws", a1, v14);
      if ( a3 )
      {
        v15 = L"prfc";
        if ( !a4 )
          v15 = L"prfh";
        StringCchPrintfW(v12, v8, L"%ws\\%ws%ws%ws", a1, v15, a3, L".dat");
        CopyFileExW(v10, v12, 0, 0, 0, 0);
      }
      else
      {
        StringCchPrintfW(v12, v8, L"%ws\\%ws.tmp", a1, v14);
        DeleteFileW(v12);
        FileW = CreateFileW(v10, 0x40010000u, 0, 0, 3u, 0, 0);
        v17 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          *(_BYTE *)v9 = 0;
          v9[1] = 0;
          *((_DWORD *)v9 + 4) = v8;
          SetFileInformationByHandle(FileW, FileRenameInfo, v9, 2 * v8 + 24);
          CloseHandle(v17);
        }
      }
    }
  }
  LocalFree(v9);
  return LocalFree(v10);
}

```

## disassembly

```asm
0x180058334  mov     [rsp+arg_10], r8
0x180058339  push    rbx
0x18005833a  push    rbp
0x18005833b  push    rsi
0x18005833c  push    rdi
0x18005833d  push    r12
0x18005833f  push    r13
0x180058341  push    r14
0x180058343  push    r15
0x180058345  sub     rsp, 48h
0x180058349  mov     r14, rcx
0x18005834c  mov     r15b, r9b
0x18005834f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180058353  mov     edi, edx
0x180058355  mov     rax, rcx
0x180058358  xor     r13d, r13d
0x18005835b  inc     rax
0x18005835e  cmp     [r14+rax*2], r13w
0x180058363  jnz     short loc_18005835B
0x180058365  lea     r12d, [rax+13h]
0x180058369  mov     rbx, r13
0x18005836c  mov     ebp, r12d
0x18005836f  mov     eax, 2
0x180058374  mul     rbp
0x180058377  cmovb   rax, rcx
0x18005837b  mov     rcx, rax
0x18005837e  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180058383  mov     rsi, rax
0x180058386  test    rax, rax
0x180058389  jz      loc_1800584DE
0x18005838f  lea     rcx, ds:18h[r12*2]
0x180058397  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18005839c  mov     rbx, rax
0x18005839f  test    rax, rax
0x1800583a2  jz      loc_1800584DE
0x1800583a8  lea     r13, [rax+14h]
0x1800583ac  cmp     edi, 4
0x1800583af  jnz     short loc_1800583C1
0x1800583b1  lea     rax, aPerfh004Dat; "perfh004.dat"
0x1800583b8  lea     rdi, aPerfc004Dat; "perfc004.dat"
0x1800583bf  jmp     short loc_1800583CF
0x1800583c1  lea     rdi, FileName; "perfc016.dat"
0x1800583c8  lea     rax, aPerfh016Dat; "perfh016.dat"
0x1800583cf  test    r15b, r15b
0x1800583d2  lea     r8, aWsWs; "%ws\\%ws"
0x1800583d9  mov     r9, r14
0x1800583dc  mov     rdx, rbp; unsigned __int64
0x1800583df  cmovz   rdi, rax
0x1800583e3  mov     rcx, rsi; unsigned __int16 *
0x1800583e6  mov     [rsp+88h+pbCancel], rdi
0x1800583eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800583f0  mov     rcx, [rsp+88h+arg_10]
0x1800583f8  mov     r9, r14
0x1800583fb  test    rcx, rcx
0x1800583fe  jz      short loc_180058462
0x180058400  lea     rdx, aPrfh; "prfh"
0x180058407  test    r15b, r15b
0x18005840a  lea     rax, aPrfc; "prfc"
0x180058411  cmovz   rax, rdx
0x180058415  lea     r8, aWsWsWsWs; "%ws\\%ws%ws%ws"
0x18005841c  lea     rdx, aDat; ".dat"
0x180058423  mov     [rsp+88h+hTemplateFile], rdx
0x180058428  mov     rdx, rbp; unsigned __int64
0x18005842b  mov     qword ptr [rsp+88h+dwCopyFlags], rcx
0x180058430  mov     rcx, r13; unsigned __int16 *
0x180058433  mov     [rsp+88h+pbCancel], rax
0x180058438  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005843d  xor     r9d, r9d; lpData
0x180058440  mov     [rsp+88h+dwCopyFlags], 0; dwCopyFlags
0x180058448  xor     r8d, r8d; lpProgressRoutine
0x18005844b  mov     [rsp+88h+pbCancel], 0; pbCancel
0x180058454  mov     rdx, r13; lpNewFileName
0x180058457  mov     rcx, rsi; lpExistingFileName
0x18005845a  call    cs:__imp_CopyFileExW
0x180058460  jmp     short loc_1800584DE
0x180058462  lea     r8, aWsWsTmp; "%ws\\%ws.tmp"
0x180058469  mov     [rsp+88h+pbCancel], rdi
0x18005846e  mov     rdx, rbp; unsigned __int64
0x180058471  mov     rcx, r13; unsigned __int16 *
0x180058474  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058479  mov     rcx, r13; lpFileName
0x18005847c  call    cs:__imp_DeleteFileW
0x180058482  xor     ebp, ebp
0x180058484  xor     r9d, r9d; lpSecurityAttributes
0x180058487  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x18005848c  xor     r8d, r8d; dwShareMode
0x18005848f  mov     [rsp+88h+dwCopyFlags], ebp; dwFlagsAndAttributes
0x180058493  mov     edx, 40010000h; dwDesiredAccess
0x180058498  mov     rcx, rsi; lpFileName
0x18005849b  lea     r14d, [rbp+3]
0x18005849f  mov     dword ptr [rsp+88h+pbCancel], r14d; dwCreationDisposition
0x1800584a4  call    cs:__imp_CreateFileW
0x1800584aa  mov     rdi, rax
0x1800584ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800584b1  jz      short loc_1800584DE
0x1800584b3  lea     r9d, ds:18h[r12*2]; dwBufferSize
0x1800584bb  mov     [rbx], bpl
0x1800584be  mov     r8, rbx; lpFileInformation
0x1800584c1  mov     [rbx+8], rbp
0x1800584c5  mov     edx, r14d; FileInformationClass
0x1800584c8  mov     [rbx+10h], r12d
0x1800584cc  mov     rcx, rax; hFile
0x1800584cf  call    cs:__imp_SetFileInformationByHandle
0x1800584d5  mov     rcx, rdi; hObject
0x1800584d8  call    cs:__imp_CloseHandle
0x1800584de  mov     rcx, rbx; hMem
0x1800584e1  call    cs:__imp_LocalFree
0x1800584e7  mov     rcx, rsi
0x1800584ea  add     rsp, 48h
0x1800584ee  pop     r15
0x1800584f0  pop     r14
0x1800584f2  pop     r13
0x1800584f4  pop     r12
0x1800584f6  pop     rdi
0x1800584f7  pop     rsi
0x1800584f8  pop     rbp
0x1800584f9  pop     rbx
0x1800584fa  jmp     cs:__imp_LocalFree
```
