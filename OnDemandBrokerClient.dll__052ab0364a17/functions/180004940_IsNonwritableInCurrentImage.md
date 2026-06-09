# _IsNonwritableInCurrentImage

- ea: `0x180004940`
- end: `0x18000498a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004410`

## callees

- `0x1800048f0`
- `0x180004940`
- `0x180004990`

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
0x180004940  mov     [rsp+arg_0], rbx
0x180004945  push    rdi
0x180004946  sub     rsp, 20h
0x18000494a  mov     rbx, rcx
0x18000494d  lea     rdi, __ImageBase
0x180004954  mov     rcx, rdi
0x180004957  call    _ValidateImageBase
0x18000495c  test    eax, eax
0x18000495e  jz      short loc_18000497F
0x180004960  sub     rbx, rdi
0x180004963  mov     rdx, rbx
0x180004966  mov     rcx, rdi
0x180004969  call    _FindPESection
0x18000496e  test    rax, rax
0x180004971  jz      short loc_18000497F
0x180004973  mov     eax, [rax+24h]
0x180004976  not     eax
0x180004978  shr     eax, 1Fh
0x18000497b  jmp     short loc_18000497F
0x18000497d  xor     eax, eax
0x18000497f  mov     rbx, [rsp+28h+arg_0]
0x180004984  add     rsp, 20h
0x180004988  pop     rdi
0x180004989  retn
0x180006a20  push    rbp
0x180006a22  sub     rsp, 20h
0x180006a26  mov     rbp, rdx
0x180006a29  mov     rax, [rcx]
0x180006a2c  xor     ecx, ecx
0x180006a2e  cmp     dword ptr [rax], 0C0000005h
0x180006a34  setz    cl
0x180006a37  mov     eax, ecx
0x180006a39  add     rsp, 20h
0x180006a3d  pop     rbp
0x180006a3e  retn
```
