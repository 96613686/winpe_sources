# _IsNonwritableInCurrentImage

- ea: `0x1800015c0`
- end: `0x18000160a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010a0`

## callees

- `0x180001570`
- `0x1800015c0`
- `0x180001610`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection(&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800015c0  mov     [rsp+arg_0], rbx
0x1800015c5  push    rdi
0x1800015c6  sub     rsp, 20h
0x1800015ca  mov     rbx, rcx
0x1800015cd  lea     rdi, __ImageBase
0x1800015d4  mov     rcx, rdi
0x1800015d7  call    _ValidateImageBase
0x1800015dc  test    eax, eax
0x1800015de  jz      short loc_1800015FF
0x1800015e0  sub     rbx, rdi
0x1800015e3  mov     rdx, rbx
0x1800015e6  mov     rcx, rdi
0x1800015e9  call    _FindPESection
0x1800015ee  test    rax, rax
0x1800015f1  jz      short loc_1800015FF
0x1800015f3  mov     eax, [rax+24h]
0x1800015f6  not     eax
0x1800015f8  shr     eax, 1Fh
0x1800015fb  jmp     short loc_1800015FF
0x1800015fd  xor     eax, eax
0x1800015ff  mov     rbx, [rsp+28h+arg_0]
0x180001604  add     rsp, 20h
0x180001608  pop     rdi
0x180001609  retn
0x180007110  push    rbp
0x180007112  sub     rsp, 20h
0x180007116  mov     rbp, rdx
0x180007119  mov     rax, [rcx]
0x18000711c  xor     ecx, ecx
0x18000711e  cmp     dword ptr [rax], 0C0000005h
0x180007124  setz    cl
0x180007127  mov     eax, ecx
0x180007129  add     rsp, 20h
0x18000712d  pop     rbp
0x18000712e  retn
```
