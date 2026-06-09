# XPathEvaluationContext::GetContextPosition(ulong *)

- ea: `0x18000522c`
- end: `0x18000524a`
- name: `?GetContextPosition@XPathEvaluationContext@@QEAAJPEAK@Z`
- size: `30`
- prototype: `__int64 __fastcall(XPathEvaluationContext *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005940`
- `0x18000be50`

## callees

- `0x18000522c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::GetContextPosition(XPathEvaluationContext *this, unsigned int *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v2 + 40LL))(v2, a2);
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000522c  mov     rcx, [rcx+18h]
0x180005230  test    rcx, rcx
0x180005233  jz      short loc_180005241
0x180005235  mov     rax, [rcx]
0x180005238  mov     rax, [rax+28h]
0x18000523c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005241  mov     dword ptr [rdx], 1
0x180005247  xor     eax, eax
0x180005249  retn
```
