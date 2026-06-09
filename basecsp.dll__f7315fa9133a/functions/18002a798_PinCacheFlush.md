# PinCacheFlush

- ea: `0x18002a798`
- end: `0x18002a80d`
- name: `PinCacheFlush`
- size: `117`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e86c`
- `0x18001ed64`
- `0x18002b1a4`

## callees

- `0x18002a180`
- `0x18002a798`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a7f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a7e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a7e5`

## pseudocode

```c
__int64 __fastcall PinCacheFlush(_QWORD *a1, int a2, int a3)
{
  __int64 v4; // rcx
  unsigned int i; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    v4 = *a1;
    if ( v4 )
    {
      if ( a3 )
      {
        for ( i = 0; i < 8; ++i )
          I_PinCacheFlush(*a1, i);
        v7 = (void *)*a1;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
        *a1 = 0;
      }
      else
      {
        if ( (unsigned int)(a2 - 1) > 7 )
          return 160;
        I_PinCacheFlush(v4, (unsigned int)(a2 - 1));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002a798  mov     [rsp+arg_0], rbx
0x18002a79d  push    rdi
0x18002a79e  sub     rsp, 20h
0x18002a7a2  mov     rdi, rcx
0x18002a7a5  test    rcx, rcx
0x18002a7a8  jz      short loc_18002A800
0x18002a7aa  mov     rcx, [rcx]
0x18002a7ad  test    rcx, rcx
0x18002a7b0  jz      short loc_18002A800
0x18002a7b2  test    r8d, r8d
0x18002a7b5  jnz     short loc_18002A7CF
0x18002a7b7  lea     eax, [rdx-1]
0x18002a7ba  cmp     eax, 7
0x18002a7bd  ja      short loc_18002A7C8
0x18002a7bf  dec     edx
0x18002a7c1  call    I_PinCacheFlush
0x18002a7c6  jmp     short loc_18002A800
0x18002a7c8  mov     eax, 0A0h
0x18002a7cd  jmp     short loc_18002A802
0x18002a7cf  xor     ebx, ebx
0x18002a7d1  mov     rcx, [rdi]
0x18002a7d4  mov     edx, ebx
0x18002a7d6  call    I_PinCacheFlush
0x18002a7db  inc     ebx
0x18002a7dd  cmp     ebx, 8
0x18002a7e0  jb      short loc_18002A7D1
0x18002a7e2  mov     rbx, [rdi]
0x18002a7e5  call    cs:__imp_GetProcessHeap
0x18002a7eb  mov     r8, rbx; lpMem
0x18002a7ee  xor     edx, edx; dwFlags
0x18002a7f0  mov     rcx, rax; hHeap
0x18002a7f3  call    cs:__imp_HeapFree
0x18002a7f9  mov     qword ptr [rdi], 0
0x18002a800  xor     eax, eax
0x18002a802  mov     rbx, [rsp+28h+arg_0]
0x18002a807  add     rsp, 20h
0x18002a80b  pop     rdi
0x18002a80c  retn
```
