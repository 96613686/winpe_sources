# CodecUtil::GetSetLastWriteTime(IShellItem *,_FILETIME *,bool)

- ea: `0x1800313b8`
- end: `0x180031479`
- name: `?GetSetLastWriteTime@CodecUtil@@YAJPEAUIShellItem@@PEAU_FILETIME@@_N@Z`
- size: `193`
- prototype: `int(CodecUtil *__hidden this, struct IShellItem *, struct _FILETIME *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18003110c`

## callees

- `0x1800313b8`
- `0x180078e60`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x18003144a`
- `KERNEL32!GetFileTime` at `0x18003144a`
- `KERNEL32!SetFileTime` at `0x180031442`
- `KERNEL32!SetFileTime` at `0x180031442`
- `KERNEL32!CloseHandle` at `0x18003145c`
- `KERNEL32!CloseHandle` at `0x18003145c`
- `KERNEL32!CreateFileW` at `0x180031415`
- `KERNEL32!CreateFileW` at `0x180031415`
- `ole32!CoTaskMemFree` at `0x180031468`
- `ole32!CoTaskMemFree` at `0x180031468`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CodecUtil::GetSetLastWriteTime(CodecUtil *this, struct _FILETIME *a2, struct _FILETIME *a3)
{
  char v3; // bp
  int v5; // ebx
  char *FileW; // rdi
  BOOL FileTime; // eax
  LPCWSTR lpFileName; // [rsp+70h] [rbp+8h] BYREF

  v3 = (char)a3;
  lpFileName = 0;
  v5 = (*(__int64 (__fastcall **)(CodecUtil *, __int64, LPCWSTR *))(*(_QWORD *)this + 40LL))(
         this,
         2147647488LL,
         &lpFileName);
  if ( v5 >= 0 )
  {
    FileW = (char *)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    v5 = ResultFromWin32Bool(FileW + 1 != 0);
    if ( v5 >= 0 )
    {
      if ( v3 )
        FileTime = SetFileTime(FileW, 0, 0, a2);
      else
        FileTime = GetFileTime(FileW, 0, 0, a2);
      v5 = ResultFromWin32Bool(FileTime);
      CloseHandle(FileW);
    }
  }
  CoTaskMemFree((LPVOID)lpFileName);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800313b8  push    rbx
0x1800313ba  push    rbp
0x1800313bb  push    rsi
0x1800313bc  push    rdi
0x1800313bd  sub     rsp, 48h
0x1800313c1  mov     bpl, r8b
0x1800313c4  mov     rsi, rdx
0x1800313c7  mov     [rsp+68h+lpFileName], 0
0x1800313d0  mov     rax, [rcx]
0x1800313d3  lea     r8, [rsp+68h+lpFileName]
0x1800313d8  mov     edx, 80028000h
0x1800313dd  mov     rax, [rax+28h]
0x1800313e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313e6  mov     ebx, eax
0x1800313e8  test    eax, eax
0x1800313ea  js      short loc_180031463
0x1800313ec  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800313f5  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800313fd  mov     r8d, 3; dwShareMode
0x180031403  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x180031408  xor     r9d, r9d; lpSecurityAttributes
0x18003140b  mov     edx, 0C0000000h; dwDesiredAccess
0x180031410  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x180031415  call    cs:__imp_CreateFileW
0x18003141b  mov     rdi, rax
0x18003141e  xor     ecx, ecx
0x180031420  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031424  setnz   cl; int
0x180031427  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18003142c  mov     ebx, eax
0x18003142e  test    eax, eax
0x180031430  js      short loc_180031463
0x180031432  mov     r9, rsi; lpLastWriteTime
0x180031435  xor     r8d, r8d; lpLastAccessTime
0x180031438  xor     edx, edx; lpCreationTime
0x18003143a  mov     rcx, rdi; hFile
0x18003143d  test    bpl, bpl
0x180031440  jz      short loc_18003144A
0x180031442  call    cs:__imp_SetFileTime
0x180031448  jmp     short loc_180031450
0x18003144a  call    cs:__imp_GetFileTime
0x180031450  mov     ecx, eax; int
0x180031452  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180031457  mov     ebx, eax
0x180031459  mov     rcx, rdi; hObject
0x18003145c  call    cs:__imp_CloseHandle
0x180031462  nop
0x180031463  mov     rcx, [rsp+68h+lpFileName]; pv
0x180031468  call    cs:__imp_CoTaskMemFree
0x18003146e  mov     eax, ebx
0x180031470  add     rsp, 48h
0x180031474  pop     rdi
0x180031475  pop     rsi
0x180031476  pop     rbp
0x180031477  pop     rbx
0x180031478  retn
```
