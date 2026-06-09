# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x18000fbb8`
- end: `0x18000fbd8`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b38`

## callees

- `0x18000fbb8`
- `0x18000ff70`

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
0x18000fbb8  sub     rsp, 28h
0x18000fbbc  mov     rax, [rcx]
0x18000fbbf  mov     qword ptr [rcx], 0
0x18000fbc6  test    rax, rax
0x18000fbc9  jz      short loc_18000FBD3
0x18000fbcb  mov     rcx, rax; this
0x18000fbce  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000fbd3  add     rsp, 28h
0x18000fbd7  retn
```
