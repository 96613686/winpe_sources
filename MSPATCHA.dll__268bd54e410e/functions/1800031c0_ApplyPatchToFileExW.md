# ApplyPatchToFileExW

- ea: `0x1800031c0`
- end: `0x18000330b`
- name: `ApplyPatchToFileExW`
- size: `331`
- prototype: `BOOL __stdcall(LPCWSTR PatchFileName, LPCWSTR OldFileName, LPCWSTR NewFileName, ULONG ApplyOptionFlags, PPATCH_PROGRESS_CALLBACK ProgressCallback, PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180003320`
- `0x180004910`

## callees

- `0x180002720`
- `0x1800031c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003213`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003246`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003287`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003213`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003246`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003287`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800032db`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800032db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032f2`

## pseudocode

```c
BOOL __stdcall ApplyPatchToFileExW(
        LPCWSTR PatchFileName,
        LPCWSTR OldFileName,
        LPCWSTR NewFileName,
        ULONG ApplyOptionFlags,
        PPATCH_PROGRESS_CALLBACK ProgressCallback,
        PVOID CallbackContext)
{
  __int64 FileW; // rbx
  BOOL v11; // ebp
  HANDLE v12; // r14
  __int64 v13; // rdi

  FileW = -1;
  if ( OldFileName )
  {
    FileW = (__int64)CreateFileW(OldFileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
    if ( FileW == -1 )
      return 0;
  }
  v11 = 0;
  v12 = CreateFileW(PatchFileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  if ( v12 != (HANDLE)-1LL )
  {
    v13 = -1;
    if ( (ApplyOptionFlags & 4) != 0
      || (v13 = (__int64)CreateFileW(NewFileName, 0xC0000000, 1u, 0, 2u, 0x80u, 0), v13 != -1) )
    {
      v11 = ApplyPatchToFileByHandlesEx(
              v12,
              (HANDLE)FileW,
              (HANDLE)v13,
              ApplyOptionFlags,
              ProgressCallback,
              CallbackContext);
      if ( v13 != -1 )
        CloseHandle((HANDLE)v13);
      if ( !v11 && (ApplyOptionFlags & 4) == 0 )
        DeleteFileW(NewFileName);
    }
    CloseHandle(v12);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v11;
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  push    rbp
0x1800031c3  push    rsi
0x1800031c4  push    rdi
0x1800031c5  push    r12
0x1800031c7  push    r13
0x1800031c9  push    r14
0x1800031cb  push    r15
0x1800031cd  sub     rsp, 48h
0x1800031d1  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800031d5  mov     r12d, r9d
0x1800031d8  mov     r15, r8
0x1800031db  mov     rax, rdx
0x1800031de  mov     rdi, rcx
0x1800031e1  mov     rbx, r13
0x1800031e4  mov     r14d, 8000000h
0x1800031ea  lea     esi, [r13+4]
0x1800031ee  test    rdx, rdx
0x1800031f1  jz      short loc_180003228
0x1800031f3  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800031fc  xor     r9d, r9d; lpSecurityAttributes
0x1800031ff  mov     [rsp+88h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180003204  mov     r8d, esi; dwShareMode
0x180003207  mov     edx, 80000000h; dwDesiredAccess
0x18000320c  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x180003210  mov     rcx, rax; lpFileName
0x180003213  call    cs:__imp_CreateFileW
0x180003219  mov     rbx, rax
0x18000321c  cmp     rax, r13
0x18000321f  jnz     short loc_180003228
0x180003221  xor     eax, eax
0x180003223  jmp     loc_1800032FA
0x180003228  xor     ebp, ebp
0x18000322a  xor     r9d, r9d; lpSecurityAttributes
0x18000322d  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x180003232  mov     r8d, esi; dwShareMode
0x180003235  mov     [rsp+88h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18000323a  mov     edx, 80000000h; dwDesiredAccess
0x18000323f  mov     rcx, rdi; lpFileName
0x180003242  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x180003246  call    cs:__imp_CreateFileW
0x18000324c  mov     r14, rax
0x18000324f  cmp     rax, r13
0x180003252  jz      loc_1800032EA
0x180003258  mov     esi, r12d
0x18000325b  mov     rdi, r13
0x18000325e  and     esi, 4
0x180003261  jnz     short loc_180003295
0x180003263  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x180003268  lea     r8d, [rbp+1]; dwShareMode
0x18000326c  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003274  xor     r9d, r9d; lpSecurityAttributes
0x180003277  mov     edx, 0C0000000h; dwDesiredAccess
0x18000327c  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x180003284  mov     rcx, r15; lpFileName
0x180003287  call    cs:__imp_CreateFileW
0x18000328d  mov     rdi, rax
0x180003290  cmp     rax, r13
0x180003293  jz      short loc_1800032E1
0x180003295  mov     rcx, [rsp+88h+CallbackContext]
0x18000329d  mov     r9d, r12d; ApplyOptionFlags
0x1800032a0  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rcx; CallbackContext
0x1800032a5  mov     r8, rdi; NewFileHandle
0x1800032a8  mov     rcx, [rsp+88h+ProgressCallback]
0x1800032b0  mov     rdx, rbx; OldFileHandle
0x1800032b3  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx; ProgressCallback
0x1800032b8  mov     rcx, r14; PatchFileHandle
0x1800032bb  call    ApplyPatchToFileByHandlesEx
0x1800032c0  mov     ebp, eax
0x1800032c2  cmp     rdi, r13
0x1800032c5  jz      short loc_1800032D0
0x1800032c7  mov     rcx, rdi; hObject
0x1800032ca  call    cs:__imp_CloseHandle
0x1800032d0  test    ebp, ebp
0x1800032d2  jnz     short loc_1800032E1
0x1800032d4  test    esi, esi
0x1800032d6  jnz     short loc_1800032E1
0x1800032d8  mov     rcx, r15; lpFileName
0x1800032db  call    cs:__imp_DeleteFileW
0x1800032e1  mov     rcx, r14; hObject
0x1800032e4  call    cs:__imp_CloseHandle
0x1800032ea  cmp     rbx, r13
0x1800032ed  jz      short loc_1800032F8
0x1800032ef  mov     rcx, rbx; hObject
0x1800032f2  call    cs:__imp_CloseHandle
0x1800032f8  mov     eax, ebp
0x1800032fa  add     rsp, 48h
0x1800032fe  pop     r15
0x180003300  pop     r14
0x180003302  pop     r13
0x180003304  pop     r12
0x180003306  pop     rdi
0x180003307  pop     rsi
0x180003308  pop     rbp
0x180003309  pop     rbx
0x18000330a  retn
```
