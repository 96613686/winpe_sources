# XPathEvaluationContext::GetContextSize(ulong *)

- ea: `0x180005250`
- end: `0x18000526e`
- name: `?GetContextSize@XPathEvaluationContext@@QEAAJPEAK@Z`
- size: `30`
- prototype: `__int64 __fastcall(XPathEvaluationContext *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005950`
- `0x18000b930`

## callees

- `0x180005250`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::GetContextSize(XPathEvaluationContext *this, unsigned int *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v2 + 24LL))(v2, a2);
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x180005250  mov     rcx, [rcx+18h]
0x180005254  test    rcx, rcx
0x180005257  jz      short loc_180005265
0x180005259  mov     rax, [rcx]
0x18000525c  mov     rax, [rax+18h]
0x180005260  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005265  mov     dword ptr [rdx], 1
0x18000526b  xor     eax, eax
0x18000526d  retn
```
