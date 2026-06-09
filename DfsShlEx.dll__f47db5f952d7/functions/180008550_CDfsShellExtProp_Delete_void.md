# CDfsShellExtProp::Delete(void)

- ea: `0x180008550`
- end: `0x180008571`
- name: `?Delete@CDfsShellExtProp@@UEAAXXZ`
- size: `33`
- prototype: `void __fastcall(CDfsShellExtProp *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180008550`
- `0x18000c010`

## pseudocode

```c
void __fastcall CDfsShellExtProp::Delete(CDfsShellExtProp *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 26);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180008550  sub     rsp, 28h
0x180008554  mov     rcx, [rcx+0D0h]
0x18000855b  test    rcx, rcx
0x18000855e  jz      short loc_18000856C
0x180008560  mov     rax, [rcx]
0x180008563  mov     rax, [rax+10h]
0x180008567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000856c  add     rsp, 28h
0x180008570  retn
```
