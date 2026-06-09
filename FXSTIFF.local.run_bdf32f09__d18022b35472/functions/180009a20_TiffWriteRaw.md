# TiffWriteRaw

- ea: `0x180009a20`
- end: `0x180009a76`
- name: `TiffWriteRaw`
- size: `86`
- prototype: `__int64 __fastcall(__int64, const void *, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d80`
- `0x18000ac38`
- `0x18000b604`

## callees

- `0x180009a20`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180009a48`
- `KERNEL32!WriteFile` at `0x180009a48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffWriteRaw(__int64 a1, const void *a2, DWORD a3)
{
  __int64 result; // rax
  DWORD v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  WriteFile(*(HANDLE *)a1, a2, a3, &v6, 0);
  *(_DWORD *)(a1 + 856) += v6;
  result = 1;
  if ( a3 == 216 )
    ++*(_DWORD *)(a1 + 848);
  return result;
}

```

## disassembly

```asm
0x180009a20  mov     rax, rsp
0x180009a23  mov     [rax+8], rbx
0x180009a27  push    rdi
0x180009a28  sub     rsp, 30h
0x180009a2c  mov     rdi, rcx
0x180009a2f  mov     dword ptr [rax+18h], 0
0x180009a36  mov     rcx, [rcx]; hFile
0x180009a39  lea     r9, [rax+18h]; lpNumberOfBytesWritten
0x180009a3d  mov     ebx, r8d
0x180009a40  mov     qword ptr [rax-18h], 0
0x180009a48  call    cs:__imp_WriteFile
0x180009a4e  mov     eax, [rsp+38h+arg_10]
0x180009a52  add     [rdi+358h], eax
0x180009a58  mov     eax, 1
0x180009a5d  cmp     ebx, 0D8h
0x180009a63  jnz     short loc_180009A6B
0x180009a65  add     [rdi+350h], eax
0x180009a6b  mov     rbx, [rsp+38h+arg_0]
0x180009a70  add     rsp, 30h
0x180009a74  pop     rdi
0x180009a75  retn
```
