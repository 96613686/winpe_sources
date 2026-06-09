# _anonymous_namespace_::WriteCursorFileInfoBytes

- ea: `0x18002c008`
- end: `0x18002c059`
- name: `_anonymous_namespace_::WriteCursorFileInfoBytes`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002b2b4`

## callees

- `0x18000ea34`
- `0x18002c008`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c033`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c033`

## string_xrefs

- `0x18002c042`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
BOOL __fastcall anonymous_namespace_::WriteCursorFileInfoBytes(__int16 a1, void *a2)
{
  BOOL result; // eax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v5; // [rsp+50h] [rbp+18h] BYREF
  __int16 v6; // [rsp+54h] [rbp+1Ch]

  v6 = a1;
  v5 = 0x20000;
  result = WriteFile(a2, &v5, 6u, 0, 0);
  if ( !result )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v3);
  return result;
}

```

## disassembly

```asm
0x18002c008  mov     rax, rsp
0x18002c00b  sub     rsp, 38h
0x18002c00f  mov     r10, rdx
0x18002c012  mov     [rax+1Ch], cx
0x18002c016  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002c019  mov     dword ptr [rax+18h], 20000h
0x18002c020  lea     rdx, [rax+18h]; lpBuffer
0x18002c024  mov     qword ptr [rax-18h], 0
0x18002c02c  mov     rcx, r10; hFile
0x18002c02f  lea     r8d, [r9+6]; nNumberOfBytesToWrite
0x18002c033  call    cs:__imp_WriteFile
0x18002c039  test    eax, eax
0x18002c03b  jnz     short loc_18002C054
0x18002c03d  mov     rcx, [rsp+38h]; this
0x18002c042  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002c049  mov     edx, 0E8h; void *
0x18002c04e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002c054  add     rsp, 38h
0x18002c058  retn
```
