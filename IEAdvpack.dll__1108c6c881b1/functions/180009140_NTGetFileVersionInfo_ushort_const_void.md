# NTGetFileVersionInfo(ushort const *,void * *)

- ea: `0x180009140`
- end: `0x180009316`
- name: `?NTGetFileVersionInfo@@YAHPEBGPEAPEAX@Z`
- size: `470`
- prototype: `__int64 __fastcall(LPCWSTR lptstrFilename, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b630`

## callees

- `0x180009140`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800092b4`
- `msvcrt!memcpy_s` at `0x1800092b4`
- `KERNEL32!GetLastError` at `0x180009229`
- `KERNEL32!GetLastError` at `0x180009229`
- `KERNEL32!LocalFree` at `0x1800092cb`
- `KERNEL32!LocalFree` at `0x1800092cb`
- `KERNEL32!FindResourceW` at `0x180009209`
- `KERNEL32!FindResourceW` at `0x180009209`
- `KERNEL32!LoadResource` at `0x180009277`
- `KERNEL32!LoadResource` at `0x180009277`
- `KERNEL32!CreateFileW` at `0x180009196`
- `KERNEL32!CreateFileW` at `0x180009196`
- `KERNEL32!CloseHandle` at `0x1800092e7`
- `KERNEL32!CloseHandle` at `0x1800092f5`
- `KERNEL32!CloseHandle` at `0x1800092e7`
- `KERNEL32!CloseHandle` at `0x1800092f5`
- `KERNEL32!LocalAlloc` at `0x18000924c`
- `KERNEL32!LocalAlloc` at `0x180009293`
- `KERNEL32!LocalAlloc` at `0x18000924c`
- `KERNEL32!LocalAlloc` at `0x180009293`
- `KERNEL32!CreateFileMappingW` at `0x1800091be`
- `KERNEL32!CreateFileMappingW` at `0x1800091be`
- `KERNEL32!MapViewOfFileEx` at `0x1800091e6`
- `KERNEL32!MapViewOfFileEx` at `0x1800091e6`
- `KERNEL32!SetLastError` at `0x18000923c`
- `KERNEL32!SetLastError` at `0x18000923c`
- `KERNEL32!UnmapViewOfFile` at `0x1800092d9`
- `KERNEL32!UnmapViewOfFile` at `0x1800092d9`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000921c`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000921c`
- `VERSION!GetFileVersionInfoW` at `0x180009265`
- `VERSION!GetFileVersionInfoW` at `0x180009265`

## pseudocode

```c
__int64 __fastcall NTGetFileVersionInfo(LPCWSTR lptstrFilename, void **a2)
{
  const void *v5; // rsi
  void *v6; // rdi
  unsigned int v7; // ebp
  HANDLE FileW; // rax
  void *v9; // r14
  HANDLE FileMappingW; // rax
  unsigned __int64 v11; // rax
  HMODULE v12; // r15
  HRSRC ResourceW; // rax
  DWORD FileVersionInfoSizeW; // eax
  DWORD v15; // r15d
  HLOCAL v16; // rax
  unsigned __int16 *Resource; // rax
  unsigned __int16 *v18; // r15
  HLOCAL v19; // rax
  DWORD dwHandle; // [rsp+78h] [rbp+10h] BYREF

  dwHandle = 0;
  if ( !a2 )
    return 0;
  v5 = 0;
  v6 = 0;
  *a2 = 0;
  v7 = 0;
  FileW = CreateFileW(lptstrFilename, 0x80000000, 1u, 0, 3u, 0, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v6 = FileMappingW;
    if ( FileMappingW )
    {
      v11 = (unsigned __int64)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
      v5 = (const void *)v11;
      if ( v11 )
      {
        v12 = (HMODULE)(v11 | 1);
        ResourceW = FindResourceW((HMODULE)(v11 | 1), (LPCWSTR)1, (LPCWSTR)0x10);
        if ( ResourceW )
        {
          Resource = (unsigned __int16 *)LoadResource(v12, ResourceW);
          v18 = Resource;
          if ( !Resource )
            goto LABEL_17;
          v19 = LocalAlloc(0x40u, *Resource + (*Resource >> 1));
          *a2 = v19;
          if ( !v19 )
            goto LABEL_17;
          memcpy_s(v19, (*v18 >> 1) + (unsigned int)*v18, v18, *v18);
          goto LABEL_16;
        }
        FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
        v15 = FileVersionInfoSizeW;
        if ( !FileVersionInfoSizeW )
        {
          if ( !GetLastError() )
            SetLastError(0x714u);
          goto LABEL_17;
        }
        v16 = LocalAlloc(0x40u, FileVersionInfoSizeW);
        *a2 = v16;
        if ( v16 && GetFileVersionInfoW(lptstrFilename, 0, v15, v16) )
LABEL_16:
          v7 = 1;
      }
    }
  }
LABEL_17:
  if ( *a2 && !v7 )
    LocalFree(*a2);
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( v6 )
    CloseHandle(v6);
  if ( v9 )
    CloseHandle(v9);
  return v7;
}

