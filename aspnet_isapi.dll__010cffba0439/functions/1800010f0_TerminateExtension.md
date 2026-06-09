# TerminateExtension

- ea: `0x1800010f0`
- end: `0x180001109`
- name: `TerminateExtension`
- size: `25`
- prototype: `BOOL __stdcall(DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001000`
- `0x18000111b`

## pseudocode

```c
BOOL __stdcall TerminateExtension(DWORD dwFlags)
{
  DisableUnloading();
  return AspNetTerminateExtension_0();
}

```

## disassembly

```asm
0x1800010f0  push    rbx
0x1800010f2  sub     rsp, 20h
0x1800010f6  mov     ebx, ecx
0x1800010f8  call    ?DisableUnloading@@YAXXZ
0x1800010fd  mov     ecx, ebx
0x1800010ff  add     rsp, 20h
0x180001103  pop     rbx
0x180001104  jmp     AspNetTerminateExtension_0
```
