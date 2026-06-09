# _IsNonwritableInCurrentImage

- ea: `0x1400014a0`
- end: `0x1400014ea`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001450`
- `0x1400014a0`
- `0x1400014f0`

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
0x1400014a0  mov     [rsp+arg_0], rbx
0x1400014a5  push    rdi
0x1400014a6  sub     rsp, 20h
0x1400014aa  mov     rbx, rcx
0x1400014ad  lea     rdi, __ImageBase
0x1400014b4  mov     rcx, rdi
0x1400014b7  call    _ValidateImageBase
0x1400014bc  test    eax, eax
0x1400014be  jz      short loc_1400014DF
0x1400014c0  sub     rbx, rdi
0x1400014c3  mov     rdx, rbx
0x1400014c6  mov     rcx, rdi
0x1400014c9  call    _FindPESection
0x1400014ce  test    rax, rax
0x1400014d1  jz      short loc_1400014DF
0x1400014d3  mov     eax, [rax+24h]
0x1400014d6  not     eax
0x1400014d8  shr     eax, 1Fh
0x1400014db  jmp     short loc_1400014DF
0x1400014dd  xor     eax, eax
0x1400014df  mov     rbx, [rsp+28h+arg_0]
0x1400014e4  add     rsp, 20h
0x1400014e8  pop     rdi
0x1400014e9  retn
0x140002e10  push    rbp
0x140002e12  sub     rsp, 20h
0x140002e16  mov     rbp, rdx
0x140002e19  mov     rax, [rcx]
0x140002e1c  xor     ecx, ecx
0x140002e1e  cmp     dword ptr [rax], 0C0000005h
0x140002e24  setz    cl
0x140002e27  mov     eax, ecx
0x140002e29  add     rsp, 20h
0x140002e2d  pop     rbp
0x140002e2e  retn
```
