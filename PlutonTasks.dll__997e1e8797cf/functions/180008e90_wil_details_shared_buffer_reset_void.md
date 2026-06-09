# wil::details::shared_buffer::reset(void)

- ea: `0x180008e90`
- end: `0x180008ee2`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003914`
- `0x180007798`
- `0x180008a68`
- `0x180008ef0`

## callees

- `0x180008e90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ec2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eb4`

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
0x180008e90  mov     [rsp+arg_0], rbx
0x180008e95  push    rdi
0x180008e96  sub     rsp, 20h
0x180008e9a  mov     rdi, rcx
0x180008e9d  mov     rcx, [rcx]
0x180008ea0  test    rcx, rcx
0x180008ea3  jz      short loc_180008ED7
0x180008ea5  or      eax, 0FFFFFFFFh
0x180008ea8  lock xadd [rcx], eax
0x180008eac  cmp     eax, 1
0x180008eaf  jnz     short loc_180008EC8
0x180008eb1  mov     rbx, [rdi]
0x180008eb4  call    cs:__imp_GetProcessHeap
0x180008eba  mov     r8, rbx; lpMem
0x180008ebd  xor     edx, edx; dwFlags
0x180008ebf  mov     rcx, rax; hHeap
0x180008ec2  call    cs:__imp_HeapFree
0x180008ec8  mov     qword ptr [rdi], 0
0x180008ecf  mov     qword ptr [rdi+8], 0
0x180008ed7  mov     rbx, [rsp+28h+arg_0]
0x180008edc  add     rsp, 20h
0x180008ee0  pop     rdi
0x180008ee1  retn
```
