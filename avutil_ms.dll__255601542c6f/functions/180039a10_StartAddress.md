# StartAddress

- ea: `0x180039a10`
- end: `0x180039a33`
- name: `StartAddress`
- size: `35`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007a900`

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
0x180039a10  push    rbx
0x180039a12  sub     rsp, 20h
0x180039a16  mov     rbx, rcx
0x180039a19  mov     rcx, [rcx+10h]
0x180039a1d  mov     rax, [rbx+8]
0x180039a21  call    cs:__guard_dispatch_icall_fptr
0x180039a27  mov     [rbx+18h], rax
0x180039a2b  xor     eax, eax
0x180039a2d  add     rsp, 20h
0x180039a31  pop     rbx
0x180039a32  retn
```
