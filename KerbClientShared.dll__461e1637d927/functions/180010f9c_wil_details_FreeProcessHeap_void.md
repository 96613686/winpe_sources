# wil::details::FreeProcessHeap(void *)

- ea: `0x180010f9c`
- end: `0x180010fbf`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d0e8`
- `0x18000d1e4`
- `0x18000d29c`
- `0x18000d884`
- `0x18000dc68`
- `0x18000e668`
- `0x18000e70c`
- `0x1800105cc`
- `0x1800122b8`
- `0x1800123dc`
- `0x180012cf0`
- `0x18001331c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fb8`

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
0x180010f9c  push    rbx
0x180010f9e  sub     rsp, 20h
0x180010fa2  mov     rbx, rcx
0x180010fa5  call    cs:__imp_GetProcessHeap
0x180010fab  mov     r8, rbx
0x180010fae  xor     edx, edx
0x180010fb0  mov     rcx, rax
0x180010fb3  add     rsp, 20h
0x180010fb7  pop     rbx
0x180010fb8  jmp     cs:__imp_HeapFree
```
