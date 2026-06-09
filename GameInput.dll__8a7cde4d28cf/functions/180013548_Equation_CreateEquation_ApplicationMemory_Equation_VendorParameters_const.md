# Equation::CreateEquation(ApplicationMemory &,Equation::VendorParameters const *)

- ea: `0x180013548`
- end: `0x180013620`
- name: `?CreateEquation@Equation@@QEAAJAEAVApplicationMemory@@PEBUVendorParameters@1@@Z`
- size: `216`
- prototype: `__int64 __fastcall(Equation *__hidden this, struct ApplicationMemory *, const struct Equation::VendorParameters *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013628`

## callees

- `0x180013548`
- `0x180013ef0`
- `0x18004c88d`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800135b8`
- `ntdll!RtlAllocateHeap` at `0x1800135b8`

## pseudocode

```c
__int64 __fastcall Equation::CreateEquation(
        Equation *this,
        struct ApplicationMemory *a2,
        const struct Equation::VendorParameters *a3)
{
  __int64 v7; // rax
  int v8; // edi
  unsigned int v9; // edi
  void *v10; // r15
  PVOID Heap; // rax
  __int64 v12; // rax
  SIZE_T Size; // [rsp+60h] [rbp+18h] BYREF
  void *Src; // [rsp+68h] [rbp+20h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v7 = *(_QWORD *)this;
  Src = 0;
  LODWORD(Size) = 0;
  v8 = (*(__int64 (__fastcall **)(Equation *, void **, SIZE_T *))(v7 + 24))(this, &Src, &Size);
  if ( v8 >= 0 )
  {
    v9 = Size;
    v10 = Src;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    *((_QWORD *)this + 6) = Heap;
    if ( Heap )
    {
      memcpy_0(Heap, v10, v9);
      v12 = *(_QWORD *)this;
      *((_DWORD *)this + 14) = v9;
      v8 = (*(__int64 (__fastcall **)(Equation *, struct ApplicationMemory *))(v12 + 32))(this, a2);
    }
    else
    {
      v8 = -2147024882;
    }
  }
  *((_QWORD *)this + 5) = a3;
  if ( v8 < 0 )
    Equation::DestroyEquation(this, a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013548  mov     [rsp+arg_0], rbx
0x18001354d  push    rbp
0x18001354e  push    rsi
0x18001354f  push    rdi
0x180013550  push    r14
0x180013552  push    r15
0x180013554  sub     rsp, 20h
0x180013558  mov     rsi, r8
0x18001355b  mov     rbp, rdx
0x18001355e  mov     rbx, rcx
0x180013561  test    r8, r8
0x180013564  jnz     short loc_180013570
0x180013566  mov     eax, 80070057h
0x18001356b  jmp     loc_18001360E
0x180013570  mov     rax, [rcx]
0x180013573  lea     r8, [rsp+48h+Size]
0x180013578  lea     rdx, [rsp+48h+Src]
0x18001357d  mov     [rsp+48h+Src], 0
0x180013586  mov     dword ptr [rsp+48h+Size], 0
0x18001358e  mov     rax, [rax+18h]
0x180013592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013597  mov     edi, eax
0x180013599  test    eax, eax
0x18001359b  js      short loc_1800135F9
0x18001359d  mov     rcx, gs:60h
0x1800135a6  xor     edx, edx; Flags
0x1800135a8  mov     edi, dword ptr [rsp+48h+Size]
0x1800135ac  mov     r15, [rsp+48h+Src]
0x1800135b1  mov     r8d, edi; Size
0x1800135b4  mov     rcx, [rcx+30h]; HeapHandle
0x1800135b8  call    cs:__imp_RtlAllocateHeap
0x1800135bf  nop     dword ptr [rax+rax+00h]
0x1800135c4  mov     [rbx+30h], rax
0x1800135c8  test    rax, rax
0x1800135cb  jz      short loc_1800135F4
0x1800135cd  mov     r8d, edi; Size
0x1800135d0  mov     rdx, r15; Src
0x1800135d3  mov     rcx, rax; void *
0x1800135d6  call    memcpy_0
0x1800135db  mov     rax, [rbx]
0x1800135de  mov     rdx, rbp
0x1800135e1  mov     rcx, rbx
0x1800135e4  mov     [rbx+38h], edi
0x1800135e7  mov     rax, [rax+20h]
0x1800135eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135f0  mov     edi, eax
0x1800135f2  jmp     short loc_1800135F9
0x1800135f4  mov     edi, 8007000Eh
0x1800135f9  mov     [rbx+28h], rsi
0x1800135fd  test    edi, edi
0x1800135ff  jns     short loc_18001360C
0x180013601  mov     rdx, rbp; struct ApplicationMemory *
0x180013604  mov     rcx, rbx; this
0x180013607  call    ?DestroyEquation@Equation@@QEAAXAEAVApplicationMemory@@@Z; Equation::DestroyEquation(ApplicationMemory &)
0x18001360c  mov     eax, edi
0x18001360e  mov     rbx, [rsp+48h+arg_0]
0x180013613  add     rsp, 20h
0x180013617  pop     r15
0x180013619  pop     r14
0x18001361b  pop     rdi
0x18001361c  pop     rsi
0x18001361d  pop     rbp
0x18001361e  retn
```
