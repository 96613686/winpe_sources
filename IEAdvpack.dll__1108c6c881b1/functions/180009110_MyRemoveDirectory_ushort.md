# MyRemoveDirectory(ushort *)

- ea: `0x180009110`
- end: `0x180009137`
- name: `?MyRemoveDirectory@@YAXPEAG@Z`
- size: `39`
- prototype: `void __fastcall(WCHAR *lpPathName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005584`
- `0x18000e060`

## callees

- `0x180009110`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180009127`
- `KERNEL32!RemoveDirectoryW` at `0x180009127`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000911e`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000911e`

## pseudocode

```c
void __fastcall MyRemoveDirectory(WCHAR *lpPathName)
{
  WCHAR *v1; // rbx

  v1 = lpPathName;
  while ( RemoveDirectoryW(lpPathName) )
  {
    PathRemoveFileSpecW(v1);
    lpPathName = v1;
  }
}

```

## disassembly

```asm
0x180009110  push    rbx
0x180009112  sub     rsp, 20h
0x180009116  mov     rbx, rcx
0x180009119  jmp     short loc_180009127
0x18000911b  mov     rcx, rbx; pszPath
0x18000911e  call    cs:__imp_PathRemoveFileSpecW
0x180009124  mov     rcx, rbx; lpPathName
0x180009127  call    cs:__imp_RemoveDirectoryW
0x18000912d  test    eax, eax
0x18000912f  jnz     short loc_18000911B
0x180009131  add     rsp, 20h
0x180009135  pop     rbx
0x180009136  retn
```
