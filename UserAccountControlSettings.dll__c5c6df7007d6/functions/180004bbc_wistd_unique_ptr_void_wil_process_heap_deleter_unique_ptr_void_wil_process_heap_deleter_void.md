# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180004bbc`
- end: `0x180004bdc`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(DirectUI **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061a0`

## callees

- `0x180004bbc`
- `0x1800051fc`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        DirectUI **a1,
        void *a2)
{
  DirectUI *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    DirectUI::HFree(v2, a2);
}

```

## disassembly

```asm
0x180004bbc  sub     rsp, 28h
0x180004bc0  mov     rax, [rcx]
0x180004bc3  mov     qword ptr [rcx], 0
0x180004bca  test    rax, rax
0x180004bcd  jz      short loc_180004BD7
0x180004bcf  mov     rcx, rax; this
0x180004bd2  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x180004bd7  add     rsp, 28h
0x180004bdb  retn
```
