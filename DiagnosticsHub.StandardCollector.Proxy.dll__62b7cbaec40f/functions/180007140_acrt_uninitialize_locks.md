# __acrt_uninitialize_locks

- ea: `0x180007140`
- end: `0x180007177`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d0`

## callees

- `0x180007140`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000715f`
- `KERNEL32!DeleteCriticalSection` at `0x18000715f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18007BEB8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18007BC60[5 * (unsigned int)--v0]);
    --dword_18007BEB8;
  }
  return 1;
}

```

## disassembly

```asm
0x180007140  push    rbx
0x180007142  sub     rsp, 20h
0x180007146  mov     ebx, cs:dword_18007BEB8
0x18000714c  jmp     short loc_18000716B
0x18000714e  lea     rax, qword_18007BC60
0x180007155  dec     ebx
0x180007157  lea     rcx, [rbx+rbx*4]
0x18000715b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000715f  call    cs:__imp_DeleteCriticalSection
0x180007165  dec     cs:dword_18007BEB8
0x18000716b  test    ebx, ebx
0x18000716d  jnz     short loc_18000714E
0x18000716f  mov     al, 1
0x180007171  add     rsp, 20h
0x180007175  pop     rbx
0x180007176  retn
```
