# _IsNonwritableInCurrentImage

- ea: `0x1400016f0`
- end: `0x14000173a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011e0`

## callees

- `0x1400016a0`
- `0x1400016f0`
- `0x140001740`

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
0x1400016f0  mov     [rsp+arg_0], rbx
0x1400016f5  push    rdi
0x1400016f6  sub     rsp, 20h
0x1400016fa  mov     rbx, rcx
0x1400016fd  lea     rdi, __ImageBase
0x140001704  mov     rcx, rdi
0x140001707  call    _ValidateImageBase
0x14000170c  test    eax, eax
0x14000170e  jz      short loc_14000172F
0x140001710  sub     rbx, rdi
0x140001713  mov     rdx, rbx
0x140001716  mov     rcx, rdi
0x140001719  call    _FindPESection
0x14000171e  test    rax, rax
0x140001721  jz      short loc_14000172F
0x140001723  mov     eax, [rax+24h]
0x140001726  not     eax
0x140001728  shr     eax, 1Fh
0x14000172b  jmp     short loc_14000172F
0x14000172d  xor     eax, eax
0x14000172f  mov     rbx, [rsp+28h+arg_0]
0x140001734  add     rsp, 20h
0x140001738  pop     rdi
0x140001739  retn
0x140005810  push    rbp
0x140005812  sub     rsp, 20h
0x140005816  mov     rbp, rdx
0x140005819  mov     rax, [rcx]
0x14000581c  xor     ecx, ecx
0x14000581e  cmp     dword ptr [rax], 0C0000005h
0x140005824  setz    cl
0x140005827  mov     eax, ecx
0x140005829  add     rsp, 20h
0x14000582d  pop     rbp
0x14000582e  retn
```
