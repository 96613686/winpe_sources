# StartAddress

- ea: `0x180011c10`
- end: `0x180011c33`
- name: `StartAddress`
- size: `35`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180024140`

## pseudocode

```c
__int64 __fastcall StartAddress(_QWORD *lpThreadParameter)
{
  lpThreadParameter[3] = ((__int64 (__fastcall *)(_QWORD))lpThreadParameter[1])(lpThreadParameter[2]);
  return 0;
}

```

## disassembly

```asm
0x180011c10  push    rbx
0x180011c12  sub     rsp, 20h
0x180011c16  mov     rbx, rcx
0x180011c19  mov     rcx, [rcx+10h]
0x180011c1d  mov     rax, [rbx+8]
0x180011c21  call    cs:__guard_dispatch_icall_fptr
0x180011c27  mov     [rbx+18h], rax
0x180011c2b  xor     eax, eax
0x180011c2d  add     rsp, 20h
0x180011c31  pop     rbx
0x180011c32  retn
```