```

## disassembly

```asm
0x180009140  mov     [rsp+arg_0], rbx
0x180009145  mov     [rsp+arg_10], rbp
0x18000914a  push    rsi
0x18000914b  push    rdi
0x18000914c  push    r12
0x18000914e  push    r14
0x180009150  push    r15
0x180009152  sub     rsp, 40h
0x180009156  mov     [rsp+68h+dwHandle], 0
0x18000915e  mov     rbx, rdx
0x180009161  mov     r12, rcx
0x180009164  test    rdx, rdx
0x180009167  jnz     short loc_180009170
0x180009169  xor     eax, eax
0x18000916b  jmp     loc_1800092FD
0x180009170  xor     esi, esi
0x180009172  xor     edi, edi
0x180009174  mov     [rdx], rsi
0x180009177  xor     r9d, r9d; lpSecurityAttributes
0x18000917a  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x18000917f  mov     edx, 80000000h; dwDesiredAccess
0x180009184  mov     [rsp+68h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180009188  xor     ebp, ebp
0x18000918a  lea     r8d, [rdi+1]; dwShareMode
0x18000918e  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180009196  call    cs:__imp_CreateFileW
0x18000919c  mov     r14, rax
0x18000919f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800091a3  jz      loc_1800092BF
0x1800091a9  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; lpName
0x1800091ae  lea     r8d, [rdi+2]; flProtect
0x1800091b2  xor     r9d, r9d; dwMaximumSizeHigh
0x1800091b5  mov     [rsp+68h+dwCreationDisposition], esi; dwMaximumSizeLow
0x1800091b9  xor     edx, edx; lpFileMappingAttributes
0x1800091bb  mov     rcx, rax; hFile
0x1800091be  call    cs:__imp_CreateFileMappingW
0x1800091c4  mov     rdi, rax
0x1800091c7  test    rax, rax
0x1800091ca  jz      loc_1800092BF
0x1800091d0  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; lpBaseAddress
0x1800091d5  lea     edx, [rsi+4]; dwDesiredAccess
0x1800091d8  xor     r9d, r9d; dwFileOffsetLow
0x1800091db  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x1800091e0  xor     r8d, r8d; dwFileOffsetHigh
0x1800091e3  mov     rcx, rax; hFileMappingObject
0x1800091e6  call    cs:__imp_MapViewOfFileEx
0x1800091ec  mov     rsi, rax
0x1800091ef  test    rax, rax
0x1800091f2  jz      loc_1800092BF
0x1800091f8  mov     r15, rax
0x1800091fb  lea     edx, [rbp+1]; lpName
0x1800091fe  or      r15, 1
0x180009202  lea     r8d, [rbp+10h]; lpType
0x180009206  mov     rcx, r15; hModule
0x180009209  call    cs:__imp_FindResourceW
0x18000920f  test    rax, rax
0x180009212  jnz     short loc_180009271
0x180009214  lea     rdx, [rsp+68h+dwHandle]; lpdwHandle
0x180009219  mov     rcx, r12; lptstrFilename
0x18000921c  call    cs:__imp_GetFileVersionInfoSizeW
0x180009222  mov     r15d, eax
0x180009225  test    eax, eax
0x180009227  jnz     short loc_180009244
0x180009229  call    cs:__imp_GetLastError
0x18000922f  test    eax, eax
0x180009231  jnz     loc_1800092BF
0x180009237  mov     ecx, 714h; dwErrCode
0x18000923c  call    cs:__imp_SetLastError
0x180009242  jmp     short loc_1800092BF
0x180009244  mov     rdx, r15; uBytes
0x180009247  mov     ecx, 40h ; '@'; uFlags
0x18000924c  call    cs:__imp_LocalAlloc
0x180009252  mov     [rbx], rax
0x180009255  test    rax, rax
0x180009258  jz      short loc_1800092BF
0x18000925a  mov     r9, rax; lpData
0x18000925d  mov     r8d, r15d; dwLen
0x180009260  xor     edx, edx; dwHandle
0x180009262  mov     rcx, r12; lptstrFilename
0x180009265  call    cs:__imp_GetFileVersionInfoW
0x18000926b  test    eax, eax
0x18000926d  jz      short loc_1800092BF
0x18000926f  jmp     short loc_1800092BA
0x180009271  mov     rdx, rax; hResInfo
0x180009274  mov     rcx, r15; hModule
0x180009277  call    cs:__imp_LoadResource
0x18000927d  mov     r15, rax
0x180009280  test    rax, rax
0x180009283  jz      short loc_1800092BF
0x180009285  movzx   ecx, word ptr [rax]
0x180009288  mov     edx, ecx
0x18000928a  shr     edx, 1
0x18000928c  add     edx, ecx; uBytes
0x18000928e  mov     ecx, 40h ; '@'; uFlags
0x180009293  call    cs:__imp_LocalAlloc
0x180009299  mov     [rbx], rax
0x18000929c  test    rax, rax
0x18000929f  jz      short loc_1800092BF
0x1800092a1  movzx   edx, word ptr [r15]
0x1800092a5  mov     r8, r15; Source
0x1800092a8  mov     ecx, edx
0x1800092aa  mov     r9d, edx; SourceSize
0x1800092ad  shr     ecx, 1
0x1800092af  add     edx, ecx; DestinationSize
0x1800092b1  mov     rcx, rax; Destination
0x1800092b4  call    cs:__imp_memcpy_s
0x1800092ba  mov     ebp, 1
0x1800092bf  mov     rcx, [rbx]; hMem
0x1800092c2  test    rcx, rcx
0x1800092c5  jz      short loc_1800092D1
0x1800092c7  test    ebp, ebp
0x1800092c9  jnz     short loc_1800092D1
0x1800092cb  call    cs:__imp_LocalFree
0x1800092d1  test    rsi, rsi
0x1800092d4  jz      short loc_1800092DF
0x1800092d6  mov     rcx, rsi; lpBaseAddress
0x1800092d9  call    cs:__imp_UnmapViewOfFile
0x1800092df  test    rdi, rdi
0x1800092e2  jz      short loc_1800092ED
0x1800092e4  mov     rcx, rdi; hObject
0x1800092e7  call    cs:__imp_CloseHandle
0x1800092ed  test    r14, r14
0x1800092f0  jz      short loc_1800092FB
0x1800092f2  mov     rcx, r14; hObject
0x1800092f5  call    cs:__imp_CloseHandle
0x1800092fb  mov     eax, ebp
0x1800092fd  lea     r11, [rsp+68h+var_28]
0x180009302  mov     rbx, [r11+30h]
0x180009306  mov     rbp, [r11+40h]
0x18000930a  mov     rsp, r11
0x18000930d  pop     r15
0x18000930f  pop     r14
0x180009311  pop     r12
0x180009313  pop     rdi
0x180009314  pop     rsi
0x180009315  retn
```
