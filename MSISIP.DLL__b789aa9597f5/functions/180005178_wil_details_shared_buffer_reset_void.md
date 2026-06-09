# wil::details::shared_buffer::reset(void)

- ea: `0x180005178`
- end: `0x1800051ca`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005080`
- `0x180007450`
- `0x180008f80`
- `0x18000ae60`
- `0x18000c4d8`

## callees

- `0x180005178`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051aa`

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
0x180005178  mov     [rsp+arg_0], rbx
0x18000517d  push    rdi
0x18000517e  sub     rsp, 20h
0x180005182  mov     rdi, rcx
0x180005185  mov     rcx, [rcx]
0x180005188  test    rcx, rcx
0x18000518b  jz      short loc_1800051BF
0x18000518d  or      eax, 0FFFFFFFFh
0x180005190  lock xadd [rcx], eax
0x180005194  cmp     eax, 1
0x180005197  jnz     short loc_1800051B0
0x180005199  mov     rbx, [rdi]
0x18000519c  call    cs:__imp_GetProcessHeap
0x1800051a2  mov     r8, rbx; lpMem
0x1800051a5  xor     edx, edx; dwFlags
0x1800051a7  mov     rcx, rax; hHeap
0x1800051aa  call    cs:__imp_HeapFree
0x1800051b0  mov     qword ptr [rdi], 0
0x1800051b7  mov     qword ptr [rdi+8], 0
0x1800051bf  mov     rbx, [rsp+28h+arg_0]
0x1800051c4  add     rsp, 20h
0x1800051c8  pop     rdi
0x1800051c9  retn
```
