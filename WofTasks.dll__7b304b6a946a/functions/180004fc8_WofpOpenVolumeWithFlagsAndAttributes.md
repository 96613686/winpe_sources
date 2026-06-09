# WofpOpenVolumeWithFlagsAndAttributes

- ea: `0x180004fc8`
- end: `0x1800050d3`
- name: `WofpOpenVolumeWithFlagsAndAttributes`
- size: `267`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, __int64, DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path`

## callers

- `0x180004788`
- `0x180004ef4`

## callees

- `0x180004fc8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800050a4`
- `KERNEL32!HeapFree` at `0x1800050bd`
- `KERNEL32!HeapFree` at `0x1800050a4`
- `KERNEL32!HeapFree` at `0x1800050bd`
- `KERNEL32!HeapAlloc` at `0x180004ff0`
- `KERNEL32!HeapAlloc` at `0x18000502f`
- `KERNEL32!HeapAlloc` at `0x180004ff0`
- `KERNEL32!HeapAlloc` at `0x18000502f`
- `KERNEL32!GetProcessHeap` at `0x180004fdf`
- `KERNEL32!GetProcessHeap` at `0x18000501e`
- `KERNEL32!GetProcessHeap` at `0x180005096`
- `KERNEL32!GetProcessHeap` at `0x1800050af`
- `KERNEL32!GetProcessHeap` at `0x180004fdf`
- `KERNEL32!GetProcessHeap` at `0x18000501e`
- `KERNEL32!GetProcessHeap` at `0x180005096`
- `KERNEL32!GetProcessHeap` at `0x1800050af`
- `KERNEL32!CreateFileW` at `0x18000508d`
- `KERNEL32!CreateFileW` at `0x18000508d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005014`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005014`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180005049`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180005049`

## pseudocode

```c
__int64 __fastcall WofpOpenVolumeWithFlagsAndAttributes(LPCWSTR lpszFileName, __int64 a2, DWORD a3)
{
  __int64 FileW; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  WCHAR *v9; // rbx
  HANDLE v10; // rax
  WCHAR *v11; // rax
  __int64 v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax

  FileW = -1;
  ProcessHeap = GetProcessHeap();
  v7 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0;
    if ( GetVolumePathNameW(lpszFileName, v7, 0x104u) )
    {
      v10 = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(v10, 0, 0x208u);
      v9 = v11;
      if ( v11 )
      {
        if ( GetVolumeNameForVolumeMountPointW(v8, v11, 0x104u) )
        {
          do
            ++FileW;
          while ( v9[FileW] );
          v12 = (unsigned int)(FileW - 1);
          if ( v9[v12] == 92 )
            v9[v12] = 0;
          FileW = (__int64)CreateFileW(v9, 0x80000000, 7u, 0, 3u, a3, 0);
        }
      }
    }
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v8);
    if ( v9 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v9);
    }
  }
  return FileW;
}

```

## disassembly

```asm
0x180004fc8  push    rbx
0x180004fca  push    rbp
0x180004fcb  push    rsi
0x180004fcc  push    rdi
0x180004fcd  push    r14
0x180004fcf  push    r15
0x180004fd1  sub     rsp, 48h
0x180004fd5  mov     r14d, r8d
0x180004fd8  mov     rbp, rcx
0x180004fdb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004fdf  call    cs:__imp_GetProcessHeap
0x180004fe5  xor     edx, edx; dwFlags
0x180004fe7  mov     r8d, 208h; dwBytes
0x180004fed  mov     rcx, rax; hHeap
0x180004ff0  call    cs:__imp_HeapAlloc
0x180004ff6  xor     r15d, r15d
0x180004ff9  mov     rsi, rax
0x180004ffc  test    rax, rax
0x180004fff  jz      loc_1800050C3
0x180005005  mov     r8d, 104h; cchBufferLength
0x18000500b  mov     rdx, rax; lpszVolumePathName
0x18000500e  mov     rcx, rbp; lpszFileName
0x180005011  mov     ebx, r15d
0x180005014  call    cs:__imp_GetVolumePathNameW
0x18000501a  test    eax, eax
0x18000501c  jz      short loc_180005096
0x18000501e  call    cs:__imp_GetProcessHeap
0x180005024  xor     edx, edx; dwFlags
0x180005026  mov     r8d, 208h; dwBytes
0x18000502c  mov     rcx, rax; hHeap
0x18000502f  call    cs:__imp_HeapAlloc
0x180005035  mov     rbx, rax
0x180005038  test    rax, rax
0x18000503b  jz      short loc_180005096
0x18000503d  mov     r8d, 104h; cchBufferLength
0x180005043  mov     rdx, rax; lpszVolumeName
0x180005046  mov     rcx, rsi; lpszVolumeMountPoint
0x180005049  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000504f  test    eax, eax
0x180005051  jz      short loc_180005096
0x180005053  inc     rdi
0x180005056  cmp     [rbx+rdi*2], r15w
0x18000505b  jnz     short loc_180005053
0x18000505d  lea     eax, [rdi-1]
0x180005060  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180005065  jnz     short loc_18000506C
0x180005067  mov     [rbx+rax*2], r15w
0x18000506c  xor     r9d, r9d; lpSecurityAttributes
0x18000506f  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180005074  mov     [rsp+78h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180005079  mov     edx, 80000000h; dwDesiredAccess
0x18000507e  mov     rcx, rbx; lpFileName
0x180005081  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180005089  lea     r8d, [r9+7]; dwShareMode
0x18000508d  call    cs:__imp_CreateFileW
0x180005093  mov     rdi, rax
0x180005096  call    cs:__imp_GetProcessHeap
0x18000509c  mov     r8, rsi; lpMem
0x18000509f  xor     edx, edx; dwFlags
0x1800050a1  mov     rcx, rax; hHeap
0x1800050a4  call    cs:__imp_HeapFree
0x1800050aa  test    rbx, rbx
0x1800050ad  jz      short loc_1800050C3
0x1800050af  call    cs:__imp_GetProcessHeap
0x1800050b5  mov     r8, rbx; lpMem
0x1800050b8  xor     edx, edx; dwFlags
0x1800050ba  mov     rcx, rax; hHeap
0x1800050bd  call    cs:__imp_HeapFree
0x1800050c3  mov     rax, rdi
0x1800050c6  add     rsp, 48h
0x1800050ca  pop     r15
0x1800050cc  pop     r14
0x1800050ce  pop     rdi
0x1800050cf  pop     rsi
0x1800050d0  pop     rbp
0x1800050d1  pop     rbx
0x1800050d2  retn
```
