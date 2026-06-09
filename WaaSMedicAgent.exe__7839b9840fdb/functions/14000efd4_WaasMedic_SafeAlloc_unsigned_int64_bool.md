# WaasMedic::SafeAlloc(unsigned __int64,bool)

- ea: `0x14000efd4`
- end: `0x14000effa`
- name: `?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z`
- size: `38`
- prototype: `LPVOID __fastcall(WaasMedic *this)`
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x14000f000`
- `0x14000f160`
- `0x14000f3ec`
- `0x14000fa3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000eff3`

## pseudocode

```c
LPVOID __fastcall WaasMedic::SafeAlloc(WaasMedic *this)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, (SIZE_T)this);
}

```

## disassembly

```asm
0x14000efd4  push    rbx
0x14000efd6  sub     rsp, 20h
0x14000efda  mov     rbx, rcx
0x14000efdd  call    cs:__imp_GetProcessHeap
0x14000efe3  mov     r8, rbx
0x14000efe6  mov     edx, 8
0x14000efeb  mov     rcx, rax
0x14000efee  add     rsp, 20h
0x14000eff2  pop     rbx
0x14000eff3  jmp     cs:__imp_HeapAlloc
```
