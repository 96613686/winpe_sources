# wil::details::shared_buffer::reset(void)

- ea: `0x140005fa8`
- end: `0x140005ffa`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003344`
- `0x140004f18`
- `0x140005bec`
- `0x140006000`

## callees

- `0x140005fa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005fcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005fcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005fda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005fda`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::reset(volatile signed __int32 **this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *this;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *this;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *this = 0;
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x140005fa8  mov     [rsp+arg_0], rbx
0x140005fad  push    rdi
0x140005fae  sub     rsp, 20h
0x140005fb2  mov     rdi, rcx
0x140005fb5  mov     rcx, [rcx]
0x140005fb8  test    rcx, rcx
0x140005fbb  jz      short loc_140005FEF
0x140005fbd  or      eax, 0FFFFFFFFh
0x140005fc0  lock xadd [rcx], eax
0x140005fc4  cmp     eax, 1
0x140005fc7  jnz     short loc_140005FE0
0x140005fc9  mov     rbx, [rdi]
0x140005fcc  call    cs:__imp_GetProcessHeap
0x140005fd2  mov     r8, rbx; lpMem
0x140005fd5  xor     edx, edx; dwFlags
0x140005fd7  mov     rcx, rax; hHeap
0x140005fda  call    cs:__imp_HeapFree
0x140005fe0  mov     qword ptr [rdi], 0
0x140005fe7  mov     qword ptr [rdi+8], 0
0x140005fef  mov     rbx, [rsp+28h+arg_0]
0x140005ff4  add     rsp, 20h
0x140005ff8  pop     rdi
0x140005ff9  retn
```
