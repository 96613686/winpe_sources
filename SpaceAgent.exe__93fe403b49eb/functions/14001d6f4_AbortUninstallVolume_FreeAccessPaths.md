# AbortUninstallVolume_FreeAccessPaths

- ea: `0x14001d6f4`
- end: `0x14001d732`
- name: `AbortUninstallVolume_FreeAccessPaths`
- size: `62`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001d640`
- `0x14001e464`

## callees

- `0x14001d6f4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001d710`
- `KERNEL32!HeapFree` at `0x14001d710`
- `KERNEL32!GetProcessHeap` at `0x14001d702`
- `KERNEL32!GetProcessHeap` at `0x14001d702`
- `KERNEL32!SetLastError` at `0x14001d71d`
- `KERNEL32!SetLastError` at `0x14001d71d`

## pseudocode

```c
__int64 __fastcall AbortUninstallVolume_FreeAccessPaths(LPVOID lpMem)
{
  HANDLE ProcessHeap; // rax
  unsigned int v3; // ebx

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    v3 = HeapFree(ProcessHeap, 0, lpMem);
    SetLastError(6u);
  }
  else
  {
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x14001d6f4  push    rbx
0x14001d6f6  sub     rsp, 20h
0x14001d6fa  mov     rbx, rcx
0x14001d6fd  test    rcx, rcx
0x14001d700  jz      short loc_14001D725
0x14001d702  call    cs:__imp_GetProcessHeap
0x14001d708  mov     r8, rbx; lpMem
0x14001d70b  xor     edx, edx; dwFlags
0x14001d70d  mov     rcx, rax; hHeap
0x14001d710  call    cs:__imp_HeapFree
0x14001d716  mov     ecx, 6; dwErrCode
0x14001d71b  mov     ebx, eax
0x14001d71d  call    cs:__imp_SetLastError
0x14001d723  jmp     short loc_14001D72A
0x14001d725  mov     ebx, 1
0x14001d72a  mov     eax, ebx
0x14001d72c  add     rsp, 20h
0x14001d730  pop     rbx
0x14001d731  retn
```
