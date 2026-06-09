# _IsNonwritableInCurrentImage

- ea: `0x140001580`
- end: `0x1400015ca`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001168`

## callees

- `0x140001530`
- `0x140001580`
- `0x1400015d0`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x140000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x140000000LL, a1 - 0x140000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001580  mov     [rsp+arg_0], rbx
0x140001585  push    rdi
0x140001586  sub     rsp, 20h
0x14000158a  mov     rbx, rcx
0x14000158d  lea     rdi, cs:140000000h
0x140001594  mov     rcx, rdi
0x140001597  call    _ValidateImageBase
0x14000159c  test    eax, eax
0x14000159e  jz      short loc_1400015BF
0x1400015a0  sub     rbx, rdi
0x1400015a3  mov     rdx, rbx
0x1400015a6  mov     rcx, rdi
0x1400015a9  call    _FindPESection
0x1400015ae  test    rax, rax
0x1400015b1  jz      short loc_1400015BF
0x1400015b3  mov     eax, [rax+24h]
0x1400015b6  not     eax
0x1400015b8  shr     eax, 1Fh
0x1400015bb  jmp     short loc_1400015BF
0x1400015bd  xor     eax, eax
0x1400015bf  mov     rbx, [rsp+28h+arg_0]
0x1400015c4  add     rsp, 20h
0x1400015c8  pop     rdi
0x1400015c9  retn
0x140004560  push    rbp
0x140004562  sub     rsp, 20h
0x140004566  mov     rbp, rdx
0x140004569  mov     rax, [rcx]
0x14000456c  xor     ecx, ecx
0x14000456e  cmp     dword ptr [rax], 0C0000005h
0x140004574  setz    cl
0x140004577  mov     eax, ecx
0x140004579  add     rsp, 20h
0x14000457d  pop     rbp
0x14000457e  retn
```
