# CVaultTransacted::FileOperationsDeleteFile(ushort const *)

- ea: `0x1800407c0`
- end: `0x1800407ea`
- name: `?FileOperationsDeleteFile@CVaultTransacted@@UEAAKPEBG@Z`
- size: `42`
- prototype: `DWORD __fastcall(HANDLE *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800407c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407dc`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x1800407ce`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x1800407ce`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsDeleteFile(HANDLE *this, const unsigned __int16 *a2)
{
  if ( DeleteFileTransactedW(a2, this[1]) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800407c0  sub     rsp, 28h
0x1800407c4  mov     rax, rdx
0x1800407c7  mov     rdx, [rcx+8]; hTransaction
0x1800407cb  mov     rcx, rax; lpFileName
0x1800407ce  call    cs:__imp_DeleteFileTransactedW
0x1800407d4  test    eax, eax
0x1800407d6  jnz     short loc_1800407E3
0x1800407d8  add     rsp, 28h
0x1800407dc  jmp     cs:__imp_GetLastError
0x1800407e3  xor     eax, eax
0x1800407e5  add     rsp, 28h
0x1800407e9  retn
```
