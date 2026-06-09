# CMtfSuggestionList::GetPath(uint,IMtfLatticePath * *)

- ea: `0x1800278b0`
- end: `0x1800278f7`
- name: `?GetPath@CMtfSuggestionList@@UEAAJIPEAPEAUIMtfLatticePath@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, unsigned int, struct IMtfLatticePath **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800278b0`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::GetPath(CMtfSuggestionList *this, unsigned int a2, struct IMtfLatticePath **a3)
{
  __int64 v3; // r9
  unsigned __int64 v4; // rax
  __int64 result; // rax

  v3 = *((_QWORD *)this + 2);
  v4 = (*((_QWORD *)this + 3) - v3) >> 3;
  if ( a2 >= v4 )
    return 2147483659LL;
  _mm_lfence();
  try
  {
    result = (***(__int64 (__fastcall ****)(_QWORD))(v3 + 8LL * a2))(*(_QWORD *)(v3 + 8LL * a2));
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
0x1800278b0  sub     rsp, 28h
0x1800278b4  mov     r9, [rcx+10h]
0x1800278b8  mov     edx, edx
0x1800278ba  mov     rax, [rcx+18h]
0x1800278be  sub     rax, r9
0x1800278c1  sar     rax, 3
0x1800278c5  cmp     rdx, rax
0x1800278c8  jb      short loc_1800278D1
0x1800278ca  mov     eax, 8000000Bh
0x1800278cf  jmp     short loc_1800278F1
0x1800278d1  lfence
0x1800278d4  mov     rcx, [r9+rdx*8]
0x1800278d8  mov     rax, [rcx]
0x1800278db  lea     rdx, _GUID_53445657_1e40_40f5_a775_8965c8894c31
0x1800278e2  mov     rax, [rax]
0x1800278e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278ea  jmp     short loc_1800278F1
0x1800278ec  mov     eax, 80004005h
0x1800278f1  add     rsp, 28h
0x1800278f5  retn
```
