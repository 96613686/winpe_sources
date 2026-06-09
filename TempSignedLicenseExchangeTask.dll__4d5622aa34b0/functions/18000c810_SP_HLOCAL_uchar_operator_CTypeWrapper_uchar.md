# SP_HLOCAL<uchar>::operator=(CTypeWrapper<uchar *>)

- ea: `0x18000c810`
- end: `0x18000c83f`
- name: `??4?$SP_HLOCAL@E@@QEAAAEAV0@V?$CTypeWrapper@PEAE@@@Z`
- size: `47`
- prototype: `void **__fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e30`

## callees

- `0x18000c810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c828`

## pseudocode

```c
void **__fastcall SP_HLOCAL<unsigned char>::operator=(void **a1, void *a2)
{
  void *v4; // rcx

  v4 = *a1;
  if ( v4 )
    LocalFree(v4);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18000c810  mov     [rsp+arg_0], rbx
0x18000c815  push    rdi
0x18000c816  sub     rsp, 20h
0x18000c81a  mov     rdi, rcx
0x18000c81d  mov     rbx, rdx
0x18000c820  mov     rcx, [rcx]; hMem
0x18000c823  test    rcx, rcx
0x18000c826  jz      short loc_18000C82E
0x18000c828  call    cs:__imp_LocalFree
0x18000c82e  mov     [rdi], rbx
0x18000c831  mov     rax, rdi
0x18000c834  mov     rbx, [rsp+28h+arg_0]
0x18000c839  add     rsp, 20h
0x18000c83d  pop     rdi
0x18000c83e  retn
```
