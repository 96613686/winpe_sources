# CReadWrite::~CReadWrite(void)

- ea: `0x18000b1c0`
- end: `0x18000b1e2`
- name: `??1CReadWrite@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(CReadWrite *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c210`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000b1cd`
- `KERNEL32!CloseHandle` at `0x18000b1cd`
- `KERNEL32!CloseHandle` at `0x18000b1db`

## pseudocode

```c
void __fastcall CReadWrite::~CReadWrite(HANDLE *this)
{
  CloseHandle(this[1]);
  CloseHandle(*this);
}

```

## disassembly

```asm
0x18000b1c0  push    rbx
0x18000b1c2  sub     rsp, 20h
0x18000b1c6  mov     rbx, rcx
0x18000b1c9  mov     rcx, [rcx+8]; hObject
0x18000b1cd  call    cs:__imp_CloseHandle
0x18000b1d3  mov     rcx, [rbx]
0x18000b1d6  add     rsp, 20h
0x18000b1da  pop     rbx
0x18000b1db  jmp     cs:__imp_CloseHandle
```
