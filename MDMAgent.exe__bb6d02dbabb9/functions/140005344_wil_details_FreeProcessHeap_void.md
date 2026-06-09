# wil::details::FreeProcessHeap(void *)

- ea: `0x140005344`
- end: `0x140005372`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `46`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140004b74`
- `0x140006510`
- `0x140009548`
- `0x1400095ec`
- `0x140009628`
- `0x1400096e4`
- `0x14000c1a0`
- `0x14000d19c`
- `0x14000d480`
- `0x14001052c`
- `0x140010c4c`
- `0x140011cd0`
- `0x140018438`
- `0x140018d74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000534d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000534d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005366`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x140005344  push    rbx
0x140005346  sub     rsp, 20h
0x14000534a  mov     rbx, rcx
0x14000534d  call    cs:__imp_GetProcessHeap
0x140005354  nop     dword ptr [rax+rax+00h]
0x140005359  mov     r8, rbx
0x14000535c  xor     edx, edx
0x14000535e  mov     rcx, rax
0x140005361  add     rsp, 20h
0x140005365  pop     rbx
0x140005366  jmp     cs:__imp_HeapFree
```
