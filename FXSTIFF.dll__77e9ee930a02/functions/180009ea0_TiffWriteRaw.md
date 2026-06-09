# TiffWriteRaw

- ea: `0x180009ea0`
- end: `0x180009efd`
- name: `TiffWriteRaw`
- size: `93`
- prototype: `__int64 __fastcall(__int64, const void *, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005ed0`
- `0x18000b120`
- `0x18000bb50`

## callees

- `0x180009ea0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180009ec8`
- `KERNEL32!WriteFile` at `0x180009ec8`

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
0x180009ea0  mov     rax, rsp
0x180009ea3  mov     [rax+8], rbx
0x180009ea7  push    rdi
0x180009ea8  sub     rsp, 30h
0x180009eac  mov     rdi, rcx
0x180009eaf  mov     dword ptr [rax+18h], 0
0x180009eb6  mov     rcx, [rcx]; hFile
0x180009eb9  lea     r9, [rax+18h]; lpNumberOfBytesWritten
0x180009ebd  mov     ebx, r8d
0x180009ec0  mov     qword ptr [rax-18h], 0
0x180009ec8  call    cs:__imp_WriteFile
0x180009ecf  nop     dword ptr [rax+rax+00h]
0x180009ed4  mov     eax, [rsp+38h+arg_10]
0x180009ed8  add     [rdi+358h], eax
0x180009ede  mov     eax, 1
0x180009ee3  cmp     ebx, 0D8h
0x180009ee9  jnz     short loc_180009EF1
0x180009eeb  add     [rdi+350h], eax
0x180009ef1  mov     rbx, [rsp+38h+arg_0]
0x180009ef6  add     rsp, 30h
0x180009efa  pop     rdi
0x180009efb  retn
```
