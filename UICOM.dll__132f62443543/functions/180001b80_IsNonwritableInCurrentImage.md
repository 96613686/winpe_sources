# _IsNonwritableInCurrentImage

- ea: `0x180001b80`
- end: `0x180001bca`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001220`

## callees

- `0x180001b30`
- `0x180001b80`
- `0x180001bd0`

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
0x180001b80  mov     [rsp+arg_0], rbx
0x180001b85  push    rdi
0x180001b86  sub     rsp, 20h
0x180001b8a  mov     rbx, rcx
0x180001b8d  lea     rdi, cs:180000000h
0x180001b94  mov     rcx, rdi
0x180001b97  call    _ValidateImageBase
0x180001b9c  test    eax, eax
0x180001b9e  jz      short loc_180001BBF
0x180001ba0  sub     rbx, rdi
0x180001ba3  mov     rdx, rbx
0x180001ba6  mov     rcx, rdi
0x180001ba9  call    _FindPESection
0x180001bae  test    rax, rax
0x180001bb1  jz      short loc_180001BBF
0x180001bb3  mov     eax, [rax+24h]
0x180001bb6  not     eax
0x180001bb8  shr     eax, 1Fh
0x180001bbb  jmp     short loc_180001BBF
0x180001bbd  xor     eax, eax
0x180001bbf  mov     rbx, [rsp+28h+arg_0]
0x180001bc4  add     rsp, 20h
0x180001bc8  pop     rdi
0x180001bc9  retn
0x180006320  push    rbp
0x180006322  sub     rsp, 20h
0x180006326  mov     rbp, rdx
0x180006329  mov     rax, [rcx]
0x18000632c  xor     ecx, ecx
0x18000632e  cmp     dword ptr [rax], 0C0000005h
0x180006334  setz    cl
0x180006337  mov     eax, ecx
0x180006339  add     rsp, 20h
0x18000633d  pop     rbp
0x18000633e  retn
```
