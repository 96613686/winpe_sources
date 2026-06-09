# _IsNonwritableInCurrentImage

- ea: `0x180001e30`
- end: `0x180001e7a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001930`

## callees

- `0x180001de0`
- `0x180001e30`
- `0x180001e80`

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
0x180001e30  mov     [rsp+arg_0], rbx
0x180001e35  push    rdi
0x180001e36  sub     rsp, 20h
0x180001e3a  mov     rbx, rcx
0x180001e3d  lea     rdi, __ImageBase
0x180001e44  mov     rcx, rdi
0x180001e47  call    _ValidateImageBase
0x180001e4c  test    eax, eax
0x180001e4e  jz      short loc_180001E6F
0x180001e50  sub     rbx, rdi
0x180001e53  mov     rdx, rbx
0x180001e56  mov     rcx, rdi
0x180001e59  call    _FindPESection
0x180001e5e  test    rax, rax
0x180001e61  jz      short loc_180001E6F
0x180001e63  mov     eax, [rax+24h]
0x180001e66  not     eax
0x180001e68  shr     eax, 1Fh
0x180001e6b  jmp     short loc_180001E6F
0x180001e6d  xor     eax, eax
0x180001e6f  mov     rbx, [rsp+28h+arg_0]
0x180001e74  add     rsp, 20h
0x180001e78  pop     rdi
0x180001e79  retn
0x180002680  push    rbp
0x180002682  sub     rsp, 20h
0x180002686  mov     rbp, rdx
0x180002689  mov     rax, [rcx]
0x18000268c  xor     ecx, ecx
0x18000268e  cmp     dword ptr [rax], 0C0000005h
0x180002694  setz    cl
0x180002697  mov     eax, ecx
0x180002699  add     rsp, 20h
0x18000269d  pop     rbp
0x18000269e  retn
```
