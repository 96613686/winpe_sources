# wil::details::shared_buffer::reset(void)

- ea: `0x18000d64c`
- end: `0x18000d69e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008a0c`
- `0x180008d7c`
- `0x18000b508`
- `0x18000d184`
- `0x18000d980`

## callees

- `0x18000d64c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d67e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d67e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d670`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d670`

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
0x18000d64c  mov     [rsp+arg_0], rbx
0x18000d651  push    rdi
0x18000d652  sub     rsp, 20h
0x18000d656  mov     rdi, rcx
0x18000d659  mov     rcx, [rcx]
0x18000d65c  test    rcx, rcx
0x18000d65f  jz      short loc_18000D693
0x18000d661  or      eax, 0FFFFFFFFh
0x18000d664  lock xadd [rcx], eax
0x18000d668  cmp     eax, 1
0x18000d66b  jnz     short loc_18000D684
0x18000d66d  mov     rbx, [rdi]
0x18000d670  call    cs:__imp_GetProcessHeap
0x18000d676  mov     r8, rbx; lpMem
0x18000d679  xor     edx, edx; dwFlags
0x18000d67b  mov     rcx, rax; hHeap
0x18000d67e  call    cs:__imp_HeapFree
0x18000d684  mov     qword ptr [rdi], 0
0x18000d68b  mov     qword ptr [rdi+8], 0
0x18000d693  mov     rbx, [rsp+28h+arg_0]
0x18000d698  add     rsp, 20h
0x18000d69c  pop     rdi
0x18000d69d  retn
```
