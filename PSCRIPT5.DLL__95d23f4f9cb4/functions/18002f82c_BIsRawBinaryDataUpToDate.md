# BIsRawBinaryDataUpToDate

- ea: `0x18002f82c`
- end: `0x18002f903`
- name: `BIsRawBinaryDataUpToDate`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180054dec`

## callees

- `0x18002f82c`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x18002f8bd`
- `KERNEL32!GetFileTime` at `0x18002f8bd`
- `KERNEL32!CompareFileTime` at `0x18002f8d7`
- `KERNEL32!CompareFileTime` at `0x18002f8d7`
- `KERNEL32!CreateFileW` at `0x18002f89e`
- `KERNEL32!CreateFileW` at `0x18002f89e`
- `KERNEL32!CloseHandle` at `0x18002f8e6`
- `KERNEL32!CloseHandle` at `0x18002f8e6`

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
0x18002f82c  mov     rax, rsp
0x18002f82f  push    rbx
0x18002f830  push    rbp
0x18002f831  push    rsi
0x18002f832  push    rdi
0x18002f833  push    r14
0x18002f835  push    r15
0x18002f837  sub     rsp, 48h
0x18002f83b  cmp     dword ptr [rcx+20h], 0
0x18002f83f  mov     rsi, rcx
0x18002f842  mov     qword ptr [rax+8], 0
0x18002f84a  mov     ebp, 1
0x18002f84f  jz      short loc_18002F859
0x18002f851  mov     edi, [rcx+20h]
0x18002f854  add     rdi, rcx
0x18002f857  jmp     short loc_18002F85B
0x18002f859  xor     edi, edi
0x18002f85b  mov     ebx, [rcx+1Ch]
0x18002f85e  jmp     loc_18002F8EC
0x18002f863  dec     ebx
0x18002f865  lea     r15, [rbx+rbx*2]
0x18002f869  cmp     dword ptr [rdi+r15*4], 0
0x18002f86e  jz      short loc_18002F879
0x18002f870  mov     ecx, [rdi+r15*4]
0x18002f874  add     rcx, rsi
0x18002f877  jmp     short loc_18002F87B
0x18002f879  xor     ecx, ecx; lpFileName
0x18002f87b  xor     ebp, ebp
0x18002f87d  xor     r9d, r9d; lpSecurityAttributes
0x18002f880  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x18002f885  mov     edx, 80000000h; dwDesiredAccess
0x18002f88a  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18002f892  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f89a  lea     r8d, [rbp+1]; dwShareMode
0x18002f89e  call    cs:__imp_CreateFileW
0x18002f8a4  mov     r14, rax
0x18002f8a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f8ab  jz      short loc_18002F8EC
0x18002f8ad  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x18002f8b5  xor     r8d, r8d; lpLastAccessTime
0x18002f8b8  xor     edx, edx; lpCreationTime
0x18002f8ba  mov     rcx, rax; hFile
0x18002f8bd  call    cs:__imp_GetFileTime
0x18002f8c3  test    eax, eax
0x18002f8c5  jz      short loc_18002F8E3
0x18002f8c7  lea     rdx, [r15+1]
0x18002f8cb  lea     rdx, [rdi+rdx*4]; lpFileTime2
0x18002f8cf  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x18002f8d7  call    cs:__imp_CompareFileTime
0x18002f8dd  test    eax, eax
0x18002f8df  setz    bpl
0x18002f8e3  mov     rcx, r14; hObject
0x18002f8e6  call    cs:__imp_CloseHandle
0x18002f8ec  test    ebx, ebx
0x18002f8ee  jnz     loc_18002F863
0x18002f8f4  mov     eax, ebp
0x18002f8f6  add     rsp, 48h
0x18002f8fa  pop     r15
0x18002f8fc  pop     r14
0x18002f8fe  pop     rdi
0x18002f8ff  pop     rsi
0x18002f900  pop     rbp
0x18002f901  pop     rbx
0x18002f902  retn
```
