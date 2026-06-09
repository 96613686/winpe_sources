# wil::details::shared_buffer::reset(void)

- ea: `0x18000bab4`
- end: `0x18000bb06`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047b8`
- `0x18000957c`
- `0x18000b700`
- `0x18000bb10`

## callees

- `0x18000bab4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bad8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bae6`

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
0x18000bab4  mov     [rsp+arg_0], rbx
0x18000bab9  push    rdi
0x18000baba  sub     rsp, 20h
0x18000babe  mov     rdi, rcx
0x18000bac1  mov     rcx, [rcx]
0x18000bac4  test    rcx, rcx
0x18000bac7  jz      short loc_18000BAFB
0x18000bac9  or      eax, 0FFFFFFFFh
0x18000bacc  lock xadd [rcx], eax
0x18000bad0  cmp     eax, 1
0x18000bad3  jnz     short loc_18000BAEC
0x18000bad5  mov     rbx, [rdi]
0x18000bad8  call    cs:__imp_GetProcessHeap
0x18000bade  mov     r8, rbx; lpMem
0x18000bae1  xor     edx, edx; dwFlags
0x18000bae3  mov     rcx, rax; hHeap
0x18000bae6  call    cs:__imp_HeapFree
0x18000baec  mov     qword ptr [rdi], 0
0x18000baf3  mov     qword ptr [rdi+8], 0
0x18000bafb  mov     rbx, [rsp+28h+arg_0]
0x18000bb00  add     rsp, 20h
0x18000bb04  pop     rdi
0x18000bb05  retn
```
