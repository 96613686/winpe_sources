# Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)

- ea: `0x14000eae0`
- end: `0x14000eb03`
- name: `?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140010b3c`
- `0x140010d34`
- `0x140011100`
- `0x140011a4c`
- `0x140017568`

## callees

- `0x140001fcc`
- `0x14000eae0`

## pseudocode

```c
void __fastcall Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    operator delete(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14000eae0  push    rbx
0x14000eae2  sub     rsp, 20h
0x14000eae6  mov     rbx, rcx
0x14000eae9  mov     rcx, [rcx]; Block
0x14000eaec  test    rcx, rcx
0x14000eaef  jz      short loc_14000EAFD
0x14000eaf1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eaf6  mov     qword ptr [rbx], 0
0x14000eafd  add     rsp, 20h
0x14000eb01  pop     rbx
0x14000eb02  retn
```
