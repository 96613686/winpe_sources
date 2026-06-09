# CFileStream::SetSize(_ULARGE_INTEGER)

- ea: `0x18000e700`
- end: `0x18000e7a2`
- name: `?SetSize@CFileStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `162`
- prototype: `int(CFileStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001c80`
- `0x18000e700`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18000e768`
- `KERNEL32!SetEndOfFile` at `0x18000e768`
- `KERNEL32!SetFilePointerEx` at `0x18000e743`
- `KERNEL32!SetFilePointerEx` at `0x18000e75a`
- `KERNEL32!SetFilePointerEx` at `0x18000e786`
- `KERNEL32!SetFilePointerEx` at `0x18000e743`
- `KERNEL32!SetFilePointerEx` at `0x18000e75a`
- `KERNEL32!SetFilePointerEx` at `0x18000e786`

## pseudocode

```c
__int64 __fastcall CFileStream::SetSize(HANDLE *this, union _ULARGE_INTEGER a2)
{
  LARGE_INTEGER liDistanceToMove; // [rsp+38h] [rbp+10h] BYREF
  LARGE_INTEGER v6; // [rsp+40h] [rbp+18h]

  v6.QuadPart = 0;
  liDistanceToMove.QuadPart = 0;
  if ( a2.QuadPart <= 0x7FFFFFFFFFFFFFFFLL
    && (!SetFilePointerEx(this[2], v6, &liDistanceToMove, 1u)
     || !SetFilePointerEx(this[2], (LARGE_INTEGER)a2.QuadPart, 0, 0)
     || !SetEndOfFile(this[2])
     || liDistanceToMove.QuadPart < (__int64)a2.QuadPart && !SetFilePointerEx(this[2], liDistanceToMove, 0, 0)) )
  {
    HrGetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x18000e700  mov     r11, rsp
0x18000e703  mov     [r11+8], rbx
0x18000e707  push    rdi
0x18000e708  sub     rsp, 20h
0x18000e70c  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000e716  mov     qword ptr [r11+18h], 0
0x18000e71e  mov     qword ptr [r11+10h], 0
0x18000e726  mov     rbx, rdx
0x18000e729  mov     rdi, rcx
0x18000e72c  cmp     rdx, rax
0x18000e72f  ja      short loc_18000E795
0x18000e731  mov     rdx, [r11+18h]; liDistanceToMove
0x18000e735  lea     r8, [r11+10h]; lpNewFilePointer
0x18000e739  mov     rcx, [rcx+10h]; hFile
0x18000e73d  mov     r9d, 1; dwMoveMethod
0x18000e743  call    cs:__imp_SetFilePointerEx
0x18000e749  test    eax, eax
0x18000e74b  jz      short loc_18000E790
0x18000e74d  mov     rcx, [rdi+10h]; hFile
0x18000e751  xor     r9d, r9d; dwMoveMethod
0x18000e754  xor     r8d, r8d; lpNewFilePointer
0x18000e757  mov     rdx, rbx; liDistanceToMove
0x18000e75a  call    cs:__imp_SetFilePointerEx
0x18000e760  test    eax, eax
0x18000e762  jz      short loc_18000E790
0x18000e764  mov     rcx, [rdi+10h]; hFile
0x18000e768  call    cs:__imp_SetEndOfFile
0x18000e76e  test    eax, eax
0x18000e770  jz      short loc_18000E790
0x18000e772  mov     rdx, qword ptr [rsp+28h+liDistanceToMove]; liDistanceToMove
0x18000e777  cmp     rdx, rbx
0x18000e77a  jge     short loc_18000E795
0x18000e77c  mov     rcx, [rdi+10h]; hFile
0x18000e780  xor     r9d, r9d; dwMoveMethod
0x18000e783  xor     r8d, r8d; lpNewFilePointer
0x18000e786  call    cs:__imp_SetFilePointerEx
0x18000e78c  test    eax, eax
0x18000e78e  jnz     short loc_18000E795
0x18000e790  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000e795  mov     rbx, [rsp+28h+arg_0]
0x18000e79a  xor     eax, eax
0x18000e79c  add     rsp, 20h
0x18000e7a0  pop     rdi
0x18000e7a1  retn
```
