# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180002ff0`
- end: `0x180003011`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046f4`

## callees

- `0x180002ff0`
- `0x180003704`

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
0x180002ff0  sub     rsp, 28h
0x180002ff4  mov     rax, [rcx]
0x180002ff7  mov     qword ptr [rcx], 0
0x180002ffe  test    rax, rax
0x180003001  jz      short loc_18000300B
0x180003003  mov     rcx, rax; this
0x180003006  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000300b  add     rsp, 28h
0x18000300f  retn
```
