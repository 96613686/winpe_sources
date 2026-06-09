# wil::details::shared_buffer::reset(void)

- ea: `0x180006598`
- end: `0x1800065f7`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003058`
- `0x180004fb8`
- `0x180006298`
- `0x180006600`

## callees

- `0x180006598`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065d0`

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
0x180006598  mov     [rsp+arg_0], rbx
0x18000659d  push    rdi
0x18000659e  sub     rsp, 20h
0x1800065a2  mov     rdi, rcx
0x1800065a5  mov     rcx, [rcx]
0x1800065a8  test    rcx, rcx
0x1800065ab  jz      short loc_1800065EB
0x1800065ad  or      eax, 0FFFFFFFFh
0x1800065b0  lock xadd [rcx], eax
0x1800065b4  cmp     eax, 1
0x1800065b7  jnz     short loc_1800065DC
0x1800065b9  mov     rbx, [rdi]
0x1800065bc  call    cs:__imp_GetProcessHeap
0x1800065c3  nop     dword ptr [rax+rax+00h]
0x1800065c8  mov     r8, rbx; lpMem
0x1800065cb  xor     edx, edx; dwFlags
0x1800065cd  mov     rcx, rax; hHeap
0x1800065d0  call    cs:__imp_HeapFree
0x1800065d7  nop     dword ptr [rax+rax+00h]
0x1800065dc  mov     qword ptr [rdi], 0
0x1800065e3  mov     qword ptr [rdi+8], 0
0x1800065eb  mov     rbx, [rsp+28h+arg_0]
0x1800065f0  add     rsp, 20h
0x1800065f4  pop     rdi
0x1800065f5  retn
```
