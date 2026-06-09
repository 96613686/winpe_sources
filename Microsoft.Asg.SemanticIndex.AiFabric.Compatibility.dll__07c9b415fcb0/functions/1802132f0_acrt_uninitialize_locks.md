# __acrt_uninitialize_locks

- ea: `0x1802132f0`
- end: `0x180213327`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180213280`

## callees

- `0x1802132f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18021330f`
- `KERNEL32!DeleteCriticalSection` at `0x18021330f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1803E1DF8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1803E1BA0[5 * (unsigned int)--v0]);
    --dword_1803E1DF8;
  }
  return 1;
}

```

## disassembly

```asm
0x1802132f0  push    rbx
0x1802132f2  sub     rsp, 20h
0x1802132f6  mov     ebx, cs:dword_1803E1DF8
0x1802132fc  jmp     short loc_18021331B
0x1802132fe  lea     rax, qword_1803E1BA0
0x180213305  dec     ebx
0x180213307  lea     rcx, [rbx+rbx*4]
0x18021330b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18021330f  call    cs:__imp_DeleteCriticalSection
0x180213315  dec     cs:dword_1803E1DF8
0x18021331b  test    ebx, ebx
0x18021331d  jnz     short loc_1802132FE
0x18021331f  mov     al, 1
0x180213321  add     rsp, 20h
0x180213325  pop     rbx
0x180213326  retn
```
