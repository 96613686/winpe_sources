# wil::details::shared_buffer::reset(void)

- ea: `0x1400075b0`
- end: `0x140007602`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031ac`
- `0x14000629c`
- `0x140007238`
- `0x140007610`

## callees

- `0x1400075b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075e2`

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
0x1400075b0  mov     [rsp+arg_0], rbx
0x1400075b5  push    rdi
0x1400075b6  sub     rsp, 20h
0x1400075ba  mov     rdi, rcx
0x1400075bd  mov     rcx, [rcx]
0x1400075c0  test    rcx, rcx
0x1400075c3  jz      short loc_1400075F7
0x1400075c5  or      eax, 0FFFFFFFFh
0x1400075c8  lock xadd [rcx], eax
0x1400075cc  cmp     eax, 1
0x1400075cf  jnz     short loc_1400075E8
0x1400075d1  mov     rbx, [rdi]
0x1400075d4  call    cs:__imp_GetProcessHeap
0x1400075da  mov     r8, rbx; lpMem
0x1400075dd  xor     edx, edx; dwFlags
0x1400075df  mov     rcx, rax; hHeap
0x1400075e2  call    cs:__imp_HeapFree
0x1400075e8  mov     qword ptr [rdi], 0
0x1400075ef  mov     qword ptr [rdi+8], 0
0x1400075f7  mov     rbx, [rsp+28h+arg_0]
0x1400075fc  add     rsp, 20h
0x140007600  pop     rdi
0x140007601  retn
```
