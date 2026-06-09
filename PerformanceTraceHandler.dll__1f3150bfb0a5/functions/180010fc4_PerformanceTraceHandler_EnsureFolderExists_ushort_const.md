# PerformanceTraceHandler::EnsureFolderExists(ushort const *)

- ea: `0x180010fc4`
- end: `0x180010ff9`
- name: `?EnsureFolderExists@PerformanceTraceHandler@@AEAAJPEBG@Z`
- size: `53`
- prototype: `int __fastcall(PerformanceTraceHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001124c`

## callees

- `0x180010fc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fd7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010fcd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010fcd`

## pseudocode

```c
int __fastcall PerformanceTraceHandler::EnsureFolderExists(PerformanceTraceHandler *this, const unsigned __int16 *a2)
{
  int result; // eax

  if ( CreateDirectoryW(a2, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180010fc4  sub     rsp, 28h
0x180010fc8  mov     rcx, rdx; lpPathName
0x180010fcb  xor     edx, edx; lpSecurityAttributes
0x180010fcd  call    cs:__imp_CreateDirectoryW
0x180010fd3  test    eax, eax
0x180010fd5  jnz     short loc_180010FF2
0x180010fd7  call    cs:__imp_GetLastError
0x180010fdd  cmp     eax, 0B7h
0x180010fe2  jz      short loc_180010FF2
0x180010fe4  test    eax, eax
0x180010fe6  jle     short loc_180010FF4
0x180010fe8  movzx   eax, ax
0x180010feb  or      eax, 80070000h
0x180010ff0  jmp     short loc_180010FF4
0x180010ff2  xor     eax, eax
0x180010ff4  add     rsp, 28h
0x180010ff8  retn
```
