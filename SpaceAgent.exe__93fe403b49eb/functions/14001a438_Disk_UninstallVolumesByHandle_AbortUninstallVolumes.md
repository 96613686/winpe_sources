# Disk_UninstallVolumesByHandle_AbortUninstallVolumes

- ea: `0x14001a438`
- end: `0x14001a4ae`
- name: `Disk_UninstallVolumesByHandle_AbortUninstallVolumes`
- size: `118`
- prototype: `__int64 __fastcall(int, LPVOID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001a2dc`

## callees

- `0x14001a438`
- `0x14001d640`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001a488`
- `KERNEL32!HeapFree` at `0x14001a488`
- `KERNEL32!GetProcessHeap` at `0x14001a47a`
- `KERNEL32!GetProcessHeap` at `0x14001a47a`
- `KERNEL32!SetLastError` at `0x14001a49b`
- `KERNEL32!SetLastError` at `0x14001a49b`
- `KERNEL32!GetLastError` at `0x14001a464`
- `KERNEL32!GetLastError` at `0x14001a464`

## pseudocode

```c
__int64 __fastcall Disk_UninstallVolumesByHandle_AbortUninstallVolumes(int a1, LPVOID **a2)
{
  DWORD LastError; // esi
  int v4; // edi
  unsigned int v5; // ebx
  LPVOID **i; // r14
  unsigned int v7; // eax
  HANDLE ProcessHeap; // rax
  BOOL v9; // eax

  LastError = 0;
  v4 = a1;
  v5 = 1;
  for ( i = a2; v4; --v4 )
  {
    v7 = AbortUninstallVolume(*i);
    if ( v5 )
    {
      v5 = v7;
      LastError = GetLastError();
    }
    ++i;
  }
  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v9 = HeapFree(ProcessHeap, 0, a2);
    if ( v5 )
    {
      v5 = v9;
      LastError = 6;
    }
  }
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x14001a438  push    rbx
0x14001a43a  push    rbp
0x14001a43b  push    rsi
0x14001a43c  push    rdi
0x14001a43d  push    r14
0x14001a43f  sub     rsp, 20h
0x14001a443  xor     esi, esi
0x14001a445  mov     rbp, rdx
0x14001a448  mov     edi, ecx
0x14001a44a  mov     ebx, 1
0x14001a44f  mov     r14, rdx
0x14001a452  test    ecx, ecx
0x14001a454  jz      short loc_14001A475
0x14001a456  mov     rcx, [r14]; lpMem
0x14001a459  call    ?AbortUninstallVolume@@YAHPEAX@Z; AbortUninstallVolume(void *)
0x14001a45e  test    ebx, ebx
0x14001a460  jz      short loc_14001A46C
0x14001a462  mov     ebx, eax
0x14001a464  call    cs:__imp_GetLastError
0x14001a46a  mov     esi, eax
0x14001a46c  add     r14, 8
0x14001a470  add     edi, 0FFFFFFFFh
0x14001a473  jnz     short loc_14001A456
0x14001a475  test    rbp, rbp
0x14001a478  jz      short loc_14001A499
0x14001a47a  call    cs:__imp_GetProcessHeap
0x14001a480  mov     r8, rbp; lpMem
0x14001a483  xor     edx, edx; dwFlags
0x14001a485  mov     rcx, rax; hHeap
0x14001a488  call    cs:__imp_HeapFree
0x14001a48e  test    ebx, ebx
0x14001a490  jz      short loc_14001A499
0x14001a492  mov     ebx, eax
0x14001a494  mov     esi, 6
0x14001a499  mov     ecx, esi; dwErrCode
0x14001a49b  call    cs:__imp_SetLastError
0x14001a4a1  mov     eax, ebx
0x14001a4a3  add     rsp, 20h
0x14001a4a7  pop     r14
0x14001a4a9  pop     rdi
0x14001a4aa  pop     rsi
0x14001a4ab  pop     rbp
0x14001a4ac  pop     rbx
0x14001a4ad  retn
```
