# wil::details::shared_buffer::reset(void)

- ea: `0x14000792c`
- end: `0x14000797e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053f8`
- `0x140006dc8`
- `0x1400077d4`
- `0x140007990`
- `0x140008284`

## callees

- `0x14000792c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000795e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000795e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007950`

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
0x14000792c  mov     [rsp+arg_0], rbx
0x140007931  push    rdi
0x140007932  sub     rsp, 20h
0x140007936  mov     rdi, rcx
0x140007939  mov     rcx, [rcx]
0x14000793c  test    rcx, rcx
0x14000793f  jz      short loc_140007973
0x140007941  or      eax, 0FFFFFFFFh
0x140007944  lock xadd [rcx], eax
0x140007948  cmp     eax, 1
0x14000794b  jnz     short loc_140007964
0x14000794d  mov     rbx, [rdi]
0x140007950  call    cs:__imp_GetProcessHeap
0x140007956  mov     r8, rbx; lpMem
0x140007959  xor     edx, edx; dwFlags
0x14000795b  mov     rcx, rax; hHeap
0x14000795e  call    cs:__imp_HeapFree
0x140007964  mov     qword ptr [rdi], 0
0x14000796b  mov     qword ptr [rdi+8], 0
0x140007973  mov     rbx, [rsp+28h+arg_0]
0x140007978  add     rsp, 20h
0x14000797c  pop     rdi
0x14000797d  retn
```
