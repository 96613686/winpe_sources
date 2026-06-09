# wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)

- ea: `0x18000c928`
- end: `0x18000c948`
- name: `?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c698`
- `0x18000dc7c`
- `0x18000dd80`
- `0x18000e434`
- `0x18000f880`

## callees

- `0x1800022a0`
- `0x18000c928`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000c928  sub     rsp, 28h
0x18000c92c  mov     rax, [rcx]
0x18000c92f  mov     qword ptr [rcx], 0
0x18000c936  test    rax, rax
0x18000c939  jz      short loc_18000C943
0x18000c93b  mov     rcx, rax; void *
0x18000c93e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c943  add     rsp, 28h
0x18000c947  retn
```
