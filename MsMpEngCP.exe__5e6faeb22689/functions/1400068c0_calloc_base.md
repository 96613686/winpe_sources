# _calloc_base

- ea: `0x1400068c0`
- end: `0x140006935`
- name: `_calloc_base`
- size: `117`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1400048e8`
- `0x140004b34`
- `0x140004c98`
- `0x140005a80`
- `0x140005ec8`
- `0x140006db4`
- `0x140007d40`
- `0x1400080a4`
- `0x1400082c8`
- `0x14000a240`

## callees

- `0x140005370`
- `0x14000689c`
- `0x1400068c0`
- `0x140009b00`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140006915`
- `KERNEL32!HeapAlloc` at `0x140006915`

## pseudocode

```c
void *__cdecl calloc_base(size_t Count, size_t Size)
{
  SIZE_T v2; // rbx
  void *result; // rax

  if ( Count && 0xFFFFFFFFFFFFFFE0uLL / Count < Size )
  {
LABEL_10:
    *(_DWORD *)sub_14000689C() = 12;
    return 0;
  }
  else
  {
    v2 = Size * Count;
    if ( !(Size * Count) )
      v2 = 1;
    while ( 1 )
    {
      result = HeapAlloc(hHeap, 8u, v2);
      if ( result )
        break;
      if ( !(unsigned int)sub_140005370() || !(unsigned int)sub_140009B00(v2) )
        goto LABEL_10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400068c0  push    rbx
0x1400068c2  sub     rsp, 20h
0x1400068c6  mov     r8, rdx
0x1400068c9  mov     rbx, rcx
0x1400068cc  test    rcx, rcx
0x1400068cf  jz      short loc_1400068DF
0x1400068d1  xor     edx, edx
0x1400068d3  lea     rax, [rdx-20h]
0x1400068d7  div     rbx
0x1400068da  cmp     rax, r8
0x1400068dd  jb      short loc_140006922
0x1400068df  imul    rbx, r8
0x1400068e3  mov     eax, 1
0x1400068e8  test    rbx, rbx
0x1400068eb  cmovz   rbx, rax
0x1400068ef  jmp     short loc_140006906
0x1400068f1  call    sub_140005370
0x1400068f6  test    eax, eax
0x1400068f8  jz      short loc_140006922
0x1400068fa  mov     rcx, rbx
0x1400068fd  call    sub_140009B00
0x140006902  test    eax, eax
0x140006904  jz      short loc_140006922
0x140006906  mov     rcx, cs:hHeap; hHeap
0x14000690d  mov     r8, rbx; dwBytes
0x140006910  mov     edx, 8; dwFlags
0x140006915  call    cs:HeapAlloc
0x14000691b  test    rax, rax
0x14000691e  jz      short loc_1400068F1
0x140006920  jmp     short loc_14000692F
0x140006922  call    sub_14000689C
0x140006927  mov     dword ptr [rax], 0Ch
0x14000692d  xor     eax, eax
0x14000692f  add     rsp, 20h
0x140006933  pop     rbx
0x140006934  retn
```
