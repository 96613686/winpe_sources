# MemAlloc(void * *,ulong)

- ea: `0x180011930`
- end: `0x180011962`
- name: `?MemAlloc@@YAHPEAPEAXK@Z`
- size: `50`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003140`
- `0x180003500`
- `0x18000367c`
- `0x180003850`
- `0x180003920`
- `0x180003adc`
- `0x18000ae20`
- `0x18000af00`

## callees

- `0x180014010`

## pseudocode

```c
_BOOL8 __fastcall MemAlloc(void **a1, unsigned int a2)
{
  void *v3; // rax

  v3 = (void *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, a2);
  *a1 = v3;
  return v3 != 0;
}

```

## disassembly

```asm
0x180011930  push    rbx
0x180011932  sub     rsp, 20h
0x180011936  mov     rbx, rcx
0x180011939  mov     edx, edx
0x18001193b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180011942  mov     rax, [rcx]
0x180011945  mov     rax, [rax+18h]
0x180011949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194e  mov     rdx, rax
0x180011951  mov     [rbx], rax
0x180011954  xor     eax, eax
0x180011956  test    rdx, rdx
0x180011959  setnz   al
0x18001195c  add     rsp, 20h
0x180011960  pop     rbx
0x180011961  retn
```
