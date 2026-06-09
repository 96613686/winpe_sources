# wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::~unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>(void)

- ea: `0x14000a0c4`
- end: `0x14000a0e4`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400114ba`

## callees

- `0x140002504`
- `0x14000a0c4`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>(
        void **a1,
        unsigned __int64 a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x14000a0c4  sub     rsp, 28h
0x14000a0c8  mov     rax, [rcx]
0x14000a0cb  mov     qword ptr [rcx], 0
0x14000a0d2  test    rax, rax
0x14000a0d5  jz      short loc_14000A0DF
0x14000a0d7  mov     rcx, rax; void *
0x14000a0da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a0df  add     rsp, 28h
0x14000a0e3  retn
```
