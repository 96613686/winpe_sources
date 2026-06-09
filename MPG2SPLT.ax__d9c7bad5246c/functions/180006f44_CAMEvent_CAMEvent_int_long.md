# CAMEvent::CAMEvent(int,long *)

- ea: `0x180006f44`
- end: `0x180006f87`
- name: `??0CAMEvent@@QEAA@HPEAJ@Z`
- size: `67`
- prototype: `CAMEvent *__fastcall(CAMEvent *__hidden this, int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f90`
- `0x180032fbc`

## callees

- `0x180006f44`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180006f5c`
- `KERNEL32!CreateEventW` at `0x180006f5c`

## pseudocode

```c
CAMEvent *__fastcall CAMEvent::CAMEvent(CAMEvent *this, BOOL a2, int *a3)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, a2, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW && a3 && *a3 >= 0 )
    *a3 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x180006f44  mov     [rsp+arg_0], rbx
0x180006f49  push    rdi
0x180006f4a  sub     rsp, 20h
0x180006f4e  mov     rbx, r8
0x180006f51  mov     rdi, rcx
0x180006f54  xor     r8d, r8d; bInitialState
0x180006f57  xor     ecx, ecx; lpEventAttributes
0x180006f59  xor     r9d, r9d; lpName
0x180006f5c  call    cs:__imp_CreateEventW
0x180006f62  mov     [rdi], rax
0x180006f65  test    rax, rax
0x180006f68  jnz     short loc_180006F79
0x180006f6a  test    rbx, rbx
0x180006f6d  jz      short loc_180006F79
0x180006f6f  cmp     [rbx], eax
0x180006f71  jl      short loc_180006F79
0x180006f73  mov     dword ptr [rbx], 8007000Eh
0x180006f79  mov     rbx, [rsp+28h+arg_0]
0x180006f7e  mov     rax, rdi
0x180006f81  add     rsp, 20h
0x180006f85  pop     rdi
0x180006f86  retn
```
