# SrvWriteConsoleInput

- ea: `0x140020550`
- end: `0x140020623`
- name: `SrvWriteConsoleInput`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14001d83c`
- `0x14001f6b8`
- `0x140020550`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140020588`
- `ntdll!RtlAllocateHeap` at `0x140020588`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020610`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020610`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140020562`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140020562`
- `ntdll!RtlFreeHeap` at `0x140020606`
- `ntdll!RtlFreeHeap` at `0x140020606`

## pseudocode

```c
__int64 __fastcall SrvWriteConsoleInput(__int64 a1)
{
  SIZE_T v2; // rbp
  PVOID Heap; // rax
  void *v4; // rsi
  NTSTATUS MessageInput; // edi

  RtlAcquireSRWLockExclusive(a1 + 104);
  v2 = (unsigned int)(*(_DWORD *)(a1 + 340) - *(_DWORD *)(a1 + 260));
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  v4 = Heap;
  if ( Heap )
  {
    MessageInput = ReadMessageInput((void **)a1, a1 + 216, 0, (__int64)Heap, v2);
    if ( MessageInput >= 0 )
    {
      if ( (unsigned int)(v2 / 0x14) )
        *(_DWORD *)(a1 + 360) = CsWriteInput(a1, (__int64)v4, v2 / 0x14, 1);
      else
        *(_DWORD *)(a1 + 360) = 0;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  else
  {
    MessageInput = -1073741670;
  }
  RtlReleaseSRWLockExclusive(a1 + 104);
  return (unsigned int)MessageInput;
}

```

## disassembly

```asm
0x140020550  push    rbx
0x140020552  push    rbp
0x140020553  push    rsi
0x140020554  push    rdi
0x140020555  push    r14
0x140020557  sub     rsp, 30h
0x14002055b  mov     rbx, rcx
0x14002055e  add     rcx, 68h ; 'h'
0x140020562  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140020568  mov     rcx, gs:60h
0x140020571  xor     edx, edx; Flags
0x140020573  mov     eax, [rbx+154h]
0x140020579  sub     eax, [rbx+104h]
0x14002057f  mov     r8d, eax; Size
0x140020582  mov     rcx, [rcx+30h]; HeapHandle
0x140020586  mov     ebp, eax
0x140020588  call    cs:__imp_RtlAllocateHeap
0x14002058e  mov     rsi, rax
0x140020591  test    rax, rax
0x140020594  jnz     short loc_14002059D
0x140020596  mov     edi, 0C000009Ah
0x14002059b  jmp     short loc_14002060C
0x14002059d  lea     rdx, [rbx+0D8h]
0x1400205a4  mov     [rsp+58h+var_38], ebp
0x1400205a8  mov     r9, rsi
0x1400205ab  xor     r8d, r8d
0x1400205ae  mov     rcx, rbx
0x1400205b1  call    ReadMessageInput
0x1400205b6  mov     edi, eax
0x1400205b8  test    eax, eax
0x1400205ba  js      short loc_1400205F4
0x1400205bc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400205c6  mul     rbp
0x1400205c9  shr     rdx, 4
0x1400205cd  test    edx, edx
0x1400205cf  jz      short loc_1400205EA
0x1400205d1  mov     r8d, edx
0x1400205d4  mov     r9b, 1
0x1400205d7  mov     rdx, rsi
0x1400205da  mov     rcx, rbx
0x1400205dd  call    CsWriteInput
0x1400205e2  mov     [rbx+168h], eax
0x1400205e8  jmp     short loc_1400205F4
0x1400205ea  mov     dword ptr [rbx+168h], 0
0x1400205f4  mov     rcx, gs:60h
0x1400205fd  mov     r8, rsi; P
0x140020600  xor     edx, edx; Flags
0x140020602  mov     rcx, [rcx+30h]; HeapHandle
0x140020606  call    cs:__imp_RtlFreeHeap
0x14002060c  lea     rcx, [rbx+68h]
0x140020610  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140020616  mov     eax, edi
0x140020618  add     rsp, 30h
0x14002061c  pop     r14
0x14002061e  pop     rdi
0x14002061f  pop     rsi
0x140020620  pop     rbp
0x140020621  pop     rbx
0x140020622  retn
```
