# CReadWriteLock::~CReadWriteLock(void)

- ea: `0x18000f094`
- end: `0x18000f0c2`
- name: `??1CReadWriteLock@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800101a0`

## callees

- `0x18000f094`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000f0a6`
- `KERNEL32!CloseHandle` at `0x18000f0b5`
- `KERNEL32!CloseHandle` at `0x18000f0a6`
- `KERNEL32!CloseHandle` at `0x18000f0b5`

## pseudocode

```c
void __fastcall CReadWriteLock::~CReadWriteLock(CReadWriteLock *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x18000f094  push    rbx
0x18000f096  sub     rsp, 20h
0x18000f09a  mov     rbx, rcx
0x18000f09d  mov     rcx, [rcx+8]; hObject
0x18000f0a1  test    rcx, rcx
0x18000f0a4  jz      short loc_18000F0AC
0x18000f0a6  call    cs:__imp_CloseHandle
0x18000f0ac  mov     rcx, [rbx+10h]; hObject
0x18000f0b0  test    rcx, rcx
0x18000f0b3  jz      short loc_18000F0BC
0x18000f0b5  call    cs:__imp_CloseHandle
0x18000f0bb  nop
0x18000f0bc  add     rsp, 20h
0x18000f0c0  pop     rbx
0x18000f0c1  retn
```
