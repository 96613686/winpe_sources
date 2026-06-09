# wil::details::shared_buffer::reset(void)

- ea: `0x180009ee8`
- end: `0x180009f3a`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000750c`
- `0x180009378`
- `0x180009d0c`
- `0x180009f40`

## callees

- `0x180009ee8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f0c`

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
0x180009ee8  mov     [rsp+arg_0], rbx
0x180009eed  push    rdi
0x180009eee  sub     rsp, 20h
0x180009ef2  mov     rdi, rcx
0x180009ef5  mov     rcx, [rcx]
0x180009ef8  test    rcx, rcx
0x180009efb  jz      short loc_180009F2F
0x180009efd  or      eax, 0FFFFFFFFh
0x180009f00  lock xadd [rcx], eax
0x180009f04  cmp     eax, 1
0x180009f07  jnz     short loc_180009F20
0x180009f09  mov     rbx, [rdi]
0x180009f0c  call    cs:__imp_GetProcessHeap
0x180009f12  mov     r8, rbx; lpMem
0x180009f15  xor     edx, edx; dwFlags
0x180009f17  mov     rcx, rax; hHeap
0x180009f1a  call    cs:__imp_HeapFree
0x180009f20  mov     qword ptr [rdi], 0
0x180009f27  mov     qword ptr [rdi+8], 0
0x180009f2f  mov     rbx, [rsp+28h+arg_0]
0x180009f34  add     rsp, 20h
0x180009f38  pop     rdi
0x180009f39  retn
```
