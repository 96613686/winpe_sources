# rc4_safe_shutdown

- ea: `0x180064fd4`
- end: `0x180065038`
- name: `rc4_safe_shutdown`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180041b14`
- `0x1800471ac`
- `0x180065040`

## callees

- `0x180064fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180064ff7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180064ff7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065009`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065009`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006502c`

## pseudocode

```c
BOOL __fastcall rc4_safe_shutdown(unsigned int *a1)
{
  unsigned int v1; // esi
  __int64 i; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&a1[2 * i + 2] + 8LL));
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180064fd4  mov     [rsp+arg_0], rbx
0x180064fd9  mov     [rsp+arg_8], rsi
0x180064fde  push    rdi
0x180064fdf  sub     rsp, 20h
0x180064fe3  mov     esi, [rcx]
0x180064fe5  xor     ebx, ebx
0x180064fe7  mov     rdi, rcx
0x180064fea  test    esi, esi
0x180064fec  jz      short loc_180065009
0x180064fee  mov     rcx, [rdi+rbx*8+8]
0x180064ff3  add     rcx, 8; lpCriticalSection
0x180064ff7  call    cs:__imp_DeleteCriticalSection
0x180064ffe  nop     dword ptr [rax+rax+00h]
0x180065003  inc     ebx
0x180065005  cmp     ebx, esi
0x180065007  jb      short loc_180064FEE
0x180065009  call    cs:__imp_GetProcessHeap
0x180065010  nop     dword ptr [rax+rax+00h]
0x180065015  mov     r8, rdi
0x180065018  xor     edx, edx
0x18006501a  mov     rcx, rax
0x18006501d  mov     rbx, [rsp+28h+arg_0]
0x180065022  mov     rsi, [rsp+28h+arg_8]
0x180065027  add     rsp, 20h
0x18006502b  pop     rdi
0x18006502c  jmp     cs:__imp_HeapFree
```
