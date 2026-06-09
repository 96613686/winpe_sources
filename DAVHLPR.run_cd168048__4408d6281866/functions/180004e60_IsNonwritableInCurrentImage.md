# _IsNonwritableInCurrentImage

- ea: `0x180004e60`
- end: `0x180004eaa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004970`

## callees

- `0x180004e10`
- `0x180004e60`
- `0x180004eb0`

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
0x180004e60  mov     [rsp+arg_0], rbx
0x180004e65  push    rdi
0x180004e66  sub     rsp, 20h
0x180004e6a  mov     rbx, rcx
0x180004e6d  lea     rdi, __ImageBase
0x180004e74  mov     rcx, rdi
0x180004e77  call    _ValidateImageBase
0x180004e7c  test    eax, eax
0x180004e7e  jz      short loc_180004E9F
0x180004e80  sub     rbx, rdi
0x180004e83  mov     rdx, rbx
0x180004e86  mov     rcx, rdi
0x180004e89  call    _FindPESection
0x180004e8e  test    rax, rax
0x180004e91  jz      short loc_180004E9F
0x180004e93  mov     eax, [rax+24h]
0x180004e96  not     eax
0x180004e98  shr     eax, 1Fh
0x180004e9b  jmp     short loc_180004E9F
0x180004e9d  xor     eax, eax
0x180004e9f  mov     rbx, [rsp+28h+arg_0]
0x180004ea4  add     rsp, 20h
0x180004ea8  pop     rdi
0x180004ea9  retn
0x180006410  push    rbp
0x180006412  sub     rsp, 20h
0x180006416  mov     rbp, rdx
0x180006419  mov     rax, [rcx]
0x18000641c  xor     ecx, ecx
0x18000641e  cmp     dword ptr [rax], 0C0000005h
0x180006424  setz    cl
0x180006427  mov     eax, ecx
0x180006429  add     rsp, 20h
0x18000642d  pop     rbp
0x18000642e  retn
```
