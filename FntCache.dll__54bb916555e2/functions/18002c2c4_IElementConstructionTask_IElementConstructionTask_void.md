# IElementConstructionTask::~IElementConstructionTask(void)

- ea: `0x18002c2c4`
- end: `0x18002c2f6`
- name: `??1IElementConstructionTask@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(IElementConstructionTask *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002c720`
- `0x180095c3c`
- `0x1800961dc`
- `0x1800a4cd0`
- `0x1800a58e4`
- `0x1800b77c0`
- `0x1800b7840`
- `0x1800b78e0`
- `0x1800c6310`
- `0x1800c6c00`
- `0x1800c6d10`
- `0x1800c6e20`
- `0x1800c6f30`
- `0x1800de049`
- `0x1800e0539`
- `0x1800e0e8d`
- `0x1800e56b1`
- `0x1800e56e6`

## callees

- `0x18002bc8c`
- `0x18002c2c4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c2ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c2ee`

## pseudocode

```c
void __fastcall IElementConstructionTask::~IElementConstructionTask(IElementConstructionTask *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &IElementConstructionTask::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CloseHandle(v2);
  IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>((__int64 *)this + 11);
}

```

## disassembly

```asm
0x18002c2c4  push    rbx
0x18002c2c6  sub     rsp, 20h
0x18002c2ca  lea     rax, ??_7IElementConstructionTask@@6B@; const IElementConstructionTask::`vftable'
0x18002c2d1  mov     rbx, rcx
0x18002c2d4  mov     [rcx], rax
0x18002c2d7  mov     rcx, [rcx+18h]; hObject
0x18002c2db  test    rcx, rcx
0x18002c2de  jnz     short loc_18002C2EE
0x18002c2e0  lea     rcx, [rbx+58h]
0x18002c2e4  add     rsp, 20h
0x18002c2e8  pop     rbx
0x18002c2e9  jmp     ??1?$IntrusivePtr@VICacheReference@@@@QEAA@XZ; IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(void)
0x18002c2ee  call    cs:__imp_CloseHandle
0x18002c2f4  jmp     short loc_18002C2E0
```
