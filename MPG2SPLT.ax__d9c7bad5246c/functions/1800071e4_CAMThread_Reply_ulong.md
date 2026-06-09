# CAMThread::Reply(ulong)

- ea: `0x1800071e4`
- end: `0x18000720e`
- name: `?Reply@CAMThread@@QEAAXK@Z`
- size: `42`
- prototype: `void __fastcall(CAMThread *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ee80`
- `0x18001bdf0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007207`
- `KERNEL32!ResetEvent` at `0x1800071f8`
- `KERNEL32!ResetEvent` at `0x1800071f8`

## pseudocode

```c
void __fastcall CAMThread::Reply(CAMThread *this)
{
  *((_DWORD *)this + 7) = 0;
  ResetEvent(*((HANDLE *)this + 1));
  SetEvent(*((HANDLE *)this + 2));
}

```

## disassembly

```asm
0x1800071e4  push    rbx
0x1800071e6  sub     rsp, 20h
0x1800071ea  mov     rbx, rcx
0x1800071ed  mov     dword ptr [rcx+1Ch], 0
0x1800071f4  mov     rcx, [rcx+8]; hEvent
0x1800071f8  call    cs:__imp_ResetEvent
0x1800071fe  mov     rcx, [rbx+10h]
0x180007202  add     rsp, 20h
0x180007206  pop     rbx
0x180007207  jmp     cs:__imp_SetEvent
```
