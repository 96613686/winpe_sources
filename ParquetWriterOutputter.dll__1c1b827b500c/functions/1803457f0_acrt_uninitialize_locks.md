# __acrt_uninitialize_locks

- ea: `0x1803457f0`
- end: `0x180345827`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180345780`

## callees

- `0x1803457f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18034580f`
- `KERNEL32!DeleteCriticalSection` at `0x18034580f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1804C7478;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1804C7270[5 * (unsigned int)--v0]);
    --dword_1804C7478;
  }
  return 1;
}

```

## disassembly

```asm
0x1803457f0  push    rbx
0x1803457f2  sub     rsp, 20h
0x1803457f6  mov     ebx, cs:dword_1804C7478
0x1803457fc  jmp     short loc_18034581B
0x1803457fe  lea     rax, qword_1804C7270
0x180345805  dec     ebx
0x180345807  lea     rcx, [rbx+rbx*4]
0x18034580b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18034580f  call    cs:__imp_DeleteCriticalSection
0x180345815  dec     cs:dword_1804C7478
0x18034581b  test    ebx, ebx
0x18034581d  jnz     short loc_1803457FE
0x18034581f  mov     al, 1
0x180345821  add     rsp, 20h
0x180345825  pop     rbx
0x180345826  retn
```
