# wil::details::shared_buffer::reset(void)

- ea: `0x1800076e8`
- end: `0x18000773a`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800051dc`
- `0x180006e7c`
- `0x1800075f8`
- `0x180007740`

## callees

- `0x1800076e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000770c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000770c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000771a`

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
0x1800076e8  mov     [rsp+arg_0], rbx
0x1800076ed  push    rdi
0x1800076ee  sub     rsp, 20h
0x1800076f2  mov     rdi, rcx
0x1800076f5  mov     rcx, [rcx]
0x1800076f8  test    rcx, rcx
0x1800076fb  jz      short loc_18000772F
0x1800076fd  or      eax, 0FFFFFFFFh
0x180007700  lock xadd [rcx], eax
0x180007704  cmp     eax, 1
0x180007707  jnz     short loc_180007720
0x180007709  mov     rbx, [rdi]
0x18000770c  call    cs:__imp_GetProcessHeap
0x180007712  mov     r8, rbx; lpMem
0x180007715  xor     edx, edx; dwFlags
0x180007717  mov     rcx, rax; hHeap
0x18000771a  call    cs:__imp_HeapFree
0x180007720  mov     qword ptr [rdi], 0
0x180007727  mov     qword ptr [rdi+8], 0
0x18000772f  mov     rbx, [rsp+28h+arg_0]
0x180007734  add     rsp, 20h
0x180007738  pop     rdi
0x180007739  retn
```
