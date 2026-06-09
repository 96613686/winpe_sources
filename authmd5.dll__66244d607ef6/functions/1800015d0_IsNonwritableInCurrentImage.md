# _IsNonwritableInCurrentImage

- ea: `0x1800015d0`
- end: `0x18000161a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010b0`

## callees

- `0x180001580`
- `0x1800015d0`
- `0x180001620`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000uLL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800015d0  mov     [rsp+arg_0], rbx
0x1800015d5  push    rdi
0x1800015d6  sub     rsp, 20h
0x1800015da  mov     rbx, rcx
0x1800015dd  lea     rdi, cs:180000000h
0x1800015e4  mov     rcx, rdi
0x1800015e7  call    _ValidateImageBase
0x1800015ec  test    eax, eax
0x1800015ee  jz      short loc_18000160F
0x1800015f0  sub     rbx, rdi
0x1800015f3  mov     rdx, rbx
0x1800015f6  mov     rcx, rdi
0x1800015f9  call    _FindPESection
0x1800015fe  test    rax, rax
0x180001601  jz      short loc_18000160F
0x180001603  mov     eax, [rax+24h]
0x180001606  not     eax
0x180001608  shr     eax, 1Fh
0x18000160b  jmp     short loc_18000160F
0x18000160d  xor     eax, eax
0x18000160f  mov     rbx, [rsp+28h+arg_0]
0x180001614  add     rsp, 20h
0x180001618  pop     rdi
0x180001619  retn
0x180006940  push    rbp
0x180006942  sub     rsp, 20h
0x180006946  mov     rbp, rdx
0x180006949  mov     rax, [rcx]
0x18000694c  xor     ecx, ecx
0x18000694e  cmp     dword ptr [rax], 0C0000005h
0x180006954  setz    cl
0x180006957  mov     eax, ecx
0x180006959  add     rsp, 20h
0x18000695d  pop     rbp
0x18000695e  retn
```
