# wil::details::shared_buffer::reset(void)

- ea: `0x18000577c`
- end: `0x1800057ce`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031e0`
- `0x180004d78`
- `0x18000568c`
- `0x1800057e0`

## callees

- `0x18000577c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a0`

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
0x18000577c  mov     [rsp+arg_0], rbx
0x180005781  push    rdi
0x180005782  sub     rsp, 20h
0x180005786  mov     rdi, rcx
0x180005789  mov     rcx, [rcx]
0x18000578c  test    rcx, rcx
0x18000578f  jz      short loc_1800057C3
0x180005791  or      eax, 0FFFFFFFFh
0x180005794  lock xadd [rcx], eax
0x180005798  cmp     eax, 1
0x18000579b  jnz     short loc_1800057B4
0x18000579d  mov     rbx, [rdi]
0x1800057a0  call    cs:__imp_GetProcessHeap
0x1800057a6  mov     r8, rbx; lpMem
0x1800057a9  xor     edx, edx; dwFlags
0x1800057ab  mov     rcx, rax; hHeap
0x1800057ae  call    cs:__imp_HeapFree
0x1800057b4  mov     qword ptr [rdi], 0
0x1800057bb  mov     qword ptr [rdi+8], 0
0x1800057c3  mov     rbx, [rsp+28h+arg_0]
0x1800057c8  add     rsp, 20h
0x1800057cc  pop     rdi
0x1800057cd  retn
```
