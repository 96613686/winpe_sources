# ExtractFile

- ea: `0x140053648`
- end: `0x140053945`
- name: `ExtractFile`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140054258`

## callees

- `0x140052ad4`
- `0x140053304`
- `0x140053648`
- `0x140080bdc`
- `0x140080c50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400538c2`
- `KERNEL32!CloseHandle` at `0x1400538c2`
- `KERNEL32!HeapFree` at `0x1400538e2`
- `KERNEL32!HeapFree` at `0x1400538e2`
- `KERNEL32!HeapAlloc` at `0x14005368e`
- `KERNEL32!HeapAlloc` at `0x14005368e`
- `KERNEL32!GetProcessHeap` at `0x140053677`
- `KERNEL32!GetProcessHeap` at `0x1400538ce`
- `KERNEL32!GetProcessHeap` at `0x140053677`
- `KERNEL32!GetProcessHeap` at `0x1400538ce`
- `KERNEL32!GetLastError` at `0x140053715`
- `KERNEL32!GetLastError` at `0x14005376b`
- `KERNEL32!GetLastError` at `0x14005387c`
- `KERNEL32!GetLastError` at `0x14005391c`
- `KERNEL32!GetLastError` at `0x140053715`
- `KERNEL32!GetLastError` at `0x14005376b`
- `KERNEL32!GetLastError` at `0x14005387c`
- `KERNEL32!GetLastError` at `0x14005391c`
- `KERNEL32!ReadFile` at `0x14005380b`
- `KERNEL32!ReadFile` at `0x14005380b`
- `KERNEL32!CreateFileW` at `0x140053700`
- `KERNEL32!CreateFileW` at `0x140053700`
- `KERNEL32!SetEndOfFile` at `0x14005375b`
- `KERNEL32!SetEndOfFile` at `0x14005375b`
- `KERNEL32!SetFilePointer` at `0x1400537a3`
- `KERNEL32!SetFilePointer` at `0x1400537a3`
- `KERNEL32!WriteFile` at `0x14005385d`
- `KERNEL32!WriteFile` at `0x14005385d`

## pseudocode

```c
__int64 ExtractFile(_QWORD *a1, __int64 a2, const WCHAR *a3, ...)
{
  unsigned int v6; // r15d
  HANDLE ProcessHeap; // rax
  void *v8; // rbp
  signed int Directory; // ebx
  HANDLE FileW; // rax
  void *v11; // rsi
  signed int LastError; // eax
  signed int v13; // eax
  __int64 v14; // rax
  void *v15; // rcx
  unsigned __int64 v16; // r8
  unsigned int v17; // ebp
  unsigned int v18; // edi
  signed int v19; // eax
  HANDLE v20; // rax
  signed int v22; // eax
  char *v23; // [rsp+40h] [rbp-38h]
  LPCWSTR lpPathName; // [rsp+48h] [rbp-30h] BYREF
  __int64 NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF
  va_list NumberOfBytesReada; // [rsp+98h] [rbp+20h]
  __int64 NumberOfBytesWritten; // [rsp+A0h] [rbp+28h] BYREF
  va_list NumberOfBytesWrittena; // [rsp+A0h] [rbp+28h]
  va_list va2; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(NumberOfBytesWrittena, a3);
  va_start(NumberOfBytesReada, a3);
  NumberOfBytesRead = va_arg(NumberOfBytesWrittena, _QWORD);
  va_copy(va2, NumberOfBytesWrittena);
  NumberOfBytesWritten = va_arg(va2, _QWORD);
  lpPathName = 0;
  v6 = 0;
  ProcessHeap = GetProcessHeap();
  v23 = (char *)HeapAlloc(ProcessHeap, 0, 0xA00000u);
  v8 = v23;
  if ( v23 )
  {
    Directory = PathGetDirectory(a3, &lpPathName);
    if ( Directory >= 0 )
    {
      Directory = DirEnsureExists(lpPathName);
      if ( Directory >= 0 )
      {
        FileW = CreateFileW(a3, 0x40000000u, 5u, 0, 2u, 0x8000080u, 0);
        v11 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          Directory = LastError;
          if ( LastError > 0 )
            Directory = (unsigned __int16)LastError | 0x80070000;
          if ( Directory >= 0 )
            Directory = -2147467259;
        }
        else
        {
          Directory = FileSetPointer(FileW, *(_QWORD *)(a2 + 32));
          if ( Directory >= 0 )
          {
            if ( !SetEndOfFile(v11) || SetFilePointer(v11, 0, 0, 0) == -1 )
            {
              v13 = GetLastError();
              Directory = v13;
              if ( v13 > 0 )
                Directory = (unsigned __int16)v13 | 0x80070000;
              if ( Directory >= 0 )
                Directory = -2147467259;
            }
            else
            {
              Directory = FileSetPointer(*a1, *(_QWORD *)(a2 + 24) + *(_QWORD *)(a1[4] + 8LL));
              if ( Directory >= 0 )
              {
                v14 = 0;
                while ( 1 )
                {
                  v15 = (void *)*a1;
                  v16 = *(_QWORD *)(a2 + 32) - v14;
                  LODWORD(NumberOfBytesRead) = 0;
                  if ( v16 > 0xA00000 )
                    LODWORD(v16) = 10485760;
                  if ( !ReadFile(v15, v8, v16, (LPDWORD)NumberOfBytesReada, 0) )
                    break;
                  v17 = NumberOfBytesRead;
                  Directory = 0;
                  v18 = 0;
                  if ( (_DWORD)NumberOfBytesRead )
                  {
                    while ( 1 )
                    {
                      LODWORD(NumberOfBytesWritten) = 0;
                      if ( !WriteFile(v11, &v23[v18], v17 - v18, (LPDWORD)NumberOfBytesWrittena, 0) )
                        break;
                      v18 += NumberOfBytesWritten;
                      if ( v18 >= v17 )
                      {
                        Directory = 0;
                        goto LABEL_30;
                      }
                    }
                    v19 = GetLastError();
                    Directory = v19;
                    if ( v19 > 0 )
                      Directory = (unsigned __int16)v19 | 0x80070000;
                    if ( Directory >= 0 )
                    {
                      Directory = -2147467259;
LABEL_33:
                      v8 = v23;
                      goto LABEL_34;
                    }
                  }
                  if ( Directory < 0 )
                    goto LABEL_33;
LABEL_30:
                  v8 = v23;
                  v6 += v18;
                  v14 = v6;
                  if ( (unsigned __int64)v6 >= *(_QWORD *)(a2 + 32) )
                    goto LABEL_34;
                }
                v22 = GetLastError();
                if ( v22 > 0 )
                  v22 = (unsigned __int16)v22 | 0x80070000;
                if ( v22 >= 0 )
                  v22 = -2147467259;
                Directory = v22;
              }
            }
          }
LABEL_34:
          CloseHandle(v11);
        }
      }
    }
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v8);
    if ( lpPathName )
      MemFree((LPVOID)lpPathName);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x140053648  mov     rax, rsp
