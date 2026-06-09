# wil::details::shared_buffer::reset(void)

- ea: `0x140007f0c`
- end: `0x140007f5e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003498`
- `0x140006408`
- `0x140007954`
- `0x140007fa0`

## callees

- `0x140007f0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f30`

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
0x140007f0c  mov     [rsp+arg_0], rbx
0x140007f11  push    rdi
0x140007f12  sub     rsp, 20h
0x140007f16  mov     rdi, rcx
0x140007f19  mov     rcx, [rcx]
0x140007f1c  test    rcx, rcx
0x140007f1f  jz      short loc_140007F53
0x140007f21  or      eax, 0FFFFFFFFh
0x140007f24  lock xadd [rcx], eax
0x140007f28  cmp     eax, 1
0x140007f2b  jnz     short loc_140007F44
0x140007f2d  mov     rbx, [rdi]
0x140007f30  call    cs:__imp_GetProcessHeap
0x140007f36  mov     r8, rbx; lpMem
0x140007f39  xor     edx, edx; dwFlags
0x140007f3b  mov     rcx, rax; hHeap
0x140007f3e  call    cs:__imp_HeapFree
0x140007f44  mov     qword ptr [rdi], 0
0x140007f4b  mov     qword ptr [rdi+8], 0
0x140007f53  mov     rbx, [rsp+28h+arg_0]
0x140007f58  add     rsp, 20h
0x140007f5c  pop     rdi
0x140007f5d  retn
```
