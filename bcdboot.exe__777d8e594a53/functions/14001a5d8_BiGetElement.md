# BiGetElement

- ea: `0x14001a5d8`
- end: `0x14001a6a8`
- name: `BiGetElement`
- size: `208`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140020dd8`
- `0x140021990`
- `0x1400228bc`
- `0x140023824`
- `0x1400244fc`
- `0x14002515c`

## callees

- `0x140018890`
- `0x14001a5d8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001a63b`
- `ntdll!RtlAllocateHeap` at `0x14001a63b`
- `ntdll!RtlFreeHeap` at `0x14001a693`
- `ntdll!RtlFreeHeap` at `0x14001a693`

## pseudocode

```c
__int64 __fastcall BiGetElement(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  int ElementDataWithFlags; // ebx
  PVOID Heap; // rdi
  SIZE_T Size; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  *a3 = 0;
  *a4 = 0;
  ElementDataWithFlags = BcdGetElementDataWithFlags(a1, a2, 0, 0, &Size);
  if ( ElementDataWithFlags == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    if ( Heap )
    {
      ElementDataWithFlags = BcdGetElementDataWithFlags(a1, a2, 0, (__int64)Heap, &Size);
      if ( ElementDataWithFlags < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
      else
      {
        *a4 = Size;
        *a3 = Heap;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)ElementDataWithFlags;
}

```

## disassembly

```asm
0x14001a5d8  mov     rax, rsp
0x14001a5db  push    rbx
0x14001a5dc  push    rbp
0x14001a5dd  push    rsi
0x14001a5de  push    rdi
0x14001a5df  push    r14
0x14001a5e1  push    r15
0x14001a5e3  sub     rsp, 38h
0x14001a5e7  mov     dword ptr [rax+18h], 0
0x14001a5ee  lea     rax, [rax+18h]
0x14001a5f2  mov     rsi, r9
0x14001a5f5  mov     qword ptr [r8], 0
0x14001a5fc  mov     r14, r8
0x14001a5ff  mov     dword ptr [r9], 0
0x14001a606  xor     r9d, r9d
0x14001a609  mov     [rsp+68h+var_48], rax
0x14001a60e  xor     r8d, r8d
0x14001a611  mov     ebp, edx
0x14001a613  mov     r15, rcx
0x14001a616  call    BcdGetElementDataWithFlags
0x14001a61b  mov     ebx, eax
0x14001a61d  cmp     eax, 0C0000023h
0x14001a622  jnz     short loc_14001A699
0x14001a624  mov     rcx, gs:60h
0x14001a62d  xor     edx, edx; Flags
0x14001a62f  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x14001a637  mov     rcx, [rcx+30h]; HeapHandle
0x14001a63b  call    cs:__imp_RtlAllocateHeap
0x14001a641  mov     rdi, rax
0x14001a644  test    rax, rax
0x14001a647  jnz     short loc_14001A650
0x14001a649  mov     ebx, 0C000009Ah
0x14001a64e  jmp     short loc_14001A699
0x14001a650  lea     rax, [rsp+68h+Size]
0x14001a658  mov     r9, rdi
0x14001a65b  xor     r8d, r8d
0x14001a65e  mov     [rsp+68h+var_48], rax
0x14001a663  mov     edx, ebp
0x14001a665  mov     rcx, r15
0x14001a668  call    BcdGetElementDataWithFlags
0x14001a66d  mov     ebx, eax
0x14001a66f  test    eax, eax
0x14001a671  js      short loc_14001A681
0x14001a673  mov     ecx, dword ptr [rsp+68h+Size]
0x14001a67a  mov     [rsi], ecx
0x14001a67c  mov     [r14], rdi
0x14001a67f  jmp     short loc_14001A699
0x14001a681  mov     rcx, gs:60h
0x14001a68a  mov     r8, rdi; P
0x14001a68d  xor     edx, edx; Flags
0x14001a68f  mov     rcx, [rcx+30h]; HeapHandle
0x14001a693  call    cs:__imp_RtlFreeHeap
0x14001a699  mov     eax, ebx
0x14001a69b  add     rsp, 38h
0x14001a69f  pop     r15
0x14001a6a1  pop     r14
0x14001a6a3  pop     rdi
0x14001a6a4  pop     rsi
0x14001a6a5  pop     rbp
0x14001a6a6  pop     rbx
0x14001a6a7  retn
```
