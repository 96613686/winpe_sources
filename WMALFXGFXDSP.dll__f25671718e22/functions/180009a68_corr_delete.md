# corr_delete

- ea: `0x180009a68`
- end: `0x180009a8b`
- name: `corr_delete`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d60`
- `0x1800098e8`

## callees

- `0x180009a68`
- `0x180009a94`

## pseudocode

```c
__int64 __fastcall corr_delete(void **a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = corr_free(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009a68  push    rbx
0x180009a6a  sub     rsp, 20h
0x180009a6e  mov     rbx, rcx
0x180009a71  mov     rcx, [rcx]; Block
0x180009a74  test    rcx, rcx
0x180009a77  jz      short loc_180009A85
0x180009a79  call    corr_free
0x180009a7e  mov     qword ptr [rbx], 0
0x180009a85  add     rsp, 20h
0x180009a89  pop     rbx
0x180009a8a  retn
```
