# __vcrt_uninitialize_locks

- ea: `0x140002400`
- end: `0x140002437`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001fd0`
- `0x140001ff8`
- `0x1400023b8`

## callees

- `0x140002400`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000241f`
- `KERNEL32!DeleteCriticalSection` at `0x14000241f`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14001A198;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14001A170[5 * (unsigned int)--v0]);
    --dword_14001A198;
  }
  return 1;
}

```

## disassembly

```asm
0x140002400  push    rbx
0x140002402  sub     rsp, 20h
0x140002406  mov     ebx, cs:dword_14001A198
0x14000240c  jmp     short loc_14000242B
0x14000240e  lea     rax, qword_14001A170
0x140002415  dec     ebx
0x140002417  lea     rcx, [rbx+rbx*4]
0x14000241b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14000241f  call    cs:DeleteCriticalSection
0x140002425  dec     cs:dword_14001A198
0x14000242b  test    ebx, ebx
0x14000242d  jnz     short loc_14000240E
0x14000242f  mov     al, 1
0x140002431  add     rsp, 20h
0x140002435  pop     rbx
0x140002436  retn
```
