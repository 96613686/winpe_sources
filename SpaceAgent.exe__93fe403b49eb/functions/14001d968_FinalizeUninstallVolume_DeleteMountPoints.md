# FinalizeUninstallVolume_DeleteMountPoints

- ea: `0x14001d968`
- end: `0x14001d9ff`
- name: `FinalizeUninstallVolume_DeleteMountPoints`
- size: `151`
- prototype: `__int64 __fastcall(int, LPCWSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, installer_update`

## callers

- `0x14001d7c0`

## callees

- `0x14001d968`

## import_xrefs

- `KERNEL32!DeleteVolumeMountPointW` at `0x14001d994`
- `KERNEL32!DeleteVolumeMountPointW` at `0x14001d994`
- `KERNEL32!HeapFree` at `0x14001d9b0`
- `KERNEL32!HeapFree` at `0x14001d9d7`
- `KERNEL32!HeapFree` at `0x14001d9b0`
- `KERNEL32!HeapFree` at `0x14001d9d7`
- `KERNEL32!GetProcessHeap` at `0x14001d984`
- `KERNEL32!GetProcessHeap` at `0x14001d984`
- `KERNEL32!SetLastError` at `0x14001d9ea`
- `KERNEL32!SetLastError` at `0x14001d9ea`
- `KERNEL32!GetLastError` at `0x14001d9a0`
- `KERNEL32!GetLastError` at `0x14001d9a0`

## pseudocode

```c
__int64 __fastcall FinalizeUninstallVolume_DeleteMountPoints(int a1, LPCWSTR *a2)
{
  unsigned int v4; // ebx
  DWORD LastError; // edi
  LPCWSTR *v6; // r14
  HANDLE i; // r15
  BOOL v8; // eax
  BOOL v9; // eax
  BOOL v10; // eax

  v4 = 1;
  LastError = 0;
  v6 = a2;
  for ( i = GetProcessHeap(); a1; --a1 )
  {
    v8 = DeleteVolumeMountPointW(*v6);
    if ( v4 )
    {
      v4 = v8;
      LastError = GetLastError();
    }
    v9 = HeapFree(i, 0, (LPVOID)*v6);
    if ( v4 )
    {
      v4 = v9;
      LastError = 6;
    }
    ++v6;
  }
  if ( a2 )
  {
    v10 = HeapFree(i, 0, a2);
    if ( v4 )
    {
      v4 = v10;
      LastError = 6;
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x14001d968  push    rbx
0x14001d96a  push    rbp
0x14001d96b  push    rsi
0x14001d96c  push    rdi
0x14001d96d  push    r14
0x14001d96f  push    r15
0x14001d971  sub     rsp, 28h
0x14001d975  mov     rbp, rdx
0x14001d978  mov     esi, ecx
0x14001d97a  mov     ebx, 1
0x14001d97f  xor     edi, edi
0x14001d981  mov     r14, rdx
0x14001d984  call    cs:__imp_GetProcessHeap
0x14001d98a  mov     r15, rax
0x14001d98d  test    esi, esi
0x14001d98f  jz      short loc_14001D9CA
0x14001d991  mov     rcx, [r14]; lpszVolumeMountPoint
0x14001d994  call    cs:__imp_DeleteVolumeMountPointW
0x14001d99a  test    ebx, ebx
0x14001d99c  jz      short loc_14001D9A8
0x14001d99e  mov     ebx, eax
0x14001d9a0  call    cs:__imp_GetLastError
0x14001d9a6  mov     edi, eax
0x14001d9a8  mov     r8, [r14]; lpMem
0x14001d9ab  xor     edx, edx; dwFlags
0x14001d9ad  mov     rcx, r15; hHeap
0x14001d9b0  call    cs:__imp_HeapFree
0x14001d9b6  test    ebx, ebx
0x14001d9b8  jz      short loc_14001D9C1
0x14001d9ba  mov     ebx, eax
0x14001d9bc  mov     edi, 6
0x14001d9c1  add     r14, 8
0x14001d9c5  add     esi, 0FFFFFFFFh
0x14001d9c8  jnz     short loc_14001D991
0x14001d9ca  test    rbp, rbp
0x14001d9cd  jz      short loc_14001D9E8
0x14001d9cf  mov     r8, rbp; lpMem
0x14001d9d2  xor     edx, edx; dwFlags
0x14001d9d4  mov     rcx, r15; hHeap
0x14001d9d7  call    cs:__imp_HeapFree
0x14001d9dd  test    ebx, ebx
0x14001d9df  jz      short loc_14001D9E8
0x14001d9e1  mov     ebx, eax
0x14001d9e3  mov     edi, 6
0x14001d9e8  mov     ecx, edi; dwErrCode
0x14001d9ea  call    cs:__imp_SetLastError
0x14001d9f0  mov     eax, ebx
0x14001d9f2  add     rsp, 28h
0x14001d9f6  pop     r15
0x14001d9f8  pop     r14
0x14001d9fa  pop     rdi
0x14001d9fb  pop     rsi
0x14001d9fc  pop     rbp
0x14001d9fd  pop     rbx
0x14001d9fe  retn
```
