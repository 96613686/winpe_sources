# CMtfPredictionCandidate::RemoveAllPrimitives(void)

- ea: `0x1800292f0`
- end: `0x18002934f`
- name: `?RemoveAllPrimitives@CMtfPredictionCandidate@@UEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800292f0`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::RemoveAllPrimitives(CMtfPredictionCandidate *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi

  *((_BYTE *)this + 116) = 0;
  v2 = (_QWORD *)*((_QWORD *)this + 6);
  v3 = (_QWORD *)*((_QWORD *)this + 7);
  while ( v2 != v3 )
  {
    try
    {
      if ( *v2 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      ++v2;
    }
    catch ( ... )
    {
      return 2147500037LL;
    }
  }
  *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
  return 0;
}

```

## disassembly

```asm
0x1800292f0  mov     [rsp+arg_0], rbx
0x1800292f5  mov     [rsp+arg_8], rsi
0x1800292fa  push    rdi
0x1800292fb  sub     rsp, 20h
0x1800292ff  mov     rsi, rcx
0x180029302  mov     byte ptr [rcx+74h], 0
0x180029306  mov     rbx, [rcx+30h]
0x18002930a  mov     rdi, [rcx+38h]
0x18002930e  cmp     rbx, rdi
0x180029311  jnz     short loc_18002931F
0x180029313  mov     rax, [rsi+30h]
0x180029317  mov     [rsi+38h], rax
0x18002931b  xor     eax, eax
0x18002931d  jmp     short loc_18002933E
0x18002931f  mov     rcx, [rbx]
0x180029322  test    rcx, rcx
0x180029325  jz      short loc_180029333
0x180029327  mov     rax, [rcx]
0x18002932a  mov     rax, [rax+10h]
0x18002932e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029333  add     rbx, 8
0x180029337  jmp     short loc_18002930E
0x180029339  mov     eax, 80004005h
0x18002933e  mov     rbx, [rsp+28h+arg_0]
0x180029343  mov     rsi, [rsp+28h+arg_8]
0x180029348  add     rsp, 20h
0x18002934c  pop     rdi
0x18002934d  retn
```
