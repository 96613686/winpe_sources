# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1400033d0`
- end: `0x1400033f1`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005934`

## callees

- `0x1400033d0`
- `0x1400042f4`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    wil::details::FreeProcessHeap(v2, a2);
}

```

## disassembly

```asm
0x1400033d0  sub     rsp, 28h
0x1400033d4  mov     rax, [rcx]
0x1400033d7  mov     qword ptr [rcx], 0
0x1400033de  test    rax, rax
0x1400033e1  jz      short loc_1400033EB
0x1400033e3  mov     rcx, rax; this
0x1400033e6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400033eb  add     rsp, 28h
0x1400033ef  retn
```
