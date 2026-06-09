# _ResourceStringAllocCopyExCoAlloc

- ea: `0x180017ddc`
- end: `0x180017e05`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: `__int64 __fastcall(__int64, SIZE_T, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017d2c`

## callees

- `0x180017ddc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017de8`

## pseudocode

```c
__int64 __fastcall ResourceStringAllocCopyExCoAlloc(__int64 a1, SIZE_T a2, _QWORD *a3)
{
  LPVOID v4; // rax

  v4 = CoTaskMemAlloc(a2);
  if ( !v4 )
    return 2147942414LL;
  *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x180017ddc  push    rbx
0x180017dde  sub     rsp, 20h
0x180017de2  mov     rcx, rdx; cb
0x180017de5  mov     rbx, r8
0x180017de8  call    cs:__imp_CoTaskMemAlloc
0x180017dee  test    rax, rax
0x180017df1  jz      short loc_180017DFA
0x180017df3  mov     [rbx], rax
0x180017df6  xor     eax, eax
0x180017df8  jmp     short loc_180017DFF
0x180017dfa  mov     eax, 8007000Eh
0x180017dff  add     rsp, 20h
0x180017e03  pop     rbx
0x180017e04  retn
```
