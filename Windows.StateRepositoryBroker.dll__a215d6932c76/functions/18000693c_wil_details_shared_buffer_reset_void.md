# wil::details::shared_buffer::reset(void)

- ea: `0x18000693c`
- end: `0x18000698e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fec`
- `0x18000629c`
- `0x180006838`
- `0x1800069a0`

## callees

- `0x18000693c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006960`

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
0x18000693c  mov     [rsp+arg_0], rbx
0x180006941  push    rdi
0x180006942  sub     rsp, 20h
0x180006946  mov     rdi, rcx
0x180006949  mov     rcx, [rcx]
0x18000694c  test    rcx, rcx
0x18000694f  jz      short loc_180006983
0x180006951  or      eax, 0FFFFFFFFh
0x180006954  lock xadd [rcx], eax
0x180006958  cmp     eax, 1
0x18000695b  jnz     short loc_180006974
0x18000695d  mov     rbx, [rdi]
0x180006960  call    cs:__imp_GetProcessHeap
0x180006966  mov     r8, rbx; lpMem
0x180006969  xor     edx, edx; dwFlags
0x18000696b  mov     rcx, rax; hHeap
0x18000696e  call    cs:__imp_HeapFree
0x180006974  mov     qword ptr [rdi], 0
0x18000697b  mov     qword ptr [rdi+8], 0
0x180006983  mov     rbx, [rsp+28h+arg_0]
0x180006988  add     rsp, 20h
0x18000698c  pop     rdi
0x18000698d  retn
```
