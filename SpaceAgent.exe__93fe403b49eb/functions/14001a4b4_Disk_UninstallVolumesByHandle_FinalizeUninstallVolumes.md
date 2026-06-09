# Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes

- ea: `0x14001a4b4`
- end: `0x14001a52a`
- name: `Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes`
- size: `118`
- prototype: `__int64 __fastcall(int, unsigned int **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001a2dc`

## callees

- `0x14001a4b4`
- `0x14001d7c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001a504`
- `KERNEL32!HeapFree` at `0x14001a504`
- `KERNEL32!GetProcessHeap` at `0x14001a4f6`
- `KERNEL32!GetProcessHeap` at `0x14001a4f6`
- `KERNEL32!SetLastError` at `0x14001a517`
- `KERNEL32!SetLastError` at `0x14001a517`
- `KERNEL32!GetLastError` at `0x14001a4e0`
- `KERNEL32!GetLastError` at `0x14001a4e0`

## pseudocode

```c
__int64 __fastcall Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes(int a1, unsigned int **a2)
{
  DWORD LastError; // esi
  int v4; // edi
  unsigned int v5; // ebx
  unsigned int **i; // r14
  unsigned int v7; // eax
  HANDLE ProcessHeap; // rax
  BOOL v9; // eax

  LastError = 0;
  v4 = a1;
  v5 = 1;
  for ( i = a2; v4; --v4 )
  {
    v7 = FinalizeUninstallVolume(*i);
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
0x14001a4b4  push    rbx
0x14001a4b6  push    rbp
0x14001a4b7  push    rsi
0x14001a4b8  push    rdi
0x14001a4b9  push    r14
0x14001a4bb  sub     rsp, 20h
0x14001a4bf  xor     esi, esi
0x14001a4c1  mov     rbp, rdx
0x14001a4c4  mov     edi, ecx
0x14001a4c6  mov     ebx, 1
0x14001a4cb  mov     r14, rdx
0x14001a4ce  test    ecx, ecx
0x14001a4d0  jz      short loc_14001A4F1
0x14001a4d2  mov     rcx, [r14]; lpMem
0x14001a4d5  call    ?FinalizeUninstallVolume@@YAHPEAX@Z; FinalizeUninstallVolume(void *)
0x14001a4da  test    ebx, ebx
0x14001a4dc  jz      short loc_14001A4E8
0x14001a4de  mov     ebx, eax
0x14001a4e0  call    cs:__imp_GetLastError
0x14001a4e6  mov     esi, eax
0x14001a4e8  add     r14, 8
0x14001a4ec  add     edi, 0FFFFFFFFh
0x14001a4ef  jnz     short loc_14001A4D2
0x14001a4f1  test    rbp, rbp
0x14001a4f4  jz      short loc_14001A515
0x14001a4f6  call    cs:__imp_GetProcessHeap
0x14001a4fc  mov     r8, rbp; lpMem
0x14001a4ff  xor     edx, edx; dwFlags
0x14001a501  mov     rcx, rax; hHeap
0x14001a504  call    cs:__imp_HeapFree
0x14001a50a  test    ebx, ebx
0x14001a50c  jz      short loc_14001A515
0x14001a50e  mov     ebx, eax
0x14001a510  mov     esi, 6
0x14001a515  mov     ecx, esi; dwErrCode
0x14001a517  call    cs:__imp_SetLastError
0x14001a51d  mov     eax, ebx
0x14001a51f  add     rsp, 20h
0x14001a523  pop     r14
0x14001a525  pop     rdi
0x14001a526  pop     rsi
0x14001a527  pop     rbp
0x14001a528  pop     rbx
0x14001a529  retn
```
