# CBufferedFile::GetFilePosition(void)

- ea: `0x18003e5c8`
- end: `0x18003e631`
- name: `?GetFilePosition@CBufferedFile@@IEAA_KXZ`
- size: `105`
- prototype: `unsigned __int64 __fastcall(CBufferedFile *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003e9a4`

## callees

- `0x1800015d0`
- `0x18003e5c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003e604`
- `KERNEL32!GetLastError` at `0x18003e604`
- `KERNEL32!SetFilePointer` at `0x18003e5f6`
- `KERNEL32!SetFilePointer` at `0x18003e5f6`

## pseudocode

```c
unsigned __int64 __fastcall CBufferedFile::GetFilePosition(CBufferedFile *this)
{
  void *v1; // rcx
  signed int v2; // eax
  __int64 v3; // rbx
  LONG DistanceToMoveHigh; // [rsp+20h] [rbp-18h] BYREF

  v1 = (void *)*((_QWORD *)this + 1);
  DistanceToMoveHigh = 0;
  v2 = SetFilePointer(v1, 0, &DistanceToMoveHigh, 1u);
  v3 = v2;
  if ( v2 == -1 && GetLastError() )
    return 0;
  else
    return v3 + ((__int64)DistanceToMoveHigh << 32);
}

```

## disassembly

```asm
0x18003e5c8  push    rbx
0x18003e5ca  sub     rsp, 30h
0x18003e5ce  mov     rax, cs:__security_cookie
0x18003e5d5  xor     rax, rsp
0x18003e5d8  mov     [rsp+38h+var_10], rax
0x18003e5dd  mov     rcx, [rcx+8]; hFile
0x18003e5e1  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18003e5e6  mov     r9d, 1; dwMoveMethod
0x18003e5ec  mov     [rsp+38h+DistanceToMoveHigh], 0
0x18003e5f4  xor     edx, edx; lDistanceToMove
0x18003e5f6  call    cs:__imp_SetFilePointer
0x18003e5fc  movsxd  rbx, eax
0x18003e5ff  cmp     ebx, 0FFFFFFFFh
0x18003e602  jnz     short loc_18003E612
0x18003e604  call    cs:__imp_GetLastError
0x18003e60a  test    eax, eax
0x18003e60c  jz      short loc_18003E612
0x18003e60e  xor     eax, eax
0x18003e610  jmp     short loc_18003E61E
0x18003e612  movsxd  rax, [rsp+38h+DistanceToMoveHigh]
0x18003e617  shl     rax, 20h
0x18003e61b  add     rax, rbx
0x18003e61e  mov     rcx, [rsp+38h+var_10]
0x18003e623  xor     rcx, rsp; StackCookie
0x18003e626  call    __security_check_cookie
0x18003e62b  add     rsp, 30h
0x18003e62f  pop     rbx
0x18003e630  retn
```
