# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180003004`
- end: `0x180003024`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043b4`

## callees

- `0x180003004`
- `0x1800034e0`

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
0x180003004  sub     rsp, 28h
0x180003008  mov     rax, [rcx]
0x18000300b  mov     qword ptr [rcx], 0
0x180003012  test    rax, rax
0x180003015  jz      short loc_18000301F
0x180003017  mov     rcx, rax; this
0x18000301a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000301f  add     rsp, 28h
0x180003023  retn
```
