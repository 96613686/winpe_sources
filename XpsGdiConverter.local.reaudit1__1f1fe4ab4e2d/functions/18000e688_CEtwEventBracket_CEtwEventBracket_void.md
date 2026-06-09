# CEtwEventBracket::~CEtwEventBracket(void)

- ea: `0x18000e688`
- end: `0x18000e6c4`
- name: `??1CEtwEventBracket@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CEtwEventBracket *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ecc0`
- `0x18000eee0`
- `0x18000f670`
- `0x18000fb70`
- `0x18000fd0c`
- `0x180010670`
- `0x1800474c5`
- `0x1800475aa`
- `0x18004768e`
- `0x1800476f2`
- `0x18004773a`

## callees

- `0x18000e688`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x18000e69c`
- `ADVAPI32!EventEnabled` at `0x18000e69c`
- `ADVAPI32!EventWrite` at `0x18000e6b3`
- `ADVAPI32!EventWrite` at `0x18000e6b3`

## pseudocode

```c
void __fastcall CEtwEventBracket::~CEtwEventBracket(CEtwEventBracket *this)
{
  if ( EventEnabled(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8)) )
    EventWrite(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8), 0, 0);
}

```

## disassembly

```asm
0x18000e688  mov     [rsp+arg_0], rbx
0x18000e68d  push    rdi
0x18000e68e  sub     rsp, 20h
0x18000e692  mov     rbx, rcx
0x18000e695  lea     rdx, [rcx+8]; EventDescriptor
0x18000e699  mov     rcx, [rcx]; RegHandle
0x18000e69c  call    cs:__imp_EventEnabled
0x18000e6a2  test    al, al
0x18000e6a4  jz      short loc_18000E6B9
0x18000e6a6  mov     rcx, [rbx]; RegHandle
0x18000e6a9  lea     rdx, [rbx+8]; EventDescriptor
0x18000e6ad  xor     r9d, r9d; UserData
0x18000e6b0  xor     r8d, r8d; UserDataCount
0x18000e6b3  call    cs:__imp_EventWrite
0x18000e6b9  mov     rbx, [rsp+28h+arg_0]
0x18000e6be  add     rsp, 20h
0x18000e6c2  pop     rdi
0x18000e6c3  retn
```
