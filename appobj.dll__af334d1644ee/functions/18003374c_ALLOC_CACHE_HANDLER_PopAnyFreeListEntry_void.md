# ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)

- ea: `0x18003374c`
- end: `0x180033793`
- name: `?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ`
- size: `71`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180033184`

## callees

- `0x18003374c`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180033778`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180033778`

## pseudocode

```c
PSLIST_ENTRY __fastcall ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(ALLOC_CACHE_HANDLER *this)
{
  _QWORD *v1; // rbx
  PSLIST_ENTRY result; // rax
  unsigned int i; // edi

  v1 = (_QWORD *)*((_QWORD *)this + 3);
  result = 0;
  if ( v1 )
  {
    for ( i = 0; (unsigned __int64)i < v1[2]; ++i )
    {
      if ( !result )
        result = InterlockedPopEntrySList((PSLIST_HEADER)(*v1 + v1[1] * i));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003374c  mov     [rsp+arg_0], rbx
0x180033751  push    rdi
0x180033752  sub     rsp, 20h
0x180033756  mov     rbx, [rcx+18h]
0x18003375a  xor     eax, eax
0x18003375c  test    rbx, rbx
0x18003375f  jz      short loc_180033788
0x180033761  xor     edi, edi
0x180033763  cmp     [rbx+10h], rax
0x180033767  jbe     short loc_180033788
0x180033769  test    rax, rax
0x18003376c  jnz     short loc_18003377E
0x18003376e  mov     ecx, edi
0x180033770  imul    rcx, [rbx+8]
0x180033775  add     rcx, [rbx]; ListHead
0x180033778  call    cs:__imp_InterlockedPopEntrySList
0x18003377e  inc     edi
0x180033780  mov     ecx, edi
0x180033782  cmp     rcx, [rbx+10h]
0x180033786  jb      short loc_180033769
0x180033788  mov     rbx, [rsp+28h+arg_0]
0x18003378d  add     rsp, 20h
0x180033791  pop     rdi
0x180033792  retn
```
