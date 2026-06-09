# AbortUninstallVolume(void *)

- ea: `0x14001d640`
- end: `0x14001d6ed`
- name: `?AbortUninstallVolume@@YAHPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(LPVOID *lpMem)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, installer_update`

## callers

- `0x14001a438`
- `0x14001a530`

## callees

- `0x14001d640`
- `0x14001d6f4`
- `0x14001d738`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001d6ab`
- `KERNEL32!CloseHandle` at `0x14001d6ab`
- `KERNEL32!HeapFree` at `0x14001d65f`
- `KERNEL32!HeapFree` at `0x14001d6c7`
- `KERNEL32!HeapFree` at `0x14001d65f`
- `KERNEL32!HeapFree` at `0x14001d6c7`
- `KERNEL32!GetProcessHeap` at `0x14001d64e`
- `KERNEL32!GetProcessHeap` at `0x14001d64e`
- `KERNEL32!SetLastError` at `0x14001d6da`
- `KERNEL32!SetLastError` at `0x14001d6da`
- `KERNEL32!GetLastError` at `0x14001d676`
- `KERNEL32!GetLastError` at `0x14001d699`
- `KERNEL32!GetLastError` at `0x14001d6b7`
- `KERNEL32!GetLastError` at `0x14001d676`
- `KERNEL32!GetLastError` at `0x14001d699`
- `KERNEL32!GetLastError` at `0x14001d6b7`

## pseudocode

```c
__int64 __fastcall AbortUninstallVolume(LPVOID *lpMem)
{
  HANDLE ProcessHeap; // r14
  BOOL v3; // ebp
  unsigned int v4; // ebx
  DWORD LastError; // edi
  unsigned int v6; // eax
  void *v7; // rcx
  BOOL v8; // eax
  BOOL v9; // eax

  ProcessHeap = GetProcessHeap();
  v3 = HeapFree(ProcessHeap, 0, *lpMem);
  v4 = AbortUninstallVolume_FreeAccessPaths(lpMem[1]);
  if ( v3 )
  {
    LastError = GetLastError();
  }
  else
  {
    LastError = 6;
    v4 = 0;
  }
  v6 = AbortUninstallVolume_FreeMountPoints(*((unsigned int *)lpMem + 4));
  if ( v4 )
  {
    v4 = v6;
    LastError = GetLastError();
  }
  v7 = lpMem[4];
  if ( v7 != (void *)-1LL )
  {
    v8 = CloseHandle(v7);
    if ( v4 )
    {
      v4 = v8;
      LastError = GetLastError();
    }
  }
  v9 = HeapFree(ProcessHeap, 0, lpMem);
  if ( v4 )
  {
    v4 = v9;
    LastError = 6;
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x14001d640  push    rbx
0x14001d642  push    rbp
0x14001d643  push    rsi
0x14001d644  push    rdi
0x14001d645  push    r14
0x14001d647  sub     rsp, 20h
0x14001d64b  mov     rsi, rcx
0x14001d64e  call    cs:__imp_GetProcessHeap
0x14001d654  mov     r8, [rsi]; lpMem
0x14001d657  xor     edx, edx; dwFlags
0x14001d659  mov     rcx, rax; hHeap
0x14001d65c  mov     r14, rax
0x14001d65f  call    cs:__imp_HeapFree
0x14001d665  mov     rcx, [rsi+8]; lpMem
0x14001d669  mov     ebp, eax
0x14001d66b  call    AbortUninstallVolume_FreeAccessPaths
0x14001d670  mov     ebx, eax
0x14001d672  test    ebp, ebp
0x14001d674  jz      short loc_14001D680
0x14001d676  call    cs:__imp_GetLastError
0x14001d67c  mov     edi, eax
0x14001d67e  jmp     short loc_14001D687
0x14001d680  mov     edi, 6
0x14001d685  mov     ebx, ebp
0x14001d687  mov     rdx, [rsi+18h]
0x14001d68b  mov     ecx, [rsi+10h]
0x14001d68e  call    AbortUninstallVolume_FreeMountPoints
0x14001d693  test    ebx, ebx
0x14001d695  jz      short loc_14001D6A1
0x14001d697  mov     ebx, eax
0x14001d699  call    cs:__imp_GetLastError
0x14001d69f  mov     edi, eax
0x14001d6a1  mov     rcx, [rsi+20h]; hObject
0x14001d6a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001d6a9  jz      short loc_14001D6BF
0x14001d6ab  call    cs:__imp_CloseHandle
0x14001d6b1  test    ebx, ebx
0x14001d6b3  jz      short loc_14001D6BF
0x14001d6b5  mov     ebx, eax
0x14001d6b7  call    cs:__imp_GetLastError
0x14001d6bd  mov     edi, eax
0x14001d6bf  mov     r8, rsi; lpMem
0x14001d6c2  xor     edx, edx; dwFlags
0x14001d6c4  mov     rcx, r14; hHeap
0x14001d6c7  call    cs:__imp_HeapFree
0x14001d6cd  test    ebx, ebx
0x14001d6cf  jz      short loc_14001D6D8
0x14001d6d1  mov     ebx, eax
0x14001d6d3  mov     edi, 6
0x14001d6d8  mov     ecx, edi; dwErrCode
0x14001d6da  call    cs:__imp_SetLastError
0x14001d6e0  mov     eax, ebx
0x14001d6e2  add     rsp, 20h
0x14001d6e6  pop     r14
0x14001d6e8  pop     rdi
0x14001d6e9  pop     rsi
0x14001d6ea  pop     rbp
0x14001d6eb  pop     rbx
0x14001d6ec  retn
```
