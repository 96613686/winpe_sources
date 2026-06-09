# CMtfSuggestionList::RemoveAt(ulong)

- ea: `0x180029360`
- end: `0x1800293d0`
- name: `?RemoveAt@CMtfSuggestionList@@UEAAJK@Z`
- size: `112`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002972`
- `0x180029360`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::RemoveAt(CMtfSuggestionList *this, unsigned int a2)
{
  __int64 v3; // rcx
  __int64 v4; // rdi
  unsigned __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx

  v3 = *((_QWORD *)this + 3);
  v4 = a2;
  v5 = (*((_QWORD *)this + 4) - v3) >> 3;
  if ( a2 >= v5 )
    return 2147483659LL;
  v7 = *(_QWORD *)(v3 + 8LL * a2);
  try
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    memmove_0(
      (void *)(*((_QWORD *)this + 3) + 8 * v4),
      (const void *)(*((_QWORD *)this + 3) + 8 * v4 + 8),
      (*((_QWORD *)this + 4) - (*((_QWORD *)this + 3) + 8 * v4 + 8)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 4) -= 8LL;
    result = 0;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180029360  mov     [rsp+arg_0], rbx
0x180029365  push    rdi
0x180029366  sub     rsp, 20h
0x18002936a  mov     rbx, rcx
0x18002936d  mov     rcx, [rcx+18h]
0x180029371  mov     edi, edx
0x180029373  mov     rax, [rbx+20h]
0x180029377  sub     rax, rcx
0x18002937a  sar     rax, 3
0x18002937e  cmp     rdi, rax
0x180029381  jb      short loc_18002938A
0x180029383  mov     eax, 8000000Bh
0x180029388  jmp     short loc_1800293C4
0x18002938a  mov     rcx, [rcx+rdi*8]
0x18002938e  mov     rax, [rcx]
0x180029391  mov     rax, [rax+10h]
0x180029395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002939a  mov     rax, [rbx+18h]
0x18002939e  lea     rcx, [rax+rdi*8]; void *
0x1800293a2  lea     rdx, [rcx+8]; Src
0x1800293a6  mov     r8, [rbx+20h]
0x1800293aa  sub     r8, rdx
0x1800293ad  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800293b1  call    memmove_0
0x1800293b6  add     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFF8h
0x1800293bb  xor     eax, eax
0x1800293bd  jmp     short loc_1800293C4
0x1800293bf  mov     eax, 80004005h
0x1800293c4  mov     rbx, [rsp+28h+arg_0]
0x1800293c9  add     rsp, 20h
0x1800293cd  pop     rdi
0x1800293ce  retn
```
