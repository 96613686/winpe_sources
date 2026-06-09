# Delete

- ea: `0x18001ff1c`
- end: `0x18001ff73`
- name: `Delete`
- size: `87`
- prototype: `__int64 __fastcall(int, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800200f0`

## callees

- `0x18001ff1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff4f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001ff3a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001ff3a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ff45`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ff45`

## pseudocode

```c
__int64 __fastcall Delete(int a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v3; // ebx
  BOOL v4; // eax
  signed int LastError; // eax

  if ( a2 && a3 )
  {
    v3 = 0;
    if ( a1 )
    {
      if ( a1 != 1 )
        return v3;
      v4 = RemoveDirectoryW(a2);
    }
    else
    {
      v4 = DeleteFileW(a2);
    }
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return v3;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001ff1c  push    rbx
0x18001ff1e  sub     rsp, 20h
0x18001ff22  test    rdx, rdx
0x18001ff25  jz      short loc_18001FF68
0x18001ff27  test    r8, r8
0x18001ff2a  jz      short loc_18001FF68
0x18001ff2c  xor     ebx, ebx
0x18001ff2e  test    ecx, ecx
0x18001ff30  jz      short loc_18001FF42
0x18001ff32  cmp     ecx, 1
0x18001ff35  jnz     short loc_18001FF64
0x18001ff37  mov     rcx, rdx; lpPathName
0x18001ff3a  call    cs:__imp_RemoveDirectoryW
0x18001ff40  jmp     short loc_18001FF4B
0x18001ff42  mov     rcx, rdx; lpFileName
0x18001ff45  call    cs:__imp_DeleteFileW
0x18001ff4b  test    eax, eax
0x18001ff4d  jnz     short loc_18001FF64
0x18001ff4f  call    cs:__imp_GetLastError
0x18001ff55  mov     ebx, eax
0x18001ff57  test    eax, eax
0x18001ff59  jle     short loc_18001FF64
0x18001ff5b  movzx   ebx, ax
0x18001ff5e  or      ebx, 80070000h
0x18001ff64  mov     eax, ebx
0x18001ff66  jmp     short loc_18001FF6D
0x18001ff68  mov     eax, 80070057h
0x18001ff6d  add     rsp, 20h
0x18001ff71  pop     rbx
0x18001ff72  retn
```
