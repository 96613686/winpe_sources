# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x140003388`
- end: `0x1400033a8`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005648`

## callees

- `0x140003388`
- `0x14000409c`

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
0x140003388  sub     rsp, 28h
0x14000338c  mov     rax, [rcx]
0x14000338f  mov     qword ptr [rcx], 0
0x140003396  test    rax, rax
0x140003399  jz      short loc_1400033A3
0x14000339b  mov     rcx, rax; this
0x14000339e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400033a3  add     rsp, 28h
0x1400033a7  retn
```
