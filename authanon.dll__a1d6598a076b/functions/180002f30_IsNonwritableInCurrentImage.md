# _IsNonwritableInCurrentImage

- ea: `0x180002f30`
- end: `0x180002f7a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a10`

## callees

- `0x180002ee0`
- `0x180002f30`
- `0x180002f80`

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
0x180002f30  mov     [rsp+arg_0], rbx
0x180002f35  push    rdi
0x180002f36  sub     rsp, 20h
0x180002f3a  mov     rbx, rcx
0x180002f3d  lea     rdi, __ImageBase
0x180002f44  mov     rcx, rdi
0x180002f47  call    _ValidateImageBase
0x180002f4c  test    eax, eax
0x180002f4e  jz      short loc_180002F6F
0x180002f50  sub     rbx, rdi
0x180002f53  mov     rdx, rbx
0x180002f56  mov     rcx, rdi
0x180002f59  call    _FindPESection
0x180002f5e  test    rax, rax
0x180002f61  jz      short loc_180002F6F
0x180002f63  mov     eax, [rax+24h]
0x180002f66  not     eax
0x180002f68  shr     eax, 1Fh
0x180002f6b  jmp     short loc_180002F6F
0x180002f6d  xor     eax, eax
0x180002f6f  mov     rbx, [rsp+28h+arg_0]
0x180002f74  add     rsp, 20h
0x180002f78  pop     rdi
0x180002f79  retn
0x180005eb0  push    rbp
0x180005eb2  sub     rsp, 20h
0x180005eb6  mov     rbp, rdx
0x180005eb9  mov     rax, [rcx]
0x180005ebc  xor     ecx, ecx
0x180005ebe  cmp     dword ptr [rax], 0C0000005h
0x180005ec4  setz    cl
0x180005ec7  mov     eax, ecx
0x180005ec9  add     rsp, 20h
0x180005ecd  pop     rbp
0x180005ece  retn
```
