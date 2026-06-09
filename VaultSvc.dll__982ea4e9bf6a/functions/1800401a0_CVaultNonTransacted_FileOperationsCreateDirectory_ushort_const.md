# CVaultNonTransacted::FileOperationsCreateDirectory(ushort const *)

- ea: `0x1800401a0`
- end: `0x1800401c5`
- name: `?FileOperationsCreateDirectory@CVaultNonTransacted@@UEAAKPEBG@Z`
- size: `37`
- prototype: `DWORD __fastcall(CVaultNonTransacted *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800401a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401b7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800401a9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800401a9`

## pseudocode

```c
DWORD __fastcall CVaultNonTransacted::FileOperationsCreateDirectory(
        CVaultNonTransacted *this,
        const unsigned __int16 *a2)
{
  if ( CreateDirectoryW(a2, 0) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800401a0  sub     rsp, 28h
0x1800401a4  mov     rcx, rdx; lpPathName
0x1800401a7  xor     edx, edx; lpSecurityAttributes
0x1800401a9  call    cs:__imp_CreateDirectoryW
0x1800401af  test    eax, eax
0x1800401b1  jnz     short loc_1800401BE
0x1800401b3  add     rsp, 28h
0x1800401b7  jmp     cs:__imp_GetLastError
0x1800401be  xor     eax, eax
0x1800401c0  add     rsp, 28h
0x1800401c4  retn
```
