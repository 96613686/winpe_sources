# CMtfSuggestionList::CreateCandidate(IMtfSuggestionCandidate * *)

- ea: `0x1800262b0`
- end: `0x1800262ef`
- name: `?CreateCandidate@CMtfSuggestionList@@UEAAJPEAPEAUIMtfSuggestionCandidate@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, struct IMtfSuggestionCandidate **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800251b8`
- `0x1800262b0`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::CreateCandidate(CMtfSuggestionList *this, struct IMtfSuggestionCandidate **a2)
{
  __int64 result; // rax
  CMtfPredictionCandidate *v4; // rax

  if ( !a2 )
    return 2147500035LL;
  try
  {
    v4 = (CMtfPredictionCandidate *)operator new(0x98u);
    if ( v4 )
      v4 = CMtfPredictionCandidate::CMtfPredictionCandidate(v4);
    *a2 = v4;
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
0x1800262b0  push    rbx
0x1800262b2  sub     rsp, 20h
0x1800262b6  mov     rbx, rdx
0x1800262b9  test    rdx, rdx
0x1800262bc  jnz     short loc_1800262C5
0x1800262be  mov     eax, 80004003h
0x1800262c3  jmp     short loc_1800262E8
0x1800262c5  mov     ecx, 98h; Size
0x1800262ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800262cf  test    rax, rax
0x1800262d2  jz      short loc_1800262DC
0x1800262d4  mov     rcx, rax; this
0x1800262d7  call    ??0CMtfPredictionCandidate@@QEAA@XZ; CMtfPredictionCandidate::CMtfPredictionCandidate(void)
0x1800262dc  mov     [rbx], rax
0x1800262df  xor     eax, eax
0x1800262e1  jmp     short loc_1800262E8
0x1800262e3  mov     eax, 80004005h
0x1800262e8  add     rsp, 20h
0x1800262ec  pop     rbx
0x1800262ed  retn
```
