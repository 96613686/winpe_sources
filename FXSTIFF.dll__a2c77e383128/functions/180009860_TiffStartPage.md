# TiffStartPage

- ea: `0x180009860`
- end: `0x1800098b4`
- name: `TiffStartPage`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d80`
- `0x18000ac38`
- `0x18000b604`

## callees

- `0x180009860`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180009877`
- `KERNEL32!SetFilePointer` at `0x180009877`

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
0x180009860  push    rbx
0x180009862  sub     rsp, 20h
0x180009866  mov     rbx, rcx
0x180009869  mov     r9d, 1; dwMoveMethod
0x18000986f  mov     rcx, [rcx]; hFile
0x180009872  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009875  xor     edx, edx; lDistanceToMove
0x180009877  call    cs:__imp_SetFilePointer
0x18000987d  mov     [rbx+348h], eax
0x180009883  cmp     eax, 0FFFFFFFFh
0x180009886  jnz     short loc_180009892
0x180009888  xor     eax, eax
0x18000988a  mov     [rbx+348h], eax
0x180009890  jmp     short loc_1800098AE
0x180009892  xor     eax, eax
0x180009894  mov     [rbx+650h], rax
0x18000989b  mov     [rbx+648h], rax
0x1800098a2  mov     [rbx+640h], rax
0x1800098a9  mov     eax, 1
0x1800098ae  add     rsp, 20h
0x1800098b2  pop     rbx
0x1800098b3  retn
```
