# _calloc_base

- ea: `0x14001b910`
- end: `0x14001b985`
- name: `_calloc_base`
- size: `117`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x140017ea8`
- `0x1400180f4`
- `0x140018258`
- `0x140019220`
- `0x140019538`
- `0x14001b070`
- `0x14001be2c`
- `0x14001da84`
- `0x14001de20`
- `0x14001e184`
- `0x14001e2b0`
- `0x140020a48`
- `0x140024654`

## callees

- `0x140016ea0`
- `0x140018a40`
- `0x140018a90`
- `0x14001b910`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001b965`
- `KERNEL32!HeapAlloc` at `0x14001b965`

## pseudocode

```c
void *__cdecl calloc_base(size_t Count, size_t Size)
{
  __int64 v2; // r9
  size_t v3; // r8
  unsigned __int64 v4; // rdx
  SIZE_T v5; // rbx
  void *result; // rax

  v3 = Size;
  if ( Count && (v4 = 0xFFFFFFFFFFFFFFE0uLL % Count, 0xFFFFFFFFFFFFFFE0uLL / Count < v3) )
  {
LABEL_10:
    *(_DWORD *)sub_140016EA0(Count, v4, v3, v2) = 12;
    return 0;
  }
  else
  {
    v5 = v3 * Count;
    if ( !(v3 * Count) )
      v5 = 1;
    while ( 1 )
    {
      result = HeapAlloc(hHeap, 8u, v5);
      if ( result )
        break;
      if ( !(unsigned int)sub_140018A40() || !(unsigned int)sub_140018A90(v5) )
        goto LABEL_10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b910  push    rbx
0x14001b912  sub     rsp, 20h
0x14001b916  mov     r8, rdx
0x14001b919  mov     rbx, rcx
0x14001b91c  test    rcx, rcx
0x14001b91f  jz      short loc_14001B92F
0x14001b921  xor     edx, edx
0x14001b923  lea     rax, [rdx-20h]
0x14001b927  div     rbx
0x14001b92a  cmp     rax, r8
0x14001b92d  jb      short loc_14001B972
0x14001b92f  imul    rbx, r8
0x14001b933  mov     eax, 1
0x14001b938  test    rbx, rbx
0x14001b93b  cmovz   rbx, rax
0x14001b93f  jmp     short loc_14001B956
0x14001b941  call    sub_140018A40
0x14001b946  test    eax, eax
0x14001b948  jz      short loc_14001B972
0x14001b94a  mov     rcx, rbx
0x14001b94d  call    sub_140018A90
0x14001b952  test    eax, eax
0x14001b954  jz      short loc_14001B972
0x14001b956  mov     rcx, cs:hHeap; hHeap
0x14001b95d  mov     r8, rbx; dwBytes
0x14001b960  mov     edx, 8; dwFlags
0x14001b965  call    cs:HeapAlloc
0x14001b96b  test    rax, rax
0x14001b96e  jz      short loc_14001B941
0x14001b970  jmp     short loc_14001B97F
0x14001b972  call    sub_140016EA0
0x14001b977  mov     dword ptr [rax], 0Ch
0x14001b97d  xor     eax, eax
0x14001b97f  add     rsp, 20h
0x14001b983  pop     rbx
0x14001b984  retn
```
