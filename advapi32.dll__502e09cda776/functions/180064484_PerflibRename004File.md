# PerflibRename004File

- ea: `0x180064484`
- end: `0x18006467d`
- name: `PerflibRename004File`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800016f4`

## callees

- `0x1800028d8`
- `0x180002e40`
- `0x180064484`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180064652`
- `KERNEL32!LocalFree` at `0x180064652`
- `KERNEL32!LocalFree` at `0x180064671`
- `KERNEL32!CloseHandle` at `0x180064643`
- `KERNEL32!CloseHandle` at `0x180064643`
- `KERNEL32!CreateFileW` at `0x180064603`
- `KERNEL32!CreateFileW` at `0x180064603`
- `KERNEL32!DeleteFileW` at `0x1800645d5`
- `KERNEL32!DeleteFileW` at `0x1800645d5`
- `KERNEL32!SetFileInformationByHandle` at `0x180064634`
- `KERNEL32!SetFileInformationByHandle` at `0x180064634`
- `KERNEL32!CopyFileExW` at `0x1800645aa`
- `KERNEL32!CopyFileExW` at `0x1800645aa`

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
0x180064484  mov     [rsp+arg_10], r8
0x180064489  push    rbx
0x18006448a  push    rbp
0x18006448b  push    rsi
0x18006448c  push    rdi
0x18006448d  push    r12
0x18006448f  push    r13
0x180064491  push    r14
0x180064493  push    r15
0x180064495  sub     rsp, 48h
0x180064499  mov     r14, rcx
0x18006449c  mov     r15b, r9b
0x18006449f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800644a3  mov     edi, edx
0x1800644a5  mov     rax, rcx
0x1800644a8  xor     r13d, r13d
0x1800644ab  inc     rax
0x1800644ae  cmp     [r14+rax*2], r13w
0x1800644b3  jnz     short loc_1800644AB
0x1800644b5  lea     r12d, [rax+13h]
0x1800644b9  mov     rbx, r13
0x1800644bc  mov     ebp, r12d
0x1800644bf  mov     eax, 2
0x1800644c4  mul     rbp
0x1800644c7  cmovb   rax, rcx
0x1800644cb  mov     rcx, rax
0x1800644ce  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800644d3  mov     rsi, rax
0x1800644d6  test    rax, rax
0x1800644d9  jz      loc_18006464F
0x1800644df  lea     rcx, ds:18h[r12*2]
0x1800644e7  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800644ec  mov     rbx, rax
0x1800644ef  test    rax, rax
0x1800644f2  jz      loc_18006464F
0x1800644f8  lea     r13, [rax+14h]
0x1800644fc  cmp     edi, 4
0x1800644ff  jnz     short loc_180064511
0x180064501  lea     rax, aPerfh004Dat; "perfh004.dat"
0x180064508  lea     rdi, aPerfc004Dat; "perfc004.dat"
0x18006450f  jmp     short loc_18006451F
0x180064511  lea     rdi, FileName; "perfc016.dat"
0x180064518  lea     rax, aPerfh016Dat; "perfh016.dat"
0x18006451f  test    r15b, r15b
0x180064522  lea     r8, aWsWs; "%ws\\%ws"
0x180064529  mov     r9, r14
0x18006452c  mov     rdx, rbp; unsigned __int64
0x18006452f  cmovz   rdi, rax
0x180064533  mov     rcx, rsi; unsigned __int16 *
0x180064536  mov     [rsp+88h+pbCancel], rdi
0x18006453b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064540  mov     rcx, [rsp+88h+arg_10]
0x180064548  mov     r9, r14
0x18006454b  test    rcx, rcx
0x18006454e  jz      short loc_1800645BB
0x180064550  lea     rdx, aPrfh; "prfh"
0x180064557  test    r15b, r15b
0x18006455a  lea     rax, aPrfc; "prfc"
0x180064561  cmovz   rax, rdx
0x180064565  lea     r8, aWsWsWsWs; "%ws\\%ws%ws%ws"
0x18006456c  lea     rdx, aDat; ".dat"
0x180064573  mov     [rsp+88h+hTemplateFile], rdx
0x180064578  mov     rdx, rbp; unsigned __int64
0x18006457b  mov     qword ptr [rsp+88h+dwCopyFlags], rcx
0x180064580  mov     rcx, r13; unsigned __int16 *
0x180064583  mov     [rsp+88h+pbCancel], rax
0x180064588  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006458d  xor     r9d, r9d; lpData
0x180064590  mov     [rsp+88h+dwCopyFlags], 0; dwCopyFlags
0x180064598  xor     r8d, r8d; lpProgressRoutine
0x18006459b  mov     [rsp+88h+pbCancel], 0; pbCancel
0x1800645a4  mov     rdx, r13; lpNewFileName
0x1800645a7  mov     rcx, rsi; lpExistingFileName
0x1800645aa  call    cs:__imp_CopyFileExW
0x1800645b1  nop     dword ptr [rax+rax+00h]
0x1800645b6  jmp     loc_18006464F
0x1800645bb  lea     r8, aWsWsTmp; "%ws\\%ws.tmp"
0x1800645c2  mov     [rsp+88h+pbCancel], rdi
0x1800645c7  mov     rdx, rbp; unsigned __int64
0x1800645ca  mov     rcx, r13; unsigned __int16 *
0x1800645cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800645d2  mov     rcx, r13; lpFileName
0x1800645d5  call    cs:__imp_DeleteFileW
0x1800645dc  nop     dword ptr [rax+rax+00h]
0x1800645e1  xor     ebp, ebp
0x1800645e3  xor     r9d, r9d; lpSecurityAttributes
0x1800645e6  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x1800645eb  xor     r8d, r8d; dwShareMode
0x1800645ee  mov     [rsp+88h+dwCopyFlags], ebp; dwFlagsAndAttributes
0x1800645f2  mov     edx, 40010000h; dwDesiredAccess
0x1800645f7  mov     rcx, rsi; lpFileName
0x1800645fa  lea     r14d, [rbp+3]
0x1800645fe  mov     dword ptr [rsp+88h+pbCancel], r14d; dwCreationDisposition
0x180064603  call    cs:__imp_CreateFileW
0x18006460a  nop     dword ptr [rax+rax+00h]
0x18006460f  mov     rdi, rax
0x180064612  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064616  jz      short loc_18006464F
0x180064618  lea     r9d, ds:18h[r12*2]; dwBufferSize
0x180064620  mov     [rbx], bpl
0x180064623  mov     r8, rbx; lpFileInformation
0x180064626  mov     [rbx+8], rbp
0x18006462a  mov     edx, r14d; FileInformationClass
0x18006462d  mov     [rbx+10h], r12d
0x180064631  mov     rcx, rax; hFile
0x180064634  call    cs:__imp_SetFileInformationByHandle
0x18006463b  nop     dword ptr [rax+rax+00h]
0x180064640  mov     rcx, rdi; hObject
0x180064643  call    cs:__imp_CloseHandle
0x18006464a  nop     dword ptr [rax+rax+00h]
0x18006464f  mov     rcx, rbx; hMem
0x180064652  call    cs:__imp_LocalFree
0x180064659  nop     dword ptr [rax+rax+00h]
0x18006465e  mov     rcx, rsi
0x180064661  add     rsp, 48h
0x180064665  pop     r15
0x180064667  pop     r14
0x180064669  pop     r13
0x18006466b  pop     r12
0x18006466d  pop     rdi
0x18006466e  pop     rsi
0x18006466f  pop     rbp
0x180064670  pop     rbx
0x180064671  jmp     cs:__imp_LocalFree
```
