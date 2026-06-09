# mmioInstallIOProcA

- ea: `0x180011ee0`
- end: `0x180011ef6`
- name: `mmioInstallIOProcA`
- size: `22`
- prototype: `LPMMIOPROC __stdcall(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180011c1c`
- `0x180011ee0`

## pseudocode

```c
LPMMIOPROC __stdcall mmioInstallIOProcA(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)
{
  if ( (dwFlags & 0xEFF8FFFF) != 0 )
    return 0;
  else
    return (LPMMIOPROC)mmioInternalInstallIOProc(fccIOProc, (__int64)pIOProc, dwFlags & 0xFEFFFFFF);
}

```

## disassembly

```asm
0x180011ee0  test    r8d, 0EFF8FFFFh
0x180011ee7  jz      short loc_180011EEC
0x180011ee9  xor     eax, eax
0x180011eeb  retn
0x180011eec  btr     r8d, 18h
0x180011ef1  jmp     mmioInternalInstallIOProc
```
