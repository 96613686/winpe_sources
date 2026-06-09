# BIsRawBinaryDataUpToDate

- ea: `0x180030d54`
- end: `0x180030e44`
- name: `BIsRawBinaryDataUpToDate`
- size: `240`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800567ec`

## callees

- `0x180030d54`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x180030deb`
- `KERNEL32!GetFileTime` at `0x180030deb`
- `KERNEL32!CompareFileTime` at `0x180030e0b`
- `KERNEL32!CompareFileTime` at `0x180030e0b`
- `KERNEL32!CreateFileW` at `0x180030dc6`
- `KERNEL32!CreateFileW` at `0x180030dc6`
- `KERNEL32!CloseHandle` at `0x180030e20`
- `KERNEL32!CloseHandle` at `0x180030e20`

## pseudocode

```c
__int64 __fastcall BIsRawBinaryDataUpToDate(__int64 a1)
{
  bool v1; // zf
  unsigned int v3; // ebp
  __int64 v4; // rdi
  __int64 v5; // rbx
  const WCHAR *v6; // rcx
  HANDLE FileW; // rax
  void *v8; // r14
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 32) == 0;
  LastWriteTime = 0;
  v3 = 1;
  if ( v1 )
    v4 = 0;
  else
    v4 = a1 + *(unsigned int *)(a1 + 32);
  LODWORD(v5) = *(_DWORD *)(a1 + 28);
  while ( (_DWORD)v5 )
  {
    v5 = (unsigned int)(v5 - 1);
    if ( *(_DWORD *)(v4 + 12 * v5) )
      v6 = (const WCHAR *)(a1 + *(unsigned int *)(v4 + 12 * v5));
    else
      v6 = 0;
    v3 = 0;
    FileW = CreateFileW(v6, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v8 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
        LOBYTE(v3) = CompareFileTime(&LastWriteTime, (const FILETIME *)(v4 + 4 * (3 * v5 + 1))) == 0;
      CloseHandle(v8);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180030d54  mov     rax, rsp
0x180030d57  push    rbx
0x180030d58  push    rbp
0x180030d59  push    rsi
0x180030d5a  push    rdi
0x180030d5b  push    r14
0x180030d5d  push    r15
0x180030d5f  sub     rsp, 48h
0x180030d63  cmp     dword ptr [rcx+20h], 0
0x180030d67  mov     rsi, rcx
0x180030d6a  mov     qword ptr [rax+8], 0
0x180030d72  mov     ebp, 1
0x180030d77  jz      short loc_180030D81
0x180030d79  mov     edi, [rcx+20h]
0x180030d7c  add     rdi, rcx
0x180030d7f  jmp     short loc_180030D83
0x180030d81  xor     edi, edi
0x180030d83  mov     ebx, [rcx+1Ch]
0x180030d86  jmp     loc_180030E2C
0x180030d8b  dec     ebx
0x180030d8d  lea     r15, [rbx+rbx*2]
0x180030d91  cmp     dword ptr [rdi+r15*4], 0
0x180030d96  jz      short loc_180030DA1
0x180030d98  mov     ecx, [rdi+r15*4]
0x180030d9c  add     rcx, rsi
0x180030d9f  jmp     short loc_180030DA3
0x180030da1  xor     ecx, ecx; lpFileName
0x180030da3  xor     ebp, ebp
0x180030da5  xor     r9d, r9d; lpSecurityAttributes
0x180030da8  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x180030dad  mov     edx, 80000000h; dwDesiredAccess
0x180030db2  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180030dba  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180030dc2  lea     r8d, [rbp+1]; dwShareMode
0x180030dc6  call    cs:__imp_CreateFileW
0x180030dcd  nop     dword ptr [rax+rax+00h]
0x180030dd2  mov     r14, rax
0x180030dd5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030dd9  jz      short loc_180030E2C
0x180030ddb  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x180030de3  xor     r8d, r8d; lpLastAccessTime
0x180030de6  xor     edx, edx; lpCreationTime
0x180030de8  mov     rcx, rax; hFile
0x180030deb  call    cs:__imp_GetFileTime
0x180030df2  nop     dword ptr [rax+rax+00h]
0x180030df7  test    eax, eax
0x180030df9  jz      short loc_180030E1D
0x180030dfb  lea     rdx, [r15+1]
0x180030dff  lea     rdx, [rdi+rdx*4]; lpFileTime2
0x180030e03  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x180030e0b  call    cs:__imp_CompareFileTime
0x180030e12  nop     dword ptr [rax+rax+00h]
0x180030e17  test    eax, eax
0x180030e19  setz    bpl
0x180030e1d  mov     rcx, r14; hObject
0x180030e20  call    cs:__imp_CloseHandle
0x180030e27  nop     dword ptr [rax+rax+00h]
0x180030e2c  test    ebx, ebx
0x180030e2e  jnz     loc_180030D8B
0x180030e34  mov     eax, ebp
0x180030e36  add     rsp, 48h
0x180030e3a  pop     r15
0x180030e3c  pop     r14
0x180030e3e  pop     rdi
0x180030e3f  pop     rsi
0x180030e40  pop     rbp
0x180030e41  pop     rbx
0x180030e42  retn
```
