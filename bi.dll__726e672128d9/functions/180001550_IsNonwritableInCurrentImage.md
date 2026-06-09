# _IsNonwritableInCurrentImage

- ea: `0x180001550`
- end: `0x18000159a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x180001500`
- `0x180001550`
- `0x1800015a0`

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
0x180001550  mov     [rsp+arg_0], rbx
0x180001555  push    rdi
0x180001556  sub     rsp, 20h
0x18000155a  mov     rbx, rcx
0x18000155d  lea     rdi, cs:180000000h
0x180001564  mov     rcx, rdi
0x180001567  call    _ValidateImageBase
0x18000156c  test    eax, eax
0x18000156e  jz      short loc_18000158F
0x180001570  sub     rbx, rdi
0x180001573  mov     rdx, rbx
0x180001576  mov     rcx, rdi
0x180001579  call    _FindPESection
0x18000157e  test    rax, rax
0x180001581  jz      short loc_18000158F
0x180001583  mov     eax, [rax+24h]
0x180001586  not     eax
0x180001588  shr     eax, 1Fh
0x18000158b  jmp     short loc_18000158F
0x18000158d  xor     eax, eax
0x18000158f  mov     rbx, [rsp+28h+arg_0]
0x180001594  add     rsp, 20h
0x180001598  pop     rdi
0x180001599  retn
0x1800037f0  push    rbp
0x1800037f2  sub     rsp, 20h
0x1800037f6  mov     rbp, rdx
0x1800037f9  mov     rax, [rcx]
0x1800037fc  xor     ecx, ecx
0x1800037fe  cmp     dword ptr [rax], 0C0000005h
0x180003804  setz    cl
0x180003807  mov     eax, ecx
0x180003809  add     rsp, 20h
0x18000380d  pop     rbp
0x18000380e  retn
```
