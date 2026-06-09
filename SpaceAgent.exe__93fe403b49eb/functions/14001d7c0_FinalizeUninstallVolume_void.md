# FinalizeUninstallVolume(void *)

- ea: `0x14001d7c0`
- end: `0x14001d88c`
- name: `?FinalizeUninstallVolume@@YAHPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(unsigned int *lpMem)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callers

- `0x14001a4b4`

## callees

- `0x14001ccc4`
- `0x14001d7c0`
- `0x14001d894`
- `0x14001d968`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001d807`
- `KERNEL32!CloseHandle` at `0x14001d807`
- `KERNEL32!HeapFree` at `0x14001d7f5`
- `KERNEL32!HeapFree` at `0x14001d861`
- `KERNEL32!HeapFree` at `0x14001d7f5`
- `KERNEL32!HeapFree` at `0x14001d861`
- `KERNEL32!GetProcessHeap` at `0x14001d7e7`
- `KERNEL32!GetProcessHeap` at `0x14001d853`
- `KERNEL32!GetProcessHeap` at `0x14001d7e7`
- `KERNEL32!GetProcessHeap` at `0x14001d853`
- `KERNEL32!SetLastError` at `0x14001d874`
- `KERNEL32!SetLastError` at `0x14001d874`
- `KERNEL32!GetLastError` at `0x14001d813`
- `KERNEL32!GetLastError` at `0x14001d831`
- `KERNEL32!GetLastError` at `0x14001d84b`
- `KERNEL32!GetLastError` at `0x14001d813`
- `KERNEL32!GetLastError` at `0x14001d831`
- `KERNEL32!GetLastError` at `0x14001d84b`

## pseudocode

```c
__int64 __fastcall FinalizeUninstallVolume(unsigned int *lpMem)
{
  unsigned int v2; // ebx
  WCHAR *v3; // rbx
  HANDLE ProcessHeap; // rax
  BOOL v5; // eax
  void *v6; // rcx
  BOOL v7; // eax
  DWORD LastError; // edi
  unsigned int v9; // eax
  unsigned int v10; // eax
  HANDLE v11; // rax
  BOOL v12; // eax

  v2 = UninstallDevice(*(PCWSTR *)lpMem);
  if ( v2 )
  {
    v3 = *(WCHAR **)lpMem;
    ProcessHeap = GetProcessHeap();
    v5 = HeapFree(ProcessHeap, 0, v3);
    v6 = (void *)*((_QWORD *)lpMem + 4);
    v2 = v5;
    if ( v6 == (void *)-1LL || (v7 = CloseHandle(v6), !v2) )
    {
      LastError = 6;
    }
    else
    {
      v2 = v7;
      LastError = GetLastError();
    }
    v9 = FinalizeUninstallVolume_DeleteAccessPaths(*((unsigned __int16 **)lpMem + 1));
    if ( v2 )
    {
      v2 = v9;
      LastError = GetLastError();
    }
    v10 = FinalizeUninstallVolume_DeleteMountPoints(lpMem[4], *((_QWORD *)lpMem + 3));
    if ( v2 )
    {
      v2 = v10;
      LastError = GetLastError();
    }
    v11 = GetProcessHeap();
    v12 = HeapFree(v11, 0, lpMem);
    if ( v2 )
    {
      v2 = v12;
      LastError = 6;
    }
    SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x14001d7c0  mov     [rsp+arg_0], rbx
0x14001d7c5  mov     [rsp+arg_8], rsi
0x14001d7ca  push    rdi
0x14001d7cb  sub     rsp, 20h
0x14001d7cf  mov     rsi, rcx
0x14001d7d2  mov     rcx, [rcx]; DevicePath
0x14001d7d5  call    ?UninstallDevice@@YAHPEBG@Z; UninstallDevice(ushort const *)
0x14001d7da  mov     ebx, eax
0x14001d7dc  test    eax, eax
0x14001d7de  jz      loc_14001D87A
0x14001d7e4  mov     rbx, [rsi]
0x14001d7e7  call    cs:__imp_GetProcessHeap
0x14001d7ed  mov     r8, rbx; lpMem
0x14001d7f0  xor     edx, edx; dwFlags
0x14001d7f2  mov     rcx, rax; hHeap
0x14001d7f5  call    cs:__imp_HeapFree
0x14001d7fb  mov     rcx, [rsi+20h]; hObject
0x14001d7ff  mov     ebx, eax
0x14001d801  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001d805  jz      short loc_14001D81D
0x14001d807  call    cs:__imp_CloseHandle
0x14001d80d  test    ebx, ebx
0x14001d80f  jz      short loc_14001D81D
0x14001d811  mov     ebx, eax
0x14001d813  call    cs:__imp_GetLastError
0x14001d819  mov     edi, eax
0x14001d81b  jmp     short loc_14001D822
0x14001d81d  mov     edi, 6
0x14001d822  mov     rcx, [rsi+8]; unsigned __int16 *
0x14001d826  call    FinalizeUninstallVolume_DeleteAccessPaths
0x14001d82b  test    ebx, ebx
0x14001d82d  jz      short loc_14001D839
0x14001d82f  mov     ebx, eax
0x14001d831  call    cs:__imp_GetLastError
0x14001d837  mov     edi, eax
0x14001d839  mov     rdx, [rsi+18h]
0x14001d83d  mov     ecx, [rsi+10h]
0x14001d840  call    FinalizeUninstallVolume_DeleteMountPoints
0x14001d845  test    ebx, ebx
0x14001d847  jz      short loc_14001D853
0x14001d849  mov     ebx, eax
0x14001d84b  call    cs:__imp_GetLastError
0x14001d851  mov     edi, eax
0x14001d853  call    cs:__imp_GetProcessHeap
0x14001d859  mov     r8, rsi; lpMem
0x14001d85c  xor     edx, edx; dwFlags
0x14001d85e  mov     rcx, rax; hHeap
0x14001d861  call    cs:__imp_HeapFree
0x14001d867  test    ebx, ebx
0x14001d869  jz      short loc_14001D872
0x14001d86b  mov     ebx, eax
0x14001d86d  mov     edi, 6
0x14001d872  mov     ecx, edi; dwErrCode
0x14001d874  call    cs:__imp_SetLastError
0x14001d87a  mov     rsi, [rsp+28h+arg_8]
0x14001d87f  mov     eax, ebx
0x14001d881  mov     rbx, [rsp+28h+arg_0]
0x14001d886  add     rsp, 20h
0x14001d88a  pop     rdi
0x14001d88b  retn
```
