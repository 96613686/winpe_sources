# wil::details::shared_buffer::reset(void)

- ea: `0x140009960`
- end: `0x1400099b2`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fe4`
- `0x140008608`
- `0x140009628`
- `0x1400099c0`

## callees

- `0x140009960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009992`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009984`

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
0x140009960  mov     [rsp+arg_0], rbx
0x140009965  push    rdi
0x140009966  sub     rsp, 20h
0x14000996a  mov     rdi, rcx
0x14000996d  mov     rcx, [rcx]
0x140009970  test    rcx, rcx
0x140009973  jz      short loc_1400099A7
0x140009975  or      eax, 0FFFFFFFFh
0x140009978  lock xadd [rcx], eax
0x14000997c  cmp     eax, 1
0x14000997f  jnz     short loc_140009998
0x140009981  mov     rbx, [rdi]
0x140009984  call    cs:__imp_GetProcessHeap
0x14000998a  mov     r8, rbx; lpMem
0x14000998d  xor     edx, edx; dwFlags
0x14000998f  mov     rcx, rax; hHeap
0x140009992  call    cs:__imp_HeapFree
0x140009998  mov     qword ptr [rdi], 0
0x14000999f  mov     qword ptr [rdi+8], 0
0x1400099a7  mov     rbx, [rsp+28h+arg_0]
0x1400099ac  add     rsp, 20h
0x1400099b0  pop     rdi
0x1400099b1  retn
```
