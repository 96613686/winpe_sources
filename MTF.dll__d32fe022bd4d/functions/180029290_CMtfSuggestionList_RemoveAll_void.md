# CMtfSuggestionList::RemoveAll(void)

- ea: `0x180029290`
- end: `0x1800292ea`
- name: `?RemoveAll@CMtfSuggestionList@@UEAAJXZ`
- size: `90`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180029290`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::RemoveAll(CMtfSuggestionList *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdi

  v2 = *((_QWORD *)this + 3);
  v3 = *((_QWORD *)this + 4);
  while ( v2 != v3 )
  {
    try
    {
      (*(void (**)(void))(**(_QWORD **)v2 + 16LL))();
      v2 += 8;
    }
    catch ( ... )
    {
      return 2147500037LL;
    }
  }
  *((_QWORD *)this + 4) = *((_QWORD *)this + 3);
  *((_BYTE *)this + 60) = 1;
  return 0;
}

```

## disassembly

```asm
0x180029290  mov     [rsp+arg_0], rbx
0x180029295  mov     [rsp+arg_8], rsi
0x18002929a  push    rdi
0x18002929b  sub     rsp, 20h
0x18002929f  mov     rsi, rcx
0x1800292a2  mov     rbx, [rcx+18h]
0x1800292a6  mov     rdi, [rcx+20h]
0x1800292aa  cmp     rbx, rdi
0x1800292ad  jnz     short loc_1800292BF
0x1800292af  mov     rax, [rsi+18h]
0x1800292b3  mov     [rsi+20h], rax
0x1800292b7  mov     byte ptr [rsi+3Ch], 1
0x1800292bb  xor     eax, eax
0x1800292bd  jmp     short loc_1800292D9
0x1800292bf  mov     rcx, [rbx]
0x1800292c2  mov     rax, [rcx]
0x1800292c5  mov     rax, [rax+10h]
0x1800292c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292ce  add     rbx, 8
0x1800292d2  jmp     short loc_1800292AA
0x1800292d4  mov     eax, 80004005h
0x1800292d9  mov     rbx, [rsp+28h+arg_0]
0x1800292de  mov     rsi, [rsp+28h+arg_8]
0x1800292e3  add     rsp, 20h
0x1800292e7  pop     rdi
0x1800292e8  retn
```
