# _IsNonwritableInCurrentImage

- ea: `0x180004450`
- end: `0x18000449a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f50`

## callees

- `0x180004400`
- `0x180004450`
- `0x1800044a0`

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
0x180004450  mov     [rsp+arg_0], rbx
0x180004455  push    rdi
0x180004456  sub     rsp, 20h
0x18000445a  mov     rbx, rcx
0x18000445d  lea     rdi, cs:180000000h
0x180004464  mov     rcx, rdi
0x180004467  call    _ValidateImageBase
0x18000446c  test    eax, eax
0x18000446e  jz      short loc_18000448F
0x180004470  sub     rbx, rdi
0x180004473  mov     rdx, rbx
0x180004476  mov     rcx, rdi
0x180004479  call    _FindPESection
0x18000447e  test    rax, rax
0x180004481  jz      short loc_18000448F
0x180004483  mov     eax, [rax+24h]
0x180004486  not     eax
0x180004488  shr     eax, 1Fh
0x18000448b  jmp     short loc_18000448F
0x18000448d  xor     eax, eax
0x18000448f  mov     rbx, [rsp+28h+arg_0]
0x180004494  add     rsp, 20h
0x180004498  pop     rdi
0x180004499  retn
0x180009ac0  push    rbp
0x180009ac2  sub     rsp, 20h
0x180009ac6  mov     rbp, rdx
0x180009ac9  mov     rax, [rcx]
0x180009acc  xor     ecx, ecx
0x180009ace  cmp     dword ptr [rax], 0C0000005h
0x180009ad4  setz    cl
0x180009ad7  mov     eax, ecx
0x180009ad9  add     rsp, 20h
0x180009add  pop     rbp
0x180009ade  retn
```