0x14005364b  mov     [rax+8], rbx
0x14005364f  mov     [rax+10h], rbp
0x140053653  mov     [rax+20h], r9
0x140053657  push    rsi
0x140053658  push    rdi
0x140053659  push    r13
0x14005365b  push    r14
0x14005365d  push    r15
0x14005365f  sub     rsp, 50h
0x140053663  mov     rdi, r8
0x140053666  mov     qword ptr [rax-30h], 0
0x14005366e  mov     r14, rdx
0x140053671  mov     r13, rcx
0x140053674  xor     r15d, r15d
0x140053677  call    cs:__imp_GetProcessHeap
0x14005367e  nop     dword ptr [rax+rax+00h]
0x140053683  xor     edx, edx; dwFlags
0x140053685  mov     r8d, 0A00000h; dwBytes
0x14005368b  mov     rcx, rax; hHeap
0x14005368e  call    cs:__imp_HeapAlloc
0x140053695  nop     dword ptr [rax+rax+00h]
0x14005369a  mov     [rsp+78h+var_38], rax
0x14005369f  mov     rbp, rax
0x1400536a2  test    rax, rax
0x1400536a5  jnz     short loc_1400536B1
0x1400536a7  mov     ebx, 8007000Eh
0x1400536ac  jmp     loc_140053900
0x1400536b1  lea     rdx, [rsp+78h+lpPathName]
0x1400536b6  mov     rcx, rdi
0x1400536b9  call    PathGetDirectory
0x1400536be  mov     ebx, eax
0x1400536c0  test    eax, eax
0x1400536c2  js      loc_1400538CE
0x1400536c8  mov     rcx, [rsp+78h+lpPathName]; lpPathName
0x1400536cd  call    DirEnsureExists
0x1400536d2  mov     ebx, eax
0x1400536d4  test    eax, eax
0x1400536d6  js      loc_1400538CE
0x1400536dc  xor     r9d, r9d; lpSecurityAttributes
0x1400536df  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x1400536e4  mov     [rsp+78h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1400536ec  mov     edx, 40000000h; dwDesiredAccess
0x1400536f1  mov     rcx, rdi; lpFileName
0x1400536f4  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x1400536fc  lea     r8d, [r9+5]; dwShareMode
0x140053700  call    cs:__imp_CreateFileW
0x140053707  nop     dword ptr [rax+rax+00h]
0x14005370c  mov     rsi, rax
0x14005370f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140053713  jnz     short loc_140053742
0x140053715  call    cs:__imp_GetLastError
0x14005371c  nop     dword ptr [rax+rax+00h]
0x140053721  mov     ebx, eax
0x140053723  test    eax, eax
0x140053725  jle     short loc_140053730
0x140053727  movzx   ebx, ax
0x14005372a  or      ebx, 80070000h
0x140053730  test    ebx, ebx
0x140053732  js      loc_1400538CE
0x140053738  mov     ebx, 80004005h
0x14005373d  jmp     loc_1400538CE
0x140053742  mov     rdx, [r14+20h]
0x140053746  mov     rcx, rsi
0x140053749  call    FileSetPointer
0x14005374e  mov     ebx, eax
0x140053750  test    eax, eax
0x140053752  js      loc_1400538BF
0x140053758  mov     rcx, rsi; hFile
0x14005375b  call    cs:__imp_SetEndOfFile
0x140053762  nop     dword ptr [rax+rax+00h]
0x140053767  test    eax, eax
0x140053769  jnz     short loc_140053798
0x14005376b  call    cs:__imp_GetLastError
0x140053772  nop     dword ptr [rax+rax+00h]
0x140053777  mov     ebx, eax
0x140053779  test    eax, eax
0x14005377b  jle     short loc_140053786
0x14005377d  movzx   ebx, ax
0x140053780  or      ebx, 80070000h
0x140053786  test    ebx, ebx
0x140053788  js      loc_1400538BF
0x14005378e  mov     ebx, 80004005h
0x140053793  jmp     loc_1400538BF
0x140053798  xor     r9d, r9d; dwMoveMethod
0x14005379b  xor     r8d, r8d; lpDistanceToMoveHigh
0x14005379e  xor     edx, edx; lDistanceToMove
0x1400537a0  mov     rcx, rsi; hFile
0x1400537a3  call    cs:__imp_SetFilePointer
0x1400537aa  nop     dword ptr [rax+rax+00h]
0x1400537af  cmp     eax, 0FFFFFFFFh
0x1400537b2  jz      short loc_14005376B
0x1400537b4  mov     rax, [r13+20h]
0x1400537b8  mov     rcx, [r13+0]
0x1400537bc  mov     rdx, [rax+8]
0x1400537c0  add     rdx, [r14+18h]
0x1400537c4  call    FileSetPointer
0x1400537c9  mov     ebx, eax
0x1400537cb  test    eax, eax
0x1400537cd  js      loc_1400538BF
0x1400537d3  xor     eax, eax
0x1400537d5  mov     r8, [r14+20h]
0x1400537d9  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400537e1  mov     rcx, [r13+0]; hFile
0x1400537e5  sub     r8, rax
0x1400537e8  mov     eax, 0A00000h
0x1400537ed  mov     dword ptr [rsp+78h+NumberOfBytesRead], 0
0x1400537f8  cmp     r8, rax
0x1400537fb  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x140053804  mov     rdx, rbp; lpBuffer
0x140053807  cmova   r8d, eax; nNumberOfBytesToRead
0x14005380b  call    cs:__imp_ReadFile
0x140053812  nop     dword ptr [rax+rax+00h]
0x140053817  test    eax, eax
0x140053819  jz      loc_14005391C
0x14005381f  mov     ebp, dword ptr [rsp+78h+NumberOfBytesRead]
0x140053826  xor     ebx, ebx
0x140053828  xor     edi, edi
0x14005382a  test    ebp, ebp
0x14005382c  jz      short loc_14005389B
0x14005382e  mov     rbx, [rsp+78h+var_38]
0x140053833  mov     r8d, ebp
0x140053836  mov     edx, edi
0x140053838  sub     r8d, edi; nNumberOfBytesToWrite
0x14005383b  mov     dword ptr [rsp+78h+NumberOfBytesWritten], 0
0x140053846  add     rdx, rbx; lpBuffer
0x140053849  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x140053852  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005385a  mov     rcx, rsi; hFile
0x14005385d  call    cs:__imp_WriteFile
0x140053864  nop     dword ptr [rax+rax+00h]
0x140053869  test    eax, eax
0x14005386b  jz      short loc_14005387C
0x14005386d  add     edi, dword ptr [rsp+78h+NumberOfBytesWritten]
0x140053874  cmp     edi, ebp
0x140053876  jb      short loc_140053833
0x140053878  xor     ebx, ebx
0x14005387a  jmp     short loc_14005389F
0x14005387c  call    cs:__imp_GetLastError
0x140053883  nop     dword ptr [rax+rax+00h]
0x140053888  mov     ebx, eax
0x14005388a  test    eax, eax
0x14005388c  jle     short loc_140053897
0x14005388e  movzx   ebx, ax
0x140053891  or      ebx, 80070000h
0x140053897  test    ebx, ebx
0x140053899  jns     short loc_1400538B5
0x14005389b  test    ebx, ebx
0x14005389d  js      short loc_1400538BA
0x14005389f  mov     rbp, [rsp+78h+var_38]
0x1400538a4  add     r15d, edi
0x1400538a7  mov     eax, r15d
0x1400538aa  cmp     rax, [r14+20h]
0x1400538ae  jnb     short loc_1400538BF
0x1400538b0  jmp     loc_1400537D5
0x1400538b5  mov     ebx, 80004005h
0x1400538ba  mov     rbp, [rsp+78h+var_38]
0x1400538bf  mov     rcx, rsi; hObject
0x1400538c2  call    cs:__imp_CloseHandle
0x1400538c9  nop     dword ptr [rax+rax+00h]
0x1400538ce  call    cs:__imp_GetProcessHeap
0x1400538d5  nop     dword ptr [rax+rax+00h]
0x1400538da  mov     r8, rbp; lpMem
0x1400538dd  xor     edx, edx; dwFlags
0x1400538df  mov     rcx, rax; hHeap
0x1400538e2  call    cs:__imp_HeapFree
0x1400538e9  nop     dword ptr [rax+rax+00h]
0x1400538ee  cmp     [rsp+78h+lpPathName], 0
0x1400538f4  jz      short loc_140053900
0x1400538f6  mov     rcx, [rsp+78h+lpPathName]; lpMem
0x1400538fb  call    MemFree
0x140053900  lea     r11, [rsp+78h+var_28]
0x140053905  mov     eax, ebx
0x140053907  mov     rbx, [r11+30h]
0x14005390b  mov     rbp, [r11+38h]
0x14005390f  mov     rsp, r11
0x140053912  pop     r15
0x140053914  pop     r14
0x140053916  pop     r13
0x140053918  pop     rdi
0x140053919  pop     rsi
0x14005391a  retn
0x14005391c  call    cs:__imp_GetLastError
0x140053923  nop     dword ptr [rax+rax+00h]
0x140053928  test    eax, eax
0x14005392a  jle     short loc_140053934
0x14005392c  movzx   eax, ax
0x14005392f  or      eax, 80070000h
0x140053934  mov     ebx, 80004005h
0x140053939  test    eax, eax
0x14005393b  cmovns  eax, ebx
0x14005393e  mov     ebx, eax
0x140053940  jmp     loc_1400538BF
```
