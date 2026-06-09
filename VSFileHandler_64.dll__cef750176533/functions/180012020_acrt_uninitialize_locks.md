# __acrt_uninitialize_locks

- ea: `0x180012020`
- end: `0x180012057`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011fb0`

## callees

- `0x180012020`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001203f`
- `KERNEL32!DeleteCriticalSection` at `0x18001203f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18003EB00;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18003E8D0[5 * (unsigned int)--v0]);
    --dword_18003EB00;
  }
  return 1;
}

```

## disassembly

```asm
0x180012020  push    rbx
0x180012022  sub     rsp, 20h
0x180012026  mov     ebx, cs:dword_18003EB00
0x18001202c  jmp     short loc_18001204B
0x18001202e  lea     rax, qword_18003E8D0
0x180012035  dec     ebx
0x180012037  lea     rcx, [rbx+rbx*4]
0x18001203b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001203f  call    cs:__imp_DeleteCriticalSection
0x180012045  dec     cs:dword_18003EB00
0x18001204b  test    ebx, ebx
0x18001204d  jnz     short loc_18001202E
0x18001204f  mov     al, 1
0x180012051  add     rsp, 20h
0x180012055  pop     rbx
0x180012056  retn
```
