# CVBAExeFile::Write(char const *)

- ea: `0x1801ac458`
- end: `0x1801ac634`
- name: `?Write@CVBAExeFile@@QEAAHPEBD@Z`
- size: `476`
- prototype: `__int64 __fastcall(CVBAExeFile *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800e702c`

## callees

- `0x180174e14`
- `0x180174ff8`
- `0x1801ac458`
- `0x1801ada60`
- `0x1801af6e0`
- `0x1801af8f0`
- `0x1801b009c`

## import_xrefs

- `KERNEL32!CreateFileMappingA` at `0x1801ac528`
- `KERNEL32!CreateFileMappingA` at `0x1801ac528`
- `KERNEL32!SetEndOfFile` at `0x1801ac5f8`
- `KERNEL32!SetEndOfFile` at `0x1801ac5f8`
- `KERNEL32!GetLastError` at `0x1801ac4e5`
- `KERNEL32!GetLastError` at `0x1801ac53b`
- `KERNEL32!GetLastError` at `0x1801ac4e5`
- `KERNEL32!GetLastError` at `0x1801ac53b`
- `KERNEL32!DeleteFileA` at `0x1801ac614`
- `KERNEL32!DeleteFileA` at `0x1801ac614`
- `KERNEL32!CloseHandle` at `0x1801ac58e`
- `KERNEL32!CloseHandle` at `0x1801ac5d1`
- `KERNEL32!CloseHandle` at `0x1801ac603`
- `KERNEL32!CloseHandle` at `0x1801ac58e`
- `KERNEL32!CloseHandle` at `0x1801ac5d1`
- `KERNEL32!CloseHandle` at `0x1801ac603`
- `KERNEL32!CreateFileA` at `0x1801ac4d2`
- `KERNEL32!CreateFileA` at `0x1801ac4d2`
- `KERNEL32!MapViewOfFile` at `0x1801ac576`
- `KERNEL32!MapViewOfFile` at `0x1801ac576`
- `KERNEL32!UnmapViewOfFile` at `0x1801ac5c6`
- `KERNEL32!UnmapViewOfFile` at `0x1801ac5c6`
- `KERNEL32!SetFilePointer` at `0x1801ac5ed`
- `KERNEL32!SetFilePointer` at `0x1801ac5ed`

## pseudocode

