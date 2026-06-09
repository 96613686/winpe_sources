# wil::details::shared_buffer::reset(void)

- ea: `0x140008344`
- end: `0x1400083a3`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003508`
- `0x1400067c8`
- `0x140007d70`
- `0x140008480`

## callees

- `0x140008344`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000837c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000837c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008368`

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
0x140008344  mov     [rsp+arg_0], rbx
0x140008349  push    rdi
0x14000834a  sub     rsp, 20h
0x14000834e  mov     rdi, rcx
0x140008351  mov     rcx, [rcx]
0x140008354  test    rcx, rcx
0x140008357  jz      short loc_140008397
0x140008359  or      eax, 0FFFFFFFFh
0x14000835c  lock xadd [rcx], eax
0x140008360  cmp     eax, 1
0x140008363  jnz     short loc_140008388
0x140008365  mov     rbx, [rdi]
0x140008368  call    cs:__imp_GetProcessHeap
0x14000836f  nop     dword ptr [rax+rax+00h]
0x140008374  mov     r8, rbx; lpMem
0x140008377  xor     edx, edx; dwFlags
0x140008379  mov     rcx, rax; hHeap
0x14000837c  call    cs:__imp_HeapFree
0x140008383  nop     dword ptr [rax+rax+00h]
0x140008388  mov     qword ptr [rdi], 0
0x14000838f  mov     qword ptr [rdi+8], 0
0x140008397  mov     rbx, [rsp+28h+arg_0]
0x14000839c  add     rsp, 20h
0x1400083a0  pop     rdi
0x1400083a1  retn
```
