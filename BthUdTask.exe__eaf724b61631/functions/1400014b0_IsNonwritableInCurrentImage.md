# _IsNonwritableInCurrentImage

- ea: `0x1400014b0`
- end: `0x1400014fa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001460`
- `0x1400014b0`
- `0x140001500`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection((__int64)&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400014b0  mov     [rsp+arg_0], rbx
0x1400014b5  push    rdi
0x1400014b6  sub     rsp, 20h
0x1400014ba  mov     rbx, rcx
0x1400014bd  lea     rdi, __ImageBase
0x1400014c4  mov     rcx, rdi
0x1400014c7  call    _ValidateImageBase
0x1400014cc  test    eax, eax
0x1400014ce  jz      short loc_1400014EF
0x1400014d0  sub     rbx, rdi
0x1400014d3  mov     rdx, rbx
0x1400014d6  mov     rcx, rdi
0x1400014d9  call    _FindPESection
0x1400014de  test    rax, rax
0x1400014e1  jz      short loc_1400014EF
0x1400014e3  mov     eax, [rax+24h]
0x1400014e6  not     eax
0x1400014e8  shr     eax, 1Fh
0x1400014eb  jmp     short loc_1400014EF
0x1400014ed  xor     eax, eax
0x1400014ef  mov     rbx, [rsp+28h+arg_0]
0x1400014f4  add     rsp, 20h
0x1400014f8  pop     rdi
0x1400014f9  retn
0x1400020c0  push    rbp
0x1400020c2  sub     rsp, 20h
0x1400020c6  mov     rbp, rdx
0x1400020c9  mov     rax, [rcx]
0x1400020cc  xor     ecx, ecx
0x1400020ce  cmp     dword ptr [rax], 0C0000005h
0x1400020d4  setz    cl
0x1400020d7  mov     eax, ecx
0x1400020d9  add     rsp, 20h
0x1400020dd  pop     rbp
0x1400020de  retn
```
