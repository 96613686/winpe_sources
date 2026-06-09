# wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)

- ea: `0x14001775c`
- end: `0x140017785`
- name: `??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018060`

## callees

- `0x1400051cc`
- `0x14001775c`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(
        __int64 a1)
{
  wil::details **v1; // rdx
  wil::details *v2; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = *(wil::details ***)a1;
    v2 = **(wil::details ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      wil::details::FreeProcessHeap(v2, v1);
  }
}

```

## disassembly

```asm
0x14001775c  sub     rsp, 28h
0x140017760  cmp     byte ptr [rcx+10h], 0
0x140017764  jz      short loc_140017780
0x140017766  mov     rdx, [rcx]; void *
0x140017769  mov     rax, [rcx+8]
0x14001776d  mov     r8, [rdx]
0x140017770  mov     [rdx], rax
0x140017773  test    r8, r8
0x140017776  jz      short loc_140017780
0x140017778  mov     rcx, r8; this
0x14001777b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140017780  add     rsp, 28h
0x140017784  retn
```
