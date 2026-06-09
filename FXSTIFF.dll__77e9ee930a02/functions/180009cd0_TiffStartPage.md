# TiffStartPage

- ea: `0x180009cd0`
- end: `0x180009d2b`
- name: `TiffStartPage`
- size: `91`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005ed0`
- `0x18000b120`
- `0x18000bb50`

## callees

- `0x180009cd0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180009ce7`
- `KERNEL32!SetFilePointer` at `0x180009ce7`

## pseudocode

```c
__int64 __fastcall TiffStartPage(__int64 a1)
{
  DWORD v2; // eax
  __int64 result; // rax

  v2 = SetFilePointer(*(HANDLE *)a1, 0, 0, 1u);
  *(_DWORD *)(a1 + 840) = v2;
  if ( v2 == -1 )
  {
    result = 0;
    *(_DWORD *)(a1 + 840) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 1616) = 0;
    *(_QWORD *)(a1 + 1608) = 0;
    *(_QWORD *)(a1 + 1600) = 0;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180009cd0  push    rbx
0x180009cd2  sub     rsp, 20h
0x180009cd6  mov     rbx, rcx
0x180009cd9  mov     r9d, 1; dwMoveMethod
0x180009cdf  mov     rcx, [rcx]; hFile
0x180009ce2  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009ce5  xor     edx, edx; lDistanceToMove
0x180009ce7  call    cs:__imp_SetFilePointer
0x180009cee  nop     dword ptr [rax+rax+00h]
0x180009cf3  mov     [rbx+348h], eax
0x180009cf9  cmp     eax, 0FFFFFFFFh
0x180009cfc  jnz     short loc_180009D08
0x180009cfe  xor     eax, eax
0x180009d00  mov     [rbx+348h], eax
0x180009d06  jmp     short loc_180009D24
0x180009d08  xor     eax, eax
0x180009d0a  mov     [rbx+650h], rax
0x180009d11  mov     [rbx+648h], rax
0x180009d18  mov     [rbx+640h], rax
0x180009d1f  mov     eax, 1
0x180009d24  add     rsp, 20h
0x180009d28  pop     rbx
0x180009d29  retn
```
