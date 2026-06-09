# _IsNonwritableInCurrentImage

- ea: `0x1800015b0`
- end: `0x1800015fa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010b0`

## callees

- `0x180001560`
- `0x1800015b0`
- `0x180001600`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000LL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800015b0  mov     [rsp+arg_0], rbx
0x1800015b5  push    rdi
0x1800015b6  sub     rsp, 20h
0x1800015ba  mov     rbx, rcx
0x1800015bd  lea     rdi, cs:180000000h
0x1800015c4  mov     rcx, rdi
0x1800015c7  call    _ValidateImageBase
0x1800015cc  test    eax, eax
0x1800015ce  jz      short loc_1800015EF
0x1800015d0  sub     rbx, rdi
0x1800015d3  mov     rdx, rbx
0x1800015d6  mov     rcx, rdi
0x1800015d9  call    _FindPESection
0x1800015de  test    rax, rax
0x1800015e1  jz      short loc_1800015EF
0x1800015e3  mov     eax, [rax+24h]
0x1800015e6  not     eax
0x1800015e8  shr     eax, 1Fh
0x1800015eb  jmp     short loc_1800015EF
0x1800015ed  xor     eax, eax
0x1800015ef  mov     rbx, [rsp+28h+arg_0]
0x1800015f4  add     rsp, 20h
0x1800015f8  pop     rdi
0x1800015f9  retn
0x1800044d0  push    rbp
0x1800044d2  sub     rsp, 20h
0x1800044d6  mov     rbp, rdx
0x1800044d9  mov     rax, [rcx]
0x1800044dc  xor     ecx, ecx
0x1800044de  cmp     dword ptr [rax], 0C0000005h
0x1800044e4  setz    cl
0x1800044e7  mov     eax, ecx
0x1800044e9  add     rsp, 20h
0x1800044ed  pop     rbp
0x1800044ee  retn
```