```c
__int64 __fastcall CVBAExeFile::Write(CVBAExeFile *this, const char *a2)
{
  DWORD LastError; // eax
  unsigned int v4; // eax
  unsigned int v5; // [rsp+40h] [rbp-30h]
  unsigned int v6; // [rsp+40h] [rbp-30h]
  unsigned int dwMaximumSizeLow; // [rsp+44h] [rbp-2Ch]
  LONG lDistanceToMove; // [rsp+48h] [rbp-28h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-20h]
  HANDLE hFileMappingObject; // [rsp+58h] [rbp-18h]
  LPCVOID lpBaseAddress; // [rsp+60h] [rbp-10h]

  CVBAExeFile::SizeExeParts(this);
  v5 = CVBAExeFile::IdentifyFixupTargets(this);
  if ( v5 )
  {
    *((_DWORD *)this + 6) = v5;
    return 0;
  }
  else
  {
    dwMaximumSizeLow = CVBAExeFile::CalcMaxSize(this, a2);
    hFile = CreateFileA(a2, 0xC0000000, 0, 0, 2u, 0, 0);
    if ( hFile == (HANDLE)-1LL || (hFileMappingObject = CreateFileMappingA(hFile, 0, 4u, 0, dwMaximumSizeLow, 0)) == 0 )
    {
      LastError = GetLastError();
      v4 = TiperrOfOFErr(LastError);
      *((_DWORD *)this + 6) = EberrOfHresult(v4);
      return 0;
    }
    else
    {
      lpBaseAddress = MapViewOfFile(hFileMappingObject, 2u, 0, 0, dwMaximumSizeLow);
      if ( lpBaseAddress )
      {
        v6 = CVBAExeFile::WriteExe(this, a2, (unsigned __int8 *)lpBaseAddress, (unsigned int *)&lDistanceToMove);
        UnmapViewOfFile(lpBaseAddress);
        CloseHandle(hFileMappingObject);
        if ( !v6 )
        {
          SetFilePointer(hFile, lDistanceToMove, 0, 0);
          SetEndOfFile(hFile);
        }
        CloseHandle(hFile);
        if ( v6 )
        {
          DeleteFileA(a2);
          *((_DWORD *)this + 6) = v6;
          return 0;
        }
        else
        {
          return 1;
        }
      }
      else
      {
        CloseHandle(hFileMappingObject);
        *((_DWORD *)this + 6) = 7;
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1801ac458  mov     [rsp-8+lpFileName], rdx
0x1801ac45d  mov     [rsp-8+arg_0], rcx
0x1801ac462  push    rbp
0x1801ac463  mov     rbp, rsp
0x1801ac466  sub     rsp, 70h
0x1801ac46a  mov     rcx, [rbp+arg_0]; this
0x1801ac46e  call    ?SizeExeParts@CVBAExeFile@@AEAAXXZ; CVBAExeFile::SizeExeParts(void)
0x1801ac473  mov     rcx, [rbp+arg_0]; this
0x1801ac477  call    ?IdentifyFixupTargets@CVBAExeFile@@AEAAIXZ; CVBAExeFile::IdentifyFixupTargets(void)
0x1801ac47c  mov     [rsp+70h+var_30], eax
0x1801ac480  cmp     [rsp+70h+var_30], 0
0x1801ac485  jz      short loc_1801AC499
0x1801ac487  mov     rax, [rbp+arg_0]
0x1801ac48b  mov     ecx, [rsp+70h+var_30]
0x1801ac48f  mov     [rax+18h], ecx
0x1801ac492  xor     eax, eax
0x1801ac494  jmp     loc_1801AC62E
0x1801ac499  mov     rdx, [rbp+lpFileName]; char *
0x1801ac49d  mov     rcx, [rbp+arg_0]; this
0x1801ac4a1  call    ?CalcMaxSize@CVBAExeFile@@AEAAKPEBD@Z; CVBAExeFile::CalcMaxSize(char const *)
0x1801ac4a6  mov     [rsp+70h+dwMaximumSizeLow], eax
0x1801ac4aa  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1801ac4b3  mov     [rsp+70h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801ac4bb  mov     [rsp+70h+dwCreationDisposition], 2; dwCreationDisposition
0x1801ac4c3  xor     r9d, r9d; lpSecurityAttributes
0x1801ac4c6  xor     r8d, r8d; dwShareMode
0x1801ac4c9  mov     edx, 0C0000000h; dwDesiredAccess
0x1801ac4ce  mov     rcx, [rbp+lpFileName]; lpFileName
0x1801ac4d2  call    cs:__imp_CreateFileA
0x1801ac4d8  mov     [rsp+70h+hFile], rax
0x1801ac4dd  cmp     [rsp+70h+hFile], 0FFFFFFFFFFFFFFFFh
0x1801ac4e3  jnz     short loc_1801AC507
0x1801ac4e5  call    cs:__imp_GetLastError
0x1801ac4eb  mov     ecx, eax
0x1801ac4ed  call    TiperrOfOFErr
0x1801ac4f2  mov     ecx, eax
0x1801ac4f4  call    EberrOfHresult
0x1801ac4f9  mov     rcx, [rbp+arg_0]
0x1801ac4fd  mov     [rcx+18h], eax
0x1801ac500  xor     eax, eax
0x1801ac502  jmp     loc_1801AC62E
0x1801ac507  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], 0; lpName
0x1801ac510  mov     eax, [rsp+70h+dwMaximumSizeLow]
0x1801ac514  mov     [rsp+70h+dwCreationDisposition], eax; dwMaximumSizeLow
0x1801ac518  xor     r9d, r9d; dwMaximumSizeHigh
0x1801ac51b  mov     r8d, 4; flProtect
0x1801ac521  xor     edx, edx; lpFileMappingAttributes
0x1801ac523  mov     rcx, [rsp+70h+hFile]; hFile
0x1801ac528  call    cs:__imp_CreateFileMappingA
0x1801ac52e  mov     [rsp+70h+hFileMappingObject], rax
0x1801ac533  cmp     [rsp+70h+hFileMappingObject], 0
0x1801ac539  jnz     short loc_1801AC55D
0x1801ac53b  call    cs:__imp_GetLastError
0x1801ac541  mov     ecx, eax
0x1801ac543  call    TiperrOfOFErr
0x1801ac548  mov     ecx, eax
0x1801ac54a  call    EberrOfHresult
0x1801ac54f  mov     rcx, [rbp+arg_0]
0x1801ac553  mov     [rcx+18h], eax
0x1801ac556  xor     eax, eax
0x1801ac558  jmp     loc_1801AC62E
0x1801ac55d  mov     eax, [rsp+70h+dwMaximumSizeLow]
0x1801ac561  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x1801ac566  xor     r9d, r9d; dwFileOffsetLow
0x1801ac569  xor     r8d, r8d; dwFileOffsetHigh
0x1801ac56c  mov     edx, 2; dwDesiredAccess
0x1801ac571  mov     rcx, [rsp+70h+hFileMappingObject]; hFileMappingObject
0x1801ac576  call    cs:__imp_MapViewOfFile
0x1801ac57c  mov     [rsp+70h+lpBaseAddress], rax
0x1801ac581  cmp     [rsp+70h+lpBaseAddress], 0
0x1801ac587  jnz     short loc_1801AC5A6
0x1801ac589  mov     rcx, [rsp+70h+hFileMappingObject]; hObject
0x1801ac58e  call    cs:__imp_CloseHandle
0x1801ac594  mov     rax, [rbp+arg_0]
0x1801ac598  mov     dword ptr [rax+18h], 7
0x1801ac59f  xor     eax, eax
0x1801ac5a1  jmp     loc_1801AC62E
0x1801ac5a6  lea     r9, [rsp+70h+lDistanceToMove]; unsigned int *
0x1801ac5ab  mov     r8, [rsp+70h+lpBaseAddress]; unsigned __int8 *
0x1801ac5b0  mov     rdx, [rbp+lpFileName]; char *
0x1801ac5b4  mov     rcx, [rbp+arg_0]; this
0x1801ac5b8  call    ?WriteExe@CVBAExeFile@@AEAAIPEBDPEAEPEAK@Z; CVBAExeFile::WriteExe(char const *,uchar *,ulong *)
0x1801ac5bd  mov     [rsp+70h+var_30], eax
0x1801ac5c1  mov     rcx, [rsp+70h+lpBaseAddress]; lpBaseAddress
0x1801ac5c6  call    cs:__imp_UnmapViewOfFile
0x1801ac5cc  mov     rcx, [rsp+70h+hFileMappingObject]; hObject
0x1801ac5d1  call    cs:__imp_CloseHandle
0x1801ac5d7  cmp     [rsp+70h+var_30], 0
0x1801ac5dc  jnz     short loc_1801AC5FE
0x1801ac5de  xor     r9d, r9d; dwMoveMethod
0x1801ac5e1  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801ac5e4  mov     edx, [rsp+70h+lDistanceToMove]; lDistanceToMove
0x1801ac5e8  mov     rcx, [rsp+70h+hFile]; hFile
0x1801ac5ed  call    cs:__imp_SetFilePointer
0x1801ac5f3  mov     rcx, [rsp+70h+hFile]; hFile
0x1801ac5f8  call    cs:__imp_SetEndOfFile
0x1801ac5fe  mov     rcx, [rsp+70h+hFile]; hObject
0x1801ac603  call    cs:__imp_CloseHandle
0x1801ac609  cmp     [rsp+70h+var_30], 0
0x1801ac60e  jz      short loc_1801AC629
0x1801ac610  mov     rcx, [rbp+lpFileName]; lpFileName
0x1801ac614  call    cs:__imp_DeleteFileA
0x1801ac61a  mov     rax, [rbp+arg_0]
0x1801ac61e  mov     ecx, [rsp+70h+var_30]
0x1801ac622  mov     [rax+18h], ecx
0x1801ac625  xor     eax, eax
0x1801ac627  jmp     short loc_1801AC62E
0x1801ac629  mov     eax, 1
0x1801ac62e  add     rsp, 70h
0x1801ac632  pop     rbp
0x1801ac633  retn
```
