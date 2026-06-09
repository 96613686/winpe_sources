# prvDeleteFFTEntry

- ea: `0x180012530`
- end: `0x1800125a0`
- name: `prvDeleteFFTEntry`
- size: `112`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800124f8`

## callees

- `0x180012530`
- `0x180015104`
- `0x180017080`

## pseudocode

```c
void __fastcall prvDeleteFFTEntry(_QWORD *Block, int a2, int a3)
{
  unsigned int i; // edi

  if ( Block )
  {
    if ( a3 == 2 )
    {
      for ( i = 0; (int)i < a2; ++i )
      {
        if ( Block[4 * i + 2] )
          ippsFree();
      }
    }
    else if ( a3 == 1 )
    {
      if ( Block[2] )
        ippsFree();
    }
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x180012530  test    rcx, rcx
0x180012533  jz      short locret_18001256C
0x180012535  mov     [rsp+arg_0], rbx
0x18001253a  mov     [rsp+arg_8], rsi
0x18001253f  push    rdi
0x180012540  sub     rsp, 20h
0x180012544  mov     esi, edx
0x180012546  mov     rbx, rcx
0x180012549  cmp     r8d, 2
0x18001254d  jz      short loc_18001256D
0x18001254f  cmp     r8d, 1
0x180012553  jz      short loc_180012590
0x180012555  mov     rcx, rbx; Block
0x180012558  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001255d  mov     rbx, [rsp+28h+arg_0]
0x180012562  mov     rsi, [rsp+28h+arg_8]
0x180012567  add     rsp, 20h
0x18001256b  pop     rdi
0x18001256c  retn
0x18001256d  xor     edi, edi
0x18001256f  test    esi, esi
0x180012571  jle     short loc_180012555
0x180012573  mov     eax, edi
0x180012575  shl     rax, 5
0x180012579  mov     rcx, [rax+rbx+10h]
0x18001257e  test    rcx, rcx
0x180012581  jz      short loc_180012588
0x180012583  call    ippsFree
0x180012588  inc     edi
0x18001258a  cmp     edi, esi
0x18001258c  jl      short loc_180012573
0x18001258e  jmp     short loc_180012555
0x180012590  mov     rcx, [rcx+10h]
0x180012594  test    rcx, rcx
0x180012597  jz      short loc_180012555
0x180012599  call    ippsFree
0x18001259e  jmp     short loc_180012555
```
